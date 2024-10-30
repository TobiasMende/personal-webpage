+++
title = "Ways to Decrease Performance: Velocity Tracking"
slug = "ways-to-decrease-performance-velocity-tracking"
image = "/img/import/2023-07-15-ways-to-decrease-performance-velocity-tracking.jpg"
date = 2023-07-15T06:00:00
publishDate = 2023-07-15T06:00:00
lastmod = 2023-07-12T06:53:39
description = "Discover why velocity tracking, a popular Agile practice, might be hindering your team's performance more than helping it. While it might seem beneficial at first, over-reliance on velocity can lead to burnout, overestimation of work, and neglect of long-term benefits. Learn about the pitfalls and start thinking critically about your Agile practices. Remember, it's not about knowing your speed — it's about moving in the right direction sustainably."
tags = ["Metrics","Practices","Ways-To Decrease Performance","Developer-Productivity","Engineering-Excellence"]
+++
# Ways to Decrease Performance: Velocity Tracking

This is the first article of my series, “[Ways to Decrease Performance](/blog/tag/ways-to-decrease-performance/)”, which intends to trigger critical reflection on common _“Agile”_ practices, that is, practices that I see many _”agile”_ teams doing.

In this article, I will focus on velocity tracking and the related topic of estimating.

## Disclaimer

My take on the topics covered in this series is (potentially) controversial, I know. And as always, remember that there rarely is black or white or right or wrong. There is no golden path perfectly suitable for every team. There is a lot of “it depends.” 

The goal of this series is not to tell anybody that they are “doing it wrong.” 

I desire to spark critical reflection on why you are following these practices. Is it because they help you, or because everybody is following them and “this is how one does it”?

## What is “Velocity Tracking”?

Velocity tracking is measuring a team’s velocity (software engineering team). This is usually done by estimating the size of a task or story in terms of a defined measuring unit.

Many teams use story points, a fictive unit that cannot and should not be compared across teams. Its raw value means nothing. It is the trend over time that matters.

The velocity is the number of story points that can be _earned_ in a given interval, like a Sprint. Story points are _earned_, when the task or story they are assigned is moved to _Done_.

Using these measures, it is possible to draw a graph, sometimes called a _burndown chart_ that shows how many story points were earned (or are left) on a given day/week/sprint.

Therefore, the progress in terms of “story points earned” can be observed visually.

Teams often use their velocity (number of story points per Sprint) for Sprint planning to know how many stories they can add to the Sprint. 

## What are the problems of “Velocity Tracking”?

While the above practice sounds attractive at first glance and gives a lot of clarity and predictability, it can harm the team’s performance in various ways.

### 1\. Humans are imperfect at estimating accurately.

When an engineer thinks about the size or complexity of a story, they go through all the things that need to be done for the story to be done and roughly estimate the time it requires them to do this. They will estimate a higher number if they assume a huge refactoring is needed to finish the story. That is, of course, if they have an accurate model of the codebase in their head and can anticipate this extra effort.

The same is true for other _time-sinks_ such as hard-to-test code paths, cross-team communication, infrastructure, security or framework aspects, and even unforeseen questions and uncertainties that must be dealt with on the fly.

All these factors can cause teams to get lost in the process of estimating stories, all with the intent of estimating better. This rarely works. Therefore, a lot of time is often spent on discussing and estimating stories with the goal of higher accuracy. That time could as well be spent working on the story together and discovering unknown or complicated aspects of it.

### 2\. “High speed” does not mean “right direction.”

But even if we would assume that your team nails the estimation and manages to estimate correctly, Sprint in and Sprint out, without investing hours or days. There are more problems with velocity tracking.

Just because you are fast does not mean you are going in the right direction. You can have a high velocity and still build the wrong thing. This becomes especially likely when you are cutting corners and are not taking the time to reflect on previous work and feedback as a team. 

Those things, however, tend to decrease the velocity. I have teams forcefully stop discussions and push through on stories to earn the points attached to them. This might feel productive but kills the factors that make high-performing teams faster than you can say “velocity tracking.”

