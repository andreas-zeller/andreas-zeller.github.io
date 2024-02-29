---
layout: post
title:  "The Devil's Guide to Incremental Research"
author: Andreas Zeller
tags: 
---

_This post originally [appeared on Twitter](https://twitter.com/andreaszeller/status/1382702351161655298?s=21) on April 15, 2021._

In the past years, I have noticed a number of "recipes" for scientific papers&nbsp;– patterns that maximize the number of publications despite limited significance. To raise awareness for these recipes, we have to name them. Enjoy!

You are the first to solve a problem. Great. But how will reviewers know if the problem is relevant? They will have to assess the technique and your results. On which grounds? In the end, your paper may be rejected simply because people don't know what to do with it.

Our suggestion: Don't take such risks. Stay with the mainstream, and make it easy for reviewers to see you are "better" than the competition. Here come a few simple recipes for "better" research that will all boost your publication numbers.

**THE RUBE GOLDBERG.** Reviewers never ask for the cost of coding and maintenance. So take some simple technique and attach some huge machinery – say, a machine learner and a data corpus. Invariably, this will improve results somewhat, and you can claim you are "better"!

**THE CHERRY SHUFFLE.** Your approach has a randomized component? Perfect! Run it again and again until it once outperforms the competition. Report these "better" results. Save the seed for later reproduction, and quietly drop the results of the earlier experiments.

**THE CODE OVERFIT.** Take an existing technique _T_ and a benchmark. Find out under which conditions _T_ does not work well. Add some "optimizations" that work well for the benchmark. Presto&nbsp;- you are "better"! In case a reviewer actually reads your code&nbsp;– just resubmit.

**THE AUTOTUNE.** Your approach has a dozen parameters? Great! Auto-tune them towards your benchmark until you are significantly "better" than the untuned competition. Report those parameters that are powers of 2. Bury others deep in the code and "lose" your git history.

**THE SURVIVOR.** Find some subjects where competing approaches already have been applied&nbsp;- say, some open source code where existing static checkers / fuzzers / verifiers find no more bugs. Your approach will find "more bugs on open source subjects" than the competition!

**THE IMPORT AND RELABEL.** Apply a technique from a neighboring field. Don't call it "Mutation Testing" or "Mining Software Repositories" but "discover" that "fault injection" or "version archives" bring benefits. Rename things to avoid reviewers from the original field.

**THE SELL AS NEW.** Or go the other way round and bring a standard technique from your community to another domain. There's 400 papers on statistical debugging, but you'll be the first one to apply it on drone code. It'll be just the same, but drone experts won't realize.

**THE MECHANICAL TURK.** Your community is obsessed with bugs and vulnerabilities, and your tool doesn't find any? Relax. Hire a hacker who finds some for you. Then adapt your tool such that it "finds" these as well. The better your hacker, the more fame for you!

**THE PROOF AS VALIDATION.** Use some formal method that so far has not been applied in your field. Be the first to apply three-valued logic to debug programs; throw in some proofs to intimidate readers. While others "evaluate", your technique is correct in the first place!

**THE FISHING EXPEDITION.** Empirical research also is a gift that keeps on giving. Use a hypothesis like "The more _X_ in a file, the more _Y_ in it, too." Whether _X_ and _Y_ are comments, loops, bugs, or emojis&nbsp;- anything will work as a "novel insight". Predict and get published!

**THE ACHILLES HEEL.** So you can fully verify the correctness of mobile apps – if only they come without loops, pointers or recursion? Good news: Such apps actually do exist, so use them for "evaluation"! Your achievements go into the title, limitations into a footnote.

Things to avoid: User studies. Real code. Talking to practitioners. All you'll learn is that your assumptions were all wrong, your approach won't work, and the problem is much hairier than expected. Don't let reality come between you and your publication.

Be efficient. Do not register your study. Do not keep logs of experiments or decisions. Do not keep a history. Do not test your code. Do not validate your results. Do not share anything. None of this is misconduct! Go for the next paper instead. Go, go, go!

Know Hanlon's Razor? Never attribute to malice that which can be adequately explained by neglect. So you're not cheating, you "could have applied more rigor" – and, anyway, the results you obtained all were real, right? Promise to do better next time, and then don't.

In summary: Don't ask. Don't answer. And don't take risks. Just get your numbers right and get these papers out. Your school, your mentor, your funding agency all count, and they count on you. So be the one who counts. Just count on us :-)


### Acknowledgments

Acknowledgments (and extra reads!):

* [Marcel Böhme](https://mboehme.github.io) inspired this guide with a [tweet thread](https://twitter.com/mboehme_/status/1379590234808086529?s=21).
* [Margatet-Anne Storey](https://www.margaretstorey.com) brought me to the idea of [research antipatterns](https://github.com/margaretstorey/mixed-methods/blob/main/mixed-methods.md#antipatterns).

Also thanks to [my group at CISPA](https://andreas-zeller.info/Group.html) for reviews and inspiration!

_See the [Twitter thread](https://twitter.com/andreaszeller/status/1382702351161655298?s=21) for comments and reactions._



