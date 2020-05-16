---
title:  "To Learn A Language"
date:   2020-02-25 20:00:00 -0700
---

Ah programming languages. They're a common subject of inquery: What
language should I learn? How do I rate my language knowledge? How easy
is it to learn a new language? They're used as requirements on job
postings, as credentials on a resume and to maybe write some code
every so often.

Let's dive into the process of learning a new language, from syntax to
full fluency.

# Quantifying Learning

There's an often echoed sentiment that programming languages, past the
first or second one, are all the same and easy to learn. I don't think
this is wholly inaccurate, but I do find this a vast
oversimplification. For one, it breezes over what it means to learn a
language.

Learning a language can mean extremely different things depending on
your general level of experience, who you're speaking with, and the
language itself. For instance, if you're a student, I think it's
perfectly acceptable to claim that you know a language if you've taken
a course or two in it and written a few programs in it. Most likely
people aren't going to ask a student in college the ins and outs of
Java generic variance. If they do, that's on them. However a
professional developer should probably have at least a few months
worth of full time, professional experience in a language before they
claim proficiency.

This means that as you progress in your career, you may actually put
*less* languages down on your resume.

The language also matters. Python and Java show up on practically
every student's resume. Because it's so common, people will just see
it as a student putting their two terms of Java on their resume and
don't verify it. But if you were to put Haskell, a language that's
somewhat infamous for being challenging, on your resume, there's a
chance a dev will want to see if you *really* know Haskell.

