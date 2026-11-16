---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 36 items, 11 important content pieces were selected

---

**Technology News**
1. [Meta FAIR/NYU: Encoder Pretraining Optional, Vision-Only Parameters Required](#item-tech-news-1) ⭐️ 8.0/10
2. [Meituan open-sources LongCat-2.5, a 1.6T agent model trained on Huawei Ascend](#item-tech-news-2) ⭐️ 8.0/10
3. [Old Bitly Links Reportedly Hijacked, Highlighting Shortener Dependency Risks](#item-tech-news-3) ⭐️ 7.0/10
4. [MacBook Pro OLED PWM flicker scrutinized by flicker-sensitive users](#item-tech-news-4) ⭐️ 7.0/10
5. [Protomaps makes self-hosted map tiles cheap and easy](#item-tech-news-5) ⭐️ 7.0/10
6. [Explainer Surveys Positional Embedding Implementations in Modern LLMs](#item-tech-news-6) ⭐️ 7.0/10
7. [Tool claims 5x faster pageable cudaMemcpy on B300](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [Lutnick Faces Conflict-of-Interest Questions as Sons&\#x27; Firm Cantor Cut Nvidia Stake](#item-finance-news-1) ⭐️ 7.0/10
2. [China e-bike certificate suspensions block vehicle registration in some cities](#item-finance-news-2) ⭐️ 7.0/10
3. [美光、三星、SK海力士DRAM价格操纵案获准继续审理](#item-finance-news-3) ⭐️ 7.0/10
4. [US, China, Russia Leaders to Hold First Trilateral Meeting at Shenzhen APEC](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Meta FAIR/NYU: Encoder Pretraining Optional, Vision-Only Parameters Required](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR and NYU trained more than 200 multimodal LLMs from scratch under matched data and lifetime compute—counting encoder pretraining against the same budget—to isolate three bundled design choices. They report that separate encoder pretraining is optional: four pretrained encoders at best tied a from-scratch encoder when the LLM was trained jointly, and even 6.5× longer MetaCLIP pretraining raised ImageNet linear-probe accuracy from 80.4% to 84.4% without improving VQA. Vision-only parameters were necessary: encoder-free models lagged at every backbone size from 0.6B to 6.4B and needed about 3× the compute to catch up, while giving those parameters to the LLM improved text but not VQA. Placing vision before the LLM was also optional: “in-fusion” vision-only branches in the first eight LLM layers matched an encoder from 1.7B to 6.4B, with about 13% lower time to first token; main comparisons used Qwen3-1.7B and 4B backbones with 0.4B vision parameters and 16 VQA plus 12 language benchmarks.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Why the vision encoder stack is contested」** A conventional multimodal LLM pairs a separately pretrained vision encoder \(contrastive models such as CLIP or MetaCLIP are common\) with an LLM that consumes its output tokens, bundling three decisions into one component: whether the encoder gets its own pretraining, whether it has parameters only vision tokens use, and whether it sits before the LLM. Released models have diverged on exactly these points, which is the disagreement the study targets: Google&\#x27;s Gemma 4 12B documentation describes an encoder-free design that projects raw image patches directly into the LLM embedding space through lightweight linear layers, while the source notes other recent models instead train an encoder from scratch or reintroduce one. Because those published models differ in training data and compute, and rarely count encoder pretraining against the same budget, their results cannot separate the three choices.

**「Impact」** For multimodal teams, the result argues against spending compute on a separate vision encoder pretraining stage when the same budget can go into joint training, but it does not support removing vision-specific capacity: encoder-free designs should expect roughly 3× the training compute at these scales. The in-fusion variant is the practical alternative to test when inference latency matters, since the authors measured a 13% lower time to first token at comparable VQA.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/google/gemma-4-12B">google/ gemma - 4 - 12 B · Hugging Face</a></li>
<li><a href="https://developers.googleblog.com/gemma-4-12b-the-developer-guide/">Gemma 4 12 B : The Developer Guide - Google Developers Blog</a></li>

</ul>
</details>

**Tags**: `#multimodal LLMs`, `#vision encoders`, `#model architecture`, `#pretraining`, `#research`

---

<a id="item-tech-news-2"></a>
### [Meituan open-sources LongCat-2.5, a 1.6T agent model trained on Huawei Ascend](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team published the weights of LongCat-2.5 a week after announcing the model, releasing them under the MIT license for commercial use. The agent-oriented model has 1.6 trillion total parameters with roughly 48 billion activated per token, and accepts text, image, and video input. Meituan says training ran entirely on Huawei Ascend accelerators with no Nvidia GPUs, a claim not independently verified here. The team reports a Terminal Bench v2.1 score of 88.4, just below Claude Opus 5&\#x27;s 89.1.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** LongCat-2.5&\#x27;s 1.6 trillion parameters represent total model capacity, while only about 48 billion are activated per token, so inference compute is closer to that of a much smaller model. Meituan says the full training run used Huawei Ascend accelerators rather than Nvidia GPUs, a notable departure for a model of this scale.

**「Impact」** The MIT license lets organizations modify and deploy the weights commercially without the usage restrictions that accompany many open-weight releases, though a 1.6T-parameter model still implies substantial serving infrastructure. The reported 88.4 Terminal Bench score, if it holds up, puts an openly licensed agent model within a point of Claude Opus 5 on the benchmark Meituan chose to highlight.

**Tags**: `#LLM`, `#open source`, `#AI agents`, `#Huawei Ascend`, `#model training`

---

<a id="item-tech-news-3"></a>
### [Old Bitly Links Reportedly Hijacked, Highlighting Shortener Dependency Risks](https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/) ⭐️ 7.0/10

A report says old Bitly links are being hijacked, with the source URL tying the incident to a Burger King tweet, but the supplied material does not specify the attack method, the number of affected links, or Bitly&\#x27;s response. The case centers on shortened links that outlive the account or service relationship that created them, leaving the original publisher unable to control where the link resolves. The report should be treated as a claim rather than an independently verified account of Bitly&\#x27;s security posture.

hackernews · hspeiser · Nov 15, 22:11 · [Discussion](https://news.ycombinator.com/item?id=50511395)

**「Background」** A shortened link is only an alias on a third-party domain \(bit.ly\) that resolves to whatever destination its holder sets, and an alias that expires or is released can later be registered by someone else. Reports on this incident describe expired Bitly endings in older posts being re-registered to point at new destinations, without any change to the posts themselves.

**「Practical Risk」** Publishers and readers who rely on old shortened links cannot assume a Bitly URL still points to its original destination; the practical safeguard is to replace shorteners with owned-domain redirects and treat unexplained redirects as untrusted.

**「Community Discussion」** Commenters largely argued that outsourced shorteners create durable, hard-to-fix breakage because accounts lapse or companies disappear; one anecdote described an unregistered Bitly link printed in a book being redirected by a reader. Another commenter was surprised that a URL shortener has a Trust and Safety team, highlighting that these services operate at a scale that invites abuse review.

<details><summary>References</summary>
<ul>
<li><a href="https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/">Old Bitly links hijacked in Burger King, McDonald’s and Trump ...</a></li>
<li><a href="https://nypost.com/2026/11/15/lifestyle/corporate-social-media-hacked-in-bizarre-bitly-link-hijacking-scheme/">Corporate social media hacked in bizarre Bitly link-hijacking ...</a></li>

</ul>
</details>

**Tags**: `#URL shorteners`, `#link hijacking`, `#web security`, `#link rot`, `#internet infrastructure`

---

<a id="item-tech-news-4"></a>
### [MacBook Pro OLED PWM flicker scrutinized by flicker-sensitive users](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

A technical blog post on MacAnorak examines pulse-width modulation \(PWM\) flicker in the MacBook Pro&\#x27;s OLED display and how it affects people who are sensitive to screen flicker — arguing that a technically superior panel can be worse to use for that group. The post drew substantive Hacker News discussion about how the flicker rate is actually measured: one commenter who re-checked the figures said the tandem OLED layers appear to PWM at 480 Hz, 180 degrees out of phase, yielding an effective 960 Hz at the brightness levels most people use, rather than the lower rate the testers reported. Another commenter cited a Nature paper \(srep07861\) reporting that humans can perceive flicker at more than double a display&\#x27;s nominal rate. No independently verified measurement of the shipping hardware is presented in the supplied material, so the exact frequency remains disputed.

hackernews · MacAnorak · Nov 15, 13:15 · [Discussion](https://news.ycombinator.com/item?id=50506719)

**「Context」** PWM dimming controls apparent brightness by switching display light on and off rapidly; a lower switching frequency can be more noticeable or uncomfortable for flicker-sensitive users. Apple&\#x27;s tandem-OLED MacBook Pro, marketed as the PROLED XDR Display, replaces the mini-LED panel used since 2021, and Notebookcheck&\#x27;s review reported about 240 Hz PWM on the OLED model versus roughly 14,880 Hz on the mini-LED version.

**「Impact」** For flicker-sensitive buyers, the practical consequence is that the display&\#x27;s comfort depends on brightness and on a flicker frequency that is still being argued over, so an in-person trial — including at the low brightness levels used in dim rooms — is the only reliable check before purchasing. The measurement disagreement also means the blog post&\#x27;s figures should not be treated as a settled specification.

**「Community Discussion」** Commenters split between disputing the measurement and broadening the frame: legitronics argued from scope traces that the tandem OLED&\#x27;s out-of-phase layers double the effective rate, while achr2 was surprised Apple shipped a panel with such a low PWM frequency and cited research on flicker perception above the refresh rate. Others, including Velocifyer and explosion-s, reported that sensitivity extends well beyond PWM — to LED color rendering, LCD motion blur, and post-concussion screen intolerance generally — and Telaneo called for research into how many people are actually affected.

<details><summary>References</summary>
<ul>
<li><a href="https://www.notebookcheck.net/Amazing-OLED-panel-Apple-MacBook-Pro-14-PROLED-XDR-Review.1438048.0.html">Amazing OLED panel - Apple MacBook Pro ... - Notebookcheck Review</a></li>
<li><a href="https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/">The MacBook Pro ’s OLED PWM Problem: When a ‘Better’ Display...</a></li>
<li><a href="https://www.youtube.com/watch?v=sGgowKoztzk">Is the PROLED ( OLED ) MacBook Pro a Disaster? Flicker ... - YouTube</a></li>

</ul>
</details>

**Tags**: `#OLED`, `#PWM flicker`, `#MacBook Pro`, `#display technology`, `#hardware ergonomics`

---

<a id="item-tech-news-5"></a>
### [Protomaps makes self-hosted map tiles cheap and easy](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

A blog post argues that self-hosting map tiles with Protomaps and its PMTiles format has become inexpensive and straightforward enough for side projects and production use. The post presents this as a practical alternative to hosted mapping services, but the available material does not include specific cost figures, benchmarks, versions, or deployment requirements.

hackernews · bcye · Nov 15, 19:26 · [Discussion](https://news.ycombinator.com/item?id=50509837)

**「Background」** Protomaps&\#x27; PMTiles format packs a pyramid of map tiles into a single archive that can be hosted on commodity object storage such as S3. Because clients retrieve the needed portions through HTTP range requests, the map can be served without a custom tile backend or a third-party tile provider.

**「Deployment trade-off」** Teams serving standard vector basemaps can deploy a single PMTiles archive to object storage or a CDN and avoid running an intermediate tile server, which Protomaps describes as serving a map from one static file. The constraint is storage scale: community reports in the thread note that high-resolution satellite mosaics become expensive at high zoom levels, with one developer stopping at z17.

**「Community discussion」** Commenters point to OpenFreeMap as a similar free option and describe serving PMTiles from Cloudflare R2 to keep control over privacy and access. One developer warns that high-resolution satellite imagery scales to hundreds of terabytes at high zoom levels, making it far more expensive to store and serve than ordinary basemaps.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps/PMTiles: Pyramids of map tiles in a single ...</a></li>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>
<li><a href="https://docs.protomaps.com/pmtiles/">PMTiles Concepts | Protomaps Docs</a></li>
<li><a href="https://protomaps.com/about">Protomaps - The open source map in a file</a></li>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>

</ul>
</details>

**Tags**: `#protomaps`, `#map-tiles`, `#self-hosting`, `#open-source`, `#geospatial`

---

<a id="item-tech-news-6"></a>
### [Explainer Surveys Positional Embedding Implementations in Modern LLMs](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

A technical explainer examines how positional embeddings are implemented in modern large language models. The supplied material does not include specific model versions, benchmark results, or code-level findings, so the article functions as conceptual background rather than a report of a new capability or measured result.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Background」** The article surveys how LLMs encode token position information, covering classic schemes and contemporary methods such as rotary position embeddings \(RoPE\), which encode absolute positions through block-diagonal rotations to support relative attention. It also examines how modern architectures adapt or omit explicit positional embeddings.

**「Community Discussion」** Commenter programjames argues that the article addresses only implementation and that a fuller understanding requires group theory, framing positional embeddings as group representations. The comment specifically describes rotary positional embeddings as representations of the translation group ℝⁿ, whose abelian structure determines its irreducible representations.

<details><summary>References</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://www.emergentmind.com/topics/rotary-position-embeddings">Rotary Position Embeddings - emergentmind.com</a></li>

</ul>
</details>

**Tags**: `#positional embeddings`, `#LLMs`, `#transformer architecture`, `#machine learning`, `#technical deep-dive`

---

<a id="item-tech-news-7"></a>
### [Tool claims 5x faster pageable cudaMemcpy on B300](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 7.0/10

A Reddit author \(/u/makneeee\) released cudamemcpy-tuner, a tool that tunes pageable CUDA memory transfers, with code on GitHub and an accompanying blog post. The reported benchmark copies a 1 GB uint8 PyTorch tensor to the GPU five times and measures throughput: 10.2 GB/s normally versus 51.5 GB/s when the same script is launched through \`cmt tune -- python bench.py\`, a roughly 5x improvement on an Nvidia B300. The post presents this as a single author-reported measurement rather than an independently verified result, and it gives no details on which tuning parameters the tool changes, which CUDA or driver versions it supports, or how it behaves on other GPUs or transfer sizes.

reddit · r/MachineLearning · /u/makneeee · Nov 15, 18:20

**「Why pageable copies are slow」** CUDA&\#x27;s \`cudaMemcpy\` behaves differently depending on whether the host buffer is pageable or pinned. NVIDIA&\#x27;s own guidance notes that higher host-to-device bandwidth is possible with page-locked \(&quot;pinned&quot;\) memory, because pageable memory cannot be transferred directly by DMA and must first be staged through a driver-managed pinned buffer. That staging path is the one the reported tool targets, which is why its benchmark compares plain \`torch\` pageable copies against the same script run under \`cmt tune\`.

**「Impact」** Developers whose workloads use pageable \(non-pinned\) host-to-device copies have a potential option to test without changing their code, since the tool wraps the existing Python script through the \`cmt tune\` command. Because the only evidence is one benchmark on one B300 system, users should re-run their own transfer benchmarks before relying on the speedup, and should confirm the tool&\#x27;s configuration persists into production runs rather than only the tuning invocation.

<details><summary>References</summary>
<ul>
<li><a href="https://developer.nvidia.com/blog/how-optimize-data-transfers-cuda-cc/">How to Optimize Data Transfers in CUDA C/C++ | NVIDIA ...</a></li>

</ul>
</details>

**Tags**: `#CUDA`, `#GPU memory transfer`, `#performance optimization`, `#developer tools`, `#benchmarking`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Lutnick Faces Conflict-of-Interest Questions as Sons&\#x27; Firm Cantor Cut Nvidia Stake](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reported that Commerce Secretary Howard Lutnick faces conflict-of-interest questions over Nvidia export-control decisions while Cantor Fitzgerald, the Wall Street firm led by his sons, reported cutting its Nvidia stake by 49% between September 2025 and March 2026, to 1.78 million shares valued at $310 million from $652 million. Cantor kept a $350 price target and an overweight rating on Nvidia, and CNBC said there is no evidence of wrongdoing or that the holding changes were tied to intelligence warnings about Nvidia CEO Jensen Huang.

rss · CNBC Finance · Nov 15, 19:58

**「Background」** Howard Lutnick formerly ran Cantor Fitzgerald before leaving in February 2025 to become commerce secretary; his sons Brandon and Kyle now lead the firm. The Commerce Department administers U.S. export controls, including the entity list that restricts sales to named companies, giving the secretary a role in decisions affecting Nvidia.

**「Impact」** Chipmakers and their cloud customers face the prospect of wider export limits: Trump authorized new restrictions on companies suspected of smuggling Nvidia chips on Nov. 5, and Nvidia&\#x27;s own big customers Amazon and Microsoft back legislation that would further curb such China exports.

<details><summary>References</summary>
<ul>
<li><a href="https://www.atlanticcouncil.org/dispatches/beyond-the-spy-scandal-what-the-nvidia-megaspeed-case-reveals-about-export-controls/">Beyond the spy scandal: What the Nvidia-Megaspeed case ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#export controls`, `#conflicts of interest`, `#Commerce Department`, `#AI chips`, `#ethics`

---

<a id="item-finance-news-2"></a>
### [China e-bike certificate suspensions block vehicle registration in some cities](https://www.peopleapp.com/column/30053564254-500007786629) ⭐️ 7.0/10

Consumers in Guangzhou, Wuhan and other Chinese cities say they cannot register newly bought electric bicycles after China Compulsory Certification \(3C\) certificates were suspended for brands including Ninebot, Yadea and Aima, according to a People&\#x27;s Daily report. The suspensions followed inspections of 201 companies and come as stricter post-certification rules took effect Nov. 1; the brands gave no timetable for restoration.

telegram · zaihuapd · Nov 15, 06:08

**「Background」** 3C \(China Compulsory Certification\) is the mandatory safety mark these vehicles need to be sold and registered; the suspensions began in late September, before the new Nov. 1 rules, after the State Administration for Market Regulation inspected 201 e-bike companies nationwide and found problems such as swapped key components and design space left for removing speed limits, on which certification bodies then stopped certificates.

**「Impact」** Buyers of the affected models are left with e-bikes they cannot legally register, and some stores are refusing refunds by saying the vehicle has already been activated, according to the report.

<details><summary>References</summary>
<ul>
<li><a href="https://t.me/zaihuapd/45136">在花 科技圈 – Telegram</a></li>
<li><a href="https://www.ithome.com/1/027/275.htm">部分 电 动 自 行 车 3 C 认 证 卡壳，消费者购 车 后 上 牌 遇阻 - IT之家</a></li>

</ul>
</details>

**Tags**: `#electric bicycles`, `#3C certification`, `#regulatory compliance`, `#consumer protection`, `#China`

---

<a id="item-finance-news-3"></a>
### [美光、三星、SK海力士DRAM价格操纵案获准继续审理](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

美国法官Noël Wise驳回了美光、三星和SK海力士撤销DRAM价格操纵集体诉讼的动议，认定原告提出的新证据使三家厂商同步减少供应的串通指控具有合理性，案件因此可以继续审理。原告是17名个人和小企业，他们指控这三家厂商在一年内四次采取平行行动限制DRAM供应，并推动价格最高上涨500%；这些数字目前仅为原告的指控，尚未经法院认定。

telegram · zaihuapd · Nov 15, 16:39

**「Background」** A motion to dismiss asks the court to end a case before trial; denying it keeps the proposed class action alive but does not decide whether the price-fixing allegations are true.

**「影响」** 该裁定使针对全球三大DRAM供应商的集体诉讼得以继续；如果诉讼推进，购买内存芯片或含内存产品的消费者和企业可能受到影响，但目前尚无任何责任或赔偿认定。

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/articles/judge-denies-motion-dismiss-dram-152445837.html?fr=sycsrp_catchall">Judge denies motion to dismiss DRAM price-fixing lawsuit ...</a></li>
<li><a href="https://xenospectrum.com/en/dram-lawsuit-hbm-supply-constraints/">Court Lets DRAM Price-Fixing Suit Against Samsung, SK hynix ...</a></li>

</ul>
</details>

**Tags**: `#DRAM`, `#antitrust litigation`, `#Micron`, `#Samsung`, `#SK Hynix`

---

<a id="item-finance-news-4"></a>
### [US, China, Russia Leaders to Hold First Trilateral Meeting at Shenzhen APEC](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 7.0/10

China’s foreign ministry said the US, Chinese and Russian leaders will hold a trilateral meeting on Nov. 19 on the sidelines of the APEC summit in Shenzhen. Media described it as their first dedicated three-way meeting, and it is not part of APEC’s official agenda.

telegram · zaihuapd · Nov 16, 01:38

**「Background」** APEC is an annual forum of Asia-Pacific economies; China is hosting the 2026 leaders&\#x27; meeting in Shenzhen on November 18–19, and the three-way meeting is a separate event on the sidelines rather than part of its official agenda. The White House had earlier confirmed the first-ever trilateral sit-down, US outlets reported.

<details><summary>References</summary>
<ul>
<li><a href="https://www.shenzhendecoded.com/en/guides/apec-2026-shenzhen">APEC Summit 2026 in Shenzhen : Plan Around November 18-19</a></li>
<li><a href="https://www.nybusinesstimes.com/hollyland-named-official-sponsor-of-apec-2026-shenzhen-meetings/">Hollyland Named Official Sponsor of APEC 2026 Shenzhen Meetings</a></li>
<li><a href="https://www.cnn.com/2026/11/13/politics/trump-putin-xi-meeting">Trump to meet with China’s Xi and Russia’s Putin at historic ...</a></li>

</ul>
</details>

**Tags**: `#US-China-Russia relations`, `#APEC`, `#summit diplomacy`, `#geopolitics`, `#policy risk`

---