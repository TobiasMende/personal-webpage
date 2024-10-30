+++
title = "Is &#8220;Not deploying on Fridays&#8221; an outdated practice?"
slug = "not-deploying-on-fridays-outdated-practice"
image = "/img/import/2022-07-09-not-deploying-on-fridays-outdated-practice.jpg"
date = 2022-07-09T13:25:00
publishDate = 2022-07-09T13:25:00
lastmod = 2024-01-08T06:37:34
description = "Is not to deploy on Fridays really that wise advice, that it used to be in the past? I would say \"No\"!"
tags = ["Continuous-Deployment","Culture","Practices","Developer-Productivity","Engineering-Excellence","Software-Craft"]
+++
# Is &#8220;Not deploying on Fridays&#8221; an outdated practice?

Every person working in a field somehow related to software development probably has heard the term “Don’t deploy on Fridays”. For years, I considered this as a wise recommendation.

However, I came to believe that this dogma is no longer true in a world of continuous deployments, feature toggles and instant rollbacks.

## Where does it come from? [](/blog/not-deploying-on-fridays-outdated-practice/#where-does-it-come-from)

Looking back, developers and operations engineers saw deployments as something dangerous. Something that has a serious risk and if it goes wrong, you are spending an entire weekend trying to fix the mess, your deployment has created.

Surely, nobody wants that. Thus, not deploying on Fridays seems like a reasonable rule of thumb. However, the type of deployments that were feared by software developers, operations engineers and everybody else in the company, stem from an entirely different era. They were fundamentally different to the type of deployments, we are doing today.

Deployments, in the past, were done manually and only when there were enough changes that justify the effort of deploying them by following such a tedious process. Thus, a deployment rarely just deployed one small change, but more likely days, weeks, or months of work. A giant potential for things to go wrong.

## Is it still relevant today? [](/blog/not-deploying-on-fridays-outdated-practice/#is-it-still-relevant-today)

Today, at least for modern companies, this looks vastly different. Every change is deployed more or less immediately. Thus, deployments are usually tiny and the likelihood of breaking things badly, is close to zero.

Furthermore, [release toggles](/blog/decoupling-deployments-and-releases/) and other mechanisms to decouple deployments and releases now belong to the standard developer know-how. Thus, most more significant changes do not change the behaviour of a system at deploy-time. This further reduces the risk of bad deployments.

This practices not only reduce the risk of breaking things, but also makes it fairly easy to fix things quickly, if something goes wrong. Typically, this is just a single click or maybe the revert of a single small change. Easy.

And of course because we are doing multiple deployments a day, they are something normal. No special event, no ceremony, no fuzz. They are something you do not even think about.

## You should deploy on Fridays, if you don’t like fixing bugs on Mondays. [](/blog/not-deploying-on-fridays-outdated-practice/#you-should-deploy-on-fridays-if-you-dont-like-fixing-bugs-on-mondays)

Not deploying on Fridays immediately throws us back into another era: The era of batch deployments, from which the fear of deployments came. But now, it is even worse:

If you do not deploy on Fridays, the first deployment on Monday will not be small at all, as you are deploying one day of work in a batch. Batch deployments are bad as they can break multiple things at once. And you can be sure, that on Monday most people will not immediately remember, what they did on Friday. Moreover, it is more difficult to figure out, which change broke things. Thus, resolving those issues will be more complicated.

## Not deploying on Fridays means higher risks for bugfixes. [](/blog/not-deploying-on-fridays-outdated-practice/#not-deploying-on-fridays-means-higher-risks-for-bugfixes)

If you are usually not deploying on Fridays, this makes it more risky if you _have to_ deploy something on Fridays. First, does this involve a special process different from the usual pipeline. Second of all, it also means that you either do some _git branch acrobatic_ or deploy all other changes alongside your fix.

All of this is more risky and stressful for developers than following the usual, well established process of deploying every change.

