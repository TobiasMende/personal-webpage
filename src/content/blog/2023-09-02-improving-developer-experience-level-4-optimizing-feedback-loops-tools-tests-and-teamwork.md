+++
title = "Improving Developer Experience, Level 4: Optimizing Feedback Loops: Tools, Tests, and Teamwork"
slug = "improving-developer-experience-level-4-optimizing-feedback-loops-tools-tests-and-teamwork"
image = "/img/import/2023-09-02-improving-developer-experience-level-4-optimizing-feedback-loops-tools-tests-and-teamwork.jpg"
date = 2023-09-02T04:00:00
publishDate = 2023-09-02T04:00:00
lastmod = 2024-01-08T05:46:30
description = "A responsive development environment, automated tests managed by engineers, and distinct deployments from releases are key. Embrace real-time code reviews for immediate insights. The intersection of automation, collaboration, and swift feedback defines developer success. How are your feedback loops?"
tags = ["Collaboration","Continuous-Deployment","Developer-Experience","Developer-Productivity","Ensemble-Programming","Software-Testing","Team-Programming","Technical-Debt","Engineering-Excellence"]
+++
# Improving Developer Experience, Level 4: Optimizing Feedback Loops: Tools, Tests, and Teamwork

[Last week](/blog/improving-developer-experience-level-3-the-triad-of-clarity-focus-and-flow/), we dove into focus, clarity, and flow. Today, we will delve into the top layer of [Maslow’s Hierarchy of Needs (DevEx Edition)](/blog/maslows-hierarchy-of-needs-devex-edition/). Here, it gets a bit technical. While the three bottom layers are mostly concerned with culture, structures, and processes, the top layer includes technical and cultural aspects. This shows how important and foundational non-technical aspects are for outstanding developer experience.

Nonetheless, the technical experience and the factors related to fast feedback can make or break the overall developer experience and cause massive frustration daily. 

Feedback varies, from real-time responses in an IDE to customer feedback on new features. To elevate the developer experience, minimizing feedback delays and ensuring effective feedback mechanisms is essential. 

Now, let’s delve into how these factors can be optimized:

## The Development Environment

The “development environment” refers to equipping engineers with the right tools. This includes a suitable IDE for their tech stack, tools like linting and type checking that provides immediate feedback, and efficient machines tailored to their needs. 

Surprisingly, many leaders overlook the demotivating impact of limiting developers to a specific operating system. Moreover, skimping on resources like RAM affects productivity. An engineer’s frustration grows when company constraints prevent access to tools that could boost efficiency. In terms of productivity, reducing feedback time — even by milliseconds — makes a difference. 

Consider the efficiency leap from faster compilation, linting, and testing, which can be achieved with better hardware. A responsive development environment is essential, not only for quicker feedback but also for effective refactoring and maintaining a healthy codebase.

## Automated Testing

There should be no discussion today if we need to test our software. And with our software’s growing functionality and complexity, there is no way around writing automated tests.

Any software used more than a single time and needs to be extended, maintained, or updated over time should have automated tests that give confidence that it works as intended. This confidence not only allows us to extend our application, it also allows us to refactor it and keep it in a maintainable state.

Trustable automated tests are a first plus for the developer experience, increasing perceived safety and confidence. However, that is not all. Concerning having fast feedback, those tests have to be as fast as possible, and their ownership must be within the engineering teams.

he traditional model of positioning the QA team at the end of the development cycle is outdated and acts as an impediment in the value stream, disrupting both flow and timely feedback. This structure is a source of frustration for both developers and QA engineers. Instead, integrate QA experts within the teams, or have them empower developers to enhance their testing skills. While QA engineers often favor end-to-end testing to assess overall system functionality, such tests take considerably longer than unit or integration tests, leading to delayed feedback.

To summarize, tests should be 

* automated,
* fast,
* owned, maintained, and understood by engineers, and
* sufficient to have confidence.

## Frictionless Releases and Deployments

Releasing and deploying software are often perceived as the most risky events by developers, who are not used to doing those often. That feeling typically vanishes when we move toward continuous deployments and decouple deployments from releases.

