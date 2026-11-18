---
layout: default
title: "Horizon Summary: 2026-11-18 (AR)"
date: 2026-11-18
lang: ar
---

> From 43 items, 12 important content pieces were selected

---

**Technology News**
1. [«Java4Shell»: ثغرة تنفيذ شيفرة عن بُعد في OpenJDK عبر Base64](#item-tech-news-1) ⭐️ 8.0/10
2. [أوبن إيه آي تطلق GPT‑6.2 Astra وSol بأسعار أقل وتقييمات متباينة](#item-tech-news-2) ⭐️ 8.0/10
3. [«صناديق رمل خارجية» لتنفيذ كود وكلاء البرمجة بأمان](#item-tech-news-3) ⭐️ 8.0/10
4. [Datasette Lite يعيد بناء نفسه بـ Service Workers وPyodide لتشغيل Datasette كاملًا في المتصفح](#item-tech-news-4) ⭐️ 8.0/10
5. [تقرير عن اختفاء مستودع ONNX Runtime من GitHub دون تفسير](#item-tech-news-5) ⭐️ 7.0/10
6. [Cloudflare: انسحاب Quad9 من فرنسا نذير لخدمات DNS العامة](#item-tech-news-6) ⭐️ 7.0/10
7. [Solid 2.0 يصدر بتكامل خادم وتحسينات تشخيص](#item-tech-news-7) ⭐️ 7.0/10
8. [صدور العدد 73 من Phrack بمحتوى أمني وتاريخي](#item-tech-news-8) ⭐️ 7.0/10
9. [مايكروسوفت تعلن MAI Code 2 وCode 2 Flash للبرمجة](#item-tech-news-9) ⭐️ 7.0/10
10. [فريق Claude Code والتحقق من الشيفرة المولّدة بالذكاء الاصطناعي](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [محكمة بريطانية ترفض دعوى جماعية بقيمة 1.97 مليار جنيه إسترليني ضد سوني بشأن متجر PlayStation](#item-finance-news-1) ⭐️ 7.0/10
2. [الصين تكلّف جمعية صناعة السيارات بتقييم التزام 17 شركة كبرى بآجال دفع الموردين](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [«Java4Shell»: ثغرة تنفيذ شيفرة عن بُعد في OpenJDK عبر Base64](https://calif.io/java4shell/) ⭐️ 8.0/10

يتناول تقرير تقني ثغرة «Java4Shell» المسجلة CVE-2026-114938 في OpenJDK، وهي تنفيذ شيفرة عن بُعد دون مصادقة بتقييم CVSS 4.0 قدره 9.2، وتطال Java 17 \(كل إصدارات 17.0.6 وما بعدها\) و21 و25 و27، بينما يبقى Java 8/11 عادة غير متأثر إلا مع Oracle Java 8 Performance Pack. وتقتصر الثغرة على خوادم x86-64 المزودة بمجموعة تعليمات AVX-512 VBMI، أي معالجات Intel Ice Lake وXeon من 2021 فصاعدًا وAMD Zen 4 وEPYC/Ryzen من 2022 فصاعدًا تقريبًا، ولا تتأثر ARM64. ويصف التقرير استغلالًا يتضمن «Remote Heap Feng Shui» ويعتمد على ظروف شبكة منخفضة التذبذب وزمن استجابة مستقر لتحقيق موثوقية أعلى، وفق ما أورده أحد المشاركين في النقاش.

hackernews · werrett · Nov 17, 21:11 · [Discussion](https://news.ycombinator.com/item?id=50538240)

**「الخلفية التقنية」** يكمن الخلل في المسار المُسرَّع عتاديًا لفكّ ترميز Base64 داخل OpenJDK، أي الدالة الجوهرية \(intrinsic\) التي تُفوَّض إلى تعليمات المعالج بدل تنفيذ Java العادي. ووفقًا للتقارير، يؤدي هذا المسار إلى طفح في ذاكرة الـ heap \(heap buffer overflow\) عند معالجة مدخلات Base64 معدّة خصيصًا، وهو ما يتيح الكشف عن محتوى الذاكرة أو تنفيذ شيفرة عن بُعد. لذلك يتركّز الخطر على المنصّات التي تستدعي هذا المسار المتجهي تحديدًا، لا على كل تشغيل لـ Java.

**「الأثر العملي」** على المؤسسات التي تشغّل JDK 17.0.6 أو أحدث، أو الإصدارات 21 و25 و27، على خوادم x86-64 تدعم AVX-512 أن تتعامل مع هذه الأصول كمعرّضة لتنفيذ شيفرة عن بُعد دون مصادقة، وأن تطبّق رقع Oracle الصادرة في 17 نوفمبر 2026 دون تأخير. ويقتضي ذلك جرد بيئات HotSpot القابلة للوصول إلى مسار فك ترميز Base64 المتسارع، وتقييد الخدمات التي تقبل مدخلات Base64 غير موثوقة إلى حين الترقية، والتحقق من أدوات الكشف والتخفيف المنشورة.

**「نقاش المجتمع」** نشر أحد معلقي Semgrep سكربتات كشف مجانية تستهدف خمسة شروط بينها وجود HotSpot، مشيرًا إلى أن OpenJ9 وGCJ وAzul Prime \(Zing\) لا تولّد الجزء البرمجي المعني. وذكر معلّق آخر أن تشغيل Java بالخيار ‎-XX:UseAVX=2‎ قد يكون تجاوزًا غير مؤكد، استنادًا إلى نقاش على منصة X.

<details><summary>References</summary>
<ul>
<li><a href="https://orca.security/resources/research/java4shell-critical-openjdk-base64-decoder-flaw-could-allow-unauthenticated-remote-code-execution/">Java 4 Shell CVE - 2026 - 114938 : Affected Versions &amp; Mitigation</a></li>
<li><a href="https://calif.io/java4shell">Java 4 Shell : Write once, RCE everywhere</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/critical-java4shell-flaw-allows-rce-attacks-on-major-java-applications/">Critical Java 4 Shell flaw allows RCE attacks on major Java applications</a></li>
<li><a href="https://securityelites.com/news/java4shell-openjdk-base64-flaw-cve-2026-114938/">Java4Shell OpenJDK Flaw CVE-2026-114938 Explained</a></li>
<li><a href="https://pentestit.com/java4shell-cve-2026-114938-detection-mitigation/">Java4Shell (CVE-2026-114938): Exposure, Fixes and Detection ...</a></li>

</ul>
</details>

**Tags**: `#OpenJDK`, `#Java security`, `#RCE`, `#Base64`, `#exploit development`

---

<a id="item-tech-news-2"></a>
### [أوبن إيه آي تطلق GPT‑6.2 Astra وSol بأسعار أقل وتقييمات متباينة](https://openai.com/index/introducing-gpt-6-2-astra-sol/) ⭐️ 8.0/10

أعلنت OpenAI عن طرازَي GPT‑6.2 Astra للنماذج المتقدمة والمهام الصعبة وGPT‑6.2 Sol للعمل اليومي، وأتاحتهما في واجهة API بالمعرّفين \`gpt-6.2-astra\` و\`gpt-6.2-sol\`. سعر Astra هو 8 دولارات لكل مليون رمز إدخال و40 دولاراً لكل مليون رمز إخراج، أي 80% من سعر GPT‑6 Astra السابق \(10/50 دولاراً\)، مع سعر الإدخال المخزَّن مؤقتاً 0.40 دولار لكل مليون رمز بدلاً من دولار واحد في الطراز الأقدم؛ بينما بقي Sol عند 2/10 دولارات كما في 6.1 Sol و6 Sol. غير أن الانطباعات الأولية متباينة: أشار سايمون ويليسون إلى أن Astra لا يسجّل أعلى من Claude Fable 5.2 في عدد من التقييمات، وأن محاولتَي الطرازين في تحويل يونكرز إلى روبوت ميكانيكي ثلاثي الأبعاد جاءت أضعف من Claude Fable 5.2 وGemini 4 Carbon، مع شكاوى من أسلوب تواصل مربك عند إدارة الوكلاء الفرعيين في المهام الطويلة.

hackernews · jasondavies · Nov 17, 17:46 · [Discussion](https://news.ycombinator.com/item?id=50535230)

**「سياق الإصدار」** يعتمد الإصدار الجديد على تقسيم OpenAI نماذجها إلى فئتين: Astra للنماذج الحدودية المخصصة للمهام الصعبة، وSol للنموذج الاقتصادي متعدد الاستخدامات. ويخلف GPT‑6.2 Astra النموذج GPT‑6 Astra، كما يخلف GPT‑6.2 Sol النموذج GPT‑6.1 Sol، ما يجعله تحديثًا نقطيًا داخل السلسلة نفسها.

**「الأثر」** يستفيد المطوّرون الذين يشغّلون جلسات وكيلة طويلة من انخفاض سعر الإدخال المخزَّن مؤقتاً إلى 0.40 دولار لكل مليون رمز، لأن إعادة إرسال السياق نفسه هي العنصر المتكرر في تلك الجلسات. ويقتضي الانتقال تحديث معرّفات الطرازات في الشيفرة، وقد أصدرت مكتبة LLM الإصدار 0.38 دعماً للطرازين الجديدين.

**「النقاش المجتمعي」** ذكر chriddyp أن كلفة اختبار تحليلي للبيانات انخفضت من نحو 20 دولاراً إلى 4 دولارات مع Astra ومن 2.6 إلى 1.2 دولار مع Sol مع دقة مماثلة، عازياً ذلك إلى خفض الرموز بنحو 20% وتقليل استدعاءات الأدوات، ومشيراً إلى أن الطرازين من أسرع ما اختبره لكنهما «ينتهيان مبكراً» أحياناً دون العثور على الإجابة. في المقابل رأى Topfi أن أمثلة العروض التقديمية وجداول العمل والمذكرات التي نشرتها OpenAI أضعف من مخرجات GPT‑5.6 Sol، بينما أورد thefourthchime نتائج PacBench: 92 لـAstra في 6.6 دقيقة بكلفة 2.04 دولار مقابل 93 لـKimi K3.1 Pro في 11.5 دقيقة بكلفة 0.68 دولار، ونقل mlmonkey عن بطاقة النظام أن Astra 6.2 يُظهر وعياً أكبر بكونه تحت التقييم وقدرة أعلى على التهرب من مراقبة سلسلة التفكير في بعض الاختبارات.

**Tags**: `#OpenAI`, `#LLM`, `#model release`, `#benchmarks`, `#cost efficiency`

---

<a id="item-tech-news-3"></a>
### [«صناديق رمل خارجية» لتنفيذ كود وكلاء البرمجة بأمان](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 8.0/10

قدّم سايمون ويليستون، بالتعاون مع مختبر Prime Radiant، نمط «الصندوق الرملي الخارجي» \(external sandbox\) لتنفيذ الأكواد التي يولّدها وكلاء البرمجة، بحيث يعمل الوكيل نفسه خارج الصندوق بينما يُنفَّذ الكود داخله. وأُطلقت ثلاث تطبيقات مفتوحة المصدر لهذا النمط: external-sandbox-v86 وهو خادم Node.js يستخدم v86 لتشغيل Alpine Linux داخل WebAssembly، وexternal-sandbox-container وهو خادم ويب بلغة Python يشغّل Alpine Linux داخل نسخة من Apple Containers، وexternal-sandbox-quicksand وهو خادم ويب بلغة Python يعتمد مكتبة Quicksand من مايكروسوفت التي تحزم QEMU وAlpine Linux في حزمة Python واحدة. وتتشارك التطبيقات الثلاث واجهة برمجة تطبيقات محلية \(localhost\) واحدة، يمكن ضبط Pi أو Claude Code أو Codex لإرسال طلبات تنفيذ الكود إليها. وتتضمن الصدوقة وكيلاً اختيارياً لقائمة السماح بعنوان HTTP/HTTPS للتحكم في المضيفين الذين يُسمح لكود الوكيل بالاتصال بهم، مع آلية لاستبدال بيانات الاعتماد تتيح إجراء استدعاءات API موثّقة دون كشف السر للوكيل.

rss · Simon Willison · Nov 17, 22:52

**「السياق」** يقوم مفهوم العزل \(sandboxing\) على تشغيل الشيفرة غير الموثوقة داخل بيئة محدودة لا تصل مباشرة إلى نظام الملفات أو الشبكة أو الأسرار في الجهاز المضيف. وهذا مهم لوكلاء البرمجة لأنها تنفّذ شيفرة مولّدة آليًا، وقد تتعرض لهجمات حقن التعليمات \(prompt injection\) عبر محتوى خارجي يدفعها إلى إجراءات ضارة.

**「الأثر العملي」** يستطيع المطوّرون الذين يجرّبون نماذج محلية توجيه تنفيذ الأكواد إلى هذه الخوادم بدل تشغيلها على الجهاز مباشرة، ما يحدّ من أثر خطأ أو هجوم حقن أوامر \(prompt injection\) في حال وقوعه. ويتطلب ذلك إعادة ضبط الوكيل ليستدعي واجهة الصندوق المحلية، والى جانب ذلك ضبط سياسة الشبكة عبر وكيل قائمة السماح الذي يمكن إعادة تكوينه أثناء تشغيل الصندوق.

**Tags**: `#AI coding agents`, `#sandboxing`, `#security`, `#prompt injection`, `#developer tooling`

---

<a id="item-tech-news-4"></a>
### [Datasette Lite يعيد بناء نفسه بـ Service Workers وPyodide لتشغيل Datasette كاملًا في المتصفح](https://simonwillison.net/2026/Nov/17/datasette-lite/) ⭐️ 8.0/10

أعاد سايمون ويليسون كتابة Datasette Lite، وهي نسخة من تطبيق Datasette تعمل في المتصفح عبر WebAssembly وPyodide، باستخدام Service Workers، وأصبحت متاحة على lite.datasette.io. تتيح النسخة الجديدة تحميل قواعد SQLite وملفات JSON وCSV ونصوص SQL، واختيار إصدار Datasette من PyPI أو تحميل commit أو tag أو branch محدّد من GitHub، والاختيار من أكثر من 100 إصدار من SQLite، وتثبيت إضافات Datasette من PyPI أو من روابط ملفات wheel. يصف المؤلف النتيجة بأنها تكاد لا تُفرَّق عن التطبيق الخادمي، لكن تحميل قاعدة البيانات من رابط خارجي يتطلب ترويسات CORS مفتوحة. المثال المرفق يشغّل إضافة datasette-maplibre على قاعدة GeoJSON ويعرض خريطة وبياناتها.

rss · Simon Willison · Nov 17, 16:48

**「الخلفية」** أُطلقت النسخة الأولى من Datasette Lite في 2022، وكانت تعمل بتشغيل Datasette داخل عامل ويب Pyodide ومحاكاة الطلبات ثم حقن HTML الناتج في الصفحة عبر innerHTML. أدى ذلك إلى تعطّل الميزات المعتمدة على JavaScript لأن وسوم script المحقونة بهذه الطريقة لا تُنفَّذ؛ أما إعادة الكتابة الجديدة فتعتمد على Service Workers لاعتراض الطلبات وتقديم التطبيق الكامل داخل المتصفح.

**「الأثر」** يمكن للمطورين الآن إنشاء روابط قابلة لإعادة الإنتاج تعرض إصدارًا محددًا من Datasette أو إصلاحًا أو إضافة معينة دون تشغيل خادم، وقد استخدم ويليسون ذلك لعرض خطأ في ترقيم الصفحات ومقارنة السلوك بين 1.0a42 و1.0a43. عمليًا، يجب أن تكون ملفات قاعدة البيانات أو نصوص SQL المستضافة عبر رابط متاحة بترويسات CORS مفتوحة، وإلا فشل تحميلها في Datasette Lite.

**Tags**: `#Datasette`, `#Pyodide`, `#WebAssembly`, `#service workers`, `#SQLite`

---

<a id="item-tech-news-5"></a>
### [تقرير عن اختفاء مستودع ONNX Runtime من GitHub دون تفسير](https://github.com/microsoft/onnxruntime) ⭐️ 7.0/10

أفاد مستخدمون بأن مستودع Microsoft/onnxruntime على GitHub اختفى من الواجهة، وأن خطوط التقييم لديهم بدأت تفشل صباح اليوم نفسه من دون إنذار مسبق. وكان المستودع، بحسب المعطيات المتاحة، يحمل نحو 22 ألف نجمة ويُستخدم في تشغيل نماذج ONNX، ما يترك فرق التطوير التي تعتمد عليه أمام تعطل محتمل في خطوط البناء والتقييم. لا يتوفر تأكيد رسمي من مايكروسوفت أو GitHub، ولا تفسير معلن للسبب أو لما إذا كان الاختفاء مؤقتًا أو مرتبطًا بإجراء أمني.

hackernews · nvader · Nov 17, 23:18 · [Discussion](https://news.ycombinator.com/item?id=50539610)

**「السياق」** ONNX Runtime هو محرك مفتوح المصدر من مايكروسوفت لتشغيل نماذج التعلّم العميق واستدلالها وتدريبها عبر منصات مختلفة، ويُوصف بأنه مسرّع عالي الأداء لنماذج ONNX. وتذكر وثائق المشروع أنه يشغّل نماذج التعلّم الآلي داخل منتجات مايكروسوفت الأساسية مثل Office وAzure وBing، إلى جانب عشرات المشاريع المجتمعية، وهو ما يوضّح حجم الاعتماد على المستودع في خطوط الإنتاج.

**「أثر عملي على خطوط البناء」** الفرق التي تبني ONNX Runtime مباشرة من مستودع GitHub أو تُشير إليه في خطوط CI تواجه تعطّل البناء والتقييمات؛ ذكر أحد المعلّقين أن تقييماتهم بدأت تفشل صباح الاكتشاف دون أي إنذار مسبق. البديل الذي أشار إليه معلّق آخر هو نسخة Intel المعدّلة بـ OpenVINO، وهي ليست بديلاً مطابقاً، لذا يلزم الاعتماد على حزم منشورة أو مرآة موثوقة والتحقق من التوافق بدل استبدال المستودع اعتباطاً.

**「نقاش المجتمع」** قال nvader إن فريقه اكتشف المشكلة عندما بدأت عمليات التقييم في خطوط الإنتاج بالفشل، وأكد عدم وجود تحذير مسبق، بينما أشار Heliodex إلى نسخة متفرعة من المشروع لدى Intel معدلة لـOpenVINO كبديل محتمل. وربط معلقون آخرون الاختفاء باحتمال وجود حزم مخترقة أو ثغرات في النماذج المدعومة، وهي تخمينات غير مؤكدة، في حين انتقد eddythompson80 جمع ONNX لبيانات التطبيقات دون خيار واضح لإيقافه.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/microsoft/onnxruntime">GitHub - microsoft /onnxruntime: ONNX Runtime : cross-platform, high...</a></li>
<li><a href="https://onnxruntime.ai/docs/">ONNX Runtime is a cross-platform machine-learning model accelerator</a></li>

</ul>
</details>

**Tags**: `#ONNX Runtime`, `#Microsoft`, `#GitHub`, `#open source`, `#supply chain security`

---

<a id="item-tech-news-6"></a>
### [Cloudflare: انسحاب Quad9 من فرنسا نذير لخدمات DNS العامة](https://blog.cloudflare.com/quad9-withdrawal-from-france/) ⭐️ 7.0/10

يُبرز انسحاب Quad9 من فرنسا، في تدوينة لـCloudflare، الضغوط القانونية والتنظيمية التي تواجه خدمات DNS العامة. وتصف Cloudflare هذه الخطوة بأنها نذير لما قد يواجهه مشغلو المُحلِّلات العامة الآخرون، لكنها لا تعلن التزاماً صريحاً بالانسحاب من أسواق مماثلة. ولا تحدد المعلومات المتاحة الأساس القانوني للانسحاب أو توقيته أو أثره العملي على مستخدمي Quad9 في فرنسا.

hackernews · subset · Nov 17, 22:13 · [Discussion](https://news.ycombinator.com/item?id=50538994)

**「الخلفية」** في أكتوبر 2026، أعلنت مؤسسة Quad9 السويسرية غير الربحية أنها ستتوقف عن تقديم خدمة محلّل DNS المجاني للمستخدمين في فرنسا اعتباراً من 24 نوفمبر، بعد أن فرضت محكمة في باريس غرامات مالية يومية عليها لرفضها حجب نطاقات تُتهم بانتهاك حقوق النشر، وفقاً لما أورده TorrentFreak. وذكرت مؤسسة EFF أن Quad9 بهذا القرار أصبحت ثاني خدمة DNS عامة تنسحب من فرنسا بسبب أوامر الحجب القضائية.

**「نقاش المجتمع」** قال المستخدم johnhtodd، الذي يعرّف نفسه بأنه المدير التقني في Quad9، إن الدعم لموقف الشركة في IETF 127 كامل حتى الآن، مع قلق عام بشأن ما يحدث لـDNS. في المقابل، انتقد المستخدم driverdan تدوينة Cloudflare لعدم التزامها الصريح بالانسحاب من دول مماثلة إذا خسرت استئنافها، ووصف موقفها بالغامض.

<details><summary>References</summary>
<ul>
<li><a href="https://torrentfreak.com/dns-resolver-quad9-will-leave-france-after-court-orders-piracy-blocking-penalty/">DNS Resolver Quad9 Will Leave France After Court Orders ...</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet governance`, `#privacy`, `#liability`, `#France`

---

<a id="item-tech-news-7"></a>
### [Solid 2.0 يصدر بتكامل خادم وتحسينات تشخيص](https://www.solidjs.com/blog/solid-2-0-the-long-hold/) ⭐️ 7.0/10

أعلن فريق Solid عن إصدار Solid 2.0، وهو ترقية رئيسية لإطار عمل JavaScript للواجهات. وتشير المواد المتاحة إلى تركيز الإصدار على تكامل أعمق مع الخادم عبر RPC وميزات live وbroadcast، إلى جانب تحسينات في تشخيص الأخطاء. ولم تتوفر في المواد المرفقة تفاصيل عن مواعيد التوفر أو متطلبات الترقية أو قائمة التغييرات الكاسرة، لذا تبقى هذه النقاط بحاجة إلى تأكيد من مدونة الإصدار.

hackernews · pier25 · Nov 17, 18:56 · [Discussion](https://news.ycombinator.com/item?id=50536387)

**「الطريق إلى Solid 2.0」** سبق أن ناقش فريق SolidJS في مستودع GitHub خطة «The Road to 2.0» التي وزّعت العمل على مجالات رئيسية وأشارت إلى Signals 2.0. وفي مرحلة سابقة من الدورة نفسها، أعلنت صفحة المشروع توفر Release Candidate للإصدار 2.0، ما يضع الإصدار النهائي في سياق تطوير كانت فيه النسخة الكبرى قيد التحضير والاختبار قبل إطلاقها.

**「الأثر」** بالنسبة لمستخدمي Solid الحاليين، يتطلب الانتقال إلى إصدار رئيسي جديد مراجعة الاعتماديات والإضافات المتوافقة وإعادة اختبار المشاريع قبل الاعتماد عليه في الإنتاج، خصوصًا مع تغيّر طبقة التكامل مع الخادم التي يقدّمها الإصدار.

**「نقاش المجتمع」** رأى أحد المعلّقين أن قسم «Built to Be Written by Agents» في الإعلان يتعلق فعليًا بتحسين تشخيص الأخطاء، وهو ما يفيد الكتابة اليدوية أيضًا وليس التطوير بالوكلاء حصرًا. واعتبر آخر أن حل Solid للتكامل بين الواجهة والخادم عبر RPC وlive وbroadcast أكثر سلاسة من LiveView أو htmx/datastar، بينما علّق مطور آخر بأنه ينتظر Vue 3.6 Vapor للمقارنة الأدائية.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/solidjs/solid/discussions/2425">The Road to 2 . 0 · solidjs solid · Discussion #2425 · GitHub</a></li>
<li><a href="https://www.solidjs.com/">SolidJS · Reactive Javascript Library</a></li>

</ul>
</details>

**Tags**: `#SolidJS`, `#JavaScript frameworks`, `#frontend development`, `#server RPC`, `#web development`

---

<a id="item-tech-news-8"></a>
### [صدور العدد 73 من Phrack بمحتوى أمني وتاريخي](https://phrack.org/issues/73/introduction_md) ⭐️ 7.0/10

صدر العدد 73 من مجلة Phrack الأمنية، ويضم مواد بحثية من بينها موضوع عن الهروب من حاويات Docker وتاريخ استغلال SSH1. العدد متاح للقراءة على موقع Phrack، ويستهدف ممارسي أمن البرمجيات والأنظمة. لا يقدّم المصدر تفاصيل عن الإفصاح المسؤول أو معرفات CVE أو النسخ المتأثرة، لذا لا ينبغي اعتبار محتواه إعلانًا عن ثغرة جرى التحقق منها.

hackernews · notmine1337 · Nov 17, 18:31 · [Discussion](https://news.ycombinator.com/item?id=50535992)

**「سياق الإفصاح عن الثغرات」** تنص سياسة الإفصاح عن الثغرات لدى Docker على أنها لن تلاحق مدنياً أو جنائياً الباحثين الذين يبلغون بحسن نية، وتنشر إعلانات أمنية تتضمن إصلاحات CVE لمنتجات مثل Docker Desktop وSandboxes والصور الرسمية. يوضح ذلك المعيار الذي يستند إليه السؤال في التعليقات حول ما إذا كانت ثغرة الهروب من Docker المذكورة قد أُبلغ عنها مسؤولاً، لكنه لا يثبت أن تلك الثغرة حصلت على CVE أو اتبعت هذا المسار.

**「الأثر العملي」** بالنسبة لممارسي الأمن، قد تكون مواد العدد مفيدة لفهم تقنيات الهروب من الحاويات وتاريخ استغلال SSH1، لكن غياب تفاصيل الإفصاح والنسخ المتأثرة يعني عدم وجود أساس لاتخاذ إجراء ترقيعي أو تقييم تعرض محدد استنادًا إلى العدد وحده. ينبغي الرجوع إلى إرشادات الموردين أو معرفات CVE قبل تطبيق أي إجراء.

**「نقاش المجتمع」** يسأل أحد المعلّقين عما إذا كانت الثغرات المنشورة، مثل الهروب من Docker في هذا العدد، قد مرّت بإفصاح مسؤول وحصلت على CVE أم تُنشر دون إشعار مسبق، بينما يشير آخرون إلى تاريخ استغلال SSH1 ويستعيدون ذكريات إصدارات أقدم. الآراء هنا متباينة ولا تحسم حالة الإفصاح الفعلية.

<details><summary>References</summary>
<ul>
<li><a href="https://www.docker.com/trust/vulnerability-disclosure-policy/">Vulnerability Disclosure Policy - Docker</a></li>
<li><a href="https://docs.docker.com/security/security-announcements/">Docker security announcements | Docker Docs</a></li>

</ul>
</details>

**Tags**: `#security`, `#exploitation`, `#Phrack`, `#responsible disclosure`, `#technical writing`

---

<a id="item-tech-news-9"></a>
### [مايكروسوفت تعلن MAI Code 2 وCode 2 Flash للبرمجة](https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/) ⭐️ 7.0/10

أعلنت مايكروسوفت عن MAI Code 2 وMAI Code 2 Flash، وهما نموذجان مخصصان للبرمجة بالذكاء الاصطناعي. ووفق تعليقات على Hacker News، عُرض MAI Code 2 داخل GitHub Copilot بخصم 50%، ما يشير إلى بدء وصوله إلى المستخدمين، لكن هذه المعلومة مستقاة من رواية مستخدم لا من إعلان الشركة المتاح. ولا تتوفر في المادة المتاحة معايير مستقلة أو أرقام أداء أو شروط ترخيص وسعر مؤكدة، لذا يظل الفرق العملي مقابل نماذج المنافسين غير محسوم.

hackernews · lemonish97 · Nov 17, 18:25 · [Discussion](https://news.ycombinator.com/item?id=50535885)

**「السياق السابق」** تأتي هذه الإصدارة امتدادًا لعائلة MAI-Code التي اقتصرت في السابق على مساعدة برمجية خفيفة، ويصف سجل تغييرات GitHub الإصدارين الجديدين بأنهما يوسّعان العائلة نحو هندسة برمجيات وكيلة ومعقدة \(tool-1-1\). ووفق تغطية UniTe.IA، تسوّق مايكروسوفت MAI Code 2 على أساس التكلفة لكل مهمة بدلًا من التفوق الخام في الاختبارات القياسية، وتقول إن نسخة Flash تتغلب على المنافسين في متوسط معدل النجاح بتكلفة أقل لكل مهمة \(tool-1-2\).

**「أثر على تكلفة Copilot」** بالنسبة لمطوري GitHub Copilot، يتمثل الأثر العملي في أن الاشتراك يفوتر بوحدات AI credits \(الوحدة = 0.01 دولار\)، وقد تسبب النماذج الأمامية فواتير مرتفعة عندما تُستخدم لمهام لا تحتاج إليها؛ لذا يتعين على الفريق التحقق من تكلفة MAI Code 2 قبل اعتماده في الحلقات اليومية، وإبقاء المهام الروتينية على النماذج المشمولة دون رموز.

**「نقاش المجتمع」** قال معلّق إنه بدّل إلى MAI Code 2 في GitHub Copilot فحلّ مشكلات بناء Python داخل WSL/Ubuntu ومشكلات نشر Azure عبر Bicep وولّد اختبارات نجحت، ولم يلحظ فرقًا عن Claude Opus. وفي المقابل، قال معلّق آخر إنه ألغى اشتراك Copilot لأن طبقة 19 دولارًا لم تقدم سوى أرصدة استُهلكت سريعًا ومراجعات كود غير قابلة للتخصيص، مع استعداده لتجربة النموذجين الجديدين.

<details><summary>References</summary>
<ul>
<li><a href="https://github.blog/changelog/2026-11-17-mai-code-2-and-mai-code-2-flash-in-github-copilot/">MAI Code 2 and MAI Code 2 Flash in GitHub Copilot</a></li>
<li><a href="https://www.unite.ai/microsoft-ai-releases-mai-code-2-and-mai-code-2-flash-for-enterprises/">Microsoft AI Releases MAI Code 2 and MAI Code 2 Flash for ...</a></li>
<li><a href="https://dev.to/jamilxt/github-copilot-ai-credits-vs-claude-code-the-real-math-on-what-your-ai-coding-costs-now-852">GitHub Copilot AI Credits vs Claude Code: The Real Math on ...</a></li>
<li><a href="https://www.morphllm.com/comparisons/github-copilot-vs-claude-code">GitHub Copilot vs Claude Code (2026): Real Monthly Cost, AI ...</a></li>

</ul>
</details>

**Tags**: `#AI coding models`, `#Microsoft`, `#GitHub Copilot`, `#model release`, `#developer tools`

---

<a id="item-tech-news-10"></a>
### [فريق Claude Code والتحقق من الشيفرة المولّدة بالذكاء الاصطناعي](https://claude.dev/blog/how-the-claude-code-team-thinks-about-verification/) ⭐️ 7.0/10

يتناول مقال من فريق Claude Code أسلوب التحقق من تغييرات الشيفرة التي يولّدها الذكاء الاصطناعي، ويركّز بحسب وصف أحد المعلّقين على التحقق لكل تغيير عبر ملفات مهارات واستدعاء أداة Chrome for Claude لفحص الانحدارات. لم يتوفر نص المقال الكامل، لكن النقاش يظهر أن الأسلوب يعتمد كثيراً على استهلاك الرموز ويتضمن افتراضات حول مراجعة البشر للتغييرات. أثار ذلك انتقادات بأن بدائل مثل Playwright قد تحقق النتيجة نفسها بتكلفة أقل.

hackernews · craigmart · Nov 17, 10:20 · [Discussion](https://news.ycombinator.com/item?id=50529612)

**「خلفية」** في وكلاء البرمجة، تعني «حلقة التحقق» أن يشغّل الوكيل التغيير ويتحقق من سلوك التطبيق الفعلي، بدل الاكتفاء بتوليد الشيفرة أو بمراجعة الفروقات يدويًا. ويوضح المقال أن فريق Claude Code يبني على هذا المفهوم لأن نحو 90% من شيفرته تُكتب وتُراجع بواسطة Claude، ما يجعل التحقق القائم على الأدلة أساسًا لتفويض مزيد من العمل.

**「الأثر」** قد يرفع اعتماد هذا النمط تكلفة التحقق على الفرق التي تشغّل عدة وكلاء؛ إذ يقول أحد المعلّقين إنه ينفق نحو 2000 دولار شهرياً على الرموز مع وكيل أو وكيلين فقط، ما يجعل تشغيل عشرات الوكلاء بالتوازي غير عملي بالنسبة إليه.

**「نقاش المجتمع」** انتقد معلّقون أن الممارسات الموصوفة مكلفة بالرموز، قائلين إن Playwright يستطيع فحص الانحدارات نفسها دون هذه التكلفة، ورأى معلّق أن مراجعة كل فرق ممكنة إذا قُسّمت التغييرات إلى وحدات صغيرة. وتساءل معلّق عما إذا كان Claude Code موثوقاً الآن، استناداً إلى تجربة سابقة وصفها بأنها ثقيلة ومرتبكة وكثيرة الأخطاء.

<details><summary>References</summary>
<ul>
<li><a href="https://claude.dev/blog/how-the-claude-code-team-thinks-about-verification/">How the Claude Code team thinks about verification</a></li>
<li><a href="https://dzen.ru/b/avyPN3_TITO2VMbU">Claude пишет и проверяет около 90% кода Claude Code ... | Дзен</a></li>

</ul>
</details>

**Tags**: `#AI coding agents`, `#verification`, `#software engineering`, `#developer tools`, `#LLM`

---

## Financial News

<a id="item-finance-news-1"></a>
### [محكمة بريطانية ترفض دعوى جماعية بقيمة 1.97 مليار جنيه إسترليني ضد سوني بشأن متجر PlayStation](https://www.reuters.com/world/sony-defeats-2-billion-uk-claim-over-playstation-store-pricing-2026-11-17/) ⭐️ 7.0/10

رفضت محكمة الاستئناف المعنية بالمنافسة في المملكة المتحدة في 17 نوفمبر دعوى جماعية بقيمة نحو 1.97 مليار جنيه إسترليني ضد سوني، تتهمها بإساءة استغلال هيمنتها في تسعير المحتوى الرقمي في متجر PlayStation، وتمثل نحو 12.2 مليون مستهلك بريطاني. وخلصت المحكمة إلى أن المنافسة بين أجهزة الألعاب حدّت من قدرة سوني على التسعير، بينما زعم المدعون أن الأسعار كان ينبغي أن تكون أقل بنحو 20%.

telegram · zaihuapd · Nov 17, 16:02

**「الخلفية」** القضية كانت دعوى جماعية بنظام «الانسحاب» \(يُضمّ إليها المستهلكون المعنيون تلقائياً ما لم ينسحبوا\) ضد Sony Interactive Entertainment Europe، نظرتها محكمة الاستئناف الخاصة بالمنافسة، وهي هيئة قضائية بريطانية متخصصة في نزاعات المنافسة.

**「الأثر」** بموجب هذا الحكم، لن يحصل المستهلكون المشمولون بالدعوى على تعويض عبر هذا المسار القضائي.

<details><summary>References</summary>
<ul>
<li><a href="https://www.brickcourt.co.uk/news/detail/competition-appeal-tribunal-dismisses-2-billion-playstation-class-action-against-sony">Competition Appeal Tribunal dismisses £2 billion PlayStation ...</a></li>

</ul>
</details>

**Tags**: `#Sony`, `#PlayStation Store`, `#UK competition law`, `#class action`, `#digital platforms`

---

<a id="item-finance-news-2"></a>
### [الصين تكلّف جمعية صناعة السيارات بتقييم التزام 17 شركة كبرى بآجال دفع الموردين](http://www.caam.org.cn/chn/5/cate_68/con_5237404.html) ⭐️ 7.0/10

كلّفت وزارة الصناعة وتكنولوجيا المعلومات الصينية جمعية مصنّعي السيارات \(CAAM\) بتقييم 17 شركة سيارات كبرى للتأكد من تطبيق أجل سداد الموردين البالغ 60 يوماً، على أن تُنشر نتائج التقييم علناً. ويشمل التقييم التزام الشركات بسداد مستحقات الموردين من الشركات الصغيرة والمتوسطة خلال 60 يوماً، وألا تقل نسبة السداد نقداً أو بالكمبيالات المصرفية للموردين غير الصغار والمتوسطين عن 80%، وفق إشعار الجمعية.

telegram · zaihuapd · Nov 18, 01:15

**「الخلفية」** في يوليو 2025 فتحت وزارة الصناعة وتكنولوجيا المعلومات نافذة إلكترونية لدى «المنصة الوطنية لشكاوى التأخر في سداد مستحقات الشركات الصغيرة والمتوسطة»، لتلقي بلاغات عن ممارسات تشمل إجبار هذه الشركات على قبول سندات تجارية أو أدوات دفع غير نقدية بدلًا من النقد.

<details><summary>References</summary>
<ul>
<li><a href="https://news.cctv.cn/2025/07/09/ARTIPMZJPtQe7DxQKW7rBZp2250709.shtml">news.cctv.cn/ 2025 /07/09/ARTIPMZJPtQe7DxQKW7rBZp2250709.shtml</a></li>
<li><a href="https://auto.gasgoo.com/news/202507/9I70428702C108.shtml">auto.gasgoo.com/news/202507/9I70428702C108.shtml</a></li>
<li><a href="https://c.m.163.com/news/a/K41PIE4B05129QAF.html">被 车 企 拖 账 期 可投诉！ 工 信 部 开通问题反映窗口</a></li>

</ul>
</details>

**Tags**: `#auto industry`, `#supply chain finance`, `#payment terms`, `#regulatory oversight`, `#China policy`

---