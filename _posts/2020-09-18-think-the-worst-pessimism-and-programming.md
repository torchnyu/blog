---
title:  "Think The Worst: The Value of Pessimism"
date:   2020-09-18 10:00:00 -0700
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
wrong. People are naturally prickly when it comes to discussing
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
```
   int get(int* arr, int n) {
      return arr[n];
   }
```
Okay okay there's some obvious issues here. We don't know how big the
array is so `n` could easily be bigger than the length. Let's write a
little more robust one:
```
   int get(int* arr, int len, int n) {
     if (n < len && n >= 0) {
       return arr[n];
     }
     return -1;
   }
```
The function checks if the index is in the bounds of the array. If it
is, it returns the element, otherwise it returns -1.

What could go wrong? A lot actually. Let's go through the issues.

- `arr` is null/not a valid pointer

Classic but bites everybody. Always include a null check!
```
   int get(int* arr, int len, int n) {
     if (n < len && n >= 0 && arr != null) {
       return arr[n];
     }
     return -1;
   }
```
- What if `arr` is allowed to have negative values? -1 is a valid value

Good point! We'll need to do some more bookkeeping. For now let's
imagine we do some proper C error handling with `goto` or
`errno`. I'll leave that to the reader.

- What if `arr[n]` doesn't have anything in it! What will it return?

Another good point myself. If we're good C citizens, we've allocated
`arr` with calloc or it's statically allocated. If we're not, it's
been allocated with good ol' `malloc` and therefore may have old data
in it. `arr[n]` could return anything.

There's almost certainly other issues. What about portability? Integer
overflow?

# Error Handling

Okay okay using C is cheating. Let's use something more civilized like
Java. Let's say we're designing a TodoList app that fetches your tasks
from a database.

```
List<Task> getTasks(User user) {
  String GET_TASKS_QUERY = String.format(
    "SELECT * FROM tasks WHERE user_id = %s",
    user.id
  );
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
throw an error.

Neither of these is necessarily better. When we call the second
`getUser`, we have to remember that it can throw an exception and
handle it accordingly. Again, your users don't expect a generic
"Internal Server Error" when they put in the wrong password. Likewise
when something actually goes wrong, there should be a way of
distinguishing that from just a normal wrong password.

However the first case can cause programmer bugs because someone may
call it assuming the user exists and end up with a
NullPointerException.

Indeed, both options are flawed. In either case, we don't distinguish
between a user not existing and a user having an invalid
password. This is a [valid security
concern](https://security.stackexchange.com/questions/158075/is-it-unsafe-to-show-message-that-username-account-does-not-exist-at-login)
but pragmatically, it's generally fine to display different messages
for invalid password versus no account and certainly more useable.

These are all considerations you should be thinking about while
writing code. What can throw an exception? What should throw
an exception? Who should catch it?

# Pessimism in Programming Languages

One interesting example of pessimism is in programming
languages. Specifically, let's talk about Rust. I'm a huge fan of
Rust. It's a very well designed language with a lot of great
features. One important quality that I value is that Rust is deeply
pessimistic.

The best feature to explain this pessimism is null values. Rust has
what's called a non-nullable type system. In a non-nullable type
system, null values are not allowed by default. For instance, Rust
will not let you do:

```
let foo = null;
```

In fact, null doesn't even exist! There is no such value that all
types can be assigned to it.

Instead, if you want to have a value that may or may not exist, you
can write it in an `Option` type. `Option` types can either be `None`
or `Some(T)` where `T` is the type of your value.

```
let mut foo: Option<i32> = None;

foo = Some(10);
```

Why is this better? Well for one it means that if a value is not in an
`Option`, you can use it with impunity. Pass it into functions; send
it to space; no matter what, it'll exist. The second benefit is that
to use an `Option` value, you must handle the None case.

```
let foo = Some(10);
let bar = Some(20);

let baz = foo + bar // Won't work
```

That won't work because to add the numbers, we need to ensure that
they're not None.

This may sound tedious, but it really isn't. What this means is that
we have to be pessimistic about certain values. For instance, take
this `get_user` function:

```
fn get_user(username: String, password: String) -> Option<User>
```

What this expresses is that we're passing in a username and password,
both of which we know are not null and exist, but that we might get
back a user, or we might not.

When we use this result, we **have** to handle the case where the user
might not exist.
```
let user = get_user(username, password);
if let Some(user) = user {
  // If the user exists, yay! We keep going
} else {
  // Otherwise, we gotta do something
}
```

This extends to errors. Generally Rust does not have
exceptions[^1]. Instead, there is a type `Result` that returns either
the value, `Ok(T)` or an error value `Err(E)`. This allows you to
express functions that can fail and give an error:

```
fn get_user(username: String, password: String) -> Result<User>
```

Now, when we call `get_user`, we know that it may return an error, but
if it doesn't, it must return a user.

[^1]: Kinda. There's panics, but those are rare and not recommended
    for most errors.

Notice how we've encoded the two different Java `getUser` functions,
but in a way where the caller knows what must happen and is forced to
handle either the null user or the potential error.

What's nice about this version is that once we've done these checks
and handled the potential issues, we know that the values are good and
won't cause any additional problems.

# Error Handling In Life

I wanna close out with one last usecase. I've noticed that some people
don't always think about potential issues in their life. Granted,
there's some issues one really shouldn't worry about. Like, who would
spend time worrying about a global pandemic? That wouldn't
happen.

*ahem*

But I digress. Pessimism is a good attribute in how you interact with
others. While it's wonderful to have strong convictions, you should
always ask yourself the same question: What if I'm wrong?

You can argue about how Rust is the greatest programming language or
how performance doesn't matter, but every so often, you should ask
yourself if you're wrong.

Some people don't like doing this because they're afraid that if they
realize that they're wrong, that's bad. I believe that you should
realize you're wrong all the time. That's how you get better.

Likewise, people tend to assume that they're on the right path in
life. They assume that they're in college doing x major and hanging
out with these people and listening to this music. But what if they're
not? Try asking yourself that sometime. Are you on the right path? And
if not, what is the right path?

This sounds scary. However to me, it also sounds exciting. It means
that you can find yourself a better life.

Why not?
