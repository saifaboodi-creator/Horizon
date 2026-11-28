---
layout: default
title: "Horizon Summary: 2026-11-28 (AR)"
date: 2026-11-28
lang: ar
---

> From 30 items, 10 important content pieces were selected

---

**Technology News**
1. [OpenSec يكشف عن ثغرة NFS حرجة في نواة Linux تتيح root قبل المصادقة](#item-tech-news-1) ⭐️ 8.0/10
2. [DeepCrossAttention من Google Research: جودة مماثلة وسرعة تصل إلى 3x](#item-tech-news-2) ⭐️ 7.0/10
3. [بلاغ: مهارات Convex ترفع أفكار التطبيقات إلى خادم بعيد دون إفصاح](#item-tech-news-3) ⭐️ 7.0/10
4. [تقرير أمني: نصوص سكيمينغ تستغل WebRTC على مواقع تسوق شائعة](#item-tech-news-4) ⭐️ 7.0/10
5. [مدّعون عامّون في ولايات أمريكية يقاضون SpaceX بسبب صور مولّدة عبر Grok](#item-tech-news-5) ⭐️ 7.0/10
6. [مقال يجادل بأن البراهين المُتحقَّق منها حاسوبيًا قد تكون خاطئة](#item-tech-news-6) ⭐️ 7.0/10
7. [ثغرة حزم موارد في «ماينكرافت بيدروك» تُصلح في الإصدار 26.65](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [مجلس الدولة الصيني يدعو إلى تعزيز دور &quot;الفريق الوطني&quot; في تثبيت سوق الأسهم](#item-finance-news-1) ⭐️ 8.0/10
2. [تقرير: ميكسي تكتتب بـ500 مليون يوان في جولة تمويل لـDeepSeek بحجم 100–105.5 مليار يوان](#item-finance-news-2) ⭐️ 7.0/10
3. [الصين تخفض حد الشراء الفردي لشهادات الإيداع الكبيرة إلى 100 ألف يوان](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenSec يكشف عن ثغرة NFS حرجة في نواة Linux تتيح root قبل المصادقة](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

نشر OpenSec تفاصيل الثغرة CVE-2026-99362، وهي تجاوز سعة في كومة نواة Linux داخل خادم nfsd تُصنَّف بـ CVSS 9.8 وتُوصف بأنها قابلة للاستغلال قبل المصادقة؛ ووفق الإعلان، تكفي اتصال واحد إلى tcp/2049 لكتابة خارج الحدود والوصول إلى صدفة root. تشمل الأنظمة المتأثرة المضيفات التي تشغّل NFSv4.1 أو 4.2 منذ Linux 3.16 \(2014\)، مثل خوادم الملفات وأجهزة NAS وعقد التخزين العنقودية. وأُعلنت إصلاحات في 6.12.117 و6.18.61 و7.3.2 و7.4-rc1 وتتطلب ترقية النواة وإعادة التشغيل، مع إمكانية تقييد tcp/2049 كحل مؤقت؛ ووفق المصدر، جرى الكشف عن CVE علنًا في 20 نوفمبر 2026، ولم يتضمن المصدر تأكيدًا مستقلًا له.

telegram · zaihuapd · Nov 27, 12:57

**「الخلفية」** يكمن السياق التقني في أن خادم nfsd المدمج في نواة لينكس يستمع إلى المنفذ tcp/2049، وأن مسار ذاكرة الرد المؤقتة لجلسات NFSv4.1/4.2 كان قابلاً للوصول من طلب عميل قبل المصادقة. ووفقاً لسجل Red Hat فإن الكتابة خارج الحدود تُستثار عبر التفاوض على حجم رد مؤقت أدنى وإرسال طلبات مركّبة تتضمن عمليات SEQUENCE، ويشير OpenCVE إلى أن المشكلة توجد في الإصدارات التي لا تحتوي فحص حدود مخزن التسلسل المُحدّث. وتذكر المصادر أن الثغرة ترافق مكوّن nfsd منذ إدخاله في نواة Linux 3.16 عام 2014، وقد صُنّفت 9.8 من جهة CNA الخاصة بالنواة و9.4 من Red Hat.

**「الأثر」** على مسؤولي الأنظمة تحديد الخوادم التي تفعّل NFSv4.1 أو 4.2 وترقية النواة إلى إصدار مُصلَح مع إعادة التشغيل، أو حصر الوصول إلى tcp/2049 كإجراء مؤقت؛ وهذا الحصر قد يقطع اتصال عملاء NFS الشرعيين ما لم يُضبط بعناية.

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
### [DeepCrossAttention من Google Research: جودة مماثلة وسرعة تصل إلى 3x](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 7.0/10

قدّمت Google Research تقنية DeepCrossAttention لتحسين كفاءة المحوّلات، وتقول إنها تحقق جودة نموذج مماثلة مع تشغيل أسرع يصل إلى ثلاثة أضعاف. وجاء ذلك في منشور بعنوان «Supercharging Transformer Residual Connections» بحسب العنوان المتاح. الادعاء بالسرعة والجودة هو ادعاء الجهة المطوّرة، ولا يتضمن المحتوى المتاح تفاصيل تقنية أو تحققًا مستقلًا.

hackernews · ComputedCamp995 · Nov 27, 23:06 · [Discussion](https://news.ycombinator.com/item?id=50672565)

**「الخلفية」** تعتمد شبكات المحولات التقليدية على وصلات متبقية ثابتة تجمع مخرجات كل طبقة في تمثيل جارٍ، وهو ما قد يؤدي مع العمق إلى تخفيف معلومات الطبقات السابقة. تقترح DeepCrossAttention من Google Research استبدال هذا المسار الثابت بأوزان قابلة للتعلّم وانتباه متقاطع عبر العمق لدمج مخرجات الطبقات السابقة ديناميكياً. وُصفت التقنية في ورقة على arXiv في فبراير 2025، وعُرضت في ICML 2025 قبل نشرها على مدونة البحث.

**「أثر عملي للمطوّرين」** بالنسبة لفرق تدريب النماذج، قد تتيح DeepCrossAttention تقليل عمق الشبكة على معيار LM1B من 42 طبقة إلى 30 مع مطابقة مستوى الحيرة \(perplexity\) وإضافة أقل من 0.2% إلى عدد المعلمات، وفق نتائج Google. لكن على الفرق اختبارها على أحمالها الخاصة قبل الاعتماد عليها، لأن الأدلة المتاحة نتيجة معيارية من الجهة المطوّرة وليست تحققاً مستقلاً.

**「نقاش المجتمع」** انتقد أحد المعلّقين استخدام رسوم خطية لعرض مقارنة بين طرق منفصلة، معتبرًا أن الرسوم الشريطية أنسب لغياب علاقة زمنية. وسأل معلّق آخر عمّا إذا كانت الإضافة قد ترفع مكاسبه من نحو 10x إلى 30x في tokens/sec بعد تحسينات سابقة؛ وهذه آراء وتجارب معلّقين لا تُعد تحققًا مستقلًا من ادعاء Google Research.

<details><summary>References</summary>
<ul>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention: Supercharging Transformer ...</a></li>
<li><a href="https://aiweekly.co/alerts/googles-deepcrossattention-trains-transformers-up-to-3x-faster">Google&#x27;s DeepCrossAttention trains transformers up to 3x faster</a></li>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://aiweekly.co/alerts/googles-deepcrossattention-trains-transformers-up-to-3x-faster">Google&#x27;s DeepCrossAttention trains transformers up to 3x ...</a></li>

</ul>
</details>

**Tags**: `#transformers`, `#attention mechanisms`, `#model efficiency`, `#Google Research`, `#deep learning`

---

<a id="item-tech-news-3"></a>
### [بلاغ: مهارات Convex ترفع أفكار التطبيقات إلى خادم بعيد دون إفصاح](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

تزعم مشكلة على GitHub رقم 64 في مستودع convex-backend-skill أن مهارات Convex ترسل أفكار تطبيقات المستخدمين، بصيغة مطالبات نصية، إلى خادم بعيد من دون إفصاح واضح. ردّ الرئيس التنفيذي لـConvex، Jamie، بأن رفع المطالبات يشغّل ميزة «quickstart»، التي وصفها بالخليفة الروحي لمنتج Convex Chef الذي أُوقف مؤخراً. المصدر المتاح هو بلاغ في المستودع وردّ رسمي، ولا يقدّم قياساً مستقلاً لنطاق الإرسال أو دليلاً على نية خبيثة.

hackernews · MickyTheMouse · Nov 27, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50669765)

**「الخلفية」** قال الرئيس التنفيذي لـ Convex في تعليقه إن الشركة أوقفت مؤخراً منتج «Convex Chef»، وهو منتج بناء تطبيقات شامل \(«vibe-coding»\)، وإن رفع الطلب \(prompt\) في هذه الإضافة يشغّل ميزة «quickstart» التي يصفها بأنها خليفتها الروحية. وكان وصف سابق على موقع Convex يبيّن أن Chef يبني تطبيقاً من وصف نصي مع خلفية Convex ومصادقة وواجهة فورية أثناء العمل \(tool-1-1\). وتصف صفحة المهارة وظيفة quickstart بأنها تشغيل قالب Convex + ويب انطلاقاً من فكرة من جملة واحدة \(tool-1-3\)، بينما ذكر تقرير تقني أن هذه المهارات ترسل فكرة التطبيق إلى نطاق convex.site \(tool-1-2\).

**「الأثر العملي」** على المطورين الذين يستخدمون إضافة convex-backend-skill ويُدخلون أفكاراً أو تفاصيل حساسة أن يفترضوا أن نص المطالبة قد يُرفع إلى خادم بعيد لتشغيل «quickstart»، وفق وصف الرئيس التنفيذي، وأن يقرروا ما إذا كانوا يقبلون ذلك قبل الاستخدام.

**「نقاش المجتمع」** رأى أحد المعلقين أن النماذج المفتوحة الأوزان ذات الاستضافة الذاتية هي المسار الأفضل على المدى الطويل، بينما ذهب آخر إلى أن حقن المطالبات أكثر شيوعاً من استدعاء النماذج لأدوات خبيثة من تلقاء نفسها. هذه آراء معلّقين وليست تأكيداً مستقلاً للبلاغ.

<details><summary>References</summary>
<ul>
<li><a href="https://www.convex.dev/examples/chef">Chef - convex.dev</a></li>
<li><a href="https://codingislove.com/convex-skills-data-remote-server/">Convex&#x27;s agent skills send your app idea to a remote server</a></li>
<li><a href="https://www.skills.sh/convex/agent-skills/convex-quickstart">convex-quickstart — convex/agent-skills</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#security`, `#AI coding tools`, `#Convex`, `#data handling`

---

<a id="item-tech-news-4"></a>
### [تقرير أمني: نصوص سكيمينغ تستغل WebRTC على مواقع تسوق شائعة](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

يفيد تقرير أمني بأن نصوصاً برمجية لسرقة بيانات بطاقات الائتمان وُجدت على مواقع تسوق شائعة وتستخدم WebRTC ضمن أسلوب الهجوم. لا تتوافر في المادة المصدرية تفاصيل عن المتاجر المتأثرة أو عددها أو الجهة التي أصدرت التقرير، ما يحدّ من تقييم نطاق الحملة ومدى انتشارها. يأتي ذلك في سياق مخاطر النصوص الخارجية المضمّنة في صفحات الدفع، وهي نقطة ركّز عليها النقاش المرافق.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「السياق: سكيمنغ الشيفرة الخارجية في صفحات الدفع」** ليست هجمات «سكيمنغ» صفحات الدفع جديدة: رصد باحثون سابقًا سكربتات مسروقة لبيانات البطاقات مزروعة في أكثر من 200 متجر جامعي، وهي الحادثة التي تسرق رقم البطاقة وتاريخ انتهائها ورمز التحقق واسم الحامل إضافة إلى بيانات الفوترة، ويُعرف هذا النمط عمومًا باسم Magecart ويعتمد على حقن شيفرة طرف ثالث في صفحة إتمام الشراء بدل اختراق خادم المتجر نفسه. ولهذا تشترط معايير PCI DSS في المتطلبين 6.4.3 و11.6.1 أن تكون سكربتات صفحات الدفع مصرّحًا بها ومُتحقَّقًا من سلامتها ومراقَبة بحثًا عن أي تلاعب، وهو ما يفسّر تركيز التقارير الأمنية على الشيفرة الخارجية المضمَّنة في مواقع التجارة الإلكترونية.

**「الأثر」** الخطر المباشر الذي تصفه الحملة هو إمكان اعتراض بيانات البطاقة أثناء الدفع، ما يجعل مراجعة النصوص الخارجية على صفحات الدفع وتقييد صلاحياتها إجراءً وقائياً مرتبطاً بالحادث.

**「نقاش المجتمع」** قلّل أحد المعلّقين من دور WebRTC بوصفه السبب الجوهري، معتبراً أنه أقل مراقبة وأن الهجوم كان يمكن تنفيذه عبر طلبات HTTP، ومؤكداً أن تضمين نصوص طرف ثالث يبقي الموقع عرضة للخطر. ورأى آخرون أن حجب الإعلانات مبرر بسبب مخاطر كهذه، وطالب أحدهم بعزل إعلانات الشبكات الإعلانية ومنع تنفيذ JavaScript داخلها، بينما ذهب معلّق إلى أن اعتماد أسرار متماثلة في المدفوعات هو الخلل الأساسي.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/over-200-college-campus-stores-infected-with-card-stealing-scripts/">Over 200 College Campus Stores Infected with Card Stealing Scripts</a></li>
<li><a href="https://community.norton.com/t/false-positive-url-cardstealer-still-blocking-our-site-9-months-after-resolved-incident/525586">False Positive – URL:CardStealer still blocking our... - Norton Community</a></li>
<li><a href="https://origami.sa/en/blog/third-party-script-card-skimming-checkout/">Optimizely Hack: An Outside Tool Planted a Card Skimmer on 178...</a></li>

</ul>
</details>

**Tags**: `#web security`, `#payment skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-5"></a>
### [مدّعون عامّون في ولايات أمريكية يقاضون SpaceX بسبب صور مولّدة عبر Grok](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

رفعت مجموعة من المدّعين العامّين في ولايات أمريكية دعوى قضائية ضد شركة SpaceX بصفتها الشركة الأم لـ xAI وروبوت الدردشة Grok، زاعمين أن المنصّة مكّنت من إنشاء مواد استغلال جنسي للأطفال وصور حميمية غير رضائية. وتذكر نشرة صادرة عن مكتب المدعي العام في فرجينيا أن الدعوى تقدّمت بها personally المدّعي العام جاي جونز ونظيره رايفيلد. والدعوى في مرحلة الرفع الأولية، ولم تصدر بعد أي نتيجة قضائية، ولا تتضمن المواد المتاحة تفاصيل تقنية عن كيفية تجاوز ضوابط Grok أو عن الأدلة المقدَّمة.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「سياق الدعوى」** تُعرِّف الدعوى شركة SpaceX بأنها الشركة الأم لـ X وxAI وGrok، وهو ما يفسر توجيه الاتهام إليها بدلًا من الشركة المطوِّرة للنموذج وحده. ورفعت النائبة العامة في فرجينيا جاي جونز الدعوى بالتعاون مع نظيرتها في أوريغون دان رايفيلد، التي أقامت إجراءً منفصلًا لكنه مشابه، ويطلب الطرفان عقوبات مدنية وأوامر قضائية تُلزم Grok وX بوقف إنشاء الصور الجنسية غير الرضائية وتوزيعها. وما زالت هذه ادعاءات لم يبتّ فيها القضاء بعد، فالمادة المتاحة تصف رفع دعوى وليست حكمًا قضائيًا.

**「التبعات القانونية」** ستصطدم الدعوى بحدود قانونية غير محسومة: فوفق نتائج بحث، قضت محكمة استئناف فيدرالية \(الدائرة السابعة\) بأن حيازة صور اعتداء جنسي على أطفال مولّدة بالذكاء الاصطناعي للاستخدام الخاص تبقى ضمن حرية التعبير المحمية، مع التمييز بين الحيازة والتوزيع — ما يرجّح أن يتركّز النزاع على التوزيع والترويج والصور غير الرضائية لأشخاص حقيقيين بدلًا من مجرد التوليد. أما بالنسبة للمنصات والمطوّرين، فإن مقاضاة SpaceX بوصفها الشركة الأم لـ xAI/Grok توسّع نطاق المسؤولية المحتملة ليشمل الكيان الحاضن لا مطوّر النموذج وحده، وهو ما لم يُحسم بعد لأن الدعوى في مرحلة الاستئناف الأولية.

**「نقاش المجتمع」** تساءل أحد المعلّقين عمّا إذا كانت ضوابط Grok كانت متساهلة افتراضيًا مع الجميع أم أن المستخدمين اضطروا إلى «خداع» النموذج لحمله على توليد هذا المحتوى، بينما طالب آخر بمحاسبة الأشخاص الذين يقومون بذلك بأنفسهم. وذهب معلّق ثالث إلى أن المحكمة العليا سبق أن قضت بأن إنتاج مواد استغلال جنسي للأطفال بالذكاء الاصطناعي للاستهلاك الشخصي يندرج ضمن حرية التعبير، مع استثناءات تخص الأطفال الحقيقيين — وهو ادعاء قانوني يطرحه المعلّق ولا تؤكده المواد المتاحة.

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
### [مقال يجادل بأن البراهين المُتحقَّق منها حاسوبيًا قد تكون خاطئة](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

نُشر على cr.yp.to مقال يجادل بأن البراهين التي يتحقق منها الحاسوب يمكن أن تكون خاطئة عندما يحتوي مدقق البرهان نفسه على خطأ في سلامته \(soundness bug\)، وهو ما يخص ممارسي التحقق الشكلي ومدققات مثل Lean وMetamath. ولا يعلن المقال عن إصدار أو حادثة جديدة، بل يفحص حدود الثقة في وصف «مُتحقَّق منه حاسوبيًا»؛ إذ لا يكفي اجتياز المدقق وحده لإثبات صحة النتيجة إذا كان المدقق غير سليم.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「سياق: ما هي أخطاء السلامة في مدقّقات البراهين؟」** يعتمد ضمان «البرهان المُدقَّق حاسوبيًا» على أن نواة المدقّق \(kernel\) لا تقبل إلا اشتقاقًا صحيحًا؛ وخطأ السلامة \(soundness bug\) هو خلل في المدقّق نفسه يسمح لعبارة كاذبة بالمرور. وصفحة د. ج. برنشتاين على cr.yp.to هي في الأساس فهرس يجمع روابط لتقارير عن أخطاء سلامة منشورة، ويغطي سبعة أنظمة هي HOL Light وMizar وMetamath وIsabelle وLean وHOL98/HOL4 وCoq/Rocq. وقد أشار برنشتاين عند نشر الصفحة إلى أنها تضم روابط إلى 199 تقريرًا عن أخطاء سلامة في عدة برامج مهمة لتدقيق البراهين.

**「الأثر」** على الفرق التي تستخدم التحقق الشكلي في البرمجيات أو الرياضيات أن تتعامل مع نتيجة مدقق واحد كدليل قابل للطعن لا كحكم نهائي، وأن تضيف مدققًا مستقلًا أو مراجعة بشرية عندما يكون الخطر مرتفعًا. وتذكر التعليقات أن قواعد Metamath الكبرى تشترط بالفعل خمسة مدققات مستقلة مكتوبة بخمس لغات برمجة، ما يعني أن خطأً واحدًا في مدقق لا يكفي لقبول برهان خاطئ في تلك القواعد.

**「نقاش المجتمع」** يقدّم twotwotwo حجة مفادها أن الفجوة بين تحقق خاطئ واحد وتضليل الرياضيين تتطلب أخطاء في عدة مدققات وعدم ظهور البرهان بمظهر غير معقول في المراجعة غير الرسمية، ويذكر أن باحثًا من DeepMind صنع «برهانًا» اجتاز Lean ونسخة عمرها أسبوع من nanoda باستغلال خطأ مختلف في كل منهما. وفي المقابل يقلّل gr\_norm من الخطر لأن أخطاء السلامة الصوتية في أدوات عمرها عقود قليلة العدد، بينما يشير dwheeler إلى أن قواعد Metamath لا تقبل البرهان إلا بعد خمسة مدققات مستقلة، ويطرح andai مشكلة إثبات شيء صحيح وفق فهم خاطئ للمطلوب.

<details><summary>References</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb) - cr.yp.to</a></li>
<li><a href="https://news.lavx.hu/article/d-j-bernstein-catalogs-soundness-bugs-in-seven-proof-checkers">D. J. Bernstein catalogs soundness bugs in seven proof ...</a></li>
<li><a href="https://x.com/hashbreaker/status/2120889008389837049">Daniel J. Bernstein on X: &quot;Posted new page &quot;False computer ...</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-7"></a>
### [ثغرة حزم موارد في «ماينكرافت بيدروك» تُصلح في الإصدار 26.65](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

أبلغ مطور الإضافات 8Crafter في 15 نوفمبر عن ثغرة في حزم موارد «ماينكرافت» بيدروك تسمح لحزمة تحتوي ملف content.zipe بتعديل ملفات واجهة Ore UI وتشغيل تعليمات برمجية مخفية. وقال إن الإصدارات 26.52 حتى 26.63 مؤكدة التأثر، مع احتمال تأثر إصدارات أقدم، على أجهزة الكمبيوتر والهواتف والأجهزة المنزلية، بينما لا يتأثر إصدار Java. وعند تفعيل التنزيل التلقائي للموارد عند دخول خادم أو Realm، قد يتلقى اللاعب الملفات دون تثبيت يدوي؛ وتشمل الاستغلالات المذكورة حذف جميع الحفظات والحصول على عنوان IP للاعب، وعلى Windows فتح URI عشوائي وتشغيل ملف دفعي لتنزيل برمجيات خبيثة في ظروف محددة. أصلحت Mojang المشكلة في الإصدار 26.65.

telegram · zaihuapd · Nov 27, 18:04

**「الخلفية」** يستخدم إصدار Bedrock واجهة Ore UI المبنية بـ React وTypeScript، ويمكن لملف content.zipe داخل حزمة موارد أن يعدّل ملفات هذه الواجهة، ما يجعل حزمة تبدو كتخصيص مرئي قادرة على تنفيذ سلوك خارج نطاقها. كشف 8Crafter المشكلة في 15 نوفمبر 2026، وصدر 26.65 في 16 نوفمبر 2026 كإصلاح عاجل لنظام Windows فقط، وفق توثيق Minecraft Wiki.

**「الأثر」** يتعين على اللاعبين ومشغلي الخوادم الترقية إلى الإصدار 26.65، وتوخي الحذر عند تفعيل التنزيل التلقائي لحزم الموارد من خوادم أو عوالم غير موثوقة. وأداة AxmBro لنظام Windows تكتشف وجود ملف content.zipe لكنها لا تحكم بما إذا كانت الحزمة خبيثة، لذا لا تكفي وحدها للتحقق.

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
### [مجلس الدولة الصيني يدعو إلى تعزيز دور &quot;الفريق الوطني&quot; في تثبيت سوق الأسهم](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

دعا اجتماع تنفيذي لمجلس الدولة الصيني برئاسة رئيس الوزراء لي تشيانغ في 27 نوفمبر إلى تعزيز دور &quot;الفريق الوطني&quot; في تثبيت سوق الأسهم وتحسين وظيفة &quot;صندوق شبه استقرار&quot; لدى شركة تشونغيانغ هويجين مع توفير ضمانات سيولة كافية. وطلب الاجتماع من الشركات المدرجة زيادة توزيعات الأرباح وإعادة شراء الأسهم، وتحسين سياسات تشجيع الأموال طويلة الأجل مثل أموال التأمين والمعاشات التقاعدية للمؤسسات وصناديق الضمان الاجتماعي على الدخول إلى السوق، إضافة إلى تشديد الرقابة على سلسلة سوق المال بأكملها والتحقيق في التلاعب المالي والمخالفات في بيع الأسهم، دون تفاصيل تنفيذية أو أرقام معلنة.

telegram · zaihuapd · Nov 27, 05:35

**「السياق」** يشير تعبير «الفريق الوطني» في الأسواق الصينية إلى كيانات الدولة، وأبرزها شركة «هوايجين» \(Central Huijin\) المملوكة للدولة، التي تضخ السيولة وتشتري الأسهم لدعم السوق عند تقلبه. واعتبر خبير نقلت عنه وسائل إعلام صينية أن التوجيه الأخير يرقّي آلية «شبه صندوق الاستقرار» لدى «هوايجين» من أداة مؤقتة لمواجهة الأزمات إلى بنية دائمة في إدارة السوق.

**「الجهات المعنية」** يستهدف التوجيه، في حال تنفيذه، شركات التأمين وصناديق المعاشات التقاعدية للمؤسسات وصناديق الضمان الاجتماعي، عبر سياسات دعم وتوجيه لتوسيع ضخ أموالها طويلة الأجل في سوق الأسهم، إضافة إلى الشركات المدرجة التي طُلب منها زيادة التوزيعات وإعادة شراء الأسهم.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611273941634358.html">如何理解 国 常会对资本 市 场的最新定调？ 专 家 解读来了 _ 东方财富网</a></li>
<li><a href="https://c.m.163.com/news/a/JSK3C1QH05198CJN.html">“ 中 国 版 平 准 基 金 ”横空出世， 稳 定 市 场将如何发挥 作 用 ？ 央 行最新表态</a></li>
<li><a href="https://finance.eastmoney.com/a/202611273941564045.html">finance.eastmoney.com/a/202611273941564045.html</a></li>

</ul>
</details>

**Tags**: `#China capital markets`, `#State Council`, `#Central Huijin`, `#market stabilization`, `#long-term funds`

---

<a id="item-finance-news-2"></a>
### [تقرير: ميكسي تكتتب بـ500 مليون يوان في جولة تمويل لـDeepSeek بحجم 100–105.5 مليار يوان](https://m.sohu.com/a/1107027659_115479) ⭐️ 7.0/10

تعهدت ميكسي \(ميه شيويه بينغ تشنغ\) بدفع 500 مليون يوان عبر صندوق للمشاركة في الجولة الثانية لتمويل DeepSeek، وفق تقرير نشرته سوهو. وبلغ حجم الجولة 100–105.5 مليار يوان، ما يضع تقييم الشركة بعد الجولة عند نحو 615.5 مليار يوان.

telegram · zaihuapd · Nov 27, 06:33

**「الخلفية」** تأتي هذه الجولة بعد جولة أولى جمعت فيها DeepSeek أكثر من 500亿元 \(نحو 74亿美元\) وفق تقرير The Information، وبعد تقارير سابقة عن خطة لجمع 500亿元 عند تقييم قبل ضخ الأموال قدره 5000亿元.

<details><summary>References</summary>
<ul>
<li><a href="https://post.smzdm.com/p/aom07rr7/">DeepSeek 估 值 5000 亿 重启 融 资 ，自建智算中心并涨价_IT...</a></li>
<li><a href="https://eu.36kr.com/zh/p/3856984071027329">DeepSeek 成功揽下500 亿</a></li>

</ul>
</details>

**Tags**: `#DeepSeek融资`, `#蜜雪冰城`, `#AI投资`, `#私募股权`, `#估值`

---

<a id="item-finance-news-3"></a>
### [الصين تخفض حد الشراء الفردي لشهادات الإيداع الكبيرة إلى 100 ألف يوان](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

أعلن البنك المركزي الصيني في 27 نوفمبر نشر «قواعد إدارة شهادات الإيداع الكبيرة»، خافضًا الحد الأدنى لاشتراك الأفراد من 200 ألف يوان إلى 100 ألف يوان، وللمؤسسات من 10 ملايين يوان إلى 5 ملايين يوان، على أن تسري القواعد اعتبارًا من 21 مارس 2027. وفي اليوم نفسه نشر البنك «قواعد إدارة أسعار الفائدة على الودائع والقروض باليوان» التي تُلزم المؤسسات المالية بتحديد أسعار الفائدة بنفسها ومنع جذب الودائع بأسعار فائدة مرتفعة غير مشروعة، وتدخل حيز التنفيذ في التاريخ ذاته.

telegram · zaihuapd · Nov 27, 11:36

**「الخلفية」** شهادات الإيداع الكبيرة منتجات إيداع لأجل بحد أدنى للمبلغ لكل من الأفراد والمؤسسات، وقد حلّت القواعد الجديدة محل الإطار المؤقت لعام 2015 وإعلان 2016 المرتبط به.

**「الأثر」** سيصبح المدخرون الأفراد الذين يملكون بين 100 و200 ألف يوان قادرين على الاكتتاب في شهادات الإيداع الكبيرة بعد تخفيض الحد الأدنى إلى 100 ألف يوان، بينما ستواجه البنوك قيداً جديداً يمنعها من جذب الودائع بفوائد مرتفعة عند تطبيق القواعد في 21 مارس 2027.

<details><summary>References</summary>
<ul>
<li><a href="https://t.me/linux_do_channel/582077">LINUX DO Channel – Telegram</a></li>
<li><a href="http://politics.people.com.cn/n/2015/0603/c70731-27094926.html">央 行 公布 大 额 存 单 管 理 办 法 个 人 投资者 起 购 额 不低于30 万 --时政-- 人 民网</a></li>

</ul>
</details>

**Tags**: `#PBOC regulation`, `#large-denomination CDs`, `#deposit rates`, `#retail banking`, `#China monetary policy`

---