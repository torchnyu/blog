I was rereading my old posts, as one does, and I saw that I had
promised an entire blog post about a specific, awful internship of
mine. Normally I don't make a habit of criticizing my former employers
publicly. However I'm well removed from this job and most of my former
coworkers. Besides, I'm not sure how many people still read this
blog. I'm not going to name the company, although it's not hard to
figure it out.

# The Interview

I got this job during my gap year in between high school and
college. I had done an internship at a small hedge fund, which I had
gotten from family contacts, then I did some traveling. I highly
recommend traveling if you can afford it. I managed to go through
Europe, had a really great time, and picked up some skills in self
sufficiency. I came back from the trip in early December and decided
to start looking for jobs. Of course December is a terrible month to
look for jobs because everybody's either on vacation or preparing to
go on vacation, so I started looking in January.

This was hard. I go into it in [my internships
post](https://blog.torchnyu.com/2020/07/01/my-internships.html), but
it was really quite frustrating. One annoying aspect of big companies
is that they require you to apply to very specific roles, i.e. a
summer internship or a fall co-op position. If you don't fit in those
boxes, they won't even have a place for you to apply. Besides, I
wasn't even a college student.

I tried going back to my internship at the hedge fund but they were
too busy. No harm, they had given me a really great few months of
mentorship and I'm still extremely grateful to them. I kept on
applying to different places and finally got a job at this company
MyTime (name changed). I went over the interview process in the
previous post, but I think it's worth highlighting the red flags.

For one, they had a ridiculous online assessment. They asked me to
write a JSON parser (which I did with `import json` in Python), an
extremely difficult task. Then, in the on-site interview, they asked
me essentially random programming trivia like "what's the package
manager for Rails", some of which the interviewer himself didn't
know. The interviewer in that case was a man named Esteban (again name
changed) who...I'll talk about a lot more.

Later on, when I was at MyTime, I compared notes with other
programmers and we all had pretty bad interview experiences. Which
gives us the first good lesson: If you leave your interview confused,
annoyed or insulted, you should probably not work at this company.

I also remember asking some standard vetting questions such as "do you
do usability testing?" and "what is your code review process?". The
answers were predictably bad: MyTime ostensibly used various style
guides but not really; they had testers but no real usability
testing. And remember, what they tell you in the interview is the
*euphemistic* version. The reality is a lot messier.

I was pretty aware of these issues at the time, but I also wanted a
damn job, so I accepted their offer.

# The Company

So what was MyTime? They were a company founded in the mid 2000's that
ostensibly focused on virtual reality. However, that was kind of a
stretch. While MyTime was working on various VR/AR ideas, the backbone
of their business was their online tour business. Online tours were
these virtual "experiences" where people could navigate a college
campus in a Google Streetview type setup. These could include 360
video, 360 images, or just regular static images. Colleges, companies,
etc. all bought them as promotional material. And while there was an
option to use Google Cardboard with these tours, calling them a VR
product was an extreme stretch.

One interesting aspect was that MyTime made the content in house. And
while the work was not high art, it was fairly impressive. They were
essentially a specialized advertising firm pretending to be a tech VR
company.

MyTime had an interesting founding story. The co-founders had met at
college, where as international students they had bemoaned their
inability to see the campus ahead of time. They decided to fix this
problem and founded MyTime. They didn't take any funding beyond some
money from the founders' families and they remained in the c-suite
positions. Astute readers are likely noting that this means all of the
c-suite had minimal job experience. Not only was that true, because
they didn't take any funding, the founders were not beholden or
supervised by anybody except themselves. Another good lesson: when
applying for a job, look into the power structure of the company.

The CTO, Omar, played a significant role. You see, Omar, as many
successful businessmen are, was a rather egotistical fellow. He
considered himself quite brilliant. However, his view of his
brilliance exceeded the success of the company, hence the insistence
that MyTime was a VR company, not an advertising firm with a web
interface. And he clearly wanted MyTime to push upward to bigger and
greater things---not a bad goal mind you.

The only issue? Because Omar was accustomed to being his boss, because
he was so egotistical, he was unable to take the steps necessary to
really manifest his dreams. He refused to take VC money. He refused to
delegate power. And worst of all, he refused to hire well. Omar
exemplified the phrase "first class people hire first class people;
second class people hire third class people". The company was full of
people, many of them nice folks, who were simply not the best. Many of
them had interviewed with Omar, an experience often confusing,
annoying or insulting. To take the job after that, one would have to
be desperate.

And do you know what the worst part about the company was, the truly
awful, terrible truth? It was surprisingly successful! MyTime made a
respectable amount of cash. They weren't pulling in billions of
dollars, but they were a bonafide successful business. It turns out
that colleges, as well as many large companies, have pretty decent
advertising budgets and are willing to shell out for a "virtual
experience" that, fortunately for MyTime as we shall see, nobody
actually uses! MyTime was in an enviable position of selling a product
that nobody actually used to a customer who had plenty of cash and
very poor judgement.

Why was this so bad? There's this theory of business that I've
noticed, and is probably codified in some business text, that
companies can become victims of their own success. If a company finds
a really strong [product-market
fit](https://en.wikipedia.org/wiki/Product/market_fit), it can often
be extremely hard to expand out of it because the entire company up
until that point has been oriented around said fit. Furthermore, the
company doesn't have any urgency to expand, as its main product is
still generating money and in many cases still growing.

The classic example of this is Google. Google has the most
ridiculously good PMF in advertising. They are the most effective
advertiser in the world, barring maybe Facebook. The upside of this
success is that Google has no real need to make a second big
product. Ever notice how Google [kills](https://killedbygoogle.com/)
so many of their products? It's because they have no need to maintain
their products unless it becomes a trillion dollar industry.

Of course not every company falls into this trap. Amazon is a
~~terrifying~~ great example of a company expanding its markets all
the time.

With MyTime this was happening on a mini-scale. The company was
successful, but because of its success, it could afford to
stagnate. How did it stagnate? For one, the codebase was
garbage. Utter garbage. It had started out as a PHP codebase written
by Omar in his college years. Then, it had migrated to a custom
model-view-controller (MVC) framework in PHP. From there, the team had
decided to complete a rewrite in the latest hot stack of React and
Redux. They didn't really understand modern JavaScript, or React or
Redux[^1], so you can guess how that rewrite went. However, because
the product was used by nobody and wildly financially succesful, they
received no negative feedback.

[^1]: Granted neither did I until quite a few months after I left MyTime.

And believe me, if someone had used the product they would have given
feedback. It was slow with terrible usability. It had innumerable
bugs. It wasn't even a very good tour of the college.

# The Work

I started working at MyTime shortly after the interview. They gave me
a somewhat old Mac Mini, which was both good and bad. Good in that I
saw how slow JavaScript can be on old machines, bad in that I saw how
goddamn slow JavaScript can be on old machines.

MyTime, like any tech company these days, had an open office plan. I
was sitting at a long table next to my manager, Dan, and surrounded by
other members of my team. This was a [terrible
arrangement](https://www.joelonsoftware.com/2006/07/30/private-offices-redux/)
for a few reasons. One, it meant no privacy from my manager. As any
developer can tell you, nobody is 100% productive. Most people, even
if their days are completely free, cannot code for more than say 4-5
hours a day. However, Dan seemed to not understand this. If I were to
seemingly slack off, by, say, going on reddit, he'd lead over and say
something delightfully passive aggressive like "hey, how's it going?
Can I help you with anything?"

Second, open office meant open to distractions. Esteban had this
infuriating habit of constantly rubbing his hands together. He'd do it
really quickly, like a nervous tick or something. Perhaps this is just
me, but there's something about a constant, low level distraction that
is mind breakingly annoying. And, yes, I could have confronted Esteban
about this, but I was not as confident in confrontation just yet.

There was also a team working on some sort of AR project, one of
Omar's attempts at expanding the company beyond its core product. I
can still remember core details of the project to this day, which
indicates how goddamn distracting it must have been. And yes, yes, one
could argue that this is the precise sort of cross pollination that an
open office provides. However my job was nowhere close to theirs and I
never used any of that information in a beneficial manner to the company.

As for the work, well this was not the carefully designed and scoped
intern projects that I later experienced at Microsoft and other
companies. Instead I was thrown into a profoundly messy, poorly
written codebase of JavaScript and PHP. To say it was difficult is to
understate it immensely. I could not understand the codebase for the
life of me. The team had adopted a whole host of technologies that
they didn't fully comprehend. Worse, they had decided that their way
out of this mess was to add more technologies they didn't understand.

I distinctly remember arguing with Esteban, a fervent [magpie
developer](https://blog.codinghorror.com/the-magpie-developer/), about
Docker. In retrospect, neither of us really knew what we were talking
about. The difference was that I admitted this ignorance, while
Esteban ignored it, making claims about what Docker could do that far
exceeded its actual capabilities. The argument ended with Esteban
laughing, and me fuming, not wonderful. This shouldn't be necessary to
state, but you should never laugh at your interns.

Looking back with a better knowledge of Docker, I'm not even sure it
would have helped their deployment. At MyTime the codebase was a
massive multi-gigabyte repo, filled with various random files, some of
which were not needed (but nobody knew which). Because it was a PHP
stack, their deployment strategy was to copy this entire
multi-gigabyte repo up to their servers. Fixing this didn't require
Docker, it just required some plain old refactoring.

There's a lot more I could talk about like how their API fetches were
these horribly organized megabyte large data dumps, how their product
naming changed multiple times and the remnants were left in the
codebase, how nobody knew all the different features and aspects of
the product. But that'd take an entire book.

Instead, let's talk about the most annoying aspect of working on the
codebase. You see, I'd come across some terrible aspect of the code,
maybe a horribly designed component, and I'd ask around about how the
component came to be, who wrote it, etc.

And nobody would know! They'd all shrug and claim ignorance. And yet
the bad code kept pilling up. There wasn't any sense of ownership in
the codebase. Nobody felt responsible for the mess, so nobody was
willing to clean it up.

In fairness, it was an extremely daunting mess to clean up. I tried at
several points to refactor, but I had neither the skill in JavaScript
nor the tactical awareness necessary to pull it off. Refactors are
worth a blog post in of themselves, but in short, they're not as easy
to do as people think. A good refactor needs to be scoped, accessible
to the rest of the team and not introduce any regressions. Otherwise
you run the risk of breaking more than you fix, which isn't great for
the product and lowers your credibility with the team. In especially
sub-par environments, the team may take this as a lesson to not
refactor or to ignore your advice.

Not to mention, refactors benefit from having the original author
around. Otherwise you run the risk of repeating the same mistakes.

So why did nobody know? For one, there was a lot of turn-over on the
team. After all, with that codebase and that management, why would you
stick around? Not to mention, the pay was pretty awful. I was paid
20/hr, a decent salary for a high school graduate living with his
parents. Y'know what one of my fellow developers was paid? Also
20/hr[^2]! That's an utterly insulting amount for a full time
developer in New York. Sure, he started out as an intern after a
bootcamp, but 20/hr is bad.

[^2]: Actually 40k/year but translated to hourly it's about 20/hr

- Team
  - Kevin: Underpaid
  - Akhil: Deliverables
  - New guys
- Trenches
