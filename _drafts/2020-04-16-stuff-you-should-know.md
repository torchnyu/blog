---
title:  "Stuff You Should Know"
date:   2020-05-16 20:00:00 -0700
---

Nobody gets the same CS degree. Everybody takes courses with different
professors at different times---and sometimes in completely different
worlds. However there are some bit and bytes of knowledge that I
believe every CS major should come out knowing. Of course, this list
of knowledge is colored by my experiences and is personal to me. There
will be some obvious omissions and extraneous additions. But I
genuinely believe if you can come out of NYU CS with these skills,
you'll be in great shape.

# Systems

Probably my biggest positive experience in NYU CS has been the systems
classes. I was lucky enough to take both Computer Systems Organization
and Operating Systems with great professors. In each course, there was
a professor who had a reputation of holding a challenging course. I'd
recommend taking the course with those professors. I'm not going to
say who, but it's readily apparent if you ask around.

Here's what you should know coming out of your systems classes:

- How to write a non-trivial C program. Ideally you should have
  written malloc and maybe one other challenging program like a basic
  kernel, albeit with starter code. You should be able to write
  something like a binary tree or a hash table from scratch without
  too much trouble.
- How virtual versus physical memory works. Alongside that how process
  isolation works.
- Memory layout of a C program.
- Scheduling OS processes
- Concurrency and why it's hard
- Memory allocation and why it's hard
- System calls
- Buffer overflow attacks

# Programming Languages

I'm particularly interested in programming languages so this area
might be a little larger than most people's. Part of the challenge is
that NYU doesn't really teach a lot about programming languages. Which
is a shame, since it's a foundational part of computer science.

Here's what you should know:

- 1-2 programming languages at a sufficient level to say, write an
  easy interview question^[1].
- What is a compiler at a high level? What is an interpreter? Give
  examples of both
- An example of a language that is compiled and interpreted
- A programming language that has first class functions such as:
  Python, JavaScript, Ruby, Haskell, Rust, Kotlin
- Automatic memory management. Provide an example of a language
  that has automatic memory management and one that doesn't
- What are static types? What are dynamic types? Provide an example of
  a language that has static typing and one that has dynamic typing.
- What is recursion? How can we use it effectively?

Okay and here's what I'd love for students to know:

- The high level steps that a compiler takes to compile code. The high
  level steps an interpeter takes to run code.
- A functional programming language such as: Haskell, OCaml, Racket,
  Standard ML, etc.
- A functional-ish languagel like: Rust, Ruby, JavaScript, TypeScript,
  Kotlin, Swift
- A basic calculator parser that turns arithmetic expressions such as
  `5 * 2 - 3` into reverse polish notation: 5 2 * 3 -
- What is lambda calculus? How is it useful?
- What is tail call optimization?

[1]: Bad benchmark, but I couldn't come up with any better one.

If you can, consider taking a programming languages elective or the
graduate level compilers class. They'll both be a little challenging
but they're great experiences.

# Math

Ah yes math. My math nerd friends say that CS is just applied math and
they're not entirely wrong. A good math background is extremely
important. And yet, I see plenty of CS students who dismiss math or
only care about certain subjects.

- What is a proof? Prove that the square root of 2 is irrational.
- All of the standard proof techniques such as strong/weak induction,
  proof by contradiction, proof by counter example
- Basic linear algebra such as matrices; vectors; row space, column
  space, null space/kernel; eigenvectors and eigenvalues; determinants.
- Combinatorics and discrete probability. You should know stuff like n
  choose k, factorial, Bayesian probability, etc.
- Law of Large Numbers and Central Limit Theorem.
- What is a limit^[2]?
- What is a function? What is a total function?


# Computation

When I say computation I mean all of the more theoretical parts of
computer science such as algorithms, data structures, automata,
complexity classes, etc. Unfortunately the only classes NYU offers for
these subjects are Data Structures, Algorithms and Theory of
Computation (and maybe some electives or math classes). This is also
my weakest area so bear with me.

You should know:

- What is an algorithm? Why do we study them?
- What does big-O notation *actually* mean? How about big-Theta and
  big-Omega?
- All of the classic sorting algorithms: insertion, select, bubble,
  merge, quick, heap
- Can we do better than n log n sorting? What assumptions are we
  making with that claim?
- All of the classic data structures and how to implement them: array,
  linked list, binary tree, heap, hash table, set, graphs
- Dijkstra's algorithm
- \*sigh\* Dynamic Programming
- What are finite state automata? When are they used?
- What is a Turing machine?
- What is the Halting problem? Give a proof of it
- What is NP? Give an example of a problem in NP.
- Is P = NP?

[2]: Bonus points if you can actually give a rigorous definition


# Software Development

# Tooling

# Professional

