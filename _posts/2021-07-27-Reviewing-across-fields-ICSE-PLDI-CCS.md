---
layout: post
title:  "How do different fields review papers? Experiences from ICSE, PLDI, and CCS"
author: Andreas Zeller
tags: 
---

**What's it like to review for ICSE, PLDI, or CCS? And how do the papers (and review culture) compare?**

In 2021, I served as reviewer on the PCs of top-tier conferences in three distinct fields: software engineering, programming languages, and security. I was thankful for the opportunity! First, there's not too many researchers who get the opportunity to serve in different fields, and I was curious. Second, I would be acting as co-PC chair for ICSE next year, and I found plenty of insights and inspiration. In this post, I share and compare my experiences with each of the conferences, from invitation to decision.

_Note: All observations reported are based on a small fraction of papers, reviews, and subfields of the respective communities, and do not necessarily generalize. If you'd like to find out more, make it your research topic!_


## Invitation

Your job as a reviewer starts with the invitation to the program committee, which states the most important facts about the conference: when and where it is held, and what you should do. This is already where the three conferences differ, as summarized by some metrics:

| Conference        | ICSE | PLDI | CCS |
| ----------------- | ----:| ----:| ---:|
| Invitation length (words) |  948 |   588|  340|
| Important dates   |   11 |     8|    5|
| Detailed process? |    y |     y|    n|    
| Detailed duties?  |    y |     y|    n|

The first thing that strikes out is the length of the ICSE invitation - 948 words, 60% longer than the PLDI one, and almost _three times as long_ as the CCS one. That is because it lists 11 important dates (more on that soon), details the roles of reviewers (reviewer/discussion leader/discussant), and points out that if you fail in any task (not declaring conflicts, not entering bids, not submitting the reviews on time, etc.), you will likely be removed (more on that later, too). All this is typical: I have served many, many times for ICSE and other SE conferences.

The PLDI invitation is shorter, yet still to the point. There's only eight important dates and only one role (reviewer). It encourages "positive and constructive reviews with sufficient detail to help the authors revise their papers and make them better." and explicitly points out the [ACM Code of Ethics and Professional Conduct](https://ethics.acm.org/code-of-ethics/). For me, this is the second time I serve on the PLDI PC - my research is in program analysis and testing, which is covered by PL and SE.

The CCS invitation is short, listing only five dates for each of the two rounds of reviewing. The reviewing process is not detailed, and there is no listing of duties, only expectations - PC members should "write their own reviews, actively argue the contribution of papers, and provide constructive feedback to authors." This is the first time I serve on a CCS PC.

Once you have agreed to serve as a reviewer, ICSE program chairs will treat you with one or more meetings (all virtual in 2020), detailing their plan for the conference and the review process and allowing for questions from the PC; this also creates some community feeling within the PC. No such thing for PLDI or CCS.


## Bidding

