---
title:  "Think The Worst: Error Handling"
date:   2020-05-24 20:00:00 -0700
---

Pessimism is a severely underrated quality of good programmers. It's
easy to write code that works when everything goes well. It's
profoundly hard to write code that doesn't screw everything up when
something goes wrong.

Part of this difficulty is technical: Software at scale is a series of
components that are connected in various, complicated ways. One
component failing can cascade, creating subtle issues that are hard to
diagnose. Sometimes the issue isn't even in the components, but how
they're connected and configured. Dan Luu talks about configuration
issues [here](https://danluu.com/postmortem-lessons/).

Part of this difficulty is psychological: People don't like thinking
about errors and unhappy paths. Developers ride off the validation of
code that compiles, that passes all the tests, that works. Thinking
about errors goes against that. At an individual level this can mean a
developer willfully ignoring the unhappy path. At a team level this
can mean shutting down or ignoring pessimistic developers. At an org
level this can manifest as a lack of resources allocated towards
contingencies.

How can we solve these difficulties? Become a pessimist! Albeit one
with tact. Nobody likes an Eeyore bemoaning that everything will go
wrong. Plus people are naturally prickly when it comes to discussing
their code failing. Try to communicate your pessimism tactfully and in
small quantities.

This won't be a full guide to pessimistic programming. There's quite a
few aspects that either I don't know enough about, or don't feel like
discussing. Always try to be learning more about potential problems
that can arise.

# Input and Output

Whenever you write a function, you should always scrutinize your
arguments as much as possible. Can they be null? What values are
valid? When could an invalid value be passed in? What should happen in
that case? What is valid output?

For instance, let's take a super simple function in C:

   int get(int* arr, int n) {
      return arr[n];
   }

Okay okay there's some obvious issues here. We don't know how big the
array is so `n` could easily be bigger than the length. Let's write a
little more robust one:

   int get(int* arr, int len, int n) {
     if (n < len) {
       return arr[n];
	 }
	 return -1;
   }

The function checks if the index is in the bounds of the array. If it
is, it returns the element, otherwise it returns -1.

What could go wrong? A lot actually. Let's go through the issues.

- `arr` is null/not a valid pointer

Classic but bites everybody. Always include a null check!

   int get(int* arr, int len, int n) {
     if (n < len && arr != null) {
       return arr[n];
	 }
	 return -1;
   }

- What if `arr` is allowed to have negative values? -1 is a valid value

Good point! We'll need to do some more bookkeeping. For now let's
imagine we do some proper C error handling with `goto` or
`errno`. I'll leave that to the reader.

- What if `arr[n]` doesn't have anything in it! What will it return?

Another good point myself. If we're good C citizens, we've allocated
`arr` with calloc or it's statically allocated. If we're not, it's
been allocated with good ol' `malloc` and therefore may have old data
in it. `arr[n]` could return anything.

- What if `n` is negative?

Classic issue with letting `int` index arrays. Always check that
indices aren't negative.

There's almost certainly other issues. What about portability? Integer
overflow?

# Error Handling

Okay okay using C is cheating. Let's use something more civilized like
Java. Let's say we're designing a TodoList app that fetches your tasks
from a database.

```
List<Task> getTasks(User user) {
  String GET_TASKS_QUERY = String.format("SELECT * FROM tasks WHERE user_id = %s", user.id);
  List<Task> tasks = execute(GET_TASKS_QUERY);
  return tasks;
}
```

Looks pretty good right? If you've been paying attention the answer
should be NO. What if `user` is null? What about if there's no tasks?
What if the id is invalid? What if we can't connect to the database?

All of these questions involve error states: user is null, tasks are
empty, id is invalid. From there, we need to figure out the potential
ways of handling these various states.

For instance, if user is null, perhaps we should throw an
exception. Except...then from a user-facing perspective the app will
just crash. Exceptions are great for programmers who are used to
reading stack traces. Not so much for users. Maybe then we shouldn't
throw an exception but surface an error message in the app. Maybe we
should direct the user to a registration screen.

These are all valid options, but it wholly depends on a few
conditions. For instance, let's take two `getUser` functions:

```
User getUser(String username, String password) {
  String hashedPassword = hashPassword(password);
  String GET_USER_QUERY = String.format("SELECT * FROM users" +
                                        "WHERE username = %s AND password = %s",
										username, hashedPassword);
  User user = execute(GET_USER_QUERY);
  return user
}
```

And
```
User getUser(String username, String password) {
  String hashedPassword = hashPassword(password);
  String GET_USER_QUERY = String.format("SELECT * FROM users" +
                                        "WHERE username = %s AND password = %s",
										username, hashedPassword);
  User user = execute(GET_USER_QUERY);
  if (user != null) {
    return user
  } else {
    throw new UserException("User not found");
  }
}
```

In the first case, if we call `getUser` and pass the result into our
`getTasks` function, our user could be `null` for perfectly normal
reasons: the password is incorrect, or maybe the user doesn't
exist. In the second case, the user cannot be undefined. If it is, we 
