+++
title = "Custom GPTs as a Developer Companion (AI for DevEx, Part 2)"
slug = "custom-gpts-as-a-developer-companion-ai-for-devex-part-2"
image = "/img/import/2023-11-25-custom-gpts-as-a-developer-companion-ai-for-devex-part-2.png"
date = 2023-11-25T05:00:00
publishDate = 2023-11-25T05:00:00
lastmod = 2023-12-21T06:11:15
description = "Discover how OpenAI's custom GPTs are changing software development. Learn about their benefits for efficiency and teamwork, and see real examples of how they're used. Ideal for developers and leaders looking to stay ahead in tech."
tags = ["AI-for DevEx","Artificial-Intelligence","Developer-Experience","Developer-Productivity","Engineering-Excellence","Software-Craft"]
+++
# Custom GPTs as a Developer Companion (AI for DevEx, Part 2)

Part 2 of “AI for DevEx” focuses on the new GPTs announced by OpenAI on November 6th and how they can enhance the experience for developers.

In part 1, we focussed on [writing and improving code with AI](https://nudge.unblocked.engineering/p/writing-and-improving-code-with-ai). This part will explore creating customized GPTs with additional context about our system.

You can read the Introduction to GPTs by OpenAI [here](https://openai.com/blog/introducing-gpts).

> You can now create custom versions of ChatGPT that combine instructions, extra knowledge, and any combination of skills.

They are part of ChatGPT Plus and open up a new world. Let’s get started with a brief introduction.

## Introduction to OpenAI’s New GPT Models

You can now create your own GPTs easily without coding. By talking with ChatGPT, you can give extra details, upload files, and choose APIs for the GPT to use.

This allows us to customize GPTs for specific tasks. It saves a lot of time because we don’t need to give the same background information in every chat. The context is already included in the GPT.

GPTs are designed to make things like this easier. You can ask ChatGPT to create a test for your code, and it already knows your preferred test framework and style. This is just one example of what GPTs can do.

Let’s look into a specific example of how to build a Custom GPT for your Tech Stack.

## Custom GPTs for Your Tech Stack

When developing with ChatGPT, you often ask related questions about your project. This includes the programming language, frameworks, and tools you use. Rather than repeating this context in each chat, you can create and train a specialized GPT for your project and use it whenever you have a question or task related to that project.

In this example, we will create a GPT for a fictive project that uses Java, Spring Boot, Gradle, Spock for Testing, AWS EKS, AWS S3, and a Postgres DB.

### Building the GPT

Building a GPT can be done via a conversation in natural language.

![Starting a conversation to build a GPT](https://unblocked.engineering/wp-content/uploads/2023/11/01-custom-gpt-start.png)

Starting a conversation to build a GPT

![Ongoing Conversation](https://unblocked.engineering/wp-content/uploads/2023/11/02-custom-gpt-setting-a-name.png)

Ongoing Conversation

![Creating a GPT image](https://unblocked.engineering/wp-content/uploads/2023/11/03-custom-gpt-further-customization.png)

Creating a GPT image

![Setting tone and and output requirements](https://unblocked.engineering/wp-content/uploads/2023/11/04-custom-gpt-tone.png)

Setting tone and and output requirements

![The Spring Buddy is ready to be used.](https://unblocked.engineering/wp-content/uploads/2023/11/05-custom-gpt-ready-now.png)

The Spring Buddy is ready to be used.

In our conversation, you can see how ChatGPT and I worked together to create a custom GPT named “Spring Buddy.” I customized it to my needs, and now I can save and use it.

Furthermore, the GPT Builder offers a playground that I can use to write prompts and see how the GPT behaves. I can use my observations to give further instructions.

### Using the GPT

Let’s try an example: 

> Generate an API + tests that can be used to store books. Books consist of a cover image, a title and an author.

Note that my prompt does not mention any technology and yet, ChatGPT knows exactly what I want.

_Disclaimer: The following answers do not exactly match how I would like to build such an app. This example shows that ChatGPT can act with my previously defined context but I still need to check if the answers are good for me._

![Asking Spring Buddy to create an API to store books + tests.](https://unblocked.engineering/wp-content/uploads/2023/11/06-run-gpt-steps.png)

Asking Spring Buddy to create an API to store books + tests.

![Generated Model and Repository](https://unblocked.engineering/wp-content/uploads/2023/11/07-run-gpt-model.png)

Generated Model and Repository

![Generated Service](https://unblocked.engineering/wp-content/uploads/2023/11/08-run-gpt-service.png)

Generated Service

![Generated Controller](https://unblocked.engineering/wp-content/uploads/2023/11/09-run-gpt-controller.png)

Generated Controller

![Generated Test Boilerplate](https://unblocked.engineering/wp-content/uploads/2023/11/10-run-gpt-test.png)

Generated Test Boilerplate

As you can see, ChatGPT created most of the code needed to add such an API to my service. For some reason it decided to now write the test, though. Because we are in a conversation, I can ask it to generate those, too.

![Asking Spring Buddy to finish the test](https://unblocked.engineering/wp-content/uploads/2023/11/11-run-gpt-write-test.png)

Asking Spring Buddy to finish the test

![The test implementation](https://unblocked.engineering/wp-content/uploads/2023/11/12-run-gpt-test-response.png)

The test implementation

As I said before, the generated code isn’t always as I like it. I would probably use a hexagonal architecture style for more complex projects, provide some fake in-memory replacements for repositories and blob storage, and rely less on mocking.

The code from the GPT isn’t perfect, but it can save time in regular coding tasks. For example, when I asked the GPT to help deploy the app, it created a `Dockerfile` and `deployment.yml` for Kubernetes. This might be basic, but it’s helpful for engineers who don’t create these files often.

**To summarize:** Custom GPTs can act as a companion during software development, not only for coding challenges but also to answer tech-stack-related questions.

In an existing project, we could theoretically improve the behavior by uploading parts of our existing code into the GPT.

## Integrating Custom GTPs with Your Development Tools

GPTs can interact with the outside world. With the introduction of custom GPTs, OpenAI also introduced the ability to define actions that GPTs can execute.

We can now provide an [OpenAPI spec](https://spec.openapis.org/oas/latest.html) in the building process of a GPT and use those actions in the GPT. 

I have created a GPT called “ADR Assistant” to assist users in writing architecture decision records (ADRs) and uploading them to an API. I am using my [N8N](https://n8n.io) instance to provide this API for demonstration purposes. This setup includes a workflow that takes the input and creates a file in a GitHub repository to store the ADR.

### Creating the ADR Assistant

I started with an initial prompt like the following:

```
I want a GPT that assists me with writing Architecture Decision Records (ADRs). An ADR has the structure of the attached Markdown file (adr.md)

I will provide bullet points. Please create an ADR in this structure using simple, concise and brief and to the point sentences.

```

I provided the file `adr.md` alongside this message. It contains an example ADR template. After agreeing on a name and picture, I went to the configuration to configure the action.

![The (mostly) autogenerated GPT configuration.](https://unblocked.engineering/wp-content/uploads/2023/11/13-adr-gpt-config.png)

The (mostly) autogenerated GPT configuration.

Under actions, you can see that I have configured the `my-custom-server` action (name changed). Actions can be defined via an OpenAPI spec like the following:

![OpenAPI Spec for my N8N workflow](https://unblocked.engineering/wp-content/uploads/2023/11/14-adr-gpt-action.png)

OpenAPI Spec for my N8N workflow

My workflow takes a request to the webhook, converts it into a call to the storage backend, and then returns a URL for the final ADR. A benefit of this setup is that I can easily change the storage backend, like switching to a Notion database for storing ADRs, if needed.

![Extremely simply N8N Workflow](https://unblocked.engineering/wp-content/uploads/2023/11/23-adr-assistant-n8n-backend.png)

Extremely simply N8N Workflow

And that is it. Now, let’s see it in action.

### The ADR Assistant in Action

First, you can see that I am using one of the calls to action of this GPT. The assistant prompts me to provide details about the ADR I want to create.

![The assistant prompts me for the ADR details.](https://unblocked.engineering/wp-content/uploads/2023/11/15-adr-assistant-in-action.png)

The assistant prompts me for the ADR details.

I am answering with an unstructured collection of bullet points I have quickly jotted down.

![A raw collection of input for the ADR](https://unblocked.engineering/wp-content/uploads/2023/11/16-adr-assistant-content-bulletpoints.png)

A raw collection of input for the ADR

The assistant still has questions, which I answer briefly:

![Briefly answering assistant questions](https://unblocked.engineering/wp-content/uploads/2023/11/17-adr-assistant-asks-questions.png)

Briefly answering assistant questions

The assistant now creates a draft for the ADR and asks me if I want to upload it.

![The Draft ADR](https://unblocked.engineering/wp-content/uploads/2023/11/18-adr-assistant-creates-draft.png)

The Draft ADR

As you can see in the following screenshot, I have changed my mind and asked for an ADR with fewer bullet-points and more cohesive text.

![I changed my mind.](https://unblocked.engineering/wp-content/uploads/2023/11/19-adr-assistant-refining-the-adr.png)

I changed my mind.

The assistant does not disappoint:

![The Next Version of the ADR](https://unblocked.engineering/wp-content/uploads/2023/11/20-adr-assistant-rewriten-adr.png)

The Next Version of the ADR

I am satisfied with this version. Time to store it, discuss it, review it, and finalize it.

![The ADR is sent to my N8N instance.](https://unblocked.engineering/wp-content/uploads/2023/11/21-adr-assistant-upload.png)

The ADR is sent to my N8N instance.

Now, the magic dance of GPT and N8N unfolds. The GPT is calling the N8N webhook, providing some tags, a title and the content of the ADR. My N8N workflow uses this information to create a file in a GitHub repository and return a URL to that newly generated file.

![The ADR in GitHub](https://unblocked.engineering/wp-content/uploads/2023/11/22-adr-assistant-adr-in-github.png)

The ADR in GitHub

And that’s it. We have successfully integrated a GPT with an API for a more complex use case.

_Note: This is a made-up example to show what GPT can do. In a real situation, I might not create ADRs this way. Instead, I’d likely write them in my preferred tool (probably Notion), using AI to help make certain parts clearer if needed._

## Sharing the GPTs with Your Team

GPTs are a fantastic tool for yourself, but it does not stop there. You can also share them with your team. This way, everybody with a ChatGPT Plus account can use them if they have the link.

With [ChatGPT Enterprise](https://openai.com/enterprise), you can also share them safely within your company only. The Enterprise plan also offers higher speeds and data privacy. OpenAI promises not to use Enterprise data for training.

OpenAI is currently launching an App Store for GPTs. Once it is live, looking for GPTs that support your use cases might be worthwhile.

**Want to play around with the two GPTs I built for this article?** — comment, and I will share them with you. _I have removed the upload feature from the ADR Assistant for privacy reasons._

## Conclusion

In conclusion, OpenAI’s custom GPTs represent a significant leap in enhancing the developer experience. They allow for:

* **Personalized Development Tools**: Tailoring GPTs to specific project needs, improving efficiency.
* **Streamlined Workflows**: Saving time and simplifying processes in coding and specialized tasks.
* **Enhanced Team Collaboration**: Facilitating better teamwork by sharing custom GPTs within organizations.
* **Integration with Tech Ecosystem**: Allowing interactions with various development tools and APIs.
* **Future Prospects**: With the upcoming OpenAI App Store, broader adoption and utility of custom GPTs are expected, marking a new era in software development.

AI is becoming more important in software development. It’s a good idea to try these tools to see how they can speed up your work.

**Have you used the custom GPTs already? How are you using them? Share your use cases in the comments!**

Stay tuned for part 3 next week to explore how testing and quality assurance change through AI. 🚀