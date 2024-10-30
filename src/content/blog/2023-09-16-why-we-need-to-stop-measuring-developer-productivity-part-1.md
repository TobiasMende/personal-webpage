+++
title = "Why We Need to Stop Measuring (Developer) Productivity — Part 1"
slug = "why-we-need-to-stop-measuring-developer-productivity-part-1"
image = "/img/import/2023-09-16-why-we-need-to-stop-measuring-developer-productivity-part-1.jpg"
date = 2023-09-16T04:00:00
publishDate = 2023-09-16T04:00:00
lastmod = 2023-09-11T12:02:10
description = "Productivity metrics, once useful for traditional businesses, are now outdated, especially for developers. Relying on these numbers can harm businesses. Metrics can be misleading, causing negative practices. We need to prioritize trust and communication over mere numbers. This article urges a rethinking of our approach to productivity."
tags = ["Culture","Developer-Productivity","Leadership","Metrics","Engineering-Excellence"]
+++
# Why We Need to Stop Measuring (Developer) Productivity — Part 1

Leaders are obsessed with productivity metrics. This is at least true for leaders who learned to lead in the last century. The ones that follow a command-and-control or carrots-and-sticks leadership approach. They need to measure each department individually to make the right decisions top-down.

While this approach might have worked for manufacturing companies in the past, it is very ill-suited for anything beyond that. And yet, most company leaders still cling to that outdated operating model and try to fit reality into its limitations. — With frustrating implications for employees, customers, the business, and everyone involved.

It is time to rethink leadership and shift toward a leadership style based on trust, communication, and collaboration rather than the false comfort of productivity metrics.

It needs to be acknowledged that there is high interest from CTOs and other leaders to find a way to measure engineering productivity because other departments can be measured accurately. And they can be measured in a way that supports company goals. So the saying goes. But is this really true?

This article will explain why measuring productivity is difficult and dangerous, no matter the department. We will see how the common approaches to measuring the productivity of departments such as sales and HR might cause more harm than good for the organization.

In part two, we will go into more detail on developer productivity in particular.

## **The lie about sales productivity.**

Let’s start with something widely accepted among most company leaders: We can measure sales productivity by the total sales revenue divided by time/money for that sale. And higher is better for the company.

Sales representatives often are ranked by the number and size of deals they close. This single metric makes it easy to know the top and bottom performers.

But does this make sense for the business?

For everything that you measure, Goodhart’s Law applies:

> _When a measure becomes a target, it ceases to be a good measure._

This is true for sales metrics, too. They are easy to game, and I have seen it many times:

1. To close a deal, non-existing or half-finished features are promised. (or other lies are told)
2. The prospect signs.
3. The lie creates pressure on other departments that are supposed to deliver the feature to turn the lie into truth.
4. The pressure creates frustration, reduced quality, burnout, and reduced performance. Deadlines are missed.
5. The client is unhappy and quits.

How is the sales productivity metric in this example?

It is great. But the damage to the company and other departments is also great. This damage is caused by company leaders who do not understand human psychology or were tricked into believing we need to measure to control.

The problem is worsened by adding other incentives for closed deals (besides keeping the job or climbing the ladder). Unfortunately, most sales departments work with some bonus system. And [**bonuses worsen the issue**](/blog/bonuses-are-bad/) and increase the gap between the company’s mission and individual goals.

We only really know if a good sale was made if we still have the client years later and they are happy. This is hard to measure at the moment when the sale is made.

A wrong sale creates frustration and pressure among customers, engineers, customer success managers, and other functions. Moreover, investors do not like high customer churn or low engagement with the product.

Thus, **high sales productivity can damage the company**.

In conclusion, it might be easy to measure sales productivity, but it isn’t worthwhile or beneficial for the company from a systemic viewpoint.

## **The same is true for other departments.**

Sales is no exception. Measuring productivity in other departments creates the same kind of conflict. Most productivity metrics suffer from a short-term bias, measuring some proxy for long-term productivity.

