---
description: تعرف على كيفية تخصيص الخادم.
---

# 📶 التطور

السبب وراء استخدام منصة الخادم المعدلة مثل Plazma بدلاً من استخدام منصة الخادم الرسمية المقدمة من Mojang Studios هو القدرة القوية على التخصيص التي يمكن أن تكون متاحة.

فيما يلي بعض الطرق لتخصيص واستخدام Plazma.

## تعديل التكوين <a href="#id-1" id="id-1"></a>

أساسيات تخصيص Plazma هي تعديل التكوين مباشرة.

Plazma يوفر إعدادات تكوين قوية تتضمن آليات اللعبة وخصائص المخلوقات.

يرجى الرجوع إلى الصفحة التالية لمزيد من المعلومات حول تكوين Plazma.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

## استخدام الإضافات <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma تدعم بشكل طبيعي جميع الإضافات القائمة على الورق.**

بالنسبة لإضافات Spigot ، قد لا تعمل بعضها بسبب تغييرات التعيين في Paper اعتبارًا من الإصدار 1.20.5،
ولكن العديد من الإضافات التي تعتمد على Paper مثل Paper و Pufferfish و Purpur تعمل جميعًا على Plazma،
وإذا لم تعمل بشكل صحيح ، فهذا يعتبر خطأ في Plazma لذا يرجى [الإبلاغ عنه على الفور.](../diagnosis/plugins.md)

{% endhint %}

هذا هو السبب الرئيسي لاستخدام Plazma وأقوى طريقة لتخصيص Plazma.
بيئة الإضافات القوية لـ Plazma تسمح بتخصيص الخادم بسهولة.

هناك عدة طرق للبحث عن الإضافات وتنزيلها. بعض الإضافات
تُرفع إلى خدمات مستودع عام وبعضها يتم تحميله على GitHub أو موقع الويب الخاص بها.

{% hint style="caution" %}

**الإضافات يمكنها الوصول مباشرة إلى النظام!**

قبل تطبيق الإضافات، استخدم خدمات مثل VirusTotal للتحقق من سلامتها دائمًا، أو
قم بتنزيل الإضافات من خدمات موثوقة.

{% endhint %}

هناك العديد من الخدمات المستخدمة لتنزيل الإضافات. من بينها، [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) وغيرها من الخدمات تخضع الإضافات لعملية تقييم قبل تحميلها، ويتم التعامل مع الإضافات غير الآمنة على الفور لضمان تداول الإضافات الآمنة فقط.

### تطبيق الإضافات <a href="#id-2.1" id="id-2.1"></a>

بمجرد تنزيل الإضافات، الآن حان الوقت لتطبيقها.

1. الإضافات عادة ما تكون بصيغة `.jar` أو `ملف تنفيذي جافا`.\
   بعض الإضافات قد تكون مضغوطة، في هذه الحالة
   قم بفك الضغط واستخدم الملف الذي يحتوي على `bukkit`, `spigot` أو `paper` في اسمه،
   وفي حال وجود ملف يحتوي على `fat` يجب استخدام الملف `fat`.
2. ضع الملف الذي تم تنزيله في مجلد `plugins` في مجلد الخادم وأعد تشغيل الخادم.
3. عند بدء تشغيل Plazma، ستظهر محتويات جديدة على الواجهة.
   هذا يعني أن Plazma قد قامت بتحميل الإضافات بنجاح.
4. حتى إذا تم تحميل الإضافات بنجاح، قد لا تبدأ الإضافات بالعمل.
   يمكنك استخدام الأمر `/plugins` لعرض الإضافات المحملة حاليًا على الخادم.
   إذا كانت أسماء الإضافات التي قمت بتثبيتها ليست باللون <mark style="background-color:red;">الأحمر</mark>
   بل <mark style="background-color:green;">الأخضر</mark>، فهذا يعني أن الإضافات قد تم تحميلها بنجاح.

إذا لم يتم تحميل الإضافات بشكل صحيح، يمكنك العثور على حلول للمشكلة في الصفحة التالية.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## استخدام حزم البيانات <a href="#id-3" id="id-3"></a>

