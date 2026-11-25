# Web Scraping Service Pricing: What Does 1,000 Requests Actually Cost? Credits, Results and Per-Call Billing Compared, and When a Managed Quote Beats Self-Serve (Full ScraperAPI Plan Table)

One million pages a month costs about $250 at one vendor, roughly $70 at another, $10,000 at a third, and a five-figure annual contract at a fourth. Every one of those numbers can be correct, because each is quoted in a different unit: per 1,000 results, per monthly credit bundle, per API call, and per managed project.

Fix the unit first, then fix the second problem: what counts as one request. ScraperAPI bills in credits, and its 5,000,000-credit plan covers 5 million standard pages, 1 million Amazon pages, or 200,000 Google SERPs depending on where you point it. A team that buys on the credit headline and then scrapes search results gets a fifth of the volume it budgeted for.

This guide covers what each pricing model actually buys, how to convert your own workload into a comparable number, and which tier or vendor matches which job.

> **Quick pick:** start on a metered API and move to a managed contract only when you need custom schemas, cleaning and warehouse delivery. ScraperAPI is free to test: a 7-day trial with 5,000 credits and no card, then a free plan at 1,000 credits and 5 concurrent threads a month. Real volume starts at Hobby with 100,000 credits and 20 threads.
>
> 👉 [See the current ScraperAPI plans, credit allowances and monthly prices](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## What a web scraping service actually sells

Two different purchases hide behind the same phrase. A managed service takes your field list and returns a finished dataset on a schedule, with the vendor handling rendering, proxies, retries, quality checks and delivery. A tool gives you an unblocker, a cloud browser or a library, and you build the pipeline yourself.

The managed tier is priced like a project, because that is what it is. Bright Data runs a four-stage process: kickoff to define sources and KPIs, collection with a dedicated project manager, validation and enrichment, then delivery through custom dashboards. Grepsr sends a paid first extraction run so you approve sample data before full delivery. PromptCloud ships a free sample before going live. ScrapeHero lists delivery in JSON, CSV, Excel, XML, SQL dumps, nested JSON or parent/child tables, pushed to Amazon S3, Dropbox, Azure, Google Cloud Storage, Snowflake or FTP.

Zyte, the company behind the open-source Scrapy framework, delivers clean structured datasets in JSON or CSV to destinations such as S3 buckets, with custom schemas depending on the plan.

If you cannot yet name your fields, your refresh cadence and your destination table, you are not ready for the managed tier. Quotes at that stage get padded with discovery work you could have done yourself. If you can name them, quote-only vendors are worth a call, because the process above is where the value sits.

## ScraperAPI plans at a glance

ScraperAPI sells the self-serve side: one API, monthly credits, no per-site contracts. Here is the published tier structure.

| Plan | Credits / month | Concurrent threads | Price | Start |
| --- | --- | --- | --- | --- |
| Free | 1,000 | 5 | $0 | [Open the free plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Hobby | 100,000 | 20 | Listed on the pricing page | [See Hobby pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | 1,000,000 | 50 | Listed on the pricing page | [See Startup pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | 3,000,000 | 100 | Listed on the pricing page | [See Business pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | 5,000,000 | 200 | $475/mo, or $427.50/mo billed annually ($5,130/year, $570 less) | [See the Scaling plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | 10,500,000 | 300 | Listed on the pricing page | [See Professional pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | 21,500,000 | 500 | Listed on the pricing page | [See Advanced pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | 22,000,000+ | 500+ | Custom quote | [See Enterprise options](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

Two differences that do not show up in the credit column: geotargeting is US and EU only on Free, Hobby and Startup, and country-level from Business upward; analytics history is the last 30 days on Hobby and Startup, unlimited from Business upward.

Monthly prices for the other tiers sit on the pricing page and change. Scaling is the one figure fixed in the plan documentation at $475/month, with the annual option at $427.50/month.

## A credit is not a page: the multiplier table

This is the part that decides whether a plan fits, and it is buried in the billing documentation rather than the plan cards.

| Request type | Credits consumed |
| --- | --- |
| Standard page | 1 |
| E-commerce (Amazon, Walmart, eBay) | 5 |
| SERP (Google, Bing, including subdomains) | 25 |
| Social (LinkedIn) | 30 |
| Bot-protection bypass (Cloudflare, DataDome, PerimeterX/HUMAN, Akamai) | +10 |
| JS rendering (`render=true`) | 10 |
| Premium proxies (`premium=true`) | 10 |
| Screenshot (`screenshot=true`) | 10 |
| Premium proxies plus JS rendering | 25 |
| Ultra premium (`ultra_premium=true`, paid plans only) | 30 |
| Ultra premium plus JS rendering | 75 |
| Geotargeting, sessions, device type, output format, auto-parsing | 0 |

Run the Scaling plan through that table and the effective price changes by a factor of 25:

- Standard pages: $475 buys 5,000,000 requests, or **$0.095 per 1,000 pages**.
- Amazon pages at 5 credits: 1,000,000 requests, or **$0.475 per 1,000 pages**.
- Google SERPs at 25 credits: 200,000 requests, or **$2.375 per 1,000 SERPs**.

Add JS rendering to a bot-protected e-commerce page and you are at 25 credits per page, the same budget as a SERP. A catalog-tracking job on heavily protected retail sites is the most expensive workload in the table, and it is the most common one.

ScraperAPI exposes a Domain Cost Estimator in the dashboard that returns the exact credit cost for any URL, plus a `max_cost` parameter to cap a single request so one ultra-premium target cannot eat the month's allowance.

👉 [Check the current plans and credit allowances before you size a tier](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Three pricing units, one conversion

Price lists across this market are not comparable as written. Convert everything to cost per 1,000 of the thing you actually need.

**Per 1,000 results.** Oxylabs publishes "starts from $0.25/1K results," which is $250 per million results. Clean, but check what a "result" includes: a parsed record, not necessarily a page fetch.

**Monthly fee plus allowance.** HasData publishes a full grid: Free at 1,000 requests a month, Startup at $49/month for 200,000 requests with 5 concurrent, Growth at $208/month for 3 million credits with 50 concurrent, Enterprise custom with 2,000+ concurrency and credit rollover. Growth works out to about $69 per million. One caveat worth knowing: Startup advertises "$0.25/1k requests" beside a $49 fee for 200,000 requests, and 200,000 × $0.25/1K is $50, not $49. Budget from the monthly fee and the allowance, not from the per-1K badge.

**Per call.** YepAPI prices from $0.01 per scrape up to $0.03 for stealth or AI extraction. Multiply by 1,000: that is $10 to $30 per 1,000 calls, or $10,000 per million at the low end. Per-call billing is a good fit for bursty, low-volume jobs and a poor fit for steady million-page crawls.

**Quote only.** ScrapeHero, Grepsr, PromptCloud and ProWebScraper publish no price at all, and ScrapeHero's homepage offers only "Get a free quote." Bright Data's managed program starts at $2,500 per month on annual terms according to its own documentation. That is a project floor for a full-service engagement, not an API rate, and it should never be lined up beside a $49 self-serve plan.

Vendors also disagree on what is billable. HasData states plainly that it bills only successful requests. ScraperAPI bills credits per request under the multipliers above, and when you exceed your concurrency limit the request gets a 429 and is turned away rather than queued, with no extra charge.

## Overage, concurrency and the refund window

What happens at the limit matters more than the headline allowance, because that is where surprise bills come from.

By default, scraping pauses until credits renew. On Hobby, Startup, Business, Scaling and Professional you can switch on auto-upgrade, which moves the account to the next tier when credits run out, usually at a lower price per credit. On the larger tiers, pay-as-you-go keeps requests running at a fixed per-credit rate under a monthly spending cap you set; the billing documentation lists Advanced and Enterprise, and the pricing FAQ also names Scaling and Professional, so confirm for your tier before you rely on it. The cap is a limit, not a prepayment.

Annual plans work differently: the full year's credits arrive upfront and can be used on any timeline. Run out early and you can renew the same annual plan for a fresh allocation.

The refund policy is short and worth quoting exactly in your notes: 7 days, no questions asked. You can cancel any time from the dashboard and are not charged for cancelling.

👉 [Start the 7-day trial with 5,000 credits on the pricing page](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Compliance questions with checkable answers

Every vendor claims compliance. Very few publish scope.

Oxylabs publishes both certificates and their coverage: ISO/IEC 27001:2022 for information security, covering its Datacenter Proxies, Residential Proxies and Web API solutions, and SOC 2 Type II covering controls for security, availability and confidentiality across the Scrape endpoint and Web Unblocker. The coverage list is the useful part, because a certification for a proxy product does not automatically extend to the scraping endpoint you are buying.

PromptCloud states that it respects robots.txt and site privacy policies and aligns with GDPR and CCPA. Bright Data claims GDPR and CCPA alignment and adherence to site policies. Zyte emphasises GDPR compliance and gives clients full intellectual property over delivered datasets, along with NDAs. Grepsr's compliance practice is not publicly disclosed.

Four questions get you past the marketing page:

1. Which legal entity signs the DPA, and which products does the certificate cover?
2. What is the written policy on robots.txt and terms of service, and will they put it in the contract?
3. Where is extracted data stored, for how long, and what is the deletion process?
4. Who owns the delivered dataset, and can you resell or republish it?

## Reviews: read the sample size before the score

Zyte shows 4.7/5 on G2 across 324 reviews, 4.8/5 on Capterra across 373, and 4.8/5 on Trustpilot across 329. Three platforms, three large samples, one consistent result.

Browse AI shows 4.8/5 on G2 across 54 reviews, 4.5/5 on Capterra across 60, and 3.1/5 on Trustpilot across 12. The spread is the story. A 12-review average on a platform with a different user mix tells you less than the 114 reviews on the two business-software platforms, and neither tells you how the vendor handles a broken crawl at 2 a.m.

Sample size and platform audience beat star averages. Look for reviews that name a specific failure mode.

## Which option fits your case

- **Testing an idea, under roughly 100,000 pages a month:** the free plan (1,000 credits, 5 threads) then Hobby (100,000 credits, 20 threads). No contract, no sales call.
- **Steady volume on mixed sites with JS rendering:** Startup at 1,000,000 credits or Business at 3,000,000, after running your target list through the credit multipliers.
- **5 million credits and 200 threads, mostly standard pages:** Scaling at $475/month, or $427.50/month annual.
- **Custom fields, QA, cleaning and delivery into Snowflake or S3, plus an NDA:** managed quotes. Bright Data starts at $2,500/month on annual projects; Zyte, ScrapeHero, Grepsr and PromptCloud price per project. Expect a longer cycle, sample approvals and a statement of work.
- **Small, spiky jobs where you cannot predict monthly volume:** per-call API billing, where $0.01 to $0.03 a call keeps idle months at zero.

## FAQ

**Is there a free trial?**
Yes. Signing up gives 7 days and 5,000 API credits without a credit card. After that the free plan continues at 1,000 credits and 5 concurrent connections per month.

**What happens when credits run out?**
Scraping pauses until renewal unless auto-upgrade is on for Hobby through Professional, or pay-as-you-go is enabled on a larger tier with a spending cap.

**Does JavaScript rendering cost extra?**
Yes, 10 credits per request on top of the base cost. Premium proxies plus rendering is 25, and ultra premium plus rendering is 75.

**Do unused credits roll over?**
Annual plans receive the full year's credits upfront and can spend them on any timeline, with early renewal available. Monthly plans pause at the limit and reset at renewal rather than carrying a balance.

**Can I get a refund?**
Within 7 days, no questions asked, via support.

## Before you order

Two things decide whether the plan you pick is the right size, and neither takes long.

Convert your actual target list into credits first. Pull your top 20 URLs, check each one's credit cost in the dashboard estimator, and weight by request volume. A workload that looks like 3 million standard pages is often 600,000 pages plus a SERP-tracking job that consumes the rest of the allowance. Set `max_cost` per request so a single protected domain cannot quietly eat a month.

Then decide how you want to hit the ceiling: a hard 429 that rejects requests at your concurrency limit, or a capped pay-as-you-go bill. Write the number down before your first production run, and keep the 7-day refund window in mind as the deadline for that decision.

👉 [Compare the ScraperAPI tiers, credit allowances and monthly prices](https://www.scraperapi.com/pricing/?fp_ref=coupons)
