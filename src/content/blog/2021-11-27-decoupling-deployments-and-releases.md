+++
title = "Crucial developer practices: Decoupling deployments and releases"
slug = "decoupling-deployments-and-releases"
image = "/img/import/2021-11-27-decoupling-deployments-and-releases.jpg"
date = 2021-11-27T12:02:00
publishDate = 2021-11-27T12:02:00
lastmod = 2024-01-08T06:46:36
description = "Decoupling deployments and releases gives you a better control about when system changes are made available to users and can help you to avoid complicated rollback processes in case, things go wrong."
tags = ["Continuous-Deployment","Software-Development","Software-Craft"]
+++
# Crucial developer practices: Decoupling deployments and releases

When systems are small and the risk of introducing defects when changing its behaviour is low, these changes can happen during deployment. However, when systems grow, the behaviour becomes more complex and more people are working on the system, it is essential to decouple behaviour changes, the releases, from deployments.

In other words, developers should be able to commit code to the mainline at any time, while not blocking deployments by doing so. Deployments need to be possible at any given time. Thus, it is essential to introduce feature branching techniques that enable developers to integrate code often without changing the behaviour.

One of those techniques is **release toggles**. Release toggles allow developers to modify the behaviour at runtime and not at deployment time. Utilising this technique can be powerful because it allows developers to gradually rollout behaviour changes, to softly roll them back if something goes wrong and even to test in production without breaking anything.

Furthermore, using release toggles to guard and control changes to the system behaviour is one of the essential practices that enable _save_ continuous deployments.

Release toggles are often also called feature flags, or are seen as a subset of feature flags1. In this article, I will only focus on **release toggles**. These are transient feature flags that only live until a feature is completely rolled out and proven to be stable in production. Usually, these kinds of toggles are controlled by developers and thus enable them, to decouple deployments and releases.

## Requirements towards release toggles [](/blog/decoupling-deployments-and-releases/#requirements-towards-release-toggles)

According to my experience, there are certain requirements, that release toggles need to satisfy to be really helpful:

1. **They need to be controllable by developers.** Developers, or more specifically the units that develop the system, [should be responsible for deployments](/blog/deployment-process-walls/), but also for rolling out changes to the users. Thus, they must be controlling deployments and releases. This is the only way to avoid depending on another team for rolling out and testing changes in production. Furthermore, only developers usually know how to detect early, when things go wrong.
2. **They need to be controllable at runtime.** You want your release toggles to change behaviour at runtime, that is, without restarting the application. This is important to react fast in case you need to roll back a change. Furthermore, it usually allows for more fine-grained control.
3. **They should be fine-grained.** It has proven to be really beneficial, if you can roll out changes gradually and not to the entire user-base at once. This allows you, to roll out changes to internal users or internal systems first, then maybe to some well-meaning early adopters and finally to the most critical customers you have.
4. **They must be easy to use.** It must be straightforward (and cheap) for developers to add new release toggles, when they need them. Otherwise, developers might just _wing it_ because they feel that the risk of making failures is lower than the cost of properly guarding the releases by toggles.
5. **They should be short-lived.** Branches in software increase its complexity. Complexity complicates maintenance and testing. Therefore, developers should aim to keep complexity low. For release toggles, this means to only keep them for a short time and remove them (and the dead code behind them) as soon as there is sufficient confidence, that the change works well in all production systems. Furthermore, hiding a massive implementation behind a release toggles also interrupts the value-flow and delays real customer feedback.

## How to implement release toggles [](/blog/decoupling-deployments-and-releases/#how-to-implement-release-toggles)

