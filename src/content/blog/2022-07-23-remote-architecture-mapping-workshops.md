+++
title = "How to do Architecture Mapping Workshops in a Remote Setup"
slug = "remote-architecture-mapping-workshops"
image = "/img/import/2022-07-23-remote-architecture-mapping-workshops.jpg"
date = 2022-07-23T13:27:00
publishDate = 2022-07-23T13:27:00
lastmod = 2024-01-08T06:37:38
description = "Mapping the architecture of the system that you are building in your company, is a worthwhile activity. With a bit of preparation you can run successful architecture workshops in a remote setup."
tags = ["Collaboration","Practices","Remote-Work","Software-Development","Technical-Leadership","Software-Craft"]
+++
# How to do Architecture Mapping Workshops in a Remote Setup

Mapping the architecture of the system that you are building in your company, is a worthwhile activity. The worth does not come so much from the end-result, the map, but much more from the activity itself, if done right.

In the tech leadership community at BRYTER, we recently did a couple of architecture mapping sessions, and I want to share my experience in this article.

## Context [](/blog/remote-architecture-mapping-workshops/#context)

The tech leadership community at BRYTER consists of the tech leads of the various software teams that we have in the company. The teams work on very different features and parts of the product. Technically, the product consists of around ten-ish frontends and a handful of backend services.

The goal of this community was to align on the overarching tech vision that makes sense for the entire company. Some people in the community had ideas how such a vision could look like. However, we needed to make sure that everybody has an at least _similar_ understanding of that idea and can give their professional opinion, critique, and feedback. Furthermore, we would also rely on the tech leads to guide their teams regarding architectural decisions, that would be formed around this vision.

We struggled. A lot. Since we started the community, it was a challenge to figure out, what is really relevant for the community and what is not. Everybody, of course, brought the topics that were important for their team. Which is good and interesting, but often is only a small part of the bigger picture.

Furthermore, naturally not everybody was equally engaged with those topics, as they were too far away from their area of work. Even worse, we saw a tendency, that tech leads would bring more topics to the meeting, that ideally could be decided in the teams or in a small group of people asynchronously or outside our regular weeklies.

We realised that our understanding of _the system_ was _extremely diverse_.

## We needed a map [](/blog/remote-architecture-mapping-workshops/#we-needed-a-map)

When we realised that really nobody in the community had the full picture, we started to work on it. Of course, there are many ways how you could do this.

* Somebody could just draw some diagrams and then tell everyone how the system looks like. — Boring.
* We could try to autogenerate diagrams from the system. — Pointless.
* Or: We map our system collaboratively. — Eye-opening.

In my opinion, the first two approaches are a waste of time in most cases. You end up with some kind of diagram, that maybe one person really understands and that might even be wrong and nobody notices it. Furthermore, I am convinced that the real value is in the process, not in the result.

Therefore, we went with the third approach. Mapping our system together was an interesting and valuable exercise that allowed for interesting conversations and discussions along the way. Everybody learned something and everybody contributed something.

## Our mapping approach [](/blog/remote-architecture-mapping-workshops/#our-mapping-approach)

