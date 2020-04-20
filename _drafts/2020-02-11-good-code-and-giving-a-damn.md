---
title:  "<s>Good</s> Better Code and Giving A Damn"
date:   2020-02-11 20:00:00 -0700
---

Good code. Everybody talks about it. Your professors, your fellow CS
students, memes on the internet. Yet it's often hard to quantify. Oh
sure, you can easily tell if code is *bad*. The names suck, the code
doesn't make sense, the functions are gigantic, etc. But how do you
define good code?

There's quite a few answers to this, both offline and online. I'll
give a few starting points at the end, but frankly you could spend a
lifetime reading about good code practices. I'd argue it's ultimately
subjective to your skill level, experiences, needs and constraints, as
well as the skill level, expectations, needs and constraints of your
coworkers and clients.

So what is one to do with this overwhelming amount of information? And
why am I writing yet another treatise on good code? Well, these two
questions answer themselves. I'm hoping that by giving a short,
ordered guide to writing *better* code (but not necessarily good!), I
can help students improve their code juuuust enough that once they get
into their careers, their code doesn't make their managers
homocidal. Trying to get people to write good code is a quixotic
task. But perhaps getting people to write better code isn't.

The ordered part is essential. I'm going to give a few key qualities
of better code. Each successive quality is less important than the
previous ones. Therefore one should not sacrifice the earlier
qualities for the latter. What I've found is that when people write
sub-par code, it's not because they don't care about good code. It's
because they care about the wrong qualities of good code.

A quick disclaimer, these are my opinions on better code, and as
previously expressed, the optimal qualities of code are a very
subjective and contentious concept. However I believe that if you were
to follow these rules, nobody would be utterly horrified with your
code. Which is really all that one can demand as a junior developer.

With that in mind, let's start the list of qualities.

# 1. Readability

Code, above all, must be readable. Any non-trivial piece of code is
read far more than it is written. Whether it's your professor, your
co-worker or you in 4 weeks, your code will be read by somebody.

All the subsequent qualities depend on readable code. Before you do
anything with code, you have to read it.

## Qualities

What are the qualities of readable code? And what about unreadable
code?

Readable code is code that is:

**compact**. Less code is less to read, less to understand, less to
maintain[^1].

[^1]: Don't take this to mean shorter variable names. This means when
    possible, look to trim code. Avoid adding features for no
    reason. Find ways to eliminate unnecessary code.

**well named**. The names correspond to what the code should do in a
clear, yet not overly verbose manner.

**organized**. There is a consistent structure, whether file
structure, object hierarchy or module organization. There is a place
for every piece of code.

**well abstracted**. The abstractions are consistent, well thought out
and powerful. You can home in on one unit of abstraction and not worry
about the other units.

Unreadable code is code that is:

**fragmented**. To understand foo() you need to go to bar() which
relies on Baz which uses Abc.

**poorly written**. The code's names don't make sense and the
documentation is non-existent. You need to be a detective to
understand the code.

**a monolith**. The code is all jumbled together in a rats nest of
interconnected dependencies.

**abstracted too much or too little**. The code is either generalized
so much so that you can't figure out what each component actually
does, or it's a soup of code where you have to understand the entire
codebase to edit a single line.

## Examples?

You may have noticed that a lot of these qualities are
contradictory. This is not an accident. Good code is not a
maxima. It's a middle ground. The art of writing good code is based
around carefully adjusting your code's qualities: not too fragmented
but not too connected.

I'm not going to give examples here for a few reasons. First, I'm lazy
and I've learned to not let blog posts sit half written for too
long. Second, I want to keep this article from feeling as long as a
Tolstoy novel. Sorry Vronsky, you'll have to wait. And third, any code
snippet I give will likely be an over the top straw man and any
proposed solution will depend on a series of subjective
qualities. Instead I urge you to keep these qualities in mind while
writing code. Ask yourself if your code can be described using the
former or latter list. Then change accordingly.

This may seem like an unsatisfying answer. Don't you want
proclamations shouted down from the hilltops? *Thou shall not name a
function with less than 5 characters or more than 20*. But that's not
how good code works. You need to develop your own opinions and your
own taste in code. Otherwise you're not writing good code; you're just
obeying a religion.

