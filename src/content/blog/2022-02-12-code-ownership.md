+++
title = "Code Ownership: Keeping the balance between structure and agility"
slug = "code-ownership"
image = "/img/import/2022-02-12-code-ownership.jpg"
date = 2022-02-12T12:53:00
publishDate = 2022-02-12T12:53:00
lastmod = 2024-01-08T06:36:25
description = "Code ownership is an important topic when it comes to enabling your teams and allowing developers to improve the system while keeping the overhead of changes low. While today, most companies would (hopefully) agree, that individual code ownership is bad because it creates knowledge silos and makes the organisation dependent on individuals, code ownership still is essential on a larger scale."
tags = ["Practices","Software-Development","Technical-Leadership","Organizational-Design","Software-Craft"]
+++
# Code Ownership: Keeping the balance between structure and agility

Code ownership is an important topic when it comes to enabling your teams and allowing developers to improve the system while keeping the overhead of changes low.

While today, most companies would (hopefully) agree, that individual code ownership is bad because it creates knowledge silos and makes the organisation dependent on individuals, code ownership still is essential on a larger scale.

In his short article [CodeOwnership](https://martinfowler.com/bliki/CodeOwnership.html), Martin Fowler has specified three categories of code ownership:

* **Strong code ownership:** Every module is owned by exactly one developer, who is the only person allowed to change this module.
* **Weak code ownership:** Every module is owned by exactly one developer, but others are allowed to change it. However, the owner is responsible for the module. When in doubt, developers should ask the owner, before making changes.
* **Collective code ownership:** Modules are owned by entire teams, who can change the modules as they like.

As stated before, individual code ownership, no matter if weak or strong, is highly suboptimal as it creates dependence onto a single developer who is responsible for a module and therefore has the most (or the only) knowledge about it.

## Collective code ownership to the rescue [](/blog/code-ownership/#collective-code-ownership-to-the-rescue)

Therefore, modules should always be owned by teams who feel responsible for the module collectively. Members of a team can change their modules, without asking other team members for permission, and thus can improve the module without any delays.

However, knowledge sharing within the team is crucial, as we cannot expect people to feel responsible for code that they know nothing about. Therefore, collaborative editing in pair or team programmings is a good approach to enable many (ideally all) people in a team to feel responsible for a module.

If synchronous co-creation and co-editing is not an option, we can at least make sure that we share knowledge about the evolution of a module via code reviews or other asynchronous methods.

## The limits of collective code ownership [](/blog/code-ownership/#the-limits-of-collective-code-ownership)

Collective code ownership works well, when the system and the group of people owning it, are small. However, when the group is growing and, naturally, the code base, too, collective code ownership has its limitations.

In a system of hundred of thousands lines of code and over twenty developers, it is unlikely, that all developers feel equally equipped to own every part of the system. This is even more true if developers are joining later than others and therefore miss large parts of the systems’ history.

In such a sociotechnical system, there needs to be another approach than _just_ collective code ownership to the entire system. Otherwise, we quickly run into situations, where developers are asked to fix a bug in parts of the system, they are completely unfamiliar. While experienced developers might be able to do that, they might need a long time to understand the problem and also might make suboptimal decisions due to lack of knowledge of the specific area.

## Collective code ownership within teams, weak code ownership across teams. [](/blog/code-ownership/#collective-code-ownership-within-teams-weak-code-ownership-across-teams)

While collective code ownership of the entire system does not scale well, we can still have collective code ownership for modules. Thus, an entire team a responsible for a module and every module is owned by exactly one team.

The question then, of course, is how to apply changes that touch more than one module or how to approach changes that affect a module not owned by my team.

While we should refrain from introducing _strong ownership on a team scale_, which means, other teams would not be allowed to change code they are not owning, _weak ownership on a team scale_ provides a couple of benefits:

1. It is clear, which team is responsible for a module and thus has most knowledge about the module. Thus, if a bug arises in this module, it is clear immediately, who might be fastest to further localise and fix the bug.
2. Everybody is allowed to change the module, but should somehow involve the owning team into the change, being it by discussing the change beforehand, co-editing with members of the team or asking for a review, after the change.
3. While it is clear which team to ask about a certain module, collective code ownership of the module makes it more likely, that somebody from the group of owners is available, if needed while still inviting others for making improvements.

## Weak code ownership on a team scale [](/blog/code-ownership/#weak-code-ownership-on-a-team-scale)

From my experience, it is beneficial to involve the owning team, when doing changes to _their_ modules. Otherwise, it would be very difficult for them, to really own them in the future.

However, code ownership should never prevent somebody from suggesting and also implementing changes, if they see benefits of it. Ideally, code ownership just ensures, that the right group of people is made aware of a change and also can raise their concerns, if they see a problem with this change. After all, the owning team will be responsible to maintain and operate this part of the system in the future and therefore has to be comfortable with the change.

## Conclusion: Combining two approaches [](/blog/code-ownership/#conclusion-combining-two-approaches)

Code ownership should be an enabling structure that allows developers to change all parts of the code base with confidence, by knowing whom to talk to. Furthermore, it should enable teams to be responsible for their modules by ensuring, that they are aware of changes in their area.

A combination of collective code ownership within a team and weak code ownership across teams combines the benefits of both approaches.

**How are you applying code ownership in your company? Share your experience here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**