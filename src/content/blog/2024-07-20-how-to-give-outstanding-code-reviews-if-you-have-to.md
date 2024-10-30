+++
title = "How to give outstanding code reviews (if you have to)"
slug = "how-to-give-outstanding-code-reviews-if-you-have-to"
image = "/img/import/2024-07-20-how-to-give-outstanding-code-reviews-if-you-have-to.jpg"
date = 2024-07-20T05:00:00
publishDate = 2024-07-20T05:00:00
lastmod = 2024-07-17T14:18:29
description = "Code reviews are essential for maintaining code quality and fostering team collaboration. While pair or team programming is often preferred for immediate feedback, asynchronous code reviews are a valuable alternative when real-time collaboration isn't feasible. This article explores the challenges of asynchronous code reviews, such as delayed feedback and less effective communication, and offers practical strategies to their effectiveness. Key recommendations include providing timely feedback, setting clear expectations, focusing on test coverage, staying curious, and using code reviews as learning opportunities. Adopting these practices can ensure high-quality code, promote knowledge sharing, and maintain a strong collaborative dynamic, even when working asynchronously."
tags = ["Developer-Experience","Developer-Productivity","Quality","Software-Development","Software-Testing","Engineering-Excellence","Software-Craft"]
+++
# How to give outstanding code reviews (if you have to)

Most software companies use code reviews to ensure that at least two people check each part of the code base and maintain its quality. Although I prefer pair or team programming over asynchronous code reviews, I recognize that this isn’t always possible. In such cases, asynchronous code reviews are the next best option.

I see asynchronous code reviews as a last resort to ensure that every piece of code is reviewed by at least two team members. When code is seen by at least two people, this promotes knowledge sharing, shared ownership, and reduces the risk of mistakes. The ideal approach for immediate feedback is pair or team programming. However, when this isn’t possible due to asynchronous work hours or too much work in progress, many teams rely on code reviews. When done correctly, code reviews can also be highly valuable.

Over the years, several times I got feedback from my colleagues that they really appreciated my reviews, and occasionally, they were surprised how I could catch certain issues just by reviewing the code. One colleague once admitted that they would even look into my reviews for other people because those usually provided a good learning opportunity. Thus, I thought I will write down how I approach code reviews.

## The issue with asynchronous code reviews

But let’s start with a brief excursion into the reasons against asynchronous code reviews, as I would opt for a pairing session in the majority of cases. The following list is by no means complete:

1. Asynchronous code reviews slow down feedback. People often wait hours or even days for their code to be reviewed, which stops them from finishing their work and increases tasks in progress. When the review finally arrives, it interrupts their current work and requires them to switch focus again.
2. Communication in asynchronous code reviews is less effective because written messages aren’t as clear as spoken conversations. This can cause reviewers to point out fewer issues, lowering the review’s quality. This problem is worse when the code to be reviewed (like a pull request) is large.
3. People know the code better when they pair on it compared to when they just review it. Thus, I would argue that the knowledge sharing is more effective in a pairing session.
4. True collaboration (pairing/teaming) is the best team building and relationship building exercise that exists. None of the teams where we collaborated a lot needed artificial team building exercises or off-sites to have a strong team-bond and healthy team dynamic. You won’t get this benefit from code reviews.

## How to give (better) asynchronous code reviews

If you really can’t pair/team up on writing the code and thus giving synchronous code reviews while switching roles frequently, you can only try to make your code reviews as valuable as possible. Here are some things to consider:

### 1\. Do them as timely as possible.

Waiting for a code review halts progress and disrupts workflow. A task isn’t complete until it is deployed and working in production. Small changes often wait hours or days for someone to review and merge them. Much of the lead time is spent “waiting for review,” which is inefficient and lowers team performance. It is also frustrating.

I try to start code reviews as soon as I know one is open. The sooner I can give feedback, the better. (The best is still synchronous feedback during pair-programming.) The main goal for the team is to get things out to customers quickly. Being busy with many separate tasks slows this down.

### 2\. Have expectations.

