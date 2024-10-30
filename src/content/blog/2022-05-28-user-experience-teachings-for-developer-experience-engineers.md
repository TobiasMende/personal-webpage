+++
title = "What Developer Experience Engineers can learn from User Experience Engineers"
slug = "user-experience-teachings-for-developer-experience-engineers"
image = "/img/import/2022-05-28-user-experience-teachings-for-developer-experience-engineers.jpg"
date = 2022-05-28T13:15:00
publishDate = 2022-05-28T13:15:00
lastmod = 2024-01-18T05:52:22
description = "Developer experience engineering is a pretty new discipline. However, there are numerous parallels to user experience engineering. Therefore, DX engineers can learn from the teachings of UX engineering."
tags = ["Culture","Developer-Productivity","Software-Craft"]
+++
# What Developer Experience Engineers can learn from User Experience Engineers

While developer experience is a relatively new term, user experience is not. In fact, the term _user experience_ was probably first coined in 1990 by Don Norman:

> No product is an island. A product is more than the product. It is a cohesive, integrated set of experiences. Think through all of the stages of a product or service – from initial intentions through final reflections, from first usage to help, service, and maintenance. Make them all work together seamlessly.

Over time, user experience engineering became a crucial discipline when building (software) products. As developers are users too, we might discover some beneficial methods for developer experience engineering, when looking into the topic of user experience. Since user experience engineering has a long history, there is a huge number of resources, tools, methods, and experience in general out there.

In this article, I will start to reflect on aspects of UX engineering and how this could look like, when applied to the developer experience (DX) engineering discipline.

## User experience design is about the _why_, _what_ and _how_ of product use [](/blog/user-experience-teachings-for-developer-experience-engineers/#user-experience-design-is-about-the-why-what-and-how-of-product-use)

User experience design is not only about the product and its usability. UX designers also focus on other aspects of the user journey, such as their motivation for using the product in the first place.

Therefore, the _”why”_ is about the reasons a user has for using the product. This goes hand in hand with the _”what”_ which is about the functionality and what the user can achieve by using the product.

Finally, we have the _how_, which refers to the accessibility, usability, and design of the product.

These three aspects are described more in detail by Peter Morville as the User Experience Honeycomb1.

## What we can learn from the UX Honeycomb [](/blog/user-experience-teachings-for-developer-experience-engineers/#what-we-can-learn-from-the-ux-honeycomb)

With the UX honeycomb, Peter Morville describes user experience with seven facets: usefulness, desirability, accessibility, credibility, find-ability, usability and value.

