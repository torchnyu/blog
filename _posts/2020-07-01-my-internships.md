---
title:  "My Internships: Applying"
date:   2020-07-01 18:00:00 -0700
---

I'm going to do something a little different. Because this blog has
clearly been lacking some self indulgence, I'm going to talk about my
personal journey interning at various places. First up is the job
application process. Due to a few factors, I was lucky enough to start
programming seriously in high school. I then took a gap year, which
allowed me to intern at two different places. I then spent the summer
after my freshman year working on a Google Summer of Code project (not
an internship!). The summer after my sophomore year I was lucky enough
to get an internship at Microsoft. Finally I just finished a round of
internship applications for next fall and am interning at
Cloudflare. I'm going to walk through how I applied, interviewed and
got the offer from each place.

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

# Internship #1: Finance

My first software development internship came about during the summer
after my senior year of high school. I had lazed around on the couch
for a month or so and my parents wanted me to do something with my
summer. A family connection put me in contact with a hedge fund using
a Ruby and C++ stack. I emailed them and they set up an interview in
person. The interview consisted of them reading my resume, asking
about some projects and having me write some SQL. Even though I didn't
know that much, they were very nice and helpful. It was probably the
easiest job interview process I've ever been through.

They emailed me back within a few days and told me when to start. The
job was unpaid, but completely geared towards teaching me instead of
benefiting them. They taught me a bunch of massively useful skills and
when I started to produce somewhat useful work, they started paying
me.

# Internship #2: Web Dev

I left my finance internship to go travel. After traveling for several
weeks, I came back and started looking for another internship.

I looked around for jobs in various places, but I didn't have my
application game down yet. I applied to a few places on sites like
AngelList, BuiltInNYC, etc. Since I was a high school graduate with
little experience applying during an off-season for internships, I
didn't get a lot of responses.

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
nice to have options.

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

At the start of my sophomore year, I was determined to not get
rejected all over again. I made a plan: email everybody I could about
getting an internship in programming languages.

This was moderately easy. A surprising amount of developers have
publicly available emails. If I had a little more chutzpah, I would
have guessed some more email addresses.

I asked my mentor from GSoC to help me with some people, but mostly I
just sent cold emails. Some of the people I reached out to included
Chris Lattner, the creator of Swift and LLVM; Guido van Rossum, the
creator of Python and Anders Hejlsberg, the creator of TurboPascal, C#
and TypeScript.

I got some responses---Chris Lattner and Guido van Rossum both
responded---but no real success. However I had two major improvements
in my job applications from last year: the Google Foobar challenge and
a phone interview with Microsoft.

The Google Foobar challenge is something that happens if you search
the right terms on Google. Your search results peel back and they
offer you a coding challenge. I accepted it and started working on
it. The challenge took a while but eventually I got far enough for a
Google recruiter to reach out. However this only dumped me into the
beginning of the actual Google application process. Which is a little
dumb imo. I shouldn't have to take another coding challenge after
Foobar.

The Microsoft phone interview went kind of well. I was given a fairly
easy question, but I didn't get the answer immediately. I suppose it
was clear that I was working through the question real-time and not
pulling an existing answer out.

Anyways after that I had an on-campus interview which went
fantastic. I solved the problem easily and the interviewer definitely
seemed pleased.

Then came the on-site. I was flown out to Seattle and put up a nice
hotel. They gave four interviews in total. The questions weren't too
hard or unconventional. I did two of the interviews in Haskell which
was quite fun. The first question I did in Haskell was a simple
removing of duplicates in a linked list. The second was a slightly
more complicated one involving trees. I'm not sure if Haskell was the
right choice for either, but it was certainly fun explaining it to the
interviewers. The final interview went fairly well, though I didn't
get the last part of the question. It was a quite cool question
though---in binary search there's a very particular edgecase related to
integer overflow.

The last interview was quite odd as well because the interviewer
simply lead me out of the building and to the parking lot. No
ceremonial gesture or gift bag, just essentially "get out". I assumed
I didn't get the job.

To my surprise, I got an offer. However it was an offer with a tight
deadline, I believe 2 weeks. I tried to extend it but Microsoft
wouldn't budge. Alas when I told my Google recruiter about said
deadline, hoping to speed up the process, they instead rejected me. At
least they had the decency to reject me via phone call.

Putting the deadlines into perspective, I was able to apply to
Microsoft, have a phone interview, an on-campus interview and get
flown out to Seattle for an on-site, in the amount of time it took
Google to schedule two phone interviews. Take that as you will.

