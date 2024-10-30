+++
title = "Value-Stream-Oriented Kanban"
image = "https://unblocked.engineering/wp-content/uploads/2024/04/value-stream-oriented-kanban.931f880794b04f0988fb5e40137fbd33.webp"
date = 2024-04-20T05:00:00
publishDate = 2024-04-20T05:00:00
lastmod = 2024-04-17T11:22:01
description = "Discover how value-stream-oriented Kanban can transform your software development process. This blog post explores how Kanban helps you see the big picture—from initial ideas to final delivery—ensuring every step adds real value for customers and your business. Find out how to set up a Kanban board that truly captures your products lifecycle, pinpoints bottlenecks, and smooths out your team's workflow for better productivity."
tags = ["Business","Developer Productivity","Engineering Leadership","Kanban","Product Management"]
categories = ["Developer Productivity","Engineering Excellence"]
+++
# Value-Stream-Oriented Kanban

Many teams, especially in the startup environment, move away from Scrum and use a leaner Kanban-based approach. This is a good thing. I don’t think Scrum is a suitable framework for modern, fast, agile companies. – Especially not in the SaaS field (the reasoning behind this statement will become another article, eventually).

Starting with Kanban, the most obvious board structure is “To Do”, “In Progress”, “Done”. This is potentially the simplest Kanban board and one often seen in examples. Teams would typically break down larger initiatives, projects, epics, <you name it> into smaller tasks that move independently over the board. The original epic would either live in “To Do” or “In Progress” while there are still sub-task not in “Done”.

The teams then measure their productivity or effectiveness utilizing Kanban metrics on the sub-task level.

This is a problem.

## What do we want from Kanban?

Kanban is great to visualize the work, discover bottlenecks, optimize flow and prevent us from starting too many things by setting reasonable WIP limits. Ideally, with this overview we can measure flow metrics such as cycle time, WIP, throughput and the work item age.

The problem starts, when we measure those metrics on the individual sub-task and not on the customer-focused initiatives: We can have excellent scores in all of those metrics while starting 5 initiatives in parallel and not having significant business impact with any of them.

Tasks can flow fast from left to right for weeks without us delivering anything meaningful to customers. We feel super productive without creating actual business value.

As we all know, starting multiple initiatives in parallel sounds like the right thing to do from a utilization perspective: Keeping people busy, maximizing utilization. The cost: Delayed delivery on all initiatives.

> The goal shall never be maximizing utilization. The goal shall be delivering business value fast. And these two things contradict each other.

### The tragedy of high utilization (short version)

While it is obvious to all of us, that we do not want to have our servers run at 100% CPU load, 100% RAM usage, or 100% disk usage, people frequently make this mistake when it comes to people. The results are even more harmful than with computer resources. Not only does the delivery of business value take exponentially much longer, it also is a sure path to burnout. Developing software products is a complex endeavor full of surprise, and estimating correctly when something will be done is almost impossible. It gets even more impossible when there is more than one thing.

## How do we define work?

With a task-centered perspective, a work item clearly is a single Kanban card, a sub-task, moving from left to right. Something that keeps us busy and fills our day. This is, what we are paid for. Right?

Take a step back from software and think about other areas of lean product development. What is a work item in an assembly line for cars? The seats that need to be built into the cars? The process of building the seats into the car? The wheels that need to be attached? Of course not. The work item is the car. It does not matter how fast you are attaching wheels. What matters is, how fast the car is ready to be delivered to the customer. Attaching wheels is a process step – a column on the Kanban board.

Therefore, in software product development, a work item as a product increment. A product increment starts as a customer problem/idea that will be discussed and understood. Then, we form a hypothesis how to evolve the product to solve this problem. This leads us to shaping, scoping, designing, implementing, and testing the product increment. Finally, we deliver the product increment.

So when is a product increment done? **It is done earliest, when it is delivered to the customer.** — Bonus points, when you visualize also the work items delivered on which you still need to collect feedback to validate your initial hypothesis.

## How the Kanban board might look like

In reality, the Kanban board should often have more than three columns to visualize the process steps in the value stream. While having just three columns for those product increment initiatives gives you clarity on how many initiatives are currently ongoing, it is difficult to see if something is stuck and in which stage.

The Kanban board should reflect the stages in the value-stream in which a valuable something can be. This will look differently for a sales team in contrast to a product team. The later might something like have:

1. New
2. Idea understood and expressed
3. Product Increment defined
4. Design / Concept
5. Under Development (Includes things like coding, reviewing, testing, …)
6. Ready for Delivery (You might not have this, if you do continuous deployments)
7. Waiting for customer feedback (Basically means: need to check data and customer feedback and see if the hypothesis was correct or if we need to iterate on the solution, which would be a new product increment based on a refined hypothesis)
8. Done
9. Discarded (you might not have this column, but just archive or delete items that you won’t consider worthy of being implemented)

