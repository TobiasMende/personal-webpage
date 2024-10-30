+++
title = "How BRYTER Achieved Increased Developer Experience, Ownership, Product Quality, and Engineering Effectiveness through Continuous Deployments"
slug = "how-bryter-achieved-increased-developer-experience-ownership-product-quality-and-engineering-effectiveness-through-continuous-deployments"
image = "/img/import/2023-09-22-how-bryter-achieved-increased-developer-experience-ownership-product-quality-and-engineering-effectiveness-through-continuous-deployments.jpg"
date = 2023-09-22T08:00:00
publishDate = 2023-09-22T08:00:00
lastmod = 2024-03-22T07:45:22
description = "BRYTER, a German LegalTech company, improved how they update their software by moving to continuous deployments. This change allowed them to make updates faster, improve their software quality, and give their teams more control and understanding of the process. As a result, they saw fewer problems and could fix issues quicker."
tags = ["Case-Study","Continuous-Deployment","Developer-Experience","Developer-Productivity","Leadership","Practices","Psychological-Safety","Technical-Leadership","Engineering-Excellence"]
+++
# How BRYTER Achieved Increased Developer Experience, Ownership, Product Quality, and Engineering Effectiveness through Continuous Deployments

BRYTER, a German LegalTech scale-up, faced challenges with its monolithic deployment process and limited understanding of the deployment process within its engineering teams. Deployments occurred only twice a week and were managed by the QA team, leading to a lack of visibility and ownership among the other teams. 

This case study explores how BRYTER overcame these challenges through a journey toward continuous deployments, resulting in increased developer experience, ownership, product quality, and engineering effectiveness.

## The Challenge

BRYTER’s engineering teams faced several challenges related to the deployment process:

1. **Limited Understanding:** Engineering teams lacked knowledge about the deployment process and the steps involved in getting a deployment live.
2. **Lack of Visibility:** With deployments occurring only twice a week, numerous changes from different teams were bundled together, leading to confusion about which changes were going live.
3. **QA Team Inefficiency:** The QA team spent a significant amount of time on deployments, leaving little room for process improvement. Additionally, they lacked the expertise to make meaningful changes to the deployment process.
4. **Ownership and Testing Challenges:** Engineering teams did not fully understand the end-to-end (E2E) tests and felt unqualified to take ownership of them. The existing tests were complex, involving multiple teams and making it difficult for individual teams to understand and own them.
5. **Technological Barrier:** The chosen technology for E2E tests (Python/Selenium) posed a barrier for adoption among engineering teams, who were more familiar with TypeScript, Node, and Kotlin.
6. **Lack of Problem-Solving:** Neither the engineering nor the QA teams were able to independently address the issues surrounding the testing and deployment process.
7. **Limited Resilience:** Engineering teams recognized that deployments were difficult and often led to incidents but lacked an understanding of why and how they could contribute to improving resilience.
8. **Resistance to Change:** Some team members were skeptical about adopting continuous deployments and concerned about the potential risks and impact on the system.

## The Solution

To overcome these challenges, BRYTER implemented several measures:

1. **Developer Experience Team:** A dedicated Developer Experience Team was created with the objective of improving the deployment process and fostering ownership within the engineering teams.
2. **Deployment Rotation:** A deployment rotation was introduced, whereby each week a different team would be responsible for the deployments while the QA team supervised the process. This allowed the product teams to learn about the deployment process and generate ideas for improvement.
3. **Retrospectives and Vision Setting:** Weekly retrospectives were held to gather feedback from the teams on the deployment rotation and identify areas for improvement. The Developer Experience Team also presented a vision of fast and seamless deployments to generate excitement and a desire to contribute among the engineering teams.
4. **Test Review and Migration:** Existing E2E tests were reviewed, and the number of tests was reduced, focusing on areas where insufficient testing existed at other levels. Additionally, the Python Selenium tests were migrated to TypeScript Playwright tests, making them faster, more robust, and accessible to teams familiar with TypeScript.
5. **Ownership of E2E Tests:** Engineering teams were encouraged to take ownership of the E2E tests, allowing them to remove or change tests within their product areas as needed.
6. **Streamlining the Release Process:** Changelog creation for every deployment was eliminated, replacing it with monthly updates that were sufficient for stakeholders. The deployment process was stabilized, accelerated, and automated, reducing the pipeline lead time from over an hour to approximately 10 minutes.
7. **Release Toggles and Dark Launching:** Release toggles were introduced, enabling dark launches of new features and gradual rollout. This decoupled deployments and releases, allowing easy rollbacks without impacting the deployment process.
8. **Monitoring and Alerting:** Monitoring and alerting capabilities were enhanced, providing real-time notifications in the event of any issues or malfunctions.

