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
- Parallelism and why it's different from concurrency
- Memory allocation and why it's hard
- System calls
- Buffer overflow attacks
- How does a hard disk work?
- How do we gain consistency? What is journaling?
- The basics of distributed systems.

# Programming Languages

I'm particularly interested in programming languages so this area
might be a little larger than most people's. Part of the challenge is
that NYU doesn't really teach a lot about programming languages. Which
is a shame, since it's a foundational part of computer science.

Here's what you should know:

- 1-2 programming languages at a sufficient level to say, write an
  medium difficulty interview question[^1].
- What is a compiler at a high level? What is an interpreter? Give
  examples of both
- An example of a language that is compiled and interpreted
- A programming language that has first class functions such as:
  Python, JavaScript, Ruby, Haskell, Rust, Kotlin
- A language with static types such as Java, C++, Kotlin, Rust, C#,
  etc.
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
- Hindley-Milner typechecking

[^1]: Bad benchmark, but I couldn't come up with any better one.

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

[2]: Bonus points if you can actually give a rigorous definition

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


# Software Development

Software Development is realistically what most of us plan on doing
with our CS degree. Unfortunately many CS programs neglect it under
the claim that "CS != Programming". That may be true, but software
development is a significant part of CS. Don't get discouraged if you
don't know some of these. NYU doesn't teach all of them unless you
take certain courses.

You should know:

- How to collaborate with 2 or more people on a project. Ideally
  without any fighting or death threats
- Some experience in one of: front-end web development, back-end web
  development, mobile application development, systems development.
- How to deploy something to production
- The high level view of how an internet request works, from DNS, to
  TCP/IP to the physical server, to the reverse proxy, to the code to
  the database and back.
- What bad code looks like
- What slightly less bad code looks like
- How to do basic refactoring
- How to read other people's code and give feedback.
- What is abstraction? How is it useful?
- What is modularity? How does it relate to abstraction?
- The basics of object oriented programming such as inheritance versus
  composition, SOLID principles, a couple design patterns, etc.
- How to use libraries and frameworks. You should be able to learn a
  new library or framework by reading documentation and tutorials.
- How to debug with print statements or a debugger.
- How to get unstuck by looking at StackOverflow or GitHub issues
- How to ask a StackOverflow question or open a GitHub issue.
- How open source collaboration works.

# Tooling

This is an area that varies a lot. Some people spend hours upon hours
on tooling, tweaking their .vimrc or .emacs.d, while others still
click File > Copy. You don't need to be a tooling master but I'd
recommend getting the easy stuff down.

- How to use git, ideally branches, rebasing, merging, and fixing
  messed up repositories
- How to use one code editor of your choice, such as emacs, vim, VSCode, Sublime Text, etc.
- How to navigate a Unix based terminal
- What is an SSH key?

After that there's a few things you could learn like:

- Docker
- Basic bash scripting
- Key commands (learn M-f, M-b, C-a, C-e, M->, M-< in emacs)
- A cloud service like Amazon Web Services, Google Cloud Platform or
  Microsoft Azure.

# Professional

Maybe the most important. All of this doesn't matter unless you can
get a job. This is another area where NYU isn't the greatest at
helping out. Here's what you should know before you graduate.

- How to look for and apply to tech jobs
- How to network and then use those connections
- How to filter out the poor or borderline insulting job opportunities
  from the real ones. I.e. how to avoid getting roped into someone's
  poorly thought out startup
- How to politely decline these not-great job opportunities.
- Ways of applying for jobs that aren't submitting through an online
  portal with no connections (cold emailing, personal connections,
  on-campus recruiting)
- How to get an internship (and go through with it! Aim to have one or more internships)
- How to judge if a company or team has their stuff together.
- Interviewing skills, whether that's solving whiteboard problems or people skills
- How to handle a not-great working situation and make the best of it.
- How to seek out mentorship and learn from people.
- How to get a job out of college

I highly recommend getting an internship at some point in
college. It's not the end of the world if you don't have one, but it
can be a great way of getting work experience, getting a great paid
summer experience, and having a backdoor into a big company for full
time work.

# That's It

These lists are fundamentally flawed in that they're specific to what
I've learned and what I know. If I had taken different classes with
different professors, my list would undeniably be different. There
would be additions of areas that I know nothing about and omissions of
areas that I believe are essential.

Don't worry too much if you don't know everything on this list. But if
there's an item or two that you don't know, yet piques your interest,
you should explore it. It's not always about what you know. It's about
what you know you do not know.
