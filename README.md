# Apify pricing: is Starter $19 or $29, what does the free $5 actually buy, and which plan do you need? (All five plans compared)

Apify publishes five plans: Free at $0, Starter at $19 per month, Scale at $199, Business at $999, and Enterprise at custom pricing. The subscription fee is only the first charge. Most Actors in the Apify Store add their own per-result or per-event fee on top, and both charges draw from the same prepaid balance, so the number on the pricing page is a starting point rather than a ceiling.

Below you'll find the full plan table, the current proxy and storage rates, the billing rules that decide your real bill, the discounts Apify actually publishes, and the workloads where a different tool costs less.

## Quick answer: pick by volume, not by feature list

> Individual developers and small teams doing regular scraping usually land on Starter: $19/month with $19 of included usage, $0.20 per compute unit, 32 concurrent runs. Teams running scheduled pipelines or memory-hungry browser Actors need Scale ($199, $0.16/CU, 256 GB of Actor RAM). If you are still testing whether one Actor returns usable data, stay on Free until the $5 runs out.

👉 [See all five Apify plans and what each one includes](https://apify.com/pricing)

## All five Apify plans side by side

| Plan | Price per month | Prepaid usage included | CU rate | Key limits | Get started |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | $5 | $0.20/CU | 16 GB Actor RAM, 5 concurrent runs, 5 datacenter IPs, community support | [Start on the free plan](https://console.apify.com) |
| Starter | $19 + pay as you go ($17/mo billed annually) | $19 | $0.20/CU | 64 GB RAM, 32 concurrent runs, 30 datacenter IPs then $1/IP, Bronze Store discount, chat support | [Choose Starter](https://console.apify.com/billing#/subscription?planId=STARTER&billingInterval=MONTHLY&openSubscriptionWizard=true) |
| Scale | $199 + pay as you go ($179/mo billed annually) | $199 | $0.16/CU | 256 GB RAM, 128 concurrent runs, 200 IPs then $0.80/IP, Silver Store discount, priority chat, 1 hour of training per quarter | [Choose Scale](https://console.apify.com/billing#/subscription?planId=SCALE&billingInterval=MONTHLY&openSubscriptionWizard=true) |
| Business | $999 + pay as you go ($899/mo billed annually) | $999 | $0.13/CU | 512 GB RAM, 256 concurrent runs, 500 IPs then $0.60/IP, Gold Store discount, account manager, 1 hour of training per month | [Choose Business](https://console.apify.com/billing#/subscription?planId=BUSINESS&billingInterval=MONTHLY&openSubscriptionWizard=true) |
| Enterprise | Custom | Unlimited | Custom | Custom RAM, concurrency and proxy rates, SLA, dedicated technical team | [Talk to Apify sales about Enterprise](https://apify.com/contact-sales) |

Two columns in that table get misread often.

**The prepaid usage is a wallet, not a discount.** On Starter you get $19 to spend each cycle on compute units, proxies, storage and the per-result fees that Store Actors charge. Apify's own product table lists rented Actors as "deducted from prepaid usage". Spend past the wallet on a paid plan and the excess lands on your next invoice.

**Actor RAM is the total across all your runs.** Starter's 64 GB is not one big machine. A single run is capped at 32 GB on every paid plan and 16 GB on Free; the plan number governs how much memory your runs can occupy at the same time.

Enterprise is a sales conversation with no published starting price and no self-serve button. It also the only tier where single sign-on is handled, since SSO is marked as not included on all four self-serve plans.

## Proxy, SERP and unblocker rates, by plan

Proxy costs are where large crawls diverge, and the gap between Free and Business is wide.

| Plan | Residential proxy | Datacenter proxy | Google SERP proxy | Unblocker |
| --- | --- | --- | --- | --- |
| Free | $8/GB | 5 IPs included | $2.50 per 1,000 SERPs | $1.50 per 1,000 requests |
| Starter | $8/GB | 30 IPs included, then $1/IP | $2.50 per 1,000 SERPs | $1.50 per 1,000 requests |
| Scale | $7.50/GB | 200 IPs included, then $0.80/IP | $2 per 1,000 SERPs | $1.25 per 1,000 requests |
| Business | $7/GB | 500 IPs included, then $0.60/IP | $1.70 per 1,000 SERPs | $1 per 1,000 requests |

Storage and data transfer scale the same way, though the amounts are small for typical jobs:

- Dataset storage: $1.00 per 1,000 GB-hours on Free and Starter, $0.90 on Scale, $0.80 on Business.
- Request queue storage: $4.00 per 1,000 GB-hours, dropping to $3.20 on Business.
- External data transfer: $0.20/GB on Free and Starter, down to $0.18/GB on Business.
- 1,000 dataset writes: $0.005 on Free and Starter, $0.004 on Business.

The free plan's proxy access has an extra condition worth knowing: it only works inside the Apify platform. You cannot point your own scripts at it from an external client.

## The two-layer bill: plan fee plus Actor fee

Apify Store Actors bill in one of three ways, and the difference decides whether your $19 stretches or evaporates.

1. **Pay per event.** A fixed price for each event the Actor's developer defines, usually one result. Instagram Scraper charges $2.30 per 1,000 results, so 10,000 results cost $23.
2. **Pay per usage.** You pay only platform usage: compute units, proxy traffic and storage. Website Content Crawler works this way.
3. **Pay per event plus usage.** Google Trends Scraper charges $1 per 1,000 results plus the platform usage of the run, so 20,000 results cost $20 before compute.

Compute units are straightforward once you have the formula: 1 CU is 1 GB of RAM for 1 hour, so CUs = memory in GB × hours. Apify's benchmarks put Cheerio-style scraping at roughly 3,000 pages per CU and browser-based scraping at about 300 pages per CU. Most individual scraping jobs land between $0.001 and $0.05 in compute.

That math explains why the plan fee rarely dominates. A Cheerio Actor on light pages can chew through thousands of records on a few cents of compute, while a per-result Actor sets its own price regardless of how efficient the crawl is.

👉 [Start with the $19 Starter plan and spend the included balance on your own Actors](https://console.apify.com/billing#/subscription?planId=STARTER&billingInterval=MONTHLY&openSubscriptionWizard=true)

## Five places the bill goes wrong

**1. Unused prepaid usage disappears at the end of the cycle.** Nothing rolls over on monthly billing. Annual billing front-loads twelve months of usage at once, and anything left at the end of the annual cycle expires too. Budget to spend the wallet, not to bank it.

**2. Starter caps your own safety net.** You can set a usage limit in the Console, but the maximum on Starter is $100. Above that, the only protection is watching the billing dashboard.

**3. Free plan overage blocks you.** Paid plans keep running past the included usage and bill the difference. On Free, access is blocked until the next monthly cycle starts.

**4. Per-result Actors make small wallets look large.** A Google Maps Actor charging $4 per 1,000 results turns $5 into 1,250 records and $19 into about 4,750, before proxy or compute costs. The usage chart shows nothing alarming while it happens, because nothing is technically wrong.

**5. Memory settings multiply everything.** A Playwright run at 2 GB for 30 minutes costs about $0.20 in compute. The free plan's $5 covers roughly 25 of those runs; halve the memory or the runtime and you double the count.

## What a typical workload costs per month

These estimates come from a third-party guide cross-checked against Apify's published rates on 2026-09-09. They cover plan usage and standard Actor fees, not a guarantee:

| Workload | Volume | Estimated monthly cost |
| --- | --- | --- |
| Personal research, occasional scrapes | Under 100 pages/month | Free plan covers it |
| Local lead gen from Google Maps | ~2,000 records/month | $5–15 |
| E-commerce price monitoring | ~30,000 records/month | $30–80 |
| Social media tracking | ~50,000 records/month | $80–150 |
| Full-site crawl | Millions of pages | Business or Enterprise |

The jump from Starter to Scale rarely comes from compute alone. Scale lowers the CU rate to $0.16, residential bandwidth to $7.50/GB and SERP calls to $2, and it raises the Store discount from Bronze to Silver, which lowers the per-result price on many Store Actors. If most of your spend is per-result fees rather than compute, the $199 tier pays for itself sooner than the volume numbers suggest.

👉 [Compare the Starter and Scale rates against your own usage](https://apify.com/pricing)

## Discounts Apify actually publishes

- **Students:** 50% off Starter, Scale and Business.
- **Startups:** 30% off the Scale plan.
- **Nonprofits and academic institutions:** individualized discounts on paid plans, no fixed percentage published.
- **Annual billing:** roughly 10% off, which puts Starter at $17/month, Scale at $179 and Business at $899. The trade-off is that the full year of prepaid usage arrives upfront and expires at the end of the annual cycle.

A cheaper entry point circulates in third-party write-ups: a Creator Plan at $1/month plus pay as you go, with a one-time $500 prepaid credit that must be used within six months, capped at 10 GB of residential proxy and 10,000 SERPs per month and limited to Apify's own universal Actors. It does not appear on the main pricing page, so confirm it in the Console before you count on it.

## What reviewers complain about

G2 reviews are worth reading for the failure modes rather than the averages. One reviewer, an AI system architect at a small company, praises the mix of ready-made Actors and custom builds, plus API and webhook integration, then names the learning curve as the main cost: actors, datasets and usage-based pricing take time to click, and the Console has a lot of surface area.

A second reviewer describes a specific failure with a Twitter Scraper. Run limits were configured, the Actor pulled thousands of tweets anyway, costs rose without an intentional trigger, and the response to the complaint produced, in their words, "no meaningful resolution or refund". The same review reports stale tweets and inconsistent results across identical runs, and concludes the platform isn't suitable for production-critical pipelines.

At the aggregate level, G2 shows cost savings of 70–80% against previous data vendors for some users and monthly bills under $50 for others, alongside a recurring complaint that the compute-unit model is hard to predict and that third-party Actor rental fees create surprise charges. Those are individual accounts, not a survey.

## When Apify is the wrong purchase

- **You need to scrape millions of pages and have engineering time.** Self-hosted Crawlee costs $0 in software and only what you pay for servers. You give up managed proxies, scheduling and the Store.
- **You only need clean page content for an LLM pipeline.** Firecrawl starts at $0 with 1,000 credits per month and bills per API credit per page, which maps more directly onto that job than a compute-unit wallet does.
- **You mainly need a huge proxy pool and datasets.** Bright Data has no free tier, sells trials, and bills on bandwidth plus dataset pricing. Teams with heavy proxy needs sometimes buy both platforms.
- **You need one fixed monthly number with no overage.** Every Apify paid plan is metered. The usage limit caps the damage, but the bill still moves.

## FAQ

**Is Starter $19 or $29?** Apify's pricing page lists $19/month with $19 of included usage. Several third-party directories still show $29 because they captured the page before Apify cut the price in September 2026; Starter was $49 in early 2025. Treat $19 as current.

**Does annual billing save money?** About 10%: $17/month on Starter, $179 on Scale, $899 on Business. The prepaid usage for the whole year is available immediately and expires at the end of the annual cycle.

**Do unused credits roll over?** No. Monthly wallets reset at the end of each billing cycle.

**What happens when I exceed the included usage?** On a paid plan, the excess is added to your next invoice and you keep running until you hit the usage limit you set yourself. On Free, access is blocked until the next cycle.

**Is the free plan enough to evaluate Apify?** For a single Actor and a few hundred results, yes. The $5 wallet, 5 concurrent runs and 16 GB of RAM are enough to see whether the data is usable. It is not enough for a Maps Actor at $4 per 1,000 results beyond about 1,250 records.

**Can I downgrade later?** Yes, from Billing in the Console. Downgrades take effect immediately with no refund for the remaining days, but you keep the old plan's prepaid usage until the cycle ends, and the usage limit resets to the new plan's default. Upgrades are pro-rated, so a mid-cycle switch charges only the remaining days at the new rate.

**What if I only need more usage for one month?** Apify's own documentation recommends raising your usage limit and paying the overage instead of upgrading a tier.

## Before you order

Match the plan to the shape of your spend, not the size of your company:

- Testing one Actor or running a few hundred scrapes a month: Free.
- Regular scraping where most of the cost is compute: Starter at $19.
- Per-result Actors dominating the bill, or scheduled pipelines with browser Actors: Scale at $199, where the CU rate, proxy rates and Store discount all drop.
- SLA, custom limits, or hundreds of concurrent runs: Business or Enterprise.

Two things to do before the first invoice arrives. Set a usage limit in the Console so a runaway Actor can't run all cycle, and check the Pricing tab on each Store Actor to see which of the three billing models it uses. Cheerio crawls and per-result Maps scrapers behave nothing alike on the same $19 wallet.

👉 [Open the Apify pricing page, pick a plan, and check the billing dashboard after your first test run](https://apify.com/pricing)
