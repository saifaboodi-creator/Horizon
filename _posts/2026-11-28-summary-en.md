---
layout: default
title: "Horizon Summary: 2026-11-28 (EN)"
date: 2026-11-28
lang: en
---

> From 30 items, 10 important content pieces were selected

---

**Technology News**
1. [OpenSec reports pre-auth root flaw in Linux nfsd, CVSS 9.8](#item-tech-news-1) ⭐️ 8.0/10
2. [Google Research claims DeepCrossAttention is up to 3x faster at similar quality](#item-tech-news-2) ⭐️ 7.0/10
3. [Convex skills issue alleges undisclosed app-idea upload](#item-tech-news-3) ⭐️ 7.0/10
4. [WebRTC-based card skimming scripts found on shopping sites](#item-tech-news-4) ⭐️ 7.0/10
5. [State attorneys general sue SpaceX over Grok&\#x27;s sexual abuse imagery](#item-tech-news-5) ⭐️ 7.0/10
6. [Essay argues computer-checked proofs can be false due to checker bugs](#item-tech-news-6) ⭐️ 7.0/10
7. [Minecraft Bedrock resource-pack flaw 26.52–26.63 fixed in 26.65](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [China State Council urges stronger &\#x27;national team&\#x27; market support, optimized Central Huijin stabilization-fund role](#item-finance-news-1) ⭐️ 8.0/10
2. [Mixue subscribes 500 million yuan in DeepSeek’s reported 100–105.5 billion yuan round](#item-finance-news-2) ⭐️ 7.0/10
3. [PBOC Cuts Large-Denomination CD Purchase Thresholds for Individuals to 100,000 Yuan](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenSec reports pre-auth root flaw in Linux nfsd, CVSS 9.8](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec published an advisory for CVE-2026-99362, a pre-authentication heap overflow in the Linux kernel&\#x27;s nfsd server that it rates CVSS 9.8. According to the report, a single connection to tcp/2049 causes an out-of-bounds write to the kernel heap that can be leveraged into a root shell without any login. The flaw is said to have existed since Linux 3.16 in 2014 and to affect hosts with NFSv4.1 or 4.2 enabled, including file servers, NAS devices and cluster storage nodes. The report lists fixes in kernels 6.12.117, 6.18.61, 7.3.2 and 7.4-rc1, and states the CVE was made public on 20 November 2026.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** For NFSv4.1 and 4.2, nfsd keeps a session reply cache for compound requests, and that cache is where CVE-2026-99362 resides. Red Hat&\#x27;s record says a remote client can trigger the out-of-bounds write by negotiating a minimal cached reply size and sending crafted compound requests containing SEQUENCE operations; OpenCVE describes the fix as an updated sequence buffer bounds check. The kernel CNA scored the flaw 9.8 and Red Hat scored it 9.4.

**「Impact」** Closing the flaw requires installing one of the listed kernel versions and rebooting; for administrators who cannot upgrade immediately, the only mitigation the advisory offers is blocking access to tcp/2049 at the firewall, which also cuts legitimate NFSv4.1/4.2 clients off from the server. Triage should therefore start with hosts that actually run NFSv4.1 or 4.2, since the report scopes exposure to those protocol versions.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://app.opencve.io/cve/CVE-2026-99362">CVE-2026-99362 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://computingforgeeks.com/nfs2root-cve-2026-99362/">NFS2ROOT (CVE-2026-99362): Check, Patch, Mitigate ...</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#NFS`, `#security vulnerability`, `#CVE-2026-99362`, `#remote exploitation`

---

<a id="item-tech-news-2"></a>
### [Google Research claims DeepCrossAttention is up to 3x faster at similar quality](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 7.0/10

Google Research published a blog post, &quot;Supercharging Transformer Residual Connections,&quot; presenting DeepCrossAttention, a transformer technique that alters attention and residual connections and, according to the company, matches baseline model quality while running up to 3x faster. The figure is a vendor claim from Google&\#x27;s own post; the supplied material contains no independent benchmark, and no details on model sizes, hardware, training versus inference settings, or the baselines compared. Treat the speedup as unverified until reproducible measurements appear.

hackernews · ComputedCamp995 · Nov 27, 23:06 · [Discussion](https://news.ycombinator.com/item?id=50672565)

**「How DCA changes residual connections」** Transformer residual connections normally combine a layer&\#x27;s output with an earlier representation through a fixed skip path. DeepCrossAttention replaces that fixed path with learnable weights and depth-wise cross-attention that combine outputs from previous layers, an approach intended to prevent information dilution. Google Research says the method was presented at ICML 2025 and was described on its blog by Kyriakos Axiotis and Thomas Fu.

**「What changes for implementers」** Adopting DCA means replacing fixed residual summation with learnable, per-token routing that mixes outputs from every earlier layer, so the practical cost is extra cross-attention machinery rather than a drop-in kernel swap. Google&\#x27;s reported LM1B result — a 30-layer DCA model matching the perplexity of a 42-layer baseline while adding under 0.2% parameters — frames the payoff as depth and training-time savings, and the supplied material contains no independent reproduction or memory-overhead figures for teams evaluating it.

**「Community discussion」** One commenter objected to the post&\#x27;s charts, arguing the compared methods should be shown as bar charts rather than line graphs because there is no temporal relationship between them. Another reader asked whether the method could be combined with speculative-decoding derivatives such as MTP and Dflash, which they said had already given them 10x tokens/sec over the past two years, to reach 30x — a speculative question, not a measured result.

<details><summary>References</summary>
<ul>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention: Supercharging Transformer ...</a></li>
<li><a href="https://aiweekly.co/alerts/googles-deepcrossattention-trains-transformers-up-to-3x-faster">Google&#x27;s DeepCrossAttention trains transformers up to 3x faster</a></li>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://explainx.ai/blog/google-deepcrossattention-transformer-residual-connections-2026">DeepCrossAttention (DCA): Google Fix for Deep Transformers ...</a></li>
<li><a href="https://aiweekly.co/alerts/googles-deepcrossattention-trains-transformers-up-to-3x-faster">Google&#x27;s DeepCrossAttention trains transformers up to 3x ...</a></li>

</ul>
</details>

**Tags**: `#transformers`, `#attention mechanisms`, `#model efficiency`, `#Google Research`, `#deep learning`

---

<a id="item-tech-news-3"></a>
### [Convex skills issue alleges undisclosed app-idea upload](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

A GitHub issue in the convex-backend-skill repository alleges that Convex&\#x27;s skills plugin sends users&\#x27; app ideas to a remote server without clearly disclosing the upload. Convex CEO Jamie responded that the prompt upload powers the Convex quickstart feature, which he described as the spiritual successor to the recently shut-down Convex Chef, and said Convex stores customer data and code and operates an AI gateway. The thread does not establish that the transfer was intentionally hidden or quantify how many users were affected.

hackernews · MickyTheMouse · Nov 27, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50669765)

**「Background」** The disputed upload is part of \`convex-quickstart\`, a skill intended to get a barebones Convex + web template running from a one-sentence idea. It follows Convex Chef, an earlier browser-based product that generated an app—with a Convex backend, authentication, and realtime UI—from a description; Convex&\#x27;s CEO says Chef was recently shut down and that quickstart is its successor.

**「Impact」** Developers using Convex&\#x27;s quickstart feature should treat prompts as data sent off-device unless product documentation says otherwise, because the CEO&\#x27;s response confirms the prompt upload but does not describe retention or disclosure controls. Teams evaluating the plugin may need to verify what is transmitted and how it is handled before using it with sensitive app ideas.

**「Community discussion」** Commenters focused on trust and control: one argued that self-hosted open-weight models are the better long-term path, while another noted that prompt injection is more common than models making malicious tool calls on their own, without asserting malice in this case. The comments did not reach a consensus on how the upload should be governed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.convex.dev/examples/chef">Chef - convex.dev</a></li>
<li><a href="https://www.skills.sh/convex/agent-skills/convex-quickstart">convex-quickstart — convex/agent-skills</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#security`, `#AI coding tools`, `#Convex`, `#data handling`

---

<a id="item-tech-news-4"></a>
### [WebRTC-based card skimming scripts found on shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

A security report describes credit-card skimming scripts that abuse WebRTC on popular shopping sites and are used to evade detection. The report highlights third-party script risk on e-commerce pages. The supplied material does not name the affected sites, the scripts, or any mitigation.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「Prior skimming campaigns and script controls」** Card-skimmer campaigns that inject malicious JavaScript into checkout pages have hit e-commerce sites repeatedly; one BleepingComputer report described scripts harvesting card number, expiry date, card type, CVV and cardholder details from more than 200 college campus stores \[tool-2-1\]. PCI DSS requirements 6.4.3 and 11.6.1 now require payment-page scripts to be authorized, checked for integrity and monitored for tampering, a control driven partly by third-party compromises such as the Optimizely incident \[tool-2-3\].

**「Impact」** For merchants, the reported attack path makes third-party scripts on e-commerce pages a concrete security concern; the supplied material does not identify affected stores or provide mitigation details.

**「Community discussion」** Commenters disagreed over whether this is a WebRTC-specific flaw or a broader third-party script problem; afavour argued the same approach could use simple HTTP requests and that embedding third-party scripts leaves sites vulnerable. Others cited the report as justification for ad blocking and asked why ad providers or browsers do not sandbox third-party JavaScript.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/over-200-college-campus-stores-infected-with-card-stealing-scripts/">Over 200 College Campus Stores Infected with Card Stealing Scripts</a></li>
<li><a href="https://origami.sa/en/blog/third-party-script-card-skimming-checkout/">Optimizely Hack: An Outside Tool Planted a Card Skimmer on 178...</a></li>

</ul>
</details>

**Tags**: `#web security`, `#payment skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-5"></a>
### [State attorneys general sue SpaceX over Grok&\#x27;s sexual abuse imagery](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

A coalition of state attorneys general has sued SpaceX, naming it as parent company of xAI and its Grok chatbot, alleging the platform enabled the creation and promotion of child sexual exploitation material and non-consensual intimate images. The suit was announced in a release attributed to attorneys general Jay Jones and Rayfield and targets Grok&\#x27;s image generation. The supplied material provides no technical detail on which safeguards failed, no count of participating states, and no specific remedy sought, and the allegations have not been adjudicated.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「Background」** Grok is xAI&\#x27;s generative AI product, and the suit names SpaceX as the parent company of xAI and Grok while also targeting X. Virginia Attorney General Jay Jones filed the action alongside a separate but similar Oregon suit by Attorney General Dan Rayfield; both seek civil penalties and injunctions to stop Grok and X from creating or distributing non-consensual sexualized images, including CSAM.

**「Who bears the exposure」** The immediate burden falls on the company rather than on individual users: the complaint names SpaceX as the parent of xAI and Grok, so the case turns first on corporate-structure and platform-liability questions before it reaches any specific generated image. For teams shipping image-generation features, the underlying legal standard is not settled — federal courts have addressed whether private possession of AI-generated child sexual abuse material is constitutionally protected speech, with at least one analysis drawing the line at distribution rather than possession. Because this is a filed complaint and not a ruling, no new compliance obligation is binding yet, and the technical question the filing raises — whether Grok&\#x27;s safeguards could be bypassed by ordinary prompts or only by deliberate circumvention, as commenters asked — is not resolved by the supplied material.

**「Community discussion」** Commenters pressed on how the outputs were obtained, with one asking whether Grok was permissive by default or whether users had to trick it, and another asking whether the people generating the material would face consequences. A third commenter asserted that the Supreme Court has already ruled that AI-generated child sexual abuse material made for personal consumption is protected speech, a claim the supplied material does not substantiate.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform">Attorneys General Jones and Rayfield File Suit Against SpaceX ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/23/oregon-virginia-spacex-grok-deepfake-lawsuits.html">SpaceX sued by 2 states over AI deepfake porn, Grok ... - CNBC</a></li>
<li><a href="https://www.doj.state.or.us/media-home/news-media-releases/ag-rayfield-takes-legal-action-against-grok-for-failing-to-block-child-exploitation/">Oregon Attorney General Rayfield and Virginia Attorney ...</a></li>
<li><a href="https://nordicresistancemovement.org/seventh-circuit-rules-ai-generated-child-pornography-possession-is-constitutionally-protected/">Seventh Circuit Rules AI - Generated Child Pornography Possession Is...</a></li>
<li><a href="https://getcoai.com/news/court-ruling-ai-generated-child-sexual-abuse-images-protected-for-private-possession-not-distribution/">Court ruling : AI - generated child sexual abuse images protected for...</a></li>

</ul>
</details>

**Tags**: `#ai-safety`, `#content-moderation`, `#regulation`, `#grok`, `#generative-ai`

---

<a id="item-tech-news-6"></a>
### [Essay argues computer-checked proofs can be false due to checker bugs](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

An essay titled &quot;False computer-checked proofs&quot; argues that a proof accepted by a software checker can still be false when the checker has a soundness bug, so &quot;computer-checked&quot; is not by itself an unconditional guarantee of correctness. The Hacker News discussion focuses on formal verification and proof assistants such as Lean and Metamath, and on whether one checker&\#x27;s acceptance is enough to trust a result.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「Background」** Proof checkers are programs that validate each step of a formal proof; a soundness bug in the checker can cause it to accept an invalid proof, so “computer-checked” is only as trustworthy as the checker. Bernstein’s page collects reported soundness bugs in seven proof-checking systems—HOL Light, Mizar, Metamath, Isabelle, Lean, HOL98/HOL4, and Coq/Rocq—and links to the underlying reports.

**「Impact」** For formal-verification users, the practical consequence is that acceptance by a single proof checker should not be treated as absolute assurance; the discussion points to using multiple independently implemented checkers, as Metamath&\#x27;s main databases do, to reduce the risk that one soundness bug certifies a false proof.

**「Community discussion」** Commenters push back on the essay&\#x27;s framing: twotwotwo and dwheeler argue that systems requiring multiple provers reduce the risk, with dwheeler noting that Metamath&\#x27;s set.mm and iset.mm require five independently created verifiers in five programming languages, and twotwotwo citing a case where a DeepMind researcher passed Lean and a then-week-old nanoda by exploiting a different bug in each. gr\_norm contends that known soundness bugs are rare enough for most software, while andai raises a separate concern that an agent can prove a formal statement that encodes its own incorrect understanding of the requirement.

<details><summary>References</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb) - cr.yp.to</a></li>
<li><a href="https://news.lavx.hu/article/d-j-bernstein-catalogs-soundness-bugs-in-seven-proof-checkers">D. J. Bernstein catalogs soundness bugs in seven proof ...</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-7"></a>
### [Minecraft Bedrock resource-pack flaw 26.52–26.63 fixed in 26.65](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

A resource-pack flaw in Minecraft Bedrock Edition let packs containing a content.zipe file modify files in the Ore UI interface framework and run hidden scripts, according to add-on developer 8Crafter, who disclosed the issue on Reddit on November 15. The developer said it is confirmed to affect versions 26.52 through 26.63, with earlier versions possibly affected as well, across PC, mobile, and console; Java Edition is not affected. Mojang has fixed the flaw in version 26.65.

telegram · zaihuapd · Nov 27, 18:04

**「Background」** Bedrock&\#x27;s Ore UI interface layer is built with React and TypeScript; a resource pack containing a content.zipe file could alter files in that layer and run hidden scripts. Add-on developer 8Crafter publicly described the flaw on Reddit on November 15, 2026, and Minecraft Wiki records the 26.65 fix as a hotfix released the following day.

**「Impact」** Players who join servers or Realms with automatic resource-pack downloads enabled could receive an affected pack without installing anything manually. The exploits cited by 8Crafter include deleting all saves and obtaining a player&\#x27;s IP address, and on Windows under specific conditions silently opening arbitrary URIs or launching a batch file inside the pack to download malware. AxmBro published a Windows read-only detection tool that finds content.zipe files but cannot determine whether a pack is actually malicious.

<details><summary>References</summary>
<ul>
<li><a href="https://minecraft.wiki/w/Bedrock_Edition_26.65">Bedrock Edition 26.65 – Minecraft Wiki</a></li>
<li><a href="https://www.minehour.com/en/blog/minecraft-bedrock-26-65-fixes-flaw-in-resource-packs">Minecraft Bedrock 26.65 fixes flaw in resource packs</a></li>

</ul>
</details>

**Tags**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#Ore UI`, `#game security`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China State Council urges stronger &\#x27;national team&\#x27; market support, optimized Central Huijin stabilization-fund role](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

A State Council executive meeting chaired by Premier Li Qiang on Nov. 27 called for greater use of the &quot;national team&quot; to steady the stock market and for further optimizing Central Huijin&\#x27;s quasi &quot;stabilization fund&quot; function, according to a TMTPost report on the meeting. The meeting also asked listed companies to increase dividends and buybacks and urged better policies to channel long-term funds such as insurance, enterprise annuity and social security money into equities, without giving figures or implementation details.

telegram · zaihuapd · Nov 27, 05:35

**「Background」** Central Huijin is a state-owned investor that holds the government&\#x27;s stakes in major Chinese financial institutions, and it has been used as part of the &quot;national team&quot; of state buyers that steps into equities to steady prices; a &quot;quasi-stabilization fund&quot; is a state vehicle meant to support the market when it falls. An expert quoted by Eastmoney said the meeting&\#x27;s wording signalled that this China-style stabilization mechanism was being upgraded from a temporary crisis-response tool to a standing part of financial governance.

**「Who is affected」** The measures, if implemented, would most directly affect insurers, corporate annuity plans and the national social security fund — the long-term investors named for expanded market entry — while listed companies would face the push for higher dividends and buybacks and tighter enforcement against financial fraud and irregular share sales; the source gives no figures or timetable.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611273941634358.html">如何理解 国 常会对资本 市 场的最新定调？ 专 家 解读来了 _ 东方财富网</a></li>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>
<li><a href="https://finance.eastmoney.com/a/202611273941564045.html">finance.eastmoney.com/a/202611273941564045.html</a></li>

</ul>
</details>

**Tags**: `#China capital markets`, `#State Council`, `#Central Huijin`, `#market stabilization`, `#long-term funds`

---

<a id="item-finance-news-2"></a>
### [Mixue subscribes 500 million yuan in DeepSeek’s reported 100–105.5 billion yuan round](https://m.sohu.com/a/1107027659_115479) ⭐️ 7.0/10

DeepSeek reportedly completed a second funding round of 100–105.5 billion yuan at a post-money valuation of about 615.5 billion yuan, according to a Sohu report that cited no original announcement. Mixue Ice Cream &amp; Tea subscribed 500 million yuan through a fund, one of 31 new investors that the report said also include Tencent, CATL, China Mobile and vivo.

telegram · zaihuapd · Nov 27, 06:33

**「Background」** The round follows DeepSeek&\#x27;s first financing, which The Information reported raised more than 500亿元 \(about $7.4 billion\), according to 36Kr.

<details><summary>References</summary>
<ul>
<li><a href="https://eu.36kr.com/zh/p/3856984071027329">DeepSeek 成功揽下500 亿</a></li>

</ul>
</details>

**Tags**: `#DeepSeek融资`, `#蜜雪冰城`, `#AI投资`, `#私募股权`, `#估值`

---

<a id="item-finance-news-3"></a>
### [PBOC Cuts Large-Denomination CD Purchase Thresholds for Individuals to 100,000 Yuan](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

China&\#x27;s central bank published new rules on November 27 that lower the minimum purchase amount for large-denomination certificates of deposit to 100,000 yuan for individual investors and 5 million yuan for institutional investors, half the previous thresholds of 200,000 and 10 million yuan, with the rules taking effect March 21, 2027. The same day, the PBOC issued deposit and loan rate rules, also effective March 21, 2027, requiring financial institutions to set rates independently and barring improper practices such as attracting deposits with high interest.

telegram · zaihuapd · Nov 27, 11:36

**「Background」** The new rules replace interim 2015 rules that had set the individual and institutional minimums at 200,000 yuan and 10 million yuan, meaning both thresholds are halved.

**「Who is affected」** Retail savers holding between 100,000 and 200,000 yuan can now qualify for large-denomination certificates of deposit — products that generally advertise higher yields than ordinary time deposits — while banks gain a wider funding channel, still barred under the same package from luring depositors with above-market rates.

<details><summary>References</summary>
<ul>
<li><a href="https://t.me/linux_do_channel/582077">LINUX DO Channel – Telegram</a></li>
<li><a href="https://news.qq.com/rain/a/20260317A05VOS00">同样是 存 10 ...</a></li>
<li><a href="https://www.chinanews.com.cn/cj/2026/08-14/10677694.shtml">五年期 大 额 存 单 售罄 低风险资金抢 购 潮传递什么信号-中新网</a></li>

</ul>
</details>

**Tags**: `#PBOC regulation`, `#large-denomination CDs`, `#deposit rates`, `#retail banking`, `#China monetary policy`

---