## Results

The implementation of continuous deployments yielded various positive outcomes:

1. **Faster Deployment and Change Delivery:** Every change went live when the pipeline was green, allowing teams to push multiple deployments within hours rather than weeks.
2. **Efficient Deployments:** Deployments occurred within minutes instead of days, becoming a routine process that did not require much attention.
3. **Reduced Incidents and Faster Recovery:** More frequent deployments with smaller changes resulted in a decrease in the change failure rate. The mean time to recovery was significantly reduced from hours to minutes, as most changes could be undone by toggling releases.
4. **Improved Product Quality:** Ownership and understanding of the product increased across teams, leading to better overall product quality. Teams added the appropriate level of tests to ensure their software was working effectively.
5. **Agile Refactoring:** The increased speed of deployments enabled teams to complete complex refactoring tasks, such as renaming database columns or migrating data, in a shorter time span.
6. **Overcoming Skepticism:** Continuous deployments were successful, addressing the initial skepticism and fears of team members. The controlled deployment process and ability to switch release toggles instilled confidence in the teams.
7. **Enabling QA Team:** The QA team was able to shift focus from deployments to supporting product teams in areas such as understanding edge cases, writing tests, and exploring performance testing options.

## Lessons Learned

BRYTER’s journey to continuous deployments taught valuable lessons:

1. **Eliminating Handovers:** Improving deployment and development processes requires removing handovers and involving teams directly in the deployment process.
2. **Experiencing Deployments:** Allowing product teams to experience and contribute to the deployment process helps build a better understanding and ownership.
3. **Safer Deployment Process:** Making the deployment process safer and less error-prone helps alleviate the perception of risk and uncertainty associated with deployments.
4. **Dedicated Team:** A dedicated team focused on improving developer experience and deployment processes is crucial for achieving significant and long-term progress.
5. **Crafting a Vision:** Communicating a strong vision of the benefits of continuous deployments helps generate excitement and understanding among the teams.

## Conclusion

BRYTER’s adoption of continuous deployments resulted in increased developer experience, ownership, product quality, and engineering effectiveness. 

By removing the burden of manual deployments, teams were able to deliver changes faster, with more confidence, and with minimal manual interactions. Continuous deployments also enabled rapid product experimentation and facilitated continuous refactoring. 

Founding the Developer Experience Team played a pivotal role in the successful implementation of continuous deployments. 

Overall, continuous deployments improved the efficiency and effectiveness of BRYTER’s engineering teams, enabling them to deliver high-quality software at an accelerated pace.

## Additional Resources

In 2023, I gave a brief talk about BRYTER’s journey toward continuous deployments during the Skill UP Days CI/CD (online). You can find the recording and the slides below.

The recording The slides 

[The journey to continuous deployment\_ Transforming technology, culture, and mindset](https://unblocked.engineering/wp-content/uploads/2023/04/The-journey-to-continuous-deployment%5F-Transforming-technology-culture-and-mindset.pdf)[Download](https://unblocked.engineering/wp-content/uploads/2023/04/The-journey-to-continuous-deployment%5F-Transforming-technology-culture-and-mindset.pdf)