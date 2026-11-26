---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 36 items, 12 important content pieces were selected

---

**Technology News**
1. [1Password Confirms Customer Account Data Theft After GitHub Compromise](#item-tech-news-1) ⭐️ 8.0/10
2. [Tencent open-sources Hy4 flash GGUF weights; smallest runs on 64 GB Mac mini](#item-tech-news-2) ⭐️ 8.0/10
3. [Minecraft Java Edition RCE Found in Server Resource-Pack Fonts](#item-tech-news-3) ⭐️ 8.0/10
4. [Much Shorter Lean Version of Anthropic&\#x27;s GRH Verification](#item-tech-news-4) ⭐️ 7.0/10
5. [Windows Loudness Equalization Reimplemented for PipeWire](#item-tech-news-5) ⭐️ 7.0/10
6. [Google Research posts Cogentic papers on factorization and discrete logs](#item-tech-news-6) ⭐️ 7.0/10
7. [SemiAnalysis launches GDPx benchmark; top model scores 12% on release day](#item-tech-news-7) ⭐️ 7.0/10
8. [Report: Samsung, SK hynix to license parts of YMTC Xtacking for 3D NAND](#item-tech-news-8) ⭐️ 7.0/10
9. [FCC Approves SpaceX&\#x27;s 1 Million-Satellite Starmind Data Center Constellation](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [U.S. Plans New Section 301 Tariffs on 14 Trading Partners](#item-finance-news-1) ⭐️ 9.0/10
2. [Report: Commerce Department pressured Intel to cede 10% stake](#item-finance-news-2) ⭐️ 8.0/10
3. [Jensen Huang Returns to Nvidia, Highlighting U.S.-China AI Talent Competition](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [1Password Confirms Customer Account Data Theft After GitHub Compromise](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password confirmed a security incident in which attackers accessed internal systems and stole some customers’ names, email addresses, account identifiers, and account creation and last-login times. The company said customer vaults and their contents were not affected and did not disclose how many users were impacted. 1Password began investigating on November 19 after signs that an employee’s corporate GitHub account had been compromised; the attacker used it to access source code and push malicious code to backend services, which led to the data download. 1Password disabled the account, rotated or revoked potentially exposed internal credentials, and strengthened verification codes for invitation and recovery emails; it said users do not need to change their accounts but should watch for phishing.

hackernews · lxhrstn · Nov 25, 17:18 · [Discussion](https://news.ycombinator.com/item?id=50644817)

**「Background」** For a password manager, the critical distinction is between encrypted vault contents and account metadata: 1Password says the reported theft involved names, email addresses, account identifiers, and login timestamps, not customers&\#x27; vaults or the secrets inside them. The entry point described in the notice was an employee&\#x27;s corporate GitHub account, which the attacker used to reach source code and push malicious code into backend services rather than to break into a customer vault directly.

**「Impact」** For affected customers, the stolen email addresses and account metadata can make follow-up phishing messages more convincing, so unsolicited 1Password-branded messages should be verified through the service directly rather than through embedded links. 1Password says vault contents were not affected and that users do not need to change their accounts.

**「Community Discussion」** Commenters focused on the GitHub-to-production path: tptacek called a compromised employee laptop leading to code pushed to GitHub and deployed the standard SaaS breach pattern, while ctidd criticized the notice for not explaining whether branch protections or push restrictions failed. qixxiq reported receiving a convincing phishing email containing some personal details from a non-1Password domain.

**Tags**: `#security incident`, `#password managers`, `#supply chain security`, `#phishing`, `#SaaS security`

---

<a id="item-tech-news-2"></a>
### [Tencent open-sources Hy4 flash GGUF weights; smallest runs on 64 GB Mac mini](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 8.0/10

Tencent Hunyuan has released GGUF quantized weights for its 224B-parameter Hy4 flash model through its AngelSlim model-compression toolkit. The original weights are about 410.27GiB, while the smallest variant, IQ2-AH, is 125.73GiB — roughly 30% of the original — and Tencent says it can run on a 64 GB Mac mini using the Strata offload framework. The published figures put generation at 89 tokens per second at 10K context on a device with 48 GB of VRAM, and 47 tokens per second at 32K context with the Q3\_K version on a 128 GB M5 Max. On evaluations including DeepSWE v1.1, Tencent reports the Q3\_K version scoring within 0.4 points of the original model.

telegram · zaihuapd · Nov 25, 09:29

**「Background」** GGUF is a file format for loading models in local inference software, and quantization stores weights at lower precision to reduce file size and memory requirements. Hy4 flash is a 224B-parameter Tencent Hunyuan model whose original weights total about 410.27GiB, so quantized variants are intended to make the same model fit on much smaller hardware.

**「Impact」** The release gives local-inference users a path to a 224B model on hardware far below datacenter scale, but the memory figures imply real tradeoffs: the 64 GB Mac mini route relies on 2-bit-class IQ2-AH weights plus Strata offload, while the benchmarked 47 tokens per second at 32K context required a 128 GB M5 Max running Q3\_K. Users should check that their inference stack supports the Strata offload framework and GGUF before expecting the quoted speeds.

<details><summary>References</summary>
<ul>
<li><a href="https://original.ifeng.com/c/8yLCKwSsFD6">腾讯混元Hy4 flash开源GGUF量化权重 224B模型可跑在64GB Mac mini上</a></li>

</ul>
</details>

**Tags**: `#Hy4 flash`, `#model quantization`, `#GGUF`, `#local inference`, `#Strata offload`

---

<a id="item-tech-news-3"></a>
### [Minecraft Java Edition RCE Found in Server Resource-Pack Fonts](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

A public proof-of-concept published on November 22, minecraft2shell, shows that a crafted TrueType font delivered through a server resource pack can trigger a native out-of-bounds write in FreeType 2.14.3 and earlier and execute arbitrary code on the Minecraft Java Edition 26.3 Windows client. The flaw affects Java Edition 1.20.5 through 1.21.10 and snapshots 26.1 through 26.4; 1.20.4 and earlier and Bedrock Edition are not affected. Mojang still ships lwjgl-freetype 3.4.3 with no official patch, while the community fix m2sfix 1.0.0, released November 24, uses a Java agent or mod to disable hinting. The reporter advises against adding resource packs before a fix and recommends disabling multiplayer server resource-pack permissions or installing the temporary mod.

telegram · zaihuapd · Nov 25, 12:46

**「Background」** Minecraft: Java Edition renders custom TrueType fonts through FreeType, the open-source font engine it binds via LWJGL. Server resource packs can deliver those font files to the client, so a hostile pack can reach the font parser without the player installing anything separately. The minecraft2shell PoC exploits an out-of-bounds write in FreeType 2.14.3 and earlier; the community workaround disables font hinting so the font&\#x27;s own bytecode does not run.

**「Mitigation required」** Until Mojang ships a patch, affected Windows Java players who join a server that pushes a crafted resource pack can have arbitrary code executed on their machine. Players should set multiplayer server resource-pack permissions to &quot;disabled&quot; or install the community m2sfix 1.0.0 Java agent or mod.

<details><summary>References</summary>
<ul>
<li><a href="https://threatcluster.io/cluster/minecraft2shell-unpatched-freetype-rce-in-minecraft-java-via-7b380721">Minecraft2Shell: Unpatched FreeType RCE in Minecraft Java via ...</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/minecraft2shell-minecraft-java-rce-resource-pack.html">Minecraft2Shell RCE in Minecraft Java Still Unpatched</a></li>
<li><a href="https://github.com/sunrisemc-tw/minecraft2shell-fix">GitHub - sunrisemc-tw/minecraft2shell-fix: Client-side ...</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/minecraft2shell-minecraft-java-rce-resource-pack.html">Minecraft2Shell RCE in Minecraft Java Still Unpatched</a></li>

</ul>
</details>

**Tags**: `#Minecraft`, `#remote code execution`, `#FreeType`, `#security vulnerability`, `#resource packs`

---

<a id="item-tech-news-4"></a>
### [Much Shorter Lean Version of Anthropic&\#x27;s GRH Verification](https://github.com/lsernau/grh-lean) ⭐️ 7.0/10

A new GitHub repository, lsernau/grh-lean, presents a much shorter, more readable Lean version of the GRH verification associated with Anthropic, aimed at mathematicians and proof engineers who need to inspect the formalization. The item describes it as a refinement of existing work rather than a new mathematical breakthrough. Commenters report a reduction from roughly 17 million lines to about 76,000 lines, and one says the readable proof separates &quot;known math&quot; from &quot;new math&quot; and includes human-readable documentation; these line-count and readability claims come from comments, not independent verification.

hackernews · nb-t · Nov 25, 21:48 · [Discussion](https://news.ycombinator.com/item?id=50648050)

**「Earlier proof」** The shorter Lean formalization follows the November 20, 2026 announcement by Levent Alpöge of a proof of the Riemann Hypothesis and the Generalized Riemann Hypothesis for Dirichlet L-functions, found with Anthropic&\#x27;s Claude and released as a Lean proof comprising 175,187 files and about 17 million lines. That earlier release established the formal proof this repository condenses.

**「Impact」** For proof engineers, the practical value is auditability: if the reported ~76,000-line version is faithful to the original, it can be inspected and navigated far more easily than a multi-million-line formalization, especially with documentation marking known versus new material. The supplied material does not independently confirm fidelity or the line counts.

**「Community Discussion」** Commenters disagree about what the shorter proof settles: one asks whether proof-golfing LLMs already answer Terence Tao&\#x27;s recent concern that huge formal proofs can lack insight, while another wants mathematicians to grasp the core argument and present it in a conventional paper or conference talk. A commenter also links to a Lean Zulip discussion.

<details><summary>References</summary>
<ul>
<li><a href="https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/">Alpöge/Claude proof of the Generalized Riemann Hypothesis</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#AI-assisted proof`, `#GRH`, `#proof engineering`

---

<a id="item-tech-news-5"></a>
### [Windows Loudness Equalization Reimplemented for PipeWire](https://github.com/xoxorwr/pw-loudness-eq) ⭐️ 7.0/10

A developer has published pw-loudness-eq on GitHub, a project that reverse-engineers Windows&\#x27; loudness equalization and reimplements the processing for PipeWire, the Linux audio server. It is a third-party repository, not an official PipeWire or Microsoft component, and the supplied material does not specify a release version or supported PipeWire versions. The port targets PipeWire users who want Windows-style loudness treatment in their audio chain.

hackernews · ThrowNotAway · Nov 25, 11:34 · [Discussion](https://news.ycombinator.com/item?id=50641171)

**「Background」** The project targets PipeWire, the Linux audio server, so the port has to reproduce a Windows sound-enhancement behavior outside Windows&\#x27; own audio stack. On Windows, Loudness Equalization is exposed as a selectable enhancement with a configurable release time, according to user reports.

**「Impact」** PipeWire users gain a way to apply the Windows loudness treatment inside a Linux audio graph, but because the implementation is a separate repository, compatibility and maintenance depend on that project rather than on PipeWire&\#x27;s release cycle.

**「Community Discussion」** Commenters disputed the terminology and the need for the port: one argued that the effect is loudness normalization rather than equalization and warned that the described algorithm can boost focused impulses such as pure tones unless a limiter is added, while others questioned why reverse-engineering a Windows DLL was necessary and suggested a standard limiter instead. Another commenter noted that Windows applies a limiter on shared-mode WASAPI, DirectSound, and MME playback but not on WASAPI exclusive or ASIO.

<details><summary>References</summary>
<ul>
<li>How do I properly set up the &#x27;Loudness Equalization</li>

</ul>
</details>

**Tags**: `#audio processing`, `#reverse engineering`, `#PipeWire`, `#Windows`, `#open source`

---

<a id="item-tech-news-6"></a>
### [Google Research posts Cogentic papers on factorization and discrete logs](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research has published a collection titled \`cogentic\_research\_papers\` in its public google-research GitHub repository, with work on integer factorization and discrete logarithms among the topics. The supplied item provides no abstracts, methods, results, or peer-review status, so it does not establish any advance against deployed cryptographic systems.

hackernews · rgwohlbold · Nov 25, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50642086)

**「Why these papers draw scrutiny」** Integer factorization and discrete logarithms underpin RSA encryption and Diffie–Hellman key exchange, so asymptotic improvements to either problem attract attention even when they do not threaten deployed key sizes. An external report on the release describes a 54-page paper claiming that an AI system closed a 34-year-old theoretical gap in factoring, while noting that the work does not break modern encryption and has not been verified by outside mathematicians.

**「Community discussion」** Hacker News commenters mostly speculated about broader implications: one cited rumors from “credible people” that this is “the tip of something bigger,” while others connected the release to recent mathematics results and AI systems exploring large search spaces. No supplied comment reported reading the papers or offered a technical assessment.

<details><summary>References</summary>
<ul>
<li><a href="https://www.rdworldonline.com/google-cogentic-ai-integer-factoring-bounds-lean-proofs/">Google’s Gemini 4 agent claims six math proofs in a day ...</a></li>

</ul>
</details>

**Tags**: `#cryptography`, `#integer-factorization`, `#discrete-logarithms`, `#google-research`, `#research-papers`

---

<a id="item-tech-news-7"></a>
### [SemiAnalysis launches GDPx benchmark; top model scores 12% on release day](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis released GDPx, a benchmark covering 11 domains it considers most valuable for frontier intelligence — chip design, cybersecurity, biology, finance, legal, quant trading, recursive self-improvement, hardware design, materials science, alignment, and software engineering — built with 14 specialized data partners into 206 tasks. The authors say comprehensive benchmarks such as GDPVal and Agent&\#x27;s Last Exam err by picking domains from share of GDP or the O\*NET taxonomy, and GDPx instead drops sectors like government and real estate. On release day the top model, Opus 5.5, scored just 12%, which SemiAnalysis argues leaves headroom to separate future releases, unlike saturated benchmarks such as Terminal Bench 4.0. The post also reports that safety classifiers depressed overall scores for Fable 5.2 and GPT-6.2 Astra in cyber, biology, and alignment, and presents an adjusted leaderboard that excludes those three domains and applies partial grading to legal and finance; the excerpt is truncated before the resulting scores are shown.

rss · Semianalysis · Nov 26, 00:05

**「Why another AI benchmark」** GDPx is a new benchmark from SemiAnalysis, launched on November 1, that focuses on the domains where frontier AI is expected to have the most impact rather than the largest share of GDP. The source says most agentic benchmarks cover only one domain, while broad ones such as GDPVal and Agent’s Last Exam select tasks using GDP percentages or the O\*NET occupation taxonomy. GDPx instead uses 206 tasks made with 14 specialized data partners across chip design, cybersecurity, biology, finance, legal, quant trading, recursive self-improvement, hardware design, materials science, alignment, and software engineering.

**「Impact」** Anyone comparing frontier models on GDPx has to account for two scoring conditions the authors flag: safety classifiers in cyber, biology, and alignment can lower a model&\#x27;s total, and legal and finance default to binary grading, so SemiAnalysis&\#x27;s partial-grading variant produces a different ranking. Because the release-day ceiling was 12%, GDPx scores are not comparable to benchmarks where top models exceed 50%, and the post says the benchmark launched November 1, with Anthropic, OpenAI, Google&\#x27;s Gemini 4 series, Alibaba, and Moonshot all shipping new models since.

**Tags**: `#AI benchmarks`, `#frontier models`, `#model evaluation`, `#AI industry analysis`

---

<a id="item-tech-news-8"></a>
### [Report: Samsung, SK hynix to license parts of YMTC Xtacking for 3D NAND](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

A report says Samsung Electronics and SK hynix have agreed, through a cross-licensing arrangement, to use parts of Yangtze Memory Technologies&\#x27; \(YMTC\) Xtacking stacking technology in 3D NAND flash. All three companies declined to comment, and no license terms, scope, or timetable were disclosed, so the arrangement remains unconfirmed. Xtacking builds the memory-cell array and the CMOS control circuitry on separate wafers and bonds them together, allowing the two parts to be manufactured and optimized independently. An Omdia senior analyst quoted in the report said the approach would let a NAND maker produce its own memory array while having logic circuitry fabricated by a foundry on a more advanced process.

telegram · zaihuapd · Nov 25, 14:33

**「Background」** Xtacking is YMTC&\#x27;s 3D NAND architecture, introduced in 2018, in which the memory-cell array and peripheral CMOS logic are fabricated on separate wafers and then joined face-to-face by wafer bonding. This split allows the array and logic portions to be produced and optimized independently.

**「Impact」** If confirmed, the licenses would give Samsung and SK hynix a route to split NAND array and logic production and to source control circuitry from foundries on advanced nodes, an option that conventional monolithic NAND flows do not offer. Because only &quot;part&quot; of Xtacking is said to be covered and none of the parties confirmed any terms, the practical scope — which nodes, products, or volumes — remains unknown.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Yangtze_Memory_Technologies">Yangtze Memory Technologies - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#3D NAND`, `#Xtacking`, `#半导体制造`, `#三星`, `#SK 海力士`

---

<a id="item-tech-news-9"></a>
### [FCC Approves SpaceX&\#x27;s 1 Million-Satellite Starmind Data Center Constellation](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 7.0/10

GeekWire reports that the U.S. Federal Communications Commission approved SpaceX to deploy up to 1 million satellites for Starmind, an orbital data-processing network, operating at altitudes of 500 to 1,002 kilometers. According to the report, the FCC described it as the first U.S. approval of a space data-center constellation. The authorization carries conditions including backup communications, periodic progress reports and a detailed orbital-debris-mitigation plan, with the first satellite required to be operational no later than 2033 and the full constellation running by 2040.

telegram · zaihuapd · Nov 26, 04:45

**「Background」** SpaceX had applied to the FCC for authority to operate a non-geostationary system of up to one million satellites, and the application was accepted for review in October 2026, according to contemporaneous reports \(tool-2-1, tool-2-3\). The November approval acts on that pending request and clears the Starmind orbital data-processing network under specified conditions.

**「Impact」** The FCC rejected objections from Amazon, Viasat and the American Astronomical Society, so the Starmind authorization proceeds over their opposition; the source does not describe the grounds of those objections or the relief the parties sought.

<details><summary>References</summary>
<ul>
<li>SpaceX Seeks FCC Approval for 1 Million Satellites</li>
<li>Starlink urges orbital data sharing as SpaceX proposes Starmind - NeoTeo</li>

</ul>
</details>

**Tags**: `#SpaceX`, `#FCC`, `#orbital data centers`, `#satellite constellations`, `#space infrastructure`

---

## Financial News

<a id="item-finance-news-1"></a>
### [U.S. Plans New Section 301 Tariffs on 14 Trading Partners](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 9.0/10

The U.S. is reportedly preparing country-specific tariffs on 14 trading partners, including China, the EU, Japan and India, under Section 301 of the 1974 Trade Act, targeting manufacturing overcapacity. China would face an additional 20% on top of existing 25% tariffs, rising to a possible 40% if it breaches the October 2025 Busan trade truce, according to the report; new rates would not exceed those already published in reciprocal trade framework agreements and would not stack on existing duties for other partners.

telegram · zaihuapd · Nov 25, 13:59

**「Background」** The proposal follows an eight-month investigation under Section 301 of the 1974 Trade Act, which lets Washington act against foreign trade practices it deems unfair, and the China escalation is tied to a one-year trade truce Trump and Xi agreed at the October 2025 Busan summit.

**「Affected parties」** If finalized, the duties would fall on U.S. importers sourcing manufactured goods from China, the EU, Japan, India and the other named partners, raising their landed costs. The measures are proposals announced on November 25, 2026, so the rates are not final.

<details><summary>References</summary>
<ul>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on China...</a></li>
<li><a href="https://ustr.gov/about/policy-offices/press-office/press-releases/2026/november/ustr-makes-determinations-and-proposes-actions-14-section-301-investigations-relating-structural">USTR Makes Determinations and Proposes Actions in 14 Section 301 ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Busan_Summit">Busan Summit - Wikipedia</a></li>
<li><a href="https://www.cfr.org/articles/united-states-and-china-agree-trade-truce">United States and China Agree to Trade Truce | Council on ...</a></li>
<li><a href="https://globalimportblog.bakermckenzie.com/2026/11/25/us-ustr-proposes-section-301-tariffs-on-14-economies-over-structural-excess-capacity/">US: USTR Proposes Section 301 Tariffs on 14 Economies Over ...</a></li>

</ul>
</details>

**Tags**: `#US tariffs`, `#Section 301`, `#China trade`, `#EU/Japan/India`, `#trade policy`

---

<a id="item-finance-news-2"></a>
### [Report: Commerce Department pressured Intel to cede 10% stake](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 8.0/10

Court documents reportedly show that a U.S. Commerce Department lawyer told Intel’s CFO in August 2025 that the board could refuse the government’s demand but warned of unpredictable consequences; days later, Intel handed over a 10% equity stake, now worth about $11 billion, without payment, according to WIRED.

telegram · zaihuapd · Nov 25, 13:25

**「Background」** Intel is a major U.S. chipmaker, and the reported August 2025 call came before its board agreed to transfer the 10% stake to the U.S. government.

**「Who is affected」** Intel&\#x27;s existing shareholders bear the direct cost: the reported handover of a 10% stake without payment dilutes their ownership without bringing new cash into the company, while giving the U.S. government a significant voice in its governance.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theverge.com/news/764480/intel-donald-trump-lip-bu-tan-deal">US government takes 10 percent stake in Intel in... | The Verge</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#US government equity stake`, `#semiconductor industry`, `#industrial policy`, `#Commerce Department`

---

<a id="item-finance-news-3"></a>
### [Jensen Huang Returns to Nvidia, Highlighting U.S.-China AI Talent Competition](https://www.cnbc.com/2026/11/25/jensen-huang-nvidia-ai-talent-race.html) ⭐️ 7.0/10

Jensen Huang resigned as Nvidia’s CEO on Nov. 12 after reports of an affair with a woman U.S. intelligence reportedly believed had links to Chinese intelligence, and returned on Nov. 23, when Nvidia shares surged. The episode has spotlighted U.S.-China competition for AI talent; China has overtaken the U.S. in share of global AI talent within three years, according to Carnegie Endowment research cited by CNBC.

rss · CNBC Finance · Nov 25, 14:29

**「Background」** Huang resigned as Nvidia&\#x27;s CEO on Nov. 12 after reports of an affair with a woman U.S. intelligence reportedly suspected had links to Chinese intelligence, and returned on Nov. 23. The episode unfolded as China&\#x27;s share of top AI talent rose to 40.6% in 2025 from 27.1% in 2022, while the U.S. share fell to 34.2% from 46.4%, according to Carnegie Endowment research.

**「Impact」** AI firms are already competing on pay: CNBC reports U.S. engineers earn two to three times their Chinese counterparts, and recruiter Rachel Wu says job switches can bring 25%–30% raises.

<details><summary>References</summary>
<ul>
<li><a href="https://www.physixfrontier.com/en/detail.html?id=375">Carnegie Report: China&#x27;s Top AI Talent Share Rises to 40.6% ...</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/12/nvidia-ceo-jensen-huang-resigns">Jensen Huang resigns as Nvidia CEO after alleged... | The Guardian</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#US-China AI competition`, `#AI talent`, `#semiconductor industry`, `#executive leadership`

---