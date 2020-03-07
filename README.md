---
---

# About Me

My students and I create tools and techniques that **help developers build better software** - by automatically testing, analyzing, and debugging its code and its development process.

Our approaches have had quite some impact in theory and practice.  My [Curriculum Vitae](assets/ZellerCV.pdf) lists the most important achievements.


## Current Projects

My most important project these days is [The Fuzzing Book](https://www.fuzzingbook.org/) - an interactive testbook on test generation ("fuzzing") techniques.  You can execute and edit the code right in your browser.

Other projects involve automated debugging and repair, analyzing mobile systems, analyzing user interfaces, and more - see our [latest publications](https://scholar.google.com/citations?user=-Qytr_YAAAAJ&hl=en&oi=ao) for details.  Our techniques typically apply and combine several techniques including dynamic analysis, static analysis, specification mining, test generation, natural language processing, machine learning, and formal languages.


## My Group

At CISPA and Saarland University, I work with [great students and Post-Docs from across the world](Group.md) on cutting-edge research.

CISPA and me are constantly looking out for great students.  Our positions are well paid and allow for highly productive research.  If you're interested in a PhD or Postdoc position, please apply.


## Theses

If you are a student of Saarland University and have fun with automated program analysis, testing, and debugging, you might want to do a thesis with us.  [Here are the details on how this works.](Theses.md)


## Latest News

<a class="twitter-timeline" data-lang="en" data-height="400" data-chrome="noheader nofooter noborders transparent" href="https://twitter.com/AndreasZeller">Tweets by AndreasZeller</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


## My Blog

My blog has a mixture of various topics from academia and software development, often with a humorous touch.  New blog posts are announced on Twitter.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
