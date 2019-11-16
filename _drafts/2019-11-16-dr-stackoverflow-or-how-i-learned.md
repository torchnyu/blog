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

# Level 1: Reading StackOverflow, GitHub Pages, et al.

Ah StackOverflow. The most worshiped of programming sites. And for
good reasons. It's an incredibly useful site. Most people restrict
themselves to just reading it, so that's what we'll discuss for this
level. Unless you happen to stumble upon a post that exactly gives you
the answer to your specific question, you'll probably end up in a
situation where one post on SO will give you 40% of the answer and
another post will give you like 30% and you have to kinda futz the
last 30%.