Even worse, if you have established a culture in which people believe that deployments on Fridays are something to refrain from, this creates negative pressure. Teams that need to fix a bug not only have to solve technical challenges, but also need to work towards getting the justification for an unplanned deployment on Fridays.

Moreover, there is the risk of deploy freezes to be abused. Let’s say, some developers want to make a change but are unsure how to do it safely without a deployment freeze (i.e., they wish to test it first on a staging system). They could just wait until Friday and merge it so that they have time until Monday to test it on the staging system without deploying it to production. This practice is incredibly dangerous. Firstly, it puts pressure on that team to stabilise or rollback that change before Monday. Second of all, if suddenly an urgent fix needs to be made on Friday, the unstable change might go to production earlier than anticipated.

Those unsafe practices might be covered by deploy freezes, where it would be better to find and apply safer practices instead.

## Going one step further: No deploy freezes ever. [](/blog/not-deploying-on-fridays-outdated-practice/#going-one-step-further-no-deploy-freezes-ever)

Therefore, the obvious solution is to get rid of deploy freezes all together – no deploy freezes on Fridays, Saturdays, Sundays or public holidays. This is the route we took at BRYTER recently.

When we were introducing [continuous deployments at BRYTER](/blog/continuous-deployment-for-the-entire-organisation/), we first introduced deploy freezes more for psychological safety than as a necessity. My team already anticipated, that we will get rid of them as soon as people got used to continuous deployments. Back then, many people extrapolated the known _risky_ deployments to 15 deployments a day. Unnecessary to say that this was not the reality.

Already 1-2 weeks into continuous deployments, people got used to deployments happening continuous and automatically. It was the new normal. People expected their changes to be live a couple of minutes after they were merged.

The deployment freezes in the late afternoons and on Fridays from noon on, caused confusion and frustration. So, as anticipated, we removed them.

This means, in theory, developers can now deploy changes during the night from Saturday to Sunday – If they want to work at that time and have somebody else to approve their changes.

Of course, this is not the reality at BRYTER. Usually, there is no activity in our repositories during weekends and thus, also no deployments are taking place, with or without deploy freeze.

## But what if I need to do a bigger, more risky change? [](/blog/not-deploying-on-fridays-outdated-practice/#but-what-if-i-need-to-do-a-bigger-more-risky-change)

Occasionally, there are changes that have a higher risk of going wrong, are harder to revert and cannot be deployed behind release toggles. — So it seems.

Foremost, it makes sense to challenge this assumption. Believing that there is a safer approach often helps you, to discover it. Even changes like major framework upgrades of a service can be done safely.

For example, you could deploy the old and the new version in parallel and just let the load balancer route traffic to the new instances. If things go wrong, you route all traffic to the old instances again.

**But what if it _really_ is not possible?**

Every so often, it is really not possible to do changes safely, or it is just too expensive to be reasonable. Upgrading a huge production database to the next version can be incredible hard to do safely on a copy of that database, where the changes need to be kept in sync.

For those changes, different rules may apply, but those changes are usually not done by automatic regular deployments but probably require a planned maintenance window (which usually means, somebody will stay up late at night on a weekend).

And if you discover other changes that seem too risky to be deployed on Fridays, it might be a good idea to wait until Monday and then discuss how to make them safer.

## Summary [](/blog/not-deploying-on-fridays-outdated-practice/#summary)

Not deploying on Fridays maybe made sense in a time, where deployments were rarely done and risky. In today’s world with continuous deployments, having artificial deploy freezes increases the risk of introducing defects that are hard to detect, locate and fix.

Removing the deployment freezes all together reduced the complexity of our deployment processes a lot. The simple rule is: If something is merged to the main branch, and you do not get any notifications about a failed pipeline, it goes to production roughly 10 minutes later.

I would certainly say, that “not deploying on Fridays” is indeed an outdated practice from the past.

**What are your thoughts about _deploying on Fridays_? How are you handling it in your company? Share your opinion here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**