### 3\. The pressure to increase velocity over time

When you have a metric that is seen as “how good you are doing,” people naturally desire to become better in that metric. Regarding velocity, this means increasing the velocity over time.

Now, teams have multiple options to do this.

#### a) Work more on things that earn points within a Sprint

To earn more story points during a Sprint, people can work harder, eventually leading to burnout and a _decrease_ in velocity.

They can also work only on things that directly increase the velocity. (“Let’s not do that refactoring now, it will cost us time and velocity”). This, too, will _decrease_ velocity in the long run as quality goes down.

#### b) Estimate higher story points

Story points are a fictive unit; thus, it is easy to estimate higher story points over time. 

This will happen naturally when the system quality decreases. (“To achieve this outcome, we must do this, this, this, and that. It is complex. Let’s estimate higher”)

Therefore with accruing accidental complexity, friction, and technical debt, velocity might still increase while the team is getting slower and slower.

Furthermore, if teams are judged by their velocity, they will do everything they can to look good in that metric. Estimating higher points is one of the easiest, safest, and healthiest solutions.

#### c) Fixing underlying issues

Of course, teams could reflect on why they operate at a certain velocity and invest effort in addressing aspects that hold them back from achieving higher velocity levels. They could also be aware if a similar story half a year ago was estimated smaller and reflect on ways to get complexity down to that level again.

The issue, however, is that they cannot do that without temporarily decreasing their velocity or putting work that does not directly benefit customers into their velocity calculation. (Interesting point for discussion: “Would you estimate bugs?” — I wouldn’t — More bugs mean more distraction and less quality or ability to deliver customer value. They surely should negatively affect the velocity. Or?)

Putting all kinds of things into the velocity calculation would be okay if we wanted to see the speed with which the team is doing _something_. But why do we want that? Most groups justify their velocity tracking with the ability to tell stakeholders when to expect a particular feature or change in general. (“We are confident that we will have that story done after this Sprint.”) — However, you cannot have both.

Either you put everything into the velocity calculation, which makes “velocity” a pretty useless metric, or you only add what has direct customer value attached. The latter often leads to devaluing work without story points (bug fixes, removing technical debt, improving pipeline lead time, …) — All of those make the team faster and increase product quality. However, they will show a dent in the velocity graph.

### 4\. Teams run at capacity

Adding to the previous point, tracking velocity creates this natural desire to add more to the Sprint to achieve a higher velocity. I have seen more than one team running at capacity, leaving no space for unexpected events such as sickness, change in effort, or anything else. 

Those teams were likely to cut corners, skip quality measures or work long hours to meet their target. All of those are harmful in the long run. Other teams struggled with stories spilling over into the next Sprint, which defeats the purpose of having Sprints in the first place.

### 5\. Teams neglect long-term benefits for short-term velocity gains

Somebody racing with their car on the highway might appear to arrive at their destination faster. That is unless they crash or drive in the wrong direction. Furthermore, their car will likely wear off faster than cars driven with more care and sustainable velocity.

For agile teams, it is the same. It is easy to lose the bigger picture and do what is the right thing long term in favor of having a higher velocity in a short time. This will ultimately push back in numerous ways.

## Summary

Tracking the velocity often motivates unhealthy, unsustainable, and damaging behaviors. The value, however, is pretty unclear. Estimates, on their own, have close-to-zero business value.

Estimating costs time. That time could also be spent running experiments and building the right thing.

While velocity tracking can offer insights into a team’s productivity, it should be considered carefully. This is because velocity tracking often motivates behaviors that can harm the team’s performance in the long term, such as overestimating work, ignoring long-term benefits for short-term gains, and fostering a culture of rushing and cutting corners. Furthermore, humans are inherently bad at estimating accurately, and high speed does not necessarily correlate with the right direction.

Instead, create a balanced team culture that values reflection, prioritizes sustainable work practices, and encourages constant improvement and learning. Remember, it’s not about knowing your speed — it’s about moving in the right direction sustainably.

**Are you tracking your team’s velocity? What for? What are your experiences with the velocity metric?**