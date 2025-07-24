+++
title = "Building Diving Nomads in Public Part 1"
slug = "building-diving-nomads-in-public-part-1"
image = "/img/blog/2025-07-25-building-diving-nomads-in-public-part-1.jpg"
date = '2025-07-25T05:00:00'
publishDate = '2025-07-25T05:00:00'
description = "How we built a platform for digital nomad divers using automation-first tools like n8n, NocoDB, and Vercel. A lean tech stack case study showing how to move fast, validate ideas, and deliver value without writing code from day one."
tags = ["Startup", "Business", "Automation", "Software-Development", "Case-Study", "Practices"]
+++

# Building Diving Nomads in Public: How We Onboard Dive Centers and Automate Memberships with (Almost) No Code

> **TL;DR**  
> We're building a platform for digital nomads with a passion for scuba diving. Our lean, automation-first tech stack allows us to move fast, deliver value early, and maybe inspire other early-stage founders to rethink how they build.

## What is “Diving Nomads”?
[Diving Nomads](https://divingnomads.club) is a community-driven platform for location-independent professionals who love to dive.

**Our vision:**
> Help remote workers and digital nomads discover incredible dive destinations that are also remote-work friendly and connect them with trusted dive centers and like-minded people.

**We're starting small:** verified partner dive centers and a membership pass. But the long-term goal is a vibrant global network of divers, coworking spots, coliving places, and underwater adventures.

## Why Should You Care (Especially if You Work in Tech)?
This article isn't just about scuba diving; it's about how to build something valuable, fast, and cheap without drowning in code from day one.

We're using a mix of self-hosted and cloud tools like **[NocoDB](https://nocodb.com/)**, **[n8n](https://l.mende.io/n8n)**, **[Vercel](https://vercel.com/home)**, **[APITemplate.io](https://l.mende.io/apitemplate)**, and **[Brevo](https://www.brevo.com/de/)** — many of them free or close to it — and glue them together with a bit of engineering.

As a software engineer, I believe my job is not to write code. It's to solve problems. And sometimes (often), no-code/low-code tools are the best way to do that, especially early on.

## Step 1: The Partner Onboarding Engine
Our first challenge was building a pipeline for onboarding dive centers.

We pulled data from various dive center directories (PADI, SSI, SDI, etc.) and built a **scraper workflow** in n8n that added ~6,500 dive centers to our **NocoDB** database, complete with email addresses.

**Build time:** ~2 hours.  
**Manual time saved:** Easily 40–50 hours.

![N8n Workflows to ingest divecenters](/img/blog/2025-07-25-dn-n8n-scraping.png)

Once the database was in place, we built a second workflow to **email 50 dive centers per day** using Brevo, track delivery and open rates via web hooks, and update all that in NocoDB.

**Follow-ups?** Handled.  
**Exclusions by region or country?** Easily filtered in NocoDB views.  
**Human touch?** Once a center replies, we switch to manual email to keep things personal. We have created a public Notion page where we share with them how we work. 

![N8n Workflow to outreach via email](/img/blog/2025-07-25-dn-n8n-email-outreach.png)


These two automations alone give us a ~4% positive response rate — without any manual outreach.

## Step 2: From Conversation to Partner
When a dive center agrees to join, we change their status in NocoDB — and an n8n workflow, built in 10 minutes, does the rest: moves their data to our partner list and stops future outreach.

**Kanban-style views** make it easy for my (non-technical) partner to manage status updates with zero technical knowledge.

## Step 3: Membership Passes for Our Community
We don’t have an official signup landing page yet — still work-in-progress — but we already have the backend flows ready:
- When a user becomes an active member in NocoDB, a webhook fires.
- N8n generates a digital pass with **APITemplate.io**.
- The pass is emailed to the user and includes a QR code.

**Total build time:** ~15 minutes  
**Time spent since then:** Zero

![N8n Workflow for creating and sending out member passes](/img/blog/2025-07-25-dn-n8n-on-member-activated.png)

The QR code links to a verification page built with **Nuxt.js** and **Claude Code**, deployed via **Vercel**. It took me about 30-40 minutes and costs us… nothing. Might move to K8S later, if needed.

![Membership Pass Verification (Example from our Partner page in Notion)](/img/blog/2025-07-25-dn-membership-pass.png)

## Let’s Talk Infrastructure
We’re not running everything ourselves — and that’s intentional.

Here's what we’re using:

| Component            | Tool                                                            | Hosted Where                 |
| -------------------- | --------------------------------------------------------------- | ---------------------------- |
| Automations          | n8n                                                             | K8S (Hetzner)                |
| Database & UI        | NocoDB                                                          | K8S (Hetzner)                |
| Digital Passes       | APITemplate.io                                                  | SaaS (Free)                  |
| Email Delivery       | Brevo                                                           | SaaS (Free)                  |
| Website              | [Carrd](https://l.mende.io/carrd) (soon: self-hosted WordPress) | SaaS (Existing Subscription) |
| QR Verification Page | Nuxt.js + Claude Code                                           | Vercel (Free)                |

> Side note: My Hetzner cluster (K8S with 6 nodes, load balancer, S3 object storage, etc.) costs ~50€/month and hosts my main tools self-managed. (Because I had n8n and NocoDB running for other use cases anyway, it was the obvious/trivial choice to start with them for Diving Nomads, as the additional cost is zero.)
### Why x?
Why NocoDB? Because it’s simple and beautiful, and my partner can work with it effortlessly. It also integrates super well with n8n and makes it easy to trigger workflows based on status changes or filtered views.

Why n8n? Because I have used it for years, I have it running anyway, and it saves me days or weeks compared to building everything in code. Furthermore, it is fun to use.

Why Vercel? I could have deployed the Nuxt.js applications into the K8S cluster relatively easily. However, Vercel is even easier and I wanted to try it. In the current stage, this doesn’t cost me anything. Once traffic ramps up, it would be easy to either pay for it or migrate the applications into my cluster.

Why Brevo? Brevo in the free tier allows us up to 300 emails **per day**. We will get a long way with it. Furthermore, it integrates nicely with n8n, and we have it for building our mailing list and newsletter anyway.

Why APITemplate.io? It nicely integrates with n8n, and the pricing is fair. It is easy to use. Up to 50 generations a month are free, and once we are at 50 new members per month, we can easily afford to pay for the next tier (or switch to another solution).

Why [Carrd](https://l.mende.io/carrd)? I wanted to avoid going down the WordPress rabbit hole again. For our waitlist, it was a simple and cheap option. For everything beyond that, the single-page approach is too limited. Therefore, we are going back to WordPress for the main page, as one requirement is that my partner can build pages with it.

## Is It a Bit Hacky? Sure. Is It Worth It? Absolutely.
We’re not writing a line of code unless we absolutely have to.  

We’re not over-architecting workflows that aren’t yet validated.  

We’re not building “for scale” — we’re building for now.

But everything is decoupled enough that when the time comes, we can turn n8n flows into backend code, webhook into lambda, and scale up from there. Seriously, I am very curious to see when we really will see scaling issues with the current infrastructure. This will be a nice problem to have.

## What’s Next?
We’re working on onboarding **coliving and coworking spaces** as the next partner category. The initial approach will be very similar — and yes, it will be mostly automated.

Could we even automate replying to partner emails? Probably.  
Will we? No. We *want* to connect personally with every partner who replies. That’s part of our DNA.

## Final Thoughts
The possibilities with today's tools are endless. You don’t need a giant engineering team to build something real.

We’re proof that you can:
- Start lean,
- move fast,
- focus on value,
- automate early,
- and still keep the human connection.

If you’re building something and wondering how to move faster, cheaper, and with more joy, [let’s talk](https://cal.com/tobiasmende/30min).
*– Tobi*