If you have a board with columns like this and have cards that reflect the product increments and not just busy-work, great. This shall give you a lot of transparency on where you stand with each of the initiatives. Now, what about WIP limits?

## Setting reasonable WIP limits

Depending on the level on which you define WIP limits, different numbers are reasonable. In my opinion, the **number of initiatives/product increments** in progress **should be smaller** than the **number of team members**.

The reason is simple: We want people to collaborate and focus on the most important thing, not being busy individually. If everybody has their initiative, people will have a hard time helping each other out, as this means switching to an entirely different context and interrupting progress on whatever valuable initiative they are currently working on.

The ideal WIP limit for initiatives within a team likely is **1**. While this sounds extrem, imagine how fast you could complete an initiative if everybody on the team had time to work on it. Initiatives that take weeks or months might be completed within days.

Now, you might want to set the limit to **2**, when you consider what is “work in progress”.

Look at the example above. Which columns are WIP? I would argue, that at least columns 3–6 count toward that limit. In these stages, someone has already invested time in this work item. If it is stuck in the pipeline, this means, someone invested time (the company’s money) in this increment without it generating any customer value. Inventory is expensive. Even worse: Priorities might change and that work item is stuck in the pipeline forever, distracting people from what actually matters.

Now, a WIP limit on the level of product increments of 1-2 per team sounds extreme, and it is. Just take a moment to reflect on the alternative: People are spread thin across different initiatives, already needing time for meetings to clarify, scope, and discuss whatever comes next while simultaneously supporting peers on “their” initiatives. And then there is also unplanned work: incidents, bugs or that “quick” request from customer success. — All of that is work, too. It is work beyond the value increments, that needs to be done, regardless of how “busy” you already are.

### What about “technical initiatives”?

A common challenge for startups is the need to go fast. Often, this comes with cutting corners and taking on technical debt. Paying this back can take significant time. The same is true for renovation projects, such as changing from an old unmaintained framework to a new maintained one. 

I recommend tracking big maintenance/renovation projects like initiatives. They are an investment in the product/company future, and they can take significant amounts of time. Ideally, if a team realizes it has to do some big tech initiative, such as migrating from an older unmaintained framework to a new one, it focusses on this endeavor to get it done quickly. Therefore, such initiatives should count toward the previously mentioned WIP.

### WIP limits on the task level

An initiative can have many tasks. And for tasks, the classic layout “To Do”, “In Progress”, “Done” might be a great fit. Furthermore, not everything is an initiative. Some things just come up and need to be done but are more a rather small task that must not be forgotten and eventually done. Tasks can be anything from sketching out an implementation over updating a dependency to fixing an urgent bug.

For tasks, WIP limits are important, too. Ideally, the majority of tasks worked on come from initiatives creating customer value. This might look different for companies who neglected technical investments for the sake of moving fast, for too long, or for companies who do not have a certain level of automation.

For example, an operations team might have an influx of tasks for permission requests from other teams. Those tasks go away once the operations team established a tool for automated permission rollout (this would be an initiative).

On the task level, I recommend a WIP limit smaller than the team size, too. This acts as a forcing function for collaboration and facilitates knowledge exchange and learning and increases resilience.

## Practical Implications

While most tools allow showing both, initiatives/projects/epics and tasks on the same board, I don’t think this is the best approach in most cases. Tasks have another flow than initiatives. We need to visualize work on different levels: The day-to-day task work and the bigger-picture initiatives. The board used daily should contain all those tasks/parts of the current initiative and everything else important for the team right now. Bugs, “quick” requests, … — those things should be prioritized in the “To Do” column. 

The question should be: Is this bug or request so urgent, that we should delay the ongoing initiative? Often, the answer is “no”, given that many initiatives, once they get focus, will be done in a week or two (otherwise, find smaller increments).

This board should not contain subtasks of future initiatives, as the team should refrain from working on them until the previous initiative is out of the WIP area. One reason for this is focus on the current initiative, another reason is, that priorities might change fast and all the planning and scoping work then go to waste and might sit in the backlog for years collecting dust (until I come in, and we delete your backlog ;-))

### Let your To Do column run empty

**You are doing it right when the To Do column frequently runs empty.** This is a sign that more work can be taken on and scoped. It is a sign of maturity, when the team can frequently decide consciously what the next things to work on, are. It helps the team to step back and think about value rather being busy moving tasks from left to right. It enables business agility: Whenever an initiative is finished, the team(s) can work on whatever is the most important thing for the business _right now_, instead of working on what the business thought would be most important _3 months ago_.

Conversely, if the number of work items seems to increase continuously, it indicates that you either need more people/teams or need to resolve productivity and performance bottlenecks (start with the latter).

### Different Boards for Different Views

In practice, it makes sense to have different boards with different columns for different abstraction levels.

