+++
title = "Building in Public: How Diving Nomads Automates Coliving & Coworking Partner Outreach"
slug = "building-diving-nomads-in-public-part-2"
image = "/img/blog/2025-08-29-building-diving-nomads-in-public-part-2.jpg"
date = '2025-08-29T05:00:00'
publishDate = '2025-08-29T05:00:00'
description = "Part 2 of building Diving Nomads in public: How we automated partner outreach for coliving and coworking spaces using n8n workflows, Google Maps API, OpenAI filtering, and NocoDB. A complete automation pipeline for scaling partner acquisition."
tags = ["Startup", "Business", "Automation", "Software-Development", "Case-Study", "Practices", "AI"]
+++

At **Diving Nomads**, we’re building something special for digital nomads who love scuba diving. Our mission is to make it easy for them to find great places to work, live, and dive — without having to choose between beautiful dive spots and solid remote work setups.

We’re doing this **in public**, sharing our journey so other founders can see how a lean, automation-first approach can work in practice. Our hope: inspire other early-stage builders to skip the over-engineering and focus on delivering value early.

## Why Coliving and Coworking Matter
For our community, the magic is in finding places where you can **dive by day** and still have a **productive, supportive place to work** in between dives.

That’s why we’re expanding our partner network beyond dive centers to include **coliving and coworking spaces**. This way, our members can plan entire trips — from where they’ll sleep and work, to where they’ll dive — in one place.

## Step 1: From Dive Center to Coliving Discovery

We already have an automated outreach engine for dive centers (see [Article #1](https://tidbits.mende.io/p/how-we-onboard-dive-centers-and-automate) for details). So the question was: *How can we apply a similar approach to coliving and coworking spaces?*

Our answer:  
Whenever we onboard a dive center in a new location, we **flag that location** for coliving/coworking partner discovery. Every night, an **n8n** workflow runs:

1. Uses the **Google Maps API** to find coliving and coworking spaces nearby
2. Adds them to our **NocoDB** tables
3. Prepares them for quality filtering

![Automatic Google Maps Search for Colivings and Coworking Spaces](/img/blog/2025-08-29-diving-nomads-colocation-onboarding.jpg)

## Step 2: Filtering Out the Noise
Not every Google Maps result is actually relevant. We get hotels, guesthouses, and sometimes random businesses.

So we added an **OpenAI-powered rating step** that checks each result against criteria like:

- Community vibe
- Workspace quality
- Amenities (e.g., kitchen access, strong Wi-Fi)
- Proximity to dive centers

The AI-generated rating is stored in NocoDB so we can filter out low-quality candidates before outreach.

![Automatic Data Retrieval, Enhancement and Evaluation](/img/blog/2025-08-29-diving-nomads-data-enhancement.jpg)

## Step 3: Finding Contact Details
Google Maps won’t hand you an email address. That’s where the next workflow comes in:

- Visits the location’s website (if listed)
- Looks for “Contact” or “About” pages
- Extracts and stores the best contact email in NocoDB

Only once we have a **valid email address** and a **good rating** do we move the space into our outreach queue.

## Step 4: Outreach — Automated but Selective
From there, the process is almost identical to our dive center outreach:

1. **n8n** sends emails via **Brevo** to roughly 30 spaces per day
2. Webhooks track delivery, opens, and bounces, feeding updates back into NocoDB
3. Follow-up emails go out automatically after 7 days if there’s no reply

Filtering in NocoDB makes it easy for my (non-technical) partner to exclude certain cities or countries if needed.

## Step 5: Keeping the Human Connection
Could we automate replies using AI? Absolutely.  
Will we? No.  

We want to personally connect with every space that replies, understand their vibe, and ensure they’re a good fit for our community. That’s why n8n stops automation the moment a reply is detected.

## Step 6: The Kanban Flow
Just like with dive centers, NocoDB’s **Kanban view** helps us track partner status:

- **New lead** → **In Contact** → **Confirmed**

When a space becomes a partner, n8n moves their data to the partner list and removes them from future outreach.

**Setup time:** 15–30 minutes per workflow  
**Ongoing manual effort:** Almost none — except for the conversations that matter.

## The Tech Stack
Here’s the mix of tools powering all this:

| Component       | Tool   | Hosted Where  |
| --------------- | ------ | ------------- |
| Automations     | n8n    | K8S (Hetzner) |
| Database & UI   | NocoDB | K8S (Hetzner) |
| Email Delivery  | Brevo  | SaaS          |
| Data Enrichment | OpenAI | API           |

Our Kubernetes cluster (6 nodes, S3 object storage, Traefik load balancing, n8n with multiple workers) costs ~€50/month and hosts all our self-managed services.

## Wrapping It Up: A Fully Automated Partner Pipeline
The result is a **fully automated pipeline** that continuously brings us high-quality partner leads — without drowning us in manual work.

We get to focus our human energy where it matters: building relationships, curating our network, and delivering value to members.

This allowed us to build a partner network of 120+ qualified partners within the last month with just two people doing this on the side.

## Why This Is relevant for Tech Leaders
Even if you’re not building a diving community, the takeaway is universal:

- Use automation to handle the repetitive, scalable work
- Keep the human touch for the moments that require trust and nuance
- Empower non-technical team members to own and adapt key workflows
- Don’t over-engineer before you’ve validated the process

## What’s Next
With both dive center and coliving/coworking outreach running in parallel, the next step is to bring it all together for members — in an interactive, searchable map. Also, as we have officially launched a week ago (🥳), I can soon also share how we run the membership platform and community.

That will probably become **Article #3** (and maybe #4) in this series.

Want to learn more about the details? Just [drop me a message](https://mende.io/contact/). Happy to share more.
*— Tobi*