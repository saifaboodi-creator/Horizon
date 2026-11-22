---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 24 items, 8 important content pieces were selected

---

**Technology News**
1. [Claimed Lean verification of Riemann Hypothesis draws scrutiny](#item-tech-news-1) ⭐️ 9.0/10
2. [Zhejiang University reports first QRAM on a superconducting quantum chip](#item-tech-news-2) ⭐️ 8.0/10
3. [GPGME double-free reported in versions before 2.3.0](#item-tech-news-3) ⭐️ 7.0/10
4. [Monitor&\#x27;s USB Ethernet Path Cut Download Speed by 75%](#item-tech-news-4) ⭐️ 7.0/10
5. [Graham Dumpleton unveils Muru, a Rust server for ASGI and WSGI apps](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft previews RDMA over USB4 for pooled local AI on Windows](#item-tech-news-6) ⭐️ 7.0/10
7. [OpenRouter Warns MiniMax Prompts May Be Read by Third Parties](#item-tech-news-7) ⭐️ 7.0/10

**Technology Blog**
1. [Good Code Comes From Avoiding Blunders, Not Cleverness](#item-tech-blog-1) ⭐️ 6.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Claimed Lean verification of Riemann Hypothesis draws scrutiny](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 9.0/10

A claim that the Riemann Hypothesis has been verified in Lean is under discussion, presented as a potentially major AI-assisted mathematics result. The supplied item does not include the proof text, the Lean version or dependencies, or an independent validation, so the verification remains unconfirmed here. Commenters focus on whether the proof could depend on a checker bug and on how much mathematics the formalization reportedly covers.

hackernews · g-b-r · Nov 21, 14:36 · [Discussion](https://news.ycombinator.com/item?id=50589618)

**「Background」** Lean is a proof assistant that accepts a theorem only when its proof type-checks against a small trusted kernel, so formal verification establishes that the result follows from the encoded definitions and axioms rather than that those definitions faithfully capture the informal claim. The item concerns a Lean formalization of the Riemann Hypothesis, a conjecture about the zeros of the Riemann zeta function; search results summarizing the linked Lean community blog post describe Levent Alpöge&\#x27;s release of the proof as a Lean library.

**「Impact」** For mathematicians and Lean users, the practical next step is independent checking of the Lean development across separate kernels and review by domain experts; commenters treat acceptance by a single checker as insufficient.

**「Community discussion」** Commenters debate trust in the checker: rcr-anti argues that a bug would now have to affect multiple kernels and their consistency proofs, while thejokeisonme notes that a fake Collatz refutation previously got through an independent checker and questions how independent they really are, though a human expert was involved in this case. Others highlight the scale of the reported formalization and credit Levent for getting strong results from Claude.

<details><summary>References</summary>
<ul>
<li>Lean verification of the Riemann Hypothesis | Lean community blog</li>
<li>Lean and Mathlib confirmed that Alpoge and Claude&#x27;s proof ... - Reddit</li>

</ul>
</details>

**Tags**: `#formal verification`, `#Lean`, `#Riemann Hypothesis`, `#AI-assisted mathematics`, `#proof assistants`

---

<a id="item-tech-news-2"></a>
### [Zhejiang University reports first QRAM on a superconducting quantum chip](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

Zhejiang University researchers report that they have run a quantum random-access memory \(QRAM\) on a real superconducting chip, called Tianmu 2, for the first time, with results published in Nature Physics. The self-developed chip ran 4-bit and 8-bit QRAM prototypes at 80.9% and 60.4% accuracy, respectively; the team says circuit depth was more than 30% lower than an unoptimized design and that the architecture showed local noise resilience. The work remains a small-scale prototype, and the team says its next step is scaling QRAM up.

telegram · zaihuapd · Nov 21, 08:31

**「Background」** QRAM is a proposed quantum memory component that would let quantum algorithms address data in superposition, a capability sought for many quantum algorithms. The reported experiment is a hardware demonstration of that idea rather than a ready-to-use memory device.

**「Impact」** For quantum-hardware researchers, the reported reduction of more than 30% in circuit depth and the local noise-resilience result point to design choices worth testing in larger QRAM circuits. However, 60.4% accuracy for the 8-bit prototype means the device is not yet reliable enough for practical data storage or algorithm use, so organizations should treat it as a proof-of-principle component rather than an available QRAM module.

**Tags**: `#量子计算`, `#QRAM`, `#超导量子芯片`, `#量子硬件`, `#研究进展`

---

<a id="item-tech-news-3"></a>
### [GPGME double-free reported in versions before 2.3.0](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 7.0/10

A reported double-free vulnerability in GPGME affects versions before 2.3.0, according to community discussion of the disclosure. Commenter miduil says Johan Carlsson discovered it and that GitLab was informed on 2026-11-12; the disclosure was moved from 2026-11-25 to 2026-11-20 because GitLab had to update earlier amid the Ruby2Shell bug. Commenter wannabe44 says all software using GPGME before 2.3.0 is affected whether linked as a shared library, DLL, or statically, citing Gpg4win, GnuPG Desktop, most mail clients, many XMPP clients, Samba, and Flatpak as examples.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Background」** GPGME is the OpenPGP library used by Gpg4win, GnuPG Desktop, and other applications. The advisory for CVE-2026-129975 describes a double free triggered by an OpenPGP key with a crafted, very long user ID and does not rule out remote code execution, which explains why the RCE framing is contested.

**「Impact」** Maintainers of downstream software should verify their GPGME version and linkage, because the reported flaw applies to shared, DLL, and static builds before 2.3.0; GitLab&\#x27;s signed-commit support makes that path a particular code-execution concern, according to miduil, and an Omnibus-related patch was linked in the discussion.

**「Community discussion」** Commenters dispute the submission&\#x27;s RCE framing: mik1998 says it is a double-free bug, not an RCE chain, while uptrails says Red Hat fixed the issue five years ago but upstream missed the fix. The thread also questions whether the advisory language overstates the impact.

<details><summary>References</summary>
<ul>
<li><a href="https://lists.gnu.org/archive/html/info-gnu/2026-11/msg00006.html">GnuPG Security Advisory for GPGME (T8557,CVE-2026-129975)</a></li>
<li><a href="https://news.lavx.hu/article/gnupg-releases-gpgme-2-3-1-to-fix-critical-double-free-vulnerability">GnuPG releases GPGME 2.3.1 to fix critical double-free ...</a></li>

</ul>
</details>

**Tags**: `#security vulnerability`, `#GPGME`, `#GnuPG`, `#double free`, `#open source`

---

<a id="item-tech-news-4"></a>
### [Monitor&\#x27;s USB Ethernet Path Cut Download Speed by 75%](https://blog.tymscar.com/posts/studiodisplayethernet/) ⭐️ 7.0/10

A troubleshooting blog post reports that a monitor&\#x27;s integrated USB Ethernet path introduced enough latency to delay packet acknowledgements, build a buffer, and cause packet loss, cutting the author&\#x27;s download speed by 75%. Replacing the adapter with a different Ethernet adapter resolved the issue. The account is a single-case hardware diagnosis, not a broad performance measurement.

hackernews · soheilpro · Nov 21, 10:36 · [Discussion](https://news.ycombinator.com/item?id=50587875)

**「Background」** Many USB-C monitors double as docks, routing Ethernet through a built-in USB hub rather than exposing a direct network port to the laptop. USB hubs and docks can add latency through their internal controllers and shared bandwidth, and that delay can prevent a host from acknowledging TCP packets quickly enough, filling the adapter buffer and causing packet drops.

**「Impact」** For users with a similar monitor- or dock-provided Ethernet path, the practical check is to bypass the integrated hub or adapter and test a direct or alternate adapter; the reported slowdown persisted until the adapter changed.

**「Community Discussion」** One commenter argued the monitor is incidental and the issue is better described as a USB network switch cutting download speed, while another stressed that the latency-induced acknowledgement delay, buffer buildup, and packet loss are the key mechanism. A separate commenter reported a similar year-long problem with a MacBook and Thunderbolt dock, saying that enabling flow control was good enough.

<details><summary>References</summary>
<ul>
<li><a href="https://www.anker.com/blogs/hubs-and-docks/do-usb-hubs-add-latency">Do USB Hubs Add Latency? How to Lessen It? - Anker US</a></li>
<li><a href="https://www.purplelec.com/info-detail/usb-hub-delay-optimization">Does a USB Hub Add Latency? Deep Dive into Performance &amp; 7 ...</a></li>

</ul>
</details>

**Tags**: `#USB hubs`, `#networking`, `#packet loss`, `#hardware troubleshooting`, `#latency`

---

<a id="item-tech-news-5"></a>
### [Graham Dumpleton unveils Muru, a Rust server for ASGI and WSGI apps](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton, the creator of mod\_wsgi, has introduced Muru, an AI-assisted Rust server intended to run both ASGI and WSGI Python applications in development and production. The project is presented as an early-stage effort: the source describes it as aiming to provide better serving tools and gives no version number, release date, benchmark, or independent performance result. Dumpleton documented the work in 18 posts published between November 4 and November 21, 2026, covering the worker model, import-once/fork-many startup, HTTPS in development, running WSGI and ASGI together, releases without restarts, canary deployments without a service mesh, container and Kubernetes behavior, scaling to zero, scheduled overlays, and a per-page toolbar with tracing. In an accompanying post he stated that AI does much of the surface work but that judging what is not yet good enough remains his responsibility, drawing on two decades of mod\_wsgi experience.

rss · Simon Willison · Nov 21, 23:56

**「Background」** WSGI and ASGI are Python interfaces between web servers and applications. Graham Dumpleton began mod\_wsgi 20 years ago, and that project became a long-running WSGI implementation; Muru is his new Rust-based server for running ASGI and WSGI applications.

**「Deployment implications」** For teams with existing WSGI code, Muru&\#x27;s \`muru.wsgi\_to\_asgi\` object in the WSGI environ lets a WSGI application hand a request off to an ASGI application, including detecting a WebSocket upgrade, so ASGI features can be adopted without rewriting the whole app as ASGI. Because that bridge is a Muru-specific environ key, code depending on it is tied to Muru rather than portable across other WSGI servers, and Dumpleton himself frames Muru as still being polished toward something he would trust in production.

<details><summary>References</summary>
<ul>
<li><a href="https://grahamdumpleton.me/posts/2026/11/muru-wsgi-and-asgi-together/">Muru : WSGI and ASGI together - Graham Dumpleton</a></li>

</ul>
</details>

**Tags**: `#Python`, `#ASGI`, `#WSGI`, `#Rust`, `#web servers`

---

<a id="item-tech-news-6"></a>
### [Microsoft previews RDMA over USB4 for pooled local AI on Windows](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft released a Windows developer preview of RDMA over USB4 that lets multiple PCs pool memory and GPU compute to run a single local AI model without a dedicated network card or switch. In a demonstration, three AMD Ryzen AI Max+ 395 systems ran 4-bit Qwen3-235B-A22B at about 18.5 tokens per second. The preview is being distributed through Windows Insider, so it remains an early developer capability rather than a finished production feature.

telegram · zaihuapd · Nov 21, 06:13

**「What RDMA is」** RDMA \(Remote Direct Memory Access\) is a technique that lets one computer read and write another device&\#x27;s memory directly, bypassing the CPU rather than having the processor mediate each transfer, as described in Habr&\#x27;s coverage of the same preview. That low-overhead memory sharing is the mechanism that makes pooling the memory and GPU resources of separate machines into one inference job feasible.

**「What it means for local AI users」** For developers and users whose models exceed a single PC’s memory, the preview lets a compatible inference framework span several USB4-connected Windows machines using NetworkDirect, the same API used with datacenter RDMA adapters. Adoption requires the Windows Insider developer preview plus compatible hardware and software; Intel’s tests also found that adding a fourth PC sped up generation but delayed the start of output.

<details><summary>References</summary>
<ul>
<li><a href="https://habr.com/ru/articles/1110636/">Microsoft представила решение на базе USB 4 и RDMA для... / Хабр</a></li>
<li><a href="https://techcommunity.microsoft.com/blog/microsoftusbblog/introducing-rdma-over-usb4%C2%AE-on-windows-run-larger-local-ai-models-across-pcs/4574602">Introducing RDMA over USB4® on Windows: run larger local AI ...</a></li>
<li><a href="https://xenospectrum.com/en/windows-rdma-usb4-local-ai/">Microsoft Previews RDMA over USB4 for Windows, Splitting ...</a></li>
<li><a href="https://www.guru3d.com/story/microsoft-previews-usb4-links-that-let-windows-pcs-pool-memory-and-gpu-resources/">Microsoft previews USB4 links that let Windows PCs pool ...</a></li>

</ul>
</details>

**Tags**: `#RDMA over USB4`, `#local AI inference`, `#Windows`, `#distributed computing`, `#AMD Ryzen AI Max+`

---

<a id="item-tech-news-7"></a>
### [OpenRouter Warns MiniMax Prompts May Be Read by Third Parties](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

OpenRouter emailed users that prompts sent to MiniMax models may have been read by third parties, according to a notice summarized in the source. Security researchers sent prompts containing test URLs to MiniMax models between July and October 2026, and third parties visited those URLs 40 to 130 hours later. OpenRouter attributed the issue to MiniMax and its forwarding providers AtlasCloud, Novita, and StreamLake, removed the affected endpoints&\#x27; &quot;zero data retention&quot; label, and advised users with sensitive credentials to rotate API keys and passwords. OpenRouter had not published the notice on its website, and the source does not establish the full scope or mechanism of the exposure.

telegram · zaihuapd · Nov 21, 06:53

**「Background」** OpenRouter is a routing marketplace rather than a single model host: the same model can be served through several third-party inference providers, and its listing for MiniMax M2.5 names five, including StreamLake and AtlasCloud. Because requests are forwarded to those providers, data-handling commitments such as a zero-data-retention label attach to individual endpoints rather than to the MiniMax model as a whole.

**「Credential and retention risk」** Developers who sent API keys, passwords, or other secrets in prompts to MiniMax models through OpenRouter should rotate those credentials, because OpenRouter says the prompts may have been read by a third party. OpenRouter has removed the zero-data-retention label from the MiniMax, AtlasCloud, Novita, and StreamLake endpoints involved, so users should not treat those routes as no-retention until the designation is restored.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/minimax/minimax-m2.5">MiniMax M2.5 - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://www.atlascloud.ai/blog/tips/minimax-h3-on-openrouter-3-real-video-tests-for-2026">https://api. atlascloud .ai/v1</a></li>
<li>OpenRouter warns MiniMax prompts may have been read by a third party</li>

</ul>
</details>

**Tags**: `#LLM安全`, `#隐私`, `#数据保留`, `#OpenRouter`, `#MiniMax`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Good Code Comes From Avoiding Blunders, Not Cleverness](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Sean Goedecke argues that engineers wrongly treat good programming as a hunt for brilliant insights, when the real secret is avoiding catastrophic mistakes. He scopes the advice to large commercial codebases worked on by big teams.

**「Solution」** Drawing on chess and tennis, he suggests that never hanging a piece or reliably returning the ball beats most opponents, even without spectacular play. Programming resembles this because it offers no durable winning advantage: one blunder can turn an elegant codebase into a janky one. His examples include introducing a parallel system, creating a second source of truth, making a safe synchronous operation delicately asynchronous, adding subtle failure points, and complicating a key interface. The cardinal sins are inconsistency and unnecessary requirements. Inconsistency breaks trust, forcing engineers to hunt for surprises instead of assuming sensible behavior. Unnecessary requirements are sticky because later engineers lack the context to remove them, and they interact combinatorially with every new feature. The author&\#x27;s heuristics are to fit each task as normally as possible into the existing codebase and trim it to the smallest set of requirements; thinking “I could use this clever pattern” is a warning sign. He adds that current coding agents match humans on consistency but are worse at avoiding unnecessary requirements.

**「Takeaway」** Goedecke&\#x27;s thesis is that great programming depends less on cleverness than on attention to detail and disciplined focus: maintain consistency and skip unnecessary requirements, because cleverness itself can become a disadvantage.

**Tags**: `#software engineering`, `#code quality`, `#complexity`, `#engineering judgment`, `#maintainability`

---