Many companies find it useful to have a board for product planning, product roadmap, ideas, or however you might want to call it. This is the place where (sometimes) abstract and unspecific ideas can come in. This board visualizes the flow from ideas to product increments, the engineering teams work on, and onward to the customer.

Not every idea might end up being worked on. Multiple ideas might be grouped and result in a single product increment. Some ideas might be split into multiple product increments. How to prioritize ideas and from which ideas to derive product increments from and which ideas to discard requires communication with all stakeholders involved. Typically, these are sales, customer success, product, and engineering.

The perspective which this group of people needs is very high level:

* Which ideas do exist?
* Which ideas are important for us? (customer value, business value, relevance in the grande picture of the product strategy and vision (you have those, RIGHT?!?))
* What do those ideas mean? (Shared understanding of use cases/problems to be solved, efforts needed to make it work, priorities)
* Which ideas have made it into a product increment?
* Where in the lifecycle is the product increment? (Examples: Scoping, Implementation, Collecting customer feedback, Done)
* Which team is currently working on this increment?

A board like this should not have all the implementation details potentially needed for the day-to-day implementation work. Once teams start working on an increment, they might want to create tasks and subtasks on their board for this initiative (see above).

I recommend that teams specify just as many tasks as they need to work on the increment, without planning everything in detail for the future. The dynamic that can be observed is: The more a team collaborates, the less specific and detailed do tasks need to be, and the less time has to be invested in upfront planning.

Whenever an increment is considered “done” on the product planning board, there should be no tasks left on the board of the engineering team. 

If there are tasks left that are not relevant enough for the increment to be considered done, this implies, that too much upfront planning was done. I recommend deleting those tasks. Otherwise, they will live in your backlog forever, and they will consume your time every time you stumble over them or discuss them with your team.

Here is a visual example:

![](https://unblocked.engineering/wp-content/uploads/2024/04/Value-stream-Kanban-Boards.jpg)

* When things come in, they are in new. This can be a mix of ideas, problems, feature requests, …
* A group consisting of people from product, engineering, Sales and CS collaborates to ensure that the new items are understood by everyone and that the shared understanding is documented. If the idea is already considered irrelevant at this point, it goes to “Discarded”. Otherwise, the card is move to the second column.
* The relationship between product increment and ideas is not always 1-to-1\. An idea might spawn multiple product increments, or multiple ideas are combined into one product increment. Once the group has found a viable product increment that they consider valuable to customers (or the business), they create the card in “Product increment defined”.
* At this point, I would consider it already as “work in progress” as it only makes sense to specify product increments, when we want to work on them. The next step involves making a technical concept and breaking the increment down into actionable tasks for the team to work on. This is also the point, when the “Up Next” column in the teams Kanban board starts to fill up (this is done by members from the product development team)
* Once the team actually starts working on the increment, it moves to “Under Development” to show stakeholders from Sales and CS that the team actively works on the increment.
* As soon as the increment is ready to be delivered, it moves to “Ready for Delivery” – Here we are talking about “making it accessible to customers”. Technically speaking, this can be when something is deployed but still behind a feature flag. This stage allows Customer Success to prepare the rollout (i.e., inform customers) and Sales to use the increment in sales demos.
* Once the product increment is rolled out to all customers, the card moves into “Waiting for customer feedback”. — This is to make sure that the increment is not forgotten as soon as it is rolled out, but that product managers and customer success take care to collect feedback (through metrics, surveys, and interviews) and monitor the adoption/usage of the increment.

Note that the team might want to deliver something earlier to internal customers or early adopters to get feedback while still in development. This reduces risk and increases the probability of a successful adoption later on.

**Remark:** This is an example of how the boards can look and who is involved in which stage. Depending on the process in your company and the product you are developing, your boards might look entirely different.

## Conclusion

A Kanban board is a great tool for visualizing processes. What matters is that companies visualize their value streams and not just their busy work. A simple Kanban board can hold both, value increments and busy work. A more specific value-stream aligned board won’t hold busy work very well and will make you feel the tension when trying to put busy work on it. The board is not a good fit.

That said, there are of course things that are more on the side of busy work rather than on the side of product increments. Bugs, incidents, occasional requests, technical updates and refactorings. Be mindful which of them you allow bypassing the product board. All of those will reduce the flow of product increments through the value stream. They are distractions from furthering the product.

Those things need to be visualized, too. The team needs to have them on their board, and stakeholders have to understand how much distraction there is and how to improve the situation. It can help to tag cards on the team board with their origin (product initiative, bug, customer request, …) to understand, where attention and time go.

**I am curious:** What do your boards look like? What kinds of boards do you have? Please share how you do it in the comments below.

## I invite you.

Are visualizing the work and optimizing the flow of value challenges in your organization? — Drop a comment below, and I will reach out to you to schedule a free session. Together, we will identify the root causes and define next steps to improve the situation for your teams.