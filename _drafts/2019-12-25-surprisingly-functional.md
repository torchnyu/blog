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
absolutely necessary, but it's certainly moving in that direction. I
will say that functional programming is incredibly fun, interesting
and will certainly make you a more informed programmer, if not a
better one.

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

  Libraries such as React and Redux have taken these concepts and
  applied them to the JavaScript ecosystem. It's only a matter of time
  before it spreads everywhere.

- A good type system is worth it. If your idea of types is Java and
  its endlessly verbose syntax, then functional programming languages
  will blow your mind. Languages like OCaml or Haskell have very good
  type inference which means you'll almost never have to specify a
  type. In general functional programming type systems get in your way
  far less often.

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

