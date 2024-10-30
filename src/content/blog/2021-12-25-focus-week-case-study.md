+++
title = "Focus Week Case Study: Bringing E2E Tests into the CI Pipeline"
slug = "focus-week-case-study"
image = "/img/import/2021-12-25-focus-week-case-study.jpg"
date = 2021-12-25T12:34:00
publishDate = 2021-12-25T12:34:00
lastmod = 2024-01-08T06:35:52
description = "In this article I will share details about our last focus week and how it led to a breakthrough on a difficult topic."
tags = ["Case-Study","Collaboration","Culture","Ensemble-Programming","Team-Programming","Developer-Productivity","Engineering-Excellence"]
+++
# Focus Week Case Study: Bringing E2E Tests into the CI Pipeline

In my [last article](/blog/focus-weeks/), I wrote about focus weeks and how my team is currently doing them at BRYTER. Today, I want to share a case study of our latest focus week.

## Context [](/blog/focus-week-case-study/#context)

At BRYTER, we are using Selenium for automated E2E tests. Before our focus week, these were maintained by the QA team in a separate repository without any connection to the main code base. Most developers never had touched nor seen these tests. Before [we moved the responsibility for deployments from the QA team to the developing units](/blog/deployment-process-walls/), only the QA team really knew about them and how to execute them. Furthermore, the [unit on deployment rotation](/blog/deployment-process-walls/) was executing the tests manually. Often, those tests were slow and flaky.

When units began to do deployments, they realised, how annoying this is and demanded this to be changed as soon as possible. Changing this, requires work on four different areas.

* First, the tests need to be made stable. We see the responsibility for this in the cross-functional units, as they know best how the application should behave and can decide if flakiness is a problem on the test or the product side.
* Second, the tests need to be made fast. We already had the idea to run them in parallel, using AWS Lambda, so that the total test duration is the maximum duration of all tests, not the sum of them.
* Third, tests need to be moved closer to the production code so that they can easily be maintained by developers and QA people together, and we know which version of the test code should test which version of the system.
* Fourth, the E2E tests need to become part of the CI/CD pipeline.

While we saw the first two steps as some kind of requirement for the fourth step, we, tackled step two, three, and four in the Platform and Developer Experience unit during a focus week.

Up to that date, two colleagues, one from the QA team and one from another unit, who happened to have a lot of experience with AWS Lambda, tried to tackle this problem whenever both of them had some time left. After roughly six months in this working mode, a lot of initial work was already done, but we were still far away from “done done” and things became complex, and we had more questions than answers. Needless to say, nobody was happy with that situation and the two colleagues who initiated this project felt more and more pressure.

Therefore, we decided to do a focus week on this topic.

## Preparation of the focus week [](/blog/focus-week-case-study/#preparation-of-the-focus-week)

We scheduled the week for three weeks after we made the decision to have it, which gave us time to cancel our meetings, let people know, we will be unavailable during that week and prepare the Mural.

Together with our QA engineer, who was already involved in the project, I started to prepare the Mural and collect some tasks, that she saw between now and the success of the project.

Furthermore, we got access to the AWS Account that was used to set up the proof of concept for E2E test execution via AWS Lambda. Before the focus week, every test would be deployed as a separate Lambda containing the framework and the test code. Those lambdas would be triggered asynchronously via AWS SNS. They would then run the tests and store the results in a S3 bucket.

This infrastructure would be deployed using AWS CDK.

Some of the tasks we identified back then:

* Stabilising the tests
* Collecting results after the test runs
* Giving developers access to the test reports
* Making the tests run in the main pipeline
* Moving the test code to the main repository (stretch goal)
* Making the tests run against review apps (stretch goal)
* Use the test code of each commit to test that commit (stretch goal)

## The team [](/blog/focus-week-case-study/#the-team)

The team that participated in the focus week consisted of the QA engineer who already was involved in the project, three backend engineers and two frontend engineers. The infrastructure engineer on our team unfortunately could not attend because of other obligations.

Therefore, on day one, luckily also the other engineer who worked on this project before, joined us. He brought in a lot of valuable knowledge about AWS Lambda, AWS CDK and the current architecture and helped us to get up to speed.

Most of us had neither worked with AWS Lambda nor AWS CDK before.

## Day 1: Painfully slow, more questions than answers [](/blog/focus-week-case-study/#day-1-painfully-slow-more-questions-than-answers)

