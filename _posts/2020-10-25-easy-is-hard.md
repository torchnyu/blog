---
title:  "Easy Is Hard"
date:   2020-10-25 10:00:00 -0700
---

We recently wrapped up [Spark](https://spark.torchnyu.com/), Torch's
mentorship program. Spark, if you're not familiar, is a mentorship
program where students are organized into batches with a few
mentors. Each batch creates a project from scratch and ships it. The
project and stack is determined by the members, but guided by the
mentors. I'm gonna write a post on general lessons we learned from
running Spark, but I thought I'd devote some time to one particular
lesson.

What's the role of a mentor? If you asked me that before Spark, I'd
probably say that a mentor should teach students the necessary tools
and guide them on implementing the project. That's partially
true. Mentors should help students implement the project. But there's
a more important role:

> A mentor should ensure that the project is easy and doable.

When students start brainstorming about project ideas, they're usually
quite ambitious. They dream up amazing apps with machine learning,
hundreds of users, complicated recommendation systems, etc. It's truly
wonderful seeing students embrace the possibilities of technology.

The only problem? Their ideas are totally infeasible. First, students
don't always know what goes into full implementations. A lot of them
are still in the phase where they're enamoured with technology, but
they may not know how the nitty gritty works. When you're in that
stage, it's quite easy to view tech as this magic wand that you can
wave and get features. I do it all the time. Sometimes I'm daydreaming
about some idea involving machine learning (I don't know machine
learning), only for me to realize that my mental model of machine
learning is:

1. Get a bunch of data
2. Feed it to an algorithm
3. ????
4. Success!

Yeah that's not how it works. Cool stuff takes time and effort. If we
want a feature like recommendations that learn off of previous
choices, we need to either put in a solid few months of work, or use
an off the shelf API. Even with an API, it'll take a bit to learn how
to use it properly.

These ideas aren't infeasible on a long term scale. If we had a full
year of time, we could easily make an app with authentication, a basic
ML system, maybe even cross platform. Unfortunately that's doesn't
happen. Students get midterms/finals; they join other clubs; they lose
interest. And the programming gets less interesting. Sure, building an
auth system is really cool, but then you gotta deploy it, maintain it,
expand auth with some weird feature that your library doesn't
handle...etc. We've all had side projects that flounder after a few
months.

The solution we came up with was to limit project length to 1-2
months. That's long enough to get a minimum implementation, but short
enough that people won't abandon it.

However, to get an implementation done in 1-2 months, it needs to be
**minimal**. That's where mentors come in. A good mentor needs to make
sure that the project is as simple as possible. This is usually more
simple than you'd expect.

Let's take an example. One group decided to build a Cards Against
Humanity clone that would take TV shows a user inputed and generate
cards. This is a hard idea. We can outline issues:

- How do we automatically generate cards from a TV show?
- How do we get data on TV shows?
- What does the game logic for Cards Against Humanity look like?
- How are we going to handle multiplayer?

We can fix each issue one by one.

- How do we automatically generate cards from a TV show?

Automatically generating is pretty hard. How about we curate some
shows to start? In fact, how about we just focus on one show?

- How do we get data on TV shows?

Since we're only focusing on one show, we can just download the show's
scripts and look at those.


- What does the game logic for Cards Against Humanity look like?

What if we focused on generating the cards before implementing the
game?

- How are we going to handle multiplayer?

If we're just generating cards, we don't need multiplayer.

With these changes, we want from a project that would require a
complex backend with multiplayer state, an online machine learning
algorithm, and an API for TV show data, to a project that involves
some Python scraping, basic NLP and a simple front end.

Some of you will counter that the simpler project sounds lame. And
yeah, I bet we lost a few people in the simplification process. But
it's really crucial to keeping the projects actually shippable.

Why do we care about shipping so much? For one, it's a great
accomplishment. Having something up and running is a great dopamine
hit. Second, it allows us a spot for people to walk away from the
project. Leaving a project in a half finished state isn't
fun. Shipping gives us a nice ending point, even if we didn't get all
the features done. This is really important cause people enjoy
starting projects more than they do finishing them. And while we'd
love to finish projects, we need to keep students engaged and coming
to meetings.

In a way, this is an evolution of the hackathon mindset. Hackathons
are great because they give you an excuse to start a project from
scratch and code like mad. You don't have to worry about whether the
code is good or whether the project actually works. All that matters
is that you get something done which you can show to the judges.

The problem with hackathons is the rampant cheating, the unhealthy
lifestyle, and the emphasis on judging and prizes. Don't get me wrong,
hackathons can be great. But there's only so many times you can see
the same "object identifier + hardware hack" win before it gets
old. Not to mention hackathons aren't exactly the most quarantine
friendly event.

I'm not sure how much longer I'm gonna stay engaged in the NYU CS
community. I'm going to be leaving NYU in the near future and frankly
I'm a little tired of talking about the same issues. But I hope that
some people pass down the spirit, if not the actual program, of
Spark.

PS. You almost never need a backend for small projects. Start with the
front end and if you still need a backend, write it after.
