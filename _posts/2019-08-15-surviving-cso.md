---
title:  "Surviving NYU's Hardest CS Class: Part I"
date:   2019-08-15 9:14:36 -0700
---

Let's set the scene. You're a sophomore or junior CS major in NYU
CAS. You've crushed Intro to Computer Science, destroyed it in Data
Structures. You strut into your next course, Computer Systems
Organization, confident that you'll defeat it as well. Only to find
yourself in for a rude awakening.

You're introduced to this weird, old language C. All of your hard
honed Java skills are now utterly useless. Your errors go from the
carefully detailed stack traces of Java to the blunt, barebones
Segmentation Faults of C. No line numbers, no function
names. Nothing. You go fom the nice bubble of managed memory, with its
constructors and references to the nitty grittiness of pointers and
malloc. Your code appears to just randomly break apart for no
reason. You're confused, stressed and failing all your stupid test
cases. What do you do?

Computer Systems Organization, or CSO, is the third class in NYU CAS's
computer science program and arguably the most difficult of the CS
curriculum.

This is for good reasons. The class covers a lot of ground, from the C
language to systems architecture to concurrency. This is especially
tricky because students face a massive paradigm shift from the
relatively high level bubble of Python and Java with its managed
memory and forgiving error messages, to the raw, bare metal of C and
x86 assembly. It's kind of like going from driving a 2019 Mercedes to
a Model T.

