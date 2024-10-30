+++
title = "Do you have walls in your deployment process?"
slug = "deployment-process-walls"
image = "/img/import/2021-11-20-deployment-process-walls.jpg"
date = 2021-11-20T11:59:00
publishDate = 2021-11-20T11:59:00
lastmod = 2024-01-08T06:46:34
description = "Walls in your deployment process block value-flow and slow-down feedback cycles. Here is how you can detect and remove them."
tags = ["Continuous-Deployment","Software-Development","Team-Topologies","Developer-Productivity","Engineering-Excellence","Organizational-Design","Software-Craft"]
+++
# Do you have walls in your deployment process?

Enabling units to quickly deploy and release new features to their customers is one of the goals of [cross-functional units](/blog/cross-functional-units-uni-functional-teams/) and the “you build it, you run it” DevOps mentality.

However, coming from historical backgrounds of siloed teams and shared monoliths, this is often not the reality, in which units are operating today.

Indeed, units are often cross-functional nowadays. However, not all functions are fully integrated in this new model. In all companies, I have worked so far, especially QA and infrastructure teams were often operating in a different mode.

There are reasons for this, but depending on who initiates (or executes) the deployments, these teams are at risk of becoming bottlenecks in the deployment process. Walls in the deployment process are the natural consequence of this.

## Case Study: Deployments at BRYTER [](/blog/deployment-process-walls/#case-study-deployments-at-bryter)

