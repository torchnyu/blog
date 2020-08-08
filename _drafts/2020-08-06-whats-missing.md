---
title:  "What's Missing"
date:   2020-08-06 10:00:00 -0700
---

I wrote a post talking about the topics [you should
know](https://blog.torchnyu.com/2020/05/31/stuff-you-should-know.html). In
the process of writing that post, I realized there were a lot of
topics I'd like to put on the list, but couldn't. My criterion for
inclusion in the list was that the topic needed to be taught in some
shape or form by an NYU CS course, ideally a core one. If one
professor taught the topic but not others? Fine. But it needed to be
something that an NYU student could have conceivably stumbled upon. In
the spirit of kvetching about NYU, here's some of these topics I wish
NYU taught.

# Programming Languages

Anybody who knows me personally is probably rolling their eyes. I
happen to be rather interested in PL, having written [my own
programming language](https://github.com/nicholaslyang/saber). Until
recently I had accepted that my interest was just a niche area that
not everybody needed to know.

What changed? Well I started working on a project to compare CS
curricula (more on that in another post). As I trawled through the
various requirements and course offers, I began to realize
something. Hey, programming languages is a pretty damn common
requirement!

There's good reasons for this. For one, programming languages is a
foundational pillar of CS. There's debate about the exact pillars, but
I'd say it goes: Systems, Theoretical CS, Programming Languages,
Artificial Intelligence and Software Engineering. Maybe Human-Computer
Interaction too.

Every programmer interacts with a programming language. No
matter what company, no matter if it's front end, back end or
middleware, you're dealing with a compiler or interpreter if you're
writing code.

What is programming languages? Programming languages is the general
study of the languages you use to write code. This can mean
implementations such as compilers or interpreters. This can mean
theoretical topics such as type theory, formal methods for proving
correctness or program analysis. This can mean different paradigms of
programming languages such as functional, logical or imperative.

Programming languages has ties to many other areas in CS. You'll need
to know some systems development to work with compilers that generate
assembly. You'll need to know some theoretical CS to analyze your PL
algorithms (cf [Swift Typechecking is
Undecidable](https://forums.swift.org/t/swift-type-checking-is-undecidable/39024)). You'll
need to know some software engineering to write a compiler and design
an effective language. You might even need some machine learning
knowledge if you're writing the [right sort of
compiler](https://www.tensorflow.org/swift).

If you want to learn more about programming languages, I'd recommend
the following resources:

- [Crafting Interpreters](http://www.craftinginterpreters.com/) is a wonderful book on how to write an
  interpreter for a language. It teaches from the ground up. All you
  need is some Java experience.

- [Beautiful Racket](https://beautifulracket.com/) is a great intro to
  creating mini programming languages to solve your problems.

- [Learn You A Haskell](http://learnyouahaskell.com/) is an often
  recommended book to learn Haskell. Some people aren't a fan, but
  hey, it's free.

- [Lambda Calculus](https://www.youtube.com/watch?v=eis11j_iGMs) is a
  fundamental concept in PL. Computerphile has a great video on it.

# Networks, Databases & Other Systems Stuff

I actually consider NYU's systems classes some of the more interesting
and informative classes that I've taken. However they lack a few
areas. We don't learn how databases work and we don't learn about
networks.

Both are fairly essential. Databases are at the center of every
application. Everybody needs to store data somehow. Networks are
crucial for communication; you can't have the internet without
networks. They're also *the* application for graph theory.

We do have a databases course, but it appears to be a very
introductory one without any real meat. Which is a shame because
databases are an area where a little knowledge can go a long
way. Whether it's using tools like indices or views, or understanding
relational algebra, database knowledge can pay off in making your data
simpler, easier to understand and easier to work with.

NYU also omits distributed systems for the most part. While they're
not as ubiquitous as databases, distributed systems are pretty common
in large companies. Most large tech companies like Amazon or Microsoft
operate distributed systems in the form of S3 or Cosmos. If you work
at a big N, you'll likely have to use some distributed systems
knowledge.

I'm not an expert on this areas, but here's some resources I've been
meaning to look at myself:

- [Use The Index, Luke](https://use-the-index-luke.com/) is a great
  site for understanding database performance

- [Networking Zine](https://jvns.ca/networking-zine.pdf) by Julia
  Evans looks wonderful for understanding networks.

- [Computer
  Networks](https://www.amazon.com/Computer-Networks-Andrew-S-Tanenbaum-ebook/dp/B006Y1BKGC)
  is a classic text on networks.

- [SQL for Web Nerds](http://philip.greenspun.com/sql/) is something I
  found on the internet just now, but hey Hacker News recommended it,
  so how bad could it be?

- [Paxos Made
  Simple](https://lamport.azurewebsites.net/pubs/paxos-simple.pdf) is
  an explanation of Paxos, one of the most important consensus
  algorithms for distributed systems, from the creator themself,
  Leslie Lamport. It miiiight not be as simple as it claims, since
  Lamport is a rather brilliant person.

# Software Engineering

This is a commonly mentioned one. Many NYU CS students graduate with
little to no software engineering knowledge. Those that do often get
their knowledge from outside sources.

When people talk about software engineering knowledge, they often mean
stuff like knowing how to build a front-end app, or being able to
write a back-end API. That's great and stuff that you should
definitely know. If you're interested in learning more, join
[Spark](https://spark.torchnyu.com/), Torch's mentorship program.

However, this is not the software engineering knowledge that I'd like
NYU to impart. Practical knowledge is hard to teach and requires
teachers who are perpetually up to date---ideally in industry
themselves. Instead I'd love NYU to teach software engineering
**technique**. As any programmer can atest, software engineering is
more than just writing code. It's about code quality, team management,
product, infrastructure, dependency management, user experience, and a
whole slew of other factors.

How do we teach these factors? Easy. Reading! I know, some of you
don't like reading. Some of you would rather debug raw hex code than
read Joseph Heller. Unfortunately there's a lot of knowledge hidden in
books and the only way to retrive it is to read them.

I'd love for students to learn about concepts like Brooks' Law: Adding
manpower to a late software project makes it later. That way when your
boss talks about hiring 2 more developers to help ship the behind
schedule, over budget project, you can flash back to your software
engineering class and jump ship.

It's incredible to me that we teach programmers without any real
respect given to our predecessors. They encountered many of our
problems. It's only fair of us to listen.

Here's some more resources:

- [Jeff Atwood's book
  list](https://blog.codinghorror.com/recommended-reading-for-developers/)
  is a great starting point. Definitely take a look and read some of these.

- [The Mythical Man
  Month](https://www.amazon.com/dp/0201835959/?tag=codihorr-20). It's
  on Jeff Atwood's list, but hey, I know some people don't click
  links. Brooks' law comes from this book. It's probably the most
  influential book on software engineering. Read it.

- [Smart And Gets Things
  Done](https://www.amazon.com/Smart-Gets-Things-Done-Technical/dp/1590598385)
  is a book on hiring. Why would you read a book on hiring? How your
  company hires determines who your company hires determines your
  experience at the company. If you apply for a job at a company and
  their hiring process is less than ideal, don't work there.

- [Joel on Software](https://www.joelonsoftware.com/) and [Coding
  Horror](https://blog.codinghorror.com/) are two classic blogs on
  software engineering. They're a little old, but their knowledge is
  still really useful.

- [Spark](https://spark.torchnyu.com/) is Torch's mentorship
  program. We're mostly teaching the nitty gritty details, but you're
  working on a team with other people, so you'll get to pick up the
  technique as well. Plus you get to be mentored by me!

- [Get A
  Job](https://blog.torchnyu.com/2020/01/02/first-job.html). Ultimately
  this is the best way to learn. Get an internship and you'll learn
  more about how to write software in three months than in four years.
