+++
title = "How Testing and Quality Assurance Change Through AI (AI for DevEx, Part 3)"
slug = "how-testing-and-quality-assurance-change-through-ai-ai-for-devex-part-3"
image = "/img/import/2023-12-02-how-testing-and-quality-assurance-change-through-ai-ai-for-devex-part-3.png"
date = 2023-12-02T05:00:00
publishDate = 2023-12-02T05:00:00
lastmod = 2023-12-21T06:13:35
description = "This article, part of the \"AI for DevEx\" series, explores the role of AI in software testing and quality assurance. It examines AI's potential in automating test case generation and UI/end-to-end tests, and reviews tools like ZeroStep and auto-playwright. The piece highlights the integration of testing in the development process and the current best use of AI in supporting test creation and testability. It concludes by anticipating future AI advancements in testing and code reviews."
tags = ["AI-for DevEx","Artificial-Intelligence","Developer-Experience","Developer-Productivity","Software-Craft"]
+++
# How Testing and Quality Assurance Change Through AI (AI for DevEx, Part 3)

Part 3 of the [AI for DevEx series](/blog/tag/ai-for-devex/) examines testing and quality assurance. It builds on [Part 1](https://nudge.unblocked.engineering/p/writing-and-improving-code-with-ai), where we saw how AI and Large Language Models can assist in coding. We focused on how AI can generate test cases for unit and integration tests there.

But the possibilities do not stop there. Some early-stage solutions exist for using AI for writing and executing automated UI and end-to-end tests.

## Testing and QA as part of Developer Experience

Before we dive into the meat of this article, I briefly want to stress why I consider experience around testing and quality assurance as important aspects of developer experience.

1. To me, quality assurance and testing are essential to developing working and maintainable software. For an engineering team to own an entire value stream, they need to have experience in testing and quality assurance.
2. Quality cannot be assured after the fact. It needs to be built in from the beginning. Only if we consider quality and testability while building software, we will we obtain a maintainable, testable, and high-quality product.
3. To get the best performance and quality, engineering teams should have the skills to build quality software, not just rely on a QA team. If there is a QA team, they should help the engineering teams to build and test their software effectively. Testing should not just be a separate service.
4. Testing and quality assurance are integral parts of software development and thus are essential for everyone who develops software together (software engineers, QA experts, etc.)

## AI for Testing

It might sound scary to use artificial intelligence in tests. How do we know the test is doing what it should? Thinking more about it, we can differentiate between using AI for asserting certain behaviors and using AI for executing specific actions.

One of the most significant pain points of UI-level testing is its fragility. A selector changes, and BOOM! A test fails. However, from a user perspective, nothing has changed. Can AI help us to solve this pain?

It might be possible! My research found three solutions that build on [Playwright](https://playwright.dev/) and add AI capabilities while writing and executing tests. I tried two of them out and share my experiences below.

_Note: There might also be solutions for other testing frameworks, such as [Selenium](https://www.selenium.dev) or [Cypress](https://www.cypress.io), but if you are still using them, you might want to check out [Playwright](https://playwright.dev). Thank me later._

### Using AI in Playwright Tests with [ZeroStep](http://zerostep.com)

ZeroStep is a SaaS solution executing actions in a Playwright test using AI. Their library introduces an `ai` command that takes natural language and executes commands accordingly. They offer a paid service, and the free tier allows up to 1,000 `ai` calls per month.

The following code is a perfectly valid Playwright + ZeroStep test:

```
test('Testimonial slider works', async ({page}) => {
    await page.goto('https://unblocked.engineering/')

    const aiArgs = {page, test}

    await ai('Accept the cookie banner.', aiArgs)
    await ai('Scroll to the Testimonials.', aiArgs)
    const first = await ai('Get the full testimonial text.', aiArgs)
    await ai('Go to the next testimonial.', aiArgs)
    const second = await ai('Get the full testimonial text.', aiArgs)
    expect(first).not.toEqual(second)

    await ai('Go to the previous testimonial.', aiArgs)
    const firstAgain = await ai('Get the full testimonial text.', aiArgs)
    expect(first).toEqual(firstAgain)
})

```

As you can see, in this example, I am using `ai` to control the browser and retrieve data from it. I am using Playwright’s `expect` function to verify assumptions about it.

#### Considerations about this test

Writing tests like this looks like fun. However, there are, of course, drawbacks. First of all, calling `ai` is extremely slow. The [test above](https://github.com/TobiasMende/testing-with-ai-demo/blob/main/zerostep-testing/tests/zerostep.spec.ts) took 15 seconds to execute. The same test with ([Playwright only](https://github.com/TobiasMende/testing-with-ai-demo/blob/main/zerostep-testing/tests/playwright-only.spec.ts)) took only 2 seconds.

However, my website (using WordPress + Elementor) is not exactly what you would call _testable_. Given this, it is surprising how simple it was to write the above test. For comparison, I have also used the Playwright recorder to create a Playwright-only alternative of the same test. It uses pretty ugly locators such as `div:nth-child(2) > .elementor-testimonial > .elementor-testimonial__content`, doomed to break on the next Elementor update.

Therefore, AI can help to test parts that are hard to test at the cost of speed (and potentially money).

The test uses `ai` for almost all interactions. I would use `ai` less in real situations and focus on better selectors. AI is helpful for flexible tasks, like filling forms with fake data. AI will fill it automatically if a new required field is added to a form.

Personally, I would like a combined approach; for example, the `ai` call could be used to resolve a selector/action on the first run, which can then be checked in with the code (like a snapshot in snapshot testing). Then, during a CI run, it would only execute the `ai` call if the selector fails to add resilience.

_You can find the full code examples for ZeroStep [here](https://github.com/TobiasMende/testing-with-ai-demo/tree/main/zerostep-testing)._

#### Considerations about ZeroStep

ZeroStep is easy to use and tempting. It is a very young product. Therefore, time will tell how it will be adopted and how much faster the `ai` calls can become. Using AI to write tests can be much faster. If it gets faster and more trusted, it could become an important tool in testing.

Behind ZeroStep is the company Reflect Software Inc., founded in 2019\. It is known for its no/low-code test automation platform [Reflect](https://reflect.run), which now provides AI capabilities similar to ZeroStep’s `ai` call.

One thing I appreciate is their desire to improve their product. One of the co-founders contacted me after I signed up and used ZeroStep to learn from my experience. This is a great way to learn from users. – We will talk next week. 

### Using AI in Playwright with [auto-playwright](https://ray.run/blog/auto-playwright)

Another new kid on the block (let’s face it, regarding testing with AI, there are only “new kids”) is `auto-playwright`. In contrast to ZeroStep, `auto-playwright` uses OpenAI as a backend. It is an [open-source library](https://github.com/lucgagan/auto-playwright) that doesn’t come with its own SaaS but requires a developer account on the [OpenAI platform](https://platform.openai.com).

While the `auto` function of `auto-playwright` almost looks like a drop-in replacement for ZeroStep’s `ai` function, it seems less powerful and solid than ZeroStep.

When trying to convert the above ZeroStep test to an auto-playwright test, the test already failed at accepting the cookie banner. OpenAI tried to guess how to identify the “Accept all” button. In various executions, its guesses ranged from `button[title=\'Accept Cookies\']` over `'button[data-cookiebanner="accept_all"]` to `button[aria-label=\'Accept all cookies\']`. All good guesses, however, accepting the banner is done via a link (`a`).

You can find the code for this example [here](https://github.com/TobiasMende/testing-with-ai-demo/tree/main/auto-playwright-testing).

#### Conclusions on `auto-playwright`

Given that auto-playwright is supposed to send the sanitized HTML of the webpage to OpenAI, the behavior was surprising, as the attempted actions seemed like arbitrary guesses without context. 

I aborted my auto-playwright excursion here. It might work better with a better testable application and wording closer to the button/link labels. However, in that case, I do not see any real advantage over recording tests using Playwright and adding assertions where I need them.

This experiment was quite expensive, too. I was trying to execute them ten times. My tests always failed at the first `auto` call. This experiment created roughly 5$ in OpenAI costs. (Roughly 400,000 context tokens and 1,000 generated tokens with the GPT 4 Turbo Model). Sending the HTML with every `auto` call isn’t exactly cheap with OpenAI.

In conclusion, I will keep an eye on this library but would not consider it for additional experiments or production usage in the current state.

## Where to go from here?

I have explored other testing frameworks with AI support. [CodeConcept](https://codecept.io/ai/) promises test generation with AI support and auto-healing of failing tests. They also rely on OpenAI and send the entire HTML page to the API. This is not only costly but, as with `auto`, has the drawback that OpenAI has no awareness about which parts of the page are visible and which are not.

In my opinion, we will see the true power of AI in two parts around testing and quality assurance soon:

1. Coming up with test cases and assisting the creation by suggesting which cases to write and how to increase testability.
2. Auto-healing failing tests: If a test fails because a selector has changed, but AI could infer the original intention, we could use AI only to make the test pass and report the new selector. This would make tests more reliable while avoiding AI-related slowness (and cost). Furthermore, it would allow us to fix tests faster as AI gives us the hint to fix them.

At the current state of AI and AI tooling around UI testing, I would recommend using AI mainly to support the creation of tests and to develop new cases and ways to improve testability. During the actual test execution, I would only use it sparsely.

## Beyond AI-enhanced Testing

Assuring good software quality depends on tests, how we write code, and whether it is maintainable. Several tools out there help with code analysis and reviews. AI-enhanced code reviews will be a topic for another article.

## Conclusion

AI is beginning to significantly impact software testing and quality assurance — tools like ZeroStep and auto-playwright promise more intuitive testing but face speed, cost, and reliability challenges.

The future of AI in testing is promising, with potential advancements in auto-generating test cases and auto-healing failing tests. For now, AI is best used as a supportive tool in test creation and improving testability. The ongoing evolution of AI in software development, including areas like AI-enhanced code reviews, will be crucial for developers to monitor.

**Have you used AI in testing and QA? I would love to hear from your experiences!**