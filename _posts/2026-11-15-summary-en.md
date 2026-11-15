---
layout: default
title: "Horizon Summary: 2026-11-15 (EN)"
date: 2026-11-15
lang: en
---

> From 39 items, 11 important content pieces were selected

---

**Technology News**
1. [SpaceX catches Starship after Flight 15; booster misses tower](#item-tech-news-1) ⭐️ 9.0/10
2. [Lovable apps exposed passport data and 200K private messages](#item-tech-news-2) ⭐️ 8.0/10
3. [DeepSeek V3 inference reimplemented in roughly 200 lines of JAX](#item-tech-news-3) ⭐️ 7.0/10
4. [EFF Says Tech Companies Are Redefining Privacy Again](#item-tech-news-4) ⭐️ 7.0/10
5. [Project Zero to shorten vulnerability disclosure to 60 days in 2027 and 30 in 2028](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI Reportedly Disbands Standalone Robotics Team, Shifts to General Models](#item-tech-news-6) ⭐️ 7.0/10
7. [Cloudflare open-sources Kitesurf, a stateless browser for AI agents](#item-tech-news-7) ⭐️ 7.0/10
8. [Tesla Cybercab terms reportedly require $299 monthly subscription to operate](#item-tech-news-8) ⭐️ 7.0/10
9. [FAA ground stop traced to router failure after fiber upgrade](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [Nvidia turmoil and a Democratic Congress could reshape the AI trade, ETF experts say](#item-finance-news-1) ⭐️ 7.0/10
2. [Eric Trump-backed robotics startup misses payroll; CEO had borrowed $4.6 million](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [SpaceX catches Starship after Flight 15; booster misses tower](https://www.spacex.com/launches/starship-flight-15) ⭐️ 9.0/10

SpaceX&\#x27;s Starship Flight 15 ended with the ship caught by the launch tower&\#x27;s arms after about 22.5 hours in orbit and roughly 14 orbits, SpaceX announced. The flight deployed all 26 Starlink V3 satellites, and SpaceX described the catch as the first tower catch of an orbital-class ship. The Super Heavy booster did not return to the tower, instead splashing down in the Gulf of Mexico, so the planned catch of both stages was not achieved.

hackernews · ls612 · Nov 14, 21:22 · [Discussion](https://news.ycombinator.com/item?id=50500963)

**「Why the tower catch matters」** Starship is designed as a two-stage reusable vehicle: the Super Heavy booster and the Ship are meant to return to the launch tower, where mechanical arms catch them instead of relying on landing legs. Flight 15 was SpaceX&\#x27;s first catch attempt for the Ship after orbital flight, a step beyond recovering the booster.

**「Impact」** The ship must still be inspected and reflown before reuse is demonstrated, and because the booster missed the tower, SpaceX has not yet shown the full two-stage recovery sequence; until both stages are recovered and reflown, the launch-cost benefit of full reusability remains unproven.

**「Community Discussion」** Commenters treated the ship catch as the key step but focused on what remains: small\_model argued the heat shield must hold up and that double catch and reflight are the next tests, while ChuckMcM suggested a small booster propellant margin may have prevented a second catch and questioned the final mass fraction to orbit. GMoromisato framed Starship as a fully reusable, assembly-line-built correction to the Space Shuttle&\#x27;s compromises.

<details><summary>References</summary>
<ul>
<li><a href="https://www.engadget.com/2316926/watch-spacex-attempt-to-catch-the-starship-upper-stage-for-the-first-time/">SpaceX Successfully Catches Starship After Launch For The First Time</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#Starship`, `#reusable launch`, `#spaceflight engineering`, `#Hacker News`

---

<a id="item-tech-news-2"></a>
### [Lovable apps exposed passport data and 200K private messages](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

A security analysis reports that apps built with Lovable exposed passport details and more than 200,000 private messages because of insufficient Row-Level Security. Lovable&\#x27;s Head of Security acknowledged that root cause and said the company scans every app automatically before publishing, offers a free deeper SAST scan, and lets users apply fixes or enable auto-fix. The report concerns Lovable-generated apps backed by Supabase, where row-level security controls which records a client can read or write.

hackernews · armcat · Nov 14, 17:43 · [Discussion](https://news.ycombinator.com/item?id=50499017)

**「The RLS layer behind the exposure」** Row-level security \(RLS\) is PostgreSQL&\#x27;s per-row access-control mechanism: queries return only the rows allowed by policies attached to a table. Supabase exposes database tables to browser code through a publishable API key, so a table without effective RLS policies can be queried directly by anyone who inspects the app&\#x27;s network calls.

**「Impact」** For developers building on Lovable and Supabase, the reported exposures put the burden on builders to verify RLS policies table by table rather than assume generated scaffolding is secure; the vendor says its pre-publish scans and auto-fix are intended to catch these findings before an app goes live.

**「Community discussion」** Commenters argued that Supabase&\#x27;s permissive defaults share responsibility; one pointed to a Supabase discussion and said that although the issue was supposedly fixed on October 30, existing projects may still use the old defaults. Another said AI-generated apps are easy targets because they are numerous and can be probed by inspecting browser network calls, leaving users unaware of the risk.

<details><summary>References</summary>
<ul>
<li><a href="https://justinmckelvey.com/blog/is-supabase-secure">Is Supabase Secure ? Yes, If RLS Is On (5-Minute Check)</a></li>

</ul>
</details>

**Tags**: `#security`, `#AI app builders`, `#Supabase`, `#row-level security`, `#data exposure`

---

<a id="item-tech-news-3"></a>
### [DeepSeek V3 inference reimplemented in roughly 200 lines of JAX](https://github.com/Vaibhaav-Tiwari/deepseek-v3-jax) ⭐️ 7.0/10

A Show HN project reimplements DeepSeek V3 inference in roughly 200 lines of pure JAX. The available description frames it as an educational, from-scratch implementation for local experimentation rather than a production release; the supplied summary does not include performance benchmarks or a formal compatibility matrix.

hackernews · VaibhaavTiwari · Nov 14, 15:04 · [Discussion](https://news.ycombinator.com/item?id=50497589)

**「What DeepSeek V3 actually is」** DeepSeek V3, as described in its technical report, is a 671B-parameter Mixture-of-Experts model in which roughly 37B parameters are activated for each token, because each token is routed through a subset of experts rather than the whole network. A from-scratch implementation therefore has to spell out expert routing, attention and the surrounding plumbing explicitly, which is what makes a ~200-line reimplementation a readable study of the architecture rather than a wrapper around a packaged model loader.

**「Impact」** For developers experimenting with AMD GPUs, one commenter reports that the project ran end-to-end on an RX 7600 XT 16GB via ROCm after setting HSA\_OVERRIDE\_GFX\_VERSION=11.0.0, which was needed because JAX&\#x27;s plugin rejected gfx1102. That makes the repository a practical ROCm/JAX starting point, with the caveat that this is one user-reported configuration rather than documented support.

**「Community discussion」** Commenters welcomed the first-principles approach as a way to understand model inference, and one reader comfortable with Java and Python asked for a roadmap to build the relevant intuition. Others said they planned to recreate the implementation for learning.

<details><summary>References</summary>
<ul>
<li><a href="https://deepwiki.com/deepseek-ai/DeepSeek-V3/1.2-model-architecture-overview">Model Architecture Overview | deepseek-ai/DeepSeek-V3 | DeepWiki</a></li>
<li><a href="https://arxiv.org/pdf/2412.19437v2">DeepSeek-V3 Technical Report - arXiv.org</a></li>

</ul>
</details>

**Tags**: `#JAX`, `#DeepSeek V3`, `#LLM inference`, `#ROCm`, `#open source`

---

<a id="item-tech-news-4"></a>
### [EFF Says Tech Companies Are Redefining Privacy Again](https://www.eff.org/deeplinks/2026/11/tech-companies-are-trying-shift-entire-concept-privacy-again) ⭐️ 7.0/10

An EFF analysis published Nov. 14 argues that technology companies are again trying to shift the concept of privacy. The supplied summary ties the discussion to AI meeting notetakers, data fusion, and individual privacy rights, but does not identify specific companies, proposals, or measured practices. It is policy commentary rather than a report of a new product or independently verified incident.

hackernews · gslin · Nov 14, 12:45 · [Discussion](https://news.ycombinator.com/item?id=50496602)

**「Background」** Privacy debates have long centered on a personal-choice model: an individual decides whether to trade data for a service, and notice-and-consent terms govern that exchange. EFF&\#x27;s analysis argues that always-on devices—Meta and Google smart glasses, Apple&\#x27;s Audio Intelligence transcription on Apple Watch, and Amazon&\#x27;s Bee recorders—shift the problem to bystanders who never made that choice. That consenting-wearer-versus-unwilling-bystander distinction is the backdrop for the current argument over data fusion and meeting transcription.

**「Practical consequence」** For employees in recorded meetings, the choice is not purely social: consent requirements for AI notetakers vary, with some jurisdictions requiring all-party agreement and others one-party consent, alongside GDPR obligations \(tool-3-1, tool-3-3\). That makes a request to disable a notetaker before a 1:1 or sensitive discussion a compliance question as much as an etiquette one, and the rules differ by location rather than by the tool itself.

**「Community discussion」** One commenter described every professional meeting now being recorded by seen and unseen AI guests, including 1:1 manager conversations, and asked whether refusing transcription could become a norm; another argued live-transcribing glasses could be transformative for deaf and nearly deaf users and need not retain data if run locally, while noting the system is “one if-statement away” from retention. Others framed the issue in rights terms, citing UN human-rights language against arbitrary privacy interference and arguing companies have no right to private data through fusion, and one recommended compartmentalized identities, air gaps, and membership in privacy groups such as EFF.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.my/items/46520/tech-companies-are-trying-to-shift-the-concept-of-privacy-again">Tech Companies Are Trying to Shift the Concept of Privacy (Again)</a></li>
<li><a href="https://askcanary.com/blog/meeting-notetaker-consent-and-legality-2026/">AI meeting notetaker consent and legality: the 2026 guide</a></li>
<li><a href="https://www.recordinglaw.com/us-laws/ai-meeting-recording-laws/">AI Meeting Recording Laws by State: Complete Guide (2026)</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#AI surveillance`, `#meeting transcription`, `#data fusion`, `#tech policy`

---

<a id="item-tech-news-5"></a>
### [Project Zero to shorten vulnerability disclosure to 60 days in 2027 and 30 in 2028](https://projectzero.google/2026/11/disclosure-policy.html) ⭐️ 7.0/10

Google Project Zero announced that it will shorten its vulnerability disclosure window from 90 days to 60 days on February 2, 2027, and then to 30 days on January 3, 2028, giving software vendors less time to patch reported flaws before public disclosure. The current &quot;Full 90&quot; policy discloses vulnerabilities 90 days after they are reported to the vendor; the later stages are called &quot;Full 60&quot; and &quot;Full 30.&quot; No details on exceptions or grace periods appear in the supplied material.

hackernews · hacb · Nov 14, 11:13 · [Discussion](https://news.ycombinator.com/item?id=50496051)

**「Background」** Vulnerability disclosure deadlines set how long a vendor has to fix a reported flaw before researchers publish details. Project Zero, Google&\#x27;s security research team, is shortening that window in stages: the 90-day period remains in place initially, with 60 days scheduled for 2027 and 30 days for 2028.

**「Impact」** Vendors and open-source maintainers that receive Project Zero reports will need to complete fixes within 60 days starting February 2, 2027, and within 30 days starting January 3, 2028, down from 90 days. Organizations should check that their security contacts and escalation paths can meet the shorter windows; the supplied material does not describe any extension process.

**「Community discussion」** One commenter warned that Ubuntu would need &quot;a LOT more time&quot; than the new deadlines allow, while another argued for immediate disclosure on the grounds that nothing else compels vendors to fix reported flaws. These are opinions about whether the shortened windows are workable, not evidence of vendor readiness.

**Tags**: `#vulnerability disclosure`, `#Project Zero`, `#software security`, `#Google`, `#security policy`

---

<a id="item-tech-news-6"></a>
### [OpenAI Reportedly Disbands Standalone Robotics Team, Shifts to General Models](https://fortune.com/2026/11/13/openai-disbands-robotics-team-as-its-general-models-start-running-robots/) ⭐️ 7.0/10

OpenAI has reportedly disbanded its independent robotics team and reassigned its researchers to broader research groups, according to a Fortune report relayed by the source. OpenAI said robotics remains central to its long-term vision and that general frontier models such as GPT-6 Astra can already control robots directly, reducing the need for a dedicated team; the source gives no technical details or independent confirmation for that capability. The report notes an earlier robotics team was disbanded in 2020 and a rebuilt effort partnered with Figure before that collaboration ended in February 2025. OpenAI is still developing a humanoid robot, with its CEO targeting a first public demonstration in 2027.

telegram · zaihuapd · Nov 14, 04:00

**「Background」** OpenAI has reorganized its robotics work before: it dissolved an earlier robotics team in 2020, rebuilt a robotics unit in 2024, and partnered with Figure until that collaboration ended in February 2025. Coverage of the reorganization cites a 74.8% task-success rate for GPT-6 Astra on robot tasks, compared with 51% for specialized robot models.

**「Impact」** OpenAI&\#x27;s robotics researchers now sit within general model teams rather than a dedicated robotics unit, so robotics work is organized around general frontier-model capabilities. The source names no replacement robotics organization, product, or partner program, leaving the practical external impact of the reorganization unclear.

<details><summary>References</summary>
<ul>
<li><a href="https://theroboticsmedia.com/article/openai-disbands-robotics-team-gpt-6-astra">OpenAI Disbands Robotics Team, Bets on GPT-6 Astra Instead</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#robotics`, `#foundation models`, `#AI industry`, `#organizational change`

---

<a id="item-tech-news-7"></a>
### [Cloudflare open-sources Kitesurf, a stateless browser for AI agents](https://www.phoronix.com/news/Cloudflare-Kitesurf-Open-Source) ⭐️ 7.0/10

Cloudflare has open-sourced Kitesurf, an Apache-2.0-licensed stateless browser for AI agents that runs on Cloudflare Workers. It parses HTML, handles CSS, and executes JavaScript without a browser container, and Cloudflare says the code is on GitHub. Cloudflare claims Kitesurf uses less CPU and memory than Chromium and can scale on demand across the Workers network; the source provides no benchmarks or independent measurements supporting those performance claims.

telegram · zaihuapd · Nov 14, 09:33

**「Prior context」** Cloudflare first announced Kitesurf on August 6, 2026, describing it as a stateless, agent-first browser that runs entirely on Workers and was offered free while in beta through Browser Run, with support for screenshots, HTML extraction, and automation. The new development is that Cloudflare has now published the Kitesurf code under Apache-2.0 on GitHub, moving it from a hosted beta service to an open-source project that others can inspect or deploy.

**「Impact」** Developers building agent automation can replace headless Chromium containers with Workers-hosted isolates, which Cloudflare&\#x27;s own 14-URL benchmark, run five times, reported as roughly 3.1x less CPU and 4.7x less memory for screenshots and 3.8x less CPU and 7x less memory for HTML extraction. Because Kitesurf parses HTML, CSS, and JavaScript without a full browser engine, teams whose agents rely on pixel-accurate rendering or complete browser APIs should verify feature coverage before migrating existing Playwright- or Chromium-based pipelines.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.cloudflare.com/kitesurf/">Introducing Kitesurf: The agent-first browser that runs in V8 ...</a></li>
<li><a href="https://developers.cloudflare.com/browser-run/kitesurf/">Kitesurf · Cloudflare Browser Run docs</a></li>
<li><a href="https://developers.cloudflare.com/changelog/post/2026-08-06-kitesurf/">Introducing Kitesurf, an agent-first browser on Browser Run</a></li>
<li><a href="https://pinggy.io/blog/cloudflare_kitesurf_ai_agent_browser/">Inside Kitesurf : Cloudflare Built a Browser Engine Just for AI Agents</a></li>

</ul>
</details>

**Tags**: `#AI agents`, `#Cloudflare Workers`, `#open source`, `#browser automation`, `#serverless`

---

<a id="item-tech-news-8"></a>
### [Tesla Cybercab terms reportedly require $299 monthly subscription to operate](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

Tesla&\#x27;s posted Cybercab terms reportedly set the vehicle price at $29,990 and require a $299 monthly autonomy subscription for the car to operate. Nonpayment or misuse can lead to suspension or cancellation, and three accumulated warnings disable autonomous driving for one week, according to the terms. The vehicle is restricted to designated areas and may not be connected to ride-hailing, delivery, or rental platforms without authorization; Tesla can change the subscription price with one month&\#x27;s notice. Electrek notes that Cybercab and the Robotaxi Model Y share AI4 hardware and autonomous-driving software, while FSD for ordinary owners still requires human supervision.

telegram · zaihuapd · Nov 15, 01:10

**「Background」** Cybercab is Tesla’s purpose-built autonomous vehicle, and the cited terms tie its operation to a paid autonomy service rather than solely to the vehicle purchase. Electrek notes that Cybercab and the Model Y used for robotaxi service share AI4 hardware and autonomous-driving software, while FSD for ordinary owners still requires human supervision.

**「Impact」** For buyers, the mandatory $299 monthly subscription adds about $3,588 a year, roughly 12% of the $29,990 vehicle price. The car is also limited to designated Robotaxi geofences, and using it on ride-hailing, delivery, or rental platforms requires authorization, restricting owners&\#x27; ability to offset the recurring fee with commercial use.

<details><summary>References</summary>
<ul>
<li><a href="https://therobotaxireport.com/cybercab-price">Cybercab price: $29,990 plus a $299 monthly fee | The ...</a></li>
<li><a href="https://electrek.co/2026/11/13/tesla-cybercab-personal-use-orders-299-subscription-geofence/">Tesla Cybercab orders open at $29,990 + $299/mo, only in ...</a></li>

</ul>
</details>

**Tags**: `#Tesla`, `#Cybercab`, `#autonomous driving`, `#subscription model`, `#robotaxi`

---

<a id="item-tech-news-9"></a>
### [FAA ground stop traced to router failure after fiber upgrade](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

U.S. Transportation Secretary Sean Duffy said on Nov. 14 that the FAA&\#x27;s nationwide ground stop was triggered by routine maintenance at a remote facility that replaced old copper wiring with fiber, after which a newly installed router malfunctioned and thousands of flights were halted. Duffy said the root cause is not yet established and could be a hardware failure, a configuration error, or a mistake by contractor L3Harris. He said the router sent more than 1,000 connection requests every four to five seconds to other routers, disrupting radar signals and aircraft communications, and he called on Congress to provide additional air traffic control modernization funding.

telegram · zaihuapd · Nov 15, 02:10

**「Background」** The outage originated in routine maintenance at a remote FAA facility, where aging copper cabling was being replaced with fiber optics. The agency has been seeking additional air traffic control modernization funding, which Transportation Secretary Sean Duffy cited after the ground stop.

**「Weekend recovery backlog for airlines and passengers」** Flight disruptions continued into the weekend as airlines raced to recover from the nationwide ground stop, with thousands of flights delayed or canceled and passengers&\#x27; travel plans disrupted heading into the weekend. Because Transportation Secretary Sean Duffy said the root cause is still undetermined — possibly a hardware fault, a configuration error, or a contractor L3Harris mistake — no corrective or preventive change to the affected router setup has been identified yet.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/14/faa-ground-stop-flights-resume-delays.html">Ground stop followed contractor upgrade to L 3 Harris telecom system...</a></li>
<li><a href="https://edition.cnn.com/2026/11/14/politics/faa-ground-stop-what-we-know">What we know about the cause of the nationwide FAA ground stop</a></li>

</ul>
</details>

**Tags**: `#FAA`, `#网络故障`, `#关键基础设施`, `#路由器`, `#航空`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Nvidia turmoil and a Democratic Congress could reshape the AI trade, ETF experts say](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 7.0/10

Nvidia’s turmoil, including CEO Jensen Huang’s resignation, is reshaping the AI trade, and ETF experts interviewed by CNBC said Big Tech and other chipmakers could benefit if a Democratic-controlled Congress slows data-center construction. Yorkville Ives cut its Nvidia price target to $225 from $300 while maintaining a buy rating; Nvidia closed the week at $162.85 a share.

rss · CNBC Finance · Nov 14, 15:50

**「Background」** Nvidia’s turmoil follows CEO Jensen Huang’s resignation and CFO Colette Kress’s appointment as interim CEO, the company said, while the source ties the policy backdrop to Democratic gains on Nov. 3 that swept control of Congress.

**「Who is exposed」** If a Democratic-controlled Congress slows data-center construction, neocloud operators such as CoreWeave — whose shares fell after the midterm sweep \[tool-2-3\] — are most exposed; Yorkville Ives estimates 10%-20% of planned data centers may not be built, and voters already rejected 46 of 47 data-center ballot measures \[tool-2-2\].

<details><summary>References</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-CEO-Transition/">NVIDIA Corporation - NVIDIA Announces CEO Transition</a></li>
<li><a href="https://venturesignal.org/us-midterms-data-centres-ballots-musk-474m/">US midterms – data centres lose 46 of 47 ballots as... | Venture Signal</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/ai-data-center-stocks-drop-100424346.html">AI data center stocks drop as Democrats sweep U.S. midterms</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI trade`, `#ETF flows`, `#US Congress`, `#CEO departure`

---

<a id="item-finance-news-2"></a>
### [Eric Trump-backed robotics startup misses payroll; CEO had borrowed $4.6 million](https://www.cnbc.com/2026/11/14/foundation-payroll-ceo-loan.html) ⭐️ 7.0/10

Foundation Future Industries, an Eric Trump-backed military robotics startup, missed payroll on Oct. 30, and CNBC reported that CEO Sankaet Pathak had borrowed $4.6 million from the company the prior year to buy a home. CNBC also reported that the company’s widely reported $24 million in government contracts came through an acquired Florida firm, not direct awards.

rss · CNBC Finance · Nov 14, 12:00

**「Background」** Eric Trump is an investor and chief strategy advisor at Foundation, though his spokesperson says he has no involvement in management, operations, strategic decisions or government-contract work; Pathak is the company’s sole board member and majority shareholder.

**「Impact」** Employees have yet to receive paychecks after the Oct. 30 missed payroll, and the company’s sole-board structure has raised governance concerns among prospective investors as it seeks hundreds of millions in funding at a $3 billion valuation.

**Tags**: `#defense startups`, `#corporate governance`, `#payroll failure`, `#Pentagon contracts`, `#Eric Trump`

---