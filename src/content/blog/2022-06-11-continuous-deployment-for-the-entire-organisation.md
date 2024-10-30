+++
title = "From two manual monolithic deployments a week to 15+ automated deployments a day"
slug = "continuous-deployment-for-the-entire-organisation"
image = "/img/import/2022-06-11-continuous-deployment-for-the-entire-organisation.jpg"
date = 2022-06-11T13:18:00
publishDate = 2022-06-11T13:18:00
lastmod = 2024-01-08T06:37:31
description = "We did it. Roughly two years after I joined BRYTER and one year after we started the developer experience team, we finally ended the era of manual deployments for roughly 15 teams."
tags = ["Case-Study","Continuous-Deployment","Culture","Practices","Software-Testing","Technical-Leadership","Developer-Productivity","Engineering-Excellence","Organizational-Design"]
+++
# From two manual monolithic deployments a week to 15+ automated deployments a day

We did it. Roughly two years after I joined BRYTER and one year after we started the developer experience team, we finally ended the era of manual deployments for roughly 15 teams.

Since May, the 16th of 2022, every change on the main branch in our main repository is ultimately going into production. This means automatic and continuous deployments for the majority of our apps and services. — And it is wonderful!

## A litte bit of context. [](/blog/continuous-deployment-for-the-entire-organisation/#a-litte-bit-of-context)

At BRYTER, four backend services and around 10 frontend apps form the main part of the system. This system is under active development. The code for those apps and services is stored in a single Git repository. Thus, 15 teams with roughly 60 developers are working on a shared code base.

There is one staging system, where the entire system is deployed and can be tested before eventually being deployed to the production VPCs. We run nine completely independent instances of the system in different regions and with different customers on them.

The deployments of our artefacts happen monolithic. This means: We always deploy everything and at the same time. When I started at BRYTER, there were technical requirements for this, which we have removed since then. Today, the monolithic deployments are just a leftover of the past because most people are most comfortable with it, and it is easy to understand.

However, we will change this soon and deploy artefacts only, when they have changed.

## A bit of history. [](/blog/continuous-deployment-for-the-entire-organisation/#a-bit-of-history)

When I started at BRYTER in June 2020, there were only two main backend services and a handful of single-page applications as the frontend.

The company at that time was smaller than our engineering team is today.

Deployments at that time were seen by developers as something dangerous and risky that you do either in the morning in the middle of the week or not at all. We therefore had one deployment on Tuesday mornings and one on Thursday mornings.

We had a QA team. That team contained three passionate and talented QA engineers. And as we did not have that many automated E2E tests, they were the ones who needed to test the application manually before it was deployed to production. Furthermore, they were executing automated E2E tests manually from their machines, when it was time to deploy, which, of course, revealed bugs at the last possible moment, causing developers to switch focus and fix the bug. Moreover, the QA team was waiting for the last changes and fixes to come in, before they would repeat the procedure again.

And since they were the ones _at the end_ of the process, they became the ones pushing the deployment button, in the end. And only the QA team really knew what it _meant_ to _deploy BRYTER_.

### This was problematic in many ways. [](/blog/continuous-deployment-for-the-entire-organisation/#this-was-problematic-in-many-ways)

First, our QA team did not have much time to improve the situation around E2E tests, as they were mainly busy with planned and unplanned deployments.

Second, developers did not really experience how their way of developing software can influence the people who are responsible for deployments for the worse or the better.

And third (and most importantly), it introduced [walls in our deployment process](/blog/deployment-process-walls/). — Developers would, more or less, throw their code over the wall and the QA team would then test it and deploy it, if they did not find any issues.

This wall also prevented both sides from learning from each other or asking questions about the process. One of the first things that was removed from the deployment process, when we involved all teams in the deployments, was the manually collected change log. It turned out, that, as we started to ask questions, we found, that we did not need a change log in this form for every release. A rolling change log, published once a month, was more than enough.

Furthermore, QA engineers were conducting manual tests for parts of the system, which were already tested by automated tests. Consequently, we stopped the manual testing, too.

## The process of changing the process. [](/blog/continuous-deployment-for-the-entire-organisation/#the-process-of-changing-the-process)

When I came into the company, I immediately started to look into the deployment process. For me, the deployment process is one of the most important aspects when it comes to how to develop software and judging the delivery performance of an entire organisation. I have many more options of incremental development and discovery when I have 20 deployments a day than when I have only one every 6 months.

Knowing various ways of how deployments can or cannot be done, I was relieved to see, that the process at BRYTER was already much simpler than in other companies I have worked before. However, this made it only more obvious to me, that we can do better.