There are various frameworks, tools, and SDKs that can help you to implement release toggles such as [Unleash](https://docs.getunleash.io/), [Gitlab Feature Flags](https://docs.gitlab.com/ee/operations/feature%5Fflags.html) and even SaaS products such as [LaunchDarkly](https://launchdarkly.com/) that come with various feature sets. Thus, it makes sense to evaluate your requirements first, before deciding for a solution.

From a code-perspective, it doesn’t really matter, which solution you are using, and it is best to hide this implementation detail from the majority of developers. Using a release toggle in code should be as easy as writing something like:

```
class VacationService(private val releaseToggles: ReleaseToggles) {
  fun calculateRemainingVacationDays(...) = if(releaseToggles.isEnabled("fast-vacation-calculation-algorithm") {
    calculateRemainingVacationDaysWithOptimizedAlgorithm(...)    
  } else {
    calculateRemainingVacationDaysWithLegacyAlgorithm(...)
  }

  private fun calculateRemainingVacationDaysWithOptimizedAlgorithm(...) { ... }

  private fun calculateRemainingVacationDaysWithLegacyAlgorithm(...) { ... }
}
```

However, the way of defining and controlling new release toggles and also how fine-grained the control is, can differ widely between frameworks.

### How we implemented release toggles at BRYTER [](/blog/decoupling-deployments-and-releases/#how-we-implemented-release-toggles-at-bryter)

At BRYTER, we decided to introduce release toggles by utilising Gitlab Feature Flags and Unleash. GitLab Feature Flags implement the Unleash API and thus can be used via the Unleash SDK. The SDK takes care of caching the release toggle configuration, handling save fallbacks and the like.

Furthermore, all our developers already have access to GitLab Feature Flags, and we can use them without any additional charge as it is available in all Gitlab Tiers. While we might change the framework and tools that we are using for release toggles in the future, using GitLab Feature Flags required very little effort from our side. Therefore, we did not need to introduce some entirely new tools or services.

GitLab allows us to control release toggles by environment and also by users. What environments and users are depends on the context and what kind of information you send from the Unleash SDK to the GitLab API. In our case, environments map to Gitlab Environments, which refer to different instances of our system. That is, there is one environment for each VPC and each review app. This allows us to roll out release only to some environments without affecting others.

Furthermore, as we are developing a multi-tenant SaaS product, we decided to use the concept of _users_ for _tenants_. This allows us to roll out release only to certain tenants (i.e., internal or beta tenants first). This provides us with a level of control that is good enough for now and satisfies all the five requirements of the previous section.

### Limitations of Gitlab Feature Flags at BRYTER [](/blog/decoupling-deployments-and-releases/#limitations-of-gitlab-feature-flags-at-bryter)

While Gitlab Feature Flags are a great way for us to introduce release toggling capabilities into our system, they come with some limitations in our context.

1. **Availability of the API:** As with every external system, you cannot assume, that it is always available. Thus, it is important to have reasonable fallbacks. Sporadically, it happens, that the GitLab API is not available and thus release toggle configuration cannot be fetched. You definitely don’t want your system to fail in that case. Thus, it is crucial, that the clients of such an API know about a save state for every release toggle and thus can fall back to it, if they cannot determine the current state of a toggle. Fortunately, Unleash comes with the ability to handle graceful fallbacks.
2. **Concepts and Naming:** While the GitLab/Unleash concept of _environments_ works well for us because we are also using GitLab environments for those, the concept of _users_ does not work well in our context. For us, it is less important and even not feasible to differentiate the behaviour by users of our system. Instead, it is more important to differentiate by _tenants_. Thus, we are using the concept of _users_ to map our _tenants_. Furthermore, our platform also knows the concept of _feature flags_ as a means for customer success managers and sales people to tailor tenant capabilities to the needs and licensing of our customers2. Thus, using _GitLab Feature Flags_ as means to map only _developer controlled release toggles_, is another cause for confusion.

## Adopting release toggles [](/blog/decoupling-deployments-and-releases/#adopting-release-toggles)

With release toggles being a new capability in our system, we are still in the phase of learning and educating developers about them and about the why and how of using them.

This is an important culture shift, that needs to happen to reap the full benefits of release toggles, which is, to allow painless, fast and save deployments in an environment with shared deployment artefacts. It enables us to safely fix-forward instead of rolling back entire deployments that might entail changes of various units/developers.

The adoption is slowly growing as we see the first success stories about these toggles within the company. However, a lot of internal marketing (mainly by the Platform and Developer Experience Unit) is required to help other units to adopt this style of working. In the past, releases happened with deployments or were guarded by the same mechanism used by customer success managers to control feature configurations. Both approaches lead to unwanted behaviour in production, and it was a matter of luck and fast reaction of our development units, that nothing bad happened. However, we should not rely on this Therefore, we are transitioning to a saver approach, release toggles.

## When not to use release toggles? [](/blog/decoupling-deployments-and-releases/#when-not-to-use-release-toggles)

Release toggles are a great tool, and every developer should know how to use and control them. However, they are not a silver bullet and should not be used, no matter, what.

They are good for guarding new features that would be used automatically by users and for refactorings, that should not change the system behaviour. This allows us to do the refactoring or the rewrite of a system part in parallel without affecting users in case of accidental behaviour changes.

On the other hand, there are some scenarios where release toggles usually have little value or are just overkill. Such a scenario can be, when introducing a new API that is neither known nor used by anybody yet. Given, that this API is sufficiently secured, it might be okay, if it can be called by people who know about it, as these people usually also know about the limitations of this API.

Moreover, when doing cross-cutting changes such as exchanging a framework or upgrading some dependencies, it can be very difficult to guard these changes with release toggles. Here, test systems like a staging environment and a set of solid end-to-end test are often the cheaper and better approach to ensure, that these updates do not break the system.

## Conclusion [](/blog/decoupling-deployments-and-releases/#conclusion)

Feature branching and release toggles are important concepts every developer should know about and consider when approaching a change of any kind of system. Used correctly, the help us to avoid negative impact to customers, unplanned work for developers and stressful situations.

Often, instead of emergency fixes and deployments, we would now just deactivate a release, if we find that it causes some troubles. This gives us the ability to reason about the right way to fix it without high pressure. Usually, this leads to much better solutions, happier developers and happier customers.

If you are interested to read more about this topic, I can only recommend [this article](https://martinfowler.com/articles/feature-toggles.html) in Martin Fowlers Blog, again.

**Are you using release toggles in your company? I would love to hear your experiences with them here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**

---

1. See [this excellent article](https://martinfowler.com/articles/feature-toggles.html) by Pete Hodgson on Martin Fowlers blog. In this article, the author describes different categories of feature flags and why and how to use them.
2. Those feature flags are part of the product, are long-lived, and should only be managed by customer success managers. Usually, they do so, when they deem a certain feature as beneficial for a tenant or when the licence, a tenant buys, includes a certain feature. Thus, things behind such feature flags are supposed to be stable features that one tenant has access to and another has not.