+++
title = "Writing and Improving Code with AI (AI for DevEx, Part 1)"
slug = "writing-and-improving-code-with-ai-ai-for-devex-part-1"
image = "/img/import/2023-11-18-writing-and-improving-code-with-ai-ai-for-devex-part-1.png"
date = 2023-11-18T05:00:00
publishDate = 2023-11-18T05:00:00
lastmod = 2023-12-25T11:18:24
description = "In 'Writing and Improving Code with AI', part of the AI for DevEx series, we examine the impact of AI tools like ChatGPT, GitHub Copilot, and AWS CodeWhisperer on software development. The article highlights real-world applications of these tools in code writing, improvement, and testing, underscoring the balance between AI assistance and human expertise in coding."
tags = ["AI-for DevEx","Artificial-Intelligence","Developer-Experience","Developer-Productivity"]
+++
# Writing and Improving Code with AI (AI for DevEx, Part 1)

Artificial intelligence (AI) is here to stay. It’s become a part of our daily lives through ChatGPT, Midjourney, or even the occasional frustrating chatbot. Despite their imperfections and the mix of risks and opportunities they present, AI tools are transforming the way we create, manage, and improve software.

This article is part of a series focusing on how Artificial Intelligence tools, particularly those based on large language models (LLMs), enhance developer experience and productivity. I’ll share real-world examples from my teams and myself, demonstrating how these tools boost our efficiency, quality of work, and enjoyment.

## Article Series Overview

AI has the potential to improve developer experience and productivity significantly. AI can add a lot of value in [multiple areas](/blog/tag/ai-for-devex/), such as:

1. 👉 _This article:_ Writing and Improving Code with AI Support
2. [Custom GPTs as a Developer Companion](/blog/custom-gpts-as-a-developer-companion-ai-for-devex-part-2/)
3. [How Testing and Quality Assurance Change Through AI](/blog/how-testing-and-quality-assurance-change-through-ai-ai-for-devex-part-3/)
4. [How AI Improves Collaboration and Communication](/blog/how-ai-improves-collaboration-and-communication-ai-for-devex-part-4/)
5. [What AI Tools mean for Deployment, Maintenance and Security](/blog/writing-and-improving-code-with-ai-ai-for-devex-part-1/)
6. [Inspiration on AI for General Productivity Improvements](/blog/llms-for-general-productivity-improvements-ai-for-devex-part-6/)
7. _<🙋‍♂️Give me suggestions for further articles – I want to write about what is interesting to you! 😊>_

In this article, I am focussing on writing and improving code.  
Let’s dive into some of the opportunities AI brings already today:

## Writing and Improving Code 

I use different AI tools for different tasks and know well which one to choose for my needs. 