### Starting the developer experience team helped immensely. [](/blog/continuous-deployment-for-the-entire-organisation/#starting-the-developer-experience-team-helped-immensely)

With the start of the tech leadership community and the developer experience team in spring 2021, I came into the perfect position. This position allowed me to initiate the necessary processes and measures that were required to bring us from two manual deployments a week, done by the QA team, to continuous deployment of every change.

Foremost, I was allowed and able to pick a couple of motivated engineers from all disciplines for the developer experience team. They believed in the continuous deployment idea and were excited to bring us there. Second, we had trust and support of _the management_1 to bring the company into this direction. Third, as the tech- and product lead of the developer experience team, I was able to give us the space to work on this vision (which basically meant to say “No” to many other requests).

With this cross-functional team, we removed all the technical, procedural and cultural obstacles that were between us and the continuous deployment _idea_.

### Hated by some, loved by none, and absolutely crucial: The deployment rotation. [](/blog/continuous-deployment-for-the-entire-organisation/#hated-by-some-loved-by-none-and-absolutely-crucial-the-deployment-rotation)

One of the early observations was that developers did know much about the deployment process and, thus, it had no implications for how they worked. Another observation was, that the QA team was so busy doing deployments, that they had almost no time to question or improve the process.

Thus, it seemed obvious, that we should share the experience of doing deployments with all developers. Unfortunately, as we only had one monolithic deployment, we could not just let every team take care of deploying their artefacts. Therefore, we came up with the idea of **the deployment rotation**, where every week another team would be responsible for executing the deployment process for all the artefacts in the monolithic deployment.2

The deployment rotation sparked countless improvement ideas to the process itself, and also helped developers to understand how important it is to develop _deployable_ software.

### Remove, Reduce, Automate, Innovate. [](/blog/continuous-deployment-for-the-entire-organisation/#remove-reduce-automate-innovate)

We removed all the steps from the deployment process that were not absolutely necessary, such as writing the change log and manual tests.

We reduced the time of individual jobs in the pipeline. In one quarter, this was the main objective of our developer experience team. And thus, our pipeline only takes roughly 25% of the time it needed a year ago. (Even though the company grew exponentially and so did the size of the code base.)

Furthermore, we found ways to bring the automated E2E tests into the pipeline and helped teams to take ownership of them. Up to that point, mostly QA engineers were maintaining and executing those tests. Developers were sometimes surprised, what was tested on the end-to-end test level. This lead to productive discussions and a reduction of E2E tests, as we had already many scenarios tested on other levels.

Once we had the E2E tests in the pipeline, we were surprised, how unstable and flaky they were. Thus, in the technical leadership community, we decided to put some focussed effort in removing unnecessary tests and stabilising those, that were _really_ necessary.

In the end, we had every step of the deployment process automated and executing in 20 minutes from push to production. With only one exception: Pushing the actual deploy button.

Apart from automating and simplifying the process, we had some other challenges to tackle. Initially, there was a strict order required, in which frontend and backend can be deployed. Furthermore, deployments were sometimes quite risky because the mechanisms for [decoupling deployments and releases](/blog/decoupling-deployments-and-releases/) were cumbersome and therefore rarely used. Moreover, not all developers were aware of those techniques and mechanisms.

With my team, we introduce an easier to use concept of release toggles that developers could define, implement and toggle. It enabled them to toggle those release toggles in different regions and for different customers to allow for gradual rollouts (and rollbacks).3

### The last 20% [](/blog/continuous-deployment-for-the-entire-organisation/#the-last-20)

After most technical and process obstacles were overcome, it was time to officially propose the (technically small) step to continuous deployments.

At BRYTER, we are having an organisational proposal process, where somebody who wants to change something about how we work at BRYTER writes down their tension and suggested improvement while also reflecting on the potential risks.

People then have the opportunity to ask clarifying questions or to object if they believe the proposal could harm the company.

I was extremely excited and nervous, when I put the proposal about doing continuous deployments onto our proposal board. Before doing so, I took a couple of rounds with colleagues from whom I knew they were for this proposal to shape it, phrase it and improve it. Only then, I published it – and went on a holiday.

After my returning, there were countless positive comments and many questions, and also ideas on how to improve the proposal and make the process safer.

Some people raised the concern, that it might be problematic if we deploy late in the evenings because not so many people are around to deal with incidents. I do not agree with this, as changes are small and rollbacks / fixes are quite trivial most of the time, when doing continuous deployments. However, I could see that this made sense, given from where we came. Thus, we introduced deploy freezes in the afternoons until the mornings and during weekends. I still do not believe that these measures make the deployments safer (actually I think the opposite is true), but it made it easier for people to feel comfortable with the proposal, which is more important.

