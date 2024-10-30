+++
title = "Just care less about not being aligned"
slug = "just-care-less-about-not-being-aligned"
image = "/img/import/2021-11-06-just-care-less-about-not-being-aligned.jpg"
date = 2021-11-06T10:12:00
publishDate = 2021-11-06T10:12:00
lastmod = 2022-12-07T12:30:41
description = "Too much alignment will slow you down as the number of stakeholders increases. Creating structures that reduce the alignment needed will help you to scale your organisation."
tags = ["Software-Development","Team-Topologies","Engineering-Excellence","Organizational-Design"]
+++
# Just care less about not being aligned

 If you work in a company that is aiming for fast growth, being overly aligned will slow you down as the number of stakeholders increases. If every time I want to introduce a new linting rule I would need to agree with 55 other developers, I will likely not do it. Instead of forcing all units to use the same tech stack, the same code style, the same testing framework and so on, we need to learn to _just care less_. Of course, the ability to care less depends on the architecture and the company structure. In a monolithic application, it is far more difficult to reduce the impact of units on each other, than in an environment of properly structured microservices. Thus, the goal is to identify and create structures that allow you to care less about alignment. The entire idea of cross-functional units is aiming for units to be independent. This is achieved by having units own vertical slices of the system completely, which reduces the need for alignment with other units to a minimum. However, sometimes even cross-functional units can influence each other because of technical dependencies or suboptimal structuring of these units.

## How a technical leadership community[1](#fn:1) can help

One goal of a technical leadership community has to be to foster unit independence and autonomy by creating structures that reduce the impact of units on each other. Such structures can be technological, like introducing distinct modules or even services, or they can be organisational, such as introducing units or shifting responsibilities between units to reduce friction between them.

### Examples for technical structures

For example, at BRYTER, we currently are working on splitting dependencies of different frontend applications. This enables units to add, update and remove their dependencies without the need to synchronise this with all other units working on the same frontend.[2](#fn:2)In the backend, we see similar efforts: Initially, we started out with one big backend module (Gradle). Here we saw an uncontrolled growth of this module, resulting in slow build times and a massive list of dependencies mixed from all units. Therefore, we are facilitating team programmings in the backend team, in which we are breaking down this monolithic module and split out smaller modules that are owned by a single unit. Of course, this does not give us full independence of units immediately (think about upgrading Kotlin), but it is a great first step that gives units shorter build times of their area and also yields more clarity about responsibilities. Furthermore, this can be a great first step before finally splitting out some modules into a new service.

### Examples for organisational structures

An organisational structure that can help with alignment can be a unit that provides certain platform components that are needed by many units. With such a unit in place, some topics that were previously discussed cross-unit can now be handled in this unit. The platform unit will then analyse the needs of the units it serves and craft a generalised solution that simplifies the task of the other units and helps to reduce cognitive load.

## Strategies to care less

Just caring less about misalignment would rarely do any good for your engineering organisation. Usually, there is a reason why people care for alignment. Thus, you need to identify these reasons, understand the concerns and find ways to address them.

### Find out why people care about alignment

People usually care about units not being aligned because they are either directly impacted by the work of another unit, or they are afraid that the unit cannot make good-enough decisions independently. The later could be the case, if people are worried about the quality of the product and about some units not holding up with certain quality standards or _best practices_ that are important to the individual having the concerns. In this case, it is best to identify the reasons where this mismatch of the path the unit is taking from the views of the people with concerns are stemming. It could be, that the person outside the unit is missing context which they can get in a quick call with someone having the context. When the cause is really that the unit is not doing things that are important, we need to dig deeper:
* If the reason is “not knowing how”, coach them or find somebody who can guide them towards a better approach.
* If it is “not having time”, help them to get the time they need by communicating the issue and its criticality to whoever puts the pressure on the unit.
* If it is “not agreeing, that this is a problem” have a conversation to understand their reasoning, assuming that they know best about their specific case.

### Reduce impact of units on each other

In cases when certain actions directly impact other units, it is hard to not care. If, for example, units are introducing flaky or slow tests into a shared codebase, it is hard to care less. Here, a cross-unit community or a platform unit can help to set certain standards and to educate people about the why and the how of following these standards. Furthermore, it is crucial to reduce the size of the shared code area. In theory, even in a monolithic code base, units can have extremely diverse code- and quality standards, if they are not actually changing the same code. Identifying the right borders and splitting the code into modules that are owned by only one unit is a good strategy to reduce the need to care.

### Help others to care less

If your unit does things differently from other units, and you know about it, be verbose about it. You can proactively show others, that you have thought of the tradeoffs and are making a conscious decision when choosing another approach. This has two benefits: First, it will assure doubters, that you know what you are doing and that you are aware of the other approach. Second, it will give other units the opportunity to learn from your approach and maybe adopt it, if people deem it suitable for their context.**What is your experience with this topic: How did you manage to stay aligned while the company was growing, or how did you manage to care less? Write me in the comments or reach out via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).** 

---

1. Here I refer to a company-internal cross-unit community that knows the bigger picture and the technical vision well and can thus identify some gaps or misalignments between the current organisation structure and the plans for the future.
2. It is important to note, that the technical leadership community will rarely do the changes alone, but should always involve the developers who are most impacted by the change.