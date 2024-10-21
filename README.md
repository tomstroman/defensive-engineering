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
This is going to sound gimmicky, but I realized that the main categories of things that
a defensive engineering team could reasonably expect to spend time on follows an alphabetical pattern,
with names beginning with A, B, and C. I further realized that this was also the *order* in which
those categories warrant attention and take precedence over each other. Finally, because my brain
didn't want to let it go, I realized that I could extend it all the way to A-B-C-D-E-F without losing
the priority sequence *or* going beyond how my team actually operated.

I will speak at greater length about each of these shortly, but without further ado, here are the six
threats, in decreasing order of day-to-day importance:
* **Alarms**, especially if you often have false ones.
* **Bug reports**, originating with end users encountering problems in mature or legacy components/products.
* **Customer requests** that are deemed worth fulfilling directly/manually instead of through product development.
* **Debt** of the technical variety, especially that without obvious ownership by another team.
* **Enhancements** of legacy products as deemed necessary by leadership but inappropriate for existing teams.
* **Features** that somehow don't fit the mission or roadmap of existing teams.

One important note is that the second half of this list (D-E-F) can include work that directly *reduces* the
prevalence of interruptions from the A-B-C half. When that's the case, it may be worthwhile to treat it with
higher priority.

Here is a little more about what I mean by each threat to team productivity. 

### Alarms
If you have automated monitoring systems that generate alerts, it's possible for such a system to get noisy.
Alerting noise causes multiple complementary problems: each alert requires one or more engineers to notice it
and pay enough attention to decide whether action is needed. And the compound effect of *false* alarms, in
particular, is alert fatigue in which specific channels of alerts, or all types of machine-generated alerts,
are judged to be "probably not urgent" and may not get read quickly -- or ever. Real issues can be drowned
out by a steady stream of ignorable alarms.