[Alberto Brandolini](https://twitter.com/ziobrando), the inventor of event storming, once [wrote on Twitter](https://twitter.com/ziobrando/status/1070770730894270464?lang=en):

> “What is the best tool for remote #EventStorming ?” A plane ticket.

I agree, and I think the same is true for extensive architecture mapping workshops. However, if gathering in one place is not an immediate option, a lot can be done in a remote context, too.

We decided to run a couple of sessions of one hour each to create different maps/diagrams of the system together. We used the weekly slots that our community had blocked for gathering, anyway. One hour may not seem a lot for, when talking about architecture and creating diagrams, but that was precisely the key. — When sessions are too long, attention drifts away. This is especially true in a remote setup, where the distraction is just one tab away.

### The goals [](/blog/remote-architecture-mapping-workshops/#the-goals)

* **Get people talking:** Use the collaboration on the mapping to spark conversations that reveal questions and uncertainties. Find answers quickly in the group.
* **Learn from each other:** Everybody has some unique knowledge about something in the system. Make sure that this knowledge is shared.
* **Create a shared understanding of the system and its pain points:** When everybody sees a different system when thinking of BRYTER, communication is incredibly hard, as we are talking about different things. Once we have a shared understanding, it would be easier to see the biggest pain points and topics that need to be addressed in the bigger picture.

### The Anti-goals [](/blog/remote-architecture-mapping-workshops/#the-anti-goals)

* **Have beautiful diagrams:** I have seen too many efforts to create diagrams failing because people could not agree on the shape of arrows or the color of boxes, or because they got distracted by prematurely beautifying the diagrams. For us, the diagrams were just a tool to spark conversations, we might revisit them later or throw them away, both outcomes are acceptable. Thus, the focus was on the conversation and not on the diagrams.
* **Answer all the questions and solve all the problems in a couple of weeks:** It is not realistic, that we would address all topics that exist in just a couple of sessions. It is important to make this clear, so that people understand the value of the session without wrong expectations.

Especially about the anti-goals, I was very clear at the beginning of each session. As we only had one hour per session, I made explicit that I do not expect us to come up with a complete and beautiful diagram, but that there will be more sessions. Therefore, we would not have to rush it.

### The Requirements [](/blog/remote-architecture-mapping-workshops/#the-requirements)

There are not too many requirements, but for completeness I will list them here:

* A video chat tool like Zoom and a stable internet connection for every participant.
* Mural, Miro, or some other Whiteboard tool where you can draw boxes and arrows.
* Motivated and curious people who want to learn and contribute
* Time to run a couple of sessions
* A bit of preparation to not waste time at the beginning of each session.

Fortunately, we had all those things at BRYTER.

### The sessions [](/blog/remote-architecture-mapping-workshops/#the-sessions)

We did four sessions in total to map the aspects of our system, that were important to us at that time.

#### Session 1: Containers [](/blog/remote-architecture-mapping-workshops/#session-1-containers)

We started with a session that would roughly focus on the second level in the [C4 model](https://c4model.com/). Thus, we would focus on containers. Containers are things like backend services, but also frontend apps, database schema or the file system.

After a round of checkins, we continued with taking rounds where everybody added one container that was on their mind and the dependencies that this container had. We then used the “raise hand” feature in Zoom to react to this change of the map. This allowed others to add missing dependencies or correct those, that were not right. — We then continued with the round.

In the end, we reflected on the image we saw and the potential hotspots that stood out. At this point, it was clear to everyone, that one specific backend service was used by all frontend apps.

Thus, we decided to dive into this part of the system in session number 2.

#### Session 2: Components of “the Backend” [](/blog/remote-architecture-mapping-workshops/#session-2-components-of-the-backend)

Basically, we were now moving to level 3 of the C4 model with focus on the main backend service, which most teams are working on.

We followed the same approach as in the first session while adding modules to the diagram. This time, we colour-coded them by modules that are Spring-free production code, Spring production code and test code (both with and without Spring).

After we had a more or less complete picture, we reflected again about the modules and their dependencies and what they mean for the independence of our teams and the build performance. — This session created a shared understanding about one specific hotspot, a central dependency of many modules, that made things difficult to break up and build in parallel. We were also talking about a more favourable structure of the system.

We decided, to repeat the first session with the details from session 2 and an added constraint.

#### Session 3: Component Domain Mapping [](/blog/remote-architecture-mapping-workshops/#session-3-component-domain-mapping)

We already knew about two domains that we see in our business, but that are only partially present in the code base. Our goal is to introduce those two domains into the code base.

Reasons for this are that it is likely to decrease complexity for developers, helps us to keep the code maintainable and eventually split services (at least) into those two domains that also have different non-functional requirements.

Thus, we added all the components of the backend plus the various frontend apps into a new diagram, where we grouped them by domain. This created visibility of the areas that are already clearly structured and those, that lay somewhere _in the middle_.

Even though the exercise sparked interesting conversations, we learned that this representation of the system was not very valuable, as some modules respect the domains internally but are still one and the same module. This aspect was not visible in the representation, we chose.

Thus, we decided to take a dive into the data model. Our theory: We need to have our data clearly separated into those two domains, without any database tables _in the middle_ or joins across domain boundaries.

#### Session 4: [](/blog/remote-architecture-mapping-workshops/#session-4)

In this session, we mapped the existing database tables regarding those two domains.

We changed the format of the session as follows:

* In advance, we created on sticky note for each table.
* During the session, we had a silent phase, where everybody was dragging and colour-coding the stickies regarding the criteria we selected.
* Afterwards, we gave some additional time to review the mapping and note down surprises and observations.
* Then we shared those with the entire group.

The format of session 4 worked very well for us because everybody was contributing asynchronously with contributions in their area of expertise. We quickly had a big picture that we then uses as a basis for a conversation.

## Summary [](/blog/remote-architecture-mapping-workshops/#summary)

Mapping our system together helped us to create a shared understanding of it and the hotspots within. This helped us to discuss our technical vision going forward, as we were able to go back to some of our maps.

Furthermore, many community members started to draw their maps of system parts, that they were most interested in and shared their results and reflections with the community.

Even if it might be nicer to do architecture mapping sessions in person, it can still be very effective and valuable doing this in a remote setup.

**Fun fact:** When we met as a community later this year, we also did some work on _real_ whiteboards but quickly went back to virtual ones, as they were more flexible and easier to use for us. Maybe, it is more a matter of habit.

**Have you done architecture mapping workshops in a remote setup? How did you do it, and what was your experience with it? Share your thoughts here in the comments or via [LinkedIn](https://www.linkedin.com/in/tobiasmende/) or [Twitter](https://twitter.com/Tobias%5FMende).**