+++
title = "Cross-functional units and uni-functional teams"
slug = "cross-functional-units-uni-functional-teams"
image = "/img/import/2021-10-29-cross-functional-units-uni-functional-teams.jpg"
date = 2021-10-29T09:08:00
publishDate = 2021-10-29T09:08:00
lastmod = 2024-01-08T06:46:29
description = "How to set up your team structures for growth."
tags = ["Software-Development","Team-Topologies","Engineering-Excellence","Organizational-Design"]
+++
# Cross-functional units and uni-functional teams

Many modern companies put a high emphasis on having multiple functions within one unit or team. The goal: The unit should be able to function with a high degree of autonomy, working on its area and owning everything in this area from beginning to end.

## Cross-functional units 

Usually, you will find product managers, backend developers, frontend developers, quality engineers and even DevOps engineers within such a unit. Depending on the required expertise, often designers, security specialists or other experts are also part of these units.

At BRYTER, we are doing the same. My current unit, for example, consists of two frontend developers, three backend developers, one cloud infrastructure engineer and one quality engineer. Because we are a highly technical and developer-facing unit[1](/blog/cross-functional-units-uni-functional-teams/#fn:1), we currently do not have an explicit product manager, but one of us (me in this case) is taking over this role. Furthermore, we don’t have a designer because we do not build any user interfaces that would need design-work.

## Uni-functional teams 

However, with a growing number of units[2](/blog/cross-functional-units-uni-functional-teams/#fn:2), it can be critical that people of the same function also share some time together across units. This is especially important, when the (mostly) independent units work on shared components, such as a shared service, a shared frontend or a shared infrastructure.

This is the case at BRYTER: Even though we have several services, most units will find themselves contributing to the shared backend and the shared frontend. Thus, constant exchange across units is very beneficial.

In such a shared environment, units definitely will impact each other at some point. Let it be by introducing slow tests, insecure dependencies, by not using release toggles to allow safe deployments of a shared service or by introducing warnings into the build. All these examples will not only affect the specific unit, but will be visible to all developers working on that shared codebase. Thus, naturally, there is a high interest of developers to align and agree on certain topics across units.

This can be done in uni-functional teams. At BRYTER, for example, we have a frontend team, a design team, a QA team and an infrastructure team. Inside these teams, we do team programmings or have discussions about common approaches for certain topics that affect not only a single unit.

For us, this is especially the reality for the backend and frontend teams. For members of the infrastructure team and the QA team, this is currently a bit different. They work closer together inside the team and are only remotely connected to a unit.

## Challenges of this two-fold approach 

Having both, cross-functional units and uni-functional teams does not come without challenges.

For folks that are more connected to their unit, it is sometimes hard to step out of the unit work to invest significant time in cross-unit team efforts.

For people who are more connected to their teams, it is more difficult to spend a fair amount of their time inside the unit.

Both tendencies have their pros and cons. A strong team comes with a strong alignment on how to do certain things, like how to maintain the infrastructure as code or which test framework to use in the company.

On the other side, a strong cross-functional unit usually has a high level of autonomy, speed, and little dependencies to other teams or units but might produce artefacts differently from other units (i.e., using other frameworks, code style, …)

I often see a tendency to put increased effort in aligning and unifying things across units. This might work well for 5-10 units, but will hardly scale to 20-30 units. Thus, we need a better approach:

We need to learn how to care less about not being aligned.[3](/blog/cross-functional-units-uni-functional-teams/#fn:3)

## What else we can do 

Besides learning to live with not being aligned, we can also foster alignment where it matters. If units cannot work completely independent but work on a shared codebase and influence each other, we can introduce some structures that can help us to unify the concerns that we care about.

In our case, we have introduced a unit for platform and developer experience topics, that makes suggestions and guides units towards a certain approach for things like testing, error handling or monitoring.

Here it is important, that such a unit does not have a _policing_\-function but just provides solutions and advocates for them. At the end, every unit should still have the autonomy to decide for or against a suggested approach, being aware, that there are no silver-bullets that will work equally well for all units. However, the goal of a developer-focused unit should always be to build things that help the majority of other units.

## Summary 

While a company can have both, cross-functional units and uni-functional teams, to scale, it is important to shift towards independent and therefore cross-functional units.

Attention has to be paid to areas, where high alignment seems to be important. Here it might be beneficial to work towards an approach that requires less alignment instead of forcing more alignment.

**I am curious about your opinion on this topic. Let me know in the comments or reach out via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**