* Marketing can lure prospects into buying via unreasonable discounts or false promises.
* HR can hire unsuitable candidates by hiding the truth about the culture to fill a quota.
* Manufacturing can deliver more pieces by sacrificing the quality.
* …

## **Measuring productivity is dangerous.**

To summarize, measuring the productivity of a department as a leader is dangerous. People want to prove their worth to the leadership. And they can do it via the metrics that are observed by leadership.

Those metrics can be gamed and often do not support long-term business success. They support local optimization at the cost of ignoring the bigger picture.

For leaders who naturally do not have the full picture, finding a combination of metrics that accurately balances the system is impossible. Thus, when leaders start to measure productivity, they put long-term business success at risk.

As we have seen before, measuring sales productivity and judging people by these metrics has the power to create problems in entirely different departments. It can fire back in terms of lower quality, technical debt, frustration among customer success and engineering, people leaving the company, or customers churning.

**CEOs, is this what you want?** Probably not.

So what can we do instead?

## **How to use productivity metrics?**

Whatever productivity metrics you use and in whatever department or area, you should not use them to judge or rate the department based on them.

That said, those metrics can be valuable indicators for the department itself. Metrics can be powerful in measuring _ourselves_ and seeing how and if we are improving. **Metrics cannot be used to measure others**whose careers and lives depend on them. People need to learn to treat those metrics differently.

A decrease in productivity (in any given and imperfect metric for measuring productivity) should not cause people to work harder, push more, and force that metric up again. Instead, it should trigger people to reflect on why that metric has decreased.

We must be aware that a change in a productivity metric without context is neither good nor bad. Maybe the world has changed, and we are measuring the wrong thing. It might be something else became more important that is not reflected in this metric.

**The reflex of pushing harder to achieve previous levels of _productivity_ needs to be interrupted and replaced by a reflex to reflect.**

Furthermore, let your experts decide what they want to measure and what they wish to do with these measures. Trust your people. Give them the freedom to figure out how to best do their job. Your responsibility as a leader is to help them understand the company’s vision, mission, and values. People can figure out the rest or ask for help if they need it.

## **A word on McKinsey and others who have “cracked it”.**

Probably everybody has realized the disagreement that the McKinsey article “[**Yes, you can measure developer productivity**](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/yes-you-can-measure-software-developer-productivity)” has caused among software engineering experts such as [**Kent Beck, Gergely Orosz**](https://tidyfirst.substack.com/p/measuring-developer-productivity), and many others. LinkedIn is full of people who agree that McKinsey is wrong.

On the other hand, many people and companies claim they have found a way to measure developer productivity. McKinsey is one of the more _popular_ ones. Notably, all those who claim they could measure developer productivity use extremely diverse approaches. Only in the last month I have spoken to several researchers and founders who claimed to have a good answer to the question “How to measure developer productivity?”.

They usually throw some fancy math (or AI) on the code repository and retrieve an answer from the code base. And they get an answer. Typically, it is an answer to a question nobody asked and which is completely irrelevant regarding real developer productivity.

Anyways. McKinsey is different. They have invented a more sophisticated framework combining classical DORA metrics with other qualitative and quantitative metrics, roughly following the [**SPACE framework**](https://queue.acm.org/detail.cfm?id=3454124) and some other McKinsey-only metrics like _contribution analysis_, _talent capability score_, and _inner/outer loop time spent_. At least in inventing their framework, they act like most software engineers: When you can’t solve a problem with a simple solution, add more complexity.

The McKinsey framework is more complex. But can it answer the question of how productive an engineering department is? Short answer: No, it cannot.

The productivity of any system can only be measured when we know all the inputs and outputs of that system and can quantify those. As we will see in part two, this isn’t the case for developer productivity, and frameworks such as the McKinsey ones do not have an answer to this dilemma.

## **Until next week!**

This was part one of my article on why we need to stop measuring (developer) productivity. Part two will be published here and on [**my substack**](https://devexnuggets.substack.com/) next Friday.

In part two, we will dive into developer productivity and why it is futile to measure it. Furthermore, we will discuss what to do instead.

Stay tuned, and let me know your thoughts so far! 💬