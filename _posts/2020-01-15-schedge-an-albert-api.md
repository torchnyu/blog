---
title:  "Schedge: An Albert API"
date:   2020-01-15 20:00:00 -0700
---

Show of hands here, who hates Albert? No, not your buddy Albert, who
I'm sure is a great person. I'm talking about [NYU's
Albert](http://albert.nyu.edu/albert_index.html), the *wonderful*
course registration site that totally doesn't make you want to murder
someone.

I, for one, detest it. I could go on and on about how much I hate
every little detail, but let's stay focused here. Fortunately, my
friend, [Albert Liu](https://github.com/a1liu/) (yes yes, the irony is
palpable) at [BUGS](https://bugs-nyu.github.io/), has built a solution
in the form of Schedge.

What is Schedge? Schedge is a program that scrapes Albert, then
provides a simple API for course data. You can query course data from
different semesters with all the corresponding meeting times and
recitations.

Of course with this data, we can easily build a better user interface
for exploring courses. I've already written a quick [proof of
concept](https://courses.torchnyu.com/). It's not much to look at, but
it's a start.

However that's just the beginning. You see, Schedge is more than just
a way to build course explorer: *Schedge is whatever you want it to
be*. Want to build an app that visualizes course times? Go ahead! Want
to see how course options have changed over the years? Why not? Want
to make a random schedule generator? Do it!

I'm really curious to see how people use Schedge. Torch's mission is
to promote and incubate NYU's CS community. Hopefully, by offering an
API to a problem so near and dear to NYU students' hearts, we can get
people writing code to solve their everyday issues. If people can
build projects with passion and dedication, then they'll learn far
more building than from any course or any lecture. And nothing
inspires passion more then waiting for Albert to goddamn load.

Schedge is still very very new and therefore will go through some
growing pains. We're adding features as quickly as we can, but there's
only a few developers currently. Which is another place where you can
help! We specifically chose a stack for Schedge that makes it easy for
NYU students to contribute. Namely, we wrote Schedge in Java [^1] with
a very simple framework called [Javalin](https://javalin.io/). If
you've taken Intro to CS at NYU, you can contribute! If you haven't,
you can also contribute! We will happily teach you Java and everything
else you need to know.

[^1]: Well actually Java and Kotlin but we're slowly moving it to just Java.

If you're interested, reach out to either
[Albert Liu](https://github.com/a1liu/) or
[me](https://github.com/nicholaslyang). Or just clone the
[repo](https://github.com/a1liu/schedge) and start playing around.

Schedge is currently up [here](https://schedge.torchnyu.com/). There's
a minor issue where http links aren't redirected to https, so don't go
to http://schedge.torchnyu.com/ and come running to me that the API's
down. We use HTTPS for everything...whether we like it or not. We have
basic API docs set up, but feel free to ping us if something doesn't
make sense.

Now go out there and build something with Schedge!
