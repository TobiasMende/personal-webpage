+++
title = "DRY – DO repeat yourself"
slug = "dry-do-repeat-yourself"
image = "/img/import/2022-04-30-dry-do-repeat-yourself.jpg"
date = 2022-04-30T13:13:00
publishDate = 2022-04-30T13:13:00
lastmod = 2024-01-08T06:37:10
description = "DRY is one of the most misunderstood and abused principles. Copy more, reuse less!"
tags = ["Practices","Software-Development","Software-Craft"]
+++
# DRY – DO repeat yourself

When I started my career as a software developer and already during university, almost no principle was mentioned as often as the DRY principle: “Do **not** repeat yourself”

The DRY principal was coined by Andy Hunt and Dave Thomas and is described as:

> Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

Unfortunately, the DRY principle is not only one of the most _known_ or at least most referenced principles in software design, but also one of the most misunderstood and abused ones.

Even the simple definition above leaves a lot of room for interpretation:

* What is a piece of knowledge?
* What is an authoritative representation?
* What is a system?

What I have seen in almost every company I have worked in so far, is that developers would encourage each other to reuse code instead of copying code around and that complicated abstractions were created just because two parts of code looked similar enough. Those efforts were often justified with a single word: DRY!

## DRY – Trading duplication for dependency [](/blog/dry-do-repeat-yourself/#dry--trading-duplication-for-dependency)

However, DRY is by far no best practice, no golden hammer and no one size fits all solution. Generally speaking, I get the impression, that most times, DRY is a harmful approach.

It seems so obvious: Avoiding duplication means less code means less maintenance effort. Right? — Wrong!

Whenever we reuse existing code, we might reduce the amount of code needed. Unfortunately, we also create dependencies onto code that we are reusing. Those dependencies typically come with a much higher cost than maintaining duplicate code.

## The hidden cost of abstractions [](/blog/dry-do-repeat-yourself/#the-hidden-cost-of-abstractions)

As soon as we create abstractions so that two different parts of the system can reuse a component, those abstractions become the contract of that component. This contract needs to be explicitly tested and is hard to change, as (at least) two systems would need to change to be compatible with the new contract of the component.

Furthermore, the abstraction must be thoughtfully designed and created in the first place. Unfortunately, following the “don’t repeat yourself” mantra, developers create abstractions often too early and overfit them to their current scenarios. This is okay, if it can be guaranteed, that both using systems change at the same time and speed and in the same direction as the component they depend on. This can usually only be ensured if the component and the using systems are tightly coupled together and maintained by the same team.

Things get more complicated, when abstractions are shared across teams and repositories, as we need to think about update and migration strategies, rollouts of new versions and the like. This can be a technical but also cultural challenge. I have seen developers spend hours or days figuring out, how they can publish an internal library in a way that other internal projects could use it. Typically, the code to be shared was not very complicated or large, and it is questionable, if the abstracting, extracting and depending on brought any benefits that are bigger than the costs.

## The hidden cost of dependencies [](/blog/dry-do-repeat-yourself/#the-hidden-cost-of-dependencies)

If we reuse code across teams, the dependencies get much more costly.

First, we need to make clear, which team owns the shared component and what the interfaces and contracts of such a component are. Second, whenever there is a change that affects the contract, this change has to be coordinated with all teams that depend on the contract. Third, changing the shared components requires more understanding about the contexts in which it is used and is often more risky and complicated than changing a component tailored for a single context, having limited impact.

Those costs frequently exceed the costs of duplicating a couple of hundred lines of code, by far.

## When is code equal? [](/blog/dry-do-repeat-yourself/#when-is-code-equal)

Furthermore, just because it looks the same, it is not necessarily the same. Just because two code snippets are equal on a textual level today does not mean that they will be equal in a week. Therefore, the shared abstraction will either be patched to become even more generic or it will finally be copied over and adapted for the changed requirements.

Code is only really equal, when it does the same thing in the same context and only changes for the same reasons. This is not true for most of the shared code that I see.

One could argue, that, for example, every single frontend component, that is not technology-agnostic, does not satisfy this requirement. For example, if we had a very generic Vue 2 component that is used in different frontend apps but is incompatible to Vue 3, this already could be a problem. Owners of one app cannot decide to upgrade to a newer version without imposing the decision to upgrade on the maintainers of the shared library (or vice versa)1. This, in turn, brings either additional compatibility and maintenance overhead for the team owning the shared component or, even worse, will require all other apps to be upgraded as well.

## Back to the roots [](/blog/dry-do-repeat-yourself/#back-to-the-roots)

The DRY principle itself did not really say anything about code. However, I mainly hear it in the context of avoiding code duplication. Therefore, let’s get back to the origins and see how we can put the DRY principle into a context, where it makes sense.

> Every piece of knowledge must have a single, unambiguous, authoritative representation within a system

### What is a piece of knowledge? [](/blog/dry-do-repeat-yourself/#what-is-a-piece-of-knowledge)

A piece of knowledge, in my opinion, can be anything from documentation, data over code to processes. Therefore, we need to make sure that for everything we document, there is exactly one document that describes it.

And for every information, there is only one entry in the database. And every algorithm is only implemented once.

_Food for thought: When we document code, aren’t we actually violating the DRY principle, as we are creating two representations of a fact (the code and the documentation)?_

Sounds extrem? Yes, it is. However, the second part of the sentence comes to the rescue: _”within a system”_

### What is a system? [](/blog/dry-do-repeat-yourself/#what-is-a-system)

From my perspective, the DRY principle only makes sense, when we see a system as something that is maintained by a single team in a single context.

With this definition, I would argue that code reuse within an app maintained by a single team is okay, while code reuse across multiple teams, by default, is not. The same is true for data.

This also seems to fit what we usually see in microservice architectures, where we in general avoid sharing code between services via libraries but rather encourage code duplication. And where we rather duplicate data and live with eventual consistency instead of force on single data model onto all services.

## Summary: Please, DO repeat yourself [](/blog/dry-do-repeat-yourself/#summary-please-do-repeat-yourself)

The DRY principle is good, if it makes us think about the pros and cons of repeating vs. not repeating ourselves. Whenever we think about this topic, we need to respect the trade-offs of those decisions which cannot be made general but have to be made on a case-by-case basis.

I see too much code reuse and would wish for people to be more comfortable duplicating code, when it is about sharing code between teams. Often this approach will lead to faster results and will allow teams to change their implementations according to the needs in their context without depending on other teams.

That said, I still believe that DRY within a single context and team can be a valuable principle.

_Remark: There is nothing wrong with using components that are provided by another team, of course. However, it is crucial, that these components are officially owned and provided by that team as the interface of their system with clearly defined requirements and a clear purpose._

**What is your opinion about the DRY principle? Share it here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**

## Additional Reading [](/blog/dry-do-repeat-yourself/#additional-reading)

* My colleague Philipp Giese wrote [an interesting article](https://philgiese.com/post/what-is-cohesion-and-why-should-you-care) about the DRY principle and how its application affects coupling and cohesion of software components.

---

1. Of course, there are other strategies, such as writing additional compatibility layers, but such layers often bring additional complexity and need to be maintained properly. The latter approach might be okay, if the same team maintains all apps. If the dependencies, however, span across teams, this is certainly an approach that does not scale to more than a handful of teams.