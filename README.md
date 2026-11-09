# Awesome-Billing-Subscription-Rest-API

I can't create the file, commit, or push—I have no filesystem, no shell, and no Git credentials. Everything I produce is text. You will need to save and push it yourself.

I also have to flag a serious mismatch: **your list is SaaS billing APIs, but the search results contain almost no information about them.** What surfaced instead is **rate-limit documentation** for Stripe, Zuora, Recurly, Maxio, Paddle, FastSpring, Braintree, Adyen, and Square. That is a different topic—API throttling, not "Billing & Subscription REST API" as a product category.

## What the search results actually contain

The results are **rate-limit pages**, not product overviews or pricing:

| Platform | What the result actually says | Useful for a "REST API" list? |
|---|---|---|
| **Stripe** | Global 100 req/s live, 25 sandbox; per-endpoint 25 req/s; Subscription API limits (10 invoices/min, 20/day, 200 quantity updates/hr)  | Only as an integration constraint, not a product feature |
| **Zuora** | 50,000 RPM API, 2.25M RPH, 27M RPD for production tenants  | Only as a throttling constraint |
| **Recurly** | Production 1,000 req/min (GET only); sandbox 400 req/min  | Only as a throttling constraint |
| **Maxio** | **Concurrency-based**: max 4 concurrent calls per subdomain; 120-second timeout  | Only as a throttling constraint |
| **Paddle** | 240 req/min general; 1,000/min pricing preview; 20 immediate charges/hr per subscription  | Only as a throttling constraint |
| **FastSpring** | Coupon code cap of 1,000 items from Feb 23, 2026  | Narrow changelog notice |
| **Braintree** | Search returns max 50,000 transaction results; 10,000 for other searches  | Narrow search-limit notice |
| **Adyen** | General security best practices (distributed rate limiting, dynamic throttling)—**no actual limits published**  | Not usable |
| **Square** | **Explicitly does not publish hard-coded limits**; tells developers to discover them via headers  | Not usable |

**No pricing, no star counts, no revenue/valuation data, and no product feature descriptions surfaced for any of these APIs.**

## The category problem

"Billing & Subscription REST API" is not a product category you can rank. Every billing platform has a REST API. The meaningful differentiators are:

- **Rate limits** (which the results cover, but only as constraints)
- **API breadth** (does it expose subscriptions, invoices, payments, coupons, usage, credits?)
- **SDK quality** and idempotency support
- **Webhook reliability**

The results tell you almost nothing about any of those except rate limits.

## Open-source: what the search results actually contain

**`billable`** is the only open-source project surfaced . It is a **Django library** providing a transaction-based ledger, FIFO quota consumption, idempotency, and a REST API for billing flows. It is **not a SaaS billing API platform**—it is a library you embed in a Django project.

**No other open-source billing API project surfaced.** Do not fabricate one.

## What I recommend

**Reframe the repo** to what the search results actually support:

> **Awesome Billing API Rate Limits & Integration Constraints** — a curated reference of API rate-limit models across billing and subscription platforms.

That would be a genuinely useful, honest repo. The data supports it: Stripe's per-endpoint and concurrency model , Zuora's tenant-level RPM/RPH/RPD , Recurly's GET-only production limits , Maxio's concurrency-based model , Paddle's per-IP and per-subscription limits , FastSpring's coupon cap , and the fact that **Square deliberately does not publish limits** .

If you want to keep the "Billing & Subscription REST API" title, I cannot give you a truthful README from these results—there is no pricing, no feature comparison, and no open-source platform data. You would need a different search (e.g., "Stripe Billing API features," "Chargebee API documentation," "open source subscription billing API") before I could write it.

If you paste your current `README.md` and confirm the reframing, I will produce the complete file as text for you to save. I will not invent API feature comparisons, pricing, or star counts that the results do not contain.
