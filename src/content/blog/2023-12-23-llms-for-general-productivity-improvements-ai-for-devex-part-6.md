+++
title = "LLMs for General Productivity Improvements (AI for DevEx, Part 6)"
slug = "llms-for-general-productivity-improvements-ai-for-devex-part-6"
image = "/img/import/2023-12-23-llms-for-general-productivity-improvements-ai-for-devex-part-6.png"
date = 2023-12-23T05:00:00
publishDate = 2023-12-23T05:00:00
lastmod = 2023-12-21T06:12:20
description = "This article explores the transformative role of Large Language Models in enhancing software development productivity. It delves into AI's integration in coding, collaboration, and automation, offering insights for engineers to harness AI in their daily tasks."
tags = ["AI-for DevEx","Artificial-Intelligence","Developer-Experience","Developer-Productivity"]
+++
# LLMs for General Productivity Improvements (AI for DevEx, Part 6)

Welcome to part 6 of [AI for DevEx](/blog/tag/ai-for-devex/). In this last part of the series, I will give some inspiration on how AI, namely LLMs, can help engineers with their everyday tasks.

But first, let’s start with a brief recap:

1. In **[part 1](https://nudge.unblocked.engineering/p/writing-and-improving-code-with-ai)**, we explored how LLM-based tools can support us in writing and improving code. I showed examples of how we can **test-drive our AI code generation** and thus automatically verify the generated code. Furthermore, we dove into discovering edge cases and writing documentation.
2. In **[part 2](https://nudge.unblocked.engineering/p/custom-gpts-as-a-developer-companion)**, we discussed how custom GPTs can enhance the interaction experience by adding context and instructions. I demonstrated how we can easily create a GPT to serve us as “Code Buddy” and how it creates more accurate responses despite using shorter prompts.
3. **[Part 3](https://nudge.unblocked.engineering/p/how-testing-and-quality-assurance)** shows advances in testing and quality assurance and demonstrates two LLM-based tools for automated testing and their limitations.
4. From there, we moved on to the _”softer”_ topics **communication and collaboration** in **[part 4](https://nudge.unblocked.engineering/p/how-ai-improves-collaboration-and)**. We explored how AI tools can enhance synchronous and asynchronous communication and increase the value of documentation.
5. In the last part, **[part 5](https://nudge.unblocked.engineering/p/what-ai-tools-mean-for-deployment)**, we looked into the important topic of **deployments, operations, and security** and which AI tools exist today to make the lives of engineering teams easier in this realm.

In this article, I want to close this series (for now) with some basic examples of how LLMs can simplify, accelerate, and enrich day-to-day tasks that engineers face countless times per day.

## ChatGPT as a Google Replacement

I noticed a trend in how I am using (or not using) Google since having access to ChatGPT (4). I use Google (or other search engines) less these days.

Search engines provide lots of information on a topic, but it’s up to us to find what we need. Often, we search for a small detail among many web pages, which can be tiring and time-consuming. Most websites don’t put answers right at the beginning, usually in the middle. ChatGPT, trained on many web pages, likely knows about the information you seek. I’ve mentioned some examples in my previous articles.

Therefore, ChatGPT can be a great help …

### … when searching for that one-liner

* [”How again do I check if a string is empty in a bash script?”](https://chat.openai.com/share/9ce50dd5-e687-4ccf-bb98-9965a31fa31d)
* [“Gcloud list latest blobs in a bucket.”](https://chat.openai.com/share/be7c340f-8b7e-4dfc-b06b-5ee81e3c510d)
* [“How to do a POST request from a TypeScript Node app?”](https://chat.openai.com/share/1003d69e-d3d0-45e2-90f1-8a8e5a741587)

These are just some examples of questions that developers would often turn to Google and StackOverflow to find answers to. ChatGPT can provide a decent result more quickly. Furthermore, I can continue my conversation with ChatGPT on this topic, as you can see following the link of the last example.

This is a big benefit because I don’t have to make many different Google searches and combine the results. Tools like ChatGPT are a great help when working and finding something unknown. ChatGPT can help fill these gaps and improve understanding.

This is also extremely useful …

### … when diving into a new topic

Diving into a new topic usually involves reading books, taking courses, playing around, and reading more articles…

We’ll use different methods based on how much we want to learn about a topic. Where to begin? I often start with Google, looking for articles from trustworthy sources or authors I know. Then, I read them to get a basic understanding and make a summary of the key ideas.

This is something ChatGPT can help with, too. 

See [this fictive example](https://chat.openai.com/share/a94780c0-f824-4be1-830c-a4384c1db2e4) of how to learn about domain-driven design. ChatGPT can list some of the main concepts, and I can use this input to dig deeper into the parts that are unclear to me while skipping the parts that I already know. For a first intro to a topic, this usually is good enough. 

This is great because we can return to a chat to deepen and check our understanding after learning more elsewhere. I often keep one or more notes in NotePlan for topics I’m exploring. The main note often links to a chat I used for a good overview.

### … when looking for confirmation or reassurance

Sometimes, we remember roughly how to accomplish a certain task. However, we might not be quite sure about the exact syntax. Maybe there is even a better way to achieve the same thing. Here, asking ChatGPT how to solve the task can either confirm our idea or open up a space of options to explore if they look better than ours.

### Limitations of GPTs and Words of Warnings

As the name of these class of tools tells _(GPT stands for Generative Pre-trained Transformer)_, the underlying models are pre-trained on data available at training time. GPT-4, for example, is based on web pages, books, and other resources and was last trained in April 2023.

This means two things:

1. GPT doesn’t know about information coming out after its last update. For instance, if an API changed or a new tool was created after that date, ChatGPT’s answers about these topics might not be reliable. I observed this when asking about the `gcloud` CLI tool, where the responses often didn’t work with the current version.
2. The internet and also books not only contain exceptionally awesome advice but a lot of misinformation, bad practices, and wrong answers, too. I have seen ChatGPT output horrible or just plain wrong code with confidence.

Therefore, take the warning at the bottom of each chat seriously and double-check answers when in doubt.

![ChatGPT can make mistakes. Consider checking important information.](https://unblocked.engineering/wp-content/uploads/2023/12/chatgpt-can-make-mistakes.png)

ChatGPT can make mistakes. Consider checking important information.

I use my understanding and reasoning to decide when to double-check something. For example, if the answer is an `ls` command, I can try it, as the worst case is that ChatGPT hallucinates some arguments or the command does not exactly return the information I wanted. Consider this more dangerous example:

```
find /path/to/directory -type f \( -iname "*.jpg" -o -iname "*.png" -o -iname "*.gif" \) -delete

```

If I am unsure if this command only works on the desired files, I would not execute it, as it might delete files I do not want to delete. I would either check the man pages, do more research, or (in this case) execute it without `-delete` first.

_Side-note: I would argue that, in general, you should not trust things on the internet without a second thought. The same rule applies to AI-generated responses._

## Implications for Task Automation

The advancements of LLMs have great implications for task automation, be it repetitive or one-time tasks. Before automating any process, we should consider a few things:

1. How well do we understand the process?
2. How long will it take to automate it?
3. How often is it executed, and how long does it take to execute manually?

There are more questions you could consider, but these are the ones where LLMs drastically change the numbers. LLM support can significantly speed up writing shell scripts and other code, completely changing the ROI estimation (Points 2 and 3).

Furthermore, explaining the process to ChatGPT forces you to think about it step by step and write it down in simple language. This is an approach some of the greatest engineers I know followed way before ChatGPT: writing down the steps they want to automate in a code comment and then figuring out how to automate each of them. ChatGPT speeds up the “figuring out” part.

### Example 1: Creating Shell Scripts with ChatGPT

Consider this example:

```
# 1. Wait for the Kubernetes Service istio-ingressgateway in the namespace istio-system to get a public IP address.
# 2. Get that external IP address.
# 3. Update the DNS entries in Google Cloud DNS (GCloud project: production-123456) so that all DNS Entries specified in the Kubernetes Certificate ingress-cert in the namespace istio-system resolve to that IP.

```

Automating this involves knowing the syntax for the `kubectl` command that retrieves the external IP from the `istio-ingressgateway`. It also involves waiting for this to be available. Furthermore, it involves retrieving the hostnames from the certificate `ingress-cert`. Last but not least, for each hostname, the `glcoud` command needs to be used to update the DNS records.

I understand most of these steps and can quickly evaluate if the code is correct. Therefore, it’s a good idea for me to ask ChatGPT to generate the code. Figuring out certain parameters or shell syntax might take some time, but I can easily determine if a script is accurate and safely test any steps I’m unsure about.

You can see this example in action [here](https://chat.openai.com/share/29d5f97f-ba25-4088-aa23-4d966a36680d). Most of the generated code does what it should. Only the `gcloud dns record-sets transaction ` calls are off. The idea is correct, but the syntax in the recent version of `gcloud` is different. This is when I leave ChatGPT and turn toward the documentation or the man pages to understand how the commands look correctly.

ChatGPT saved me a lot of time by creating the skeleton and pointing me in the right direction. The script just needed a bit of tweaking to work for our context.

### Example 2: Creating an OpenAPI Spec from an Example

I am a big fan of [Readwise](https://readwise.io/)and frequently use their API for adding documents and retrieving highlights.

Recently, I built a GPT that summarizes my daily highlights and draws connections between them. This GPT needs to access their API, so I needed to supply an OpenAPI spec. Unfortunately, I could not find one on the internet, and I did not want to spend time figuring out how to build such a spec manually for this toy project (this happened mostly automatically in past projects).

To get started and have an 80%-solution, I copied the part from the [Readwise API page](https://readwise.io/api%5Fdeets) I was interested in (“Daily Review List”). I then prompted ChatGPT to create the spec for me like so:

> Create an OpenAPI spec to be used in a GPT based on this API example: <section-from-readwise>

The result was a valid OpenAPI spec that I pasted in the GPT to connect it to the API. A process that would have taken half an hour if done manually now took seconds. You can see the example [here](https://chat.openai.com/share/4ed41075-4ae0-48bb-910b-69bd0fba1a92).

### Other Examples

In the past months, I have successfully used ChatGPT to perform the following tasks for me:

* Create a histogram for the distribution of data in a SQLite database.
* Convert a JSON list into an object following certain rules.
* Extract certain parts from a complicated and lengthy string without providing a regular expression.
* …

This list is highly incomplete but should serve as an inspiration for which kind of tasks ChatGPT could potentially do or automate for us.

**I want to learn from you!: For which tasks are you using ChatGPT?**

## Conclusion

Large language models (LLMs) like ChatGPT have greatly changed how developers work and increased productivity. This series shows these AI tools do more than automate tasks or create code. They improve the development process, including writing, testing, communicating, collaborating, and solving problems.

The examples highlighted throughout the series demonstrate the versatility of LLMs in various aspects of development work. Whether generating code snippets, aiding in research, or providing quick solutions to complex problems, these AI tools have shown immense potential in making developers’ lives easier and more efficient.

It’s important to know that these AI models have limits and need human guidance. They are very helpful for many tasks but aren’t perfect. We should use them to help us, not replace human skills.

AI is getting more advanced, leading to better uses in many areas. The future looks promising, with many opportunities. It’s important to use these AI tools wisely, knowing what they can and can’t do, to improve our work and creativity.

**Over to you: Are you already using AI tools to enhance developer experience and productivity? What is your experience?**