Furthermore, a transition period from the manual deployments with manual checking of results of flaky tests suites to fully automated deployments was suggested. Therefore, we introduced a two-weeks transition period into the schedule.

After all concerns were addressed, I reached out to some teams where I have not heard much feedback and presented the proposal in one of their weekly meetings. Here, we were able to clarify some questions. Overall, the feedback was incredibly positive.

Thus, the proposal was accepted and roughly one month later my team did the last changes to the pipelines to activate continuous deployments.

## Why did it take so long? [](/blog/continuous-deployment-for-the-entire-organisation/#why-did-it-take-so-long)

Roughly one year, my team was actively working towards continuous deployment. “Working” of course does not mean, that we did not do anything else aside. We were working on numerous other topics. And this was good.

Implementing all the technical changes and bringing us to a technical state where we could safely continuously deploy BRYTER would probably have taken two to three months. However, this was the smaller fish to fry.

When we started to push into the direction of continuous delivery, not everybody in the company saw the value in it, nor had alle teams the necessary practices to allow for this. Thus, one of the big topics throughout the year was to help teams to see the benefits of continuous delivery and to address the concerns and fears around this topic. The deployment rotation, even though most developers disliked it, helped with this, as it reduced the distance between developers and deployments.

Furthermore, introducing mechanisms for toggling releases and helping teams to make use of them, was another factor, that brought us closer to continuous deployments.

Usually, I would probably not roll out a continuous deployment process for 15 teams at the same time. However, due to the current architecture of our system, there was not really another option besides postponing CD until we might (or might not have) team-sized services.

In summary, moving towards continuous delivery is a more cultural rather than a technical change, and those changes do not happen faster by putting more pressure. A gradual transition from where we were one or two years ago to where we are today, probably worked best.

## What is next? [](/blog/continuous-deployment-for-the-entire-organisation/#what-is-next)

Continuous deployments are just the beginning for us. My team already has countless ideas how to further improve our software delivery process and how to make teams faster and more independent, too.

Technically, we are already in a position where we could deploy services and apps independently of each other. However, we decided to push “making use of it” a month into the future to give everybody the time to feel comfortable with the current process. Furthermore, we also need to overcome some limitations of GitLab pipelines first4.

Apart from independent deployments, reducing and eventually removing deploy freezes is another topic on our agenda. We introduce the deployment freezes because people were more comfortable having them, not because we believe that they are helpful or even necessary.

Deploy freezes increase the complexity of the deployment process, as developers need to be aware, if their merge happens outside the deployment window, as this means, their change will not be deployed. This becomes especially a problem, when we do independent deployments, as what was merged first might not always be deployed first.

> **Example:** A change affects backend and front-end. The backend must be deployed first for it to work. A developer creates two merge requests, one for backend and one for frontend. They merge the backend MR in the afternoon and finish the frontend MR in the morning.
> 
> They assume that the backend must have long been deployed, as there were no alerts about pipeline failures. However, the backend MR might be merged just slightly after the deployment freezes started and thus not have been deployed (until the next change to the backend is merged on the following day).
> 
> — Of course, there are more complicated more technical solutions to solve this, but why have deployed freezes in the first place?

Once, confidence in our fully automated deployment process increases, we expect people to be more comfortable with smaller windows where we prevent automatic deployments.

## Summary [](/blog/continuous-deployment-for-the-entire-organisation/#summary)

Introducing continuous deployments at BRYTER was an interesting challenge that entailed technical, procedural and cultural changes. Today, the majority of people working here are delighted that we got there together.

It already made us much faster and enabled us to ship experiments and work in even smaller increments. I cannot imagine to ever going back to manual deployments again.

**Are you doing continuous deployments? What is your experience with them? Write me here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**

---

1. It does not feel accurate to talke about _the management_ in the BRYTER context, as we are not a hierarchical company. However, it helps if people who have a lot of respect and authority support and idea and show their trust. Naturally, founders and VPs belong to this group of people.
2. Read more about the deployment rotation in [this article](/blog/deployment-process-walls/).
3. Read more about how we implemented and adopted release toggles at BRYTER in [this article](/blog/decoupling-deployments-and-releases/).
4. GitLab currently does not provide a solution to avoid cancellation of pipelines just on one branch, but not on another. As we want to have the auto-cancellation on the merge request branches, we have activated this feature. Unfortunately, this means that GitLab sometimes cancels pipelines on the main branch when new changes are merged. There is a [feature request](https://gitlab.com/gitlab-org/gitlab/-/issues/34221) to solve this problem, but as of today, there is no workaround for this that works in our context.