---
layout: default
title: "Horizon Summary: 2026-11-12 (EN)"
date: 2026-11-12
lang: en
---

> From 39 items, 12 important content pieces were selected

---

**Technology News**
1. [Hacker News post claims Nvidia CEO Jensen Huang has resigned](#item-tech-news-1) ⭐️ 9.0/10
2. [Critical mod\_http2 RCE in Apache HTTP Server](#item-tech-news-2) ⭐️ 8.0/10
3. [AWS releases official Rust local emulator for its services](#item-tech-news-3) ⭐️ 8.0/10
4. [UMAP 0.6 adds faster initialization and optimizers, opt-in layout changes](#item-tech-news-4) ⭐️ 8.0/10
5. [Google&\#x27;s Gemini Decisions API adds multimodal probability scoring](#item-tech-news-5) ⭐️ 7.0/10
6. [Essay Examines Why Correct Software Is Hard](#item-tech-news-6) ⭐️ 7.0/10
7. [Anthropic IPO Draws Hacker News Debate on Timing, Valuation, and Moat](#item-tech-news-7) ⭐️ 7.0/10
8. [Audit questions TRIBE v2&\#x27;s topographic maps, finds motion selectivity in MT+](#item-tech-news-8) ⭐️ 7.0/10
9. [Apple details Secure Exclaves and recording-indicator checks](#item-tech-news-9) ⭐️ 7.0/10

**Technology Blog**
1. [Serving MiniMax H3-Image at 4K on Vera Rubin](#item-tech-blog-1) ⭐️ 8.0/10

**Financial News**
1. [U.S. Commerce Department Finalizing Rule to Block Chinese AI Firms&\#x27; Remote Chip Access](#item-finance-news-1) ⭐️ 8.0/10
2. [礼来口服减重药获批，成为中国首款口服GLP-1减重药](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Hacker News post claims Nvidia CEO Jensen Huang has resigned](https://apnews.com/article/nvidia-megaspeed-china-singapore-huang-5403f152a601cf82ce939f1d24fffa0f) ⭐️ 9.0/10

A Hacker News submission asserts that Nvidia CEO Jensen Huang has resigned and links to AP, Reuters, NYT and Nvidia coverage, but the supplied item contains no article text, so the departure&\#x27;s terms, timing, and stated reason remain unverified. The submission is tagged with export controls, succession, and market impact, indicating the issues the coverage and discussion center on. Neither Nvidia nor the linked outlets&\#x27; reporting is available in the supplied material to confirm the claim.

hackernews · lldb · Nov 12, 13:52 · [Discussion](https://news.ycombinator.com/item?id=50467087)

**「Background」** On Nov. 12, 2026, Nvidia’s board announced that Jensen Huang had resigned as president, CEO and a board member, naming CFO Colette Kress interim CEO and appointing Harvey C. Jones as the board’s first chair. The Guardian and Forbes reported that the resignation followed disclosures of extramarital affairs, including with an alleged Chinese spy and a company employee; Nvidia’s announcement did not state a reason.

**「Market and Succession Fallout」** Nvidia shares fell more than 7% on Thursday following confirmation of Huang&\#x27;s resignation as president, CEO and board member, according to TheWrap&\#x27;s reporting — a direct hit to holders and to index-tracking funds with heavy Nvidia weight. Because Huang has been the public face of Nvidia&\#x27;s product roadmap and its posture toward export controls, customers and developers planning around Nvidia hardware have no named successor to hold to those commitments until the board announces interim leadership.

**「Community Discussion」** Commenters dispute the cause: one argues the affair is not the reason and that Nvidia may have skirted export bans, while another calls Huang &quot;compromised&quot; and says he should not be retained for shareholders&\#x27; sake. Others compare the response to how Elon Musk and Mark Zuckerberg have been treated, questioning whether the standards are consistent; these are opinions, not established facts.

<details><summary>References</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-CEO-Transition/default.aspx">NVIDIA Corporation - NVIDIA Announces CEO Transition</a></li>
<li><a href="https://www.forbes.com/sites/alexanderpuutio/2026/11/12/nvidia-ceo-jensen-huang-resigns-his-success-and-actions-left-no-choice/">Nvidia CEO Jensen Huang Resigns. His Success And ... - Forbes</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/12/nvidia-ceo-jensen-huang-resigns">Jensen Huang resigns as Nvidia CEO after alleged affairs</a></li>
<li><a href="https://www.investopedia.com/nvidia-ceo-jensen-huang-resigns-and-the-stock-plunges-nvda-12249556">Nvidia CEO Jensen Huang Resigns—and the Stock Plunges</a></li>
<li><a href="https://www.thewrap.com/industry-news/business/nvidia-ceo-jensen-huang-resignation-stock-reaction/">Nvidia Stock Plunges Over 7% as CEO Jensen Huang ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Jensen Huang`, `#executive resignation`, `#export controls`, `#AI hardware`

---

<a id="item-tech-news-2"></a>
### [Critical mod\_http2 RCE in Apache HTTP Server](https://www.wiz.io/blog/cve-2026-119618-rce-apache-http-server-vulnerability) ⭐️ 8.0/10

A Wiz blog post reports CVE-2026-119618, a critical remote code execution vulnerability in Apache HTTP Server&\#x27;s mod\_http2, and points to an httpd patch commit. Hacker News commenters said the affected mod\_http2 range is 2.0.8 through 2.0.42 and that the first fixed version is 2.0.43, flagging an apparent &quot;2.0.24 and newer&quot; typo in the version listing; another commenter noted HTTP/2 is not enabled by default, so exposure depends on server configuration. The supplied material does not confirm exploitation in the wild, a CVSS score, or which httpd releases bundle the vulnerable module.

hackernews · soheilpro · Nov 12, 02:11 · [Discussion](https://news.ycombinator.com/item?id=50462177)

**「Background」** \`mod\_http2\` is the optional Apache HTTP Server module that provides HTTP/2 support, so the vulnerable code is in that module rather than the core server alone. The published affected ranges are Apache HTTP Server 2.4.55 through 2.4.70 and stand-alone \`mod\_h2\` 2.0.8 through 2.0.42; Red Hat notes that \`mod\_h2\` versions before 2.0.8 do not contain the affected code.

**「Upgrade path and mitigation caveat」** Sites running an affected httpd build need to move to Apache HTTP Server 2.4.71 or later, the release that fixes the race condition in assign\_headers\(\), rather than relying on configuration changes alone. Administrators who instead take the interim step of stopping HTTP/2 or shutting the service down should confirm it stays down: one commenter noted that a certbot cron job or systemd timer can restart httpd and leave it running despite a \`systemctl disable --now\` command.

**「Community discussion」** Commenters focused on exposure and mitigation: one said HTTP/2 is not enabled by default in Apache, while another warned that disabling httpd may not keep it off because a certbot cron job or systemd timer can restart it. A third commenter said Apache is rarely encountered in modern Linux administration, an anecdote that does not establish deployment levels.

<details><summary>References</summary>
<ul>
<li><a href="https://www.wiz.io/blog/cve-2026-119618-rce-apache-http-server-vulnerability">Critical RCE Vulnerability in Apache HTTP Server ... | Wiz Blog</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-119618">CVE - 2026 - 119618 - Red Hat Customer Portal</a></li>
<li><a href="https://security-tracker.debian.org/tracker/CVE-2026-119618">CVE - 2026 - 119618</a></li>
<li><a href="https://www.wiz.io/blog/cve-2026-119618-rce-apache-http-server-vulnerability">Critical RCE Vulnerability in Apache HTTP Server ... | Wiz Blog</a></li>

</ul>
</details>

**Tags**: `#Apache HTTP Server`, `#RCE vulnerability`, `#CVE`, `#mod\_http2`, `#open source security`

---

<a id="item-tech-news-3"></a>
### [AWS releases official Rust local emulator for its services](https://simonwillison.net/2026/Nov/11/aws-emulator/) ⭐️ 8.0/10

AWS has published aws-emulator on GitHub, an official local emulator that lets developers run tests against local clones of its services without provisioning a paid API key. Simon Willison notes the tool is written in Rust and was produced by &quot;a huge swarm of agents,&quot; with 29,684 commits in the project&\#x27;s first three weeks; he points to a guest post by Swaminathan \(Swami\) Sivasubramanian on Werner Vogels&\#x27; blog describing how it came about. On macOS and Windows the emulator currently requires Docker to run. The post does not detail which services are covered or how closely emulated behavior matches the real ones.

rss · Simon Willison · Nov 11, 21:18

**「Background」** Tests point the AWS CLI or an AWS SDK at the emulator by setting environment variables, so existing commands and SDK code run against local services instead of live cloud resources. AWS describes the emulator as free and open source, covering nearly every AWS service and measuring fidelity against real AWS behavior. On macOS and Windows it currently runs in Docker using the provided Dockerfile, while Rust tests using the AWS SDK for Rust can run the emulator inside the test process.

**「Impact」** Developers can point AWS-dependent test suites at a local endpoint instead of provisioning live resources or holding paid credentials, which was previously addressed mainly by third-party projects. The Docker dependency on macOS and Windows means a single downloadable binary usable in cross-platform test suites is not yet available, a limitation Willison hopes AWS will remove.

<details><summary>References</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/aws/test-your-applications-against-aws-locally-with-aws-emulator/">Test your applications against AWS locally with AWS Emulator</a></li>
<li><a href="https://docs.aws.amazon.com/emulator/latest/userguide/what-is-service.html">What is AWS Emulator?</a></li>
<li><a href="https://docs.aws.amazon.com/emulator/">AWS Emulator Documentation</a></li>

</ul>
</details>

**Tags**: `#aws`, `#local-testing`, `#rust`, `#ai-agents`, `#developer-tools`

---

<a id="item-tech-news-4"></a>
### [UMAP 0.6 adds faster initialization and optimizers, opt-in layout changes](https://www.reddit.com/r/MachineLearning/comments/1xudaah/umap_06_new_initialization_new_optimizers_and/) ⭐️ 8.0/10

UMAP 0.6 is out with a new recursive initialization, new optimizers, and a nearest-neighbor search that the author says is about 4x faster through better use of PyNNDescent. On 3 million arXiv papers, a seeded 0.6 run finishes in under 5 minutes using all cores, while the author reports a seeded 0.5 run takes 52 minutes single-threaded. The author also claims finer cluster detail, better kNN recall, and reproducible multithreaded runs with a fixed seed. The new initialization and optimizers are opt-in because they change the output: set compatibility\_layout=False to use them; future versions are planned to make them the default.

reddit · r/MachineLearning · /u/lmcinnes · Nov 12, 13:51

**「Background」** UMAP is a dimensionality-reduction technique that constructs a nearest-neighbour graph and then optimizes a low-dimensional embedding intended to preserve that graph&\#x27;s structure. Its result depends heavily on the starting layout and on the optimizer used to refine it; the source describes spectral initialization and PCA as older starting methods that produced blurrier layouts.

**「Impact」** Users who enable compatibility\_layout=False should expect different embeddings and should re-check downstream analyses or visualizations, while existing code that does not set the flag keeps the older layout behavior.

**Tags**: `#UMAP`, `#dimensionality reduction`, `#machine learning`, `#open source`, `#performance`

---

<a id="item-tech-news-5"></a>
### [Google&\#x27;s Gemini Decisions API adds multimodal probability scoring](https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/) ⭐️ 7.0/10

Google has released the Gemini Decisions API, built on Gemini Decision 1, for closed-ended yes/no, choice, and rubric-scoring questions that return probabilities. The model accepts text, images, audio, video, and PDFs, whereas Jev is text/JSON-only and OpenAI&\#x27;s decision model handles text and images. The API is priced at $0.10 per million input tokens with free output, matching GPT-6 Luna but above Jev&\#x27;s $0.042 per million; Google lists it in AI Studio with up to 1,000 questions per request and about 150–250 ms end-to-end latency. In a video test, it returned a probability of 0.923 for “robot” rather than a binary 1.0.

hackernews · iamdelirium · Nov 11, 18:32 · [Discussion](https://news.ycombinator.com/item?id=50456791)

**「Background」** Gemini Decision 1 is not the first decision-model API: Jev and OpenAI already offered endpoints that return a probability or selection for a predefined question rather than open-ended text. Jev&\#x27;s API documentation describes three typed question forms—Noul for yes/no, Choice for picking among defined options, and Score for an ordered rubric—and returns calibrated probabilities for them. Gemini adopts the same categories and the Noul term, while extending input beyond Jev&\#x27;s text- and JSON-only support.

**「Impact」** Developers using it for tool selection, policy checks, or model routing can pass PDFs and media directly and receive graded probabilities, but they must define cutoffs because outputs are continuous rather than 0/1; text-only workloads remain cheaper on Jev at $0.042 per million input tokens.

**「Community discussion」** Commenters called the audio, video, and PDF support the notable differentiator, with one arguing Google under-marketed it, while noting that Jev remains faster and cheaper for common text tasks. Others questioned how the probabilities are calculated, citing prior criticism of LLM confidence scores, and one said the API is pricier than rivals but potentially worth it for audio and video.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/typesafe/jev-1.13">Jev 1.13 - API Pricing &amp; Providers | OpenRouter</a></li>

</ul>
</details>

**Tags**: `#Gemini API`, `#decision models`, `#multimodal AI`, `#Google AI`, `#developer tools`

---

<a id="item-tech-news-6"></a>
### [Essay Examines Why Correct Software Is Hard](https://pron.github.io/posts/correctness-and-complexity) ⭐️ 7.0/10

AriFordsham&\#x27;s essay &quot;Why Writing Correct Software Is Hard&quot; examines why software correctness is fundamentally difficult. The accompanying Hacker News discussion focuses on formal verification versus real-world reliability, the validity of specifications, and Rice&\#x27;s theorem. The item is a conceptual essay, not a product release, measured result, or vendor claim.

hackernews · AriFordsham · Nov 12, 10:28 · [Discussion](https://news.ycombinator.com/item?id=50465352)

**「Background」** The essay enters a long-running computer-science argument over whether a program can be proved to satisfy its specification. That argument rests on a distinction between two very different tasks: proving a particular property of one specific program, which is often feasible by hand or with a proof assistant, and constructing a general algorithm that decides such questions for every program, which Rice&\#x27;s theorem — building on the undecidability of the halting problem — rules out for any non-trivial semantic property.

**「Community Discussion」** Commenters disagreed about whether formal correctness is the right target. hinkley likened software to contract law and argued that acceptable inputs, outputs, and intermediate states cannot all be pinned down at once; turbobutton distinguished abstract mathematical correctness from real-world reliability, mpweiher asked how a specification&\#x27;s own correctness is established, and johnbender argued the essay misreads Rice&\#x27;s theorem.

**Tags**: `#software correctness`, `#formal verification`, `#complexity theory`, `#Rice&\#x27;s theorem`, `#software engineering`

---

<a id="item-tech-news-7"></a>
### [Anthropic IPO Draws Hacker News Debate on Timing, Valuation, and Moat](https://ipo.anthropic.com/us/) ⭐️ 7.0/10

A Hacker News submission titled &quot;Anthropic IPO&quot; points to an Anthropic-hosted page at ipo.anthropic.com/us/, indicating the company is moving toward a public listing; the submission itself carried no article text, so deal terms reach readers secondhand. A commenter summarizing the linked documents lists a $70–$78 price range \(midpoint around $74\), an $85.3B gross deal including a $26B private placement, a ~$968B implied market cap at $74 on 13.09B shares, Q3 2026 revenue of $17.0B \(+1,127% year over year\), a run-rate of roughly $81B as of October 2026, and $900.9B in compute commitments through 2045, under the ticker ANT on Nasdaq. Those figures reflect one commenter&\#x27;s reading of the filings and were not independently verified in the material supplied. Anthropic&\#x27;s own confirmation of timing and final terms is not present in the source.

hackernews · josephljohnston · Nov 12, 11:46 · [Discussion](https://news.ycombinator.com/item?id=50465829)

**「Background」** Anthropic’s IPO filing follows a period in which its growth has been paired with unusually large, long-dated compute obligations. CNBC’s coverage centered on whether Anthropic can grow revenue fast enough to cover mounting infrastructure costs, while another report described roughly $450 billion in mostly noncancelable cloud-computing agreements over seven to ten years.

**「Impact」** If the commenter&\#x27;s reading of the documents holds, Anthropic would enter public markets with roughly $900.9B of compute commitments running to 2045 against a ~$81B annualized revenue run-rate — a fixed cost base and revenue trajectory that public quarterly reporting would expose to outside scrutiny rather than to private investors alone.

**「Community Discussion」** Commenter maerF0x0 questioned the timing, arguing that if Anthropic&\#x27;s models were close to recursive self-improvement, backers would have pushed to delay the listing instead of accepting dilution now rather than raising more private rounds. Another commenter, brainless, argued that model choice is easy to switch and most applications do not need frontier models, so Anthropic and OpenAI will have to become end-user application companies — an opinion about strategy, not a disclosed fact.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/11/anthropic-ipo-profit-computing-commitments.html">Anthropic IPO : $900 billion in computing commitments</a></li>
<li><a href="https://www.linkedin.com/news/story/anthropic-draft-ipo-filing-reveals-huge-compute-commitments-7700268/">Anthropic draft IPO filing reveals huge compute commitments</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#IPO`, `#AI industry`, `#business strategy`

---

<a id="item-tech-news-8"></a>
### [Audit questions TRIBE v2&\#x27;s topographic maps, finds motion selectivity in MT+](https://www.reddit.com/r/MachineLearning/comments/1xuillf/does_metas_brainresponse_model_tribe_v2_actually/) ⭐️ 7.0/10

A self-reported independent audit of Meta&\#x27;s TRIBE v2 fMRI-prediction model found no significant retinotopic map \(d=0.05\) or tonotopic map \(ρ=-0.07\), but strong motion selectivity in MT+ \(d=4.31, 52× enrichment over chance\). The Reddit author says the model&\#x27;s paper never tested these classic topographic maps and that its methods spatially average video features before prediction, which would be expected to remove position information. An apparent eccentricity effect turned significant and &quot;correct&quot; under three stimulus-geometry controls, which the author interprets as an image-statistics confound rather than a genuine positional code. The findings are preliminary: a single unverified post with linked code and paper, not peer-reviewed.

reddit · r/MachineLearning · /u/Own\_Tank1283 · Nov 12, 17:16

**「Background」** TRIBE v2 is Meta&\#x27;s open-weight brain-encoding model, trained on more than 500 hours of fMRI from over 700 people to predict neural responses to video, audio, and text. Standard retinotopic mapping uses spatially modulated stimuli such as checkerboard wedges and rings to estimate population receptive fields and map visual-field organization, while analogous tonotopic and motion-localizer scans test frequency and MT+ selectivity. Those assays are a standard way to check whether a model captures topographic organization rather than only overall response magnitude.

**「Impact」** For groups using TRIBE v2 to infer spatial or topographic organization, the audit argues that predicted position maps need external validation and replication; motion selectivity in MT+ is the only topographic signature the author reports recovering.

<details><summary>References</summary>
<ul>
<li><a href="https://smartchunks.com/meta-tribe-v2-brain-prediction-fmri-model/">Meta ’s New AI Predicts Brain Activity, And They Just... | Smart Chunks</a></li>
<li><a href="https://balsa.wustl.edu/study/show/9Zkk">The HCP 7T Retinotopy Dataset: Description and pRF Analysis</a></li>

</ul>
</details>

**Tags**: `#computational neuroscience`, `#fMRI encoding models`, `#reproducibility`, `#multimodal models`, `#retinotopy`

---

<a id="item-tech-news-9"></a>
### [Apple details Secure Exclaves and recording-indicator checks](https://security.apple.com/blog/secure-exclaves/) ⭐️ 7.0/10

Apple published a Nov. 12 post detailing Secure Exclaves, an architecture that processes audio and video in a separate secure environment so the main system and apps receive only necessary recognition results in ambient mode rather than raw data, according to the company. Apple says the design is already used in HomeView face and sound recognition and in the iPhone 18 Pro privacy indicator. On the iPhone 18 Pro, dedicated hardware checks the microphone indicator dot&\#x27;s color, brightness, and visibility before audio is allowed into the main system; Apple also requires the dot to remain visible during relevant Siri audio sessions for at least three seconds in total. These are Apple&\#x27;s stated implementation details as relayed by a brief aggregator post, not an independent technical verification.

telegram · zaihuapd · Nov 12, 09:13

**「Context: isolation for camera and mic data」** Secure Exclaves are, in Apple&\#x27;s description, protected and compartmentalized runtimes that process camera and microphone data separately from the rest of the system, supported by isolation features built into multiple core components of the silicon so that data analyzed inside an exclave cannot be reached from outside it. The design underpins an &quot;ambient sensing&quot; mode in which apps and the main system receive only the recognition results they need rather than raw audio or video.

**「Impact」** Under Apple&\#x27;s description, a covered or spoofed microphone indicator fails the hardware check and audio is not admitted into the main system, making the visible dot part of the audio path rather than a cosmetic warning. Siri audio sessions on the iPhone 18 Pro must also keep the dot visible for at least three seconds in total.

<details><summary>References</summary>
<ul>
<li><a href="https://security.apple.com/blog/secure-exclaves">Secure Exclaves and Ambient Sensing - Apple Security Research</a></li>
<li><a href="https://www.androidpure.com/apple-secure-exclaves-iphone-18-pro-mic-indicator/">Apple Says iPhone 18 Pro Holds Hey Siri Audio Until the Mic ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#security architecture`, `#privacy`, `#hardware`, `#secure enclaves`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Serving MiniMax H3-Image at 4K on Vera Rubin](https://vllm.ai/blog/2026-11-12-minimax-h3-image-rubin) ⭐️ 8.0/10

rss · vLLM Blog · Nov 12, 00:00

**「Background」** MiniMax H3-Image is an open-weight text-to-image and editing model that produces native 4096×4096 images in six sampling steps. The vLLM-Omni team set out to support it on NVIDIA Vera Rubin at Day 0, where the challenge was turning a dense diffusion workload into interactive latency and useful throughput.

**「Solution」** Their report attributes the main gains to integration rather than a new algorithm: eligible DiT linear layers run in MXFP8 with FlashInfer CuTe-DSL kernels, sequence work is split across four GPUs with Ulysses SP4, and AdaLN projections are cached. VAE tiles are distributed across GPUs and decoded with CUDA Graph replay plus multiple streams; a BF16 control reduced VAE decoding from 2.635s to 0.213s and end-to-end latency from about 4.0s to 1.6s. With four Rubin GPUs and SP4 at concurrency 1, the team reports 0.866s median latency \(p95 0.944s\), 2.21× faster than GB200 and 1.64× faster than GB300. They stress that the 0.87s headline comes from short prompts; their 1,292-character coffee prompt averaged 1.09s. Throughput is a separate operating point: four single-GPU replicas reached 6,115 images/hour at concurrency 8, 38.7% above SP4. The authors project 146,755 images/day and $105.16/GPU/hour gross at an assumed $0.06879/image—or $78.87 at 75% utilization—before operating costs.

**「Takeaway」** The larger point is that subsecond native 4K serving comes from coordinating kernels, parallelism, caching, and decode orchestration—while reporting latency and throughput as distinct deployment choices. The economic projections remain extrapolations, but the engineering lessons transfer beyond this model.

**Tags**: `#diffusion serving`, `#GPU inference optimization`, `#vLLM-Omni`, `#benchmark methodology`, `#MXFP8`

---

## Financial News

<a id="item-finance-news-1"></a>
### [U.S. Commerce Department Finalizing Rule to Block Chinese AI Firms&\#x27; Remote Chip Access](https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule) ⭐️ 8.0/10

The U.S. Commerce Department is reportedly finalizing a rule that would stop Chinese AI companies from remotely using advanced AI chips through data centers abroad, extending existing semiconductor export restrictions to Malaysia, Singapore, Thailand and four other countries, according to The Information. The rule, which the White House has asked Congress to mandate, could be published as early as this month and is still being coordinated with other government agencies; Nvidia has lobbied against closing the remote-access gap.

telegram · zaihuapd · Nov 12, 03:42

**「Background」** The U.S. already restricts exports of advanced AI chips directly to China, but countries such as Malaysia sit in a middle tier of Commerce&\#x27;s export-control framework where those chips can be imported and operated without China-level restrictions — the gap the new rule targets, according to reporting on that framework.

**「Who would be affected」** Chinese AI developers such as Moonshot AI and ByteDance, which have been reaching Nvidia GB300 chips through cloud nodes in Thailand and Malaysia, would lose that route, while data-center and cloud operators in the covered Southeast Asian countries would need U.S. licenses to keep serving them.

<details><summary>References</summary>
<ul>
<li><a href="https://abhs.in/blog/bytedance-36000-nvidia-b200-chips-malaysia-us-export-controls-2026">ByteDance Routes 36,000 Nvidia B200 Chips Through Malaysia to...</a></li>
<li><a href="https://watcher.news/analysis/nvidia-china-export-controls-cloud-loophole/">Nvidia Chip Export Control Loophole China Firms Exploit via</a></li>
<li><a href="https://evermx.com/case/us-closes-nvidia-amd-ai-chip-export-loophole-china-2026">US Closes Nvidia and AMD AI Chip Export Loophole That... | Evermx</a></li>

</ul>
</details>

**Tags**: `#US export controls`, `#AI chips`, `#China AI`, `#Southeast Asia`, `#semiconductor policy`

---

<a id="item-finance-news-2"></a>
### [礼来口服减重药获批，成为中国首款口服GLP-1减重药](https://www.reuters.com/business/healthcare-pharmaceuticals/china-approves-eli-lillys-weight-loss-pill-orforglipron-2026-11-12/) ⭐️ 8.0/10

中国国家药品监督管理局于11月12日批准礼来的奥福格列隆（商品名穆优达）作为1类新药，用于肥胖或超重且伴至少一种体重相关合并症的成人，成为中国首个获批的口服GLP-1减重药。该药每日一次，不受饮食饮水限制，将与诺和诺德、辉瑞和信达生物的每周一次注射减重药竞争；其2型糖尿病适应证仍在审评中，价格和上市时间尚未公布。

telegram · zaihuapd · Nov 12, 10:09

**「Background」** GLP-1 drugs mimic a gut hormone that curbs appetite; the obesity treatments already on the Chinese market are weekly injections, while orforglipron is a small-molecule version taken as a daily pill and was the first oral small-molecule GLP-1 receptor agonist to reach late-stage \(Phase 3\) testing for both obesity and type 2 diabetes.

**「Who is affected」** Adults in China with obesity or excess weight plus at least one related condition gain a once-daily pill alternative to the once-weekly GLP-1 injections sold there by Novo Nordisk, Eli Lilly, Pfizer and Innovent, though the undisclosed price and launch date leave its real-world reach unclear.

<details><summary>References</summary>
<ul>
<li><a href="https://www.preprints.org/manuscript/202505.0972">Oral Small-Molecule GLP - 1 Receptor Agonists: Mechanistic Insights...</a></li>
<li><a href="https://www.timeslive.co.za/news/world/2026-08-24-how-drugmakers-sidestep-ad-bans-in-chinas-obesity-awareness-push/">How drugmakers sidestep ad bans in China ’s obesity awareness push</a></li>
<li><a href="https://mezha.net/eng/bukvy/d46e467b_drugmakers_intensify_competition/">Drugmakers Intensify Competition for China ’s Weight Loss Market</a></li>

</ul>
</details>

**Tags**: `#GLP-1`, `#China drug approval`, `#Eli Lilly`, `#obesity treatment`, `#pharmaceutical competition`

---