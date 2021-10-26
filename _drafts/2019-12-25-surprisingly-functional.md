---
title:  "Surprisingly Functional: An FAQ For Functional Programming"
date:   2019-12-23 20:00:00 -0700
---

Functional programming. Maybe you've heard of it, maybe you
haven't. Maybe you've been told that it's over complicated
monad-functor-monoid nonsense used by
[witches](https://aphyr.com/posts/342-typing-the-technical-interview)
and overeager nerds. Maybe you've heard that React or Redux uses
functional programming, kinda [nodded and
blinked](https://media.giphy.com/media/3ELtfmA4Apkju/giphy.gif) and
moved on with your life. Regardless, it's undeniable that functional
programming is having a little bit of a moment. Facebook is using
ReasonML, JavaScript libraries are adopting functional ideas like
immutability, C# is adding non nullable types, and so on.

I won't go as far as to say that functional programming knowledge is
absolutely necessary. I will say that functional programming is
incredibly fun, interesting and will certainly make you a more
informed programmer, if not a better one.

# What Is Functional Programming?

Functional programming is a paradigm of programming based around
functions, immutable data and declarative programming. I'll define
each of these terms in succession.

# But...why?

At this point, you're probably thinking "but...why should I learn
functional programming?". And I can't really give a single answer to
this question. The problem is that functional programming is less a
cohensive paradigm as much as a melange of various ideas. So here's a
few reasons.

You should learn functional programming because...

- First class functions are in or coming to practically every
  programming language. Whether it's
  [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function),
  [Python](https://dbader.org/blog/python-first-class-functions),
  [Java](https://www.geeksforgeeks.org/lambda-expressions-java-8/) or
  any other language, functions that can be passed as arguments or
  returned from functions are crucial for modern development.

- Programming through data is extremely important. Whether it's
  purity, immutability or any other fancy term, functional programming
  emphasizes data above all. One way of describing functional
  programming is that it allows you to think more about how your data
  is organized and transformed versus the nitty gritty of your
  algorithms. Rob Pike famously said:

  > Data dominates. If you've chosen the right data structures and
  > organized things well, the algorithms will almost always be
  > self-evident. Data structures, not algorithms, are central to
  > programming.

  By using structures called algebraic data types, functional programs
  allow you to structure your data in ways that make manipulating and
  describing them extremely simple.

  Libraries such as React and Redux have taken concepts such as
  immutability and reactivity, and applied them to the JavaScript
  ecosystem. It's only a matter of time before it spreads everywhere.

- A good type system is worth it. If your idea of types is Java and
  its endlessly verbose syntax, then functional programming languages
  will blow your mind. Languages like OCaml or Haskell have very good
  type inference which means you'll almost never have to specify a
  type. Functional programming type systems get in your way far less
  often.

- No more NullPointerExceptions. Many functional languages feature
  non-nullability, which basically means values cannot be null by
  default. This fixes what Tony Hoare called the "billion dollar
  mistake" in programming. In short, no segfaults, no
  NullPointerExceptions, no "undefined" is not a function.

- It'll give you insight into a different paradigm and different way
  of thinking. Even if you don't use a functional language in your day
  to day programming, you can take the ideas and concepts from
  functional programming and apply it to your problems. MapReduce is a
  very famous example of such application.

# What is Functional Programming

## Pure Functions

Functional programming is a discipline centered around functions,
specifically what are called *pure* functions. A pure function are
very similar to the functions you deal with in math, in that they
always give the same result when they are called with the same
parameters. Here is a pure function in JavaScript:

```
const pure = (x) => x + 2
```

Or if you prefer Haskell:
```
pure x = x + 2
```

No matter how many times you call `pure(10)`, it'll always give
`12`. A non pure function in JavaScript would be:

```
const nonPure = (x) => {
	console.log(x);
}
```

If I call `nonPure(10)` one time, I'll get an output of:

```
10
```
But if I call it two times, I'll get:

```
10
10
```

## Side Effects

This act of printing is called a *side-effect*. Side-effects are when
a function has some effect or change that is externally visible.

Pure functions have some nice properties. Because they always produce
the same result given the same input, they're very easy to cache, or
as we call it *memoize*:

```
const memoize = (f) => {
  let cache = new Map();
  return (arg) => {
	if (cache.has(arg)) {
		return cache.get(arg);
	}

    const value = f(arg);
	cache.set(arg, value);
	return value;
  }
}
```

The reason the above function works[^1] is because given a specific set of
arguments, a pure function must always return the same
value. Therefore we can just record this value, and instead of calling
the function, we can return the value.

[^1]: Fun aside, there were a couple gotchas I avoided in writing this
    function. Indeed, I decided to write only for the single argument
    case for a reason.


## Mutation

Another example of a side effect is mutation, basically when code
changes data:

```
const pushFive = (arr) => {
  arr.push(5);
}

const arr = [];

pushFive(arr); // arr = [5]
pushFive(arr); // arr = [5, 5]
```

Note how with each call of `pushFive`, `arr` changes its value.

Therefore, in functional languages, we primarily deal with *immutable*
values, i.e. values that cannot change. This may seem confusing or
even impractical; how do you write code without changing values? It
may take some practice, but it's not hard to write code using
immutable values.

For instance, in JavaScript, there's a wonderful operator called the
spread operator (...), which lets us use arrays immutably. Let's write
`pushFive` again:

```
const pushFive = (arr) = >{
  return [...arr, 5];
}

const arr = [];
pushFive(arr); // [5]
pushFive(arr); // [5]
```

What's the difference? In this version of `pushFive`, we use the
spread operator to copy `arr`'s contents into a new array with an
extra element, `5`. We then return this new array. What's cool about
this approach is that `arr` is never mutated. We can call
`pushFive(arr)` all we want, and as long as `arr` is the same, it'll
produce the same result. What's less cool is that we're copying `arr`
each time we call this. If `arr` is 2000 elements, that could take a
long time[^2]. Of course, in a lot of cases arrays are small and
computers are fairly good at copying small arrays, but it is something
to consider.

[^2]: Technically this is a shallow copy and therefore isn't *that* slow but still.

This practice of creating a new data structure instead of mutating
shows up a lot when we write immutable code. Since copying can be
quite slow, there's an entire field of immutable data structures
dedicated to designing data structures that seem like they're copying
the data, but actually reuse as much as possible. If that doesn't make
a lot of sense to you, I'd recommend reading up on immutable data
structures.

## Abstract Data Types

Switching gears entirely, let's talk about one of my favorite
functional programming features. They don't always show up in
functional languages, but they often do[^3].

[^3]: Specifically in the ML/Haskell lineage.

In almost every programming language we have some way to combine types
into a struct/object/tuple, basically a collection of types.

```
struct Person {
  int age;
  char* name;
  bool is_student;
}

class Person {
  int age;
  String name;
  boolean isStudent;
}

struct Person {
  age: u32,
  name: String,
  is_student: bool
}
```

You can think of structs as a type that contains an int AND a string
AND a boolean. We call these *product* types in functional languages.

However, a lot of languages lack a way to express *OR*, as in a type
that is an int OR a string. Fortunately, functional languages have a
solution in the form of *sum* types[^4]

[^4]: Why sum vs product? Well if you think about the number of
    possible values a type can have, a product type takes the number
    of values its first element can have and multiplies it by the
    number of values its second element can have, and so on. A sum
    type takes the number of values its first variant can have and
    adds it to the number of values its second variant can have, and
    so on.

Basically we define a type `Student` that has two possible variants
(or as they're traditionally called, type constructors): `HighSchool`
or `College`. Doing this in Rust:

```
enum Student {
  HighSchool,
  College
}
```

These variants can contain values, say a string for the student's
major in college.

```
enum Student {
  HighSchool,
  College {
    major: String
  }
}
```

Note that when a value of type `Student` is the `College` variant,
there's a field, `major`, that we can access. When it is the
`HighSchool` variant, we cannot access `major` because `HighSchool`
doesn't have that field.

Fields can be generic:

```
enum Student<T> {
  HighSchool,
  College {
    major: T
  }
}
```

As it turns out, wanting this OR that is very common. In fact, there's
a case that you, me, and every programmer uses, day in and day out:
null values. Within most languages there's some concept of
null/nil/None. We can express this with sum types!

```
enum Option<T> {
  None,
  Some(T)
}
```

Note that writing `Some(T)` is a way to have a variant take a field
without naming it, something called tuple structs in Rust.

Because we can express null with sum types, we can actually remove
null from the language entirely and substitute it with `Option`. This
may seem weird, but it's a massive improvement. If you've written code
at a place with code quality standards or if you're familiar with
defensive programming, you'll have written a lot of `assert(foo !=
null)`.

We have to write this preamble because in most languages `foo` can
always be `null`. The only way to confirm is to read through the
codebase and double check that `foo` is never assigned to `null`. Even
then, if the codebase is a library, a user could pass in
`null`. Therefore, any field access, any method call could cause a
`NullPointerException` or a segfault. In functional languages, we know
that any field access, any method call can **never** cause a
`NullPointerException` or a segfault.

Instead, if a value can be null, we wrap it in `Option`:
`Option<String>`, `Option<AbstractDataManager>`. Then, when we need to
use it, we can use what's called pattern matching. Pattern matching is
when you take a value and depending on the structure of the value, you
execute different branches of code. It's kind of like a case/switch
but significantly more powerful. In Rust, we use the `match` keyword
to pattern match:

```
match foo {
  Some(f) => {
    println!("foo is not null: {}", f);
  },
  None => {
    println!("foo is null");
  }
}
```

This code takes a variable `foo`, and depending on whether it's `Some`
or `None`, it executes different code. You can think of this as
"unwrapping" `foo` from `Option<T>` to `T`, while also handling the
case where `foo` could be `None`.

Pattern matching is incredibly useful 