When reviewing code or reading code in general, it is beneficial to have an expectation about what the code should do and how I would do it myself. Doing so will likely trigger surprises that keep me alert, which in turn leads to learning opportunities for myself, but also makes it easier to find things the author might have missed.

Therefore, before starting a code review, I think about the desired outcome, the implementation and common pitfalls upfront.

### 3\. Check tests first.

Once I have thought about what I expect from the PR, I give attention to the tests and see if they cover my expectations or if some of my expectations are not covered by tests.

Tests shall be a good documentation of what to expect and should therefore be comparable with my expectations. If they are difficult to read, I would start suggesting ways to improve readability. If they are missing, this is a red flag or at least justifies extra caution while proceeding with the review.

### 4\. Be curious.

Often, there is no right or wrong, and code reviews are no exception. Despite having expectations, stay open-minded to learn something new. When something surprises me in a code review, I ask for the reasoning / the intent behind it. Chances are high that the author has thought about the code they were writing before.

### 5\. See code reviews as a learning opportunity.

When speaking with engineers about their reasons for giving code reviews, many reasons come up, but “to learn” is rarely one of them. I think, this is a missed opportunity. When we are attentive and open to alternative solutions and willing to ask questions from curiosity to better understand a solution, there is a massive opportunity to learn something while reviewing code.

### 6\. Explain the why.

When you share a different approach or criticize an approach, try to explain the why and why you think it is better. I would often share links to articles or documentation that helps the author to understand the background.

Don’t be too strict on things that don’t really matter. Some aspects are a matter of personal preference. It’s fine to mention your preferred way, but also respect the author’s style and approach. As a team, you might have established guidelines. Formatting guidelines are best enforced by an auto formatter in a pre-commit hook, not by a reviewer.

### 7\. Also highlight positive aspects.

Sometimes we are so focussed on finding mistakes and improvement opportunities that we fail to highlight also the great things and aspects that surprise us positively.

### 8\. Don’t block PRs with uncritical comments.

Occasionally, you might want to point something out without requiring immediate action. Clearly communicate whether your comments are blocking or non-blocking. If you only have “FYI” remarks and the code is ready to be merged, approve the PR right away. This saves time and avoids the need for a re-review. For example, comments like “This would look nicer with a static import” pose minimal risk and aren’t worth delaying the merge.

### 9\. Jump on calls early.

Sometimes, issues are more critical. A change might risk breaking the production system or violate the desired architecture (architecture tests can help here). This is a valuable learning opportunity. The author likely wrote the code in the best way they knew how. If they violated architectural guidelines, it means those guidelines were either not clearly communicated, not understood, or the author doesn’t know how to achieve their goal while adhering to the architecture rules.

Especially when things are a bit more complicated or comments turn to a back-and-forth discussion, I like to jump on a call and discuss the matter in person. This provides a much more efficient space to understand each other and learn from each other. It even provides an opportunity to pair-program on the needed change to ensure that we understand each other and can even ask more questions as they come up.

I would also jump on a call when I find a PR too big to handle or believe that it is completely missing the point and would lead me to add 1000 comments. A quick call and walk-through can help me to understand the PR better and give better comments. Or we can use the call to restructure the PR so that we have multiple cohesive and smaller PRs, which again serves as a good learning opportunity.

## Conclusion

While synchronous methods like pair- or team-programming offer the most immediate and effective feedback, asynchronous code reviews remain valuable when real-time collaboration isn’t feasible. By addressing common pitfalls such as delayed feedback and impaired communication, and by adopting practices like timely reviews, setting clear expectations, and fostering a learning environment, asynchronous code reviews can be significantly improved.

Emphasizing positive aspects, clearly communicating the importance of feedback, and initiating direct discussions when necessary can further enhance the quality and efficiency of code reviews. Ultimately, the goal is to ensure high code quality, promote knowledge sharing, and maintain a collaborative team dynamic, even when working asynchronously.

**This is, in a nutshell, how I do code reviews. How do you do them? Share your approach in the comments!**