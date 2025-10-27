+++
title = "Building Diving Nomads in Public Part 3"
slug = "building-diving-nomads-in-public-part-3"
image = "/img/blog/2025-10-31-building-diving-nomads-in-public-part-3.jpg"
date = '2025-10-31T05:00:00'
publishDate = '2025-10-31T05:00:00'
description = "Part 3 of building Diving Nomads in public: How we built a fast, static partner map using Nuxt.js and Leaflet with 200+ locations. A fully client-side app powered by generated JSON read models, automated with n8n, and delivered via CDN for instant loads."
tags = ["Startup", "Business", "Automation", "Software-Development", "Case-Study", "Practices"]
+++

# Building in Public – Part 3: How We built the Diving Nomads Partner Map
This is part three of the *Building Diving Nomads in Public* series.  

After sharing [how we automated outreach for dive centers and coliving / coworking partners](https://tidbits.mende.io/p/building-in-public-part-2), this chapter is about the thing people actually use – our **Partner Map**.

It looks simple by design: fast to load, easy to navigate, and reliable even when other parts of the system are busy. Below is how it works and why we built it this way.
![Diving Nomads Partner Map](/img/blog/2025-10-31-diving-nomads-partnermap.png)
## What the map does
The map shows three categories:

- **Dive centers**
- **Coliving spaces**
- **Coworking spaces**

Users can filter with a free-text search – by **name**, **label**, **country**, or **city** – and toggle categories. A tap or click on a pin opens a small popover with the essentials: partner name, website, and the benefits for our members.
![Diving Nomads Member Map](/img/blog/2025-10-31-diving-nomads-member-map.png)
On the **public** view, we keep it minimal for speed. The **membership area** shows more detail where it’s useful.
![Diving Nomads Minimal Map](/img/blog/2025-10-31-diving-nomads-minimal-map.png)

We already have **200+ partners** on the map, and it stays snappy even on slow connections.

## Why a fully static app
I didn’t want a heavy backend or a “live” API for something that mostly displays public data. So the map is a **fully client-side Nuxt.js app** that reads from a few **static JSON files**.

- **Framework:** Nuxt.js (because we already use it elsewhere, and it keeps the frontend simple)
- **Map library:** Leaflet (open source, lightweight, battle-tested)
- **Tiles:** OpenStreetMap and other providers supported by Leaflet – we’re not locked into one ecosystem and can adjust the look easily

The result: no server round-trips to fetch data, no database reads at page load – the browser pulls small JSON files and renders the map immediately.

## The read model – generated, not queried
All partner entries live primarily in **NocoDB**. From there, **n8n** compiles a public **read model** every hour:

1. Pull current partners from NocoDB (dive centers, colivings, coworkings)
2. Normalize fields and strip anything not meant for the public
3. Write one JSON file for all places, one for statistics, and one for logos which we automatically show on the website

Those JSON files contain **only public data** and no secrets, which is why the static approach works well here. If NocoDB has downtime, the map still works – it reads the last generated files.

- **Hosting (files + app):** Hetzner Web Hosting
- **Delivery:** CloudFront CDN in front of it
- **Cache:** After a rebuild, the automation **invalidates the CDN paths**, so new versions roll out quickly
- **Deployment:** The app is deployed with simple GitHub actions that take less than a minute to run.

We can also trigger the rebuild manually with one click if we want an immediate update.
![The n8n workflow updating the read replicas and invalidating the caches.](/img/blog/2025-10-31-diving-nomads-read-replica-refresh-n8n.png)

## Why Leaflet (and not a proprietary SDK)
Leaflet is the de-facto open-source standard for rendering maps on the web. Two practical reasons I chose it here:

- **Freedom in tiles:** I can use OpenStreetMap or other free/paid providers and switch styles without changing the app structure.
- **Small surface area:** For what we need – markers, popovers, categories, search – Leaflet stays out of the way and keeps bundle size low.

The combination of **Nuxt.js + Leaflet + static JSON** is simple, predictable, and easy to maintain.

## Membership area specifics
Some partners use online booking systems with discount fields. We do **not** expose discount codes publicly.

In the **membership area**, a member can request a code:

- The member clicks **“Request discount code”**
- **n8n** checks membership status in **NocoDB**
- If active, the code is sent via email (Brevo)

This keeps partners comfortable and members happy. It also avoids inventing permissions or token logic inside the map – the map stays a reader of public data, nothing more.

## Performance and practical trade-offs
Currently, the JSON files are small – we’re well under any threshold where performance becomes an issue. If we pass **1,000+ partners**, I’ll consider:

- basic **minification** of the JSON
- splitting the data into **region-based** files
- simple **client-side pagination** / lazy loading

None of this is urgent today. The static approach already gives us 95% of the win: instant loads, minimal moving parts, and very low hosting costs.

## How it stays up to date
- **Schedule:** The read model rebuilds **hourly**
- **Manual trigger:** If needed, I run it on demand
- **Webhook option:** We could re-generate on each status change in NocoDB, but we don’t need near-real-time updates – hourly is enough for this use case

The important bit: the map isn’t coupled to the database. It’s a **published snapshot**. That separation makes everything calmer to operate.

## Stack at a glance
- **Frontend:** Nuxt.js
- **Maps:** Leaflet
- **Source of truth:** NocoDB
- **Automation:** n8n
- **Email:** Brevo
- **Static hosting:** Hetzner Web Hosting
- **CDN:** CloudFront
- **Deployment model:** fully static – app + JSON files

## Small design details that helped
- **Public vs. member detail:** Keeping the public popover lean makes the first impression fast. Deeper details belong where context exists – the membership area.
- **Consistent field names:** Normalizing fields in the n8n step avoids front-end conditionals. The app can stay dumb – exactly how I like UIs.

## Where the map data comes from (briefly)
This map sits on top of the earlier work:

- **Dive centers:** collected and contacted automatically; once confirmed, they’re added to partners
- **Coliving / coworking:** discovered via Google Maps API, scored, de-noised, and enriched (email scraping), then queued for outreach

When any of these become partners, they are automatically put into a different NocoDB table for active partners, and the next read-model build puts them on the map.

## Closing
This map is intentionally boring in its architecture – and that’s the point. Static files, a CDN, and a small Vue app are more than enough here.

The payoff: it’s fast, robust, and cheap to run. And if another part of the system has a bad day, the map still shows people where to dive, live, and work – which is the job.

All of this could be built in less than a day as we had all the foundations in place (n8n, NocoDB, static web-hosting, Brevo setup, …). And of course, we also have automated tests for the few bits of logic in the map.

If you’re curious about the specifics or want to adopt a similar pattern, happy to chat and support you in getting your idea off the ground. You are welcome to [schedule a quick 30-min call](https://cal.com/tobiasmende/30min) to bounce ideas back and forth.