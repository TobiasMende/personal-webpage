+++
title = "Company Culture determines Product Quality"
slug = "company-culture-determines-product-quality"
image = "/img/import/2023-09-09-company-culture-determines-product-quality.jpg"
date = 2023-09-09T04:00:00
publishDate = 2023-09-09T04:00:00
lastmod = 2023-09-06T07:03:05
description = "Explore the link between company culture and product quality. Learn how effective communication and organizational flexibility contribute to meeting customer expectations and improving products."
tags = ["Culture","Developer-Experience","Quality","Engineering-Excellence"]
+++
# Company Culture determines Product Quality

You have probably heard the claim that improving developer experience and company culture will lead to higher product quality and satisfied customers. 

* But is this true?
* How are company culture and product quality related?
* Are product quality and customer satisfaction side effects of a great company culture?

While it would most likely go too far to call customer satisfaction a side effect of great company culture, the connection between company culture and product quality is more substantial than you might expect.

Before we dive into this surprising connection, let’s briefly define both terms: quality and culture.

## What is Great Company Culture?

Definitions of company culture and greatness differ when we ask different people. In short, I would define company culture as 

> The shared values, attitudes, interactions, behaviors, and standards that make up the work environment.

To me, a great company culture is one where people feel safe to bring their whole selves to speak up and raise concerns. — An environment where values are clear and aligned and where there is a shared truth around the company vision, purpose, and goals. 

Furthermore, knowledge sharing, mutual support, and trust are the norm in such an environment. Collaboration and communication happen openly and as much or little as needed to achieve the common goal. This includes cross-team and cross-department communication. To co-create such an environment, people in every role and position have the means to influence the surrounding environment to support their work best.

## What is Quality?

Now, let’s talk about quality. There is no such thing as absolute high quality or low quality. 

Quality can mean various things depending on where you get your definition of _quality_ from. In my opinion, the following is one of the most compact and yet suitable definitions:

> Quality = Performance upon expectations

This explains why we have so many quality issues in software: **Expectations differ, are not fully communicated, or are not fully understood.** This inevitably leads to disappointment and _low quality_.

Let’s dive deeper and explore the expectations part.

## Expectations: A moving target

To achieve high perceived quality, we need to meet the expectations of customers and other stakeholders. For this to happen, we need three things:

1. Clarity of who our stakeholders are.
2. Clear expectations from those stakeholders.
3. A correct understanding of their expectations.

Only if we get those three right can we hope to find a solution that maximizes the fulfillment of those expectations, even in light of contradictions and tradeoffs.

Very few software projects meet those three preconditions. Even in Waterfall-like projects, requirements changed later because people discovered they needed something different. Even if all expectations are clear from the beginning, the specification is complete, and all stakeholders are known upfront (big IF), there is still no guarantee that our understanding of the expectations is the same as that of stakeholders. 

**Implication:** In reality, both, the expectations and our understanding of them, change continuously.

To make it even more complicated, stakeholders not only have expectations about how the software behaves but also about non-functional requirements like maintainability and changeability, which might also change. And often, they have expectations about costs, too. 

**Implication:** We can only ensure that our mental models converge through continuous bidirectional communication with all stakeholders.

### Communication usually fails