What am I getting at? Traditionally, once changes are deployed, customers feel the impact immediately. This elevates the significance of each deployment since it simultaneously introduces changes to the end-users. However, with experience, we can distinguish between deploying a change and releasing it to our audience. We can incrementally introduce (or retract) these changes, mitigating potential risks. I’ve delved deeper into this crucial subject in my article: “[Crucial developer practices: Decoupling deployments and releases](/blog/decoupling-deployments-and-releases/)”.

Separating deployments from releases streamlines the process. Increasing the frequency of these deployments minimizes risks and reduces their perceived significance. In time, deployments are as routine as build and test steps in the pipeline. 

By automating these deployments and entrusting the pipeline with quality assurance, we eliminate common challenges associated with the deployment process.

It will also help your team to improve the process continuously. Continuous deployments and easy means of releasing software shorten one of the most important feedback loops: The feedback loop from a production system and real customers back to developers.

To gain rapid feedback from their deployment process, teams should own deployments rather than delegate to an operations team.

Handoffs in the value stream are an antipattern that is the root cause of friction, reduced flow, and delayed feedback. — If that sounds like your context, [let’s talk](https://unblocked.engineering/#DiscoveryCall)!

## Reviews are Feedback, too

There are many other feedback loops besides automated tests and customer feedback, such as events from a monitoring system or feedback from code reviews.

Streamlining the code review feedback loop is vital for engineers, yet it’s frequently overlooked. Developers shouldn’t feel the need to request reviews and then wait extended periods for feedback constantly. The remedy? Foster collaboration. Through pair- or team-programming, continuous coding and communication become the norm. This expedites feedback and promotes superior solutions, mutual learning, and a stronger understanding among team members.

Thus, the best way to do reviews is continuously and synchronously, not in the asynchronous way tools offer us in the form of pull- or merge requests.

## Summary

In the latest edition of DevEx Nuggets, we saw that swift and continuous feedback is at the core of an outstanding developer experience. This feedback spans from simple IDE interactions all the way to valuable input from customers on new features. 

![](https://unblocked.engineering/wp-content/uploads/2023/08/Feedback-Loops.png)

Feedback loops and the delays that usually come with them

The development environment is also crucial; engineers should be equipped with the right tools, receive immediate feedback mechanisms, and operate on efficient systems. Investing in the proper equipment and configurations can’t be stressed enough. 

As software grows in complexity, the emphasis on automated tests has become undeniable. These tests must be automated, quick, managed by engineers, and comprehensive in their coverage. The traditional setups of having separate QA teams are becoming less relevant, highlighting a shift in how testing should be approached. 

On the deployment front, the emphasis is on regular, low-risk deployments distinct from the actual releases seen by customers. Automation plays a central role here, ensuring smooth and consistent releases. 

Finally, the way we look at code reviews is evolving. There’s a push towards more continuous and synchronous review methods, like pair programming, which provides immediate feedback and fosters learning and collaboration among peers. 

Marrying swift feedback with automation, collaboration, and the right resources delivers the optimal developer experience.

**Where do you stand with your feedback loops? What do you want to improve next?**

## Unlock Your Team’s Full Potential! 🚀

**For Engineers:**

* Feeling undervalued despite pouring in hard work and passion?
* Drowning in meetings and technical complexities and debt?
* Concerned about sacrificing quality for speed or facing siloed knowledge?

**For Leaders:**

* Do you need to go faster, but hiring is not working or not an option?
* Overwhelmed by endless fires to put out and decision-making bottlenecks?
* Worried about team motivation, trust issues, or talent retention?

🌟 **I can help!** 🌟

Let’s dive into these challenges together and chart a way forward. Don’t let these pain points hinder or destroy your team’s brilliance. I’m here to help and to provide tailored strategies to turn these challenges into growth opportunities.

🔔 **Act Today!** 🔔

[Book a FREE discovery call with me](https://unblocked.engineering/#DiscoveryCall), and let’s unlock the success your team deserves!