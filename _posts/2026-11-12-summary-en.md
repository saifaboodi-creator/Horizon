---
layout: default
title: "Horizon Summary: 2026-11-12 (EN)"
date: 2026-11-12
lang: en
---

> From 38 items, 11 important content pieces were selected

---

**Technology News**
1. [NVIDIA Announces CEO Transition, but Key Details Are Unverified](#item-tech-news-1) ⭐️ 8.0/10
2. [Anthropic IPO Link Draws Hacker News Debate on Valuation and Strategy](#item-tech-news-2) ⭐️ 8.0/10
3. [Critical RCE in Apache HTTP Server&\#x27;s mod\_http2 \(CVE-2026-119618\)](#item-tech-news-3) ⭐️ 8.0/10
4. [AWS releases official aws-emulator for local testing, reportedly built by AI agents](#item-tech-news-4) ⭐️ 8.0/10
5. [UMAP 0.6 adds recursive initialization and faster optimizers](#item-tech-news-5) ⭐️ 8.0/10
6. [US Commerce reportedly finalizing AI chip remote-access rule for Chinese firms](#item-tech-news-6) ⭐️ 8.0/10
7. [Google launches Gemini Decisions API with multimodal inputs](#item-tech-news-7) ⭐️ 7.0/10
8. [Why Writing Correct Software Is Hard](#item-tech-news-8) ⭐️ 7.0/10
9. [TRIBE v2 audit reports MT+ motion selectivity but no retinotopy or tonotopy](#item-tech-news-9) ⭐️ 7.0/10

**Technology Blog**
1. [vLLM-Omni Brings H3-Image 4K Serving to Vera Rubin](#item-tech-blog-1) ⭐️ 8.0/10

**Financial News**
1. [China approves Eli Lilly&\#x27;s oral weight-loss drug, first oral GLP-1 in the country](#item-finance-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [NVIDIA Announces CEO Transition, but Key Details Are Unverified](https://nvidianews.nvidia.com/news/nvidia-announces-ceo-transition) ⭐️ 8.0/10

NVIDIA&\#x27;s newsroom posted an item titled &quot;NVIDIA Announces CEO Transition,&quot; but the supplied material contains no article text or verified details on who is stepping down, who succeeds, when the change takes effect, or whether the board has approved it. A Reuters live-page link is present, but without readable content it cannot confirm the transition&\#x27;s terms or cause.

hackernews · lldb · Nov 12, 13:52 · [Discussion](https://news.ycombinator.com/item?id=50467087)

**「Context: Scrutiny Before Resignation」** NVIDIA&\#x27;s announcement followed scrutiny of Jensen Huang that intensified after he disclosed an affair, according to CNBC&\#x27;s live coverage; the New York Times reported that Huang had been entangled with a woman identified by U.S. intelligence as a Chinese spy. Nvidia&\#x27;s own release said Huang, the company&\#x27;s founder, resigned as president, CEO, and board member effective immediately.

**「Customer and partner uncertainty」** Jensen Huang’s resignation leaves Nvidia’s customers and partners facing leadership and succession uncertainty while an investigation proceeds. Organizations with GPU procurement or AI deployment plans should seek continuity assurances on product roadmaps and support, since the reports do not identify any specific product or compatibility changes.

**「Community discussion」** Commenters speculated that export-control violations, rather than an affair, drove the change, with one saying the reporting makes it hard to avoid concluding NVIDIA sold to China despite the ban. Others debated whether Jensen Huang was being held to a different moral standard than Elon Musk and argued that a compromised CEO creates governance risk; these are opinions, not confirmed facts.

<details><summary>References</summary>
<ul>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-announces-ceo-transition">NVIDIA Announces CEO Transition | NVIDIA Newsroom</a></li>
<li><a href="https://www.cnbc.com/2026/11/12/nvidia-jensen-huang-ceo-live-updates.html">Nvidia CEO Jensen Huang resigns: Live updates</a></li>
<li><a href="https://www.nytimes.com/live/2026/11/12/business/nvidia-jensen-huang-resigns">Jensen Huang Resigns as Nvidia CEO After Affairs: Live Updates</a></li>
<li><a href="https://www.cnbc.com/2026/11/12/nvidia-jensen-huang-ceo-live-updates.html">Nvidia CEO Jensen Huang resigns: Live updates</a></li>

</ul>
</details>

**Tags**: `#NVIDIA`, `#CEO transition`, `#semiconductors`, `#export controls`, `#Hacker News`

---

<a id="item-tech-news-2"></a>
### [Anthropic IPO Link Draws Hacker News Debate on Valuation and Strategy](https://ipo.anthropic.com/us/) ⭐️ 8.0/10

A Hacker News submission pointing to ipo.anthropic.com/us/ brought attention to an Anthropic IPO, but the supplied material contains no official filing, terms, or confirmation of listing status beyond the headline and URL. One commenter cited document figures including a $70–78 price range, roughly $968B implied market cap, $17.0B Q3 2026 revenue, about $81B run-rate revenue, $900.9B in compute commitments through 2045, and a Nasdaq ticker of ANT; those figures are unverified here. The discussion focused on whether the listing reflects durable demand for frontier models or a need for capital amid competition from cheaper and local models.

hackernews · josephljohnston · Nov 12, 11:46 · [Discussion](https://news.ycombinator.com/item?id=50465829)

**「Background」** An initial public offering would move Anthropic from private fundraising to a public listing, which is the threshold the posted ipo.anthropic.com page is pointing toward. The only deal specifics in the supplied material come from a commenter who says they reviewed the linked documents: a $70–78 price range, the Nasdaq ticker ANT, and an implied market cap of about $968B at $74; those figures are community-reported and not independently confirmed here.

**「Impact」** If the listing proceeds at the stated $70–$78 per-share range, Anthropic’s enterprise and developer customers will be relying on a vendor whose revenue, margins, and roughly $968 billion midpoint valuation are disclosed quarterly. That gives procurement teams a public basis for comparing API pricing and multi-year capacity commitments across model providers.

**「Community discussion」** Commenters disagreed about what the IPO says about Anthropic&\#x27;s position: one argued that if recursive self-improvement were near, investors would have delayed the listing rather than accept dilution, while another said most LLM use cases can switch to cheaper models, pushing labs toward end-user applications. A separate thread criticized Anthropic&\#x27;s use of 19th-century landscape paintings in promotional material as incongruous branding.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gate.com/blog/gate-anthropic-ipo-valuation-subscription-and-outlook">Gate Anthropic IPO : Valuation , Subscription and Outlook | Gate Blog</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#AI industry`, `#IPO`, `#public markets`, `#frontier AI`

---

<a id="item-tech-news-3"></a>
### [Critical RCE in Apache HTTP Server&\#x27;s mod\_http2 \(CVE-2026-119618\)](https://www.wiz.io/blog/cve-2026-119618-rce-apache-http-server-vulnerability) ⭐️ 8.0/10

A critical remote code execution vulnerability tracked as CVE-2026-119618 affects the HTTP/2 module \(mod\_http2\) in Apache HTTP Server, according to Wiz&\#x27;s advisory writeup. The supplied material does not include the advisory&\#x27;s own text, so specifics such as the affected release range and the first fixed version could not be verified here; commenters noted that the published patched version \(2.0.24\) appears inconsistent with a stated affected range of 2.0.8 through 2.0.42, and one reader argued the correct first patched version is 2.0.43. A patch commit was linked in the discussion, and operators of internet-facing httpd instances with HTTP/2 enabled are the group most directly concerned.

hackernews · soheilpro · Nov 12, 02:11 · [Discussion](https://news.ycombinator.com/item?id=50462177)

**「Background」** HTTP/2 support in Apache HTTP Server is delivered by mod\_http2 \(also published as the standalone mod\_h2 module\), which carries its own version number separate from the server&\#x27;s 2.4.x releases. That is why the advisory lists two affected ranges: httpd 2.4.55 through 2.4.70 and mod\_http2 2.0.8 through 2.0.42. Red Hat notes that mod\_http2 versions before 2.0.8 do not contain the affected code, and that Red Hat Enterprise Linux 8 and earlier are not affected.

**「Upgrade and mitigation caveats」** With a 9.8 CVSS score but no confirmed exploitation or KEV entry as of the scanner author’s writing, operators running affected mod\_http2 releases should verify the fixed version and upgrade promptly; commenters flag the advisory’s “2.0.24” figure as a likely typo and identify 2.0.43 as the first patched release. If they instead take httpd offline as a stopgap, they should also disable or audit certbot cron jobs and systemd timers, because a renewal run can restart httpd and bring the vulnerable service back up.

**「Community Discussion」** Commenters focused on patch clarity: ian-g flagged an apparent error in the advisory&\#x27;s patched-version field, saying it likely should read 2.0.43 rather than 2.0.24, and jamesy0ung linked a candidate fix commit in the Apache httpd repository. rurcliped added an operational caveat for anyone shutting down httpd as a stopgap — a certbot cron job or systemd timer can restart it, so instructions like &quot;systemctl disable --now apache2&quot; may not keep the service off — while account42 questioned whether HTTP/2&\#x27;s complexity was worth its benefits.

<details><summary>References</summary>
<ul>
<li><a href="https://www.wiz.io/blog/cve-2026-119618-rce-apache-http-server-vulnerability">Critical RCE Vulnerability in Apache HTTP Server ... | Wiz Blog</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-119618">CVE - 2026 - 119618 - Red Hat Customer Portal</a></li>
<li><a href="https://sobasically.ai/stories/cisa-issues-advisory-on-apache-http-server-http2-remote-code-execution-defect/">CISA issues advisory on Apache HTTP Server HTTP /2 remote code...</a></li>
<li><a href="https://github.com/foxcornlab/apache-httpd-scanner">GitHub - foxcornlab/ apache -httpd-scanner: Detection-only triage for...</a></li>

</ul>
</details>

**Tags**: `#security vulnerability`, `#Apache HTTP Server`, `#HTTP/2`, `#RCE`, `#open source`

---

<a id="item-tech-news-4"></a>
### [AWS releases official aws-emulator for local testing, reportedly built by AI agents](https://simonwillison.net/2026/Nov/11/aws-emulator/) ⭐️ 8.0/10

AWS has released aws-emulator, an official Rust-based tool for running tests against local clones of AWS services without provisioning a paid API key. Simon Willison reports that the project recorded 29,684 commits in its first three weeks and describes it as written by a large swarm of AI agents; AWS&\#x27;s Swami Sivasubramanian wrote about how it came to be in a guest post on Werner Vogels&\#x27; blog. It currently requires Docker on macOS and Windows, and its security documentation warns against using it to test IAM policies, resource-based policies, KMS key policies, cross-account or cross-region access, or other security controls, noting that the emulator never denies a request signed with its own key.

rss · Simon Willison · Nov 11, 21:18

**「Prior art for local AWS testing」** Local AWS emulation is not new: developers who want integration tests without provisioning billed resources have relied on community projects such as LocalStack and Moto, both of which Hacker News commenters cite as alternatives they already use. What is new here is an emulator published by AWS itself, released alongside a Sivasubramanian essay on how the engineer&\#x27;s job changes when agents write the code.

**「Testing constraints」** Developers can run integration tests against local AWS service clones without provisioning paid API keys, but on macOS and Windows they currently need Docker available in local and CI environments. The emulator should not be used to validate IAM policies, resource-based policies, KMS key policies, or cross-account and cross-Region access, according to security guidance quoted in the discussion.

**「Community discussion」** Commenters debated whether aws-emulator will be a maintained product: one questioned whether it was an exercise or a real product AWS will ship and support, saying Floci with Testcontainers has worked well and also covers GCP and Azure in limited use, while another argued that without AI agents AWS would not have attempted an emulator across so many services, eroding the moat of projects such as LocalStack. A commenter also highlighted the security documentation&\#x27;s warning that the emulator should not be used to test IAM policies, resource-based policies, KMS key policies, cross-account or cross-region access, or other security controls.

<details><summary>References</summary>
<ul>
<li><a href="https://www.allthingsdistributed.com/2026/11/aws-emulator-and-the-engineers-job-when-agents-write-the-code.html">AWS Emulator and the engineer&#x27;s job when agents write the code</a></li>

</ul>
</details>

**Tags**: `#aws`, `#local-emulation`, `#testing`, `#rust`, `#ai-agents`

---

<a id="item-tech-news-5"></a>
### [UMAP 0.6 adds recursive initialization and faster optimizers](https://www.reddit.com/r/MachineLearning/comments/1xudaah/umap_06_new_initialization_new_optimizers_and/) ⭐️ 8.0/10

UMAP 0.6, available via \`pip install -U umap-learn\` and conda-forge, adds a recursive UMAP-based initialization, new optimizers with hard-negative mining, and roughly 4x faster nearest-neighbor search through PyNNDescent. The maintainer reports that a seeded 3-million arXiv-paper run finishes in under five minutes versus 52 minutes for UMAP 0.5, and that the full run is now reproducible with a fixed seed while using every core. The maintainer also claims better million-scale quality, including finer cluster detail and improved kNN recall, but these speed and quality figures are self-reported and not independently verified. Because the new initialization and optimizers change output, they are opt-in via \`compatibility\_layout=False\`; the maintainer says future versions will make them the default.

reddit · r/MachineLearning · /u/lmcinnes · Nov 12, 13:51

**「Background」** UMAP is a dimensionality-reduction library that lays out a nearest-neighbour graph and optimizes a low-dimensional representation using attraction and repulsion. Earlier versions relied on spectral embedding or PCA for initialization and tuned the optimizer around a limited portion of the attraction–repulsion spectrum; the 0.6 post presents both as constraints at million-point scale.

**「Impact」** Million-scale users can get a seeded, all-core reproducible run on the new optimizer path, but they must opt in with \`compatibility\_layout=False\`, which changes embeddings and may require revalidating downstream cluster labels.

**Tags**: `#UMAP`, `#dimensionality reduction`, `#nearest neighbor search`, `#open-source ML`, `#performance optimization`

---

<a id="item-tech-news-6"></a>
### [US Commerce reportedly finalizing AI chip remote-access rule for Chinese firms](https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule) ⭐️ 8.0/10

The US Commerce Department is reportedly finalizing a rule that would block Chinese AI companies from remotely using advanced AI chips through overseas data centers, with an announcement possible as soon as this month, according to The Information. The measure would extend existing semiconductor export restrictions to seven countries including Malaysia, Singapore, and Thailand to close remote-access and chip-smuggling gaps; Commerce is consulting other agencies before finalizing it, so the rule is not yet in effect. The White House has asked Congress to legislate a requirement for the rule, while Nvidia has lobbied against closing the remote-access gap, arguing that US AI infrastructure needs to prevail globally.

telegram · zaihuapd · Nov 12, 03:42

**「Existing controls and the remote-access gap」** The rule builds on existing US semiconductor export restrictions that already limit direct shipments of advanced AI chips to China; the gap it targets is remote access, where Chinese AI firms rent compute capacity in overseas data centers instead of importing the hardware themselves. According to the report, the White House has already asked Congress to legislate the requirement, directing the Commerce Department to draft this rule, and Nvidia has lobbied against closing the remote-access gap.

**「Impact」** For Southeast Asian data-center operators renting Nvidia GPUs to Chinese customers — a setup TechTimes described in late August as sitting in a legal gray zone that existing rules could not clearly reach — the finalized rule would convert a tolerated workaround into a compliance risk, requiring end-customer screening or contract reviews. Chinese AI developers that have depended on such rented capacity \(CNBC reported in August that firms were reaching advanced Nvidia compute through Southeast Asian data centers\) would need alternative sources, though the rule&\#x27;s actual terms and effective date have not been published.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/08/19/china-ai-nvidia-chips-us-export-controls.html">China AI firms tap Nvidia power overseas as U.S ... - CNBC</a></li>
<li><a href="https://www.forbes.com/sites/viviantoh/2026/08/31/the-ai-chip-wars-new-front-control-the-cloud-not-the-silicon/">The U.S. Tried To Keep AI Chips From China. The ... - Forbes</a></li>
<li><a href="https://www.techtimes.com/articles/325957/20260829/commerce-drafts-ai-chip-rule-loophole-it-created-rescinding-biden-know-your-customer.htm">Commerce Drafts AI Chip Rule for Loophole It Created by ...</a></li>

</ul>
</details>

**Tags**: `#export controls`, `#AI chips`, `#semiconductors`, `#US-China tech`, `#data centers`

---

<a id="item-tech-news-7"></a>
### [Google launches Gemini Decisions API with multimodal inputs](https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/) ⭐️ 7.0/10

Google has launched the Gemini Decisions API, built on a new Gemini Decision 1 model, for closed-ended decisions such as tool selection, policy checks, and model routing. It handles yes/no, choice, and rubric-scoring questions—matching Jev&\#x27;s three question types—and accepts text, images, audio, video, and PDFs, while Jev is text/JSON-only and OpenAI&\#x27;s GPT-6 Luna decision model handles text and images. Pricing is 10 cents per million input tokens with output free, the same as GPT-6 Luna and above Jev&\#x27;s 4.2 cents per million; the API is available in Google AI Studio. Google says one request can score up to 1,000 questions with 150–250 ms end-to-end latency; in a video test, the model returned probabilities—roughly 0.92 for &quot;robot&quot; and &quot;USA&quot; and 0.05 for &quot;dragon&quot;—where Jev and OpenAI return 1.0 or 0.0.

hackernews · iamdelirium · Nov 11, 18:32 · [Discussion](https://news.ycombinator.com/item?id=50456791)

**「Background」** Decision models are a narrower interface than chat completions: they take a set of closed-form questions—yes/no, multiple-choice, or rubric-scored—and return a probability for each instead of free-form text. Google is entering a category already occupied by Jev, which is text-only, and OpenAI&\#x27;s GPT-6 Luna decision model, which handles text and images; Gemini Decision 1 extends the accepted inputs to audio, video, and PDFs.

**「Impact」** Teams that need to classify audio, video, or PDF content can send those files directly to a hosted decision model instead of relying on a text-only API; for high-volume plain-text decisions, Jev remains less than half the input-token price.

**「Community discussion」** Commenters treated audio, video, and PDF support as the main differentiator, with one calling it the first decision model to handle those inputs and noting that Jev remains faster and cheaper for common text tasks. Another said the higher price can be worthwhile for audio and video, while a separate thread questioned how decision models calculate probabilities and cited concerns about asking LLMs for confidence scores.

**Tags**: `#Gemini`, `#decision models`, `#multimodal AI`, `#Google AI`, `#APIs`

---

<a id="item-tech-news-8"></a>
### [Why Writing Correct Software Is Hard](https://pron.github.io/posts/correctness-and-complexity) ⭐️ 7.0/10

A technical essay on pron.github.io examines why writing correct software is difficult, focusing on formal verification, specifications, and complexity-theoretic limits. The accompanying Hacker News thread questions whether mathematical correctness captures real-world behavior and debates how Rice&\#x27;s theorem applies to particular programs. This is an essay and community discussion, not a product release or an independently measured result.

hackernews · AriFordsham · Nov 12, 10:28 · [Discussion](https://news.ycombinator.com/item?id=50465352)

**「Background」** The essay&\#x27;s argument draws on Rice&\#x27;s theorem, a computability result stating that no general algorithm can decide, for an arbitrary program and specification, whether that program satisfies the specification—equivalently, non-trivial semantic properties of arbitrary programs are undecidable. This limit applies to fully automatic verification of arbitrary code; it does not preclude proving properties of a specific program by hand or with targeted tooling.

**「Impact」** For developers considering formal verification, the practical concern is specification validity: a proof can show that code matches a formal specification without showing that the specification reflects real-world requirements. Teams should therefore budget for specification and design work rather than treating proof construction as the whole task.

**「Community Discussion」** Commenters disagreed about whether formal correctness translates into real-world reliability: one argued that software handling complex human workflows must deal with the “endless vagaries of reality,” while another asked how a specification itself can be judged correct. A separate critique disputed the essay&\#x27;s use of Rice&\#x27;s theorem, arguing that it rules out a general decision method for all programs rather than one-off proofs about a given program.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Rice&#x27;s_theorem">Rice&#x27;s theorem - Wikipedia</a></li>
<li><a href="https://www.cs.cornell.edu/courses/cs6410/2013fa/slides/10-verifiable-systems.pdf">Formally Verified Operating Systems - Department of Computer ...</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#software correctness`, `#complexity theory`, `#Rice&\#x27;s theorem`, `#programming methodology`

---

<a id="item-tech-news-9"></a>
### [TRIBE v2 audit reports MT+ motion selectivity but no retinotopy or tonotopy](https://www.reddit.com/r/MachineLearning/comments/1xuillf/does_metas_brainresponse_model_tribe_v2_actually/) ⭐️ 7.0/10

A self-posted independent audit of Meta&\#x27;s TRIBE v2 reports that the fMRI prediction model showed sharp motion selectivity localized to MT+ \(d=4.31, 52-fold enrichment over chance\) but did not recover retinotopic \(d=0.05, n.s.\) or tonotopic \(ρ=-0.07, n.s., with loudness controlled\) maps when tested with classic checkerboard, hemifield, moving-dot, and tone-sweep stimuli. The author writes that eccentricity initially looked null but became significant and spatially &quot;correct&quot; under three separate stimulus-geometry controls, which he interprets as an image-statistics confound rather than a genuine positional code. The work is described as a solo, self-funded project with linked code and paper, is not peer-reviewed, and the supplied post text is truncated.

reddit · r/MachineLearning · /u/Own\_Tank1283 · Nov 12, 17:16

**「Background」** TRIBE is Meta&\#x27;s trimodal brain encoder, trained to predict whole-brain fMRI responses to video, audio, and text; the original paper reported state-of-the-art results in the Algonauts 2025 competition \(tool-2-1\). Meta released TRIBE v2 together with its model, codebase, paper, and an interactive demo on March 26, 2026, which is what made the kind of independent probing described here possible \(tool-2-2\).

**「Impact」** For researchers using TRIBE v2 as a brain-encoding model, the audit argues that strong motion selectivity does not establish topographic coding and that stimulus-geometry controls are needed before treating eccentricity or other position-related predictions as neural maps.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2507.22229">[2507.22229] TRIBE: TRImodal Brain Encoder for whole-brain ...</a></li>
<li><a href="https://ai.meta.com/blog/tribe-v2-brain-predictive-foundation-model/">Introducing TRIBE v2: A Predictive Foundation Model Trained ...</a></li>

</ul>
</details>

**Tags**: `#neuroAI`, `#fMRI`, `#model evaluation`, `#replication`, `#topographic maps`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [vLLM-Omni Brings H3-Image 4K Serving to Vera Rubin](https://vllm.ai/blog/2026-11-12-minimax-h3-image-rubin) ⭐️ 8.0/10

rss · vLLM Blog · Nov 12, 00:00

**「Background」** The vLLM-Omni team reports day-0 MiniMax H3-Image support on NVIDIA Vera Rubin. The open-weight model performs text-to-image generation and editing in six sampling steps at native 4K, pairing a dense 33.1B DiT with VAE decoding under interactive-latency and throughput constraints.

**「Solution」** The authors targeted DiT compute, decoding overhead, and memory. On Blackwell and Rubin, eligible DiT linears use MXFP8 GEMMs—FlashInfer CuTe-DSL on Rubin—while the encoder and VAE keep native precision; Ulysses SP4 spreads sequence work across four GPUs with replicated DiT weights, and AdaLN caching reuses conditioning projections. For decoding, they distribute VAE tiles across GPUs and combine CUDA Graph replay with multiple CUDA streams, reporting a control where VAE decoding falls from 2.635s to 0.213s and end-to-end latency from about 4.0s to 1.6s. Moving final image-layout conversion to the CPU fixed a repeated-4K stall. Four Rubin GPUs with SP4 and MXFP8 reach 0.866s median \(p95 0.944s\) for native 4096×4096 text-to-image—2.21× faster than GB200 and 1.64× faster than GB300—while a separate SP1×DP4 replica setup reaches 6,115 images/hour at concurrency 8, versus 4,407 for SP4. They distinguish the 0.87s short-prompt result from a 1.09s coffee-product prompt and caution that GPU count, precision, and memory placement vary. Using MiniMax&\#x27;s USD 0.06879 Standard 4K API example as an assumed sale price, they project USD 105.16/GPU/hour gross at full utilization, before operating costs.

**「Takeaway」** The authors&\#x27; larger point is that 4K diffusion serving is a systems problem: kernel choice, parallelism, and decoding-path engineering can make it interactive and economically plausible, though the headline is a configuration-specific operating point rather than a universal GPU comparison.

**Tags**: `#diffusion serving`, `#vLLM-Omni`, `#CUDA Graph`, `#sequence parallelism`, `#GPU benchmarking`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China approves Eli Lilly&\#x27;s oral weight-loss drug, first oral GLP-1 in the country](https://www.reuters.com/business/healthcare-pharmaceuticals/china-approves-eli-lillys-weight-loss-pill-orforglipron-2026-11-12/) ⭐️ 8.0/10

China&\#x27;s drug regulator approved Eli Lilly&\#x27;s once-daily oral GLP-1 weight-loss drug, orforglipron calcium tablets \(brand name Mu You Da\), on November 12 as a Class 1 new drug for adults who are obese or overweight with at least one weight-related condition, making it the country&\#x27;s first approved oral GLP-1 weight-loss treatment, according to Reuters. The drug will compete with weekly injectable weight-loss medicines from Novo Nordisk, Pfizer and Innovent Biologics; its Type 2 diabetes indication is still under review, and pricing and launch timing were not disclosed.

telegram · zaihuapd · Nov 12, 10:09

**「Background」** Before this approval, the competing weight-loss drugs cited in the report — from Novo Nordisk, Pfizer and Innovent — were weekly injections, making orforglipron China’s first daily oral option in this drug class.

**「Who is affected」** Chinese adults with obesity or overweight plus at least one weight-related condition gain a once-daily oral alternative to the once-weekly injectable GLP-1 weight-loss drugs from Novo Nordisk, Pfizer and Innovent; price and launch timing are undisclosed, so patient access remains unclear.

**Tags**: `#Eli Lilly`, `#GLP-1`, `#China drug approval`, `#obesity treatment`, `#pharmaceuticals`

---