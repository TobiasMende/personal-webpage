+++
title = "Maslow’s Hierarchy of Needs — DevEx Edition"
slug = "maslows-hierarchy-of-needs-devex-edition"
image = "/img/import/2023-07-08-maslows-hierarchy-of-needs-devex-edition.png"
date = 2023-07-08T04:00:00
publishDate = 2023-07-08T04:00:00
lastmod = 2024-01-08T05:46:29
description = "This article applies Maslow's Hierarchy of Needs to developer experience (DevEx), emphasizing prioritizing developers' basic needs like psychological safety before higher needs like challenging work. It presents a tailored Maslow's pyramid for developers and underscores the impact of superior DevEx on productivity and business success."
tags = ["Culture","Developer-Experience","Developer-Productivity","Engineering-Leadership","Engineering-Excellence"]
+++
# Maslow’s Hierarchy of Needs — DevEx Edition

Do you know how to prioritize your developer experience investments? You might have read about the three dimensions and 25+ factors of developer experience (see below). But what to do about that? — Maslow’s hierarchy of needs gives the answer.

Do you remember Maslow’s hierarchy of needs, introduced by Abraham [Maslow in 1943](http://psychclassics.yorku.ca/Maslow/motivation.htm)? Already 80 years old, the hierarchy is still relevant today when understanding humans, their needs, and motivations.

Due to the significance of Maslow’s observations, the hierarchy of needs is important not only to understand humans but also to understand leadership and to put our developer experience efforts into a context.

## Recap: Maslow’s Hierarchy of Needs

The hierarchy of needs is often represented as a pyramid with the basic needs at the bottom.

![](https://unblocked.engineering/wp-content/uploads/2023/06/Maslow-Pyramid.png)

Maslow’s hierarchy states that higher needs move into the background when more basic needs are unmet.

> If all the needs are unsatisfied, and the organism is then dominated by the physiological needs, all other needs may become simply non-existent or be pushed into the background. It is then fair to characterize the whole organism by saying simply that it is hungry, for consciousness is almost completely preempted by hunger. — A. H. Maslow

A person struggling to find food or shelter rarely thinks about their purpose or the meaning of life. Only when the basic needs are met do we start to think about topics like morality, creativity, purpose, or how to maximize our potential.

## Maslow’s Hierarchy of Needs for Developer Experience

In the paper “[An Actionable Framework for Understanding and Improving Developer Experience](https://arxiv.org/pdf/2205.06352.pdf)” by Michaela Greiler, Margaret-Anne Storey, and Abi Noda from 2022, the authors introduced 25 key factors of developer experience. While I agree with these factors as I have seen their impact in practice many times, I also realized that their significance differs.

So how do we prioritize our developer experience efforts to have the most impact? While it is always a good idea to ask developers what would improve their experience, I believe that Maslow’s hierarchy of needs can help us to weigh these factors based on human needs. After all, developers are humans, too.

### The 25+ Key Factors of Developer Experience

The paper “[An Actionable Framework for Understanding and Improving Developer Experience](https://arxiv.org/pdf/2205.06352.pdf)” lists the following 26 developer experience factors:

* development and release  
   * codebase health  
   * development environment  
   * automated testing  
   * frictionless release
* product management  
   * clear goals, scope, and requirements  
   * working iteratively (small WIPs)  
   * unreasonable deadlines  
   * having a say on roadmap/priorities  
   * providing value to the business
* collaboration and culture  
   * supportiveness  
   * knowledge sharing  
   * feeling connected  
   * code review process  
   * collaboration between departments  
   * psychological safety  
   * communication  
   * having aligned values  
   * getting recognition
* developer flow and fulfillment  
   * autonomy  
   * challenging/stimulating work  
   * making progress without obstacles  
   * uninterrupted time  
   * work-life balance  
   * learning  
   * stability of job and team  
   * clear paths for career growth

I have mapped these factors to the hierarchy of needs, which gives us an approach to weighing these factors.

### Introducing Maslow’s Pyramid, the DevEx Edition

![](https://unblocked.engineering/wp-content/uploads/2023/06/DevEx-Edition.png)

As you can see, none of the factors fall into the physiological needs category; fortunately, these needs are not an issue in most work environments of software engineers.

However, already on the second layer of the pyramid, “Safety and Security,” we find factors like psychological safety, stability of job and team, as well as work-life balance.

Other factors, such as the development environment or automated testing, are much higher up in the pyramid and, therefore, less fundamental.

Of course, we can discuss if “providing business value” is more about self-actualization or esteem, and these mappings are not always exact. However, we can clearly see that some factors satisfy far more basic needs than others.

Take “supportiveness” and “feeling connected,” for example. Does an engineer who feels unsupported and unconnected really care about challenging and stimulating work?

#### Maslow’s Pyramid, the DevEx Edition in Text Form:

1. **Physiological Needs:** luckily not an issue in most work environments
2. **Safety/Security:** psychological safety, stability of job and team, work-life-balance
3. **Love/Belonging:** supportiveness, knowledge-sharing, collaboration between departments, feeling connected, communication, having aligned values
4. **Esteem:** clear goals, scope and requriements, working iteratively, unreasonable deadlines, getting recognition, making progress without obstacles, autonomy, uninterrupted time
5. **Self-Actualization:** codebase health, development environment, having a say on roadmap/priorities, clear paths for career growth, frictionless releases, automated testing, providing business value, challenging/stimulating work, learning

### Observations

The pyramid guides leaders who need to decide where to invest first. If factors on the lower layers are not fulfilled, the likelihood is big that basic needs are not yet met. Thus doubling down on investments at the top of the pyramid might not yield as much of an improvement as an investment at the lower levels.

This is enforced by the negativity bias, the human tendency to pay more attention to problems than to the things that are already working well.

That said, it is important not to abandon efforts further up in the pyramid if there are issues with the lower levels, as this will send the wrong signal and worsen the situation.

Furthermore, it is important to note that factors at the top of the pyramid are important for outstanding developer experience. The factors further down in the pyramid are supporting factors that enable the effectiveness of the factors further up. Thus, working your way up the pyramid toward outstanding developer experience is important.

Most of the developer experience factors are located pretty high in the pyramid. This is unsurprising as we discuss factors that lead to high performance, engagement, motivation, and business success. Those outcomes are far more likely for thriving individuals and teams. Handling the “self-actualization factors” well differentiates between an _okay-ish_ team/organization and an _excellent_ team/organization. — That is, if factors further down are handled well.

## Conclusion

In conclusion, applying Maslow’s hierarchy of needs to developer experience helps us prioritize efforts and make informed prioritization decisions. The goal is first to address the most basic needs, thereby building a strong foundation for high performance, engagement, and motivation, ultimately driving business success.

Developers are humans first, and catering to their basic safety, security, love, and belonging needs can significantly influence their productivity and engagement. However, this doesn’t mean that we disregard the factors at the top of the pyramid. Instead, it’s a matter of balancing and ensuring all needs are met in the right order.

In the DevEx context, the primary focus would be ensuring psychological safety, job stability, and work-life balance. Once these needs are met, we can gradually shift attention towards factors that impact self-esteem and, finally, self-actualization needs like providing challenging work and learning opportunities.

Just as Maslow’s hierarchy remains relevant to understanding human needs and motivations, this developer-centric adaptation is an effective guide in enhancing the developer experience.

We should continuously evaluate and adjust our strategies based on feedback from developers, ensuring an environment that not only sustains but fosters creativity and innovation. After all, an excellent developer experience translates to producing high-quality, innovative products and services, driving your organization toward success.

* **Want to level up your Developer Experience? I can help on all levels of the pyramid and invite you to [schedule a free discovery call](https://unblocked.engineering/#DiscoveryCall) with me!**