---
title:  "Dr StackOverflow or: How I Learned to Stop Worrying and Love Being Stuck"
date:   2019-11-16 20:00:00 -0700
---

Getting stuck sucks. There's no way around it. Whether it's not being
able to find the missing semicolon or having trouble understanding
this new library, being stuck is one of the most frustrating parts of
programming. That being said, it's also one of the most important
aspects of programming. A programmer who can surmount these roadblocks
is worth their weight in gold.

I've found that students don't always know how to get unstuck. Which
is understandable; getting unstuck isn't a skill taught in a lot of CS
programs. But here's your chance to prevent that. I'm going to provide
4 levels of getting unstuck, from basic to advanced. Some of these
levels you may already do. Others you may not.

# Level 0: Local Debugging and Fixing

This is the standard way people get unstuck. They try to debug or fix
the problem within the code. Your code isn't compiling? Find the
error. You're getting the wrong output? Trace through your code
execution and see where things are going wrong.

Generally people have decent strategies for this level. Some people
use debuggers like gdb (which are actually a [lot
cooler](https://www.youtube.com/watch?v=PorfLSr3DDI) than your CSO
prof made them out to be!). Others, like myself, use print
statements. Print statements are nice because they allow you to see
the flow of your code. I use numbers a lot of the time so that you can
see when the code halts:

```
char* file_content = read_file();
printf("1\n");
char* first_entry = get_first_entry(file_content);
printf("2\n");
int first_number = parse_int(first_entry);
printf("3\n");
```


If the output is:

```
1
2
```

Then you know that the bug is probably in `parse_int`.

Another good strategy to learn is to write small tests. In some
languages you're lucky enough to have a REPL or Read Eval Print
Loop. That's the prompt that pops up when you type in `python` to your
Terminal. REPLs are great ways to test out small assumptions. For
instance, say I forgot how to get the length of an array in Python

```
>>> arr = [1, 2, 3]
>>> arr.length
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'list' object has no attribute 'length'
>>> arr.len
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'list' object has no attribute 'len'
>>> len(arr)
3
```

And hey, cool! Now I remember.

For languages that don't have REPLs, like C, you can write a small
program and check. I have a folder called scratch on my computer where
I test out small programs.

For instance, my `scratch.c` file currently has a small program
testing out how to read items from a directory in C. When I was
writing `ls` for my Operating Systems course, I wasn't super clear on
how that worked. Instead of blindly forging ahead and trying to get
the code right in the context of the complicated lab code, I decided
to just write a small test that read from a directory. That way I was
able to understand that code in isolation before applying it to the
larger context of `ls`.

And sure, you can always look up the answers to these small questions
on StackOverflow, but there's something to be said about testing your
hypotheses. For one, if you're ever without an internet connection and
writing code, you'll be able to make progress. Second, you'll be able
to reason through your code a little better. If someone asks you a
question, instead of just directing them to StackOverflow, you can
write a little test and find out.


# Level 1: Reading StackOverflow, GitHub Issues, et al.

Ah StackOverflow. The most worshiped of programming sites. And for
good reasons. It's an incredibly useful site. Most people restrict
themselves to just reading it, so that's what we'll discuss for this
level. Unless you happen to stumble upon a post that exactly gives you
the answer to your specific question, you'll probably end up in a
situation where one post on SO will give you 40% of the answer and
another post will give you another 30% and you have to kinda futz the
last 30%. You can and should get good at futzing. Futzing basically
means making leaps of logic and trying different approaches. This is
where version control comes in handy. You can commit your existing
code, try a new approach, then roll it back if it doesn't work.

Common techniques in futzing include using different package versions,
rewriting part of the code, and going back to Level 0 or local
debugging.

<!-------------------->
<!-- <Example here> -->
<!-------------------->

Another great resource is GitHub issues. GitHub issues are problems
opened on GitHub repositories for a given library or language. GitHub
issues are great for fixing problems with newish libraries or cutting
edge language features. For instance I use issues for problems with
front end libraries because front end development moves so quickly
that the likelihood I'll get a good, up to date answer on
StackOverflow is next to nil. Likewise, if I were using Rust's nightly
language builds and ran into a weird error, I might look on Rust's
[GitHub issues page](https://github.com/rust-lang/rust/issues).

One quick tip is to search through closed issues as well. Often these
will have your solution.

Of course sometimes you run into an issue with what appears to be five
million comments, ending with "any updates on this issue?" (\*cough\*
[Rocket](https://github.com/SergioBenitez/Rocket/issues/19)
\*cough\*). That sucks.

There's other niche sites that are useful. For instance, Server Fault
for system administrator problems, Emacs StackOverflow for emacs
issues, and on occasion Reddit can be useful.

# Level 2: Writing StackOverflow, GitHub Issues, etc.

This is the big jump. This is what separates the children from the
adults. If you dare to dip your toe into the vast, sometimes
intimidating pool of knowledge that is StackOverflow, you can reap
some immense benefits.

StackOverflow has a reputation of being prickly and unfriendly. And
sometimes that can be the case. But it's a little undeserved in my
opinion. If you follow the tenants of writing a good question, then
you won't face the wrath of StackOverflow. SO includes a great
[guide](https://stackoverflow.com/help/how-to-ask) on writing a
question. But really, it boils down to doing your due diligence in
researching the topic and exhausting all possibilities before
posting. Jon Skeet, one of the most legendary StackOverflow question
answerers (over a million reputation points), has a
[post](https://codeblog.jonskeet.uk/2010/08/29/writing-the-perfect-question/)
as well.

It also helps to be polite. You may be panicking and stressed and
under a deadline, but that doesn't mean you should be rude. I try to
always end the question with a thank you and my name. It may seem
overly polite or formal but I hope it endears me to anybody reading
the question.

GitHub issues are great place to ask as well. Again, GitHub issues are
more for cutting edge problems or specific libraries. Sometimes the
project will have a template to fill out. These are great and you
should do your best to follow it as closely as possible.

Sometimes I use GitHub issues if I'm trying to accomplish something
but the documentation isn't up to par. Even though it's not
technically a bug in the code, it's a bug in their
documentation. Which is equally important imo.

# Level 3: Reading the Source

This is the level that most people don't even think about. I myself
only started to do this within the last year or two (I credit a
wonderful interview of Joe Armstrong, the creator of Erlang for the
inspiration). But when you think about it, the source code is
the only truly accurate and up to date documentation.

Reading code isn't easy. I'll probably write about this too, since
there's a few strategies I've picked up over the years. But it's
arguably as important of a skill as writing code. Much like how
reading good prose helps you write good prose, reading good code helps
you write better code. And reading bad code can help you understand
what not to do.

Plus there's nothing better than opening a GitHub issue that pinpoints
the exact issue with line numbers and everything. The maintainer will
probably like that a lot more than a "help my code doesnt work!!!".

# Level 4: Fixing the Source

The truly enlightened approach. Have a problem with a library? Fix it
your damn self! Not only will you fix your problem, you'll get some
open source street cred. There's nothing like saying you've
contributed to the TypeScript language.

Again, this isn't easy. But getting used to reading and eventually
contributing to massive codebases is an extremely valuable skill. A
lot of work in a large tech company is precisely that. If you can
learn these skills now, you'll be well prepared for working in the
industry.


# Other

Alongside these tips there's 

