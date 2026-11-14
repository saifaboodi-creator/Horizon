---
layout: default
title: "Horizon Summary: 2026-11-14 (AR)"
date: 2026-11-14
lang: ar
---

> From 41 items, 8 important content pieces were selected

---

**Technology News**
1. [تدريب MoE بتريليون معامل على 384 من GH200 باستخدام TorchTitan](#item-tech-news-1) ⭐️ 8.0/10
2. [إدارة الطيران الفيدرالية تصدر وقفاً وطنياً للرحلات المغادرة بسبب عطل اتصالات](#item-tech-news-2) ⭐️ 7.0/10
3. [تيم بيترز، من أوائل مساهمي بايثون، يتوفى عن 74 عامًا](#item-tech-news-3) ⭐️ 7.0/10
4. [DeepSeek يوسّع واجهة API بقدرات تطبيقية وعرض محادثة مفتوح المصدر](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenAI تطلق ChatGPT Wallet لمدفوعات الوكلاء في الولايات المتحدة](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [كانتور فيتزجيرالد تقلّص حصتها المعلنة في إنفيديا وسط تدقيق بشأن لوتنيك](#item-finance-news-1) ⭐️ 8.0/10
2. [غولسبي: الفيدرالي «لديه عمل يقوم به» بشأن التضخم بعد ارتفاع أسعار المنتجين 6.5%](#item-finance-news-2) ⭐️ 8.0/10
3. [月之暗面 تعيد هيكلة شركتها استعدادًا لطرح عام في هونغ كونغ](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [تدريب MoE بتريليون معامل على 384 من GH200 باستخدام TorchTitan](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

شارك مهندس في Reddit خلاصة تجربة مع فريقَي TorchTitan وPyTorch لتدريب نموذج خليط خبراء \(MoE\) بنحو تريليون معامل على 384 من معالجات GH200، قائلًا إنه بلغ نحو 1,300 رمز/ثانية لكل GPU وإن ذلك يعد تحسينًا بمقدار 14× عن نقطة البداية. استخدم التصميم FSDP على 384 اتجاهًا مع EP بأربعة اتجاهات داخل العقدة، وتضمّن نقاط تفتيش كاملة للتنشيط مع إخراجها إلى Grace، ومُحسّن Muon، وتقسيم FlexShard، ونقل تدرجات الخبراء عبر all-to-all بدل reduce-scatter لتقليل بايتات InfiniBand. هذه أرقام ونتائج يوردها كاتب التجربة وليست قياسًا مستقلًا، ويشير إلى أن بعض التحسينات أُضيفت إلى TorchTitan مثل تشغيل Newton-Schulz على GPU عندما تكون المعاملات على المضيف.

reddit · r/MachineLearning · /u/f14-bertolotti · Nov 13, 16:28

**「الخلفية」** TorchTitan منصة مفتوحة المصدر وأصيلة في PyTorch للتدريب الموزّع الواسع النطاق، صُممت لتوحيد تقنيات التدريب المتقدمة وتقليل الأعباء الهندسية اللازمة لتشغيلها. ولتدريب نموذج MoE ضخم لا يتسع لبطاقة واحدة، يعتمد التقرير على التوازي الكامل في البيانات FSDP، حيث تحتفظ كل بطاقة بشريحة من كل وزن وتجمع الباقي عند الحاجة، وعلى توازي الخبراء EP حيث تمتلك كل بطاقة مجموعة فرعية من الخبراء. وتأتي بطاقات GH200 داخل حاسوب JUPITER العملاق بوصلة Grace–Hopper عالية النطاق، بينما يظل الاتصال بين العقد عبر InfiniBand أبطأ بكثير، وهو ما يفسّر تركيز التحسينات على تقليل حركة الشبكة.

**「الأثر العملي」** قد تفيد هذه التجربة الفرق التي تدرب MoE كبيرًا على عناقيد Hopper محدودة العرض بين العقد، إذ تشير إلى أن إبقاء expert parallelism داخل العقدة، وتقليل نقل التدرجات، وإخراج حالات المُحسّن إلى Grace يمكن أن يعالج اختناق InfiniBand؛ لكن الأرقام المذكورة تظل ادعاء الكاتب وليست نتيجة تحقق مستقل. ومن الناحية العملية، يعتمد أحد التحسينات على علم خاص في FSDP2 اسمه unshard\_async\_op كان وقت الكتابة في طريقه ليصبح API عامًا، ما يعني أن الفرق قد تحتاج إلى ترقية TorchTitan أو التعامل مع واجهة غير مستقرة لتطبيقه.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/pytorch/torchtitan">GitHub - pytorch / torchtitan : A PyTorch native platform for training...</a></li>
<li><a href="https://arxiv.org/pdf/2410.06511">TorchTitan : One-stop PyTorch native solution for production ready...</a></li>

</ul>
</details>

**Tags**: `#TorchTitan`, `#Mixture-of-Experts`, `#Distributed Training`, `#GH200`, `#PyTorch`

---

<a id="item-tech-news-2"></a>
### [إدارة الطيران الفيدرالية تصدر وقفاً وطنياً للرحلات المغادرة بسبب عطل اتصالات](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 7.0/10

أصدرت إدارة الطيران الفيدرالية \(FAA\) أمراً بوقف وطني للرحلات المغادرة، ما أوقف إقلاع الطائرات في مطارات الولايات المتحدة. وأشارت تقارير أولية نقلها مشاركون، استناداً إلى صحيفة وول ستريت جورنال عن أشخاص مطلعين، إلى أن العطل يطال شبكة اتصالات تديرها L3Harris Technologies وتُستخدم في ترددات الراديو الحيوية التي يعتمد عليها مراقبو الحركة الجوية للتواصل مع الطيارين. وظل السبب الجذري غير مؤكد، ولم يتضح ما إذا كان العطل أصاب أيضاً تغذيات الرادار، بينما كانت التفاصيل التقنية شحيحة. وقال مشارك إن صحيفة نيويورك تايمز أفادت برفع الوقف، بينما نقل مشارك آخر تحذيراً من مسؤول بأن العطل قد لا يُحل خلال ساعة.

hackernews · zulln · Nov 13, 21:05 · [Discussion](https://news.ycombinator.com/item?id=50489641)

**「السياق」** يوقف أمر وقف الإقلاع الوطني مؤقتًا مغادرة الرحلات، فيما تُدار الطائرات الموجودة في الجو على أساس كل حالة على حدة، وفق ما أوردته التقارير. وفي الملاحة الجوية، تنقل شبكة اتصالات لاسلكية تعليمات المراقبين إلى الطيارين؛ وقد ربطت التقارير العطل بشبكة تديرها L3Harris لهذا الغرض، من دون توضيح ما إذا كانت تغذية الرادار تأثرت أيضًا.

**「التأثير」** أدى وقف الإقلاع الوطني الذي أصدرته إدارة الطيران الفيدرالية إلى تعطيل آلاف رحلات المغادرة في الولايات المتحدة، ولم يُرفع إلا بعد أكثر من أربع ساعات، ما يعني أن المسافرين وشركات الطيران واجهوا اضطرابًا واسعًا في جداول الرحلات.

**「نقاش المجتمع」** تباينت ملاحظات المشاركين بين رصد توقف الإقلاع في مطار لوس أنجلوس منذ نحو الساعة 10:30 صباحاً بتوقيت المحيط الهادي وتعطل موقع مطار سان فرانسيسكو، وبين ربط الحادث بطرح حديث لنظام ذكاء اصطناعي لإدارة الحركة الجوية وُصف بأنه متعثر. وتبقى هذه مشاهدات فردية واستنتاجات غير مؤكدة، ولا تثبت سبب العطل أو علاقته بذلك النظام.

<details><summary>References</summary>
<ul>
<li><a href="https://www.yahoo.com/news/us/article/faa-issues-nationwide-ground-stop-on-all-departing-flights-citing-communication-issue-213136811.html">FAA issues nationwide ground stop on all departing flights, citing...</a></li>
<li><a href="https://www.theguardian.com/us-news/live/2026/nov/13/us-politics-latest-news-updates-democrats-republicans-donald-trump-van-hollen-chuck-schumer?page=with:block-6af789c78f080d8d1c27a4b6">US flight outage live updates: FAA grounds thousands... | The Guardian</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.cpr.org/2026/11/13/flights-ground-stop-faa-dia/">UPDATE: National ground stop lifted after more than 4 hours ...</a></li>

</ul>
</details>

**Tags**: `#FAA ground stop`, `#air traffic control`, `#telecommunications outage`, `#critical infrastructure`, `#system reliability`

---

<a id="item-tech-news-3"></a>
### [تيم بيترز، من أوائل مساهمي بايثون، يتوفى عن 74 عامًا](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

أعلن غيدو فان روسم، مبتكر لغة بايثون، وفاة تيم بيترز، أحد أوائل مساهمي المجتمع، عن عمر 74 عامًا. ووفق الإعلان الذي نقله المصدر، كان بيترز ثاني مستخدم حقيقي لبايثون، ومؤلف خوارزمية الترتيب Timsort، وكاتب «زن بايثون» \(PEP 20\)، كما خدم 13 عامًا في مجلس إدارة مؤسسة بايثون البرمجية. لم يتضمن الإعلان تفاصيل عن سبب الوفاة.

telegram · zaihuapd · Nov 13, 09:55

**「خلفية」** خوارزمية Timsort هي خوارزمية فرز هجينة ابتكرها تيم بيترز، وقد ارتبط اسمه أيضًا بإسهامات واسعة في لغة Python وتنفيذها الأصلي CPython. أما PEP 20، المعروفة بـ«زن بايثون»، فهي مجموعة من 19 مبدأً إرشاديًا لكتابة برامج Python، صاغها بيترز ونشرها في القائمة البريدية للغة عام 1999، ثم سُجلت لاحقًا كوثيقة معلوماتية نشطة.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Tim_Peters_%28software_engineer%29">Tim Peters (software engineer) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Zen_of_Python">Zen of Python - Wikipedia</a></li>
<li><a href="https://peps.python.org/pep-0020/">PEP 20 – The Zen of Python | peps.python.org</a></li>

</ul>
</details>

**Tags**: `#Python`, `#Tim Peters`, `#Timsort`, `#PEP 20`, `#open source community`

---

<a id="item-tech-news-4"></a>
### [DeepSeek يوسّع واجهة API بقدرات تطبيقية وعرض محادثة مفتوح المصدر](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

وفقًا لمنشور على تلغرام، وسّع DeepSeek واجهة API لتشمل قدرات تطبيقية يمكن للمطورين تفعيلها عبر معاملات في الواجهة القائمة، مثل البحث مع التفكير العميق وإدخال الملفات وقراءة الروابط والصوت، مع تولّي الخادم استدعاء الأدوات وربط السياق تلقائيًا. وأضاف المنشور أن نموذج V4.1-Flash مدعوم في ثلاث واجهات API، وأن خدمات Search وFetch وOCR وASR وTTS يمكن استدعاؤها منفصلة. كما أشار إلى نشر نسخة تجريبية أمامية مفتوحة المصدر للمحادثة تتيح استيراد المحادثات السابقة وتشغيل واجهة DeepSeek محليًا، لكن التقرير لم يقدّم روابط التوثيق الأولية أو تفاصيل شروط الدعم والتوافر.

telegram · zaihuapd · Nov 13, 14:27

**「السياق السابق」** كانت واجهة DeepSeek البرمجية تتبع صيغة متوافقة مع OpenAI وAnthropic، ما يسمح باستخدام حزم SDK والأدوات المتوافقة معهما للوصول إليها. أما القدرات التي يقوم عليها تطبيق DeepSeek نفسه — البحث والملفات والروابط والصوت — فكانت قبل هذا الإعلان محصورة في التطبيق، وتؤكد صفحة أخبار DeepSeek الرسمية أنها باتت الآن متاحة عبر الواجهة بمعاملات قليلة أو كواجهات مستقلة مثل OCR وASR وTTS. النموذج V4.1-Flash المذكور في الإعلان هو نموذج MoE متعدد الوسائط بـ552 مليار معامل وسياق يصل إلى مليون رمز، وفق بطاقة النموذج على DeepInfra.

**「ما يعنيه ذلك لمن ينشر الواجهة محليًا」** على المطوّر الذي يريد تشغيل واجهة الدردشة المفتوحة المصدر محليًا ضبط الإعدادات عبر \`createConfig\(\{ apiOrigin, devServer \}\)\` لتحديد أصل الـAPI ووكيل خادم التطوير، لأن العرض التجريبي يستخدم النموذج \`deepseek-flash\` افتراضيًا ويمرّر الطلبات عبر واجهات Messages/Files المتوافقة مع Anthropic؛ أي أن اختيار نموذج آخر مثل V4.1-Flash المذكور في الإعلان يستلزم تعديل هذا الإعداد بدل الاعتماد على الوضع الافتراضي.

<details><summary>References</summary>
<ul>
<li><a href="https://deepinfra.com/deepseek-ai/DeepSeek-V4.1-Flash/api">DeepSeek V4.1 Flash API - Documentation - DeepInfra</a></li>
<li><a href="https://api-docs.deepseek.com/">Your First API Call | DeepSeek API Docs</a></li>
<li><a href="https://api-docs.deepseek.com/news/news261113/">The full DeepSeek App experience, now via API</a></li>
<li><a href="https://github.com/deepseek-ai/chat-demo/tree/main">GitHub - deepseek-ai/chat-demo: Chat Demo · GitHub</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#API`, `#LLM apps`, `#multimodal`, `#open source`

---

<a id="item-tech-news-5"></a>
### [OpenAI تطلق ChatGPT Wallet لمدفوعات الوكلاء في الولايات المتحدة](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

أعلنت OpenAI عن ChatGPT Wallet بالتعاون مع American Express وMastercard وVisa، ويتيح لمشتركي ChatGPT Pro في الولايات المتحدة بعمر 18 عامًا فأكثر، ممن لديهم بطاقات صادرة أمريكيًا، أن يجعلوا الوكلاء يشترون دون كشف رقم البطاقة الحقيقي. يتطلب كل شراء مراجعة المستخدم للسلعة والمبلغ وتأكيده عبر Face ID أو بصمة الإصبع، فيما تصدر شبكة الدفع رمزًا بديلًا عن رقم البطاقة. والميزة متاحة اعتبارًا من اليوم عبر dots.

telegram · zaihuapd · Nov 13, 15:43

**「السياق: رموز الدفع وشراء الوكلاء」** يقوم مفهوم رمز الدفع على استبدال رقم البطاقة الحقيقي برمز بديل تصدره شبكة الدفع، بحيث يُستخدم الرمز في إتمام العملية بدل كشف تفاصيل البطاقة الأصلية. ويضيف إعلان OpenAI طبقة جديدة هي السماح للوكلاء بالشراء داخل ChatGPT، مع قيام المستخدم بمراجعة كل عملية وتأكيدها عبر Face ID أو بصمة الإصبع.

**「الأثر」** عمليًا، يقتصر الوصول إلى المحفظة في هذا الإطلاق على مشتركي ChatGPT Pro في الولايات المتحدة الذين يستخدمون بطاقات صادرة هناك، لذا لا يستطيع المستخدمون خارج الولايات المتحدة أو حاملو بطاقات أجنبية الاستفادة منها.

**Tags**: `#OpenAI`, `#AI agents`, `#payments`, `#digital wallet`, `#tokenization`

---

## Financial News

<a id="item-finance-news-1"></a>
### [كانتور فيتزجيرالد تقلّص حصتها المعلنة في إنفيديا وسط تدقيق بشأن لوتنيك](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

ذكرت CNBC أن كانتور فيتزجيرالد، التي يقودها نجلا وزير التجارة الأمريكي هوارد لوتنيك، خفّضت عدد أسهم إنفيديا المُبلغ عنها بنحو 50% بين سبتمبر 2025 ومارس 2026 إلى 1.78 مليون سهم، بينما واصلت ترتيب تمويل لشركاء الشركة. يأتي ذلك وسط تدقيق في مقاومة لوتنيك المزعومة، وفق أكسيوس، لجهود تشديد الرقابة على شحنات رقائق إنفيديا إلى الصين، وبعد استقالة الرئيس التنفيذي جنسن هوانغ الخميس، من دون دليل على مخالفة أو تأثير على قرارات الوزير.

rss · CNBC Finance · Nov 13, 23:42

**「الخلفية」** وزارة التجارة الأمريكية هي الجهة المسؤولة عن ضوابط تصدير التكنولوجيا الحساسة، ومنها «قائمة الكيانات» التي تُدرَج فيها الشركات المقيَّدة. وكانت الوزارة تتعرض لضغط لإدراج «ميغاسبيد»، وهي شركة مقرها سنغافورة يُشتبه في تحويلها شرائح إنفيديا المتقدمة إلى الصين؛ ونقل «أكسيوس» أن لوتنيك قاوم ذلك، قبل أن يُعلن جنسن هوانغ استقالته من إنفيديا يوم الخميس.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/13/us-inflation-outlook-federal-reserve-rate-hike.html">Bessent blames Lutnick’s Commerce, slams Nvidia chip China leakage</a></li>
<li><a href="https://www.bbc.com/news/articles/c67429m3vem3o">How a sex scandal at Nvidia is putting pressure on the White House</a></li>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#export controls`, `#conflicts of interest`, `#semiconductor industry`, `#US-China tech policy`

---

<a id="item-finance-news-2"></a>
### [غولسبي: الفيدرالي «لديه عمل يقوم به» بشأن التضخم بعد ارتفاع أسعار المنتجين 6.5%](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 8.0/10

قال رئيس الاحتياطي الفيدرالي في شيكاغو، أوستان غولسبي، إن المركزي الأميركي «لديه بالتأكيد عمل يقوم به» لاستعادة مصداقيته في مكافحة التضخم، بعدما سجل مؤشر أسعار المنتجين زيادة سنوية بلغت 6.5% في أكتوبر، وهي الأعلى منذ نوفمبر 2022.

rss · CNBC Finance · Nov 13, 14:22

**「الخلفية」** يأتي ذلك وسط بقاء التضخم فوق هدف الفيدرالي البالغ 2%، وبعد قراءة أعلى من المتوقع لمؤشر أسعار المستهلك، فيما تسعّر أسواق العقود الآجلة بالكامل رفعاً بمقدار ربع نقطة مئوية في اجتماع 8-9 ديسمبر، وهو تسعير سوقي وليس قراراً فعلياً.

**Tags**: `#monetary policy`, `#inflation`, `#Federal Reserve`, `#PPI`, `#interest rates`

---

<a id="item-finance-news-3"></a>
### [月之暗面 تعيد هيكلة شركتها استعدادًا لطرح عام في هونغ كونغ](https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb) ⭐️ 7.0/10

تعيد شركة الذكاء الاصطناعي الصينية Moonshot AI هيكلة كيانها المؤسسي استعدادًا لطرح عام أولي في هونغ كونغ، وفقًا لتقرير صحيفة وول ستريت جورنال نقلًا عن أشخاص مطلعين. ويشمل ذلك إيقاف عمل الشركة القابضة المسجلة في جزر كايمان ونقل أسهم المستثمرين الأوائل بالدولار الأمريكي إلى الكيان التشغيلي الرئيسي للشركة داخل الصين.

telegram · zaihuapd · Nov 13, 11:29

**「الخلفية」** سبق أن أفادت بلومبرغ بأن «مونشوت إيه آي» قدّمت طلباً سرياً للاكتتاب في هونغ كونغ بعد جولة تمويل خاصة، ما يضع إعادة الهيكلة في سياق استعدادات طرح كانت قيد الإعداد.

**「مَن يتأثر」** يتأثر بهذا التغيير المستثمرون الأوائل الذين ستُنقل حصصهم من الشركة القابضة في جزر كايمان إلى الكيان التشغيلي الأساسي داخل الصين، ما يغيّر الشكل الذي يحملون به استثماراتهم ويفتح أمامهم مساراً محتملاً للبيع عبر الإدراج المزمَع في هونغ كونغ.

<details><summary>References</summary>
<ul>
<li><a href="https://bifu.co/news/detail/moonshot-ai-s-50-billion-valuation-a-question-of-peers">Moonshot AI &#x27;s $50 Billion Valuation : A Question of Peers</a></li>
<li><a href="https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb">China’s Moonshot AI Restructures to Pave Way for IPO</a></li>
<li><a href="https://aiweekly.co/alerts/moonshot-ai-unwinds-cayman-vehicle-for-50b-hong-kong-ipo">Moonshot AI Unwinds Cayman Vehicle for $50B Hong Kong IPO</a></li>

</ul>
</details>

**Tags**: `#Moonshot AI`, `#Hong Kong IPO`, `#corporate restructuring`, `#China AI`, `#startup financing`

---