![](https://unblocked.engineering/wp-content/uploads/2024/01/2022-05-28-uxhoneycomb-1.jpg "The UX Honeycomb by Peter Morville")

The UX Honeycomb by Peter Morville

Those seven aspects are absolutely relevant for developer experience design, too. Therefore, I find it very helpful to think about those aspects and how they can look like in the developer experience world.

### Usefulness [](/blog/user-experience-teachings-for-developer-experience-engineers/#usefulness)

A product or service must fulfil a user’s needs or wants. Otherwise, there is no purpose for it. This undoubtedly is true for products and services targeting developers, too.

Thus, as developer experience engineers, we need to ask, survey or observe our users and understand, how they work and what needs they have.

With my team, we are doing this in various ways. First, we work closely with other teams in pairing and collaboration sessions. Second, we have an inbox and developers can dump their ideas at any time. Furthermore, we use company events to run sessions where developers can bring in their ideas but also their frustrations around certain topics. Finally, we run surveys from time to time and observe how people are using our offerings, where they struggle and what might be missing.

### Desirability [](/blog/user-experience-teachings-for-developer-experience-engineers/#desirability)

Products should be desirable, meaning aesthetic and appealing to work with. While this is especially true for products targeting less experienced users, it still can make a difference for products targeting experts.

At the end, if your solution is more cumbersome to work with than the alternative, the developers you are caring for, usually will not adopt it.

### Accessibility [](/blog/user-experience-teachings-for-developer-experience-engineers/#accessibility)

User experience engineers must not only care for a _standard_ user with certain characteristics, but also keep folks with different backgrounds and/or disabilities in mind.

Ideally, products and services are usable by all of them. While it can feel tempting to ignore this facet when dealing with company-internal developer experience topics, it still is an important aspect.

Your colleagues are different and need different things from a product to use it. Some might be more experience in using the console than others, some already have seen numerous technologies, some not. Some can differentiate red and green, some can’t.

Consequently, even when building internal products, it makes sense to pay attention to the accessibility of your products.

### Credibility [](/blog/user-experience-teachings-for-developer-experience-engineers/#credibility)

Credibility means, that the products and services are trustworthy. When thinking about external facing products, we think about things like data protection and trustworthiness of the company. But also reliability and stability influence the credibility of you and your products.

Moreover, for developer experience teams, credibility is a crucial aspect. Developers need to trust in you and the quality of your offerings to feel safe and comfortable to rely on those.

Therefore, it is important to hold up to promises, keep APIs as stable as possible and communicate planned changes ahead of time. Furthermore, it is mandatory to ensure high quality and reliability of your services, too.

### Find-ability [](/blog/user-experience-teachings-for-developer-experience-engineers/#find-ability)

Find-ability or discoverability is about the aspect of your users being able to find your products, services, and offerings in general.

This was an aspect that we neglected for some time in the developer experience team at BRYTER. However, we learned, that it is of course not enough to create some _products_ and announce them once. We needed a better way of making them findable by developers.

Developer with a specific problem need to have a way to find the best solution we can offer at that specific moment. Being these abstractions for writing tests or for creating CI pipelines, documentation, or monitoring features and other services that our team is providing.

Companies usually maintain websites where they advertise their products and use-cases for which their products are suitable. As a developer experience team, it is valuable to think about similar tools to improve discoverability of your offerings, such as developer portals.

### Usability [](/blog/user-experience-teachings-for-developer-experience-engineers/#usability)

Ideally, products are usable without a long and painful learning curve. Our users should be able to adopt new products quickly and, if possible, without external training or documentation and with a pleasant and quick learning journey.

In general, this means, that a system should behave as expected, with as little surprises as possible and that the users’ intuition will guide them into the right direction in most cases. This is true for business users as well as for developers.

When designing systems for a great developer experience, usability is an important factor. Whatever system, tool or service we provide with the intent of improving the experience for developers, we need to ensure that developers can adopt it quickly and that learning the tool does not become the main task.

For this, it is beneficial to think about analogies between systems. Users can adopt new systems faster, when they can be used similarly as other systems, that they already know. Consistency plays a significant role when it comes to usability.

Furthermore, our solutions must prevent users from doing harmful operations (easily). This will give our users the psychological safety to try out our offerings because they do not need to be afraid of doing _bad_ mistakes.

### Valuable [](/blog/user-experience-teachings-for-developer-experience-engineers/#valuable)

If your product does not bring any value to your customers, they will not buy it. For internal developer experience teams, this seems less relevant, as our offerings are not _bought_ by developers.

However, this factor is important from two different perspectives. First, developers hate to waste time. If they do not see the value in something you offer them, they will just ignore it. Second, if you provide too many things that are not valuable to the developers you are serving, the value that your team has for your company, decreases.

The value of a dedicated developer experience team is, that it helps other developers to do their jobs faster, better and ideally with more joy. This, in the end, has a multiplicative impact on the business output, if the offerings of such teams are valuable to _their customers_.

## Summary [](/blog/user-experience-teachings-for-developer-experience-engineers/#summary)

After all, developers are users, too. Therefore, the teachings from the user experience discipline are invaluable for developer experience teams that want to increase their impact.

While developers might be used to less usable products and steep learning curves, they still enjoy products with a good user experience. Offerings of developer experience teams are no exception to this.

**What are your thoughts on this? Write me here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**

---

1. [Article by Peter Morville about the UX Honeycomb](http://semanticstudios.com/user%5Fexperience%5Fdesign/)