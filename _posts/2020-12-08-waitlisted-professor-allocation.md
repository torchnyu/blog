---
title:  "Waitlisted: Solving Professor Allocation"
date:   2020-12-08 10:00:00 -0700
---

In this episode of grumpy undergrad yells at cloud, let's talk
professor allocation.

I've been critical of NYU CS of late, but there's one area in which
we're undeniably strong. We have great professors. We have a
[Nevanlinna Prize
laureate](https://en.wikipedia.org/wiki/Subhash_Khot), [the founder of
an entire field](https://en.wikipedia.org/wiki/Patrick_Cousot) and to
cap it off a [Turing Award
laureate](https://en.wikipedia.org/wiki/Yann_LeCun).

However, show of hands here, how many of the above have you had as
professors? I'd bet none. Indeed if you scroll through the professors
list, there's a few patterns. They teach a lot of graduate courses and
when they teach undergraduate courses, it's the occasional elective.

This is a shame. A lot of these professors are fantastically talented
and would be great resources. Not to mention, the lack of professors
directly hurts the course offerings. NYU can only offer Programming
Languages, a frankly essential pillar of computer science, as an
occasional elective taught by an adjunct[^1]. They've had to cancel
advanced electives because they needed the professor to teach a core
CS requirement. We can't even get an undergraduate compilers class!

Furthermore, as a few of you
[complained](https://old.reddit.com/r/nyu/comments/k8uilm/the_state_of_registering_for_cs_electives_right/)
on
[Reddit](https://old.reddit.com/r/nyu/comments/k90h5t/cas_cs_is_going_from_bad_to_worse/),
the classes that we have fill up within seconds.

[^1]: A brilliant adjunct who is active in the programming languages
    space, but still.

My natural inclination here is to demand that NYU hire more
professors. They probably should, but that's a harder problem than it
seems. Plenty of professors are being poached by industry, and
besides, NYU has to compete with a lot of schools for professors. As
much as I'd like to criticize NYU for this, I'll admit they have a
tricky problem on their hands.

Ditto with having professors teach less graduate courses. The masters
courses are a cash cow and Courant needs the money[^2]. PhD courses
are of course a very important part of getting a PhD.

[^2]: There's a whole history lesson here but the short is that
    Courant doesn't get defense money anymore.

Instead I'll make the claim that NYU is failing at a classic computer
science problem: resource allocation. If you have limited resources,
e.g. CPU, RAM, professors, what do you do? You optimize!

And it turns out that teaching is nicely optimizable. For one, it's
[embarrassingly
parallel](https://en.wikipedia.org/wiki/Embarrassingly_parallel). CS
lectures scale really nicely. It doesn't matter if 20 or 100 people
are watching. The lecture works the same way. Oh sure, some professors
have participation and activities, but frankly those could be done in
groups or at recitation with a TA. Right now we have small classes for
our CS core requirements. My CSO course was 30 students max. That's
great for our rankings but less great for resource allocation.

There's likely a concern about classroom space. Courant isn't a
building with many large lecture halls. There's some possible
solutions. Even after in-person classes resume, we could still have a
system where some students go to a different classroom and watch the
lecture projected onto a screen. Other students will likely attend
from online because they're unable or do not wish to attend in person.

Circling back to TAs, they're quite an underused resource. Professors
are great, but they're often removed from an undergraduate's
experience. They're leading experts in their fields and may not
understand what it's like to struggle with the material. TAs can
bridge that gap. Yet, if you look at the opportunities mailing list,
you can see that we also have a TA allocation problem. We don't have
enough people who can be TAs and honestly, of the TAs I've had, a few
have been duds. Because most of them haven't attended NYU, they're not
particularly helpful with the curriculum.

Solution? Let undergraduates be TAs! It's what almost every other
school does. Oh sure there's likely some issues with graduate student
unions. I'm sympathetic---graduate students use TA positions to make a
living. The answer is rather simple. Let graduate students have the
[right of first
refusal](https://en.wikipedia.org/wiki/Right_of_first_refusal). All
gigs are open to graduate students first, and then undergraduates
second.

I suppose there's some concerns about conflict of interest. I
understand these concerns, but it's hard to take them seriously when a
whole slew of schools allow undergraduate TAs with little to no issues.

With this new model, we can have one to two sections of each core
class. The professor will be aided by a veritable army of TAs, enough
to provide a small group for activities. Some of the students may have
to attend the lectures over Zoom, but likely some will want this.

This model will help with a few other problems. Currently classes are
super inconsistent. Depending on the professor, Operating Systems may
be in Java and a relatively shallow course, or it may be a class in C
that covers the intricacies of Unix to a respectable depth (I may or
may not be biased here). If one professor teaches the class, they will
set the tone. Perhaps NYU could even operate in a system where
professors agree to teach the same class for 5 years. That way the
professor can get the course down and devote minimal time to
preparing, while the department gains consistency.

Why care about consistency? Some of the greatest courses in CS history
have been ones dictated by a single professor or a small group of
professors. Classes such as the original MIT Intro CS course 6.001,
Northeastern's Intro to CS course run by Mattias Felleisen et al, CS50
with David Malan, etc.

We could get into a whole post on why this is effective (auteur
theory?), but there's a few obvious reasons. For one, a consistent
course sets students up for success. All of the tutors and TAs will
have gone through exactly the same course. They can provide tips and
tricks on how to succeed. Currently if you take CSO with Gottlieb,
good luck tutoring someone who has Jinyang. I've written advice on a
course or two, but it's severely limited by the fact that courses are
highly inconsistent. I can't write an advice post on Operating Systems
because I took the course in C with Professor Walfish and I'm not sure
my advice will translate to someone who took it with a different
professor.

Professors will also get more practice teaching the same
subject. Having the same subject year over year lets the professor see
what teaching strategies work and which topics are challenging. I've
had too many classes where the professor was clearly shaky on their
lesson topics or exercises.

Consistency also means each course can know to a high degree of
certainty what the previous course covered. Professors won't have to
retread ground, which they do far too much right now. The amount to
which algorithms and data structures overlap is ridiculous. Ditto with
CSO and OS. Having a consistent curriculum will let NYU cover more.

But these are all secondary to the main benefit: **We can allocate
professors for other courses**. This means that some of the standard
undergrad professors can teach electives in their specialization. I'd
love for Michael Walfish to teach an advanced systems course or for
Victor Shoup to run an advanced algorithms course. They can also teach
some graduate courses, providing professors like Patrick Cousot the
chance to teach an undergraduate elective. These courses will
naturally be smaller, so hey, ranking benefit.

What I've noticed about NYU CS' response to requests is that it's
primarily prefaced by "we can't". We can't offer more classes. We
can't make classes more challenging. We can't offer a compilers
course. I understand that these requests are demanding. But the answer
isn't to reject them immediately and immutably. We should solve our
problems through innovative ideas and not just treat them as facts of
life.

I understand that this proposal is a fairly significant change and
there are undoubtedly roadblocks that will need to be resolved. But we
can't fall back onto "we can't". We need to push forward
and provide a truly amazing education to students.
