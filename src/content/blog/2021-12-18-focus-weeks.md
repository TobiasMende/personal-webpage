+++
title = "Focus Weeks: How to collaboratively crack difficult problems with joy"
slug = "focus-weeks"
image = "/img/import/2021-12-18-focus-weeks.jpg"
date = 2021-12-18T12:32:00
publishDate = 2021-12-18T12:32:00
lastmod = 2024-01-08T06:35:49
description = "Focus weeks are a tool for cracking difficult or complex topics as a team while fostering team collaboration and improving team culture."
tags = ["Collaboration","Culture","Ensemble-Programming","Team-Programming","Developer-Productivity","Engineering-Excellence"]
+++
# Focus Weeks: How to collaboratively crack difficult problems with joy

Focus weeks are a tool for cracking difficult or complex topics as a team while fostering team collaboration and improving team culture.

At BRYTER, first the Core Unit came up with the concept of focus weeks. It worked that well for them, that we decided to copy this concept in my unit, as we saw similar challenges.

Up to this date, in the Platform and Developer Experience Unit, we did two focus weeks, each of which yielded astonishing results.

## Challenges, focus weeks help us to overcome [](/blog/focus-weeks/#challenges-focus-weeks-help-us-to-overcome)

As the name suggests, focus weeks can help you, if you suffer from a lack of focus for certain topics.

Especially when units have a broad area of responsibility, they are prone to get numerous distractions in the form or _urgent_ request.

As for our unit, we are usually the first to be pinged, when something went wrong or is just unclear with the CI/CD pipelines, when an incident suggests that it might be a platform component that raised the initial exception or if people don’t know who else to ping. Moreover, we have the _normal_ feature development work of building developer-facing features, and we have a separate channel of constantly incoming _feature_\-requests from other units. Furthermore, for some of us, there are meetings, that sometimes chunk focus time into small pieces.

In theory, we can shut off many of these distractions, by muting certain channels and only getting the really _urgent_ notifications (by definition of the person notifying us). However, this requires a lot of training of other people in the organisation and is not the only challenge.

The bigger challenge, which is especially a problem in the previously described environment, is **procrastination**. When there is a never-ending stream of incoming _easier_ topics, it is tempting to shift to these and not work on the hard topics. This is especially true when working alone or when only having 30-60 minute blocks between meetings. Another factor can be, if people working on the hard topic don’t feel equipped enough to make difficult and consequential decisions.

The later can be the case if there is a person on the team that has more knowledge in some areas but is absent during collaboration time. Occasionally, we felt the need to discuss certain topics (i.e., about infrastructure) with the infrastructure expert on the team, who was unable to make it to our _normal_ collaboration times because of other obligations. In such cases, people would just ping them on Slack and switch to another topic that seems easier to solve in that very moment.

## What are focus weeks? [](/blog/focus-weeks/#what-are-focus-weeks)

Now, that I explained some of the challenges that we were facing, let me explain, how focus weeks work in my unit at BRYTER.

A focus week consists of 4-5 days which the entire team blocks in their calendars. We cancel all meetings during that time and announce to other units, that we are not available during that time. Furthermore, we would usually create a Mural where we collect all goals and tasks that we already see for that week. The Mural is a living document that evolves during the week and where we sketch ideas and write things we want to avoid forgetting about.

If people need to be partially absent during the time of the focus week because of private or company obligations, we mark this in the schedule on our Mural.

During these 4-5 days, we start our days between 8 and 9am to run some errands in the morning, such as reviewing some merge requests or going through Slack messages. At 9am, the entire team meets in a Zoom room to kick off the day. After a quick round of checkins, we discover the tasks we want to tackle during the day and also, how we want to approach them.

