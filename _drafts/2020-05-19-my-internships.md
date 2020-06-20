---
title:  "My Internship Applications"
date:   2020-05-19 20:00:00 -0700
---

I'm going to do something a little different. Because this blog has
clearly been lacking some self indulgence, I'm going to talk about my
personal journey applying to internships. Due to a few factors, I was
lucky enough to start programming seriously in high school. I then
took a gap year, which allowed me to intern at two different places. I
then spent the summer after my freshman year working on a Google
Summer of Code project (not an internship!). The summer after my
sophomore year I was lucky enough to get an internship at
Microsoft. Finally I just finished a round of internship applications
for next fall and am interning at Cloudflare. I'm going to walk
through how I applied, interviewed and got the offer from each
place.

Overall I've been very fortunate in many ways: I've utilized family
connections; I've had gambles work out and I've had some excellent
mentors.

# Internship #0: Lab Labor

My first internship, if you can even call it that, was at a lab over
the summer. The job was basically pity-given to me via a family
contact. I met the contact to ask about advice for research labs and
he took it as me asking if I could intern at his lab. In retrospect,
this wasn't really what either of us wanted. I learned that asking
someone a seemingly innocuous question can turn into an accidental
imposition on them.

As for the job, it was unpaid work that consisted of first programming
some models from various papers that I didn't really understand. I
wrote the first few models in MATLAB, then when that got unwieldy, I
switched to Java. I figured out a hacky way to get MATLAB to graph the
Java simulation by having Java output a bunch of text files that
described the simulation, then having MATLAB load them and graph it.

After that, I was partnered with a college student from Australia. He
and I were in charge of this project involving a mechanical fish. I'll
spare you the details but it involved attempting to waterproof a 3d
printed fish model that would contain expensive electronics. After
lots of failed attempts involving a 3d printer in one of the most
disgusting rooms I've ever seen and some really messy waterproofing
silicone material, I slipped away at the end of the summer.

# Internship #1: Finance

My first software development internship came about during the summer
after my senior year of high school. I had lazed around on the couch
for a month or so and my parents wanted me to do something with my
summer. Another family connection put me in contact with a hedge fund
using a Ruby and C++ stack. I emailed them and they set up an
interview in person. The interview consisted of them reading my
resume, asking about some projects and having me write some SQL. Even
though I didn't know that much, they were very nice and helpful. It
was probably the easiest job interview process I've ever been through.

They emailed me back within a few days and told me when to start. The
job was unpaid, but completely geared towards teaching me instead of
benefiting them. They taught me a bunch of massively useful skills and
when I started to produce somewhat useful work, they started paying
me.

# Internship #2: Web Dev

I left my finance internship to go travel. I traveled for a month and
a half, then came back home around early December. After the holidays,
I started looking for work.

I looked around for jobs in various places, but I didn't have my
application game down yet. I applied to a few places on sites like
AngelList, BuiltInNYC, etc. I was a high school graduate with little
experience applying during an off-season for internships, so I didn't
get a lot of responses.

This was honestly a very frustrating time. I spent some of it teaching
myself Ruby on Rails, but it did suck to apply to jobs and get nothing
back.

Eventually I got a response from a company with a VR product. I did a
coding challenge with them, one question of which was to write a JSON
parser. I remember I did it in Python with `import json`. Brilliant
solution. In retrospect a JSON parser is a relatively non trivial
exercise. I don't know if they ever got a legitimate answer.

Looking back at my emails, I guess I had a phone interview with
them. I don't remember if it was technical but most likely it was not.

After the phone interview I don't remember, I interviewed in person
with them. It was 3 interviews, two with developers and one with an HR
person. I don't believe any of the interviews were that technical. The
highlight, if you can call that, was one interviewer asking me what
the dependency manager was for Rails. I answered Bundler, because
that's the answer. He then stared at me for a few seconds, clearly not
knowing the answer himself, before responding that I was right. I
don't know what he was trying to accomplish with the question.

I asked a few questions about the company, such as their code review
process or any style guides they follow. They didn't give satisfactory
answers but at that point I didn't care. I just wanted a job.

They extended me an offer, albeit with a ridiculously short deadline,
something called an [exploding
offer](https://www.joelonsoftware.com/2008/11/26/exploding-offer-season/)[^1]. I
accepted it because eh, it was a job and paid (20/hr). Looking back, I
should have extended it a little. I received an email from another
company a few days later and it would have been
nice to have multiple options.

[^1]: Funny story, I read that exact blog post while working at this
    company. It was a wonderful moment of regret.

That place was an interesting ride. I learned a whole slew of modern
front end at the job which has served me well in many
ways. Unfortunately the codebase was not well written in many
ways. The programmers were pumping out features at an unsustainably
fast rate and had an "in the trenches" attitude closer to Verdun than
Versailles. Which, honestly, I didn't get. The product had a really
fantastic niche. They didn't have many direct competitors. They could
have spent the time to refactor the codebase. Ah well. The entire
experience deserves a blog post of its own.

# "Internship" #2.5: Google Summer of Code

After my gap year I came into my freshman year of college extremely
motivated. I applied to internships at a bunch of top companies. None
responded. I was in a weird state where I wasn't new enough to get
into the first year programs like Google Engineering Practicum (now
known as STEP) or FBU, but not good enough to get past the screening
for the actual SWE internships. I probably should have tried
alternative channels for getting internships, some of which you'll see
in the next few chapters.

After getting rejected from the top places, I considered going to
intern at other companies. But I wasn't sure about going back to a
small company. My last internship was *ahem* an experience and I
wasn't sure if I wanted to replicate that[^2].

[^2]: I *really* should write something about that place.

I was kind of content to work on my own projects over that
summer. After my gap year, I wasn't afraid of having extra time to
work on my projects. On a whim I applied to Google Summer of
Code.

Google Summer of Code is a program where Google pays students to work
on open source. You get around 7k for the summer, which isn't a bad
salary for a job with flexible hours and demands.

I had developed an interest in programming languages, so I decided to
apply with a project on the Ruby language. To apply to GSoC, you need
to make a project proposal. I applied at the last minute with a
project ripped directly from the suggested topics.

To my surprise, I got into GSoC. This was especially surprising since
the project proposal was also explicitly rejected by Ruby's creator
and benevolent dictator for life, Matz. I was able to spend the summer
ripping into Ruby's internals and attempting to add type
annotations. That turned out to be **hard**, as Ruby has some crazy
internals. I did have a wonderful mentor who did his best to help me,
but man, [DSLs embedded in comments that generate C code that manually
call Ruby functions by patching into the VM, which don't even exist in
the first place because they're autodefined using
`alias_method`](https://horriblyunderqualified.com/posts/wtf-ruby-pt-1/)
are confusing.

What was bittersweet about GSoC was that it did take away time from my
other projects.

# Internship #3: Microsoft

At the start of my sophomore year, I was determined to not have the
same experience as my freshman year. I didn't want to get rejected all
over again. I made a plan: email everybody I could about getting an
internship in programming languages.

This was moderately easy. A surprising amount of developers have
publicly available emails. If I had a little more chutzpah, I would
have guessed some more email addresses.
