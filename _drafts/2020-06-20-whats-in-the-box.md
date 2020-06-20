---
title:  "What's In The Box?"
date:   2020-06-20 20:00:00 -0700
---

I've been trying to come up with proper explanations for why concepts
like code splitting, abstraction, and naming are important. One
analogy came to mind recently.

Imagine you're moving and need to pack up your stuff. Maybe your
university kicked you out of housing. Maybe you're starting a new job.

How would you pack your stuff? Do you put everything into one large
box? Probably not. It's too big to move around and there's no way to
partition your stuff. You can't have some boxes that you bring to
storage and others you bring home.

Likewise you don't want to put your items in individual boxes. That'd
be way too tedious and plus you need to juggle all of these boxes.

What you want to do is put your stuff in medium sized boxes. Not too
big so you can partition them, but not too small so that they're
unwieldy.

This is the process of code splitting. Not quite modularity, more just
partitioning your code into small pieces. Note that the "boxes" in
programming can be objects, functions, structs, really whatever unit
of code you'd like.

But that's not all you want to do. You could have medium sized boxes
but pack them in a really ineffective way. You could have boxes that
mix kitchen supplies with clothes with books. But that'd make finding
your stuff hard. You'd have to consider almost every box when looking
for an item.

Instead you probably want to put like things with like things. You
want your kitchen supplies with your kitchen supplies. You want your
clothes with your clothes. And sure, sometimes you end up with a
little extra clothes and a little extra kitchen supplies so they need
to share a box. But that's not common and if you get some more kitchen
supplies, you can consolidate and make a kitchen-only box.

This is the process of creating good abstractions. Now when you're
looking for your chef's knife, you know to look in the kitchen items
boxes. You've created an overarching theme or idea that corresponds to
the boxes.

However abstractions aren't useful unless the boxes can convey the
abstraction. How do we do that? Naming!

When you put stuff in a box, you probably want to write on the outside
what the box contains. Of course, there's a few options for what you
could write. You could write "supplies" or "stuff", but that'd be too
generic. You'd have a bunch of boxes named "supplies". You could list
everything inside the box like "chef's knife, spatula, wooden
spoon..." but that'd be tedious and plus, once you add or remove
something, that name becomes incorrect.

You probably want to go for something in the middle. Maybe "kitchen
supplies". Or "kitchen supplies: utensils". There isn't an absolutely
correct answer. Depending on how much stuff and your needs, different
names may make sense.

This is the process of naming. Naming in programming is really helpful
for the same reason naming in moving is helpful: It helps future
you. When you're packing the boxes, you can probably remember what
went where. You can remember that your record player went into this
box and your algebra textbook went into that box. But six months later
when you're pulling stuff out of storage, you probably won't
remember. You'll need the names to decipher what is where. Or if
someone else goes into storage, say a family member or a friend, they
won't know your system. They'll have to use your names.

In programming the same is true. You may remember that
SubjectCoursesList also displays School info as well when you write
the component, but six months down the line you probably won't. And
another programmer will definitely not know because they didn't write
the code.

What I like about this analogy is that it provides several important
qualities for your code and explains what can go wrong without all of
them. Far too often I see people who break up their code, but then
don't go on to build proper abstractions. Or they build great
abstractions, but then they put them behind confusing or even
deceptive names. All of these pieces matter.

This analogy breaks down in some ways. I couldn't figure out a way to
fit in orthogonality or modularity, but I'd be happy to see if someone
else can.
