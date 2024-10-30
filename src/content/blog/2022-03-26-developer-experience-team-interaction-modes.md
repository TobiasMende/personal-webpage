+++
title = "Interaction modes of a developer experience team"
slug = "developer-experience-team-interaction-modes"
image = "/img/import/2022-03-26-developer-experience-team-interaction-modes.jpg"
date = 2022-03-26T13:10:00
publishDate = 2022-03-26T13:10:00
lastmod = 2024-01-08T06:37:07
description = "As a developer experience team, we are often working in a platform mode but are constantly shifting into enabling mode for better results."
tags = ["Team-Topologies","Developer-Productivity","Organizational-Design"]
+++
# Interaction modes of a developer experience team

In my [last article](/blog/developer-experience-team-shape/), I wrote about how we shaped our developer experience team and why we decided for this team constellation. In this article, I will focus on how this team interacts with the other software development teams and which aspects are particularly important.

## Two main interaction modes [](/blog/developer-experience-team-interaction-modes/#two-main-interaction-modes)

In our developer experience team, we find, that we mostly work as a **platform team**. As a platform team, we are providing tools, services, platform components and documentation that other teams can rely upon.

But: Sometimes, just working in a platform mode and providing components for other teams is not enough. Frequently, we find that our work also influences how other teams can work. For example, when we introduced [release toggles](/blog/decoupling-deployments-and-releases/) roughly half a year ago, part of our work was to document the feature and implement the abstractions. However, just providing the components and hoping for other teams to start using those components, that might also entail a change in how they work as it enables better development practices, might be too optimistic.

Thus, we realised that it is beneficial for us, to also work closer with other teams and therefore switch more into an **enabling mode**. In such a working mode, we would make effort to join teams for team programmings around certain topics where we can help them to adopt the technologies, we provide.

## Working as a platform team [](/blog/developer-experience-team-interaction-modes/#working-as-a-platform-team)

As a platform team, we need to work on three pillars that form a solid offering for developers. Actually, these pillars are very similar to what you would aim for in _normal_ product development:

1. Usability
2. Find-ability
3. Credibility

### Usability [](/blog/developer-experience-team-interaction-modes/#usability)

Our goal is to make the lives of developers easier. Therefore, our offerings must be easy to use and developers need to know how they can use the services and components we provide.

Aiming for a high usability increases the likelihood that people use our _products_ and will bring higher adoption rates.

### Find-ability [](/blog/developer-experience-team-interaction-modes/#find-ability)

The best usability is worth nothing, if people do not know about the products you are offering. This is true for companies as it is for developer experience teams.

As a platform team, you also are your marketing and sales team to a certain degree. You need to make sure that developers understand, what you offer and which problems of theirs you are solving with those products.

There are many approaches to increase the find-ability of your offerings. First, you can make sure that you have the appropriate amount of documentation in a place, where developers would usually look for. Second, you can also give trainings, presentations and announce updates and new _products_ via internal communication channels, such as Slack.

In our company, we are posting a weekly update with changes that are interesting to other teams. Furthermore, we announce bigger news individually in Slack or as a tech fair presentation. In addition, we sometimes also facilitate cross-team programmings to share knowledge about platform capabilities and also get direct feedback from developers.

### Credibility [](/blog/developer-experience-team-interaction-modes/#credibility)

It is crucial that developers can trust in your offerings. This means, that they should work as expected and not be surprising in their use.

Therefore, they should behave as documented, have a good quality and should not change too often. Especially if you changed the APIs of your offerings or frequently deprecate some of them, people will lose trust as you give them a lot of work, which might eat up the benefits.

Furthermore, it is beneficial to aim for consistency of your different offerings to reduce space for surprises.

## Working as an enabling team [](/blog/developer-experience-team-interaction-modes/#working-as-an-enabling-team)

When working in an enabling mode, the work is less about providing a _product_ but more about helping teams to understand and adopt those products or even practices that might be beneficial for their work.

As a developer experience team, constantly shifting between those two modes, has many benefits:

Foremost, you increase the adoption rates and make sure that people understand your offerings. Second of all, you get immediate feedback from your _customers_. And third, you stay in close contact with the other teams and get a feeling for their biggest pains and struggles.

Working in an enabling mode can mean many things. Parts of your team might temporarily join another team to work with them together on a certain topic. This can be days, weeks, or even months. The goal here is to build up knowledge in the other team so that it can work fully independent in the end.

It can also mean to facilitate team programmings around certain topics, where your team discovers a slow adoption or a lack of knowledge.

In general, you have to make yourself approachable for other developers and teams and have a _customer-oriented_ mindset.

## Disclaimers [](/blog/developer-experience-team-interaction-modes/#disclaimers)

### Do not become a bottleneck [](/blog/developer-experience-team-interaction-modes/#do-not-become-a-bottleneck)

As a platform team, you are at risk of becoming a bottleneck. Especially, if you do it wrong. It is crucial that you do not do the work for other teams, like implementing parts of certain features or setting up and maintaining their deployment pipelines for them. Instead, you need to make their work easier, i.e., by developing abstractions that make working with the CI/CD pipelines less cumbersome.

Therefore, if other teams ask questions about those areas, do not just do the work for them, but pair-up with them and make sure that after you are gone, they can maintain the solution on their own.

I found that it is important to communicate this frequently, as other teams might have a different understanding of a developer experience team and might wait on that team to deliver certain solutions or make certain decisions.

### You are not the police [](/blog/developer-experience-team-interaction-modes/#you-are-not-the-police)

As a developer experience team, you will get a broad overview of various working styles of different teams. Frequently, you might see something that does not fit your understanding of good software development practices, or you just think you know better how others should do their job.

Whatever it is, you must not restrict the freedom of other teams. Sure, you can consult them and give them some impulses, but you can never force them to work in the way that you would prefer.

Force will create resistance and will also lead to frustrated developers. This can sometimes be difficult as it feels easier to _just decide_ which test framework all teams should use, which testing style and how they should document their work. However, this will never work eventually, as people might just stop thinking and blindly do what you say without understanding. Or they might just quit and find another place where they are more free to do their work as they like.

Thus, if you want to influence the way how people work, you need to enable them and help them to attain an intrinsic motivation to follow your way. In other words: Help them to understand why your way is better, but do not take away the other ways from them.

## Summary [](/blog/developer-experience-team-interaction-modes/#summary)

As a developer experience team, we move continuously on the spectrum from platform to enabling mode. Depending on the topic we are currently working on, we might find ourselves more on the one or the other side.

In my opinion, it is highly beneficial for our team but also for other teams, to be mindful and flexible about the working modes as sometimes better results can be achieved by not sticking to one of the extremes.

**Are you working in a developer experience team? What is your main operation mode? Share your insights here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**