Honestly, day 1 did not feel very productive. We started with an introduction into the problem and the current approach that was already there:

* What worked already?
* What did not?
* Which challenges and questions are there to be solved?

The team was pretty silent. Everybody was quite overwhelmed by the many and new technologies and the number of questions that we could not answer yet.

I had moments, where I thought the focus week was a mistake and won’t get us anywhere. Oh gosh, was I wrong!

After the first moment of just being overwhelmed, we agreed to experiment with a simpler approach: What if we could run the Lambdas synchronously and obtain the results as a return value? What if we just could send the tests to be executed to the lambda?

If this would be possible, most of the tasks would become _trivial_. We decided to give it a try and to stay together as a team, until we know that this approach could work on the Lambda side. Therefore, we spent day one doing ensemble programming with the full team.

## Day 2: It worked! I wanted to split the team. [](/blog/focus-week-case-study/#day-2-it-worked-i-wanted-to-split-the-team)

We had the first success during this week. The simpler approach seemed to work. We were able to send and execute the tests synchronously. Furthermore, we got a summary about the results back. Yay!

But to this point, it was just a prototype. I felt the urge to split up into two groups: One to build the stable lambda worker and one to build the client that would utilise the Lambda to run all tests in parallel and gather the reports.

As a team, we decided not to split up yet, but to continue this day together, which was good in the end because it allowed us to learn more together.

## Day 3: We split. – So. Much. Progress! [](/blog/focus-week-case-study/#day-3-we-split--so-much-progress)

In the morning of day two, we pushed ourselves out of the comfort zone and split into two groups. Another backend developer and me would start to work on the client, while the three remaining team members, who participated in day three, would finish the Lambda code.

At the end of the day, we were all positively surprised: We finished the worker implementation, and most of the client-side code. We just wanted to clean up the reports in S3 and integrate the client into the pipeline.

At this point, we saw that we could achieve all of our (stretch) goals by the end of the week.

## Day 4: Moving the test code, updating documentation, finishing the client [](/blog/focus-week-case-study/#day-4-moving-the-test-code-updating-documentation-finishing-the-client)

On day 4, we continued in two groups. One would move the test code to the main repo, make sure that the tests could still be executed locally as well as in the Lambda, and updated the documentation accordingly.

The other group finished the client side and started to integrate the client into the CI pipeline.

## Day 5: Wrapping it up [](/blog/focus-week-case-study/#day-5-wrapping-it-up)

On day 5, only 3-4 of us were left, as the others started their weekend early. Thus, we continued all together to wrap up our work. Some parts still needed to be merged, and we improved the pipelines a bit.

Furthermore, we started to stabilise some tests already. We decided to just integrate the tests, that, we believed, were stable at that time. _(Spoiler: We learned, they were not as stable as we thought)_

## State after the focus week [](/blog/focus-week-case-study/#state-after-the-focus-week)

By the end of the week, we had a solid test framework that allowed us to run the E2E tests in parallel on our staging environment but also on review apps. Furthermore, the test code was part of the main repo. Therefore, units could now evolve the E2E tests while they were evolving the product, and we would always use the latests tests for the associated code.

The week was a massive success. In the following week, we started to record a couple of short videos clips in Slack to introduce other units to these changes and also created an overview of current E2E tests and their state (stable vs. flaky). Currently, units are working on stabilising tests for their area and add them to the pipeline.

After every merge to the main branch, we would automatically execute the tests and therefore reduce the number of tests, that need to be executed manually before deployments. Our goal, of course, is to fully get rid of manual test executions, which are the last manual step we are doing before deployments.

Because we were now executing these tests more often, we also learned that some of them were flakier than we had thought, but also that our application showed some weird behaviour (like super-long response times) from time to time.

Therefore, we were not only able to improve the test code, but the production code as well.

## Conclusion [](/blog/focus-week-case-study/#conclusion)

Just one week of focus enabled my team to create and own the test framework for test execution in the pipelines. Furthermore, we created a lot of value for the company and were able to crack a problem, that we were struggling with for a long time.

In the following weeks, we were learning from the feedback we were getting from the _production_ use of our solution. Moreover, we were improving the documentation and the framework itself, which was quite low effort, given that everybody knew how to do it.

Next time, we will probably limit focus weeks to only four days, as some of us do not work on Fridays, and it is just nice to finish the week together with a celebration on Thursday afternoons.

**Do you have similar experiences to share? I am curious to hear them in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**