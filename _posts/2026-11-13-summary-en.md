---
layout: default
title: "Horizon Summary: 2026-11-13 (EN)"
date: 2026-11-13
lang: en
---

> From 45 items, 12 important content pieces were selected

---

**Technology News**
1. [Anthropic announces IPO with reported $70–78 price range](#item-tech-news-1) ⭐️ 9.0/10
2. [Smolmaxxing claims 16B LLM inference on sub-1GB devices](#item-tech-news-2) ⭐️ 8.0/10
3. [Google releases Gemini 4 Hydrogen and Orchestrator for coding agents](#item-tech-news-3) ⭐️ 8.0/10
4. [Rust 1.100 stabilizes never type and custom allocators](#item-tech-news-4) ⭐️ 8.0/10
5. [UMAP 0.6 adds recursive initialization and new optimizers](#item-tech-news-5) ⭐️ 8.0/10
6. [Chips and Cheese Interviews AMD&\#x27;s Mike Clark on Zen 6](#item-tech-news-6) ⭐️ 7.0/10
7. [CVE-2026-6460 PostgreSQL type-confusion write-up draws RCE debate](#item-tech-news-7) ⭐️ 7.0/10
8. [Microsoft 365 email outage drags on for hours as status updates lag](#item-tech-news-8) ⭐️ 7.0/10
9. [Reddit Audit Finds Meta TRIBE v2 Lacks Retinotopic and Tonotopic Maps](#item-tech-news-9) ⭐️ 7.0/10
10. [US Commerce Department finalizing rule to block Chinese AI firms&\#x27; remote chip access](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [China approves Eli Lilly&\#x27;s oral weight-loss drug, the country&\#x27;s first oral GLP-1 for obesity](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed says October 2027 meeting will not include a rate vote](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Anthropic announces IPO with reported $70–78 price range](https://ipo.anthropic.com/us/) ⭐️ 9.0/10

Anthropic has posted an IPO announcement, and a Hacker News commenter citing the linked documents reports a $70–78 per-share price range and the ticker ANT on Nasdaq. The same commenter lists an $85.3B gross deal size including a $26B private placement, an implied market cap of roughly $968B at the $74 midpoint across 13.09B shares, Q3 2026 revenue of $17.0B \(up 1,127% year over year\), a run rate of about $81B as of October 2026, and $900.9B in compute commitments through 2045. The item supplies no source text of its own, so these terms are commenter-reported and are not independently confirmed here.

hackernews · josephljohnston · Nov 12, 11:46 · [Discussion](https://news.ycombinator.com/item?id=50465829)

**「Background」** Anthropic, the developer of the Claude model family, had remained privately held through successive venture funding rounds, so this listing is its first sale of shares to public investors. The updated filing reported by CNBC sets the offering at 825 million shares priced at $70–$78; at the $74 midpoint, that values the company at about $968 billion \(tool-2-1, tool-2-2\).

**「Impact」** If the reported terms hold, public investors would be valuing Anthropic at roughly $968B while underwriting $900.9B of compute commitments running through 2045, making those long-dated infrastructure obligations something ANT shareholders carry directly rather than private backers. The reported customer base of more than 11,900 accounts with at least $100K in trailing revenue, including about 250 above $10M, is the scale investors would weigh against those commitments.

**「Community discussion」** Commenters disagreed about what the IPO timing says about Anthropic&\#x27;s position: one argued that if the models were capable of recursive self-improvement, investors would have delayed the listing to reach clear market dominance instead of accepting dilution now, while others said local models are already good enough for most users and that Anthropic and OpenAI will have to move toward end-user applications. Another commenter raised concern that the Series H could already be underwater if the IPO prices at the low end of the range.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/10/anthropic-sets-price-range-of-70-to-78-in-upcoming-ipo.html">Anthropic sets price range of $70 to $78 in upcoming IPO - CNBC</a></li>
<li><a href="https://xenospectrum.com/en/anthropic-ipo-roadshow-valuation/">Anthropic IPO Values It at About $968 Billion as Net Loss ...</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#IPO`, `#AI industry`, `#LLM economics`, `#compute`

---

<a id="item-tech-news-2"></a>
### [Smolmaxxing claims 16B LLM inference on sub-1GB devices](https://github.com/hyperionaidev/smolmaxxing/) ⭐️ 8.0/10

An open-source project called Smolmaxxing is trying to run LLM inference on small and old hardware; its author reports reaching 16B-parameter models on a first-generation iPad Air and a Xiaomi TV box, each with less than 1 GB of usable memory. The project publishes custom kernels, modified models on Hugging Face, and results intended for reproduction, but the speed and capability claims have not been independently verified in the supplied material. The effort targets memory-constrained legacy devices rather than conventional GPUs or servers.

hackernews · mrashad74 · Nov 12, 15:23 · [Discussion](https://news.ycombinator.com/item?id=50468888)

**「How sub-1GB inference is possible」** The approach relies on mixture-of-experts models, where only a subset of parameters is activated per token, so the full weight set does not need to be resident at once. The project&\#x27;s own repository states that its iPad Air and Xiaomi TV Box builds keep only part of each model in memory and read the remainder from flash as needed.

**「Impact」** Developers can inspect and reproduce the kernels and run the modified Hugging Face models, but they should treat the reported throughput as unverified and check whether a given device has enough usable memory and kernel support. The main compatibility question is whether the same results hold outside the two named devices.

**「Community discussion」** Commenters focused on how much of the task is now agent-automatable: Farmadupe2 argued that writing an inference engine is largely compute and multiplication, so sourcing old hardware and granting SSH access may be harder than the code. Others shared related small-model work, including a 6.5M-parameter local model for reasoning and experiments with 2–11 GB Maxwell and Pascal GPUs for tool calling.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/hyperionaidev/smolmaxxing/">GitHub - hyperionaidev / smolmaxxing : maxxing the ability to run...</a></li>

</ul>
</details>

**Tags**: `#LLM inference`, `#edge computing`, `#model optimization`, `#open source`, `#low-resource hardware`

---

<a id="item-tech-news-3"></a>
### [Google releases Gemini 4 Hydrogen and Orchestrator for coding agents](https://antigravity.google/blog/gemini-4-hydrogen-in-google-antigravity/) ⭐️ 8.0/10

Google released Gemini 4 Hydrogen, a model aimed at everyday coding and agentic workflows, alongside an Orchestrator feature intended to coordinate work across models. It is available to developers, enterprises, and general users at $1.50 per million input tokens and $7.50 per million output tokens. Google says Hydrogen runs 2.5× faster than Gemini 3.8 Flash and raises its Terminal-Bench 4.1 score from 18.2% to 57%, and that its default tier beats Argon on the Artificial Analysis index; these are vendor figures, and the supplied material does not explain how Orchestrator routes requests or how it is billed.

hackernews · jonbaer · Nov 12, 18:52 · [Discussion](https://news.ycombinator.com/item?id=50472260)

**「How Orchestrator fits」** In Antigravity, the Orchestrator coordinates multi-model work: Google&\#x27;s blog says it reached near-Carbon task success on Terminal-Bench 4.1 while consuming 24% less quota and finishing 19% faster, and the Antigravity SDK can instead wire Hydrogen and Carbon directly for explicit pipelines. Google also describes Hydrogen as a fast, cost-efficient model built for reliable agentic workflows and everyday tasks.

**「Impact」** Teams running coding agents have a new candidate default in Hydrogen, given its stated speed gain over 3.8 Flash and flat per-token pricing. Before moving production traffic, though, developers using Orchestrator in a multi-model pipeline should verify how cached context and calls to secondary models are charged, since the announcement does not specify this.

**「Community discussion」** Commenters welcomed a faster Flash-class option, with one saying Argon and Carbon were slow enough that they had switched to 3.8 Flash, while others questioned the Hydrogen/Argon/Carbon naming and how caching and billing work when a pipeline calls out to another model. One developer, who assigns subagents models based on task difficulty, said they were uneasy about delegating that choice to a model because models tend to be optimistic about their own capabilities.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/">Introducing Gemini 4 Hydrogen for Agentic Workflows</a></li>
<li><a href="https://antigravity.google/blog/gemini-4-hydrogen-in-google-antigravity/">Gemini 4 Hydrogen and Orchestrator | Google Antigravity Blog</a></li>

</ul>
</details>

**Tags**: `#Gemini 4`, `#Google Antigravity`, `#LLM orchestration`, `#multi-model pipelines`, `#AI model release`

---

<a id="item-tech-news-4"></a>
### [Rust 1.100 stabilizes never type and custom allocators](https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/) ⭐️ 8.0/10

Rust 1.100.0 has shipped, stabilizing the never type and custom allocators for Rust developers. Cargo gains a minimum publish age setting, or dependency cooldown, that makes the resolver ignore versions newer than the configured threshold unless they are already in Cargo.lock, and it now warns about unused dependencies. \`cargo install\` also uses the lockfile already present in the .crate tarball by default, making \`--locked\` a no-op.

hackernews · mbStavola · Nov 12, 18:39 · [Discussion](https://news.ycombinator.com/item?id=50472038)

**「Cargo dependency cooldowns」** Cargo&\#x27;s resolver selects dependency versions that satisfy the constraints in Cargo.toml, while Cargo.lock records the exact versions already chosen for a project. RFC 3923 adds a minimum publish age, or cooldown, that makes the resolver ignore versions published inside the configured window unless they are already locked; Rust 1.100 exposes this as an opt-in setting intended to reduce exposure to supply-chain attacks.

**「Impact」** For Rust teams, the cooldown setting offers a way to avoid adopting crates published in the last configured window, but versions already recorded in Cargo.lock remain eligible. Teams that script \`cargo install --locked\` should account for the flag no longer changing behavior because the tarball lockfile is used by default.

**「Community discussion」** Commenters welcomed the release and singled out the never type, custom allocators, dependency cooldowns, and unused-dependency warnings as favorites; one also noted that useful stabilizations such as \`bool::toggle\(\)\`, \`Box::map\(\)\`, and \`str::trim\_prefix\(\)\` were not mentioned in the blog post. Another commenter questioned whether compiler performance had improved and complained about repeatedly clearing large temporary build files.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/">Announcing Rust 1 . 100 .0 | Rust Blog</a></li>
<li><a href="https://byteiota.com/rust-1100-cargo-cooldowns/">Rust 1 . 100 : Cargo Dependency Cooldowns Are Here... | byteiota</a></li>
<li><a href="https://rust-lang.github.io/rfcs/3923-cargo-min-publish-age.html">3923 - cargo -min-publish-age - The Rust RFC Book</a></li>

</ul>
</details>

**Tags**: `#Rust`, `#Cargo`, `#language releases`, `#never type`, `#custom allocators`

---

<a id="item-tech-news-5"></a>
### [UMAP 0.6 adds recursive initialization and new optimizers](https://www.reddit.com/r/MachineLearning/comments/1xudaah/umap_06_new_initialization_new_optimizers_and/) ⭐️ 8.0/10

UMAP 0.6 has been released with a new recursive initialization that lays out a coarse graph and refines it, new optimizers using hard-negative mining, and nearest-neighbor search the maintainer reports is about 4× faster through better use of PyNNDescent. The maintainer reports that on 3 million arXiv papers UMAP 0.6 finishes in under five minutes, while a seeded UMAP 0.5 run takes 52 minutes single-threaded; the new optimizers allow a fixed-seed run to be reproducible while using every core. The release is said to resolve finer cluster structure and improve neighborhood accuracy at million scale; these are maintainer claims rather than independent measurements. Install with pip install -U umap-learn or from conda-forge, but the new initialization and optimizers are opt-in via compatibility\_layout=False because they change output and are planned to become defaults later.

reddit · r/MachineLearning · /u/lmcinnes · Nov 12, 13:51

**「Background」** UMAP is a dimensionality-reduction method that lays out high-dimensional data in a low-dimensional space. Earlier versions relied on spectral or PCA initialization and optimized within a limited attraction-repulsion regime; UMAP 0.6 replaces those starting points with a recursive UMAP-based initialization and adds hard-negative mining for large datasets.

**「Impact」** Users who need embeddings comparable to existing UMAP 0.5 outputs should keep compatibility\_layout at its default for now; those who set compatibility\_layout=False can use the new initialization and optimizers, but should expect different layouts and test downstream results before switching.

**Tags**: `#UMAP`, `#dimensionality reduction`, `#open source`, `#performance`, `#machine learning`

---

<a id="item-tech-news-6"></a>
### [Chips and Cheese Interviews AMD&\#x27;s Mike Clark on Zen 6](https://chipsandcheese.com/p/talking-zen-6-with-mike-clark-at) ⭐️ 7.0/10

Chips and Cheese published an in-depth interview with AMD&\#x27;s Mike Clark discussing Zen 6, AMD&\#x27;s next-generation CPU architecture, and the piece was circulated on Hacker News. The supplied material contains no transcript or technical content from the interview, so no specific architectural changes, performance figures, core counts, or launch timing for Zen 6 can be confirmed from it. The item is a reported technical conversation rather than a product announcement, and any claims about Zen 6 must be attributed to what Clark said in the interview rather than treated as a shipped capability.

hackernews · dverlaeckt80 · Nov 12, 14:12 · [Discussion](https://news.ycombinator.com/item?id=50467460)

**「Background」** Mike Clark is an AMD architect closely identified with the Zen line, and he has previously explained design decisions spanning multiple Zen generations. Zen 6 is AMD’s next-generation CPU core, and AMD executives including Clark have said it was not designed specifically for agentic AI workloads, a positioning that helps frame the architecture discussion.

**「Community Discussion」** The one supplied comment, from koutakun, highlights how uncommon it is to see CPU designers discuss their work at this level of depth, framing the interview&\#x27;s value as its rarity rather than making any technical argument about Zen 6.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cloudspress.com/what-mike-clarks-2021-anandtech-interview-revealed-about-amds-zen-strategy/">What Mike Clark ’s AnandTech Zen Interview Really Predicted</a></li>
<li><a href="https://mezha.net/eng/news/mezha-385a51640a816c08fe1be1d3_amd_executives_say/">AMD executives say Zen 6 was not designed specifically for... | Межа</a></li>

</ul>
</details>

**Tags**: `#AMD Zen 6`, `#CPU architecture`, `#hardware`, `#semiconductors`, `#technical interview`

---

<a id="item-tech-news-7"></a>
### [CVE-2026-6460 PostgreSQL type-confusion write-up draws RCE debate](https://mehmetince.net/part-3-6-how-i-ended-up-turning-a-22-year-old-postgresql-type-confusion-primitive-into-rce-cve-2026-6460/) ⭐️ 7.0/10

A detailed write-up published Nov. 12 traces CVE-2026-6460 to a 22-year-old PostgreSQL type-confusion primitive and describes a path from it to remote code execution. The article frames the issue as an exploitation chain built on long-standing PostgreSQL internals rather than a newly introduced defect. Commenters disputed the RCE label, arguing that the chain starts with an authenticated database account and is better classified as privilege escalation.

hackernews · ozirus · Nov 12, 18:22 · [Discussion](https://news.ycombinator.com/item?id=50471761)

**「PostgreSQL type tracking flaw」** PostgreSQL stores values in an internal Datum representation whose type is tracked separately rather than being self-identifying. CVE-2026-6460 arises from inadequate tracking of those typed values, allowing stale values to appear in data-dictionary entries and PL/pgSQL variables after data-definition sequences such as ALTER TABLE ... ADD COLUMN followed by ROLLBACK. The flaw affects PostgreSQL versions before 18.7, 17.12, 16.16, 15.20, and 14.25, and exploitation requires an authenticated user with permissions to create or alter database objects.

**「Community discussion」** Commenters including logophobia and jmuguy argued that the exploit is better described as privilege escalation than RCE because it requires some authenticated database access; logophobia said this makes it mainly a multi-tenant database issue. Other commenters thanked the author for documenting the zero-day path and PostgreSQL internals.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-6460">CVE-2026-6460 - Red Hat Customer Portal</a></li>
<li><a href="https://app.opencve.io/cve/CVE-2026-6460">CVE-2026-6460 - Vulnerability Details - OpenCVE</a></li>

</ul>
</details>

**Tags**: `#postgresql`, `#vulnerability-research`, `#type-confusion`, `#CVE`, `#database-security`

---

<a id="item-tech-news-8"></a>
### [Microsoft 365 email outage drags on for hours as status updates lag](https://status.cloud.microsoft/) ⭐️ 7.0/10

Microsoft 365 suffered a multi-hour service degradation that left email unavailable for many organizations, while Teams chat and meetings continued to work and Azure infrastructure appeared unaffected, according to user reports. Microsoft&\#x27;s status page was itself unreliable, but an RSS feed carried periodic updates: at 9:02 PM UTC the company said it had validated an alternative health check on a subset of affected infrastructure, allowing those servers to return to service, and by 10 PM ET it said the change applied to improve serviceability &quot;is not taking as expected&quot; and that it was identifying alternate workstreams to add capacity amid &quot;sustained traffic management imbalances.&quot; The supplied material contains no root cause or restoration timeline, and one system administrator reported email still down at hour eight for an organization of more than 15,000 employees.

hackernews · dkpk · Nov 12, 18:20 · [Discussion](https://news.ycombinator.com/item?id=50471731)

**「Background」** Microsoft 365 is Microsoft&\#x27;s cloud subscription suite, and its email component is Exchange Online, which users reach through Outlook clients and the web. Because Microsoft hosts that service, a fault on its side can remove email access for many organizations at once rather than being confined to a single company&\#x27;s mail server.

**「Impact for IT teams」** Affected organizations lost email as a working channel for hours, and because the public status page was not updating well, administrators had to subscribe to the RSS feed to follow Microsoft&\#x27;s recovery steps. The updates supplied offered no customer-side mitigation; one administrator reported that Teams remained the only functioning part of Microsoft 365 in their tenant.

**「Community reaction」** Commenters focused on duration and scale: one administrator called it the worst Microsoft 365 outage their organization had seen since adopting the suite in 2019, noting that Azure itself seemed fine and the problem was 365-specific, while another reported eight hours of email downtime across 15,000-plus employees. A separate commenter attributed the incident to company-wide underinvestment in favor of AI work — an opinion, not an established cause.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=AHC76Eas5-s">Microsoft 365 OUTAGE : Outlook DOWN for Thousands! - YouTube</a></li>

</ul>
</details>

**Tags**: `#microsoft-365`, `#cloud-outage`, `#service-reliability`, `#enterprise-it`, `#hacker-news`

---

<a id="item-tech-news-9"></a>
### [Reddit Audit Finds Meta TRIBE v2 Lacks Retinotopic and Tonotopic Maps](https://www.reddit.com/r/MachineLearning/comments/1xuillf/does_metas_brainresponse_model_tribe_v2_actually/) ⭐️ 7.0/10

A self-reported, non-peer-reviewed Reddit audit reports that Meta&\#x27;s TRIBE v2 fMRI prediction model did not reproduce classic retinotopic or tonotopic maps when tested with standard mapping stimuli. The poster says TRIBE v2 predicts fMRI from video, audio, and text, but its paper did not test these topographic maps and its methods spatially average video features before prediction. Running checkerboard wedges and rings, hemifield flicker, moving dots, and tone sweeps through the model, the poster found no retinotopic map \(d=0.05, n.s.\) and no tonotopic map \(ρ=-0.07, n.s., even with loudness controlled\), but sharp motion selectivity in MT+ \(d=4.31, 52x enrichment over chance\). An eccentricity effect looked null by default but became significant and &quot;correct&quot; under three stimulus-geometry controls, which the poster interprets as an image-statistics confound rather than a real positional code.

reddit · r/MachineLearning · /u/Own\_Tank1283 · Nov 12, 17:16

**「Background」** Meta FAIR&\#x27;s TRIBE v2 is a foundation model that predicts whole-brain fMRI responses to images, video, audio, and text; it was trained on 720 volunteers and reported 2-3x gains over prior methods \[tool-2-2\]\[tool-2-3\]. Retinotopy and tonotopy are standard fMRI tests for whether visual-field position and sound frequency are organized into cortical maps, giving a concrete way to check whether a brain-response model captures spatial structure rather than only stimulus-driven activity.

**「Impact」** For researchers and developers, the reported nulls mean TRIBE v2 should not be treated as a spatially resolved encoder without positive controls: a model can produce plausible motion maps while failing retinotopy and tonotopy. The eccentricity result further suggests that any position-like effect needs stimulus-geometry controls before being read as a topographic code.

<details><summary>References</summary>
<ul>
<li><a href="https://www.digitalapplied.com/blog/meta-tribe-v2-ai-brain-digital-twins-guide">Meta TRIBE v 2 : AI Brain Digital Twins Open-Sourced</a></li>
<li><a href="https://awesomeagents.ai/news/meta-tribe-v2-brain-prediction-ai/">Meta TRIBE v 2 Predicts Brain Activity From Any... | Awesome Agents</a></li>

</ul>
</details>

**Tags**: `#neuroscience`, `#fMRI`, `#model evaluation`, `#reproducibility`, `#Meta AI`

---

<a id="item-tech-news-10"></a>
### [US Commerce Department finalizing rule to block Chinese AI firms&\#x27; remote chip access](https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule) ⭐️ 7.0/10

The US Commerce Department is reportedly finalizing a rule that would bar Chinese AI companies from remotely using advanced AI chips through overseas data centers, with publication possible as early as this month. The measure would extend existing semiconductor export restrictions to seven countries, including Malaysia, Singapore, and Thailand, to close remote-access and chip-smuggling gaps. The department is consulting other government agencies before finalizing the rule. Nvidia has lobbied against closing the remote-access gap, arguing that US AI infrastructure needs to prevail globally.

telegram · zaihuapd · Nov 12, 03:42

**「Background」** US export controls on advanced AI chips have primarily restricted where chips are shipped, rather than whether Chinese firms can use them remotely through data centers in third countries. That distinction is the gap the pending Commerce Department rule is intended to close.

**「Compliance burden shifts to overseas data centers」** If the rule is finalized as reported, Chinese AI developers renting GPU capacity in Singapore, Malaysia, Thailand and the other covered Southeast Asian countries would lose that route to restricted chips, forcing them to relocate training and inference workloads or fall back to less advanced hardware. Data center and cloud operators in those countries would in turn face new obligations to verify what customers are running and who ultimately controls it, since the stated purpose is to close the remote-access and smuggling gap that currently runs through exactly those jurisdictions.

<details><summary>References</summary>
<ul>
<li><a href="https://aipolicydaily.org/archive/daily/2026-11-10/">Commerce chip probe went to DOJ | WH seeks chip remote access ...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#US Commerce Department`, `#data centers`, `#Nvidia`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China approves Eli Lilly&\#x27;s oral weight-loss drug, the country&\#x27;s first oral GLP-1 for obesity](https://www.reuters.com/business/healthcare-pharmaceuticals/china-approves-eli-lillys-weight-loss-pill-orforglipron-2026-11-12/) ⭐️ 8.0/10

China&\#x27;s National Medical Products Administration approved Eli Lilly&\#x27;s oral GLP-1 weight-loss drug orforglipron \(brand name Mu You Da\) on Nov 12 as a Class 1 new drug, for adults who are obese or overweight with at least one weight-related condition — the first oral GLP-1 approved for weight loss in the country. The once-daily pill has no food or water restrictions, but Lilly has not disclosed pricing or launch timing, and a separate type 2 diabetes indication is still under review.

telegram · zaihuapd · Nov 12, 10:09

**「Background」** GLP-1 obesity drugs mimic a gut hormone that reduces appetite; orforglipron is a once-daily pill, while the treatments it will compete with in China are once-weekly injections.

**「Impact」** The approval gives Eli Lilly an early advantage over Novo Nordisk in China’s weight-loss market and offers adults with obesity or overweight plus a related condition a once-daily oral option, though price and launch timing are undisclosed.

<details><summary>References</summary>
<ul>
<li><a href="https://pubmed.ncbi.nlm.nih.gov/37344954/">Orforglipron (LY3502970), a novel, oral non-peptide glucagon-like...</a></li>
<li><a href="https://www.reuters.com/business/healthcare-pharmaceuticals/china-approves-eli-lillys-weight-loss-pill-orforglipron-2026-11-12/">Eli Lilly becomes first drugmaker to have a GLP-1 weight-loss ...</a></li>
<li><a href="https://www.scmp.com/business/companies/article/3374229/eli-lilly-beats-novo-nordisk-china-approval-first-oral-glp-1-weight-loss-drug">Eli Lilly beats Novo Nordisk to China approval for first oral ...</a></li>

</ul>
</details>

**Tags**: `#GLP-1`, `#Eli Lilly`, `#China drug approval`, `#obesity treatment`, `#pharmaceutical competition`

---

<a id="item-finance-news-2"></a>
### [Fed says October 2027 meeting will not include a rate vote](https://www.cnbc.com/2026/11/12/in-policy-switch-fed-says-its-october-2027-meeting-will-not-see-a-vote-on-interest-rates.html) ⭐️ 7.0/10

The Federal Reserve said its October 26-27, 2027 meeting will not include an interest-rate vote and will instead be devoted to monetary-policy strategy, part of Chairman Kevin Warsh&\#x27;s push to reduce the central bank&\#x27;s market footprint. The 2027 calendar has seven voting meetings and moves the year&\#x27;s final meeting to November from December, following Warsh&\#x27;s plan for two nonvoting meetings in 2028.

rss · CNBC Finance · Nov 12, 19:05

**「Background」** Under standard practice, the rate-setting Federal Open Market Committee meets eight times a year, and each of those meetings ends with an interest-rate vote and a post-meeting statement from the central bank.

**「Who is affected」** Investors and businesses that treat each FOMC statement as a policy signal will get seven scheduled rate decisions in 2027 instead of the customary eight, and no post-meeting statement after the Oct. 26-27 session.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#FOMC`, `#interest rates`, `#central bank communication`

---