At [BRYTER](https://bryter.com/careers/), we have shared deployment artefacts. Multiple units contribute to these. Our QA team of three people, at that time, was kicking off the deployment process and was executing various manual and semi-automatic steps. Most of these were widely unknown to the developers.

All we developers needed to care about, was that deployments happen on Tuesday and Thursday, and we need to get our code merged by that time if we want it to be part of the deployment. Sounds paradisal for developers? Somehow yes. It is always convenient if you do not have to deal with the consequences of your actions.

Of course, we were responsible for shipping working software and for solving production incidents fast. However, there was the safety net in the form of the QA team, who would test our code and would often find something that was blocking deployments. This not only meant a delay of the deployment, but also a lot of wasted effort by the QA team, which was now waiting for a fix from development, after which they would restart the deployment process.

Not rarely, the entire process would take a full day, blocking at least two people of a three-people-team. Imagine, what doing this twice a week meant for their productivity. And of course, they were not happy with this situation. In fact, developers were not happy with the situation as well because they could not understand why deployments took so long and were not done more often.

Thus, as a conclusion of this, everybody was unhappy and the only people, knowing about the deployment process, were in the QA team which was busy doing deployments and had no capacity for actually working on the process. Furthermore, a uni-functional team also isn’t well equipped for working on a CI/CD pipeline, as this usually involves a lot of knowledge of other disciplines such as infrastructure.

Thinking about this systemic issue in the “Platform and Developer Experience Unit”, we decided, to completely throw-over the process and fundamentally change how we deploy at BRYTER.

### The idea: Let developers do deployments [](/blog/deployment-process-walls/#the-idea-let-developers-do-deployments)

In order for developers to really own their product, they also need to own the deployments and the effects they have on the system. The good as well as the bad ones. Furthermore, we thought that developer involvement in deployments will spark countless interesting questions, ideas, and learnings around the process that will finally lead to an improvement of the process itself.

Therefore, we decided that it would be much better, to have developers be in charge of deployments. We, of course, had full support of the QA team, who also disliked the fact, that they ended up in charge of the deployments. Furthermore, when I pitched the idea to the technical leadership community in the company, the feedback was overwhelmingly positive.

Thus, we started to flesh out the idea to pitch it to all developers.

### How we started this change [](/blog/deployment-process-walls/#how-we-started-this-change)

Shifting the responsibility for the deployments from the QA team to the units cannot be done just like that. The QA team has built up a huge amount of knowledge around the deployment process, whereas most developers had almost none. Thus, just shifting the responsibility would be a dangerous thing to do.

Consequently, the QA team started to document the process in depth and were adding further information while performing deployments.

Furthermore, we decided that every deployment, done by a unit, will be shadowed by a QA person, who will not do the steps but will give developers the safety that they need to do this operation, which was highly unusual for them. This is especially important because developers perceive deployments as a bit risky, even if there is a solid set of tests. Things can go wrong, even good automated tests in place and most developers felt not equipped to deal with them, given that not only their unit, but many others were contributing changes to a deployment.

Because we have multiple units contributing to a shared deployment artefact, we decided to rotate the deployment responsibility. Thus, in every week, another unit would do the deployments.

The goal was, that every unit gets a rough understanding of the deployment process. But even more important, every unit had the opportunity to ask questions about the process and encounter the challenges first hand.

In each week, we would do a retrospective with the unit, the QA team and a member of the platform unit to learn from the experiences, while they were still fresh. Furthermore, we introduced a board to track improvement ideas and the progress of implementing these.

### What we learned from the change [](/blog/deployment-process-walls/#what-we-learned-from-the-change)

We learned. A lot. And we improved. A lot.

First, developers were **shocked**, how complicated and tedious the deployment process was. This pain produced two things:

1. Empathy for the QA team (“We can’t believe you had to do this at least twice a week. **Every** week. Sorry for that!”)
2. Interest in the deployment process and, with this, many questions and ideas. (“Why are we testing this in that way”, “Why is this not automated”, “Why are we doing this at all”, …)

Now that developers were experiencing the pain of doing deployments first hand, we were **very** motivated to improve the situation. Moreover, this cross-functional approach of doing deployments helped to surface waste in the process.

For example, was the QA team testing certain things manually during deployments. With the developers on board, we decided to drop these steps entirely because we already had automated tests for these areas since a long time. The QA team just was not aware of them.

Furthermore, we stripped some other tasks, such as creating a change log, from the deployment process and automated others like smoke-testing the application after deployments on staging and in production.

Moreover, developers learned about the Selenium end-to-end tests and that these are sometimes flaky because of _careless_ changes to the frontend or because of missing communication between developers and QA people inside of units. This is a situation we are currently improving by bringing the responsibility for the Selenium tests into the cross-functional units and also by automating them completely. Up to this date, they were not part of the automated continuous integration pipeline but were executed manually directly before a production deployment.1

Last but not least, developers are experiencing the difficulty of coupling deployments and releases and not properly separating these two actions by using release toggles. This is one of the benefits of having this direct feedback loop that comes from the involvement of developers in the deployment process.

### Next Steps [](/blog/deployment-process-walls/#next-steps)

Of course, this is not the end of the improvement process. Having varying groups of people doing the deployments could sound as if it makes things worse. And to some extent, it does. It definitely isn’t something, that made us faster immediately. But it puts us into a situation from which improvements can be made more easily because interest in these improvements is much higher now and more people can contribute ideas on how to improve the process.

Currently, we are working on making the automated end-to-end tests stable, fast and part of the CI/CD pipeline. With this in place, developers will get direct end-to-end test feedback after (or even before) merging.

The deployment process then will not be much more than clicking a button. Once this is working sufficiently well, we aim to remove that button and fully automated the deployment every time build and test stages are green. Thus, developers will not need to be on a “deployment rotation” any longer, but deployments will happen continuously and fully automated.2

## Key Takeaways for your Context [](/blog/deployment-process-walls/#key-takeaways-for-your-context)

Where and how to start this change obviously depends on the company, the culture and where you are currently standing. If you see a problem with your deployment process (or any other matter), it helps to:

1. **Write it down.** This will help you to think it through more in depth. Furthermore, it will help you to find some gaps and rough edges, that you can refine.
2. **Discuss it with others.** Ask the right people if they can relate to this problem and what their ideas are. Before you initiate a bigger change, it is always good to know that you are not alone with the perception, that there is a problem.
3. **Refine your approach.** Use the feedback that you get from your peers to fill the gaps and make your idea more round.
4. **Pitch it.** With the support of the right people for your endeavour, pitch it to the other people who will be affected or who need to cooperate to make the change a success.
5. **Implement it.** Put it into action and help others to contribute their part to the result.
6. **Give updates.** Keep your peers up to date on how it is going, which improvements you are seeing and also, where you discover problems that need to be addressed. This makes sure that not only you can see the progress and value, but also the folks that might not be as connected to your mission see, why the change is valuable.

## Conclusion [](/blog/deployment-process-walls/#conclusion)

Units that develop parts of the product should have a stake in the deployment process and should be able to deploy their changes frequently and without external help.

By shifting the responsibility onto the units, they had to learn about the status-quo and were able to contribute to a better solution.

While this shift was not without friction nor resistance, it helped us to move closer to continuous deployment and sparked many discussions and initiatives around improving the current process.

**How are you doing deployments? Who is responsible for the deployment process? Let me know in the comments or reach out via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende). Sharing highly appreciated!**

---

1. Executing test _before_ deployments and not _before_ integrating code causes more problems, which are out of scope for this article.
2. Adopting continuous deployment is a [more cultural shift than a matter of tooling and automating processes](/blog/adopting-continous-delivery-culture/).