+++
title = "There is no system like production: Why you should test in production"
slug = "testing-in-production"
image = "/img/import/2021-12-11-testing-in-production.jpg"
date = 2021-12-11T12:27:00
publishDate = 2021-12-11T12:27:00
lastmod = 2024-01-08T06:35:29
description = "If you do not test in production, your customers are the only ones, who do. While it sounds scary at first, testing in production is an important addition to pre-production quality assurance processes."
tags = ["Software-Development","Software-Testing","Developer-Productivity","Software-Craft"]
+++
# There is no system like production: Why you should test in production

![](https://unblocked.engineering/wp-content/uploads/2021/10/testing-in-production.jpg)

Shipping software without testing sounds scary. And this is also, what this article **is not** about. Organisations spend a lot of time and money to make sure that code is as much error-free as possible, when it reaches production and affects users.

Besides of a solid automated tests, this is often done by having staging and/or pre-production environments, where code is deployed and tested before it is deployed to production systems. This not only causes further delays in the deployment process, but also frequently fails to fulfil its purpose.

Even with configuration as code, it is impossible for two systems to be the same. Production systems might have more power, scale differently, or may even contain components that are absent in a staging environment. But even if all this is exactly the same, the data and the load in staging environments usually greatly differs from production systems. Thus, many problems will only occur in production.

* Database schema migrations that work fast enough on staging may take minutes on the production database, affecting hundreds or thousands of users.
* Cache hits and misses depend on usage patterns and therefore might be completely different between systems.
* Higher load, more concurrency, more connections, …

Furthermore, issues in a staging system are often treated as less serious than issues in production and therefore possibly make it to production.

Instead of spending time on keeping systems as similar as possible, we can take another path: We can test in production.

## Testing production does not mean not to test pre-production [](/blog/testing-in-production/#testing-production-does-not-mean-not-to-test-pre-production)

People frequently resist the idea of testing in production because they assume that it means not to test before production. But why not have both?

You should have a set of automated tests that give you a high certainty that your software works. But still, you can run some checks and tests in production that increase your confidence that it really works there. In theory, you can run these tests periodically to detect problems that might depend on time or system load.

Ideally, you have the possibility to roll out certain changes only to your test users or internal users first, without affecting all other users. [Release toggles can help you with this](/blog/decoupling-deployments-and-releases/).

At BRYTER, we would often roll out certain changes to internal tenants in production, where we can see how the changes behave in the real system. There we can test the changes and also get early feedback by internal users. If we encounter issues, we deactivate the change again and ship a fix with the next deployment.

## Do you still need staging? [](/blog/testing-in-production/#do-you-still-need-staging)

Having the ability to test in production could raise the question whether or not you still need a staging environment. The answer, of course, depends on many factors, such as the confidence that you have in the automated tests and other quality checks that run before production.

However, an interesting question to ask yourself is: What do I need staging for?

We are so used to have certain systems and stages in our pipelines in our processes, that we sometimes do not consider removing parts of them altogether.

Furthermore, having a staging system might lead your developers to test only there and never actually use the real system, leaving your customers as the only people to test your production environment.

## Should you always test in production? [](/blog/testing-in-production/#should-you-always-test-in-production)

Obviously, there are exceptions to every rule. First, only testing in production will probably do more harm than good. On the other hand, for most systems, I would rather optimise for a shorter deployment lead time than for a 100% test coverage.

Testing your system in every possible way and combination of inputs before it goes live can make sense, if the possible damage ist high and deployments are costly. When I was developing gas detection systems for Dräger, _deployments_ were done by technical support people visiting customers with USB sticks. Furthermore, systems where life-critical. Here, testing in production surely is not an option, given the cost of failure and our inability to see, what is going on in production.

In other environments, where the worst case was much less serious, I usually saw that the benefit of fast and frequent deployments outweighs the risk of shipping a bug.

## Conclusion [](/blog/testing-in-production/#conclusion)

No matter how good your pre-production quality assurances processes are, some problems will only occur in production. Besides having good processes how to react in these cases, it is also beneficial to be able to detect such issues quickly.

If you do not test in production, your customers are the only people who test your software under real conditions.

While monitoring and logging systems can help you to detect issues when they happen, testing in production can help you to surface them, before your customers do.

**Are you testing in production? What are your experiences? Share them here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**