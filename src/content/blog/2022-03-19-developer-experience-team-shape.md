+++
title = "Shaping developer experience teams for autonomy"
slug = "developer-experience-team-shape"
image = "/img/import/2022-03-19-developer-experience-team-shape.jpg"
date = 2022-03-19T13:08:00
publishDate = 2022-03-19T13:08:00
lastmod = 2024-01-08T06:36:49
description = "Once you have decided, that a developer experience team would provide value to your organisation, the question is, how such a team should be set up, how it should be shaped, and how it should interact with other teams."
tags = ["Team-Topologies","Developer-Productivity","Organizational-Design"]
+++
# Shaping developer experience teams for autonomy

Once you have decided, that a developer experience team would provide value to your organisation, the question is, how such a team should be set up, how it should be shaped, and how it should interact with other teams.

## Autonomy and independence are key! [](/blog/developer-experience-team-shape/#autonomy-and-independence-are-key)

When we started our developer experience team at BRYTER roughly a year ago, it was clear to us, that such a team, like most other teams, should have a high level of autonomy and independence. The team should be able to decide more or less freely what to work on and when. Furthermore, the team must be able to do so without needing too much support from other teams, such as an infrastructure team, for example.

At BRYTER, we work under the assumption that people closest to a certain area know best about that specific area. Thus, we do not tell teams top-down what they are supposed to work on, but teams figure this out on their own. This leads to a high level of autonomy for teams to make the best decisions they can and get feedback in short cycles.1

A high level of team-autonomy can only work, if teams are also independent. This means, that they do not depend on other teams or individuals to get their work done. Dependence almost always creates the need for alignment and synchronisation, and thus negatively affects the autonomy of both parties.

With that in mind, the most sensible choice was, to set up the team cross-functionally. And this is, what we also did with the developer experience team.

## A cross-functional developer experience team [](/blog/developer-experience-team-shape/#a-cross-functional-developer-experience-team)

Our goal was, to build a team that can tackle _every_ problem for developer experience, no matter, where it sits. This can be an issue in the frontend build, the backend architecture, tooling, the continuous integration infrastructure, the deployment process or monitoring systems.

The technological landscape in such a team can be much bigger than the one of a normal software development team. This is even more true, if your company only has one team for the _entire_ developer experience within the company.

As it is highly unlikely to find many individuals that are advanced in all those technologies, it makes sense to have different experts on the team who can provide profound knowledge about different areas. In our case, we started with two frontend engineers, four backend engineers, one QA engineer and one infrastructure engineer on that team. We decided to start without a dedicated technical product manager back then, having one of us (me in this case) taking over the product leadership and tech leadership responsibilities. This worked good enough to start like this, as our _product_ is targeting developers and thus is a highly technical product. However, as the team grows and takes on more responsibilities, a dedicated TPM might be a valuable addition to this team.

## How to recruit for a developer experience team [](/blog/developer-experience-team-shape/#how-to-recruit-for-a-developer-experience-team)

### Starting with internal recruitment [](/blog/developer-experience-team-shape/#starting-with-internal-recruitment)

We formed the initial team by “recruiting” engineers from other teams internally. This had huge advantages. First, those people were already onboarded to BRYTER and our culture. Second, they also had connections within the company. Third, they knew the pain points, as they have experienced them first-hand.

This lead to a cross-functional developer experience team of highly motivated people with tons of ideas which areas needed improvements. Furthermore, as all engineers were known in the company already, we also had a certain standing that helped us to tackle some topics that required closer collaboration with other teams.

Later on, we then extended the team with external new joiners, which worked very well, too.

### Looking for a _slightly_ different skill-set [](/blog/developer-experience-team-shape/#looking-for-a-%5Fslightly%5F-different-skill-set)

During the last year, we learned that we require a _slightly_ different skillsets than _normal_ backend or frontend engineers might have. While these skillsets are definitely very beneficial, they are not enough. Many of our “construction sides” are around tooling, CI pipelines or other more _peripheral_ topics where many developers do not have deep knowledge or understanding.

Furthermore, our work is very different from the normal product feature development, that is done in value-stream aligned teams.

Thus, it is important to find engineers who enjoy this kind of work and are okay with going out of their comfort zone and stepping into unknown areas frequently.

## Educating the team [](/blog/developer-experience-team-shape/#educating-the-team)

Given the variety of topics and technologies, it cannot be expected that there always is an expert for every topic on that team. We sometimes discover parts of our tech ecosystem, that we did not know (much) about but needed to acquire knowledge about to get our job done.

We take those discoveries as an opportunity to build knowledge within the team. Either by collaboratively exploring that technology and gaining hands-on experience, or by getting some training for a dedicated technology.

Currently, for example, we realised that we would benefit from more Kubernetes knowledge to depend less on the infrastructure team. Therefore, we decided that a couple of our team members participate in a training for that technology and can then bring this knowledge into the team.

Apart from attending trainings, collaboration is one of the greatest approaches to facilitate learning and knowledge transfer. Furthermore, it is also great for the team dynamics, too.

In our team, we have dedicated blockers for collaboration time and will also reach out to each other for ad-hoc collaboration sessions. Furthermore, we achieved great results by utilizing [focus weeks](/blog/focus-weeks/) for topics, where knowledge was scarce and uncertainty was high.

## The scope of a developer experience team [](/blog/developer-experience-team-shape/#the-scope-of-a-developer-experience-team)

Given that we only have one team around developer experience, it was pretty clear to us, that all topics that affect developer experience potentially belong to that team. However, not all topics are equally important and also cannot be acquired all at the same time, as knowledge needs to be built up as well.

Thus, we started with the most important topics and are slowly extending the scope as topics are acquired and brought under control and into manageable complexity.

What we learned is, that in our context, the work of our team must entail both, tooling and platform development. This has at least three reasons:

First, many developer experience issues are related to some technical issues in the product, such as an architecture that screws up build parallelization. Second, some topics benefit from implementing necessary changes in the platform directly. When we introduced [release toggles](/blog/decoupling-deployments-and-releases/), we not only introduced the system and documentation around it but also provided abstractions that can be used in the code to utilize those toggles. Third, also working on the platform makes sure that we are constantly dogfooding our changes. When we restructure the CI pipelines, we directly experience this change and therefore get feedback faster compared to waiting for feedback from other teams.

## Be engaged with other teams [](/blog/developer-experience-team-shape/#be-engaged-with-other-teams)

As a developer experience team, it is crucial to always keep the connection to the other teams, as they are essentially your customers. It is important to frequently get their feedback and even work with them to see where they currently face challenges related to developer experience.

There are many ways how this can be done, which will exceed the scope of this article. My [next article](/blog/developer-experience-team-interaction-modes/) about interaction modes of a developer experience team will be dedicated to this topic.

## Summary [](/blog/developer-experience-team-shape/#summary)

As product development teams, developer experience teams should also be shaped cross-functional and geared towards a high level of autonomy and independence. However, their work is different and might require more in-depth knowledge in areas where many engineers might not have extensive knowledge or experience. Thus, training can be even more essential in such a team.

**How is your developer experience team structured? Share your thoughts here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**

---

1. Of course, autonomy only works to a given extent. There still is some guidance about the desired direction of the company and some alignment between teams on the larger goals.