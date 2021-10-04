What If...Courses Were Good?

I really should stop writing posts. More so than that, I should stop
writing about how I should stop writing posts. Anyways, let's get on
with it.

I've written a lot about how I'd change NYU CS. Most of these plans
involve ambitious, sweeping changes. And while I'd still love for NYU
to implement them, I'll admit that this is pretty unlikely. Therefore,
let's come up with some smaller scale plans, a little more spit and
shine and less a complete overhaul. Specifically, let's talk about
each course and how to improve it.

## Discrete Math

Discrete math is actually top on my list of courses to reform. It's
not a particularly inspiring course right now. The students fall into
an extremely bimodal distribution. You have students who are
completely new to proofs and rigor alongside students who have done
proofs and can solve combinatorics problems in their sleep. The first
group finds Discrete Math a miserable, tough course. The second group
finds it incredible boring.

If you knew what bimodal meant, you're probably in the second
group. If you understand that knowing bimodal is a sufficient but not
necessary condition, you're also probably in the second group.

My first solution would be to split the class into two classes:
Introduction to Proofs, and Discrete Math. Introduction to Proofs can
be a nice, slow introduction to rigor and proving stuff. Students will
take turns presenting proofs and challenging each other's
work. Discrete Math will cover the actual discrete math in much more
depth. Topics such as structural induction, state machines, recurrence
relations, maybe even lambda calculus will be covered. If you
want to go avant-garde, you could do the class in a proof checking
language like Coq, Idris, or Lean. That'd be so cool.

Of course, that's somewhat ambitious. A whole new class? NYU can't
handle that! If Discrete had to stay a single class, I'd try to make
it a flipped classroom with presentations. Students will try to solve
the problems and go to class to either present them or get
help. Unfortunately the students who lack discipline or motivation
will suffer, but it's not like these students are enjoying the CS
curriculum right now either.

## Introduction to Computer Science

I've written about how to overhaul the [intro
courses](https://blog.torchnyu.com/2020/12/08/waitlisted-professor-allocation.html)
before, but CS50 wasn't built in a day. Let's think smaller scale. I'd
try to standardize the curriculum and focus on training students to
solve problems computationally. Java should be a means towards an end,
not the entire goal of the class. Perhaps there'd be a Java bootcamp,
either during recitation or with online lectures. Even better, the
class should switch to Python or JavaScript. The majority of the
curriculum would be focused on solving problems. Students would be
encouraged to work on problems together and then present their
solutions.

Ideally there would be standard infrastructure for formatting and
running the code. Most students suck at formatting their code and an
autoformatter would sweep that problem away.

## Data Structures

Switch the language to C. Yes, it's a little old fashioned; yes, we
will be depriving these students of object oriented programming; yes,
they will suffer. But they already suffer a lot in CSO. At least now
their suffering will be amortized. Besides, there's no better way to
get good at C than a bunch of data structures work.

There's really no reason for Data Structures to include so much about
object oriented programming. It's a great paradigm---I'm not one of
those people who despises OOP---but plenty of people get along just
fine without OOP. It's not really data structures as much as software
architecture.

A lot of the course should be implementation based. I know that's
controversial, but because Algorithms is already going to cover the
theory, there's really no point in making this class a half-assed
version of Algorithms. Plus it'll get students to practice
programming. Free interview prep!

## Computer Systems Organization

Ah CSO, we meet again. Hopefully with C out of the way in Data
Structures, this class is a lot easier, which means we can make it
hard again! All sections should do the malloc lab because it's pretty
fun. I'd also consider taking the `ls` lab from OS and putting it in
here. There should be some assembly work, maybe even a lab in
asm. Students should leave CSO really comfortable with Unix, C and
vaguely comfortable with assembly. You could even do a CTF as the
final exercise. That'd be fun!

I'd consider teaching ARM instead of x86 but that's just me. I'd also
have a lecture at the end of CSO explaining how Rust removes 99% of
the pain you get from C.

## Operating Systems

OS is in C, because dammit who uses Java to write an operating system?
I'd love an honors course with Rust but we're staying in the land of
the real for this post.

I really liked my OS class so I'm not going to recommend too many
changes. It would be cool to cover more modern operating systems
concepts like solid-state drives, microkernels, embedded OS's, etc.

Even cooler would be comparing Windows, macOS/Darwin, and Linux.

## Algorithms

I never took Basic Algorithms, I took the grad level Fundamental
Algorithms, which as it turned out was likely easier than Basic. Big
mistake on my part.

With Data Structures being more implementation based, Algorithms
should be pretty theoretical. I'd like the curriculum to cover some
aspects of computation like state machines, push-down automata, even
Turing machines.

Again, I'd love the class to be focused around problem solving and
presenting solutions.

## Other Courses

Beyond those improvements, I'd love for NYU to have more
courses. There's simply not enough courses to provide a thorough CS
education.

- Introduction to Functional Programming

The closest we have to this class is undergraduate programming
languages, but that's taught extremely inconsistently. Plus a
programming languages class inherently has to cover other stuff
besides functional programming.

With a proper FP class, we could cover multiple variations of
functional programming such as Haskell, Elixir, OCaml, etc. We could
also delve into immutable data structures, a really cool area.

- Compilers


