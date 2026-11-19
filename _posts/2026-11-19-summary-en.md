---
layout: default
title: "Horizon Summary: 2026-11-19 (EN)"
date: 2026-11-19
lang: en
---

> From 43 items, 12 important content pieces were selected

---

**Technology News**
1. [Google launches Gemini 4 Neon for coding and research](#item-tech-news-1) ⭐️ 8.0/10
2. [NGINX2Root chain exploits Nginx HTTP/2 for unauthenticated code execution](#item-tech-news-2) ⭐️ 8.0/10
3. [Google DeepMind Makes Genie 4 Available to Eligible AI Ultra Subscribers](#item-tech-news-3) ⭐️ 8.0/10
4. [Microsoft unveils seven AI models pitched on scalable price-performance](#item-tech-news-4) ⭐️ 7.0/10
5. [Quad9 France exit fuels debate over DNS anti-piracy blocking](#item-tech-news-5) ⭐️ 7.0/10
6. [A History of Early Intel CPUs From 4004 to 486](#item-tech-news-6) ⭐️ 7.0/10
7. [Show HN: Interactive Voyager 1 Tour Down to a Memory Chip](#item-tech-news-7) ⭐️ 7.0/10
8. [Stenberg: AI Rust rewrites of curl lag 300 upstream commits](#item-tech-news-8) ⭐️ 7.0/10

**Financial News**
1. [Fed minutes signal more rate hikes and AI inflation risk](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed’s Waller floats half-point December rate hike](#item-finance-news-2) ⭐️ 8.0/10
3. [Tencent Q3 2026: AI capex surges, free cash flow turns negative](#item-finance-news-3) ⭐️ 7.0/10
4. [China and South Korea announce substantive conclusion of FTA services and investment talks](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google launches Gemini 4 Neon for coding and research](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

Google launched Gemini 4 Neon, a model it says is aimed at fast end-to-end execution of complex software engineering, knowledge work, and scientific workflows, and made it available to developers, enterprises, and Google AI Pro/Ultra subscribers. Google lists API pricing at $3 per million input tokens \($0.15 cached\) and $15 per million output tokens, with a 1 million-token context window. The company reports a score of 58.6 on Artificial Analysis&\#x27;s coding-agent index, 61 on its intelligence index at the xhigh setting \(third overall\), and 65.2% on Terminal-Bench 4.1, while claiming 32% lower per-task cost than Carbon at the default high setting.

hackernews · yigitdemirag · Nov 18, 21:34 · [Discussion](https://news.ycombinator.com/item?id=50552424)

**「Context」** Gemini 4 Neon joins Google&\#x27;s Gemini 4 family alongside Carbon, the variant the announcement uses as its cost comparison and that commenters describe as optimized for long-horizon work. That distinction matters because Google is positioning Neon around fast end-to-end execution for software engineering, knowledge work, and research rather than as the top scorer on every evaluation. The benchmark references—Artificial Analysis&\#x27; coding-agent index and Terminal-Bench 4.1—are external evaluation schemes used to compare Neon with Carbon and other models.

**「Impact」** Developers can access Neon through Google AI Pro/Ultra or pay $3 per million input tokens and $15 per million output tokens, and teams comparing it with Carbon will need to weigh its claimed lower per-task cost and coding-agent performance against its different positioning rather than assume it is a direct replacement.

**「Community discussion」** Commenters said the expanding set of Gemini and competitor names—Neon, Carbon, Sol, Astra, Opus—is hard to map to concrete use cases, with one calling for Google to settle on a naming scheme. Another argued Neon is stronger overall than Carbon but that Carbon remains better for long-horizon research-scale reasoning, while a third reported Neon running at 127 tokens/s on OpenRouter versus 46 for Carbon and questioned the flagship positioning.

**Tags**: `#Gemini 4 Neon`, `#Google AI`, `#large language models`, `#AI model releases`, `#model naming`

---

<a id="item-tech-news-2"></a>
### [NGINX2Root chain exploits Nginx HTTP/2 for unauthenticated code execution](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

Wiz reports two Nginx HTTP/2 vulnerabilities that it says permit unauthenticated remote code execution; a summary of Xint&\#x27;s broader NGINX2Root research describes five Nginx flaws plus a Linux kernel bug chained to take an attacker from an Nginx visitor to host root. The specifically named HTTP/2 flaw, CVE-2026-123007, is a flow-control memory-corruption bug that allows unauthenticated command execution inside an Nginx worker. Nginx 1.30.7 and 1.31.9, released November 18, fix 10 CVEs; Rapid7 has published a proof-of-concept exploit, and no in-the-wild exploitation has been reported. Administrators who cannot upgrade should disable externally exposed HTTP/2; HTTP/2 is not enabled by default, and a community-cited W3Techs figure puts it on about 12% of servers.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Background」** HTTP/2 support in nginx is an optional listener setting rather than a default, so this attack surface exists only where operators have enabled it on a public-facing server. Nginx handles requests in worker processes; CVE-2026-123007 is a flow-control memory-corruption flaw that lets an unauthenticated attacker execute commands in that worker, and the broader NGINX2Root chain adds a Linux kernel flaw to reach host root.

**「Patch or disable HTTP/2」** Operators who terminate HTTP/2 in nginx should upgrade to 1.30.7 or 1.31.9, or disable \`http2\` on externally reachable listeners if they cannot patch, because Rapid7 has published proof-of-concept scripts for CVE-2026-123007. The practical exposure is narrower than &quot;unauthenticated RCE&quot; alone implies: Rapid7 notes that available bandwidth and connection timeouts limit Internet exploitation, with its reproduced attack taking about two and a half minutes, while Wiz rates both flaws CVSS 4.0 9.2 and stresses that secure application code does not protect the underlying sites and APIs.

**「Community discussion」** Commenters focused on disclosure timing: black3r argued the fix appeared in the open-source repository a week before the advisory, with a commit message naming Xint.io, so a public warning to disable HTTP/2 could have come sooner. fduran noted HTTP/2 is not on by default and cited W3Techs&\#x27; roughly 12% adoption figure, while testtestmetest disputed practical exploitability, saying it requires about 128 GB of HTTP/2 traffic and specific CPU instructions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.rapid7.com/blog/post/ve-cve-2026-123007-critical-nginx-http-2-integer-underflow-leads-to-rce-fixed/">Rapid 7 discloses a critical vulnerability affecting NGINX HTTP / 2 that...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://github.com/sfewer-r7/CVE-2026-123007">GitHub - sfewer-r7/ CVE - 2026 - 123007 : Proof-of-concept ( PoC ) scripts...</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#http2`, `#vulnerability`, `#remote-code-execution`, `#security`

---

<a id="item-tech-news-3"></a>
### [Google DeepMind Makes Genie 4 Available to Eligible AI Ultra Subscribers](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 8.0/10

Google DeepMind has made Genie 4, a new version of its generative world model, available to eligible Google AI Ultra subscribers. The supplied announcement material does not specify model capabilities, benchmarks, regional limits, or separate pricing for Genie 4. It also does not clarify how eligibility is determined, leaving the practical scope of the rollout unclear.

hackernews · leumon · Nov 18, 18:49 · [Discussion](https://news.ycombinator.com/item?id=50550415)

**「Background」** Project Genie is Google DeepMind’s generative world-model project for creating interactive worlds. The Genie 4 update arrived in research preview with real-time steering and audio, and Gemini models act as a director that plans steps and checks frames while Genie renders the visuals; Google had not published a technical report at release.

**「Practical limits for developers」** Developers cannot yet treat Genie 4 as a drop-in game engine: it generates plausible next states from prompts and interaction rather than storing an authoritative world state, so teams building deterministic gameplay would still need a conventional engine for state and could use Genie only for generated content. Access is also gated to eligible Google AI Ultra subscribers, and one commenter reports the Ultra page still lists Genie 3, leaving UK and Workspace users unsure whether they can use it.

**「Community discussion」** Commenters focused on access confusion: one user in the UK said a Workspace account could not obtain AI Ultra and a non-Workspace Gmail account still listed Genie 3 as the Ultra benefit, questioning whether region or an outdated page was responsible. Others speculated that the model could someday underlie game engines, asking whether Google would permit games like GTA to be remade on it or whether it could become a far more capable Roblox-like platform.

<details><summary>References</summary>
<ul>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google ’s Genie 4 world model adds audio, more realistic... | TechCrunch</a></li>
<li><a href="https://www.deeplearning.ai/the-batch/issue-378">Gemini 4 Carbon Heads Toward Wider Availability , What...</a></li>
<li><a href="https://alaintural.com/writing/world-models-are-not-game-engines/">World Models Are Not Game Engines Yet · Alain Tural</a></li>

</ul>
</details>

**Tags**: `#generative world models`, `#Google DeepMind`, `#AI model releases`, `#AI subscription access`, `#game engines`

---

<a id="item-tech-news-4"></a>
### [Microsoft unveils seven AI models pitched on scalable price-performance](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

Microsoft announced seven new AI models at its Ignite 2026 event, framing the lineup around scalable price-performance rather than frontier capability. The release includes MAI Code 2, which commenters say they have been testing for coding work; the available announcement material gives no parameter counts, benchmark scores, pricing tiers, or availability dates for any of the seven models. The price-performance positioning is a vendor claim, and no independent measurement of the models&\#x27; performance is included.

hackernews · gmays · Nov 18, 16:08 · [Discussion](https://news.ycombinator.com/item?id=50548021)

**「Context」** Microsoft used Ignite 2026 to present a seven-model family spanning coding, cybersecurity, image generation, speech, healthcare transcription and decision routing, with MAI Code 2 as its new flagship agentic-coding line. The launch is explicitly framed around price-performance: Microsoft says MAI Code 2 Flash is comparable to GPT-6 Luna at 65% of the price and to Haiku 5.5 at 20% of the price, while MAI Image 2.7 is said to lead Artificial Analysis image editing at one-fifth the price of GPT Image 2.6 Sunburst \(max\). It also signals a shift toward selling its own models alongside hosting other companies’ models on Azure.

**「Evaluation burden for enterprise coding teams」** For enterprise development teams, the practical consequence is a new cost-focused option for everyday coding work: Microsoft says MAI Code 2 and MAI Code 2 Flash deliver leading performance at a fraction of the cost of competing models, and that MAI Code 2 is becoming a workhorse inside Microsoft products. Because the supplied material provides no benchmark numbers or independent evaluation, teams considering a switch should test code quality, latency, and integration against their existing models rather than treat the vendor&\#x27;s price-performance claim as established.

**「Community discussion」** One commenter \(johnshahbazian\) said they had been testing MAI Code 2 and found it &quot;quite good&quot; for their usual work, judging Microsoft&\#x27;s claim of parity with Opus or Sol to be broadly reasonable. Another \(ahmedfromtunis\) argued Microsoft should release some models as open source or open weight if it hopes to secure market share, warning of a &quot;Windows Phone OS all over again&quot; scenario, while a third dismissed the keynote as shallow and lacking innovation.

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world-class models at scalable price-performance ...</a></li>
<li><a href="https://windowsforum.com/news/microsoft-ignite-2026-mai-code-2-models-agent-365-governance-and-enterprise-ai-stack.453003/">Microsoft Ignite 2026: MAI Code 2 Models, Agent 365 ...</a></li>
<li><a href="https://windowsforum.com/news/microsoft-ignite-2026-mai-code-2-and-new-ai-models-target-lower-costs.452751/">Microsoft Ignite 2026: MAI Code 2 and New AI Models Target ...</a></li>
<li><a href="https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/">MAI Code 2 and Code 2 Flash: Everyday coding at... | Microsoft AI</a></li>
<li><a href="https://mobidevices.com/en/microsoft-mai-code-2">Microsoft releases MAI Code 2 AI model | MobiDevices.com</a></li>

</ul>
</details>

**Tags**: `#Microsoft`, `#AI models`, `#LLM releases`, `#price-performance`, `#MAI Code 2`

---

<a id="item-tech-news-5"></a>
### [Quad9 France exit fuels debate over DNS anti-piracy blocking](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

Quad9 has withdrawn from France in a dispute over anti-piracy DNS blocking, and an analysis argues that DNS resolvers are the wrong enforcement point for such measures. The piece casts DNS-level blocking as a policy and infrastructure problem rather than an effective way to reduce piracy. The supplied item does not detail the court order&\#x27;s scope, the specific domains involved, or the timing of the withdrawal.

hackernews · ritzaco · Nov 18, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50545958)

**「Background」** Quad9 is a nonprofit public recursive DNS resolver that normally blocks domains associated with malware and phishing. According to Tech Stackups and Cloudflare, a French court order sought by beIN Sports required blocking piracy-related domains, and Quad9 chose to stop serving users in France on November 24, 2026, rather than comply.

**「Impact」** The practical consequence is a compliance fork for public DNS operators: comply with national blocking orders or exit the jurisdiction, which can reduce resolver choice for users in countries that mandate DNS filtering. Operators deploying public resolvers should treat national anti-piracy blocking mandates as a jurisdictional risk.

**「Community discussion」** Commenters were skeptical of DNS blocking as anti-piracy policy: one described non-prosecution efforts as a backdoor to suppressing speech, while another argued that cheaper, DRM-free paid downloads and a better legal experience are the only effective remedy. Others questioned whether blame belongs with the French court for misapplying the law or with lawmakers for passing it, and whether individual pirates should be pursued when commercial IP use by AI companies is not.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Quad9">Quad 9 - Wikipedia</a></li>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad 9 ’s withdrawal from France : A canary in the... | Cloudflare Blog</a></li>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad 9 Is Leaving France : Why DNS Resolvers Are... | Tech Stackups</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet policy`, `#content blocking`, `#piracy`, `#Quad9`

---

<a id="item-tech-news-6"></a>
### [A History of Early Intel CPUs From 4004 to 486](https://pikuma.com/blog/history-of-x86-4004-to-486) ⭐️ 7.0/10

A pikuma article offers a detailed historical overview of early Intel CPUs spanning the 4004 through the 486, a period that includes the origins of x86. It is an explanatory retrospective rather than a report of a new release, product change, or benchmark. The accompanying Hacker News discussion adds technical corrections and context on several claims in the article.

hackernews · ibobev · Nov 18, 14:47 · [Discussion](https://news.ycombinator.com/item?id=50546967)

**「Background」** The x86 family takes its name from Intel&\#x27;s 8086, introduced in 1978 as a 16-bit CPU with 29,000 transistors and clock speeds of 5 to 10 MHz. Its lineage traces through earlier Intel chips including the 4004 and the byte-oriented 8008, introduced in April 1972.

**「Community Discussion」** Commenters offered technical corrections: one argued that little-endian ordering originally came from data-access speed on the 2200, not arithmetic, and that the 8085 was not alone in multiplexing address and data; another said Intel engineers, including Stan Mazor, did modify the 8008 instruction set despite the article&\#x27;s wording. A separate thread questioned why Intel and AMD still make modern PCs start in a 1978-era mode, with one commenter arguing that only BIOS writers would notice a change.

<details><summary>References</summary>
<ul>
<li><a href="https://cpumuseum.jimdofree.com/museum/intel/8008/">Intel 8008 - CPU MUSEUM - MUSEUM OF MICROPROCESSORS...</a></li>
<li><a href="https://www.auslogics.com/en/articles/intel-processor-generations-in-a-timeline-history-and-evolution/">Intel Processor Generations in a Timeline: History ... — Auslogics Blog</a></li>
<li><a href="https://dokumen.tips/documents/pre-pentium-intel-processors-4004-8008-8080-80868088-80186-80286-80386-80486.html">(PPT) Pre-Pentium Intel Processors 4004 8008 8080 8086 /8088 80186...</a></li>

</ul>
</details>

**Tags**: `#x86`, `#CPU history`, `#computer architecture`, `#Intel`, `#hardware`

---

<a id="item-tech-news-7"></a>
### [Show HN: Interactive Voyager 1 Tour Down to a Memory Chip](https://rshekhar.com/voyager/) ⭐️ 7.0/10

A Show HN interactive site lets visitors explore Voyager 1&\#x27;s systems down to individual memory chips, including one bit of the command computer&\#x27;s memory, along with live positions for both Voyagers, the nuclear battery&\#x27;s 24 plutonium spheres, the Golden Record cover, the radio repair story, and the Earth dish currently listening. The author provides direct links to the hardest-to-find sections and a four-minute film; the post says Voyager 1 reached one light-day from Earth that day. It is an educational visualization rather than a new mission announcement or independently verified engineering analysis.

hackernews · raj-shekhar · Nov 18, 16:18 · [Discussion](https://news.ycombinator.com/item?id=50548161)

**「Background」** Voyager 1, launched in 1977, explored the outer planets and has been traveling out of the solar system for nearly five decades. On November 18, 2026, it reached one light-day from Earth, making it the first human-made object to travel that far, according to NASA and Smithsonian coverage.

**「Impact」** For readers who want to examine a specific subsystem, the author&\#x27;s direct links make the RTG, memory-chip, Golden Record, and radio-repair sections easier to share or assign without navigating the full model.

**「Community Discussion」** Commenters welcomed the project, with one linking a separate Golden Record tribute and an audio-to-image decoder and another asking whether the site was AI-generated and checked against authoritative sources. A hardware-focused commenter also pressed for the exact physical failure mechanism behind the memory read errors, while another said the visualization is engaging despite missing some details.

<details><summary>References</summary>
<ul>
<li><a href="https://svs.gsfc.nasa.gov/15120">How Far Away Is Voyager 1? One Light-Day, Explained</a></li>
<li><a href="https://www.smithsonianmag.com/blogs/air-space-museum/2026/11/18/nasas-voyager-1-has-reached-1-lightday-from-earth-it-is-the-first-humanmade-object-in-space-to-reach-that-distance/">NASA’s Voyager 1 has reached 1 light‑day from Earth. It is ...</a></li>

</ul>
</details>

**Tags**: `#Voyager 1`, `#interactive visualization`, `#spaceflight computers`, `#hardware education`, `#memory chips`

---

<a id="item-tech-news-8"></a>
### [Stenberg: AI Rust rewrites of curl lag 300 upstream commits](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

curl creator Daniel Stenberg reported that AI coding agents spent a little over three weeks converting 185,000 lines of curl&\#x27;s C code into 340,000 lines of Rust, while the real curl project merged more than 300 commits over the same span. A little over 200 of those were bugfixes, plus several vulnerability fixes, none of which the Rust rewrites contain, he wrote in a November 17 blog post quoted by Simon Willison. Stenberg said he expects roughly another 200 fixes in the following month and asked whether the clones can keep up. The line counts are his own \(&quot;I counted&quot;\) and the figures are his account of the upstream repository, not an independently verified measurement.

rss · Simon Willison · Nov 18, 15:58

**「Context: curl&\#x27;s C codebase and the recurring rewrite argument」** curl is a long-standing open-source data-transfer tool and library, distributed largely as a C codebase that ships frequent point releases bundling security fixes and dozens of bugfixes. Proposals to rewrite it from scratch have circulated for years — a 2021 r/programming thread titled &quot;I Could Rewrite Curl&quot; debated exactly that premise — and the AI-agent Rust ports Stenberg is responding to are third-party efforts, not an official migration by the curl project.

**「Impact」** For developers evaluating an AI-generated port, the practical consequence is that a rewrite captures a snapshot and starts diverging immediately: anyone running such a Rust version would lack the bugfixes and security patches that keep landing upstream. Keeping a port viable therefore requires an ongoing process to track and reapply curl&\#x27;s commits, not a one-time conversion.

<details><summary>References</summary>
<ul>
<li>curl 8.14.1 with Daniel Stenberg - YouTube</li>
<li>“I Could Rewrite Curl” : r/programming - Reddit</li>

</ul>
</details>

**Tags**: `#AI code generation`, `#curl`, `#Rust`, `#open source maintenance`, `#security`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed minutes signal more rate hikes and AI inflation risk](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

Federal Reserve meeting minutes released Wednesday showed officials expected further rate increases would likely be needed to return inflation to 2%, while the committee voted 10-2 to hold its benchmark rate at 3.75%-4%, with both dissents favoring a quarter-point hike. The minutes also said AI-related demand was &quot;a material source of inflation risk&quot; and flagged rapid growth in AI-related debt held through complex, opaque financing.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** The Fed&\#x27;s benchmark rate — the federal funds rate, which banks charge each other overnight and which helps set borrowing costs across the economy — has stayed in a 3.75%–4% range since the Oct. 27–28 meeting, where two officials dissented in favor of an immediate quarter-point increase. The minutes documenting that debate were released Wednesday.

<details><summary>References</summary>
<ul>
<li><a href="https://www.federalreserve.gov/monetarypolicy/files/fomcminutes20261028.pdf">Minutes of the Federal Open Market Committee - October 27-28 ...</a></li>
<li><a href="https://www.federalreserve.gov/monetarypolicy/fomcminutes20261028.htm">FOMC Minutes, October 27-28, 2026 - Federal Reserve Board</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#AI risks`, `#interest rates`

---

<a id="item-finance-news-2"></a>
### [Fed’s Waller floats half-point December rate hike](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 8.0/10

Federal Reserve Governor Christopher Waller said Wednesday the central bank may need a half-percentage-point interest-rate hike at the Dec. 8-9 policy meeting to “shock people” and bring inflation down, a larger move than the quarter-point increase futures markets fully price.

rss · CNBC Finance · Nov 18, 15:13

**「Background」** The Fed cut rates three times in 2025, then raised them in September and held steady in October, while most inflation readings remained above 3% versus its 2% target.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#market expectations`

---

<a id="item-finance-news-3"></a>
### [Tencent Q3 2026: AI capex surges, free cash flow turns negative](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

Tencent reported 2026 third-quarter revenue of 207.3 billion yuan, up 8% from a year earlier and below market expectations, while net profit attributable to shareholders rose 0.8% to 63.6 billion yuan. Capital expenditure was 81.433 billion yuan, far above the 55.4 billion yuan market estimate, leaving quarterly free cash flow at negative 69.1 billion yuan; Tencent also said its WorkBuddy product used more than 100 trillion tokens per day, the highest among domestic large-language-model AI products on a daily basis.

telegram · zaihuapd · Nov 18, 09:20

**「Background」** WorkBuddy is Tencent&\#x27;s AI assistant; the company said it had more than 10 million daily active users as of early November, which gives a sense of the user base behind the daily token figure.

<details><summary>References</summary>
<ul>
<li><a href="https://www.sohu.com/a/1103246665_114760">腾讯WorkBuddy日活跃用户数超1000万，日均Token调用量超100万亿_模型_...</a></li>

</ul>
</details>

**Tags**: `#腾讯`, `#财报`, `#AI资本开支`, `#自由现金流`, `#大模型Token用量`

---

<a id="item-finance-news-4"></a>
### [China and South Korea announce substantive conclusion of FTA services and investment talks](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

China and South Korea said on November 18 that follow-up negotiations on services and investment under their bilateral free trade agreement had reached a substantive conclusion, with China committing to most-favored-nation treatment for South Korean films and games and wider openings in tourism, legal, construction and financial services. The two sides also agreed to extend joint audiovisual production beyond film to TV series, animation, variety shows and documentaries; the talks began in March 2018 and some technical items still need working-level negotiation, so the deal is not yet finalized or ratified.

telegram · zaihuapd · Nov 18, 10:02

**「Background」** The two countries&\#x27; free trade agreement took effect in 2015, but services and investment were left to follow-up talks that began in March 2018 and only resumed in January 2025 after a four-year gap, according to Lianhe Zaobao. Those earlier rounds covered the same sectors now listed in the announcement, which both sides describe as a substantive rather than a signed or ratified conclusion.

**「Who is affected」** South Korean film, gaming and television producers, together with their Chinese co-production partners, stand to gain first from the pledged market openings, but the commitments are not yet enforceable: some technical points remain with working-level negotiators and the deal has not been finalized or ratified.

<details><summary>References</summary>
<ul>
<li><a href="https://www.zaobao.com.sg/realtime/china/story20250116-5743403">时隔四 年 韩 中 重 启 自 贸 协 定 服 贸 投 资 后 续 谈 判 | 联合早报</a></li>

</ul>
</details>

**Tags**: `#China-South Korea FTA`, `#services trade`, `#investment liberalization`, `#audiovisual industry`, `#financial services`

---