One good way to practice readability is to read code. You can see
which code you think is readable and which code you think is
not. There's plenty of
[great](https://github.com/microsoft/typescript)
[open](https://github.com/rust-lang/rust)
[source](https://github.com/ReactTraining/react-router)
[repos](https://github.com/cssinjs/jss) to read.

One caveat, when starting out, you'll probably find a lot of code
impossible to read. This is not a surprise. Code is harder to read
than to write. But try to distinguish between code that is doing its
best to be readable and code that you have to fight to understand.

# 2. Extensibility

Extensibility means that a programmer can drop in and add new
functionality easily. Often this comes from **modular** and
**orthogonal** design.

Again, while this is important, readability comes first. If you can't
read the code, you can't extend it.

## Modularity

Modularity is the key concept in extensible code. Modularity ties into
the idea of abstractions. Code should communicate as modules which
hide information. What this means is that one module should not have
to know the details of the other module’s implementation. Instead,
they communicate via their interfaces.

Interfaces are the contracts that modules provide describing the
methods and data one can access.

Let's take an example of real world modularity. In a restaurant, there
is one major division: back of the house versus front of the
house. The front of the house consists of the waiters and the maître
d'hôtel (the person who greets and seats you). The back of the house
consists of the chef and his cooks.

In a properly run restaurant, the back of the house and the front of
the house are fully modular. The waiters do not know how the food is
cooked and the cooks do not know who is ordering the food or where
it's going. This allows each section to focus on their own tasks and
not worry about the others'. The interface between each is the
expediter, basically the person in charge of receiving orders from
waiters and calling out orders to the cooks. Waiters give tickets
detailing orders to the expediter, the expediter calls them out to the
chefs who make the dish. The expediter then makes sure the dish gets
to the waiters. At no point does the waiter know how the order is
being fulfilled, nor does the chef know to whom it is being
delivered.

Now imagine there is no expediter. Instead, waiters have to tell the
cooks exactly the order to cook the dishes, and the cooks have to
explain which dishes are ready. This would be a disaster! Waiters
wouldn't be able to drop an order then go serve another table. They'd
have to stay there and ensure that everything was cooked on time. And
cooks would have to remember which waiter ordered which dish. The lack
of abstraction means that the back and front of the house need to know
far more about each other than necessary.

A good way to phrase this principle is that you should attempt to make
your modules as dumb as possible. Modules should not know too much
about the entire system.

That being said, there is such a thing as code that is too
modular. After all, if you turn what used to be one unit of code into
two, you necessarily have to build a way for these two units of code
to communicate.

Going back to the restaurant metaphor, in most kitchens there are
multiple stations that do different tasks. There's a grill station, a
garde manger (cold food), a saute station, etc. A well intentioned
manager could see these stations and think "huh, garde manger
shouldn't be in a room with the blazing hot grill and saute
stations". Or maybe they think that having a separate room for each
station will prevent them from getting in each other's way. Whatever
the reason[^2], the manager decides to put stations in different parts
of the restaurant.

[^2]: Gimme a break here, just imagine it's a not very smart manager.

What's wrong with this picture? Synchronization. Each station needs to
be in sync when working on orders. The garde manger needs to be
working on the salad for the 4-top[^3] at the same time the grill is
making their chicken, at the same time the saute is making their
chicken. While each station, now that they're isolated, can
theoretically work more efficiently, it doesn't matter at all because
they have no way to communicate. Oh sure, they could have ticket
machines or runners or some complicated synchronization system. But
contrast that to colocation: grill yells out "Chicken is done in 2",
garde manger responds "Okay salad in 2", etc.

[^3]: 4 person table

Modularity is extremely important for abstraction, the act of limiting
the information each component holds. But you should be sure that the
component doesn't actually need this information.

## Interchangeability

What do you get once you have modularity? Well besides abstraction,
you get the ability to interchange modules with ease. As long as the
modules share the same interface, you should be able to swap them.

A real life instance of interchangeability is Uber. One important
aspect of Uber that is often lost in the "Uber for X" craze is
interchangeability. Uber drivers are fundamentally
interchangeable. Unless they are profoundly good drivers or profoundly
bad drivers, nobody notices their Uber driver. This is because all
drivers have the same, simple interface: drive from point A to point
B. As long as they all obey this interface, drivers can be
interchanged with ease.

The issue that a lot of people make when they pitch an idea like "Uber
for Babysitters" is that there isn't a clean interface for
babysitting. Oh sure, the main requirement is watching a kid for some
hours and making sure the kid is fed, safe and happy. But there's a
lot of subtle differences between what people want in a
babysitter. Some people want a sitter who can cook. Some want sitters
who are of a certain age. Some want a sitter who can also help with
homework. There's no universal interface here.

In programming, interchangeability is a key part of
polymorphism. You've probably seen this with object inheritance. A
Honda, a Toyota, etc. can all inherit from a Car object. A function
that takes a Car object can therefore take a Honda, Toyota,
etc. object.

# 3. Reusability

Contrary to popular belief, this is not the same as
extensibility. Reusable code means the code can be taken and reused in
different places in the codebase. Extensibility can help with
reusability but it just means that code can be extended in some
fashion.

Reusability is certainly nice, but people tend to fall into the trap
of trying to reuse *everything*. Again, this is where the hierarchy is
important. Reusability is nice, but you should prioritize readability
and extensibility above all.

One good source on limiting reusability is Rob Pike. He has a [Go
Proverb](https://go-proverbs.github.io/) that goes: "A little copying
is better than a little dependency". What this means is that while
it's tempting to reuse code, you have to understand that reuse implies
dependency. Let's say I have a `formatTime` function. I use it in my
`Clock` class to format times. Now let's say I started writing a
`Timer` class. It seems automatic that I'd reuse my `formatTime`
function, right? In both cases we're displaying time. And so I reuse
it and woo, go me! I've managed to write less code and deliver. But
say word comes down that the `Clock` class needs to display AM/PM, or
maybe timezones. Hmm, I could change `formatTime` to display these
things, but then `Timer` would be screwed up. Or I could use a config
object in `formatTime` to optionally configure `formatTime`, but that
adds complexity to the function. Or I could split `formatTime` into
two versions for clocks and for timers, perhaps `formatTime` and
`formatTimeLength`. I'm not saying any one of these is the *right*
answer. It's just important to acknowledge each of the possibilities
in turn.

I used to try to reuse code a lot, especially when I noticed repeating
patterns. But repetition isn't always a bad thing. Sometimes code can
be similar while still serving two separate purposes.

A good rule to follow is the rule of three. Basically, if you see code
repeated three times, consider trying to factor it out. Two times?
Hold off and see if it shows up one more time.

NPM is a good example of reusability gone mad. Packages, while great,
do lend themselves to a sort of obsessive reusing. 
