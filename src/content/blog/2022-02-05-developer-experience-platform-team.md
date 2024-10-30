+++
title = "A platform team for next-level developer experience"
slug = "developer-experience-platform-team"
image = "/img/import/2022-02-05-developer-experience-platform-team.jpg"
date = 2022-02-05T12:49:00
publishDate = 2022-02-05T12:49:00
lastmod = 2024-01-08T06:36:24
description = "Developer experience is a crucial topic which affects all development teams of a company. Therefore, it can be beneficial to introduce a team that has as their only mission to improve developer experience and productivity as these improvements multiply the impact of the other teams."
tags = ["Software-Development","Team-Topologies","Developer-Productivity","Engineering-Excellence","Organizational-Design"]
+++
# A platform team for next-level developer experience

In this article, I am sharing my experience (and opinions) of how a platform team should be set up to provide great developer experience for other development teams.

## Background [](/blog/developer-experience-platform-team/#background)

In the second quarter of 2021, I started the “Platform and Developer Experience Unit” at BRYTER together with seven other colleagues. We set up this team because we realised, that certain important cross-team-topics just did not get the attention they needed.

Those topics ranged from CI pipelines over shared services to dependency updates.

First, we had quite a hard time to figure out, what to work on first and even more so, what not to work on. At some point, we were asked to own almost every component that provided an API that was used by more than one team. Needless to say that this is not a good strategy.

After almost one year and countless iterations and conversations, we have a pretty good understanding, how we can provide the most value for the company.

Furthermore, I also learned a lot from the [Team Topologies book](https://teamtopologies.com/book) by Matthew Skelton and Manuel Pais and their [Platform as a Product course](https://academy.teamtopologies.com/courses/platform-as-a-product), that helped me to reflect and iterate on the mission of our platform team.

Here are some of the most important learnings, that I made in the last year.

## Do not do the work for other teams [](/blog/developer-experience-platform-team/#do-not-do-the-work-for-other-teams)

This might sound surprising, but hear me out!

One of the most significant pitfalls is doing work for other teams. It is tempting to help other teams in a way, that the platform team is doing services for other teams. If a team might need a change on their CI pipeline, just do it for them, right? Wrong!

As a platform unit, one of the highest goals is, to get out of the way of other units. Instead of doing work for them, you should enable them to do their work themselves. And ideally, you make it as easy as possible. For CI pipelines, this could mean, instead of writing their pipeline descriptions for them, you provide base job configurations for common jobs so that they can just extend those without reinventing the wheel.

Whenever you find yourself in a situation, where you need to do work for other teams, think about ways to enable the teams to do the work. This might sound like you are off-loading work, but in reality you just help them to own their product end-to-end.

Doing work for others makes them dependent on you, and thus goes against the goal of enabling others.

## Do not contribute to features [](/blog/developer-experience-platform-team/#do-not-contribute-to-features)

As a platform team for developer experience, your highest goal is to provide a great, well, developer experience. This, means: increase developer productivity and help developers to enjoy their work more. Find their greatest pain-points and the areas where they waste most of their time and provides better solutions for those.

However, _platform_ sounds a lot like you would provide the basic services that are needed by other units. Mail services, blob storages, virus scanners, you name it. Suddenly, almost every basic part of some feature is a platform concern – A mistake, I made at the beginning.

This leads to the attempt to satisfy two very different customer groups. On the one hand, you have the developers. On the other hand, you have external customers and try to provide basic parts of features, that are then finished up by other teams.

The latter is extremely unrewarding and puts the platform team under constant pressure to implement features. This leaves little to no time for the actual mission: developer experience.

## Developers as your customers [](/blog/developer-experience-platform-team/#developers-as-your-customers)

In such a platform team, you are not targeting external customers, but your colleagues. You try to understand their needs, their pain points and what slows them down.

You will try to find solutions that bring the most value to many of them. Not only that, but you apply fundamental product management practices. You try to do the smallest thing possible to improve the developer experience, and work in small increments. Ship often. Listen to developer feedback.

Furthermore, you shall not force teams to use your _product_.

## Do not be the police [](/blog/developer-experience-platform-team/#do-not-be-the-police)

When building some cool tool or platform component that helps developers, it is tempting to force them to use it or to tell them, how they need to do their job. This is the wrong approach.

A product company cannot force their customers to use their product and the features they build. It is the same with a platform team and developers.

You can provide a reasonable set of linter rules and recommend a test framework. However, teams need to be free to choose something else instead. Only they know what helps them most. You can offer a solution, but teams can decide not to use it, knowing that you also might not support them, if they pick _another provider_.

Furthermore, if you find that most teams are not using your solution, you need to ask yourself if you are building the right platform.

But also, do not jump to the conclusion of building the wrong platform too quickly.

## Platform adoption is slow [](/blog/developer-experience-platform-team/#platform-adoption-is-slow)

It will take a lot of time (and marketing) until other teams have adopted your solution. Whenever you ship a new tool or platform feature, only the most curious teams will jump on it right away. Others might take weeks or months until they are ready to use it.

Moreover, as a platform team, you usually do not have the luxury of having a dedicated marketing and sales team. You need to _sell_ your solution yourself. Show developers the benefits of your solution and how to use it. Help them, i.e., in team programmings, to apply it to their use case.

## Keep the platform small [](/blog/developer-experience-platform-team/#keep-the-platform-small)

It is tempting, to build over-engineered solutions with all kinds of bells and whistles. But as for any other product, the same is true for a platform: Build the smallest thing that possibly could work. Of course, you could build a generator that automatically generates CI pipelines for other teams, depending on their requirements. But maybe, a documentation how to define pipelines together with some sensible base jobs is already enough?

Do not underestimate the maintenance costs that complicated solutions will bring with them.

## Where to go from here? [](/blog/developer-experience-platform-team/#where-to-go-from-here)

There is much more to share about developer experience. It is an exciting topic, as you have the privilege to work closely with your customers. Therefore, it can be super-rewarding as you see your impact directly. From my experience, it takes some time until you see the positive impact, but the benefits are growing exponentially.

We are currently renaming the “Platform and Developer Experience Unit” to “Developer Experience Unit” and therefore scratching the “Platform” from the name. We learned, that in our context, the “Platform” in the name is more confusing than helping. Furthermore, good developer experience needs both, good tools and a good platform and these two areas go hand-in-hand.

## Summary [](/blog/developer-experience-platform-team/#summary)

At a certain company size, a platform team focussing on developer experience can have a huge positive impact. Such a team should…

* … not do work for teams but make their work easier and enable them.
* … see developer as their customers and the platform as a product.
* … therefore not act as police and not force teams to use their solutions.
* … not get caught up in feature development for external customers.
* … keep the platform small and most importantly,
* … be patient. Platform adoption takes time.

**Do you have a team for developer experience in your company? What are your experiences with such a team? Let me know here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**