A defensive-engineering approach would be to become familiar with the various monitoring systems in use and the
kinds of alerts they're generating, and get relentless about fixing or reclassifying the underlying causes.
If the alert does indicate a real problem but one of low urgency, it *may* not make sense to fully resolve the
problem relative to other priorities (especially if it's very complex and risky to fix outright), but
at least introduce improved handling around it to reflect the broader team's assessment of urgency. For example,
catch a previously uncaught exception, write details to a log, and then optionally build an automated digest of
logged events that runs on some cadence (say, daily or weekly).

Summary: *False alarms desensitize the team and delay the detection of real emergencies. Fix them.*

### Bug reports
In this section I'm specifically focusing on reports of malfunctions within products or components that are
not undergoing active development, but that have been released and in use for potentially a very long time.
Every such report has the *potential* to be your first glimpse into a new, very serious issue. Most of them
will not be that, but they still represent a scenario in which real users -- paying customers, perhaps -- are
having a poor experience with your product. Not every bug is worth fixing quickly, or *ever* for that matter,
but every bug is worth a rapid screening by someone with the ability to recognize the true threat it poses.

I've seen situations where a customer mentions that some minor function -- hardly critical to their workflow,
not urgent at all -- has stopped working quite right. And it's not even broken in production, just in their testing
account on some customer-facing staging environment. The bug gets reported and dutifully escalated to engineering,
with the lowest possible indication of urgency and negative impact. But the cause of the misbehavior is actually
an undetected flaw caused by a new version of a third-party dependency that's two days away from being deployed
into the production environment, with potentially catastrophic effect. A simple glance at the server logs would
reveal this immediately and set things in motion to correct the issue before it reaches production. But because
the bug report either didn't recognize or didn't convey the true threat, there's a chance it may spend a long time
in an inbox or backlog someplace before an engineer even looks at it.

A defensive-engineering mindset treats every bug report as worthy of at least a cursory, time-boxed glance
by an engineer to screen it for the possibility of imminent or ongoing disruption. This doesn't mean fixing
every bug right away. It doesn't even mean fixing every bug. But even the screening process is time-consuming,
and there's a psychological overhead associated with context switch necessary for an engineer to pause what they were
doing when a new bug report arrives. That cost is greater if the investigative burden is being shouldered by
an engineer who was actively working on building the next great feature, instead of an engineer who was in the
middle of something more interruptible, like a technical-debt reduction task.

Summary: *Bug reports can bury the lede about the true impact and should be screened quickly for further escalation.
Screening costs less when it doesn't interrupt an engineer in the middle of deep focus.*

### Customer requests
I shudder as I begin this section because my challenge is going to be to meet the (admittedly low) standard of
brevity established by the preceding sections. I have much to say on this topic and will allow myself to omit it
here if I tell myself I'll write up a whole separate article. So, I'll *plan* on that.

The scenario I have in mind here is that a Very Important Customer has a need. That need cannot be met by the
existing product, and updating the product to accommodate that particular need is not a viable solution. It
might be that they're asking for new functionality that goes against the vision for the product and *should not*
be built in a general way. or maybe it would be completely appropriate, but there's no way to get it designed,
developed, and deployed in time to be useful to the customer. Nevertheless, the customer's case is very persuasive
and the company (engineering leadership) agrees that it is strategically necessary for engineering to help the
customer by giving them what they want.

This can be some of the most expensive work an engineering team does: it may require a great deal of creativity,
manual effort, time, or other resources (such as temporary additional infrastructure). It does not increase
revenue by contributing to the marketable product, and it takes time away from engineering resources who would
otherwise be doing precisely that. And, perhaps most perniciously, it sets a precedent by communicating that
engineering is willing and able to say yes to this kind of request now... and in the future. Saying no is harder
after you've said yes.

But despite all the reasons not to embrace this type of work, there are going to be times when it just has to
be done. Defensive engineering is being prepared for customers' disruptive requests. It means having someone in
place who understands how to ascertain the exact requirements and how to make use of existing components and
products to meet them, and how best to bridge the gaps that remain between existing capabilities and the
committed outcome (so this might be an engineer who's comfortable wearing a product-manager hat for short periods).
But more than that, it means you don't have to interrupt a productive feature-building team to meet that need.

Again, I hope to write at greater length about this elsewhere, but one quick thought: defensive engineering
should not consider a customer's request complete just because the customer is satisfied with what they've received.
Rather, the engineer or team that delivered the solution should spend a little extra time answering the question
"Why did engineering have to do this, and what would it take not to have to do it again?" Be specific, even
brainstorming a little about the kind of tool or feature that would have allowed the customer or their liaisons
to get what they wanted without involving engineering at all. No matter how impractical, no matter how unique the
request, good defensive engineering includes both handling the undesirable task *and* learning from it.

Summary: *Urgent requests from customers -- whether external/paying or internal -- can't always be avoided.
Interpreting and filling these requests efficiently, and figuring out how to avoid repeating them, is a skill set 
worth cultivating in an organization committed to defensive engineering.*

### Debt
Technical debt refers to the accumulation of deferred responsibility. For example, building something 95% of the
way solves 100% of the *immediate* need. Maybe the final 5% also represents an exaggerated share of the total
cost of development, and the same time could be spent getting halfway to viability on the *next* feature, and
we're really under pressure to ship... I know *you* would never say "we'll get to it later, after things
settle down a bit," but chances are good that *somebody* has said that, or made similar decisions to borrow
against the future for the sake of delivery in the present.

The existence of technical debt is something many organizations have accepted as an inevitable reality, and I'm not
even sure that's incorrect. And even a dedicated team will not eliminate all technical debt, so I'm not at all saying
that defensive engineering should mean trying to drive that balance to zero.

But some debt is ignorable only at an organization's peril. Defensive engineering means choosing
the timing and circumstances of defusing this or that latent threat to stability, reliability, scalability, etc.
instead of waiting until it explodes on its own. 

Summary: *Know what's festering in your tech debt backlog. Identify latent threats and deal with them before
they become an emergency.*

### Enhancements
Building new capabilities into an existing product or component is usually the kind of thing that defensive
engineering aims to, well, defend. But sometimes the adage is true: the best defense is a good offense. See the
**Customer requests** section above -- I've advised that handling a one-off request includes figuring out how
to avoid repeating it. Sometimes this leads to the identification of a gap in the product that would actually
be relatively straightforward to address, and when this is the case -- *especially* if the request has a moderate
likelihood of recurrence -- then it's worth figuring out how to get that capability added.

Other times, the enhancement does not come from an internal recognition of need to help meet or avoid customer
requests, but rather the enhancement *is* a customer's request, but with the luxury of time. For example,
a customer who is using the application in a way that's not adequately exposed through existing in-app reporting
may want a version of the report that includes their special usage. Building a custom report for them is an option,
but maybe it's the kind of thing that would benefit a larger customer pool. Altering the existing report to include
this new data, perhaps on an opt-in basis, makes sense -- but which team has room in their roadmap for this? Not
that you need a hint by this point, but here's one anyway: it's the one that was already working to understand 
what the customer needed and figuring out the best way to implement it, and maybe already did on a custom, one-off
basis.

Here's a twist: defensive engineering might not ultimately include the actual development of the enhancement. Perhaps
an existing feature team is best suited for that. But you can still defend their productivity by anticipating and
answering as many questions about the "what" and "how" -- working with customers, defining the requirements,
writing specifications, preparing a testing strategy, perhaps even creating and organizing work items in your
ticketing system -- these are all activities that make it easy for any available engineer to work confidently on
implementing the enhancement.

Summary: *Extending the functionality of existing products can be a powerful defensive strategy. Enlist the
help of feature-oriented teams if necessary, but aim for maximum clarity and simplicity in the requests you make.*

### Features
If you've read the "Enhancements" section above, you already know most of my thinking on this. It's rare that
a whole feature -- essentially an entire component or product capability that did not previously exist -- would
be considered a *defensive* engineering investment. And I don't mean it in the sense of "defending" a marketing
advantage by staying ahead of the competition on innovation.

Instead, building a feature -- designing, developing, and deploying it -- is a work of defensive engineering when
it's in the service of greatly decreasing the anticipated engineering cost of defensive engineering itself. These
features are not typically something that might show up in marketing materials, though they may help to close a deal
if their absence would be a deal-breaker for certain potential customers.

That seems kind of abstract so let me give an example. Perhaps customers have begun asking for reports on users'
activities within the system (for reasons that are not important) and the product doesn't have the capability --
either to keep track of that information in the first place, or to make it available to customer admins. This has
never been something Product has indicated as essential functionality or prioritized on any roadmap. Meanwhile,
customers' requests carry legal weight or other compelling reasons, so assembling such reports becomes a
painstaking process of searching and interpreting available logs and compiling the results into something
deliverable. 

In this example, defensive engineering means you've already handled the first couple of requests using what was
available and without having to slow down feature development to do it, and it means that you've *also* figured out 
how not to have to do it again. You know what's needed at a high level and in detail -- database tables,
API endpoints, servers, a web interface, test plans -- and you get the appropriate sign-off from relevant stakeholders.
You make the plan and build as much of this yourself as you can,
and any tasks that must be outsourced to feature teams are clearly formulated and communicated.

The outcome is that customers are now able to get what they need without requiring ongoing engineering involvement,
defensive or otherwise. This, in turn, frees up your dedicated defensive engineering resources to mount a better
defense elsewhere.

A variation on this: building features can be expensive and is low on this list of defensive-engineering priorities.
I've previously mentioned that defensive techniques are a skill set worth cultivating. It may be that an
individual or team accustomed to the frequent context-switching of full-time defensive engineering has trouble getting
into a feature-programming groove, especially with all the distractions from the higher categories on this list.
A project that would take a dedicated feature team one or two sprints to build and ship might end up taking a
defending team double the calendar time, or tenfold, or maybe even never quite reach completion. So sometimes one of
the most effective forms of defensive engineering is to have an experienced feature team take a short break to
build something defensive, protecting the defenders' freedom to do what they do best.

Summary: *If a whole new product feature is the most effective way to defend the defenders themselves, build it.*

## Yuck. I hate the idea of engineers spending time on that stuff. So do the engineers.
I can't say I disagree. But it's important to ask the question: how much of "that stuff" are engineers going to
be doing anyway, often at uncontrollable/unpredictable times, always at the expense of planned work and
delivery schedules, and seldom with a clear path toward improving the situation? I think it's unrealistic
to measure the cost of defensive engineering against some hypothetical ideal of 100% innovation. Instead, it's
more appropriate to say "Unplanned work is consuming 25% of engineering effort and causing us to miss 40% of 
our timing goals." If you could drop your miss rate to 10% by pre-allocating 10% of your engineers to focus
full-time on unplanned work, would it be worth it? Maybe the answer is yes, maybe no. I'm sure it's not easy
to measure the time spent on unplanned work and even harder to determine how much it's affecting delivery.

And yeah, regarding engineers not wanting this, I hear you.
I mentioned above that defensive engineering may not lead to many
"traditional" engineering accomplishments that stand out on an annual review or a résumé. Engineers may be
passionate about building things. If that's the case, let them. And protect them. On my defensive engineering
team, I had members that transferred to feature teams after six or twelve months, and I was happy for them.
But it was also very gratifying to hear back how their time playing defense had also made them a better
developer, able to write more resilient code or more clearly anticipate the kinds of structure that would
be easier to understand and exonerate by someone in the distant future trying to understand an obscure bug.

## Ready for concluding thoughts? What's next?
Sure, let me wrap this up. I mentioned in the beginning that this was just me, wanting to start a reflection
on how I've spent the last few years, and what considerations might be helpful to someone else trying to
decide how to handle a growning burden of threats to productivity.

The first thing I want to mention is that what I've written here is a mixture of description and
prescription. I didn't do everything equally well, either as an individual contributor or as a team lead.
Some of this is advice to myself 4-5 years ago.

I also mentioned that I want to add some supplementary articles going into greater depth on
topics I touched on here (I would say "briefly," to which you might say "ha!"). For example:
* Best practices for documenting and "containing" one-off/customer requests
* Efficient defensive engineering as a team when not everyone has production access
* Writing server logs to help and not hinder the future troubleshooter or damage assessor
* Measuring effectiveness of defensive engineering: OKRs, ongoing necessity, and scaling

I have thoughts ready to go on some of those bullet points, and others are -- like the article itself --
more aspirational. As I said before, I've spent a lot of time *doing* this stuff, and had fewer opportunities
for the kind of reflection on things that didn't feel as urgent. I wrote this up in a weekend, and honestly
have no idea whether the future holds anything but obscurity for it, but it feels very satisfying
to finally put some structure to the swirling thoughts. And if you've read this far and found it helpful or
at least interesting, I'm glad to have given you something to ponder.

Thanks for reading.

Tom Stroman, 2024-10-20

## Related resources
At the time of writing this conclusion, I've shared only my own thoughts.
That being said, while my observations and nomenclature may be "original"
in that I didn't consciously appropriate them from someone else (nor did I use any generative AI in this
article's composition), I very much doubt that I'm the first one ever to say...
probably *anything* that I've said here. 

I have therefore reserved this section for adding links (and perhaps accompanying discussion) to other articles, blogs,
README files, LinkedIn posts, you name it. If it seems like it would provide meaningful
corroboration, counterpoint/contradiction, challenge, perspective, supplementation... if, after encountering
something, I feel like I'd be doing readers or authors a disservice by not mentioning it here... on the list it goes.