As Woody Zuill points out in his excellent talk “[Failure to Communicate](https://www.youtube.com/watch?v=SvW5PvrLn2Y)”:

> Communication usually fails, except by accident.
> 
> Wii’s Law

It is improbable that a first solution matches all the expectations. This is especially true when multiple people are involved, and there are various expectations and a complex problem to be solved. In software engineering, we typically have all of the above.

In software engineering, we will be wrong most of the time. Our goal is not the perfect first shot but to be slightly better with every attempt. This is why there is so much fuzz around _Agile_, _Feedback Loops_, _Software Teaming_ (previously Mob Programming), and _Continuous Deployments_. Those are all means to an end: Approaching _quality = performance upon expectation_ as fast as possible.

## Product Quality = System Changeability x Ability to Communication

With the previous considerations in mind, we can see product quality not as something that we can build in from the start but as something that we can converge and work towards as we better understand and manage expectations and create appropriate solutions. This makes quality a product of our ability to communicate (fast, frequently, and correctly) and our ability to change the system (fast, frequently, and correctly).

Therefore, we can focus on two key aspects: communication and changeability. **How effective we can communicate and how effective we can change the software determines the perceived quality and also affects the cost, given that team size and other factors remain the same.**

![System- & Mental Model Convergence through Communication and Change](/img/import/2023-09-system-convergence.jpg)

System- & Mental Model Convergence through Communication and Change

**Implication:** Changeability and communication are crucial factors for every company in the business of finding elegant solutions to complex problems.

## How to increase changeability?

Changeability is not only a property of the software product itself but also of the company building it. When considering Conway’s Law and Brooks’ Corollary on its implications for management, an organization’s communication structures must match the system structure. This is where great culture comes into play.

> Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization’s communication structure. 
> 
> Conway’s Law

> Because the design that occurs first is almost never the best possible, the prevailing system concept may need to change. Therefore, flexibility of organization is important to effective design.
> 
> Brooks’ Corollary

In a great culture, it is easy for people to raise potential mismatches of organizational and system structures and spark discussions about that mismatch. Friction can be openly addressed, and people can influence their environment to do their best work. 

Furthermore, when it comes to software engineering, people can communicate and justify needed system changes and get them done. Again, this usually requires effective cross-department communication, which is more likely to happen when trustful relationships exist, and people have aligned goals and values.

On top of being able to change the company, the software must also be changeable. This requires code to be readable, understandable, and changeable with confidence. This typically means having an appropriate amount of fast and easy-to-maintain automated tests. Teams must be able to identify the necessary changes quickly and change only what they want to change without unwanted side effects.

### Non-functional requirements are not absolute.

Changeability, maintainability, modifiability, extensibility, and most other _\-ities_ are not absolute. A higher degree of changeability isn’t always better or leads to higher quality. **When we say, “This software isn’t changeable,” we mean that the needed changeability is above the actual changeability.** However, investing too much in creating changeable software can increase complexity and cost. Therefore, finding the right amount of “changeable” requires continuous communication.

![The Changeability Tradeoff and Optimal Changeability](/img/import/2023-09-changeability-tradeoff.jpg)

The Changeability Tradeoff and Optimal Changeability

## How to improve communication?

Communication is difficult. It becomes even more difficult if we cannot speak openly, have secret motives, or assume that other people might follow a hidden agenda. Trust and psychological safety increase the likelihood of successful communication dramatically. In addition, having a shared truth and knowing what this truth is helps to work through almost all disagreements or misunderstandings.

This shared truth can come from shared values, a shared understanding of the company’s purpose, and aligned goals. Once a group has established that shared truth and trusts it as a common foundation, everything can be connected to that foundation, increasing the likelihood of successful communication.

Apart from that, communicating more and with close feedback loops helps us get to know each other better and improve our communication. 

**Implication:** Our ability to change the system and communicate about the change and the system itself (fast and correctly) enables great solutions to complex problems.

## Conclusion

System changeability and ability to communicate are heavily influenced by company culture to a large extent. Improving company culture can lead to higher organizational flexibility, better communication, better understanding, a convergence of mental models and expectations, and a higher quality system and product.

This is especially true for stakeholders within the company. However, a company with a great culture lives that culture publicly. Values and behaviors are visible on the outside and influence relationships with customers and other stakeholders, too.

That said, there are other factors that we cannot influence by just focusing on company culture. Customers might have unchangeable but unrealistic expectations (under real-world constraints such as money and time limits).

Thus, while product quality isn’t a guaranteed side effect of a great company culture, a great company culture significantly increases the odds of a high-quality product and satisfied customers.

**What are your thoughts on the influence of company culture on product quality? I’d love to hear what I have missed or what you would like to add.**