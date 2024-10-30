+++
title = "Why We Need to Stop Measuring (Developer) Productivity — Part 2"
slug = "why-we-need-to-stop-measuring-developer-productivity-part-2"
image = "/img/import/2023-09-23-why-we-need-to-stop-measuring-developer-productivity-part-2.jpg"
date = 2023-09-23T04:00:00
publishDate = 2023-09-23T04:00:00
lastmod = 2024-01-08T06:32:24
description = "Measuring developer productivity is a flawed endeavor; it often replaces uncertain realities with misleading certainties. While metrics can offer insights, they cannot directly quantify productivity. Instead of seeking elusive measures, focus on understanding and eliminating barriers to engineers' best work. After all, nurturing an environment for outstanding work is a more valid approach to enhancing productivity."
tags = ["Culture","Developer-Productivity","Engineering-Leadership","Leadership","Metrics","Engineering-Excellence"]
+++
# Why We Need to Stop Measuring (Developer) Productivity — Part 2

This is part two of my article on measuring developer productivity. In [part one](https://devexnuggets.substack.com/p/why-we-need-to-stop-measuring-developer), we discussed the dangers of measuring productivity in general and why the need for productivity metrics for management and leadership is based on flawed assumptions.

While management based on productivity metrics is pointless and potentially harmful, there is still some value in metrics commonly labeled “developer productivity metrics”. That is if teams measure and use those metrics, not management.

## You cannot measure developer productivity. Nor should you.

As we have seen, measuring productivity might be wrong, even in areas where it seems easy. What is usually measured is the short-term productivity ((sales made in a month x average deal size) / # of sales representatives)

This metric does not tell us how long the client will stay with the company and if that annual recurring revenue (ARR) will be recurring next year or in five years.

What does that mean for software engineering? [Martin Fowler wrote about this](https://martinfowler.com/bliki/CannotMeasureProductivity.html) over 20 (!) years ago, and his article is still valid today:

> Productivity, of course, is something you determine by looking at the input of an activity and its output. So to measure software productivity you have to measure the output of software development – the reason we can’t measure productivity is because we can’t measure output.

The output in terms of business value is hard to measure. We might feel tempted to estimate that, but it replaces uncertainty with wrong certainty, which is worse. To further complicate it, there usually is a delay between the delivery of a feature and the business value it creates. We do not know how often a product is sold or how often the feature will lead to new business opportunities when we deliver it. We might also not know how much maintaining that feature or product will cost us in the future.

Thus, we cannot measure the real thing, engineering productivity, as the business wants to measure it. We can measure all kinds of proxies and use simplified models of reality for _enhanced guessing_. This might give us the illusion of knowing. 

**But do we really know?**

### Example: DORA Metrics

Take the [DORA Metrics](https://cloud.google.com/blog/products/devops-sre/using-the-four-keys-to-measure-your-devops-performance) as an example. They are (relatively) easy to measure and can give teams an idea of how well they are doing regarding deployment frequency, change failure rate, lead time for changes, or mean time to recover. Those are interesting factors to know (for the team). The team might decide they are unhappy with their change failure rate and derive actions to improve it (i.e., better automated tests).

But what do those metrics tell us about productivity? Nothing.

Indeed, a short lead time for changes and a high deployment frequency make delivering changes quickly to customers easier. This is _one precondition_ for getting customer feedback and iterating on the solution faster. This _increases the likelihood_ that we build something customers really need (and thus are willing to pay money for). Thus, **DORA metrics tell us very little about productivity. At best, they tell us about the likelihood of the ability to work productively in engineering.**

Therefore, DORA metrics can be insightful for the team to consider if they want to improve their software delivery game. **DORA metrics are pointless to measure by leaders under the mantle of understanding productivity.**

### More metrics do not improve the situation

Okay, so DORA metrics alone are not enough. So, let’s add more metrics. (Un)fortunately, there is no scarcity of metrics that we could measure in software engineering:

* Number of PRs per week
* Lines of code per hour
* Symbols changed per hour
* Incidents per month
* Time spent on coding vs. time spent on other activities
* …

The list is endless. And every day, somebody comes up with that new magic formula that answers all our questions on developer productivity or even happiness. Eventually, those people step back and say: “Well, okay, it is not the only metric you need, but it is a great addition.” — Leaving everyone with yet another metric to measure something that is not worth measuring.

Do not get me wrong. Some of these metrics might yield interesting insights. They just cannot be linked directly with developer productivity. Thus, connecting whatever metric with the claim to measure developer productivity is (likely) wrong.

And even if we measure everything that we can measure. How do we aggregate all those measures to get a definite answer to our question on developer productivity? There is no definite answer to this question.

Therefore, we should not attempt to measure developer productivity. Claiming that we can measure developer productivity is misleading and likely moves us away from our actual goal.

Certain measures can be valuable if we suspect problems in a specific area. For example, when engineers complain that they spend too much time in meetings, it can be worthwhile to understand how much time they spend and what these meetings are for. We can then seek to reduce the time engineers spend in meetings they do not consider relevant. Or we can make the meetings more relevant to engineers.

Kent Beck shares some great ideas on [how to answer the question](https://tidyfirst.substack.com/i/136503529/how-do-you-answer-the-question) about developer productivity. I can 100% sign those. He starts with the following warning:

> Be clear about why you are asking & what your power relationship is with the person or people being measured. When the person with power is measuring the person without, you’re going to get distortions.

## You cannot measure developer productivity. Here is what to do instead.

So, we cannot measure productivity. Bummer.

Have we all accepted that fact and stopped wasting time finding that new genius framework, metric, or product? Great! 

Now, let’s move on and focus on what drives productivity: People.

Think about it: **What reasons do your employees have not to do their best work?**

Whatever comes to your mind: Is this true? And if so, how can you remove that reason?

The reasons that come to your mind might be:

* They do not have enough experience. 👉 Coach them.
* They do not know where the company is supposed to go. 👉 Tell them.
* They do not understand the business. 👉 Educate them.
* They are bad people, here to sabotage my company. 👉 Fire them. Or rethink your image of people.
* We have created incentives that mislead them. 👉 Remove those.
* We have created a culture that demotivates and disengages people. 👉 Fix it.

After you have fixed the things that could prevent people from caring about business success, **ask them: What do you need to work even better? What holds you back? What frustrates you?**

People will tell you. And because business success is in their interest, they will tell you what they believe will contribute to its success. And they will be able to tell you why they believe that.

Asking employees shows you care about them, their experience, and their opinions. It opens the opportunity for surfacing and discussing potential issues that executives are unaware of. It helps everybody to understand what currently hinders individuals and teams and what cost might be attached to it.

Regarding engineering, you can (temporarily) [hire Technical Agile Coaches (like me)](https://unblocked.engineering/) to identify improvement opportunities or areas of frustration. Together, we can improve in those areas and make engineering more enjoyable, smoother, and productive. You can also run surveys and interviews among engineers to understand their feelings about their work, where they waste their time, and what they would change. My [Developer Experience Assessment](https://unblocked.engineering/developer-experience-assessment/) is an easy and cheap way to start this.

Ultimately, it boils down to shaping an environment where engineers have an outstanding experience and everything they need to do outstanding work. This is an environment where engineers can shape the environment collaboratively. My latest series on improving developer experience gives some pointers:

* [Improving Developer Experience: Starting with Psychological Safety, Team Stability, and Work-Life Balance](/blog/improving-developer-experience-starting-with-psychological-safety-team-stability-and-work-life-balance/)
* [ Improving Developer Experience, Level 2: Belonging, Collaboration, and Communication](/blog/improving-developer-experience-level-2-belonging-collaboration-and-communication/)
* [Improving Developer Experience, Level 3: The Triad of Clarity, Focus, and Flow](/blog/improving-developer-experience-level-3-the-triad-of-clarity-focus-and-flow/)
* [Improving Developer Experience, Level 4: Optimizing Feedback Loops: Tools, Tests, and Teamwork](/blog/improving-developer-experience-level-4-optimizing-feedback-loops-tools-tests-and-teamwork/)

## Conclusion

We cannot measure developer productivity. That is not a problem. 

We can still identify bottlenecks and use context-dependent metrics to understand which areas we can improve. Most importantly, we have hired smart people who often know exactly what holds them back the most.

It would be stupid to assume that fixing those things would not, eventually, lead to higher productivity.

**While we cannot measure developer productivity, we can identify improvements that will likely increase productivity in the future.**

## See you in 4 weeks! 👋

As this article comes out, I am already traveling to a beautiful small village in Tuscany, Italy 🇮🇹, for a two-week co-working retreat. I will use that time to recharge, reconnect, read, and relax. 😉 — I won’t publish newsletters or articles during this little late-summer break. 

You can expect the next article on the 20th of October on [my substack](https://devexnuggets.substack.com).

**In the meantime, let me know if you have any topics on your mind that you would like me to write about.** 💬

## Let’s work together! 🤝

If you think your team could become more productive or are seeking improvement opportunities, I am here to help. Together, we can identify bottlenecks and pain points for your engineering teams and work on the factors that actually matter. **Book a [free 30-minute discovery call](https://unblocked.engineering/#DiscoveryCall) to discuss how that can look in your context.**