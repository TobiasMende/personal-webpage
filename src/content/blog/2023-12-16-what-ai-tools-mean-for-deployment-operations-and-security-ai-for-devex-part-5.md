+++
title = "What AI Tools Mean for Deployment, Operations and Security (AI for DevEx, Part 5)"
slug = "what-ai-tools-mean-for-deployment-operations-and-security-ai-for-devex-part-5"
image = "/img/import/2023-12-16-what-ai-tools-mean-for-deployment-operations-and-security-ai-for-devex-part-5.png"
date = 2023-12-16T05:00:00
publishDate = 2023-12-16T05:00:00
lastmod = 2023-12-21T06:12:44
description = "Discover how AI tools are reshaping deployment, operations, and security in software development, as detailed in 'AI for DevEx, Part 5'. This article delves into the roles of AI in enhancing monitoring, vulnerability scanning, and error resolution, offering insights into the evolving landscape of AI in software engineering."
tags = ["AI-for DevEx","Artificial-Intelligence","Developer-Experience","Developer-Productivity"]
+++
# What AI Tools Mean for Deployment, Operations and Security (AI for DevEx, Part 5)

Welcome back to [AI for DevEx](/blog/tag/ai-for-devex/), Part 5\. In the last part, we explored how AI tools can [help us to improve our collaboration and communication](https://nudge.unblocked.engineering/p/how-ai-improves-collaboration-and). Today, we’re focusing on an often ignored aspect of software engineering: the importance of deployment, operation, monitoring, and security for teams that manage their software from creation to running it in production. Terms like DevOps, DevSecOps, and Dev<InsertAnyFunctionHere>Ops have been created to emphasize the need for teams to own their software completely.

With teams now handling software building, deployment, security, monitoring, and operation, they face more tools, languages, and complexities. This increases the cognitive load significantly. To address this, platform teams emerged. They create abstractions over complex, low-level details and make it easier to own the value stream without becoming a hindrance. Read “[A platform team for next-level developer experience](/blog/developer-experience-platform-team/)” to learn more.

The term “[AIOps](https://en.wikipedia.org/wiki/Artificial%5FIntelligence%5Ffor%5FIT%5FOperations)” was already coined by Gartner in 2016, and many AI tools have existed for a while. With recent advancements in the AI field, more tools were entering the market and existing ones got better.

Can artificial intelligence help us to further reduce the cognitive load in engineering for both, value-stream-aligned teams and platform teams? Let’s see:

## Deployment, Monitoring and Alerting

Many teams I have worked with were still watching logs during deployments to catch malfunctions. This is an error-prone, time-consuming, and boring approach to monitoring that we move away from quickly in almost all cases. Latest, when introducing continuous deployments, this approach becomes highly unpractical.

Automated monitoring for logs and traces and alerts for anomalies help detect issues. This is easy for obvious anomalies like unavailable health checks or a drastic increase in HTTP 500 errors. However, simple or percentage-based thresholds might not be enough for complex, dynamic applications.

Furthermore, this kind of monitoring and alerting only detects your anticipated errors.

Tools like [DataDog Watchdog](https://www.datadoghq.com/product/platform/watchdog/) and [new relic AI](https://newrelic.com/platform/applied-intelligence) can detect those unpredictable and hard-to-catch anomalies for years. These tools also help understand the root causes by putting logs, metrics, and deployments into context. Faster root cause identification often means faster recovery and reduced cognitive load.

Scaling incidents typically occur due to unexpected workloads. Even scalable applications might not scale quickly enough. For example, a containerized Spring Boot monolith might take a minute or two to start, or a Kubernetes cluster could run out of nodes, delaying new node provisioning. Predicting these issues in advance would be helpful.

Some companies predict upcoming traffic increases manually and over-provision their infrastructure upfront. Tools like [Federator.ai](https://prophetstor.com/federator%5Fai/) and [PredictKube](https://dysnix.com/predictkube) analyze historical data, predict upcoming workloads, and proactively scale the system.

To summarize, AI can help you understand your application’s behavior in production and make it more resilient, too.

## Vulnerability Scanning, Continuous Security Monitoring, Static Code Analysis

Speaking of monitoring, there is another important area where AI tools are tremendously helpful: Vulnerability scanning, security monitoring and static code analysis.

### Static Code Analysis and AI Code Reviews

Static code analysis is not new. Tools like [SonarQube](https://www.sonarsource.com/products/sonarqube/) have existed for decades. They provide simple rule-based guidance to avoid security issues in the code base or uphold certain quality standards.

New tools like [Metamob](https://metabob.com/) use AI to find and explain problems in code, like wrong library use or missed edge cases. They also scan for software security issues and check for known vulnerabilities.

### Vulnerability Scanning

[Snyk’s DeepCode AI](https://snyk.io/de/platform/deepcode-ai/), launched earlier this year, is an example of an AI model that is particularly trained to detect security vulnerabilities and suggest fixes directly in the IDE. It extends classic static analysis capabilities and dependency scanning with the ability to reason about the context in which code is written and can detect issues beyond simple pattern recognition.

Last month, [GitHub introduced its AI-powered application security testing](https://github.blog/2023-11-08-ai-powered-appsec/): GitHub Advanced Security. This solution scans code and provides AI-generated fixes that can be applied during pull-request reviews.

### Continuous Security Monitoring

Monitoring is not only relevant for early incident detection. It also plays a role in detecting potential security threats and anomalies in usage patterns. The exact patterns to look for are often unknown. Furthermore, the increasing amount of data to look into and the number of systems to observe make this even harder. 

Like classical monitoring, the challenge is to separate normal dynamic changes from anomalies and keep the false positives as low as possible while not missing any true positives.

Furthermore, AI-enhanced continuous security monitoring solutions cannot only detect threats better, but also suggest potential remediations.

## Debugging and Understanding Errors

Another considerable time sink for engineers can be debugging and understanding errors (good unit tests can help 😉). 

Today, tools like GitHub Copilot, ChatGPT, and [Jetbrains AI](https://www.jetbrains.com/ai/), the newest kid on the block, can explain code and error messages. CI/CD platforms like [CircleCI](https://circleci.com/) now have an “Explain this error” button to give a quick AI-generated explanation of an error and how to fix it. 

![In CircleCI, AI-support is just a click of a button away.](/img/import/2023-12-circleci-explain-this-error.png)

In CircleCI, AI-support is just a click of a button away.

## On Tool to Rule Them All?

The landscape of AI tooling that supports the software development lifecycle is huge. There isn’t that one tool for all the needs, and we can expect a lot of movement in the market in the upcoming years. 

It is an interesting space that I am observing with excitement and curiosity. Just this week, I discovered [GitLab Duo](https://about.gitlab.com/gitlab-duo/) which promises to become the suite to support engineers throughout their workflow (on the GitLab platform). Currently, [most capabilities](https://docs.gitlab.com/ee/user/ai%5Ffeatures.html) are in the Experiment stage and only available to enterprise customers, but it shows the potential and what we can expect soon.

## Conclusion

AI tools significantly transform software development, particularly in deployment, operations, and security. These tools enhance our ability to monitor applications and preemptively address potential issues, thereby streamlining operations.

In security, AI-driven tools like Snyk’s DeepCode AI and GitHub’s application security testing are revolutionizing vulnerability scanning and static code analysis. They efficiently identify security flaws and suggest remedies, fortifying the code against potential threats.

Additionally, as seen in GitHub Copilot and ChatGPT, AI debugging and error resolution assistance are invaluable. These tools provide insightful explanations and solutions, greatly reducing the time spent on troubleshooting.

AI is changing software development and operations by making them more efficient, secure, and simpler. As AI tools improve, they will greatly change how software is developed and operated.

**How are you using AI during deployment, operations, and for improving security? Let us know in the comments! 💬👇**