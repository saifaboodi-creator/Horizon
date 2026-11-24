---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 38 items, 11 important content pieces were selected

---

**Technology News**
1. [Ladybird releases first alpha for macOS and Linux](#item-tech-news-1) ⭐️ 8.0/10
2. [Z.ai releases GLM-5.4, its first looped-transformer coding model](#item-tech-news-2) ⭐️ 8.0/10
3. [Anthropic posts claimed AI-discovered VP ≠ VNP Lean 4 proof](#item-tech-news-3) ⭐️ 8.0/10
4. [Unofficial Arm documentation site to close after Arm request](#item-tech-news-4) ⭐️ 7.0/10
5. [Codex2api 3.1.10–3.1.12 suspected supply-chain compromise](#item-tech-news-5) ⭐️ 7.0/10
6. [Claude-Assisted Riemann Hypothesis &\#x27;Proof&\#x27; Unravels Over Vacuous Lean Code](#item-tech-news-6) ⭐️ 7.0/10
7. [HarmonyOS 5–7 devices pass 100 million; apps top 460,000](#item-tech-news-7) ⭐️ 7.0/10
8. [Singapore Says It Won’t Be a Conduit for US Chip Controls](#item-tech-news-8) ⭐️ 7.0/10

**Technology Blog**
1. [ERNIE 5.5 Flash Preview Arrives on vLLM as a Plugin](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [AI Selloff Clouds Planned Listings by DeepSeek and Moonshot](#item-finance-news-1) ⭐️ 7.0/10
2. [Shanghai Metro to Adjust Fares for First Time in 21 Years](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Ladybird releases first alpha for macOS and Linux](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird has released its first alpha, with installable builds for macOS and Linux so users no longer need to compile the from-scratch browser themselves. It implements most core browser components in-house—HTML parsing, CSS, layout, JavaScript and WebAssembly—while relying on external HarfBuzz, Skia, ffmpeg and SQLite. The project warns that some sites will not work and the browser will sometimes crash; a tester found service-worker support incomplete enough to break Datasette Lite.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Prior context」** Ladybird grew out of the SerenityOS project, and until this release the only way to run it was to compile it yourself; the alpha is its first downloadable build for macOS and Linux. Earlier in 2026 the project began porting parts of its LibJS engine from C++ to Rust with the help of AI coding agents, and its October 2026 project newsletter reported a new JavaScript JIT, a rewritten Cranelift-based WebAssembly engine roughly 7x faster on the JetStream 3 WASM benchmark, and about 75,650 additional web-platform-tests passes, mostly from pointing coding agents at missing functionality.

**「Impact」** For macOS and Linux users, the alpha provides a no-compile way to test an independent engine against real sites, with in-browser broken-site reporting and opt-in crash reports feeding back to the project. It is not yet a dependable daily driver: the release notes warn of site failures and crashes, and the service-worker gap shows that some web-app APIs remain incomplete.

**「Community discussion」** Commenters reported that a range of sites rendered correctly, with one saying the Proxmox NoVNC interface felt snappier than in Firefox, though another flagged noticeably jerky page scrolling. A separate commenter urged Ladybird to prioritize anti-fingerprinting measures such as spoofed or randomized JavaScript values and more granular permissions.

**Tags**: `#Ladybird`, `#browser-engine`, `#open-source`, `#alpha-release`, `#web-compatibility`

---

<a id="item-tech-news-2"></a>
### [Z.ai releases GLM-5.4, its first looped-transformer coding model](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai released GLM-5.4, which it describes as its first model built on a looped-transformer architecture: a group of weight-shared layers runs for multiple iterations, increasing effective depth without increasing parameter count. The model is not available as open weights and is currently reachable through Z.ai&\#x27;s Coding Plan subscription rather than the regular API; the post says Coding Plan keys work with the shared OpenAI-compatible endpoint at https://api.z.ai/api/v1. The post&\#x27;s hands-on test found GLM-5.4&\#x27;s pelican SVG outputs similar in quality to GLM-5.3&\#x27;s, while Z.ai&\#x27;s generalized-coding claims remain vendor assertions without independent benchmarks.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「Background」** In a standard Transformer, each layer runs once per forward pass; a looped transformer instead runs a group of weight-shared layers through multiple iterations, increasing effective depth without increasing the parameter count. Z.ai&\#x27;s documentation says GLM-5.4 implements this by reusing 28 layers of the GLM-5 base model across two iterations.

**「Access requires the Coding Plan」** Developers who want to try GLM-5.4 cannot reach it through Z.ai&\#x27;s regular API plan or via OpenRouter, and the model is not \(yet\) available as open weights, so access currently requires a GLM Coding Plan subscription. Because Coding Plan keys work against the same OpenAI-compatible Responses API at https://api.z.ai/api/v1 as regular keys, existing OpenAI-format clients and plugins can point at the new model without code changes — as Simon Willison did when building his llm-glm plugin. Independent benchmarks and published API pricing were still absent at launch, so capability claims remain vendor-stated.

**「Community discussion」** Commenters welcomed Z.ai&\#x27;s comparatively detailed technical disclosure and described looped transformers as a natural direction even though unresolved problems remain. One user reported that Chinese models&\#x27; long &quot;marathon thinking&quot; sessions make even conceptually simple tasks slow and frustrating, with completion times much higher than frontier models unless throughput is unusually high.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.z.ai/guides/llm/glm-5.4">GLM-5.4 - Overview - Z.AI DEVELOPER DOCUMENT</a></li>
<li><a href="https://www.orcarouter.ai/blog/glm-5-4-release-what-we-know">GLM - 5 . 4 Arrives on Z.ai&#x27;s Coding Plan: No Benchmarks Yet</a></li>

</ul>
</details>

**Tags**: `#LLM`, `#looped transformers`, `#GLM-5.4`, `#coding models`, `#Zhipu AI`

---

<a id="item-tech-news-3"></a>
### [Anthropic posts claimed AI-discovered VP ≠ VNP Lean 4 proof](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic has released a paper titled “VP ≠ VNP over every field” and a Lean 4 formalization in its formal-math repository, saying an internal research Claude model discovered the result and wrote both the paper and code. The claimed theorem gives a superpolynomial arithmetic-circuit lower bound for the Hamilton cycle polynomial and concludes that VP is a proper subclass of VNP, which would settle Valiant’s 1979 algebraic complexity conjecture; it concerns arithmetic circuits only, not P versus NP. The repository says an audit against three standard axioms and an independent nanoda kernel check found no “sorry” outside reserved files, but no human mathematician has reviewed the work, Lean cannot establish that the formal statement matches the claimed theorem, and Appendix Q lists discrepancies.

telegram · zaihuapd · Nov 24, 06:02

**「Background」** VP and VNP are the algebraic analogues of P and NP: VP collects polynomial families computable by polynomial-size arithmetic circuits, while VNP collects those expressible as exponential sums of VP-computable polynomials. Leslie Valiant introduced both classes in 1979 and conjectured that they differ, a question that has stayed open since — coverage of the Anthropic claim still described it as unresolved 47 years later. A separation requires proving that some VNP polynomial, such as the Hamiltonian-cycle polynomial, admits no polynomial-size arithmetic circuit; as external commentary on the paper notes, this is the algebraic analogue of P vs NP and does not settle that Boolean question.

**「Impact」** For complexity theorists and formal-verification researchers, the immediate consequence is a concrete Lean artifact that can be independently checked. Acceptance would require verifying that the formal statement matches the claimed theorem and resolving the discrepancies listed in Appendix Q, because a clean kernel check alone does not establish the mathematical claim.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=UuOiRi9T-9c">Claude&#x27;s VP VNP Proof: 47 Years Open, Still Unchecked... - YouTube</a></li>
<li><a href="https://www.alphaxiv.org/abs/2611.vp-vnp-arithmetic-lower-bounds">VP VNP Over Every Field | alphaXiv</a></li>

</ul>
</details>

**Tags**: `#AI for mathematics`, `#Lean 4`, `#computational complexity`, `#formal verification`, `#Anthropic`

---

<a id="item-tech-news-4"></a>
### [Unofficial Arm documentation site to close after Arm request](https://arm.jonpalmisc.com/) ⭐️ 7.0/10

The unofficial Arm documentation site arm.jonpalmisc.com will be discontinued on 4 December 2026 after Arm requested its removal, according to the site&\#x27;s operator. The operator said Arm cited his use of its trademarks and intellectual property in hosting the documentation, a constraint he described as difficult to work around while keeping the site useful. He said he is considering offers to host mirrors, seek legal advice, and release the source code without Arm IP so others could generate a similar site for personal use. No replacement or mirror has been confirmed.

hackernews · tech234a · Nov 23, 19:17 · [Discussion](https://news.ycombinator.com/item?id=50617499)

**「Background」** Arm&\#x27;s architecture is defined in the Arm Architecture Reference Manual, which Arm describes as the authoritative human-readable account of the instruction set; Arm also publishes machine-readable XML and corresponding JSON releases. The site being discontinued was an unofficial way to browse Arm documentation rather than an Arm-operated service, so the operator had to address Arm&\#x27;s trademark and IP concerns while trying to preserve a useful reference.

**「Impact」** Engineers who relied on this unofficial rendering of Arm&\#x27;s architecture documentation will need to use Arm&\#x27;s own documentation or another source after 4 December 2026. Because the operator has not confirmed a mirror or a sanitized source release, continuity of access is not assured.

**「Community discussion」** Commenters questioned whether Arm&\#x27;s trademark and IP complaint is sound, with one pointing to BSD-style licensing on versions of Arm&\#x27;s machine-readable specification and another comparing the site with an existing Stanford-hosted Arm64 reference. Others criticized the takedown as harmful to engineers working with Arm hardware, while the operator said mirror offers and a sanitized source release are being considered.

<details><summary>References</summary>
<ul>
<li><a href="https://support.arm.com/documentation/110173/2026-06/">Release notes for BSD license JSON in A profile architecture</a></li>
<li><a href="https://documentation-service.arm.com/static/6abbe7254c55541bd990dfe4">Release notes for BSD license JSON in A profile architecture</a></li>

</ul>
</details>

**Tags**: `#Arm`, `#documentation`, `#trademark/IP`, `#hardware`, `#community-discussion`

---

<a id="item-tech-news-5"></a>
### [Codex2api 3.1.10–3.1.12 suspected supply-chain compromise](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

A Telegram post reports that Codex2api&\#x27;s author account was compromised and that the attacker bypassed the main branch by pushing a tag, causing Release builds to include a backdoor. Versions 3.1.10–3.1.12 are reported as affected: v3.1.11 allegedly removed authentication, enabling unauthenticated remote command execution, while a workflow exfiltrated 16 GitHub Actions secrets and affected at least 21 repositories under the same account. Users who installed or updated to those versions are advised to stop using them immediately, roll back to 3.1.9, and rotate GitHub tokens, SSH keys, database credentials, DeepSeek keys, and all other related secrets.

telegram · zaihuapd · Nov 23, 11:21

**「Background」** Codex2api publishes releases built by GitHub Actions, so a pushed Git tag can trigger a release build without merging code to the main branch. That makes tag-push permissions and the release workflow part of the project&\#x27;s software supply chain: compromise of the author account can turn a tag into a backdoored build, and a workflow can expose repository secrets.

**「Remediation scope」** Anyone who installed or updated to 3.1.10–3.1.12 should stop using the tool, roll back to 3.1.9, and rotate GitHub tokens, SSH keys, database credentials and DeepSeek and other related secrets, since 3.1.11 removed authentication and exposed unauthenticated remote command execution. Because a workflow reportedly exfiltrated 16 Actions secrets and the compromise is said to reach at least 21 repositories under the same author account, credentials beyond the Codex2api repository itself should be treated as exposed. The report is a suspected incident relayed from a Telegram post, so the full blast radius remains unconfirmed.

**Tags**: `#supply-chain security`, `#GitHub Actions`, `#remote code execution`, `#secrets management`, `#open source security`

---

<a id="item-tech-news-6"></a>
### [Claude-Assisted Riemann Hypothesis &\#x27;Proof&\#x27; Unravels Over Vacuous Lean Code](https://x.com/i/web/status/2124987173439209561) ⭐️ 7.0/10

A widely circulated claim that Claude helped produce a Lean formalization proving the Riemann Hypothesis and its generalized form has reportedly collapsed after researchers found that key definitions were tautological and geometric conditions were vacuous, making the proof potentially vacuous. The authors had released 17 million lines of Lean across 175,000 files without a human-readable proof, and the Lean/Mathlib community said the next day it had “sufficient confidence” that the code proved the proposition, according to the report. On Nov. 23, Alpöge acknowledged that “250,000 pages was a joke,” that the code was “garbage but compiles,” and that the criticism was entirely reasonable. The account comes from a social-media aggregation and has not been independently verified.

telegram · zaihuapd · Nov 24, 01:29

**「Background」** Lean is a formal theorem prover, and Mathlib is the mathematical library used with it; a formal proof is only meaningful if its definitions capture the intended statement. Here, critics argued that key definitions were tautological and geometric conditions were effectively empty, which could let the proof pass checking without establishing the Riemann Hypothesis itself.

**「Verification gap」** Researchers and teams reviewing AI-generated Lean proofs now have a concrete reason to audit definitions and theorem statements manually: the archive compiled and passed kernel checks, yet the alleged Riemann proof was found to rely on tautological definitions and vacuous geometric conditions. Treating compilation or Lean/Mathlib acceptance as proof of the stated result risks directing review effort toward the wrong layer and building on an empty formalization.

**Tags**: `#AI-generated proofs`, `#Lean theorem prover`, `#Riemann Hypothesis`, `#formal verification`, `#AI hype`

---

<a id="item-tech-news-7"></a>
### [HarmonyOS 5–7 devices pass 100 million; apps top 460,000](https://www.xinhuanet.com/20261124/68842538167d4e59a875056d5eb885ad/c.html) ⭐️ 7.0/10

Huawei Terminal announced on November 24 that phones, tablets and computers running HarmonyOS 5, 6 or 7 have surpassed 100 million units. The platform now offers more than 460,000 apps and services and has more than 12 million registered developers. OpenHarmony has drawn over 14,000 contributors and 120-plus industry distributions; partner-contributed capabilities exceed 160 and are integrated into more than 1,600 apps, with usage up 90-fold in a year.

telegram · zaihuapd · Nov 24, 01:46

**「Background」** HarmonyOS was first released in 2019, and Huawei introduced the native HarmonyOS version in October 2024. The device figure reported on November 24 covers phones, tablets, and PCs running HarmonyOS 5, 6, or 7, so it aggregates several OS generations rather than a single release.

**「Impact」** For developers, Huawei&\#x27;s 100 million figure describes a combined HarmonyOS 5–7 installed base; the announcement gives no version-level breakdown, so it does not show how many devices run the newest release.

**Tags**: `#HarmonyOS`, `#OpenHarmony`, `#mobile OS`, `#developer ecosystem`, `#Huawei`

---

<a id="item-tech-news-8"></a>
### [Singapore Says It Won’t Be a Conduit for US Chip Controls](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said Singapore will not be used as a route to evade U.S. chip export controls, as authorities investigate Megaspeed&\#x27;s purchases of Nvidia chips. The statement came a day after the U.S. Commerce Department added Megaspeed and six other Southeast Asian companies to a trade blacklist, including affiliates in Malaysia and Thailand. The Federal Register cited a &quot;significant risk&quot; that they would divert advanced computing products to unauthorized users, according to the report. Reuters reported that Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions was also listed; Alibaba said it has never diverted controlled advanced computing chips.

telegram · zaihuapd · Nov 24, 05:03

**「Earlier US blacklisting」** The remarks followed a US Commerce Department decision, reported a day earlier, to place Megaspeed and six other Southeast Asian firms on a trade blacklist. The Federal Register cited a &quot;significant risk&quot; that the companies would divert advanced computing products to unauthorized users; the listings included their Malaysian and Thai affiliates and Alibaba&\#x27;s Singapore unit Apex Enterprise Solutions.

**「Who is affected」** Because the Commerce Department added Megaspeed, six other Southeast Asian firms \(including their Malaysian and Thai affiliates\) and Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions to its trade blacklist, those entities now fall under US export licensing requirements before American suppliers can ship them controlled advanced-computing products. Alibaba says it never transferred restricted advanced computing chips, so the designation is likely to be disputed, while other Singapore-based cloud and trading intermediaries should expect closer scrutiny of chip orders.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/business/us-blacklist-megaspeed-chip-firm-linked-nvidia-scandal-source-says-2026-11-23/">US blacklists Alibaba subsidiary and Megaspeed linked to ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/24/us-adds-megaspeed-to-trade-blacklist-over-export-control-concerns-.html">U.S. adds Megaspeed to trade blacklist over export control ...</a></li>

</ul>
</details>

**Tags**: `#semiconductor export controls`, `#AI chips`, `#Nvidia`, `#Singapore`, `#US tech policy`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [ERNIE 5.5 Flash Preview Arrives on vLLM as a Plugin](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 6.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** Baidu&\#x27;s ERNIE team and vLLM released day-0 support for ERNIE 5.5 Flash Preview, a 280B-total, 14B-active sparse mixture-of-experts model with a 1M-token context and tool use for long-horizon agent tasks. It had to run on the official vLLM wheel without a fork, custom image, or nightly build.

**「Solution」** The support ships as vLLM-ERNIE, a standalone plugin installed alongside vllm==0.32.0 and discovered through the vllm.general\_plugins entrypoint; it registers ERNIE architectures lazily, plus config, tokenizer, chat renderer, and parsers, leaving other models unaffected. The 43-layer model combines 37 Heavily Compressed Attention layers with 6 MLA-DSA layers, 512 routed experts \(top-10\) plus a shared expert in a 2048-dimensional latent space, and four mHC residual streams. The authors describe fused kernels for VHA cross-head mixing, Multi-Router Latent MoE, the MultiMax output head, and gated attention, reporting 1.55×–6.53× per-kernel speedups over naive implementations; FlashIndexer adds dynamic head routing and threshold pre-filtering, using a router distilled from DSA selections on about 1B tokens, for a reported 1.4× speedup at 1M context. Routed experts use MXFP4 W4A8 quantization-aware training, other weights and the KV cache use FP8, and a bundled three-layer DSpark draft model proposes up to seven tokens per step, said to reach mean acceptance length above 4.0 on coding and agent workloads. Deployment options include data-parallel attention with expert parallelism, TP2/4/8, PD disaggregation over Mooncake, and CPU KV offload, but the post gives vendor-reported figures without benchmark methodology.

**「Takeaway」** The release shows how a plugin can give a complex new MoE day-0 support on upstream vLLM while co-designed kernels and training target long-context cost, though its performance claims remain vendor-reported.

**Tags**: `#vLLM`, `#ERNIE 5.5`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`

---

## Financial News

<a id="item-finance-news-1"></a>
### [AI Selloff Clouds Planned Listings by DeepSeek and Moonshot](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 7.0/10

A global selloff that followed Anthropic&\#x27;s record $119.5 billion IPO is weighing on Chinese tech shares and complicating potential share sales by DeepSeek, Moonshot and StepFun, which the report says are preparing or considering listings. Chinese tech stocks have shed $1.7 trillion in market value since the end of June, the report said.

telegram · zaihuapd · Nov 23, 09:31

**「Background」** The chill followed Anthropic’s record-breaking initial public offering—its first sale of shares to the public—whose stock rose 17% on its first trading day before falling 8.5% the next, amid a global AI-stock selloff that weakened investor appetite as private Chinese AI developers DeepSeek, Moonshot and StepFun prepared or considered their own share sales.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/live/2026/11/19/technology/anthropic-ipo-ai/when-will-anthropic-shares-start-trading">Anthropic’s Value Surges After Multibillion-Dollar I.P.O.</a></li>
<li><a href="https://www.cnbc.com/2026/11/21/anthropic-ipo-tech-selloff.html">Anthropic’s record IPO collides with tech’s worst week on ...</a></li>

</ul>
</details>

**Tags**: `#AI selloff`, `#China tech`, `#IPOs`, `#Anthropic`, `#market volatility`

---

<a id="item-finance-news-2"></a>
### [Shanghai Metro to Adjust Fares for First Time in 21 Years](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

Shanghai Metro announced its first fare adjustment in 21 years, effective Dec. 1, with a 3-yuan starting fare for 0–4 km, then 1-yuan increases at successive bands of 4, 4, 4, 7, 7, 10 and 10 km, and every 15 km beyond 50 km. From Nov. 26 it will sell 35-, 45-, 60- and 90-ride tickets for 190, 210, 270 and 390 yuan, and riders using one payment channel get 10% off after 90 yuan in monthly spending.

telegram · zaihuapd · Nov 23, 10:45

**「Background」** Shanghai&\#x27;s metro fares had stayed unchanged for 21 years before this revision, which replaces the old pricing with distance-based charges: 3 yuan covers the first 0–4 km, and each additional 4, 4, 4, 7, 7, 10 and 10 km adds 1 yuan. The new multi-ride tickets and monthly 10% discount after 90 yuan of spending on one payment channel are intended to soften the effect on frequent riders.

**「Impact」** Shanghai households with regular metro commutes are the main affected group; the new multi-ride tickets and monthly discount are designed to limit the effect on high-frequency riders.

**Tags**: `#Shanghai Metro`, `#public transit fares`, `#fare adjustment`, `#commuting costs`, `#discount passes`

---