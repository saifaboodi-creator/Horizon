---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 39 items, 11 important content pieces were selected

---

**Technology News**
1. [Terry Tao Post Links Unforced Navier-Stokes Singularity to Generalized Riemann Hypothesis](#item-tech-news-1) ⭐️ 9.0/10
2. [Levent Alpöge claims proof of Generalized Riemann Hypothesis with 1.3GB Lean formalization](#item-tech-news-2) ⭐️ 8.0/10
3. [Thinking Machines releases Inkling 2 Mini, an open-weights looped model](#item-tech-news-3) ⭐️ 8.0/10
4. [KVM flaw lets VMs read AMD host memory](#item-tech-news-4) ⭐️ 8.0/10
5. [TSMC Halts 16nm-and-Below Orders From Chinese Firms Under Tighter U.S. Rules](#item-tech-news-5) ⭐️ 8.0/10
6. [Unverified GitHub claim of Navier–Stokes blow-up draws discussion](#item-tech-news-6) ⭐️ 7.5/10
7. [Signal Moves to Limit Mobile AI Agents&\#x27; Access to User Data](#item-tech-news-7) ⭐️ 7.0/10
8. [OpenAI API adds 2- or 8-hour background tasks with token discounts](#item-tech-news-8) ⭐️ 7.0/10

**Technology Blog**
1. [Why Caching LLM Outputs Barely Saves Tokens](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Fed officials diverge on rate hikes as Warsh withholds guidance](#item-finance-news-1) ⭐️ 7.0/10
2. [U.S. companies shift from buybacks to net share issuance](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Terry Tao Post Links Unforced Navier-Stokes Singularity to Generalized Riemann Hypothesis](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 9.0/10

Terry Tao published a blog post dated November 20, 2026, titled “Unforced Euler singularity, unforced Navier-Stokes singularity, and the Generalized Riemann Hypothesis.” The supplied item does not include the post text, so the specific arguments, any claimed proofs, and their status remain unverified here. On Hacker News, discussion centered on AI-assisted proof and Lean verification; one commenter linked to a Lean Zulip thread and said two independent kernels accept “the result,” suggesting the proof was checked in more than one Lean kernel without establishing exactly which theorem was proved.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Background」** The Navier–Stokes equations model incompressible fluid flow, and a central open question is whether an initially regular flow can develop a singularity in finite time. In an October 4, 2026 post, Terence Tao noted that recent Euler and Navier–Stokes work produced with the aid of large language models had renewed attention on that question, building on decades of earlier mathematical research.

**「What Lean verification does and doesn&\#x27;t settle」** For mathematicians and AI-proof developers, acceptance by two independent Lean kernels lowers the risk that a formalized result rests on a bug in a single kernel implementation, since Lean&\#x27;s design keeps a small trusted kernel checking untrusted proof terms. It does not by itself establish that the formal statement matches the intended theorem: AI-generated arguments are prone to hidden gaps, so statement-level human review remains the remaining verification burden.

**「Community Discussion」** Commenters combined technical confidence with anxiety: one noted that acceptance by two independent Lean kernels makes kernel-bug exploitation unlikely, while another asked how AI systems that generate and verify proofs within existing abstractions could create new concepts such as the Langlands program. Several researchers said they felt uncertain whether human mathematical research still has room, framing that as a personal concern rather than a established conclusion.

<details><summary>References</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/10/04/on-classical-solutions-and-singularity-formation-in-incompressible-fluids/">On classical solutions and singularity formation in ...</a></li>
<li><a href="https://mlcrypto.mit.edu/course/scribe-notes/lec14_scribe.pdf">Lecture 14: Lean: A Different Take on Verification</a></li>
<li><a href="https://mathoverflow.net/questions/513540/should-we-trust-ai-generated-formal-proofs-in-lean-4">Should we trust AI-generated formal proofs in Lean 4?</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#AI-assisted proof`, `#Lean theorem prover`, `#formal verification`, `#Navier-Stokes`

---

<a id="item-tech-news-2"></a>
### [Levent Alpöge claims proof of Generalized Riemann Hypothesis with 1.3GB Lean formalization](https://alpo.ge/remark.pdf) ⭐️ 8.0/10

A PDF hosted at alpo.ge/remark.pdf and posted to Hacker News claims a proof of the Generalized Riemann Hypothesis, attributed to Levent Alpöge, accompanied by a Lean formalization distributed as 14 tarball parts that a commenter measured at roughly 1.3GB and about 15 million lines. The supporting artifact is therefore a machine-checkable candidate proof rather than only a prose argument, and the commenter&\#x27;s download-and-extract commands indicate it is meant to be built and checked locally. Nothing in the supplied material shows the proof has been peer reviewed, accepted by a journal, or independently confirmed end to end; the claim remains unverified here. A related Hacker News submission separately advertises a &quot;Hurried Announcement&quot; concerning Alessandro Masullo and GRH, which is a distinct announcement from the Alpöge PDF.

hackernews · iamronaldo · Nov 20, 14:16 · [Discussion](https://news.ycombinator.com/item?id=50574968)

**「Background」** Levent Alpöge is a number theorist known for work in arithmetic statistics; reports on 20 November 2026 described the Anthropic staff member as claiming, with Claude, a proof of the 167-year-old Riemann hypothesis. The posted item concerns the Generalized Riemann Hypothesis, which extends the 1859 Riemann hypothesis from the Riemann zeta function to a broader family of L-functions.

**「What checking it requires」** For mathematicians and formal-verification practitioners, the immediate consequence is a verification workload: retrieving all 14 parts, reassembling and extracting the archive, and running the Lean build over an artifact of roughly 15 million lines before the result can be treated as established. That scale makes independent checking feasible mainly for people with the tooling and compute to compile it, so the claim&\#x27;s status will hinge on third-party build results rather than on the PDF alone.

**「Verification vs. doubt」** One commenter argued there is &quot;no any doubt&quot; the proof is correct, citing multiple formal verification routes and pointing to a check page maintained by MIT&\#x27;s Andrew Sutherland that was run with Claude Code and was still being updated as of 2026-11-20 22:05 UTC; this is a commenter&\#x27;s report, not confirmation in the supplied material. Another commenter linked a separate post at math216.wordpress.com describing what they called a completely human proof, while others treated the news as a threshold moment for AI-assisted mathematics and quoted Terence Tao saying a month earlier that AI companies could not &quot;touch&quot; the Riemann hypothesis and that something beyond current AI would be needed.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Levent_Alp%C3%B6ge">Levent Alpöge - Wikipedia</a></li>
<li><a href="https://www.nacionale.com/en/articles/has-riemann-hypothesis-been-proved-levent-alpoge-claude-anthropic-claim-lean">Riemann hypothesis proof claimed with Claude, unverified</a></li>
<li><a href="https://www.clarin.com/us-news/who-is-levent-alpoge-the-anthropic-mathematician-who-claims-solved-the-riemann-hypothesis-with-claude_0_2WdGvYKBVM.html">Who is Levent Alpöge ? The Anthropic mathematician who claims he...</a></li>

</ul>
</details>

**Tags**: `#Riemann Hypothesis`, `#Lean theorem prover`, `#formal verification`, `#mathematics`, `#AI-assisted research`

---

<a id="item-tech-news-3"></a>
### [Thinking Machines releases Inkling 2 Mini, an open-weights looped model](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines has released Inkling 2 Mini, an open-weights model built on a looped-transformer architecture and sized with local inference in mind. A commenter relays a team note saying training was end-to-end in nvfp4, and early testers report running it through llama.cpp on consumer hardware, but the supplied material does not independently verify the coding-benchmark comparisons. One commenter says it appears competitive with Qwen3.8-27B if those benchmarks hold; another reports about 27 tokens/s decode on a Ryzen 395 with llama.cpp Vulkan and about 10 tokens/s on a 32GB M1 Pro at q4 xl.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Background」** Inkling 2 Mini is a 26B-parameter mixture-of-experts model with 5.4B active parameters, built as a looped transformer: instead of stacking more distinct layers, it passes hidden states through its middle layers repeatedly so each token receives more computation. It is a much smaller sibling of Thinking Machines&\#x27; Inkling 2 Small, shipped with NVFP4 and MXFP8 expert weights and a DSpark drafter intended to speed up local inference.

**「Impact」** Developers who want the reported local throughput should expect to track unmerged llama.cpp PRs and possibly apply a community speed patch, rather than relying on a stock build.

**「Community Discussion」** Commenters treated the open-weights looped architecture as the main draw, with one calling it competitive with Qwen3.8-27B if benchmarks hold and another predicting most open models will go looped; one also asked what that means for safety and interpretability. Reported local performance varied widely by hardware—about 27 tokens/s on a Ryzen 395 via llama.cpp Vulkan versus about 10 tokens/s on a 32GB M1 Pro—and a tester said a small patch added roughly 30% speed.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://artificialanalysis.ai/articles/inkling-2-mini">Thinking Machines has released Inkling 2 Mini, an open ...</a></li>
<li><a href="https://huggingface.co/blog/inkling2mini">Welcome Inkling 2 Mini, Cutting-edge Performance for your ...</a></li>

</ul>
</details>

**Tags**: `#open-weights`, `#LLM`, `#looped-transformers`, `#local-inference`, `#llama.cpp`

---

<a id="item-tech-news-4"></a>
### [KVM flaw lets VMs read AMD host memory](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

CVE-2026-99312 in Linux KVM allows a virtual machine to read host memory on AMD hosts when nested virtualization is enabled. Researchers reported reading about 127 GB of host memory from inside a VM on DigitalOcean. Upstream fixes were released on November 18 in stable kernel 7.3.5 and other stable kernels, but Debian and Ubuntu distribution kernels remain unpatched; disabling nested virtualization is the workaround until a fix is available.

telegram · zaihuapd · Nov 20, 14:23

**「Background」** KVM is the hypervisor built into the Linux kernel, and nested virtualization lets a guest VM run its own hypervisor — the configuration in which this flaw is reachable. Terra Security reports that CVE-2026-99312 involved a stale pointer that remained in the kernel for just under four years and was introduced by an earlier security fix; DigitalOcean describes the same stale-pointer mechanism.

**「Impact」** Cloud providers and operators running affected AMD KVM hosts should disable nested virtualization or deploy a fixed kernel, because guest isolation is compromised until the host is patched. Hosts that do not enable nested virtualization are outside the reported scope.

<details><summary>References</summary>
<ul>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to- Host Escape | Terra Security Research</a></li>

</ul>
</details>

**Tags**: `#KVM`, `#CVE-2026-99312`, `#Linux kernel`, `#virtualization security`, `#AMD`

---

<a id="item-tech-news-5"></a>
### [TSMC Halts 16nm-and-Below Orders From Chinese Firms Under Tighter U.S. Rules](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

TSMC has notified customers that it is pausing orders from Chinese companies for its 16nm-and-below processes, in order to comply with tightened U.S. semiconductor export rules, according to a secondary report. Under the new rules, TSMC cannot supply these nodes without a U.S. export license or exemption obtained in advance; previously the foundry could itself assess whether a customer&\#x27;s design met exemption criteria, but customers must now apply first. Chinese firms are reportedly restricted to older nodes such as 28nm and 40nm and are said to lose access to the high-bandwidth memory used in AI data-center hardware. The report lists Apple, AMD and Nvidia among U.S.-approved customers, with no Chinese companies named, and says TSMC will comply with the new rules.

telegram · zaihuapd · Nov 21, 02:01

**「Licensing shift behind the pause」** The pause hinges on U.S. export licensing for advanced chips: TSMC may supply Chinese customers only if they first obtain a U.S. export license or exemption. Previously, TSMC could itself assess whether a customer design met exemption criteria; under the tightened rules, customers must apply in advance.

**「What changes for Chinese chip designers」** Chinese chip designers that rely on TSMC&\#x27;s 16nm-and-below nodes now face a licensing gate: they must obtain a U.S. export license or exemption before orders can proceed, and TSMC is reportedly widening customer screening to include corporate ownership, major shareholders, operating locations, packaging contractors, and shipping arrangements. That leaves older 28nm and 40nm processes as the fallback described in the report, constraining access to advanced AI/data-center chips and HBM.

<details><summary>References</summary>
<ul>
<li><a href="https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls">TSMC has suspended some chip orders amid tighter export controls</a></li>
<li><a href="https://www.taiwannews.com.tw/en/news/6478978">TSMC suspends some advanced chip orders from China</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#TSMC`, `#export controls`, `#China`, `#AI hardware`

---

<a id="item-tech-news-6"></a>
### [Unverified GitHub claim of Navier–Stokes blow-up draws discussion](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 7.5/10

A GitHub repository hosted under Tristan Buckmaster&\#x27;s account presents a claimed finite-time blow-up result for the Navier–Stokes equations and was posted to Hacker News on November 20, 2026, where it drew discussion. The supplied material contains no paper, proof outline, or independent verification, so the claim should be treated as unverified rather than as an established resolution of the Navier–Stokes problem. Commenters describe it as the unforced counterpart to an earlier claimed forced blow-up result attributed to OpenAI, but that comparison is likewise unconfirmed here.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「The problem being claimed」** The Navier–Stokes existence and smoothness problem, one of the Millennium Prize problems, asks whether smooth initial data in three dimensions always produce globally smooth solutions with bounded kinetic energy, or whether finite-time breakdown can occur — in its classical formulations, with a smooth external force permitted. The linked repository accompanies a 79-page paper by L. Alpöge and T. Buckmaster and ships a Lean 4 package that formalizes the paper&\#x27;s statements and proofs, including a mapping to Theorems 1.1 and 7.1, Corollary 7.2 and Appendix B. The accompanying abstract claims the unforced case — smooth data, compactly supported on R^3 and periodic on T^3, whose solutions blow up in finite time — with the blow-up resting on a certificate: an approximate self-similar profile checked by interval arithmetic.

**「Impact」** Until a manuscript or independent expert check appears, researchers and readers cannot rely on the repository link as evidence of a proof; the practical step is to look for a preprint and technical review before citing or repeating the claim.

**「Community discussion」** Commenters focused on the distinction between the unforced problem and a claimed earlier result that used a carefully designed external force, with one arguing the unforced version is more &quot;realistic&quot; \(tancop\). Others discussed priority and drama surrounding the claim and asked whether a simulation could show the blow-up in real time to build intuition \(jrflo, ninkendo\); these are opinions and unverified claims, not confirmation of either result.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://hotrepo.ai/tristanbuckmaster/navier-stokes">tristanbuckmaster/navier-stokes: Lean 4 formalization of a ...</a></li>
<li><a href="https://aixiv.online/abs/2611.02204">[2611.02204] Finite-time blow-up for the Navier–Stokes ...</a></li>

</ul>
</details>

**Tags**: `#Navier-Stokes`, `#fluid dynamics`, `#mathematics`, `#finite-time blow-up`, `#research`

---

<a id="item-tech-news-7"></a>
### [Signal Moves to Limit Mobile AI Agents&\#x27; Access to User Data](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal published a blog post on protecting user privacy by restricting AI agents on mobile operating systems from capturing user data. The supplied material does not include the post’s technical mechanisms, affected platforms, versions, or rollout timing, so the concrete scope of the change is unclear. The discussion describes Signal as trying to prevent AI apps from reaching Signal chats, including when a contact—not the user—has installed such an app.

hackernews · dotcoma · Nov 20, 09:42 · [Discussion](https://news.ycombinator.com/item?id=50572348)

**「Background」** Mobile operating systems now include agentic AI features, such as Gemini and Siri, that analyze on-screen information to answer questions or act for the user; Signal says this can capture and store Signal data and undermine its ability to guarantee privacy independently. Signal&\#x27;s response blocks screenshots on Android and iOS, but Meredith Whittaker has acknowledged the fix is incomplete because AI agents could still reach app data through the device file system.

**「Impact」** For Signal users, the discussion points to an OS-level boundary: app-level screenshot or capture protections cannot control what happens on a contact’s device, so meaningful limits would depend on mobile OS permissions or sandboxing that Signal’s post does not detail here.

**「Community Discussion」** Commenters welcomed Signal’s attention to AI apps’ access to chats but split on remedies: some argued that app-level screenshot blocking cannot replace regaining control of the operating system, while others urged Signal to publish its forensics findings so smaller developers could benefit. A separate complaint said Signal’s VPN and captcha behavior creates barriers for journalists and their sources.

<details><summary>References</summary>
<ul>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#ai-agents`, `#mobile-security`, `#operating-systems`, `#signal`

---

<a id="item-tech-news-8"></a>
### [OpenAI API adds 2- or 8-hour background tasks with token discounts](https://developers.openai.com/api/docs/guides/background) ⭐️ 7.0/10

OpenAI&\#x27;s API now offers a background mode for long-running requests: setting \`background: true\` and \`background\_options.completion\_window\` to \`2h\` or \`8h\` runs the request asynchronously and prices tokens 30% or 40% below standard, respectively. Omitting the window uses the default \`soonest\` and carries no discount. The feature is in public beta on GPT-6.2 Astra, GPT-6.2 Sol, GPT-6.1 Terra and GPT-6 Luna, and responses are temporarily stored even when \`store\` is false or zero data retention is enabled.

telegram · zaihuapd · Nov 20, 11:15

**「How background mode works」** OpenAI&\#x27;s Background Mode is part of the Responses API: instead of holding a request open on a single HTTP connection, a caller sets background: true, receives a response ID, and retrieves the result later. That asynchronous pattern is the mechanism behind the reported 2-hour and 8-hour completion windows and their token discounts.

**「Retention and pricing caveats」** Developers using \`store: false\` or zero data retention must treat background mode as a retention exception: OpenAI temporarily stores response data even under those settings, so regulated or sensitive workloads need separate safeguards before opting in. The 40% discount also requires explicitly selecting the 8-hour \`completion\_window\` on one of the listed beta models; the default \`soonest\` setting carries no discount.

<details><summary>References</summary>
<ul>
<li><a href="https://kissapi.ai/blog/openai-background-mode-api-guide-2026.html">OpenAI Background Mode API : Run Long Tasks Without Timeouts...</a></li>
<li><a href="https://aiengineerguide.com/til/openai-background-mode/">Handling Async Inference with OpenAI &#x27;s API Background mode</a></li>

</ul>
</details>

**Tags**: `#OpenAI API`, `#asynchronous processing`, `#LLM pricing`, `#data retention`, `#AI infrastructure`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why Caching LLM Outputs Barely Saves Tokens](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference economics already depends on caching inputs — typically in the KV cache — so the full conversation history isn&\#x27;t recomputed on every message. Sean Goedecke asks whether outputs deserve the same treatment, since agents visibly repeat themselves a lot: re-quoting code snippets, echoing evidence documents, and reproducing sample model outputs because reading agent output is tiresome. Output tokens are also far more expensive to produce than input tokens are to ingest, which makes the waste look worse than the input-caching case.

**「Solution」** The author&\#x27;s proposed mechanism is to stop the repetition at the source: fine-tune or prompt a model to emit references like &quot;src/script.py:12-15&quot;, or pointers into its own conversation history, which the harness then expands transparently for the user. He argues this is probably not worth doing, because it optimizes only visible output. Models likely don&\#x27;t repeat themselves much in internal chain-of-thought, since that information is already available to them. In his own agent histories, visible output is only about 6% of output tokens: 50% are reasoning tokens and 44% are tool calls. That runs straight into Amdahl&\#x27;s law — even an optimistic two-thirds saving on visible output would cut total output tokens by roughly 4%. He flags only moderate confidence here, noting some early open-source reasoning models do loop, but they also use far more tokens than frontier models. The real lever is the invisible 94%, which depends largely on intelligence: smarter models need fewer reasoning tokens and tool calls, which is why a model that costs 5x more per token but uses 6x fewer tokens can be cheaper overall.

**「Takeaway」** Output caching targets too small a slice of agent token spend to matter; the meaningful savings come from model intelligence reducing the invisible reasoning and tool-call tokens that dominate cost.

**Tags**: `#LLM inference economics`, `#output caching`, `#Amdahl&\#x27;s law`, `#coding agents`, `#token costs`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed officials diverge on rate hikes as Warsh withholds guidance](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Federal Reserve officials are speaking more often and publicly splitting over how fast to raise rates while Chair Kevin Warsh refuses to signal the policy path, CNBC reported. Traders are pricing a 100% probability of at least a quarter-point rate hike at the December meeting, according to CME Group’s FedWatch, as inflation runs above 3% against the Fed’s 2% target.

rss · CNBC Finance · Nov 20, 21:10

**「Background」** Warsh has pushed a communication overhaul—fewer FOMC meetings and less public commentary—and in June 2026 cut the Fed’s policy statement to 132 words while removing forward guidance, the public signaling of future rate moves that he argues locks policymakers in.

**「Impact」** Bank of America economist Aditya Bhave warned that the public back-and-forth is causing undue volatility in interest rates, which matters for households and businesses whose borrowing costs are tied to market rates.

<details><summary>References</summary>
<ul>
<li><a href="https://www.financialexpress.com/market/global-market-pulse/why-fed-chair-warsh-scrapped-forward-guidance-in-a-132-word-pivot/4272071/">Why Fed Chair Warsh scrapped forward guidance in a 132-word ...</a></li>
<li><a href="https://cryptobriefing.com/fed-chair-warsh-communication-reforms/">Federal Reserve Chair Kevin Warsh proposes communication ...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#forward guidance`

---

<a id="item-finance-news-2"></a>
### [U.S. companies shift from buybacks to net share issuance](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

U.S. companies have shifted from net share repurchases in 2024 to net equity issuance equal to 3.1% of total market capitalization as of late last week, according to an Acadian Asset Management analysis. The change adds to the supply of shares the four-year-old bull market must absorb.

rss · CNBC Finance · Nov 20, 14:15

**「Background」** For years, U.S. companies were net buyers of their own shares through buybacks, which reduced the number of shares outstanding and helped lift per-share earnings; the Acadian analysis says that pattern has now reversed. A 2000 study by Malcolm Baker and Jeffrey Wurgler found that periods when companies issued relatively more equity than debt tended to precede weaker stock returns.

**「Impact」** If sustained, the added supply is a potential headwind for U.S. equity investors because it reverses the buyback-driven shrinkage of tradable shares that had helped support prices.

<details><summary>References</summary>
<ul>
<li><a href="https://www.jstor.org/stable/222488">The Equity Share in New Issues and Aggregate Stock Returns</a></li>

</ul>
</details>

**Tags**: `#equity issuance`, `#share buybacks`, `#US equities`, `#IPOs`, `#AI investment`

---