After a five-minute break, we start with team or pair programming. Depending on the tasks we discovered before, the team decides which working mode is the best suitable. If there is an important task which is very complicated and where we do not have a lot of knowledge, we would do a team programming to get things started. In this session, we usually have one driver who writes the code and at least one navigator who decides which path to take. The other people mostly watch, listen, Google asynchronously and assist the navigator with their discoveries. Typically, we are rotating roles every 15 minutes and have another 5-10 minute break after 1.5 hours.

At noon, we have a one-hour lunch break, after which we meet and quickly decide how to proceed in the afternoon. At 15:30, we finish the day with a retrospective in which we reflect about the day, what went well and what we want to change on the following day.

We repeat this until the time (4-5 days) is over, or we are done with all tasks, we wanted to solve.

## Technical set-up [](/blog/focus-weeks/#technical-set-up)

So far, all of our focus weeks were 100% remote and therefore a good technical set-up is crucial.

First, if the topic requires a special setup which not all of us have done already, we would try to prepare this in advance to not lose precious focus time.

Furthermore, we have a Mural as central element, where we maintain the schedule, the goals, the tasks, our progress, idea sketches, architecture drawings, collections of ideas and really any kind of information that could help us later.

Then, we have a Zoom room which we keep open permanently during the days. If we decide to split into smaller groups, we are using breakout rooms for that. We configure these breakout rooms so that everybody can roam freely around and visit every breakout room whenever they feel like it. Therefore, if someone has a question for people in another room, they can just switch the room and ask without loosing time.

As we always do pair or team programming, we need a setup that allows us to do this remotely. We were experimenting with IntelliJ and “Code with me” but currently are back to IntelliJ for coding and Zoom for screen sharing and communication, plus [mob.sh](https://mob.sh/) for handovers. This works sufficiently well for us.

## Results of focus weeks [](/blog/focus-weeks/#results-of-focus-weeks)

Both of our focus weeks were a massive success for the team on all levels.

We managed to accomplish much more than, we would have thought, would be possible. We were able to tackle topics that were bothering us for weeks or even months within 4 to 5 days only.

But that is not the biggest benefit that we had from focus weeks. Every time, we had a focus week, the feeling of being a team and the feeling of belonging became much stronger. We were proud of what we achieved together and were celebrating it together.

Everybody contributed to the solution, and we all learned a lot from each other, but also together. Even if many of us had no or only little knowledge about a certain topic, we were able to absorb the missing knowledge and getting up to speed as a team within the first 1-2 days.

Now, everybody would be able to maintain and evolve the solution as we all understand the approach.

Moreover, everybody had fun during that week and enjoyed it.

## Drawbacks of Focus Weeks [](/blog/focus-weeks/#drawbacks-of-focus-weeks)

Focus weeks are extremely valuable but come at a price. They are extremely intense and therefore also extremely exhausting. Even though everybody really enjoyed them, we all agreed that we would not do them every week. Probably even once a month is already a bit too much.

Currently, we are thinking that the sweet spot is somewhere around two focus weeks per quarter.

Another potential drawback is the limited availability of the team for other things. Luckily, other units are very understanding and supporting and accept that their requests might not be answered within minutes, as they are used to.

## Conclusion [](/blog/focus-weeks/#conclusion)

Focus weeks helped us a lot when we could not make satisfying progress otherwise. They are great for to improve the team dynamics and to make massive progress in a short time.

At the same time, they are not a silver bullet. They take a lot of energy and would not be sustainable for a longer period of time.

We are using focus weeks sparingly to kick-off certain topics or to unblock complex topics where we are stuck. It works for us.

That said, I still believe, that ideally focus weeks should not be needed. Teams should find enough time for focus and collaboration during _normal_ weeks, and we are working on that. Currently, we are experimenting with a team support rotation. Therefore, one or two people would take care of all the external distractions, leaving the other people on the team with lots of focus time.

Next week, I will share [a case study](/blog/focus-week-case-study/) about one of the focus weeks that we did.

**Are you having similar concepts such as focus weeks? What are your experiences? Share them here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**