ChatGPT Plus is helpful when there’s no specific AI tool available. Creating [custom GPTs](https://openai.com/blog/introducing-gpts) for particular tech needs makes it easier and reduces the need to give background information each time. (More in part 2)

Developers now have various code generation tools in their IDEs, like [GitHub Copilot](https://copilot.github.com), [AWS CodeWhisperer](https://aws.amazon.com/codewhisperer/), and the original ChatGPT as a fallback.

### Smarter Autocompletion

One of the basic capabilities of AWS CodeWhisperer and GitHub copilot is to autocomplete more significant parts of the code than just the next symbol.

![GitHub Copilot suggesting an entire line of code that makes sense based on the context.](https://unblocked.engineering/wp-content/uploads/2023/11/github-copilot-autocomplete.png)

GitHub Copilot suggesting an entire line of code that makes sense based on the context.

In the above image, GitHub Copilot is suggesting a full line of code to add, which represents another test case of a test I am writing.

### Generating Implementations

Here’s an easy-to-follow example where I use AWS CodeWhisperer and ChatGPT to create Go code that meets specific test cases. For these large language models (LLMs) to effectively write code, we must clearly define the code’s purpose. This can be done either in simple text or, as in this case, through test cases. By using test cases, I can run them to check if the code works as intended.

![Using AWS CodeWhisperer to generate code](https://unblocked.engineering/wp-content/uploads/2023/11/aws-codewhisperer.png)

Using AWS CodeWhisperer to generate code

Another tool at our disposal is ChatGPT. For instance, I created a specialized GPT named “Go Guru” to help with Go projects. It’s tailored to understand that I work with Go, GCP, Elastic, and other technologies in this project. This means it can provide relevant responses to my queries without needing extra context each time.

![My custom built GPT for Go immediately generates the function that satisfies this test.](https://unblocked.engineering/wp-content/uploads/2023/11/gpt-go-guru-code-generation.png)

My custom built GPT for Go immediately generates the function that satisfies this test.

### Uncovering Test Gaps

But of course, we must not stop there. You might have noticed that I have only provided very few test cases. Comparing the ChatGPT and AWS CodeWhisperer solutions, you see the check for `sourceWidth == 0` in the ChatGPT answer. Something that I have (intentionally) not specified in my tests. So what else did I miss?

![List of test cases that I might consider adding.](https://unblocked.engineering/wp-content/uploads/2023/11/chatgpt-missing-testcases.png)

List of test cases that I might consider adding.

### Generating Additional Test Cases

In the above image, you can see that ChatGPT gives me a pretty comprehensive list of cases that I still would like to cover. Therefore, ChatGPT can be a great assistant for finding cases I might have missed. And, of course, it can also give me code for those cases:

![ChatGPT Generated Test Cases](https://unblocked.engineering/wp-content/uploads/2023/11/chatgpt-generate-testcode.png)

ChatGPT Generated Test Cases

### Changing The Behavior 

Let’s say I would like to change the behavior to not upscale but return the `sourceHeight` instead.

![ChatGPT Generated Updated Behavior](https://unblocked.engineering/wp-content/uploads/2023/11/Screenshot-2023-11-14-at-09.33.34.png)

ChatGPT Generated Updated Behavior

In this example, ChatGPT provides me with new test cases and an updated implementation.

I can get similar behavior with GitHub Copilot in IntelliJ as follows:

![Instructing GitHub Copilot with code comments](https://unblocked.engineering/wp-content/uploads/2023/11/github-copilot-todo.png)

Instructing GitHub Copilot with code comments

I am writing my intent in a `TODO` comment in this example. GitHub Copilot gave me a suggestion on how to extend the test cases. Note that here, I like the ChatGPT 4 response more, as it gave better test names and also a new implementation.

### Creating Automated Documentation

_Disclaimer: The above example is too simple, and I would not write documentation despite the test cases._

That being said, code generation tools can also help us by suggesting documentation if we need it. In Go, we start function documentation with `/// ` – after that, AWS CodeWhisperer and GitHub Copilot give okay-ish documentation based on the function’s implementation.

Of course, we can also paste code into ChatGPT and ask it to explain or document it.

### Creating Tests for Existing Code

_Disclaimer: In general, I am for a test-first approach. However, you might find untested code you would like to refactor when working with legacy code._

It is a good practice first to secure the code with tests as much as possible and then start the refactoring. Here, GitHub Copilot can help. In the Copilot Chat (Beta in IntelliJ), we can ask to generate tests for the highlighted code using the `/tests` command:

![Tests generated by GitHub Copilot](https://unblocked.engineering/wp-content/uploads/2023/11/copilot-generated-tests.png)

Tests generated by GitHub Copilot

I do not like the generated tests, but they are a good start. As it is a chat, I can ask to simplify the tests, giving me a structure similar to my tests above. 

The quality of tests largely depends on how test-friendly the code is. Code not initially developed with test-driven development (TDD) or without preliminary tests tends to be less testable. Under such circumstances, even advanced tools like LLMs can’t perform wonders. They might generate complex and brittle tests. While these can be a starting point, they’re no substitute for a deep understanding of handling legacy code. I recommend Michael C. Feathers’s book “[Working Effectively with Legacy Code](https://www.goodreads.com/en/book/show/44919).” Though nearly 20 years old, it’s still a valuable guide for tackling difficult-to-test code and safely transforming it into a well-tested version.

## Conclusion

AI tools are helpful in writing, optimizing, and testing code but don’t replace solid software development practices. They help experienced engineers build better software faster and are great for learning new tools and technologies efficiently.

While they can give valuable feedback, their feedback can be misleading or plain wrong at times. Therefore, they require human judgment and understanding to be helpful. 

AI-based code generation excels when you first define specifications and automated tests. Describe the behavior, let an LLM generate the code, and then run your tests to ensure correctness. This method can speed up test-first and TDD processes by focusing more on behavior definition while AI handles test compliance. However, remember that AI-generated code may need refining for clarity, which is also an area where AI can assist.

**Over to you: How do you use AI in software development?**