I was lucky enough to come into the class with some C experience. I've
also learned some more useful techniques for systems development after
I took CSO. I hope that by writing up a quick guide for preparing and
surviving CSO, future students can be more prepared, get better grades
and be happier people. Well, at least the first two. The last one
might require [incremental lifestyle changes sustained over
time](https://www.youtube.com/watch?v=TbwlC2B-BIg).

This guide is applicable whether you have an entire summer to prepare,
a few weeks to practice or even if you're in the middle of the course
and struggling.

Quick aside, if you're in CSO already and worried that you're going to
fail, don't panic. You are almost certainly not the only person in
this situation. In fact, there's a decent chance a lot of people are
in the same boat. CSO generally has a reasonable curve to it. Not that
you should rely on the curve to pass. Now let's get to work:

## Tooling

Tooling is a seriously underrated aspect of programming. While a good
programmer should be productive on any platform with any tools, a well
cultivated set of tools can speed up productivity and prevent
bugs. Unfortunately, most professors don't go over tooling except for
the bare minimum needed to run the labs. There's a whole lot more than
that.

You don't have to set up all of these things immediately. My advice is
to set up the bare minimum, then tinker with your set up every few
weeks and see if you can improve something. Tooling is always
something you can refine in some shape or form. I'm always playing
around with new editors and new tools.

### The Absolute Bare Minimum You Need To Do

Memorize these 3 flags: `-Wall -Wpedantic -Wextra`. Flags are ways of
modifying your compiler and how it views your code. Like how you can
flip a switch on some cars and go into sports mode. These three flags
basically turn up your compiler's standards for code quality. You see,
compilers by default attempt to accept as much code as possible. Even
code that is clearly wrong or nonsensical. This is not good, as it
leaves you open to make a whole bunch of mistakes. By adding these
flags, The compiler will now warn you about potential issues in your
code.

One side effect is that when you run your code, you may get a gigantic
boatload of errors. **That's fine**. The compiler is your friend,
who's warning you about potential issues in your code. Better the
compiler than the professor's test suite.

You can, naturally, call the compiler manually with these flags. That
means entering something like `gcc -Wall -Wpedantic -Wextra main.c`
into the command line. Or you can [add it to your
Makefile](http://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/). Make,
if your professor hasn't explained, is a way of automatically building
your project. Make only compiles the files that have changed, saving
you time. It's very useful and extremely common in the systems world.

I can't emphasize how important these flags are. As long as you use
these three flags, I guarantee your debugging experience will improve
immensely. Probably the best bang for your buck in this whole post.

### Valgrind

[Valgrind](http://www.valgrind.org/) is another extremely useful
tool. It helps detect memory leaks and threading issues, basically the
most common bugs you'll encounter in CSO. I'd highly recommend running
your code with it automatically.

### Git

If you haven't already, seriously consider learning git. Version
control allows you to save various versions of your code, making it
easier to store and roll back your code changes. I know, I know,
you're saying to me, "git's confusing and besides, I'm the only one
making changes". Yeah yeah, it's still very useful. If you keep your
code in git, you can fearlessly change stuff knowing that you can
always revert back to an old version. Besides, quite literally every
single reasonable programming job uses git, so I'd just bite the
bullet and learn it. There's a lot of [great](https://try.github.io/)
[resources](https://www.atlassian.com/git/tutorials)
[online](https://git-scm.com/book/en/v2) for git.

Just FYI, don't host your repos publicly. People will find your repo
and they will copy you. Then professors will find out too and you'll
have to answer questions about why your code was in a public repo.

### Editor

A good editor is worth its weight in gold. Text editors are extremely
powerful underneath the hood, allowing you to quickly navigate and
modify code. Some CSO professors teach Vim, which is an excellent old
school editor. The main benefit of Vim is that it's already installed
on most computers (or vi, its predecessor). Personally, I use emacs,
another excellent old school editor. But really you can use any
editor[^1]. My only suggestion is that it should be usable via the
shell, as CSO requires a lot of shell usage.

If you want, you can also download yourself a copy of CLion. You get
it [free with your NYU email!](https://www.jetbrains.com/student/)
You should totally take advantage of this for all of JetBrains
editors---they're awesome.

### Bash

Which brings me to the final area: learn to use bash. Bash is a Unix
shell. It's what you use to build your code and run commands. You can
navigate directories with bash, write simple scripts and even access
remote servers. On Mac, you can run bash with the Terminal. On Linux
you can use Command Line. If you're using Windows, you'll need to
either install a Linux VM, dual boot Linux or use the Linux subsystem.

For CSO, your TA usually has you set up a Linux VM to run your
code. That's perfectly fine, although personally I run the VM headless
and [SSH into
it](https://stackoverflow.com/questions/5906441/how-to-ssh-to-a-virtualbox-guest-externally-through-a-host). That
way I don't have to interact with the VM except via Terminal.

I'd encourage learning some basic commands like `ls`, `cd`, `pwd`,
etc. It'll make your life a lot easier.

[^1]: nano, vim, emacs, micro, ed if you're hardcore

## (C)lash of Clangs

Okay, so you've gotten your tooling all set up, or you've skipped the
tooling section cause tooling's boring. What's the next thing you can
do? Simple. Learn C. 

C is a rather tricky language, even for very experienced
programmers. It has a lot of ways to shoot yourself in the foot, or in
programmer parlance, it has a lot of footguns. If you can learn it
ahead of time, you'll save yourself a lot of pain and confusion.

Find yourself a good source to learn or relearn C. I'm not up to date
on the best books for C. And frankly, this will depend on your
personal learning style and experiences. Some people prefer terse,
tricky books, while others prefer more verbose volumes. Personally I
used The C Programming Language by Kernighan & Ritchie, or K&R as it's
known. Dennis Ritchie, for those of you who aren't familiar, is one of
the creators of C. However, K&R teaches a very old fashioned style
with terrible variable names (like atoi) and really...optimistic uses of
memory. 

Instead, do your own research. Look at [some lists
online](https://stackoverflow.com/questions/562303/the-definitive-c-book-guide-and-list),
maybe peruse some [reddit
threads](https://www.reddit.com/r/learnprogramming/comments/7fdhf3/books_on_programming_in_c/). Don't
feel like you have to stick to one book by the way. I tend to bounce
around a few sources, generally a mixture of books and online
tutorials.

### The Absolute Bare Minimum You Need To Do (Again)

Yeah yeah, I hear you, you don't have time to read a goddamn book on
C. You got other shit to do in your life. Watch Netflix, go on dates,
[endlessly simmer on the film Avatar's usage of
Papyrus](https://www.youtube.com/watch?v=jVhlJNJopOQ), whatever.

For C, "all" you need to learn is pointers. What are pointers? A
pointer is a memory address. Think of it as essentially an index into
the reeeaallly big array that is computer memory. Pointers are the one
and only way of handling memory in C. 

Languages like Java or Python abstract away pointers with the idea of
references. C has no such concept. Instead, you have pointers that
point to places in memory which can contain whatever data you
choose. One crucial fact you need to keep in mind when writing C is
that **pointers are just a value**. Pointers are simply positive
integers that refer to places in memory. You can store them, pass them
into functions, return them from functions, really whatever you can do
with any value. They're not magic. And yet, they're incredibly
powerful. Pointers allow for indirection. They allow you to create
data structures, to create abstraction, to go from playing with a
glorified calculator to, well, programming. I'm not going to go into
the nitty gritty of pointers here cause that takes a lot more time and
space and a far better author than me.

You should understand pointers well enough that you can build simple
data structures like a linked list, a hash table, and a binary tree in
C. If you can do that, you're in a great place.

### Debugging

Debugging in C is very different due to how C handles (or doesn't
handle) errors. Java will generally spit out nice stack traces which
you can just follow to find your problems. In C, the most common error
you'll get is a segfault. A segfault often happens when you're
attempting to go to a location in memory that doesn't make
sense. Think of it as like telling your computer to go to Platform 9
3/4. Segfaults do NOT give stack traces and they basically immediately
halt the program. The way I debug segfaults personally is to print out
markers at various parts in my code, then see which markers get
printed before my code segfaults. For instance, let's say we have the
following code:

```
printf("1\n");
char* x = NULL;
printf("2\n");
*x = 5;
printf("3\n");
```

It's totally okay if you don't understand this. Come back to it once
you've learned some C. In most cases this will print out:

```
1
2   
Segmentation fault: 11
```

Notice how `3` is NOT printed out. This is because segfaults
immediately halt program execution. This will allow me to say "huh, I
guess my error is in between 2 and 3". In fact, you can kinda [binary
search](https://en.wikipedia.org/wiki/Binary_search_algorithm) your
code by putting one marker in the middle of your code, then if it gets
printed out, putting a new marker between the old one and the end of
your code, otherwise putting a new marker between the beginning of
your code and the old marker, etc.

However contrary to popular belief, segfaults are not the worst errors
in C. The worst errors in C are the *silent* ones. These are errors
that don't manifest until you happen to run a particular input or
until a particular thread wins. The only way to really ensure that
your code works 100% is to test it yourself. Now, entire books have
been written on proper, thorough testing. But a quick gist is to
always test for bad input. Passing in a pointer? Make it NULL, 0, -1,
anything you want. Giving in integers? What if they're really large?
What if they're negative? Write code that runs through these
situations.

Under no circumstances should you **ever** submit code that you have
not compiled and run. Never assume your code will work. Test and
verify.

### Arrays and Strings

One final note, arrays and strings are a big point of trickiness in
C. Well, actually, I repeat myself. Strings in C *are* arrays. They're
arrays of characters. Well, arrays of characters followed by a special
`\0` character. And arrays? They're basically just contiguous pieces
of memory. An array of 10 integers? Just 10 integers sitting together
in memory. These facts lead to some confusion, especially when coming
from a high level language. For one, you can't just get the length of
an array. If you ask C for the length, it'll do the digital equivalent
of shrugging. You need to store that information in a separate
variable. Likewise, you can't just combine (or concatenate if you're
fancy) strings in C. Combining strings requires allocating a new chunk
of memory and coping both strings into that chunk. Kinda a pain.

If you have some extra time after pointers, I'd spend a solid bit of
time learning the ins and outs of strings and arrays. It'll definitely
be worth your time.

That's all I'm going to talk about for now. In the next post I'll
cover x86 assembly, some concurrency and other miscellaneous
topics. Stay tuned!

--- Nicholas