Once all papers are in, you _bid_ for papers you want to review. All three conferences use the HotCRP submission system (SE folks read it  "Hot-see-arr-pee", for PL folks, it's "Hot Crap"), where you can enter a number between -20 and 20 for each submission, depending on whether you'd like to review or not.

For ICSE with its 600+ submissions, this can be pretty tedious; fortunately, authors already have tagged their papers with multiple areas, and you as a reviewer already have indicated your expertise on these. So, all fields are pre-filled with values; the higher, the better the match between the author-supplied areas and your expertise. This allows you to quickly filter.

With PLDI 2021, you were asked to supply a number of your own papers first. Then, the [Toronto paper matching system](https://www.cs.toronto.edu/~zemel/documents/tpms.pdf) then determines, for each submission, how semantically close it is to your work and gives a high score for good matches. So I got a number of papers pre-assigned that were all on testing and debugging. However, you can still control which papers to bid on, which allowed me to downvote some papers on debugging quantum programs - I may be an expert in debugging, but not so much in quantum programs.

With CCS, you would simply go through the submissions and enter preferences; but then, this was not very hard, as authors select individual _tracks_ in the first place, and I would only see papers in the software security track. I mostly bid on papers on fuzzing and on program analysis.

Eventually, for all conferences, I got papers that fit my expertise well - software testing and fuzzing; grammars, parsers, and automata; reduction; program analysis. So let the reviewing begin!


## The Papers

### ICSE: Evaluation, please

Most SE papers I review present some novel approach to testing and analysis, followed by an implementation and some empirical evaluation. Usefulness is the key metric in evaluating SE papers, so the evaluation is crucial; authors take quite some time to discuss their approach from several angles. But authors are also expected to assess the limitations of their approach and their evaluation, and so you find dedicated sections on these, too. Lots of papers provide data and code packages for replication; at ICSE 2022, [sharing your data even becomes the default](https://conf.researchr.org/track/icse-2022/icse-2022-papers).


### PLDI: Semantics and more

PL people love semantics, and therefore it is no surprise that PLDI submissions go deep and dense; their 12 pages typically come with long appendices further detailing type equations, semantics, or empirical results. To check the proofs, you have to understand in detail how the technique works, and so you read and dig through it. There typically is an implementation (the "I" in "PLDI"), so you can assess that, too. I can review two ICSE or CCS papers on a good day, but never more than one PLDI paper.


### CCS: My tool finds more bugs

But now to CCS. Typical Computer Science papers do a fair job in relaying the authors' excitement about their own work; this helps motivating the reader (or reviewer) to actually read it. This excitement can go over the top, but is _nothing_ compared to the bragging culture in "my" CCS submissions. 

In security, vulnerabilities are key. If you find a vulnerability, this gives you bragging rights, in particular if it is widespread and exploitable. But if your work is about a _system_ to find vulnerabilities, then you as a computing professional "should be transparent and provide full disclosure of all pertinent system capabilities, limitations, and potential problems to the appropriate parties.", as stated in §1.3 of the [ACM Code of Ethics](https://ethics.acm.org/code-of-ethics/).

The papers I reviewed for CCS were all about finding bugs, and each and every paper bragged that they found more bugs than the state of the art. But none of my submissions came with even a whiff of discussion on whether the results would be generalizable, or why the algorithms would be correct. Not a single one would discuss statistical significance or effect size. Data sets, replication packages, threats to validity or even discussions of limitations were all absent.

> **"At any SE or PL conference, these CCS papers would have sunk in an instant"**

For more than half of my papers, the argument was that the new approach "can" find "up to N%" more vulnerabilities than the state of the art, and therefore is "better", without any exploration of why these "results" could be misleading.
At any SE or PL conference, these papers could have sunk in an instant: First, from a methodological standpoint, "bugs found" is a very unreliable metric to compare approaches - which on top [can be constructed far too easily](https://andreas-zeller.info/2021/04/15/the-devils-guide-to-incremental-research.html). Second, SE and PL reviewers would invariably question the evaluation design - How was the benchmark chosen? What is the average over multiple runs? How was the ground truth collected? Did the evaluation inform the development of the approach? If so, how is this a fair comparison? and more. No, none of "my" papers addressed any of these questions.

Having said that, as a reviewer, I _can_ make up my own mind if an approach works. And if the approach is well described and makes a reasonable argument on why it should work, I can live with a weak evaluation. This is what saved a number of papers, and my overall score for CCS papers turned out to be higher than average.

(On a side note: One paper reinvented [model-based testing](https://en.wikipedia.org/wiki/Model-based_testing) (and came _so_ close to invent model checking, too); other papers reinvented [fuzzing thread schedules](https://www.cs.purdue.edu/homes/xyzhang/spring07/Papers/test-thread.pdf) or [process mining](https://en.wikipedia.org/wiki/Process_mining). Please, folks: when you search for related work, also look beyond your community.)



## The Review Process

So, as a reviewer, you read all the papers, submit all your reviews, and you're done? Not at all. This is when the actual _review process_ sets in, turning a bunch of independent reviews into a joint decision.

### ICSE: The power of process

ICSE is the flagship conference of the Software Engineering community. As a good Software Engineer, you believe in the power of process; and you know that despite all best efforts, errors may crawl in at any time. The ICSE reviewing process is modeled with these principles in mind. 

Reviewing for ICSE means to adhere to a _ton_ of deadlines – there's a deadline each for 50% and 100% of your reviews; there's a deadline for completing 50%, 75%, 100% of discussions; there's a deadline for entering the meta-review; and there's a deadline for approving the meta-review. You will be constantly reminded of these deadlines, especially it looks like you may miss them.

The important thing is that if you miss _any_ of these deadlines, _you will be terminated_ – as a reviewer not only for ICSE, but also for other SE conferences. In fact, when composing a program committee, the question of how reliable you are as a reviewer is almost as important as your expertise. You simply _are not late, ever_ (unless you have a good reason such as sickness). All this is well understood in the community, and reminders therefore come with some distinctive authoritative tone.

> **"As a reviewer for SE and PL conferences, you are not late. Ever."**

Also, reviewing _forms_ for ICSE are more detailed than for other conferences: You are asked to provide specific questions for authors to answer in their rebuttal; and you have a form field where you enter how the authors' answers influenced your review. If you miss to fill these out, you get – guess what? - another reminder.

All this results in a slow, but pretty organized way of doing reviews, which does its best to prevent low-quality reviews. So again, as an author, you can expect detailed and constructive feedback, possibly the best from any SE conference. Still, there are some [formulaic ways to reject papers](https://autoreject.org) – "we need more evidence" being the most common, especially for empirical work.


### PLDI: Trust in people

The PLDI review process is similar to the ICSE review process - reviews come in, discussions start, decisions are made. But the process is much more lightweight - there's no "quality gates", no formal acknowledgment that you have read and reacted to the rebuttal. No, PLDI simply _trusts_ its reviewers to do the right thing™. and they actually do it.

Everything went smoothly: We got a few mails from the program chair telling us to do X, and my co-reviewers did X. Reviewers were very eager to discuss, needing no special prompts; discussions also quickly aligned. Like a good football team, everybody seemed to always know what was to be done next. All in all, it was a huge amount of work reviewing these papers, but also a pleasure to work and discuss with real experts. If you get an invitation to serve for PLDI, I would highly recommend it.


### CCS: Professional negligence

My "reviewing invariant" for CCS was: people were late. This already was set in the tone of the reminders – while PLDI and SE reminders remind you to do the right thing (or else), CCS reminders came across as _pleas_ – would you please, oh _please_ be on time? And these pleas would be _justified_. On the first deadline, only one third of papers had the two reviews required. On 
the day of the review deadline, when reviews were to be sent out to authors, only about half of the reviews were in already. Some authors received their third review 3-4 days after the rebuttal period already had started.

> **"My 'reviewing invariant' for CCS was: people were late"**

Having four flagship conferences in security, each with two "rolling" deadlines, means that some researchers will be overcommitted to a never-ending reviewing load, which is bad. But the message all this sends out is that reviewers do not care - not about the papers, not about the conference, not about your co-reviewers, not about the program chairs. If my co-reviewers do not care, why should I? And if other reviewers do not care about my paper, why should I care about theirs the next time I review something?

(Now here's an anecdote from ESEC/FSE 2011, where I was PC chair. One reviewer _was_ late - the deadline was over, and not a single review was in. When I called him on the phone and told him that we would open up for rebuttals the next day, he was shocked - he had thought he still had a week or so to finish his reviews. Within 24 hours, he (and his students?) produced fifteen impeccable reviews for his entire batch. As I said: You are not late. Ever.)


## Reviews

Once you submit your review, you can see the reviews of your co-reviewers, too, and then compare their assessment against yours.

Again, as a PL person, you take semantics very seriously, and that is how papers are reviewed - very thoroughly, dissected to the last word, checking every type equation. Regardless of how well you did your research, reading a review from PLDI will feel like an hour-long session at the dentist (without anesthetics), as reviewers precisely dig into every weakness they find - and as there's up to five reviewers, there's a lot the reviewers will find. Yet, the overall attitude is constructive and helpful, and despite the pain, you get the feeling that reviewers actually want to help you achieve the best possible result. 

> **"PL reviewers are a bunch of nerds who happily jump on every new bit of tech they find; SE reviewers are a panel of bureaucrats searching for any mistake you may have made"**

ICSE reviewers also generally do a good job at reviewing, but the attitude is slightly different: If PL reviewers are a bunch of nerds who happily jump on every new bit of tech they find, then SE reviewers are a panel of bureaucrats searching for any mistake you may have made - and then using that very mistake to sink your paper. But as an author, if you show something useful and get through the formalisms, ticking all the boxes, or simply "doing nothing wrong" otherwise - your paper will likely get in. ICSE is a conference of serious papers, all valuable, sometimes even exciting.

But if I were to describe the attitude of my CCS co-reviewers, the best word would be "worn out". Reviewers were able to precisely identify strengths and weaknesses, but also got quickly tired if something was badly presented and/or hard to comprehend. I could not always follow why some set of arguments brought forward would result in the specific stance of the reviewer. That might be because I am used to some [clearly defined criteria](https://conf.researchr.org/getImage/icse-2022/orig/ICSE+2022+Review+Process+and+Guidelines-2.pdf) that I can use to assess a paper; if finding more bugs is the sole criterion, then the outcome is harder to predict.


## Discussions and Decisions

When all reviews are in, reviewers must find a _consensus_ on whether the paper should be accepted or not. This takes place in a discussion period of a few weeks, also involving the authors' response.

At PL and SE conferences, the general scheme is that [at least one reviewer must champion the paper](http://scg.unibe.ch/download/champion/) and thus argue for acceptance. Arguing about soundness, semantics, and significance, reviewers can fight over papers in long discussions. These discussions are often as much worth a read as the papers themselves – the record, I believe, was 45 discussion items. Still, both at PLDI and ICSE, we always converged towards a consensus, and I learned a lot along that way.

One notable difference between PLDI and ICSE was that I found that at PLDI,  reviewers were always happy to _adjust their stance in light of new information_ - whether this information came from the authors' rebuttal or from co-reviewers. On one of my PLDI papers, I started as the lone positive reviewer against three negatives. The paper eventually went into acceptance after a ton of discussions and clarifications. At ICSE, I frequently found that reviewers feel that changing their stance is a sign of weakness (which is not true).

At CCS, the discussions of "my" papers were rather short - again, my impression was that too few reviewers really cared about the outcome. When I would raise points about methodology (statistical significance? validity? yada yada yada), authors would universally ignore these concerns in their rebuttals; and co-reviewers would not pick them up either. But neither would other issues be discussed at length. At some point, it felt as if every reviewer would happily agree with _any_ majority decision as long as the whole thing would finally be over.

But then, at CCS, being late extended to discussions, too – reviewers would be mum for weeks, only to emerge with a new question for authors after the discussion already had come to a conclusion. (This year, you would have two weeks in which reviewers could ask more questions to authors, to which authors promptly responded.) As it came to closing discussions, people were late, too; and some reviewers reversed their stance only hours before decisions were to be sent out, asking to still change the overall outcome.

At the time of this writing, the CCS decisions were announced a week ago, but some authors are still waiting for to learn on why their paper was rejected.  How long does it take to write a decision summary? Ten minutes? Again, what example does this give to young researchers?

## After Acceptance

One neat aspect of PLDI is _universal conditional acceptance_: Even if your paper is accepted, it will always be a conditional accept, and you will work with the reviewers to get it into shape such that it can be proudly published. (And if your paper is rejected, at least you will get plenty of helpful feedback from experts.) Again, this indicates how the entire community builds a great conference.

CCS has shepherding, but mostly to address presentation issues. For complex cases, there's major revisions, meaning that a revised version will be checked by the same reviewers after a period of time. (I wasn't told details, but I expect these submissions to pop up on my desk again some day - hopefully not at a time when I'll be busy sorting the 600+ submissions for ICSE 2022.)

ICSE has none of this - once your paper is accepted, you are fully trusted to publish a great final version of your work. All reviewers are dismissed and can happily enjoy the holiday season (or prepare their own papers?). Their only remaining formal task will be at the conference itself, where they will stand up and enjoy the applause from the audience.


## Final Thoughts

Serving in a number of different communities is enlightening - not only as it comes to the differences in the review process, but also in review culture, research methodology, and core values of the respective communities. I would strongly recommend for any researcher to occasionally review outside of their comfort zone - and conversely, _have program committees explicitly include reviewers from outside of the community_. Investigating the different scientific cultures in subfields of computer science might make a great research topic in itself.

> **"I would strongly recommend for any researcher to occasionally review outside of their comfort zone."**

My less then stellar experience in reviewing for CCS leaves me worried about research culture in the security community. For me, science is about the accumulation and distillation of knowledge, not about who is better than whom. If at all, "better" research comes through significance, not through a metric. Yet, as long as we keep on bragging about metrics, we will have more and more incremental papers – and exhausted reviewers.

Bragging and overclaiming is a problem I see at all conferences. Since few years, the quality I now appreciate most in papers is _honesty_: Here's what we did, here's what it does, here's when we know it works, here's what will not work. Being honest, being dependable, showing respect are values we must cherish and [where we must lead by example](https://ethics.acm.org/code-of-ethics/). And anyone of us can start right now.
