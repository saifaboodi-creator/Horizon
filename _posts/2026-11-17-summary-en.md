---
layout: default
title: "Horizon Summary: 2026-11-17 (EN)"
date: 2026-11-17
lang: en
---

> From 48 items, 15 important content pieces were selected

---

**Technology News**
1. [vLLM v0.34.0 makes automatic KV-cache sizing default and drops Model Runner V1](#item-tech-news-1) ⭐️ 8.0/10
2. [Carnegie Mellon publishes full CS course lectures free on YouTube](#item-tech-news-2) ⭐️ 7.0/10
3. [Report: Optimizely served malware via scripts on Zoom and GitLab](#item-tech-news-3) ⭐️ 7.0/10
4. [Linebender wiki explains squircles and smooth curve families](#item-tech-news-4) ⭐️ 7.0/10
5. [Jiff 1.0 ships as a new datetime library for Rust](#item-tech-news-5) ⭐️ 7.0/10
6. [Marimba adds calibrated speech question answering to a frozen ASR encoder](#item-tech-news-6) ⭐️ 7.0/10
7. [Duetto steers pretrained music transformer at sampling time for live jazz](#item-tech-news-7) ⭐️ 7.0/10
8. [US and Nine Countries Sign San Francisco Declaration on AI Supply-Chain Security](#item-tech-news-8) ⭐️ 7.0/10
9. [Amazon: Artex-driven AI agents stole API keys to fund model calls](#item-tech-news-9) ⭐️ 7.0/10
10. [US extends AI chip export controls to remote access](#item-tech-news-10) ⭐️ 7.0/10
11. [Alibaba, Tencent, Moonshot Reportedly Limit Cyber Capabilities in New Models](#item-tech-news-11) ⭐️ 7.0/10
12. [Apple China App Store adds AIGC filing deadline of Jan. 31, 2027](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Lutnick faces scrutiny over Cantor Fitzgerald&\#x27;s Nvidia ties](#item-finance-news-1) ⭐️ 8.0/10
2. [Nvidia CEO Jensen Huang resigns as shares slide; Yorkville Ives cuts price target but keeps buy rating](#item-finance-news-2) ⭐️ 7.0/10
3. [Intel and CEO Lip-Bu Tan sued in shareholder class action](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 makes automatic KV-cache sizing default and drops Model Runner V1](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM v0.34.0 makes extensible KV-cache sizing the default on CUDA and ROCm, calculating cache capacity from memory actually free after CUDA graph capture and warmup rather than from an estimate. The release says this yields a larger cache and more throughput—MiniMax-M3 on H200 rises from 433k to 672k tokens—but can raise per-token decode latency by 6–18% on some H200 models at concurrency 128; users can pass --gpu-memory-utilization 0.9 or --no-enable-extensible-kv-cache to opt out. Model Runner V1 is removed, so VLLM\_USE\_V2\_MODEL\_RUNNER=0 now fails at startup and V1 logits processors must be ported to vllm.v1.worker.gpu.sample.logits\_processor. Other breaking changes include a default block size of 64 instead of 16, removal of ROCm 7.2 artifacts, and a requirement for huggingface\_hub &gt;= 2.0.0; the release also reports up to 1.95× decode speedup for Step5 on 4×GB200 and new models including Mistral Large 4.

github · khluu · Nov 16, 23:22

**「Background」** vLLM is an open-source LLM inference server, and its Model Runner is the GPU-side execution path that runs model forward passes and sampling. Before v0.34.0, operators could fall back to the older Model Runner V1 by setting \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\`; this release removes that fallback, so the variable now causes startup failure.

**「Impact」** Operators upgrading existing deployments should remove VLLM\_USE\_V2\_MODEL\_RUNNER=0 before starting v0.34.0 and pass --block-size 16 if their workloads depend on the previous default; ROCm 7.2 users must move to ROCm 10.0 images or wheels. Because the KV-cache change is default-on, teams that see higher per-token latency at high concurrency need to opt out explicitly rather than rely on the old sizing.

**Tags**: `#vLLM`, `#LLM inference`, `#KV cache`, `#model runner`, `#release notes`

---

<a id="item-tech-news-2"></a>
### [Carnegie Mellon publishes full CS course lectures free on YouTube](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

Carnegie Mellon&\#x27;s Griffin School of Computer Science has launched CS Learn, which is publishing full semesters of lectures from current CMU computer science courses free on YouTube, with one course premiering each day during launch week and more planned for January. Phillip Compeau, who runs the project, said students built tools that automate much of the production work, allowing a small team to release the courses. The initial catalog spans a variety of topics, though the supplied material does not list every course.

hackernews · pcompeau · Nov 16, 20:43 · [Discussion](https://news.ycombinator.com/item?id=50522980)

**「Context: open courseware and CMU&\#x27;s Griffin School」** CS Learn is run out of Carnegie Mellon&\#x27;s Kenneth C. Griffin School of Computer Science, and its YouTube channel describes the project as opening the school&\#x27;s classrooms to learners everywhere with real lectures from real CMU courses. Phillip Compeau, who runs CS Learn, acknowledged in the launch discussion that MIT&\#x27;s OpenCourseWare made free course material available roughly 25 years earlier, framing the difference as production method rather than firstness. Coverage of the launch describes the initial slate as spanning machine learning, ML systems and software construction, taught by faculty drawn from seven departments.

**「Impact」** For learners, the immediate effect is access to current CMU lectures without enrollment or payment; the unanswered question in the discussion is whether assignments and homework will also be released, so the courses may function as lecture-only material for now.

**「Community discussion」** Commenters welcomed specific offerings, including 15-259 Probability and Computing and Tianqi Chen&\#x27;s ML Systems, and asked for core courses such as 15-122, 15-150, 15-151, 15-251 and 15-451. One commenter argued that learning fundamentals properly makes AI a power tool rather than a replacement, an opinion rather than a claim established by the source.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/channel/UCqvooOJo8792T83va7LMMSA">CS Learn at Carnegie Mellon - YouTube</a></li>
<li><a href="https://todayforai.com/en/items/art-2c7b6259-c5f">Carnegie Mellon Opens Computer Science Courses Free on YouTube</a></li>

</ul>
</details>

**Tags**: `#computer-science-education`, `#open-courseware`, `#online-learning`, `#youtube`, `#cmu`

---

<a id="item-tech-news-3"></a>
### [Report: Optimizely served malware via scripts on Zoom and GitLab](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 7.0/10

A report alleges that Optimizely was compromised and served malware through third-party scripts on sites including Zoom and GitLab. The supplied material does not establish how attackers obtained write access or the full scope of affected customers; a commenter quoting the report says Optimizely&\#x27;s CDN delivered the code as given rather than suffering cache poisoning, and that Optimizely&\#x27;s own domains were also affected. The incident concerns trust in third-party JavaScript and tag-management vendors rather than a confirmed browser vulnerability.

hackernews · kristjansson · Nov 16, 23:00 · [Discussion](https://news.ycombinator.com/item?id=50524767)

**「Background」** Optimizely Web is a hosted experimentation and testing platform that customers embed as a third-party script across their pages; because that script executes in the embedding page&\#x27;s security context, compromising the vendor can affect every site that includes it. Reports on the 16 November 2026 incident say malicious JavaScript was injected into Optimizely Web and reached visitors across 178 organizations, including Zoom, the BBC, CNN, Salesforce, GitLab, HSBC, and IKEA.

**「Impact」** Optimizely said it added nothing itself — its CDN served whatever it was given — but it confirmed an outside party inserted malicious JavaScript into some customer projects, then blocked the vulnerable path, deployed a fix and notified all affected customers. The practical burden therefore falls on the site operators: the injected code executed in visitors&\#x27; browsers under the customers&\#x27; own domains, so those teams have to determine which pages carried the snippet and whether it triggered redirects or credential theft, rather than relying on the vendor&\#x27;s fix alone. Until Optimizely explains how the attacker obtained write access across unrelated customer projects, other customers have no basis for judging whether their own projects were reachable by the same path.

**「Community discussion」** Commenters described the incident as a predictable risk of tag-management systems that let marketing add third-party JavaScript without engineering review, with one arguing that vendors and large sites lack accountability and should self-host critical scripts. Others suggested browser-level script blocking to reduce exposure and questioned whether major sites run such third-party code alongside sensitive functions.

<details><summary>References</summary>
<ul>
<li><a href="https://shiftdelete.net/en/optimizely-malware">Optimizely Malware Hit 178 Sites: What It Stole and What to Do</a></li>
<li><a href="https://cybersecuritynews.com/optimizely-websites-hijacked/">Hackers Infect 178 Major Websites via Optimizely to Steal ...</a></li>
<li><a href="https://gizmodo.com/sprawling-malware-attack-reportedly-affects-zoom-cnn-fox-news-peacock-and-170-others-2000840831">Sprawling Malware Attack Reportedly Affects Zoom and Other Major...</a></li>

</ul>
</details>

**Tags**: `#supply-chain-security`, `#web-security`, `#third-party-scripts`, `#malware`, `#Optimizely`

---

<a id="item-tech-news-4"></a>
### [Linebender wiki explains squircles and smooth curve families](https://linebender.org/wiki/curves/squircle/) ⭐️ 7.0/10

Linebender has published a wiki article on squircles and related smooth curves, written by Raph Levien, as part of the project&\#x27;s curves documentation. The page is an explanatory reference rather than a release or announcement: it covers the squircle shape family and neighbouring spline-based constructions used in graphics and interface work. The Hacker News discussion treats it as background material for people authoring shapes for graphics, UI design, and font or spline geometry, with commenters extending it toward clothoids, superellipses, and three-dimensional analogues.

hackernews · raphlinus · Nov 16, 07:55 · [Discussion](https://news.ycombinator.com/item?id=50515151)

**「Background」** A squircle is a shape intermediate between a square and a circle, but it has no single mathematical definition: several curve families fit the shape, and general squircles are parametrized so they can vary between a circle and a square. The Linebender wiki article collects these curve forms, which makes the distinction between specific formulas and a general shape family central to the discussion.

**「Why it matters」** For developers and designers who author UI or graphics shapes, the practical takeaway raised in the thread is derivative continuity: commenters note that curves without discontinuities in their derivatives are what enable perceived smoothness once a shape is manipulated or interacted with physically, which is the criterion for choosing between a squircle and an ordinary rounded rectangle.

**「Community discussion」** Commenter thot\_experiment described building a spline-authoring tool in which superellipses and clothoids feature heavily, linking a demo and cautioning that it is an early exploration full of edge-case exceptions. scarecrw recommended a paper on the &quot;sphube,&quot; a three-dimensional counterpart to the squircle, while mosura argued that curves free of derivative discontinuities are exactly what make smoothness achievable in physical interaction.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Squircle">Squircle - Wikipedia</a></li>
<li><a href="https://linebender.org/wiki/curves/squircle/">Squircles - Linebender</a></li>

</ul>
</details>

**Tags**: `#squircles`, `#computational geometry`, `#computer graphics`, `#UI design`, `#splines`

---

<a id="item-tech-news-5"></a>
### [Jiff 1.0 ships as a new datetime library for Rust](https://burntsushi.net/jiff/) ⭐️ 7.0/10

Jiff 1.0 has been released as a datetime library for Rust, written by Andrew Gallant \(burntsushi\). The project&\#x27;s documentation explicitly states that Jiff &quot;isn&\#x27;t always the right thing to use,&quot; framing it as a deliberate choice rather than a universal replacement. The library&\#x27;s documentation also addresses time scales, including TAI, according to discussion of the release, though the source material does not detail how those scales are implemented. No benchmarks, migration tooling, or compatibility guarantees were provided in the available material.

hackernews · burntsushi · Nov 16, 16:53 · [Discussion](https://news.ycombinator.com/item?id=50519744)

**「What Jiff is」** Jiff is a Rust datetime library by Andrew Gallant \(burntsushi\) that aims to provide high-level datetime primitives which are difficult to misuse. Its documentation says it puts time zone handling front and center, automatically handling many common daylight-saving-time problems.

**「Impact for Rust developers」** Rust teams weighing a move away from chrono now have a 1.0-stable alternative whose documentation frames its design around high-level datetime primitives that are difficult to misuse at reasonable performance, rather than around drop-in compatibility. Because the project publishes both a comparison with other Rust datetime crates and a rationale for building another library, adopters can scope the API differences and migration cost before switching; whether the broader ecosystem actually follows remains, in the comments, an expressed hope rather than a demonstrated shift.

**「Community discussion」** A former chrono maintainer \(quodlibetor\) said chrono&\#x27;s stable API made incremental improvements difficult and that burnout ended his maintenance tenure, expressing gratitude that Jiff exists. Other commenters praised Jiff&\#x27;s explicit statement that it is not the right tool for every use case and hoped the wider Rust ecosystem would adopt it over chrono, while one user simulating solar-system orbits asked how Jiff handles time scales such as UT1 alongside microsecond-relative and geological-scale needs.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/jiff: A datetime library for Rust that ...</a></li>
<li><a href="https://burntsushi.net/jiff/">A datetime library for Rust - Andrew Gallant&#x27;s Blog</a></li>
<li><a href="https://docs.rs/jiff/latest/jiff/">jiff - Rust</a></li>
<li><a href="https://users.rust-lang.org/t/jiff-is-a-new-date-time-library-for-rust-that-encourages-you-to-jump-into-the-pit-of-success/114781">Jiff is a new date - time library for Rust that encourages you to jump...</a></li>

</ul>
</details>

**Tags**: `#Rust`, `#datetime`, `#open-source libraries`, `#time scales`, `#API design`

---

<a id="item-tech-news-6"></a>
### [Marimba adds calibrated speech question answering to a frozen ASR encoder](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

A new preprint introduces Marimba, which answers typed yes/no, multiple-choice, or score questions about an audio window and returns a calibrated probability. It uses one frozen Qwen3-ASR-0.6B encoder pass per 8-second window for all question types, with zero-shot term scoring from ASR hypotheses plus Platt calibration, the model&\#x27;s own language scores, and small readouts on frozen layers for turn end, speaker change, and speaker count. In the authors&\#x27; reported results on 1,000 public questions, Marimba matches or beats Qwen3-Omni \(30B-A3B\) on 6 of 9 tests, but Qwen3-Omni remains better on Speech Commands. The authors note that their turn-end readout was trained on Smart Turn data, so that row is in-distribution; on Smart Turn&\#x27;s test set Marimba scores 0.930 AUROC versus 0.982 for Smart Turn v3.2, and on CochlScene every head is at chance, indicating no generalization to unseen tasks.

reddit · r/MachineLearning · /u/solanotodesch · Nov 16, 15:47

**「Background」** Turn-end detection is the speech task of deciding whether a speaker has finished, so a voice agent can reply rather than wait through a pause. Smart Turn v3.2 is an existing model that takes the last 8 seconds of speech and returns that probability, and it is the comparison point Marimba&\#x27;s authors single out because their turn-end readout was trained on Smart Turn data.

**「Impact」** Developers can install the marimba-audio package and use the Apache-2.0 weights, but the chance-level CochlScene result means Marimba should not be treated as a general audio classifier, and its turn-end readout needs testing beyond Smart Turn&\#x27;s data.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/sitatech/Smart-Turn-v3.2-ONNX">sitatech/ Smart - Turn - v 3 . 2 -ONNX · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#speech-recognition`, `#audio-understanding`, `#model-efficiency`, `#calibration`, `#Qwen3`

---

<a id="item-tech-news-7"></a>
### [Duetto steers pretrained music transformer at sampling time for live jazz](https://www.reddit.com/r/MachineLearning/comments/1xxkyh3/steering_a_pretrained_music_transformer_at/) ⭐️ 7.0/10

Duetto is a real-time MIDI jazz partner that plays standards with a keyboardist as a small band—solo, comping, or walking bass—by steering the pretrained Anticipatory Music Transformer at sampling time rather than fine-tuning it. A rule layer masks or biases logits before each note, using chord tones, guide tones, and phrases from the Weimar Jazz Database; in the Autumn Leaves demo at 160 bpm, about 61% of solo notes came from quoted phrases or the theme. The author reports roughly 12 ms per note for the medium model and 18 ms for the large model on a 3080 Ti, and about 90 ms per note for the large model on a Jetson Orin Nano, with a server keeping about one second of music sampled ahead and resampling unplayed material when the player plays. The project is a demo with code free for noncommercial use, and the author notes that it can drift from the player, respond unpredictably, and become fragile when balancing model output against rule-based bias.

reddit · r/MachineLearning · /u/GGAllin43 · Nov 16, 09:19

**「Background」** The Anticipatory Music Transformer, published by John Thickstun, David Hall, Chris Donahue, and Percy Liang in 2023, is a pretrained symbolic-music model built on interleaved event and control sequences, an arrangement intended to support anticipatory generation for music control tasks. Duetto leans on that existing pretrained model rather than retraining it, treating the player&\#x27;s notes and the model&\#x27;s own output as a single event sequence and editing the logits before each note is sampled.

**「Impact」** For developers prototyping interactive symbolic-music systems, the project shows that a fixed pretrained model can be adapted through logit masking and biasing plus a short resampling buffer without retraining, but the reported drift and fragile bias balance mean the control layer, not just model speed, is the main engineering work. The released code is free only for noncommercial use.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2306.08620">[2306.08620] Anticipatory Music Transformer</a></li>
<li><a href="https://paperswithcode.co/paper/2306.08620">Anticipatory Music Transformer (arXiv...) | Papers with Code</a></li>

</ul>
</details>

**Tags**: `#music generation`, `#sampling-time control`, `#transformers`, `#real-time interaction`, `#pretrained models`

---

<a id="item-tech-news-8"></a>
### [US and Nine Countries Sign San Francisco Declaration on AI Supply-Chain Security](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 7.0/10

The United States, Australia, India, Israel, Japan, South Korea, Qatar, Singapore, the UAE, and the UK signed the San Francisco Declaration on November 15, agreeing that economic security underpins national security and pledging to protect sensitive technologies and critical infrastructure in the superintelligence supply chain. The declaration calls for five working groups covering innovation-policy frameworks, SI applications in critical sectors, full-stack SI supply-chain collaboration, safe harbors and supply-chain security hubs, and SI security and resilience.

telegram · zaihuapd · Nov 16, 10:40

**「Background」** The declaration is organized around the supply chain for superintelligence \(SI\), meaning the sensitive technologies and critical infrastructure that support advanced AI systems rather than a single model or product. The source says the signatories will set up five working groups covering an innovation policy framework, SI use in critical sectors, full-stack supply-chain cooperation, safe harbors and supply-chain security hubs, and SI security and resilience. It does not describe binding obligations, funding, or deadlines, so the practical scope will depend on what those groups produce.

**「Impact」** AI hardware, software, and critical-infrastructure providers operating across the 10 signatories would face five separate government-led policy tracks—innovation rules, sector deployment, full-stack supply chains, safe harbors, and resilience—rather than a single harmonized rulebook. The declaration as summarized does not establish binding requirements, deadlines, or a compliance standard.

**Tags**: `#AI governance`, `#AI supply chain`, `#international policy`, `#superintelligence`, `#critical infrastructure`

---

<a id="item-tech-news-9"></a>
### [Amazon: Artex-driven AI agents stole API keys to fund model calls](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

Amazon says attackers used the open-source penetration-testing framework Artex to direct AI agents at internet-exposed AI applications such as LiteLLM and Dify, stealing API keys, validating them, and pooling them to pay for additional large-language-model calls. The campaign ran from October 3 to November 5 before Amazon&\#x27;s MadPot decoy network intercepted and disrupted it, according to the company. Amazon attributed the activity to a China-related threat group with medium confidence, said not all listed targets were compromised, and added that it has notified AWS customers that may have been affected. The account is Amazon&\#x27;s own disclosure and was not independently verified in the supplied material.

telegram · zaihuapd · Nov 16, 13:00

**「Background」** LiteLLM is a gateway that exposes one API to more than 100 model providers and manages API keys and budgets, while Dify is a visual platform for building LLM applications. Because such deployments need upstream model credentials to function, internet-exposed instances can become a route for attackers to steal those keys.

**「Impact」** For operators of internet-exposed LiteLLM or Dify deployments, the practical consequence is that API keys and the model quota they fund should be treated as at risk until access logs rule out theft, and keys should be rotated and public endpoints restricted. LiteLLM is widely deployed—95 million monthly PyPI downloads—and has recently had critical flaws that let low-privilege users steal AI provider API keys, so a single exposed gateway can put credentials well beyond one application at risk.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.litellm.ai/">LiteLLM documentation | liteLLM</a></li>
<li><a href="https://www.youtube.com/watch?v=-RdhQcD5lQw">Create Your First AI Agent in Minutes with Dify . ai - YouTube</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-litellm-ai-gateway-critical-vuln-chain-202/">LiteLLM AI Gateway: Critical Vulnerability Chain Exposes API ...</a></li>
<li><a href="https://www.itpro.com/security/cyber-attacks/litellm-flaws-allow-full-admin-control-and-api-key-theft">LiteLLM flaws allow full admin control and API-key theft</a></li>

</ul>
</details>

**Tags**: `#AI代理`, `#网络安全`, `#API密钥`, `#威胁情报`, `#云安全`

---

<a id="item-tech-news-10"></a>
### [US extends AI chip export controls to remote access](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 7.0/10

The US Commerce Department issued an interim final rule on November 16 extending export controls on advanced AI chips and servers to remote access, closing a route through third-country data centers that let users operate restricted hardware without importing it. According to The Verge, the rule also requires licenses for re-exporting AI chips to Indonesia, Malaysia, Singapore, Thailand and Brazil. The source says the measure, drafted with Treasury and National Security Council involvement, is intended to further tighten China&\#x27;s access to advanced chips, but it gives no effective date, license criteria, or the chip performance thresholds covered.

telegram · zaihuapd · Nov 16, 14:44

**「Background」** US advanced-AI-chip export controls have focused on physical shipments and re-exports of chips and servers, administered by the Commerce Department&\#x27;s Bureau of Industry and Security. Because access through foreign data centers did not itself require moving controlled hardware across a border, remote compute could fall outside that licensing framework—the gap the new interim final rule is meant to close.

**「Compliance impact」** Cloud and data-center operators that provide remote access to covered advanced AI chips will have to treat those services as licensable exports, and exporters or reexporters sending covered chips to or within Indonesia, Malaysia, Singapore, Thailand and Brazil will need BIS licenses under the interim final rule. Operators should audit third-country access paths and customer locations; without a license, they may need to block affected remote sessions or reroute workloads.

<details><summary>References</summary>
<ul>
<li><a href="https://media.bis.gov/sites/default/files/documents/BIS+Issues+Rule+Addressing+Remote+Access+to+American+Super+Intelligence+Technology.pdf">BUREAU OF INDUSTRY AND SECURITY - media.bis.gov</a></li>
<li><a href="https://www.unite.ai/bis-releases-rule-targeting-remote-access-to-advanced-ai-chips/">BIS Releases Rule Targeting Remote Access to Advanced AI Chips</a></li>
<li><a href="https://www.datacenterdynamics.com/en/news/us-dept-of-commerce-issues-rule-to-restrict-remote-access-to-advanced-ai-chips/">US Dep’t of Commerce issues rule to restrict remote access to ...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#US export controls`, `#remote access`, `#semiconductors`, `#tech policy`

---

<a id="item-tech-news-11"></a>
### [Alibaba, Tencent, Moonshot Reportedly Limit Cyber Capabilities in New Models](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 7.0/10

Alibaba, Tencent and Moonshot have reportedly weakened offensive cyber capabilities in their latest models while improving defensive performance, according to Bloomberg. Alibaba&\#x27;s newest flagship Qwen model is not being released with open weights, so users cannot download or customize the full version. The shift comes as China&\#x27;s Commerce Ministry has proposed export-control rules that would bar exports of AI tools capable of attacking critical infrastructure or government networks; Tencent reportedly cut cyber features before this month&\#x27;s Hy4 launch.

telegram · zaihuapd · Nov 17, 02:20

**「Background」** China’s Commerce Ministry has proposed export controls that would bar AI tools capable of attacking critical infrastructure or government networks from being exported, the policy backdrop for these model changes. An October 21 report described how the draft rules left China’s open-weight AI releases facing uncertainty as Beijing balanced security concerns against its competitive position.

**「Impact」** The closed release means users who need to download and customize Alibaba&\#x27;s full flagship Qwen model cannot do so; teams planning on open-weight access should treat the latest flagship as unavailable for that workflow.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/10/21/world/asia/china-exports-ai-controls.html">China ’s Free A . I . Models Are Thrown Into Uncertainty - The New York...</a></li>

</ul>
</details>

**Tags**: `#Chinese AI`, `#AI safety`, `#cyber capabilities`, `#export controls`, `#open-weight models`

---

<a id="item-tech-news-12"></a>
### [Apple China App Store adds AIGC filing deadline of Jan. 31, 2027](https://www.ithome.com/1/028/158.htm) ⭐️ 7.0/10

Apple&\#x27;s App Store Connect for mainland China distribution now requires developers of apps with AIGC features to provide an AIGC service declaration and filing information, plus a security assessment certificate. New apps must comply immediately, while existing apps have until January 31, 2027, to supply the required details. Covered features include chatbots, image and video generation, and voice or face editing; apps using third-party technology must also upload authorization agreements and algorithm filing numbers. Apple&\#x27;s 2026 review guidelines include generative AI provisions.

telegram · zaihuapd · Nov 17, 04:29

**「Background」** China&\#x27;s Interim Measures for the Management of Generative AI Services took effect on August 15, 2023, establishing filing and security-assessment obligations for providers of publicly available generative AI services. Later security requirements detailed expectations for corpus and model safety and assessment, and implementation analyses noted that services integrating third-party AIGC technology still fall under the rules—context for Apple&\#x27;s new AIGC declaration and filing fields.

**「Impact」** For developers, China-bound AIGC releases now require regulatory paperwork at submission time: teams using third-party models must obtain provider authorization and algorithm filing numbers, and existing apps need those details before the 2027 deadline.

<details><summary>References</summary>
<ul>
<li><a href="https://www.junhe.com/legal-updates/2243?locale=zh">《 生 成 式 人 工 智 能 服 务 管 理 暂 行 办 法 》正 式 施 行 ，框定我 国 AIGC 监 管 思路</a></li>
<li><a href="https://www.lexology.com/library/detail.aspx?g=c6345e61-b209-4dac-8b8c-3c5af2673ae6">《 生 成 式 人 工 智 能 服 务 安 全 基本要求》出台 -- 为 AIGC ... - Lexology</a></li>
<li><a href="https://www.secrss.com/articles/56640">《 生 成 式 人 工 智 能 服 务 管 理 暂 行 办 法 》发布，解析 AIGC ...</a></li>

</ul>
</details>

**Tags**: `#App Store`, `#AIGC compliance`, `#China regulation`, `#Apple`, `#developer policy`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Lutnick faces scrutiny over Cantor Fitzgerald&\#x27;s Nvidia ties](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

CNBC reported that Commerce Secretary Howard Lutnick is facing scrutiny over his sons’ firm Cantor Fitzgerald’s ties to Nvidia and a reported classified intelligence warning about CEO Jensen Huang, while Cantor’s reported Nvidia share count fell 49% between September 2025 and March 2026. Axios reported that Lutnick resisted pressure to crack down on Megaspeed, a Singapore-based company suspected of funneling Nvidia chips to China.

rss · CNBC Finance · Nov 16, 12:14

**「Background」** Cantor Fitzgerald is the Wall Street firm Howard Lutnick ran before becoming commerce secretary in February 2025; it is now led by his sons, and Commerce administers the entity list, which would restrict exports to Singapore-based Megaspeed.

**「Impact」** Commerce&\#x27;s unresolved entity-list review leaves Megaspeed, a Singapore-based Nvidia customer, facing possible U.S. export restrictions that would limit its access to advanced AI chips and, by extension, Nvidia&\#x27;s sales through that channel.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/16/nvidia-commerce-china-lutnick.html">Nvidia fallout: Commerce targets loophole for China &#x27;s data center use</a></li>
<li><a href="https://www.npr.org/2026/11/14/nx-s1-6040379/commerce-department-under-pressure-for-delaying-export-controls-on-nvidia-chips">Commerce Department under pressure for delaying export ...</a></li>
<li><a href="https://www.axios.com/2026/11/11/bessent-lutnick-megaspeed-nvidia-china-chips">Bessent confronted Lutnick over Nvidia customer Megaspeed ...</a></li>
<li><a href="https://tradersunion.com/news/regulators/show/4187833-us-delays-megaspeed-blacklist-chips/">U.S. commerce department delays Megaspeed blacklist move amid ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#China export controls`, `#conflict of interest`, `#Commerce Department`, `#semiconductor smuggling`

---

<a id="item-finance-news-2"></a>
### [Nvidia CEO Jensen Huang resigns as shares slide; Yorkville Ives cuts price target but keeps buy rating](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 7.0/10

Nvidia founder and CEO Jensen Huang has resigned, and the chipmaker closed the week at $162.85 a share after its longest losing streak since 2012. Yorkville Ives cut its price target on Nvidia to $225 from $300 on Thursday but kept a buy rating, with analyst Dan Ives arguing the company remains roughly 2-3 years ahead of its nearest competitor in AI chips.

rss · CNBC Finance · Nov 16, 12:13

**「Background」** Nvidia’s board announced on Nov. 12, 2026, that co-founder Jensen Huang had resigned as CEO and director, naming CFO Colette Kress interim chief executive, after reports of extramarital affairs. Nvidia has been the dominant supplier of data-center AI chips, with roughly three quarters of AI GPU revenue in 2026, so a leadership crisis at the company can unsettle the broader AI trade.

**「Impact」** In a CNBC &quot;ETF Edge&quot; interview recorded before the resignation was announced, ETF managers said that if investors lose trust in Nvidia, demand could shift to other chip suppliers and large cloud-owning tech companies; AMD rose nearly 13% and Broadcom posted similar gains over the week.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bbc.com/news/live/c6zjry11v8w1t">Huang agrees to appear before Congress, US lawmakers... - BBC News</a></li>
<li><a href="https://www.nytimes.com/live/2026/11/12/business/nvidia-jensen-huang-resigns">Nvidia Updates: Huang ’s Resignation Reverberates Through...</a></li>
<li><a href="https://www.gate.com/blog/jensen-huang-resigns-is-nvda-stock-still-a-good-investment">Jensen Huang Resigns : Is NVDA Stock Still a Good... | Gate Blog</a></li>
<li><a href="https://commandlinux.com/statistics/ai-gpu-market-share-nvidia-vs-amd-vs-intel/">AI GPU Market Share NVIDIA vs AMD vs Intel: 2026 Statistics</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI trade`, `#ETFs`, `#semiconductors`, `#data centers`

---

<a id="item-finance-news-3"></a>
### [Intel and CEO Lip-Bu Tan sued in shareholder class action](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

Intel and CEO Lip-Bu Tan face a shareholder class action alleging the company concealed weak PC demand and inventory buildup before its October 29, 2026 fourth-quarter revenue and profit forecast fell short of expectations, sending shares down 28.6% the next day and erasing about $140 billion in market value. The suit, led by a Michigan pension fund and filed Friday in federal court in San Jose, covers investors who bought shares between July 23 and October 29, 2026, and also names CFO Zinsner as a defendant.

telegram · zaihuapd · Nov 16, 11:10

**「Background」** A shareholder class action is a lawsuit brought on behalf of investors who bought shares during a specified period; this suit follows Intel’s Oct. 29, 2026 fourth-quarter revenue and profit forecast that missed expectations and a 28.6% share drop the next day, and covers purchases from July 23 to Oct. 29, 2026.

**「Affected shareholders」** Investors who bought Intel shares between July 23 and October 29, 2026 fall within the proposed class and could seek damages if the suit is certified; the fraud allegations are unproven.

<details><summary>References</summary>
<ul>
<li><a href="https://wccftech.com/intel-ceo-lip-bu-tan-named-defendant-class-action-lawsuit-pc-sales-slowdown/">Intel CEO Lip - Bu Tan Named As Defendant In New Class - Action ...</a></li>
<li><a href="https://www.reuters.com/business/intel-sued-by-shareholders-following-29-stock-plunge-2026-11-15/">Intel sued by shareholders following 29% stock plunge | Reuters</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#shareholder class action`, `#stock plunge`, `#PC demand`, `#earnings guidance`

---