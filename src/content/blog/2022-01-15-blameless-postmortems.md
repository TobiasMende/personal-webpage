+++
title = "Blameless Post-Mortems: Incidents are a learning opportunity"
slug = "blameless-postmortems"
image = "/img/import/2022-01-15-blameless-postmortems.jpg"
date = 2022-01-15T12:42:00
publishDate = 2022-01-15T12:42:00
lastmod = 2024-01-08T06:36:18
description = "Blameless post-mortems are an effective tool to facilitate learning from failures, to share knowledge and to significantly improve the entire system, including software, infrastructure, and processes."
tags = ["Culture","Practices","Psychological-Safety","Engineering-Excellence","Software-Craft"]
+++
# Blameless Post-Mortems: Incidents are a learning opportunity

Blameless post-mortems are an effective tool to facilitate learning from failures, to share knowledge and to significantly improve the entire system, including software, infrastructure, and processes.

In software development, failure is inevitable. Sooner or later, something will go wrong, no matter how good your processes, your automated tests or your people are. The question is not, if failures happen, but when and what you will do with them.

If you do it right, incidents are a huge learning opportunity that can bring your engineering organisation to the next level. In this article, I will describe, how blameless post-mortems can help you to grow a culture of continuous learning and improving.

## What is a post-mortem? [](/blog/blameless-postmortems/#what-is-a-post-mortem)

In medicine, “post-mortem” (Latin for “after-dead”) refers to an autopsy that is conducted after somebody dies to learn more about the causes.

Similarly, in software development and DevOps, a post-mortem is an analysis of an incident or system failure, after this failure occurred. Usually, a post-mortem is conducted after the immediate problem is solved or mitigated.

It is done by the people who were involved in the incident response or could contribute information for other reasons. During the post-mortem, this group of people would figure out what went wrong, how and why.

The goal is, to focus on **process failures**, not on **personal failures**.

## Blameless is important [](/blog/blameless-postmortems/#blameless-is-important)

If you want to build a healthy organisation, you must build a culture based on trust, not on blame and fear.

Blaming or punishing people for something, that went wrong, is easy. Moreover, it is incredibly harmful. People who are afraid that they might be blamed or punished for something they did, are much less likely to openly communicate this. However, if somebody thinks they might have made a mistake, you want them to raise this as early as possible. This will help to discover and address the problem rather sooner than later.

Furthermore, blaming will stop solution-seeking. “We found the guilty person, let’s move on with business.” — However, there is no such thing as a guilty person. Maybe, somebody made a mistake that contributed to a system failure. But, if a single mistake of an individual can fail your system, that is the real issue.

For this and other reasons, it is important not to blame people but to encourage them to share what happened, why it did happen and what we could learn from it.

## How to prepare a post-mortem [](/blog/blameless-postmortems/#how-to-prepare-a-post-mortem)

Right after the incident is solved, and the stressful situation is over, the people who were involved in solving the incident should collect all the facts around it.

Here, we are interested in the series of events, that have happened and how they were discovered.

* How did we become aware, that there is an issue?
* What was the impact of this issue?
* What was the series of events, that lead to the failure?
* How and when was it solved?

It is immediately useful to add all kinds of information, links and what not to these events. These could be log outputs, merge requests, CI pipeline executions, Slack messages, metrics.

Next, there should be a meeting with all people who were somehow involved in this incident and could contribute ideas and information. This meeting should be shortly after the incident, so that memories are still fresh. Usually, we try to have a post-mortem within a week after the incident. It can make sense to openly announce the post-mortem in the company, so that others know when it happens and can join, if they feel they could contribute.

## During the post-mortem [](/blog/blameless-postmortems/#during-the-post-mortem)

We start the post-mortem as every other meeting with a check-in, where everybody can share how they arrive and feel. This gives us time to arrive, connect and be present in the conversation.

Thereafter, we would review the series of events around the incident, which we documented right after the incident. Even though everybody should have access to this document before the post-mortem, this step makes sure that everybody is on the same page. Furthermore, it gives participants the opportunity to ask questions and add information that might be missing.

From all these details, we would boil down a summary of why it went wrong. Moreover, we would collect “lessons learned”:

* What helped us?
* What slowed us down?
* What could we have done differently?
* What knowledge did we not have before the incident, but have now?

During post-mortems, we try not to jump to solutions too quickly, but make sure that we understand the incident well enough first and stay focused on facts before we jump to finding solutions and actions.

Subsequently, we are searching for measures that would help to prevent similar incidents. We collect specific actions that have somebody attached, who is responsible for their execution.

We end the session with a check-out.

## Beware of overreacting [](/blog/blameless-postmortems/#beware-of-overreacting)

When seeking for actions to prevent similar incidents in the future, it is important to not forget the cost of action and put it into relation with the incident costs. Furthermore, we need to be careful not to find too-easy solutions.

If, for example, an automatic deployment to a production system caused the issue, an _obvious_ solution might be switching to manual deployments or introducing other manual gates. However, if you have automatic tests, a staging environment and a review process in place, the question should rather be, why all these measures did not prevent the incident. Then we can go from there and maybe increase what we can test automatically.

If only one in a hundred deployments causes an issue, forcing all deployments to be manual, would be a huge cost and slow down. It still might not prevent similar incidents to happen again. Just patching a broken process will lead to a more complex (and potentially more broken) process.

The goal of a post-mortem is not to prevent all possible incidents that might happen in the future, but to make sure that incidents are less likely after the measures were implemented, than before.

Furthermore, implementing complicated and extremely specific measures for an issue that just occurred once might lead to a complication of the process. Those measures provide no value, as the fix is too specific to a problem that is unlikely to happen ever again.

## When to do post-mortems [](/blog/blameless-postmortems/#when-to-do-post-mortems)

Always. Whenever a change to the system lead to a degraded experience for its users or caused stress or distraction for engineers or other stakeholders, a post-mortem can be beneficial.

If we have too many conditions whether to do a post-mortem, we might end up not doing them because we might think, the issue is too trivial or the solution too obvious.

Blameless post-mortems should become a habit for you and your team without many conditions. As with retrospectives, you only know what they bring you, when you do them. And you would also not skip retrospectives just because everything seems okay. Or would you?

## Summary [](/blog/blameless-postmortems/#summary)

Blameless post-mortems are a great tool for improving your systems, processes, and your company over time. They take something bad (an incident) and make something good (a learning and improvement opportunity) out of it.

**When and how are you doing post-mortems? I would love to hear your experiences with them here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**