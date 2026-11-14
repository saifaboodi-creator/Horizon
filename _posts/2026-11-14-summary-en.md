---
layout: default
title: "Horizon Summary: 2026-11-14 (EN)"
date: 2026-11-14
lang: en
---

> From 41 items, 8 important content pieces were selected

---

**Technology News**
1. [TorchTitan report: 1T-parameter MoE at 1,300 tokens/s per GPU](#item-tech-news-1) ⭐️ 8.0/10
2. [FAA orders nationwide ground stop over reported telecom outage](#item-tech-news-2) ⭐️ 7.0/10
3. [Tim Peters, early Python contributor and Timsort author, dies at 74](#item-tech-news-3) ⭐️ 7.0/10
4. [DeepSeek reportedly opens app-level API, open-sources chat demo](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenAI launches ChatGPT Wallet for agent purchases in the US](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [Lutnick Faces Questions Over Nvidia Ties as Sons’ Firm Cuts Reported Stake](#item-finance-news-1) ⭐️ 8.0/10
2. [Chicago Fed&\#x27;s Goolsbee Says Fed Still Has &\#x27;Work to Do&\#x27; on Inflation](#item-finance-news-2) ⭐️ 8.0/10
3. [Moonshot AI restructures ahead of planned Hong Kong IPO](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [TorchTitan report: 1T-parameter MoE at 1,300 tokens/s per GPU](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

A Reddit experience report from the TorchTitan/PyTorch collaboration says a ~1T-parameter mixture-of-experts model trained on 384 GH200 GPUs at ~1,300 tokens/s per GPU, 14× its starting throughput. The reported setup was 384-way FSDP with node-local 4-way expert parallelism and no pipeline parallelism; gains included 4× from full activation checkpointing, Muon to reach 64k-token sequences, whole-expert FlexShard, GPU-side Newton-Schulz for host-offloaded optimizers \(42 s to ~2 s, +35%\), attention-cost bucketing \(+13%\), bf16 expert-gradient all-to-all in place of fp32 reduce-scatter, and FP8 expert all-gather with blockwise scales \(+18%\). The author also reports an allocator fix through FSDP2&\#x27;s private unshard\_async\_op flag—said to be moving toward a public API—that eliminated retries across all 384 ranks, cut peak reserved memory by 13.5 GiB, and added 21% throughput. These are experience-report claims, not peer-reviewed results; the +7% group-limited routing gain is explicitly flagged as possibly hurting training.

reddit · r/MachineLearning · /u/f14-bertolotti · Nov 13, 16:28

**「Background」** TorchTitan is an open-source, PyTorch-native distributed training system for large-scale models, so this post is an experience report on that stack rather than a new framework announcement. The target hardware is the GH200, which pairs a Hopper GPU with a Grace CPU; the reported optimizations use the fast Grace–Hopper link for offloading and InfiniBand for inter-node traffic. The workload is a mixture-of-experts model, where each token is routed to a subset of experts, adding expert all-to-all communication to FSDP’s parameter sharding and gathering.

**「Impact」** Teams training MoE models with TorchTitan and FSDP2 have concrete patterns to test—whole-expert FlexShard, bf16 expert-gradient all-to-all with fp32 local accumulation, and GPU-side Newton-Schulz for host-offloaded optimizers—but the allocator fix currently relies on FSDP2&\#x27;s private unshard\_async\_op flag, which the author says is being made public.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/pytorch/torchtitan">GitHub - pytorch / torchtitan : A PyTorch native platform for training...</a></li>
<li><a href="https://arxiv.org/pdf/2410.06511">TorchTitan : One-stop PyTorch native solution for production ready...</a></li>

</ul>
</details>

**Tags**: `#TorchTitan`, `#Mixture-of-Experts`, `#Distributed Training`, `#GH200`, `#PyTorch`

---

<a id="item-tech-news-2"></a>
### [FAA orders nationwide ground stop over reported telecom outage](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 7.0/10

The FAA issued a nationwide ground stop for departing flights on November 13, 2026, according to NBC News, with few technical details in the supplied item. Community-cited reporting pointed to an outage in an L3Harris Technologies telecommunications network that carries radio frequencies air-traffic controllers use to communicate with pilots; the item does not confirm that as the cause or establish whether radar feeds were affected. Commenters also cited a New York Times report that the ground stop had been lifted, while another cited a warning that the underlying outage could be extended; those reports are not independently verified in the supplied material.

hackernews · zulln · Nov 13, 21:05 · [Discussion](https://news.ycombinator.com/item?id=50489641)

**「Background」** A ground stop halts departures nationwide while officials decide whether flights can safely proceed; flights already airborne are handled separately. The system at issue is a telecommunications network operated by L3Harris that carries radio frequencies air-traffic controllers use to communicate with pilots, according to reporting cited in the supplied results, and it was not immediately clear whether radar feeds were also affected.

**「Operational impact」** For airlines and passengers, the order halted departures nationwide; CNBC reported that thousands of departing flights were disrupted before the FAA lifted the ground stop after about four hours.

**「Community Discussion」** Commenters criticized the sparse official information, with one reporting that LAX had no departures since about 10:30 AM PST and that JFK departures were almost all delayed. Another commenter raised the FAA&\#x27;s recently announced nationwide rollout of its SMART AI air-traffic tool as possible context, but the supplied material does not establish a link to the outage.

<details><summary>References</summary>
<ul>
<li><a href="https://www.yahoo.com/news/us/article/faa-issues-nationwide-ground-stop-on-all-departing-flights-citing-communication-issue-213136811.html">FAA issues nationwide ground stop on all departing flights, citing...</a></li>
<li><a href="https://www.theguardian.com/us-news/live/2026/nov/13/us-politics-latest-news-updates-democrats-republicans-donald-trump-van-hollen-chuck-schumer?page=with:block-6af789c78f080d8d1c27a4b6">US flight outage live updates: FAA grounds thousands... | The Guardian</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>

</ul>
</details>

**Tags**: `#FAA ground stop`, `#air traffic control`, `#telecommunications outage`, `#critical infrastructure`, `#system reliability`

---

<a id="item-tech-news-3"></a>
### [Tim Peters, early Python contributor and Timsort author, dies at 74](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

Python creator Guido van Rossum announced that Tim Peters, an early Python contributor, died at age 74. Peters was described as Python&\#x27;s second real user; he wrote the Timsort sorting algorithm and PEP 20, &quot;The Zen of Python,&quot; and served on the Python Software Foundation board for 13 years.

telegram · zaihuapd · Nov 13, 09:55

**「Background」** Timsort is a hybrid sorting algorithm that Peters created and that is closely associated with CPython, Python&\#x27;s original implementation. PEP 20, “The Zen of Python,” is an active informational PEP that collects aphorisms about Python&\#x27;s design—19 of which are written down—and Peters posted the principles to the Python mailing list in 1999, with the PEP record dated August 2004.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Tim_Peters_%28software_engineer%29">Tim Peters (software engineer) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Zen_of_Python">Zen of Python - Wikipedia</a></li>
<li><a href="https://peps.python.org/pep-0020/">PEP 20 – The Zen of Python | peps.python.org</a></li>

</ul>
</details>

**Tags**: `#Python`, `#Tim Peters`, `#Timsort`, `#PEP 20`, `#open source community`

---

<a id="item-tech-news-4"></a>
### [DeepSeek reportedly opens app-level API, open-sources chat demo](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

DeepSeek has reportedly opened a set of application-level capabilities through its existing API; enabling the relevant parameters gives developers deep-thinking search, file input, link reading, and voice conversation, with the server handling tool calls and context assembly. The post states that V4.1-Flash is supported across three interfaces, while Search, Fetch, OCR, ASR, and TTS can each be called separately. It also released an open-source chat front-end demo that can import prior conversations and be run locally against the API. No primary documentation, parameter names, pricing, rate limits, or independent confirmation were provided, so exact availability and compatibility remain unverified.

telegram · zaihuapd · Nov 13, 14:27

**「Background」** DeepSeek&\#x27;s API has been OpenAI/Anthropic-compatible, so developers can reach it by adjusting configuration in existing SDKs or compatible software. The V4.1-Flash model named in the update is a multimodal Mixture-of-Experts model with a 552B backbone and support for contexts of up to one million tokens, according to DeepInfra&\#x27;s model documentation. DeepSeek&\#x27;s own docs frame the change as exposing the capabilities behind the DeepSeek App — search, files, links, safety and voice — either by enabling built-in features with parameters or by calling standalone OCR, ASR and TTS APIs.

**「Deployment consideration」** Developers who self-host the open-sourced chat demo must supply their own API origin through \`createConfig\(\{ apiOrigin, devServer \}\)\`; the demo defaults to the \`deepseek-flash\` model and talks to Anthropic-compatible Messages and Files APIs rather than DeepSeek&\#x27;s own request format. Because Search, Fetch, OCR, ASR and TTS are exposed as separately callable endpoints, teams can also add individual capabilities to an existing application without routing everything through the full chat flow that performs server-side tool calling and context stitching.

<details><summary>References</summary>
<ul>
<li><a href="https://deepinfra.com/deepseek-ai/DeepSeek-V4.1-Flash/api">DeepSeek V4.1 Flash API - Documentation - DeepInfra</a></li>
<li><a href="https://api-docs.deepseek.com/">Your First API Call | DeepSeek API Docs</a></li>
<li><a href="https://api-docs.deepseek.com/news/news261113/">The full DeepSeek App experience, now via API</a></li>
<li><a href="https://github.com/deepseek-ai/chat-demo/tree/main">GitHub - deepseek-ai/chat-demo: Chat Demo · GitHub</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#API`, `#LLM apps`, `#multimodal`, `#open source`

---

<a id="item-tech-news-5"></a>
### [OpenAI launches ChatGPT Wallet for agent purchases in the US](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI introduced ChatGPT Wallet, which lets AI agents make purchases without the user&\#x27;s real card number: the wallet passes a payment token issued by the card network instead of the underlying card details. OpenAI built the feature with American Express, Mastercard and Visa. Every purchase requires the user to review the item and amount and confirm with Face ID or a fingerprint. It is available starting today to ChatGPT Pro subscribers aged 18 and over in the US, and requires a US-issued card.

telegram · zaihuapd · Nov 13, 15:43

**「What a network token changes」** ChatGPT Wallet relies on network tokenization: the card networks issue a substitute number tied to the user&\#x27;s real card, so the agent and the merchant handle the token rather than the underlying card details. Access is gated by conditions stated in the announcement — a ChatGPT Pro subscription, US residency, an age of 18 or over, and a US-issued card — so the wallet is not a general replacement for stored card credentials.

**「Impact」** Because each transaction needs an explicit biometric confirmation by the account holder, agents cannot complete purchases unattended in the background — a practical limit on automated checkout flows. Users outside the US, non-Pro accounts, and anyone without a US-issued card cannot use the wallet at launch.

**Tags**: `#OpenAI`, `#AI agents`, `#payments`, `#digital wallet`, `#tokenization`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Lutnick Faces Questions Over Nvidia Ties as Sons’ Firm Cuts Reported Stake](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

CNBC reported that Cantor Fitzgerald, led by Commerce Secretary Howard Lutnick’s sons, cut its reported Nvidia share count by 49% between September 2025 and March 2026 while continuing to arrange financing for Nvidia partners. The report comes as Lutnick faces scrutiny over resisting a crackdown on a company suspected of smuggling Nvidia chips to China and over a classified warning about Nvidia CEO Jensen Huang’s ties to a suspected Chinese spy; Huang resigned Thursday.

rss · CNBC Finance · Nov 13, 23:42

**「Background」** Nvidia CEO Jensen Huang resigned on Thursday amid scrutiny of his ties to a suspected Chinese spy, and Commerce Secretary Howard Lutnick — whose department controls export licenses for advanced AI chips — was reported by Axios to have resisted a crackdown on Megaspeed, a Singapore-based Nvidia customer suspected of diverting chips to China. Cantor Fitzgerald, the Wall Street firm Lutnick formerly ran and now led by his sons Brandon and Kyle, had reported Nvidia as one of its largest stock holdings.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bbc.com/news/articles/c67429m3vem3o">How a sex scandal at Nvidia is putting pressure on the White House</a></li>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html">Howard Lutnick ’s sons’ Nvidia ties amid Jensen Huang China spy ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#export controls`, `#conflicts of interest`, `#semiconductor industry`, `#US-China tech policy`

---

<a id="item-finance-news-2"></a>
### [Chicago Fed&\#x27;s Goolsbee Says Fed Still Has &\#x27;Work to Do&\#x27; on Inflation](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 8.0/10

Chicago Fed President Austan Goolsbee said the Federal Reserve &quot;has definitely got work to do&quot; to reestablish its inflation credibility, after the October producer price index rose 6.5% from a year earlier — the highest annual rate since November 2022 — on a 0.3% monthly gain.

rss · CNBC Finance · Nov 13, 14:22

**「Background」** The Fed targets 2% inflation, and Goolsbee said inflation has stayed above that level for almost six years and is currently moving the wrong way; futures markets tracked by CME FedWatch fully price a quarter-point rate increase at the Dec. 8-9 meeting, with a better-than-10% chance of a half-point move.

**「Impact」** If the December increase is delivered, households and businesses carrying variable-rate debt would face higher borrowing costs, and Goolsbee — who does not currently vote on the rate-setting committee — said the outcome depends on whether inflation is on a path back to 2%, which he doubts.

**Tags**: `#monetary policy`, `#inflation`, `#Federal Reserve`, `#PPI`, `#interest rates`

---

<a id="item-finance-news-3"></a>
### [Moonshot AI restructures ahead of planned Hong Kong IPO](https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb) ⭐️ 7.0/10

Chinese AI startup Moonshot AI is restructuring its corporate setup to pave the way for a Hong Kong initial public offering, according to people familiar with the matter cited by The Wall Street Journal. The reported plan retires its Cayman Islands holding company and moves shares held by early US-dollar investors into its main operating entity in mainland China; no valuation or listing timetable was disclosed.

telegram · zaihuapd · Nov 13, 11:29

**「Background」** Chinese startups commonly hold foreign-currency investment through an offshore company registered in the Cayman Islands, and Moonshot had already filed confidentially for a Hong Kong listing after a private fundraising that valued it at $50 billion, according to Bloomberg.

**「Who is affected」** Early USD investors in Moonshot AI would hold stakes in its mainland China operating entity instead of the Cayman holding company, changing the legal vehicle for their shares ahead of the planned Hong Kong listing.

<details><summary>References</summary>
<ul>
<li><a href="https://bifu.co/news/detail/moonshot-ai-s-50-billion-valuation-a-question-of-peers">Moonshot AI &#x27;s $50 Billion Valuation : A Question of Peers</a></li>
<li><a href="https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb">China’s Moonshot AI Restructures to Pave Way for IPO</a></li>

</ul>
</details>

**Tags**: `#Moonshot AI`, `#Hong Kong IPO`, `#corporate restructuring`, `#China AI`, `#startup financing`

---