Often with programming languages, there's a concept that is absolutely
key to a given language. With Haskell this concept is
[monads](https://en.wikipedia.org/wiki/Monad_(functional_programming)). In
C, it's pointers. In Rust, it's ownership. If you don't understand
these core concepts, I wouldn't recommend claiming you know the
language.

With other languages, there's sometimes a large surface area. C++ is a
gigantic language. In that case, I'd try to specify what subset you
know. Do you know modern C++ (C++11 and onward)? Do you know the
original C with classes? Do you know modern JavaScript (ES6+)? Or just
the basic `function`/`var` style? These are basically different
languages so it helps to clarify.

# Bare Minimum

With these ideas in mind, what's the bare minimum before you can go
around proclaiming you know XYZ lang?

To start, you should know the basic syntax, i.e. how to define a
function, how to write a Hello World, etc. You should know the general
categorization of the language, such as static vs dynamic typing,
imperative vs functional, scripting vs systems, etc. You should be
able to write a simple project in the language, perhaps a solid one
page command line tool or a simple web server.

When people claim learning a language is easy, this is generally what
they mean. It's not hard to learn the syntax, categorization and
enough semantics to write a simple program. Especially since most
languages look similar, so syntax is easily learned. And if you stick
to imperative languages, most of them have quite similar semantics.

However there are non-imperative languages, which is where the "learn
a new language in a day" proclamation breaks down. To give a real life
language analogy, romance languages are quite similar---it's not
terribly hard to learn French if you speak Italian or vice versa. But
you can't say that all languages are easy to pick up just because
you've only encountered romance languages. Somewhere out there Chinese
is lurking and it ain't easy.

I highly recommend learning a different paradigm than imperative as
it'll teach you a completely new style and a new approach to
programming. Functional programming is the classic alternative, but
logic programming languages like Prolog are also very interesting.

If you're at the bare minimum stage and applying for your first job, I
belive it's perfectly fine to put down that you know the language. You
may stumble a bit in an interview, but that's perfectly normal.

However if you're beyond your first or second internship/job, you
should be a little more strict with yourself on language
proficiency. Perhaps put a caveat such as "(familiar)" or "(learning)"
next to the language.

# Getting Comfortable

After the bare minimum, there's the stage where you get comfortable in
a language. This is where you start to learn the idioms and ideas
behind the language. You start to understand that there's a particular
way in which programmers of this language analyze and solve problems.

I faced this myself when I learned Ruby. I was at my first internship
where I was tasked to write a simple scraper in Ruby. I learned Ruby's
syntax and semantics, then wrote a first draft quickly. I figured that
past a few code refinements, the program should be ready for
production. However when I showed it to my mentors, they quickly
pointed out that I had written the code as if I were writing Python or
Java in Ruby. For instance, I would have code such as:
```
if name == nil
  return nil
end
```

Which, while semantically correct, is not quite idiomatic. The
idiomatic version, as pointed out to me, goes:

```
return nil if name.nil?
```

This may not seem like a huge difference. But idioms do matter. Every
experienced Ruby programmer will understand both lines of code, but
they'll immediately recognize the idiomatic version, whereas with the
first version they might take a second to scan. Not to mention the
second version is shorter and elegant. It's the difference between
writing a sentence that, while technically correct, is awkwardly
phrased and a little ungainly, versus writing a clear and concise
sentence.

If I'm reading code that clearly does not follow the idioms of the
language, I'm going to be a lot less confident in the author's skill
in this language, and therefore apply a lot more scrutiny.

A good place to pick up idioms are style guides. Plenty of big
companies have style guides for certain languages. Google has [a
few](http://google.github.io/styleguide/). Some languages come with
their own principles like
[Go](https://golang.org/doc/effective_go.html),
[Python](https://www.python.org/dev/peps/pep-0008/), and
[Kotlin](https://kotlinlang.org/docs/reference/coding-conventions.html).

I'd recommend that you be at this level when you apply for a full time
job with a language on your resume. A properly trained developer
should write idiomatic, well written code.

# Philosophy

Another big factor is the philosophy behind the language. Almost every
language has some guiding principle. These are different from code
idioms in that they're more vague and high level. Here's a few examples:

- Go: Fast, simple, stable
- Rust: Fast and safe
- Ruby: Fun and friendly
- Python: Clear, simple, elegant

Some of these philosophies are exposed directly. Go has the delightful
[Go Proverbs](https://go-proverbs.github.io/). Python has the [Zen of
Python](https://www.python.org/dev/peps/pep-0020/). Others are
expressed more indirectly via the community or popular libraries.

I'd try to get a sense of a language's philosophy. You don't have to
completely agree with it or follow it all the time. But it's a good
starting point and a great way to figure out the proper usecases of a
language.

For instance, if I were writing a microservice that needed to be
performant and I was working in a large company, where many people
might need to touch this code. I'd consider using Go since it
emphasizes speed, simple code and stability.

If I were writing a quick one off script that's doing some boring
string manipulation, maybe I'd use Ruby since it's friendly, quick to
use and makes even a boring task kinda fun!

# Developing Opinions

A classic interview question posed by, I believe, Steve Yegge asks
people for their favorite language, then their favorite and least
favorite thing about it. I really like this question. A good sign that
someone knows a language is when they can critique it in a well
thought out, reasonable manner. By that I don't mean the usual "OMG JS
sucks so much!!!" that you find online. A proper critique of a
language understands that every language has its strong areas and its
weak areas. That every language is fundamentally a tool that can be
used in certain situations and not in other situations. A proper
critique combines the facets of using the language, understanding its
idioms and internalizing its philosophy give an in depth, nuanced
assessment.

If you find a language utterly perfect, or if you find it utterly
irredeemable, you don't really know the language.

Bjarne Stroustrup famously said: "There are only two kinds of
languages: the ones people complain about and the ones nobody uses."
Use a language, find something to complain about.

Critiquing a language gets easier as you know more languages. You can
compare the different paradigms, the different tooling setups, the
different syntax. What you'll inevitably find is that you probably
don't prefer one exact language. You prefer this element of Rust, that
element of Go, this part of Ruby, etc. Which is bittersweet, since
you'll never get the perfect language.

Another important part of critiquing is that you start to carve out a
subset of the language that you like and prefer. Perhaps you start to
avoid multiple inheritance. Maybe you learn to not use `var` in
JavaScript. Some people believe that learning a language entails
learning all the features and neat little edgecases. Which isn't
wrong. The next step is to take all of that knowledge and select only
the elements you like.

# Diving Underneath

If you truly want to understand a language, you need to dive under the
hood. What's great is that practically every language has an open
source implementation out there. Clone it, read the source code, and
tinker with it.

You can learn a lot from implementation. Some languages are impossible
to fully understand without understanding their implementation. I
wouldn't trust a C++ programmer who doesn't understand object memory
layouts or vtables. I wouldn't trust a Java programmer who doesn't
understand garbage collection.

A lot of languages are implemented in themselves, a process called
bootstrapping. Often times this implementation is a great example of a
large scale codebase in this language.

However contributing to the implementation isn't always the same as
knowing the language. If the implementation is not in the language,
then you're not writing in the language. Plus compiler or interpreter
writing is very different than normal development. You may end up with
a different set of idioms and best practices.

# What Language Should I Learn?

Yeah yeah yeah you say. Who cares about working on a compiler? I want
to get hired. What languages should I learn to do that?

Well, anything really. As long as you're learning a language and
writing code in it, you'll be hireable. If you learn more common
languages like Python and Java, there's no shortage of jobs that use
both. If you learn something more obscure like Haskell or Rust, you'll
get some solid nerd cred from it. People worry too much about the
right language. They worry that if they don't learn the precise
language that the company is hiring for, they won't get the
job. That's not true at all. Unless the company is hiring for a senior
position who will have major architecture control, they shouldn't care
that much about language.

I believe Joel Spolsky said something along the lines of if you hire a
top notch programmer with no experience in Ruby for a job, in a year
you'll have a top notch programmer with a year's experience in
Ruby. If you hire a mediocre programmer with 4 years of Ruby, in a
year you'll have a mediocre programmer with 5 years of Ruby. Guess
who's gonna be the better hire?

Part of the problem is that people take job listings too seriously. If
a job listing says it requires 2 years of Java for an entry level
position, it's not *really* asking for 2 years. It's more a "it'd be
nice if you had around 2 years"

Large companies often use several different languages anyways. Just
apply and find out.

If you're *still* unsatisfied with this response, and just need a damn
answer, learn JavaScript. People complain endlessly about it but you
can't find a language with more usecases and more jobs. You can write
mobile applications, front end, back end, even machine learning in
JS. Plus modern JS is a quite nice language.

If that offends your sensibilities, then great, learn whatever
language you believe is better.

**Addendum**

Joining the language community can be a great way to learn a
language's idioms and philosophy. It can also help you choose your
preferred language. Certain languages emphasize values such as
niceness, clarity, stability, etc. This can matter more than even
technical factors. After all these people will most likely be your
coworkers and collaborators.

Depending on the language, the community may cluster in different
locations. I know JavaScript people are pretty active on Twitter,
Haskell has a decent IRC channel and most languages tend to have a
subreddit. Check them out!
