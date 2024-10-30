+++
title = "Adopting Continuous Delivery: More a culture change than automation of processes"
slug = "adopting-continous-delivery-culture"
image = "/img/import/2021-12-04-adopting-continous-delivery-culture.jpg"
date = 2021-12-04T12:07:00
publishDate = 2021-12-04T12:07:00
lastmod = 2024-01-08T06:46:37
description = "When moving towards a more continuous software delivery process, focus on evolving the culture instead of just automating the processes."
tags = ["Continuous-Deployment","Software-Development","Developer-Productivity","Engineering-Excellence","Organizational-Design","Software-Craft"]
+++
# Adopting Continuous Delivery: More a culture change than automation of processes

Continuous delivery, the process of automatically delivering changes of a system without human interaction, is one of the most beneficial practices that software teams can adopt. In [Accelerate](https://www.goodreads.com/en/book/show/35747076-accelerate), the authors Nicole Forsgren, Jez Humble and Gene Kim, discovered a strong link between using continuous delivery and organisational performance: Teams that continuously deliver their changes have a stronger sense of ownership, get faster feedback and need to rework their code less. Furthermore, deployments are less stressful and the risk of burnout is reduced.

Therefore, it is understandable, that more and more companies want to transition to a continuous delivery process. Often, focus is put on the processes that are done manually and how to automate those.

This approach is hardly optimal, as it ignores the cultural component of this change. Usually, the bigger challenge is not how to automate processes, but how to work with this new software delivery approach. Just automating manual processes is doomed to fail.

## Observe first [](/blog/adopting-continous-delivery-culture/#observe-first)

Developers are good at automating things. Thus, it is tempting to automate tedious processes straight away. However, this is not the ideal solution.

Whenever I came into a new team or company where the delivery process was less than ideal, I resisted the urge to automate it but tried to understand it first.

* Who is involved?
* Which steps are part of the process and why?
* What can go wrong? And what is the reaction to this?
* Who is responsible for the system reliability?
* …

Sometimes you will find astonishing complex deployment processes that are almost impossible to automate. Usually, they are the result of small changes to an existing simpler process. Those changes were done to prevent some problem, that occurred in the past. Just as we sometimes add accidental complexity to software while fixing a bug, the same can happen with processes.

Understanding and questioning the process can help to discover the _real_ process, which is buried deep in the complexity. Sometimes, safety mechanisms that were added in the past lead to local improvements of the process while making the overall process more complex. Completely rethinking the process can lead to simpler solutions.

## Be aware of the “Wall of confusion” [](/blog/adopting-continous-delivery-culture/#be-aware-of-the-wall-of-confusion)

The wall of confusion can quickly arise, when software teams are not responsible for deploying and running their software. Whenever another team is responsible for deployments, this team will guard itself from potential malfunctions and problems in production by creating (painful) change management processes that are meant to reduce the risk of something going wrong.

This rarely works. In my article “[Do you have walls in your deployment process?](/blog/deployment-process-walls/)” I describe how these walls can be discovered and removed.

Continuous deployment can only work, if software teams have a high level of ownership for the stability and reliability of their software in production.

## Ownership for production systems [](/blog/adopting-continous-delivery-culture/#ownership-for-production-systems)

Traditionally, ownership of production systems often lies in the hand of an infrastructure team. However, such a team cannot own stability and reliability of a software system, as these factors can be negatively influenced by deployments that bring changes into the system. Therefore, such teams can only really own these aspects, if they prevent changes.

Changes not only bring risk but also value and therefore, organisations aiming for high-performance need to enable teams to change the system fast and often. This only works, when teams own their software from beginning to end, from the requirements to execution in production. Any malfunctions of the system need to be discovered by the teams that can fix them as soon as possible. Therefore, ideally, there is no other team between the production system and the development team.

This guarantees a quick and barrier-free feedback-loop that enables teams to improve the system fast.

Teams who own their services have “skin in the game”. They benefit from improvements and feel lack of quality directly. Thus, they are highly motivated to apply good practices that have proven to increase the quality and will solve pain points quickly.

## Continuous delivery needs continuous improvement [](/blog/adopting-continous-delivery-culture/#continuous-delivery-needs-continuous-improvement)

Continuous delivery helps us to continually improve the system. But also, the continuous delivery process needs to be improved constantly. Sometimes, things can go wrong and deployments can break parts of the application. It can be tempting to just go back to manual deployments in such an event.

Before jumping to quick actions, development teams should run a blameless post-mortem to discover the root cause of the issue. This will help them find better ways of preventing these kinds of problems in the future.

Rarely, doing things manual is the best solution. Quite often, problems stem from a lack of automated tests or lack of [release toggles](/blog/decoupling-deployments-and-releases/) that allow for save release of changes, independent of deployments.

With continuous delivery in place, developers need to learn how to do small and incremental changes to the system that are guarded by automated tests, release toggles or other mechanisms that reduce the risk of deployments. **Essentially, they need to be aware, that there is no other safety net after they push their code, besides what they have implemented.**

## Summary [](/blog/adopting-continous-delivery-culture/#summary)

When adopting continuous delivery, developers need to learn the practices that allow to safely change and evolve software without relying on other people or teams to catch mistakes.

This is often the more difficult part of automating deliveries. Therefore, development teams should not just push towards automating processes, but also build up the culture that makes safe continuous deployments possible.

**Share your story about the adoption of continuous delivery, if you have one, here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**