When I got to Microsoft, I actually had a meeting already scheduled
with someone who explained that the email I sent to Anders actually
put my name in the application system and likely got me the phone
screen. It gets even more interesting than that, but that's another
blog post entirely.

I also sent off applications to GitHub and Stripe but was rejected. In
GitHub's case it was due to a coding screen that was pretty
unspecified and not well designed. I was supposed to write code in a
repo that would then be subjected to automated tests. That I couldn't
see. Yeah...not great. Stripe autorejected me after I did their
HackerRank screen. No clue why.

# Internship #4

I blocked off this summer to travel (yeah...) and work on my own
projects, so I purposefully did not intern anywhere. However with
coronavirus and all, I decided to take the fall semester off and work
instead of attending online classes.

While I did block off this summer, I did have one or two companies
that I was willing to consider. I applied to Jane Street, a prop
trading firm that is famous for using the functional programming
language OCaml. Jane Street rejected me after a phone interview. I'm a
little puzzled why---I thought the interview went well---but I suspect
I just didn't wow them.

I also applied to Citadel. I figured it was a shot in the dark. NYU
isn't a target school and I don't have a 4.0 GPA.

I got a phone interview, which I was actually really nervous for. I
don't know why, but something about Citadel made me
anxious. Fortunately the problem wasn't too hard, my mind was in the
right place and I had some nice tricks that I pulled off. I also used
an unconventional language. The result was one of my most successful
interviews (in my view).

After that I got invited to on-sites. Due to a miscommunication, I
missed one of the interviews, but I managed to have three out of the
four. Again I don't think I did very well. I got the first interview
fairly well, but I got stuck on the last question and claimed that the
algorithm was O(n log n) and not O(n)[^3]. I got the second question
reasonably well since it was a more finance specific question,
although I had a weird bug that confused even my interviewer. The
third interview wasn't great. I didn't get very far at all and missed
a really elementary optimization. I got the feeling the interviewer
was a little disappointed.

[^3]: Okay okay technically it's both because big-O are sets for upper
    bounds but I'm not gonna write an omega here.

In a recurring theme, I thought I did badly, but somehow I got an offer.

Funny story, I actually forgot what season my Citadel application was
for, so I asked the recruiter. She responded that she was going to ask
me that question!

While I was waiting for the Citadel offer process to go through, I
decided on a whim to apply to Cloudflare. I had read their blog posts
and knew they were working in WebAssembly, Rust and compilers, all
areas of interest for me.

I knew they had summer internships open still, but I wanted a fall
internship. I decided to cold email the one person whose email I could
easily get: the CEO. I got his email off of Twitter and shot off an
email.

A quick disclaimer: I'm confident in sending cold emails because I
have very particular interests that I have pursued on my own. I was
able to craft a pretty convincing argument on why Cloudflare was a
good fit. Please don't do this if you're just going to write an email
arguing how you're "really passionate about computer science".

The CEO responded and I got into the application process. I'm a little
hesitant to talk about this process because this was a very unique
situation. I happened to have experience in a somewhat niche area that
Cloudflare also happened to be working in.

Yadda yadda, I got an offer from Cloudflare. I deliberated a little
bit: The Citadel offer was quite generous. The Cloudflare offer, while
still quite good, was not at the level of a top hedge fund. However
the Cloudflare offer was such a great fit in terms of technologies
that I couldn't resist. I'm really appreciative to both companies for
taking the time to meet with me. And I'm super excited to be working
at Cloudflare in the fall!

# Conclusions

I've learned a few lessons from these applications:

- When you're starting out, apply EVERYWHERE. Don't be too
  proud. Anything that is paid and programming will help you immensely
  moving forward

- Once you get offers, be more particular. Vet the companies and push
  back against exploding offers.

- Try unconventional application methods. Send cold emails **if you
  have something to say**. Use family contacts. Be shameless

- It's okay to not have internships sometimes. Especially if you have
  your own projects. You may go from begging companies to give you the
  time of day to declining internships faster than you'd think.

- Getting good at a popular technology can be helpful. Knowing React
  and modern front-end has helped me a lot in various ways.

- Developing a niche can also be good. You don't have to, but if you
  can honestly claim to be one of maybe 30 people who can do xyz, that
  makes you a waaaay better sell.

- Your perception of interview performance is not correlated at all to
  how you actually did. If anything it's negatively correlated.
