+++
title = "The Inverse Conway Manoeuvre in Existing Systems – It does not work!"
slug = "the-inverse-conway-manoeuvre-in-existing-systems"
image = "/img/import/2023-04-15-the-inverse-conway-manoeuvre-in-existing-systems.jpg"
date = 2023-04-15T06:00:00
publishDate = 2023-04-15T06:00:00
lastmod = 2023-04-15T06:20:07
description = "The Inverse Conway Manoeuvre is unlikely to work in existing sociotechnical systems of a certain size and stability. It is even less likely to work in remote companies and distributed teams."
tags = ["Collaboration","Employee-Happiness","Software-Architecture","Team-Topologies","Technical-Leadership","Engineering-Excellence","Organizational-Design","Software-Craft"]
+++
# The Inverse Conway Manoeuvre in Existing Systems – It does not work!

In 1968, Melvin E. Conway postulated a _law_ about a connection between organizational design and system structure, which got pretty famous. The paper has the title “[How Do Committees Invent?](http://www.melconway.com/Home/Committees%5FPaper.html)” and the _law_ goes as follows:

> Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization’s communication structure.

This connection between product and organizational architectures was confirmed by research, for example in 2007 in the paper “[Exploring the Duality between Product and Organizational Architectures: A Test of the “Mirroring” Hypothesis](https://www.hbs.edu/ris/Publication%20Files/08-039%5F1861e507-1dc1-4602-85b8-90d71559d85b.pdf)” by Alan McCormack et al.

Three years later, in 2010, Jonny LeRoy and Matt Simons published [an article](http://jonnyleroy.com/2011/02/03/dealing-with-creaky-legacy-platforms/) in the December 2010 issue of Cutter IT Journal, coined the term _Inverse Conway Manoeuvre_.

In this article, I will dive into the applicability of the Inverse Conway Manoeuvre in existing sociotechnical systems, that is, systems consisting of organization structures, social networks, and system architecture.

## Definition of the _Inverse Conway Manoeuvre_

Originally, the authors stated that it might be possible to change the system architecture by changing the organizational structure and communication paths and thus using Conway’s law.

This sparks the idea that one could achieve a desired system architecture by structuring the organization in a way that would likely produce that system architecture, following Conway’s law.

This works well in green field environments when creating a new system with a new and unformed organization. 

But what if there is a history of some kind? What if a system architecture is already in place, an organization already has established structures and communication paths, or both?

## The Inverse Conway Manoeuvre in Existing Sociotechnical Systems

In the past, I have seen many attempts and tried to utilize the Inverse Conway Manoeuvre to alter an existing system architecture by changing team topologies. The idea: When we change the team structures, the teams will start to change the system until we arrive at the desired architecture.

There are at least two problems with this approach:

1. Changing existing teams and communication paths is hard.
2. Changing existing system architecture is hard.

### 1\. Changing existing teams and communication paths is hard

Of course, we must do more than just draw an architecture and an organizational design and restructure the teams to match it. Teams consist of humans, and humans have personal relationships. Breaking existing groups forcefully will have disastrous effects on the morale of the people within, their productivity, and, ultimately, the system they ought to build.

Thus, restructuring teams can only work, if the members of the team have an intrinsic motivation to change the team structures. For this to happen, they need to understand and believe in restructuring the teams. Only if all the team members of affected teams understand and support the restructuring, it could work.

Especially when it is tough to change communication paths and where people will jump on a call and collaborate happily across team boundaries if it gets their job done quicker. Thus, you might find that the old communication structures still exist, and therefore the desired effect on the system does not happen.

Furthermore, restructuring teams can come with a high cost on productivity. 

> Teams take time to form and be effective. Typically, a team can take from two weeks to three months or more to become a cohesive unit. — from “Team Topologies” by Matthew Skelton and Manuel Pais

 This is even more true when the new team structure conflicts with the system architecture, which brings me to the second problem:

### 2\. Changing existing system architecture is hard

Changing existing and potentially complex system architecture is hard work. It requires a profound understanding of the current system and the desired state. Furthermore, it requires in-depth knowledge and belief in the reasons behind this refactoring.

Only if enough people believe in the value of the change and understand how they can contribute to it could they potentially work towards that goal. If one of those is missing or there are other factors, such as outside pressure to ship features, people are prone to continue on the tried and tested paths, further solidifying the old architecture.

### Conclusion: When both are hard, do both simultaneously!

We cannot rely on an Inverse Conway Manoeuvre to change an existing architecture. This is even more true in distributed teams where we cannot encourage in-team communication and discourage cross-team communication _(by the way: I believe preventing this is bad, anyway)_. Forcefully applying the Inverse Conway Manoeuvre in existing systems does not work.

When people were still sitting in offices, managers could _hypothetically_ go in, come up with a new team design and place different teams on opposite sides of a building or other floors. This made cross-team communication a lot less likely. Even if people would benefit from this kind of communication, it was much more likely that they would waste time figuring it out inside their team. This may have favored the Inverse Conway Manoeuvre. However, in distributed teams and companies, we need to have these physical boundaries. It is (or should be) easy to work together in various constellations.

This is terrible news for the Inverse Conway Manoeuvre but good news for the people. We cannot force communication structures as quickly as in offices. Because of the first problem above, this also isn’t the best approach to changing system architecture and the team structures around it.

The flexibility and variability of communication networks are significant benefits of remote companies, where little support can be enough for the most effective communication path to winning. (Of course, there are downsides, too. But this is for another article) 

A better approach to changing system architecture and team structures is to do both simultaneously.

## Evolving new system architecture and team structure simultaneously

 One of the best approaches that I have found to work extremely well when changing the system architecture is, not surprisingly, collaboration. In “[The value of team programmings](/blog/the-value-of-team-programmings/)” I already stated some benefits of cross-team collaboration.

Cross-team collaboration also is an excellent way of changing the system architecture for the following reasons (there are likely more):

1. Such a change usually affects more than one team. Thus, discussing and implementing it together is helpful to create a shared understanding and get all the information available.
2. Architecture refactoring can be quite complex. Having more people think about the change, how to implement it, and what could go wrong is likely to improve the outcome.
3. During the collaboration, it is easy to clarify the intent of the refactoring and make sure everybody understands why and how the change is implemented.
4. The teams get to know each other better and learn to work with each other and people will probably be more open to restructuring the team structures, once the architectural change is done.
5. It avoids the ivory tower architect syndrome. There is not the architect who invents an architecture, forces the system into that structure, and lets the teams deal with the consequences. The architecture is evolved collaboratively. It might even be, that the initial target architecture that some people had in mind is not the final architecture, as the teams learn and adapt on the go.

Evolving the architecture collaboratively can be ongoing for weeks, months, or even longer. Depending on the complexity and size of the system that needs to be changed, and the focus, teams can put on it. Already collaborating on this change for half a day every week can slowly evolve the system into the desired state.

When people understand the reasons and how to change the system, they are also more likely to work in that direction during their day-to-day feature work.

## What others say

This article summarizes my observations and experiences around Conway’s Law, its inverse, and its applicability to existing sociotechnical systems. Now, the interesting question, of course, was: Is it just me? Maybe we did something wrong? Perhaps my understanding is wrong?

Searching for other experiences, I found two excellent posts that confirm my observations. I recommend reading both.

In “[Conway’s Law Doesn’t Apply to Rigid Designs](https://verraes.net/2022/05/conways-law-vs-rigid-designs/)”, Mathias Verraes concludes that the Inverse Conway Maneuver does not work in rigid systems and suggests extending the Inverse Conway Manoeuvre as follows:

> **If the system is new or flexible**, change the organizational structure to get the system design you want. **If the system is rigid, emphasize design work.**

The second article I would like to recommend as an additional read on this topic is by Martin Fowler on [Conway’s Law](https://martinfowler.com/bliki/ConwaysLaw.html), where he references the article by Mathias:

> While the inverse Conway maneuver is a useful tool, it isn’t all-powerful. If you have an existing system with a rigid architecture that you want to change, changing the development organization isn’t going to be an instant fix. Instead, it’s more likely to result in a mismatch between developers and code that adds friction to further enhancement.

## Conclusion: It is unlikely to work!

The Inverse Conway Manoeuvre is unlikely to work in existing sociotechnical systems of a specific size and stability. It is even less likely to work in remote companies and distributed teams. 

In short, in existing sociotechnical systems, the Inverse Conway Manoeuvre is challenging to execute and unlikely to yield the desired outcomes. The Inverse Conway Manoeuvre can work on new and flexible systems but might not be as relevant for existing systems as we believe. Applying the Inverse Conway Manoeuvre on existing systems will result in friction, reduced performance, and frustration among engineers at worst and no effect at all at best.

In existing sociotechnical systems, collaborating on the changes of the technical system can yield much better results, as it makes changes in the social system much easier and more likely to succeed.

**What is your experience with the Inverse Conway Manoeuvre? Have you seen it working in existing sociotechnical systems?**