حزم البيانات هي طريقة لتخصيص Minecraft بشكل أساسي،
تشبه [حزم الموارد](#user-content-fn-1)[^1].

من خلال حزم البيانات، يمكنك إجراء تعديلات على جزء من اللعبة مثل إضافة مجموعات جديدة من الكائنات والتحديات.

{% hint style="caution" %}

**حزم البيانات يمكن أن تلحق ضررًا بالعالم!**

بعض حزم البيانات المعطوبة يمكن أن تلحق ضررًا بالعالم، وهذا لا يمكن التراجع عنه.

لذلك، يُنصح بعمل نسخ احتياطية للعالم قبل تطبيق حزم البيانات.

{% endhint %}

يمكنك تنزيل حزم البيانات من عدة خدمات مثل [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) وغيرها.

بمجرد تنزيل حزم البيانات، يمكنك وضعها في مجلد `datapacks` في مجلد العالم في الخادم لتطبيقها.
إذا لم يكن هناك مجلد، يمكنك إنشاؤه لإضافة الحزم.

{% hint style="warning" %}

**[قد لا يتم تطبيقه بشكل صحيح عند التطبيق الأول لبعض حزم البيانات](#user-content-fn-2)[^2].**

للتأكد من ذلك، يُوصى بإعادة تشغيل الخادم **مرتين**.

{% endhint %}

حزم البيانات يمكن أن تتلف بسهولة مع تحديثات Minecraft.

خاصة عند تلف حزم البيانات بشكل كامل، يمكن أن يؤدي ذلك إلى تعطل الخادم،
لذا من المهم إجراء اختبارات كافية قبل تحديث الخادم.

{% hint style="info" %}

**يمكنك تعطيل جميع حزم البيانات وبدء الخادم بإدخال `safeMode` بعد أمر بدء التشغيل.**

[لمزيد من المعلومات، يرجى الرجوع إلى `المرجع > الوسائط والخصائص`](../reference/arguments.md#safemode)

{% endhint %}

يمكنك التحقق من الحزم المطبقة باستخدام الأمر `/datapack list`.

***

## التحسينات <a href="#id-4" id="id-4"></a>

تم تطبيق العديد من تصحيحات التحسين على Plazma. بالإضافة إلى ذلك، عند بدء Plazma لأول مرة، سيتم تحسين التكوين تلقائيًا، لذا لن تحتاج إلى إجراء أي عمليات تحسين إضافية إذا اتبعت تعليمات [البدء](./README.md).

ومع ذلك، في حال تواجد العديد من اللاعبين أو كان حجم العالم كبيرًا، يمكنك إجراء عمليات تحسين إضافية من خلال الدليل أدناه.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## الوكيل <a href="#id-5" id="id-5"></a>

يقوم الوكيل بربط الخوادم مع بعضها البعض ويسمح للاعبين بالانتقال بين الخوادم أو التواصل مع خوادم أخرى دون عناء.

لمزيد من المعلومات حول ضبط الوكيل بشكل آمن وصحيح، يرجى الرجوع إلى الصفحة أدناه.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## الأمان <a href="#id-5" id="id-5"></a>

تطورت Minecraft إلى درجة يمكن للمستخدمين العثور بسهولة على [محرك هجوم الثغرات](#user-content-fn-3)[^3] عبر الإنترنت.

على الرغم من أن معظم الثغرات التي يمكن تنفيذها في الألعاب العادية تكون [محظورة بشكل افتراضي](#user-content-fn-4)[^4]،
إلا أن استغلال الثغرات عبر تحميلات الأطراف الثالثة ليس محظورًا.

لذا، في حال كان الخادم معرضًا للعامة، يُوصى بتثبيت إضافات مثل مانع الغش وضبط الوكيل وإعادة التشغيل التلقائي والنسخ الاحتياطي لضمان استعادة سريعة في حالة تعطل الخادم.

### ضبط الأذونات <a href="#id-5.1" id="id-5.1"></a>

قد تحتوي أوامر الإدارة لبعض الإضافات على ثغرات إذا لم يتم ضبط الأذونات بشكل صحيح.

يُوصى باستخدام إضافات إدارة الأذونات مثل [LuckPerms](https://luckperms.net/) لتقييد أذونات المستخدمين العاديين.

### منع X-Ray <a href="#id-5.2" id="id-5.2"></a>

يُعتبر X-Ray واحدة من الثغرات التي يمكن استغلالها بسهولة حتى في عملاء التحسين الأساسيين.

توفر Plazma تكوينًا يمكن من خلاله منع X-Ray بشكل افتراضي.

يرجى الرجوع إلى الصفحة أدناه لمزيد من التفاصيل حول كيفية منع X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### القائمة البيضاء <a href="#id-5.3" id="id-5.3"></a>

في حال رغبت في السماح بالوصول إلى الخادم لبعض المستخدمين فقط،
يُوصى بإما استخدام [Ngrok](./README.md#id-6.2) لاستخدام [عنوان الخادم المشفر](#user-content-fn-5)[^5] أو ضبط القائمة البيضاء لمنع الوصول للاعبين الآخرين.

يمكنك تمكين وصول اللاعبين عن طريق `/whitelist add <player>` من خادم الوحدات النمطية، أو
حظر وصولهم مرة أخرى باستخدام `/whitelist remove <player>`.

لعرض اللاعبين المسموح لهم بالوصول، استخدم `/whitelist query`.

***

[^1]: أو إضافة Minecraft: Bedrock Edition.

[^2]: إضافة مجموعات جديدة من الكائنات والتحديات.

[^3]: يُشار عادةً إلى ذلك باسم "التعديل".

[^4]: قد لا تكون الثغرات محظورة في حال عدم تحسين التكوين أو كون Plazma قديمًا أو وجود ثغرات جديدة.

[^5]: يتم الوصول إلى الخادم عندما يقوم اللاعبون بالاتصال من خلال خادم الوكيل Ngrok، ويتم تغيير عنوان Ngrok الصادر مع كل إعادة تشغيل.