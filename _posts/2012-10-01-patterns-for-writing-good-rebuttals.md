---
layout: post
title:  "Patterns for writing good rebuttals"
author: Andreas Zeller
tags: 
redirect_from: 
  - "/onresearch/rebuttal-patterns.php3.html"
---

I compiled the following patterns for rebuttals (also known as author clarifications) for major software engineering conferences (ICSE, ESEC, FSE, ASE, ISSTA), having seen a number of rebuttals as PC chair of ESEC/FSE 2011 and having written a number of rebuttals for top conferences.  These patterns may or may not be applicable in your context; use at your own risk.

## Understand the decision process.

Most SE conferences apply a process called [Identify the Champion](http://scg.unibe.ch/download/champion/).  Carefully read these process patterns, understanding the roles of the reviewers and the PC chair, and where your rebuttal can make a difference.
	
## Identify the undecided.

These are reviewers who may be swayed by your arguments.  You can identify them (a) by generally liking your paper, but not the details, (b) because they provide their scores, or (c) because they explicitly state that they may be swayed.  Focus your arguments on these reviewers.  (And if you ever become a PC chair: include scores in the reviews, such that your authors know whom to focus upon.)

## Identify the champion.

The champion likes your paper anyway, so don't bother too much with her review.  If there's no potential champion, chances of getting your paper accepted are slim.

## Arm the champion.

In the final discussion, your champion will need arguments against the detractors, especially strong detractors.  Refute every single issue raised by the detractors to give your champion extra arguments for acceptance.  Lower the confidence in the detractors' reviews by pointing out mistakes.

## Identify the detractors.
A strong detractor can only be countered by a strong champion.  Rather than trying to dissuade a strong detractor, your aim should be on arming the champion (see above).

## Answer the questions.
Some conferences want you to only answer the specific questions the reviewers have asked, and/or instruct their PC members to only focus on these answers.  Try to relate every argument of yours to a specific question.
	
## Write for the PC chair.

If your reviewers have done a bad job, say so in the beginning, and the PC chair may assign you another reviewer.  Stick to facts (review is just one paragraph, reviewer claims "no Foo" when Section 3 is named "All about Foo", etc.) that the PC chair can check in less than a minute.  If a reviewer completely misunderstood the paper, feel free to report this, but keep in mind it is your duty to ensure even a casual reader gets the message. If _all_ reviewers misunderstood your paper, the problem is not the reviewers.

## Write for the committee.

When your paper is discussed during the PC meeting, reviewers will glance through the reviews, and also read your rebuttal.  If there's one thing you want the committee to know, say so in the very beginning (because that's all most reviewers will read).  This assumes that your paper will be discussed, so focus on getting it discussed first.

	
## Convince.

Convince the reviewers that you'll be able to improve the paper. If the reviewer asks: "Do you have a formal definition of Foo?", don't say "Yes".  But don't say "Thanks! We'll add this." either. Say "A Foo is a Bar within a Qux range; we'll add a detailed definition."  You don't need to provide the full change; just sketch the change you will make.


## Choose comments wisely.

Focus on _major_ concerns - the ones where the reviewer assumes you may not be able to improve the paper.  You do _not_ need to convince the reviewer that you're able to fix typos, straight-forward presentation issues, language issues, or anything else that can be fixed by simple proofreading. This is taken for granted.


## Organize your rebuttal.

Make it easy for reviewers to find their questions (and your arguments).  Refer to reviewers by R1, R2, ...; questions by R1Q1, R1Q2, ...  Use bullet points and short sentences to allow for quick scanning.  Start with the most important and most common concerns, going down towards lesser issues.

## No tricks.

If the limit is 500 words, `do_not_trick_the_process by_replacing_spaces_with_underscores` or likewise; all that will happen is that the PC chair will delete your rebuttal.  If it's 2500 characters, do not assume that reviewers KAAYAYA and AYP because they FSITPOG (know all about you and your acronyms and accept your paper because they feel stupid in the presence of genius).

## Thank the reviewers.

A rebuttal is not a place to vent off your fumes, even though your work is so great and the reviewers are all so stupid.  Reviewing is hard work and even the least significant review contains grains of truth which will be helpful for your future work.

## Don't expect too much.

Your rebuttal will not save your paper.  Your rebuttal will play a role only if your paper is on the edge, or if reviewers made very obvious mistakes.  If the reviewers update their reviews to reply to your arguments, that's already a lot.  But regardless of the outcome, your rebuttal will help to improve your paper and eventually get it accepted - if not now, there's always another deadline on the horizon.


## Change Log

* 2012-01-10: initial version; minor editorial corrections.
* 2012-01-10: added "Write for the committee", "Choose comments wisely", and "Convince", suggested by Thomas Zimmermann.

