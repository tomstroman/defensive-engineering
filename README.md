# defensive-engineering
A collection of thoughts on countering common threats to software engineering organizations' productivity

## What is this, and where are you going with it?
The thoughts expressed here are my own.

As of this writing in late 2024, I've been a software engineer for about a decade. For the last half of that time,
my day-to-day focus has been of a nature that I've come to describe as "defensive engineering." In early 2020 I became the
inaugural leader of a team within my company's engineering organization that was literally named "Shield"
(sometimes affectionately prefixed with "Agents of").

This Shield Team's mandate was simple to state: protect the rest of the
engineering teams from distractions. Our leadership had surveyed the current challenges facing the org, and
determined that non-innovative or "unplanned" (but necessary) work was dragging down overall productivity.
A backlog of bugs and technical debt was compounded by a steady stream of bug reports and other Support cases requiring
engineering investigation and intervention.

The existing practice was to distribute these interruptions to
all the various teams, and expect them to handle them in addition to their roadmap delivery commitments.
The status quo was disruptive and dissatisfactory, and leadership made a decision to concentrate this onslaught
of distractions onto a team designated to provide a first line of defense, "shielding" the other teams, freeing
them up to focus on their commitments as much as possible.

### Why you?
Because of
various proclivities I had already demonstrated (an affinity for solving complex problems, tenacity in
explaining root causes of obscure or severe bugs, and generally a record of making meaningful contributions
in challenging situations), I was a natural choice to lead this team, and I readily accepted the post.
I found Shield to be an excellent fit to my interests and talents. I thrived
in that role, and gained a lot of experience and learned many lessons.

This document (or perhaps, a collection of documents) is my reflection on defensive engineering as a
deliberate practice. It is not intended to tell other engineering departments how they should or
should not operate. It may not even represent my most current thinking on how to address the
challenges I set out to describe, especially from a prevention standpoint. But it may prove useful
to individuals or organizations, startups and established companies alike, as they explore their
options for identifying and addressing productivity below expectations.

### Other opinions?
I suspect that as soon as I put this out there, I'm going to start hearing about other people who have written on this
topic. My perspective has been limited -- mostly, I've been *doing* this kind of work rather than
*talking* about it. I expect there to be varying amounts of agreement, and disagreement, with other
material out there, some of it potentially very well known. I welcome the idea of discussion and dialog.
If it makes sense to, I'll add a section where I list other resources that I have encountered and how
I see them as relating to -- even continuing to shape -- my own views as expressed here.

## What is defensive engineering?
At its simplest, defensive engineering is the decision to protect the productivity
of a team by budgeting for the opportunity cost of non-innovative work. 

This can take many forms. An individual engineer who finishes some new code and chooses to look at
a bug from their team's shared inbox or backlog is, temporarily, choosing not to work on the next 
piece of new code. Meanwhile, their teammates are allowed to continue the work they have in progress.

A team that says "four days a week we code, and then have Bug-fix Friday" or "Tech-debt Tuesday" is
recognizing that non-innovative work takes time, and they're planning ahead for it. This is a form
of defensive engineering, even though the team is protecting its own productivity -- they sacrifice
a designated day of new code to protect their flow the rest of the week.

Teams may choose the concept of a rotation, where one engineer "takes one for the team" by being
the designated responder to new issues for some period of time, such as a sprint or two. There's
a prioritized backlog of technical debt rather than new feature work, and they pull from this
while also understanding that new bug reports or other interruptions might put the tech-debt work
on hold.

And my own experience of the last few years marks the other end of the spectrum, representing
the greatest commitment to defensive engineering: doing away with
the rotation altogether, and having a team of engineers in a quasi-permanent state of defense.
An engineering organization might decide to implement this solution as a short-term project
(say, six or twelve months to attain a measurable goal like reducing the backlog/tech debt by 75%,
or just until an important feature gets shipped without further delays caused by distractions),
or it could become part of the organizational fabric with a more open-ended mission. 

(I'll say this more than once, I'm sure: having an
engineer or team of engineers dedicated to defense is not a decision to make lightly, and it's
important to have a clear understanding of both why it's necessary for a given org, and also a
plan to reassess that necessity periodically. After all, I used the phrase "opportunity cost"
up above, and an engineer constantly playing defense is not directly building product that
translates into revenue, and the trajectory of their career growth can end up looking 
different from that of their coworkers. Young/early-startup organizations, take note: the
decisions you make in the early days about how to handle technical debt, code reliability,
observability/monitoring, and "one-off" special requests will set you on a path that either
eschews or embraces the need for dedicated defensive engineering expenditures later in your growth.)

## Don't we already have engineers "on call"? How is defensive engineering any different?
If you're providing a 24/7 critical service where
an outage on Saturday night can't wait until Monday morning for attention, it's likely that you've
got some engineers in a state of readiness to respond, and some (hopefully automated) monitoring
and alerts in place to get their attention when needed. I hope such incidents are rare enough
that you have no need for such a thing as a full-time on-call engineer, whose *sole* duty is to
respond to emergencies, and who in fact spends the majority of their time doing just that. It may
be the case instead that the burden of Saturday-night outage resolution is shared among a handful
of your most experienced, capable engineers, who spend very little of their time on incidents and
much more of it writing high-quality code, designing sound architecture, and mentoring others.

Defensive engineering may overlap with on-call in some ways, but an important distinction is that
much of what occupies the engineer's working hours doesn't usually rise to a level of urgency that
warrants Saturday-night attention. With that being said, an experienced defensive engineer may
be very valuable working side-by-side with on-call to investigate and resolve an emerging problem,
both by virtue of the breadth and depth of their product knowledge, and also by the investigative
and mitigative skills they've honed through the course of countless non-emergency defensive tasks.

Put another way: an on-call team responds to immediate threats to reliability, revenue, reputation,
generally the company's ability to continue delivering what customers already bought and use. They
fix outages. Defensive engineering (whether a team, a rotation, a planned day, or a distraction)
responds to the latent and pervasive threats to productivity in their many forms. Reduced productivity
is less tangible and immediate than an outage, manifesting instead in effects like a longer turnaround time for 
shipping new or enhanced product, slowing the sales or implementation cycle,
and possibly sabotaging a competitive edge.

## I'll humor you. What exactly are these "threats" you're defending against?
I look forward to describing them very soon.
