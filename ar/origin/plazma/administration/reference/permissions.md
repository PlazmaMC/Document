---
description: تعرف على أذونات Plazma.
---

# 🛡️ أذونة

الصلاحيات هي أداة أمان بسيطة تحدد نطاق تفاعل اللاعب داخل الخادم.

يجب استخدام الإضافات مثل [LuckPerms](https://luckperms.net) للاستفادة الكاملة من الصلاحيات وتعديلها بسهولة.

***

## فهم نظام الصلاحيات الأساسي <a href="#id-1" id="id-1"></a>

يوفر Minecraft مجموعات صلاحيات إدارية أساسية.

يمكن تعيين صلاحيات [المشرفين](#user-content-fn-1)[^1] وكتل الأوامر، ويمكن تعديلها في [خصائص الخادم](configurations/property.md).

0. **اللاعب**\
   هو مجموعة صلاحيات تُمنح عادة لجميع اللاعبين.
1. **الوسيط**\
   يمكن تجاهل حماية الانبعاث.
2. **مدير العالم**\
   يمكن استخدام جميع الأوامر وكتل الأوامر المتعلقة بإدارة العالم.\
   هو مجموعة صلاحيات تُطبق افتراضيًا على حزم البيانات وكتل الأوامر.
3. **المدير**\
   يمكن استخدام جميع الأوامر المتعلقة بإدارة اللاعبين.
4. **المدير العام**\
   يمكن استخدام جميع الأوامر، بما في ذلك إدارة الخادم.\
   هو مجموعة صلاحيات تُطبق افتراضيًا على وحدة التحكم والمشرفين.

***

## تعيين الصلاحيات <a href="#id-2" id="id-2"></a>

***

## الصلاحيات الكاملة <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **الافتراضي**: `لا شيء`

يسمح للاعب بالانحناء والتفاعل مع الكيان لركوبه.

عند ركوب الكيان، يمكن للاعب التحكم في حركة الكيان باستخدام مفاتيح الحركة، والقفز أو التحليق باستخدام مفتاح القفز.

يتم إدخال [Namespaced ID](#user-content-fn-2)[^2] للكيان في `(Namespaced Key)`.

{% hint style="info" %}

**[Purpur سيتم تشغيلها فقط عند تمكين `(Entity) > ridable` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **الافتراضي**: `لا شيء`

يسمح للاعب باستخدام مهارات الكيان أثناء ركوبه.

ليست جميع مهارات الكيان متاحة. يرجى الرجوع إلى القائمة الكاملة للمهارات الخاصة المتاحة.

{% hint style="info" %}

**هل لديك أفكار جيدة للمهارات الخاصة؟**

نشر أفكارك على [Plazma Discord](https://plazmamc.org/discord) أو [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>عرض المهارات الخاصة المتاحة حاليًا</summary>

- **`crepper`**\
  عند الضغط على مفتاح القفز، سينفجر.\
  إذا كان للاعب أذونة `allow.powered.creeper`، فيمكنه الضغط المطول على مفتاح القفز للشحن.
- **`dolphin`**\
  عند الضغط على مفتاح القفز، سيقوم بالاندفاع.
- **`phantom`**\
  عند الضغط على مفتاح القفز، سيطلق اللهب.
- **`wither`**\
  عند التفاعل، سيطلق رأس الويذر.

</details>

{% hint style="info" %}

**[Purpur سيتم تشغيلها فقط عند تمكين `(Entity) > ridable` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/compass` الأمر](commands.md#compass).

#### `bukkit.command.credits`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/credits (Player)` الأمر](commands.md#credits).

عند كتابة `.other` بعد اسم الإذن، يسمح بالاستخدام للاعب آخر.

#### `bukkit.command.demo`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/demo (Player)` الأمر](commands.md#demo).

عند كتابة `.other` بعد اسم الإذن، يسمح بالاستخدام للاعب آخر.

#### `bukkit.command.ping`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/ping (Player)` الأمر](commands.md#ping).

عند كتابة `.other` بعد اسم الإذن، يسمح بالاستخدام للاعب آخر.

#### `bukkit.command.ram`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/ram` الأمر](commands.md#ram).

#### `bukkit.command.rambar`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/rambar (Player)` الأمر](commands.md#rambar).

عند كتابة `.other` بعد اسم الإذن، يسمح بالاستخدام للاعب آخر.

#### `bukkit.command.restart`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/restart` الأمر](commands.md#restart).

#### `bukkit.command.tps`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/tps` الأمر](commands.md#tps).

#### `bukkit.command.tpsbar`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/tpsbar (Player)` الأمر](commands.md#tpsbar).

عند كتابة `.other` بعد اسم الإذن، يسمح بالاستخدام للاعب آخر.

#### `bukkit.command.timings`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/timings` الأمر](commands.md#timings).

{% hint style="warning" %}

**تم إيقاف استخدام هذا الأمر.**

لمعرفة المزيد عن الأوامر المشابهة، يرجى التحقق من [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام [`/uptime` الأمر](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **الافتراضي**: `مدير العالم`

يسمح باستخدام الأمر `/gamemode (GameMode) (Player)`.

عند كتابة `.other` بعد اسم الإذن، يسمح بالاستخدام للاعب آخر.

#### `paper.antixray.bypass`

- **الافتراضي**: `لا شيء`

في حال تم تفعيل حظر الأشعة السينية، لن يتم تشويش الكتل للاعبين الذين لديهم الإذن.

هذا سيؤدي إلى تحسين الأداء لكلا الجانبين.

> لمعرفة كيفية ضبط حظر الأشعة السينية، يرجى الرجوع إلى الصفحة التالية.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **الافتراضي**: `لا شيء`

{% hint style="warning" %}

سيتم تغيير هذا الإذن إلى `plazma.bypass.watchdog` في النسخة 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **الافتراضي**: `لا شيء`

يسمح باستخدام رموز [الألوان](https://minecraft.wiki/w/Formatting_codes#Color_codes) في السنادي.

{% hint style="info" %}

**سيتم تشغيلها فقط عند تمكين `anvil > allow-colors` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **الافتراضي**: `لا شيء`

يسمح باستخدام رموز [التنسيق](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) في السنادي.

{% hint style="info" %}

**سيتم تشغيلها فقط عند تمكين `anvil > allow-colors` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **الافتراضي**: `لا شيء`

يسمح باستخدام علامات [MiniMessage](https://docs.advntr.dev/minimessage/format.html) في السنادي.

{% hint style="info" %}

**سيتم تشغيلها فقط عند تمكين `anvil > allow-minimessages` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **الافتراضي**: `لا شيء`

يسمح بتعطيل `الميل` باستخدام رموز التنسيق `&r` في السنادي.

{% hint style="info" %}

**سيتم تشغيلها فقط عند تمكين `anvil > allow-colors` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **الافتراضي**: `لا شيء`

عند توقيع اللاعب على كتاب، سيتم تطبيق رموز [التنسيق](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **الافتراضي**: `لا شيء`

يستثني اللاعب من طرد الخمول.

#### `purpur.debug.f3n`

- **الافتراضي**: `مدير العالم`

يسمح للاعب بتغيير وضع اللعبة باستخدام مفتاح `F3 + N`.

لن يعمل إذا لم يكن لديه الإذن المطلوب لهذا الوضع.

#### `purpur.drop.spawners`

- **الافتراضي**: `لا شيء`

عند تنقيب كتلة البيض، سيتم إسقاط كتلة البيض.

{% hint style="info" %}

**سيتم تشغيلها فقط عند تمكين `gameplay-mechanics > silk-touch` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **الافتراضي**: `لا شيء`

يغير حجم صندوق النهاية.

يمكن إدخال `one`, `two`, `three`, `four`, `five`, `six` في `(NumberString)`.

{% hint style="info" %}

**سيتم تشغيلها فقط عند تمكين `ender_chest > six-rows` و `ender_chest > use-permissions-for-rows` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **الافتراضي**: `لا شيء`

يسمح بعمل الصندوق الواقي حتى عند وجود توتم الخلود في المخزن.

{% hint style="info" %}

**يجب تفعيل `totem-of-undying-works-in-inventory` في [تكوينات Purpur العالمية](configurations/purpur/world.md) ليعمل.**

{% endhint %}

#### `purpur.joinFullServer`

- **الافتراضي**: `لا شيء`

يسمح للاعب بتجاوز الحد الأقصى لعدد اللاعبين المتصلين.

#### `purpur.mending_shift_click`

- **الافتراضي**: `لا شيء`

يسمح للاعب بإصلاح العناصر التي يحملها عندما يكون `جلوسًا والتفاعل`.

{% hint style="info" %}

**يجب تفعيل `shift-right-click-repairs-mending-points` في [تكوينات Purpur العالمية](configurations/purpur/world.md) ليعمل.**

{% endhint %}

#### `purpur.place.spawners`

- **الافتراضي**: `لا شيء`

يسمح للاعب بتثبيت مولدات الوحوش.

{% hint style="info" %}

**سيتم تشغيلها فقط عند تمكين `gameplay-mechanics > silk-touch` في [تكوينات Purpur العالمية](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **الافتراضي**: `لا شيء`

يسمح للاعب بالانتقال على الفور عند استخدام بوابة النيذر.

#### `purpur.sign.color`

- **الافتراضي**: `لا شيء`

يسمح باستخدام [أكواد الألوان](https://minecraft.wiki/w/Formatting_codes#Color_codes) على اللافتات.

{% hint style="info" %}

**يجب تفعيل `sign > allow-colors` في [تكوينات Purpur العالمية](configurations/purpur/world.md) ليعمل.**

{% endhint %}

#### `purpur.sign.magic`

- **الافتراضي**: `لا شيء`

يسمح باستخدام رمز التشويش `(&o)` على اللافتات.

{% hint style="info" %}

**يجب تفعيل `sign > allow-colors` في [تكوينات Purpur العالمية](configurations/purpur/world.md) ليعمل.**

{% endhint %}

#### `purpur.sign.style`

- **الافتراضي**: `لا شيء`

يسمح باستخدام [رموز التنسيق `(&o استثناء)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) على اللافتات.

{% hint style="info" %}

**يجب تفعيل `sign > allow-colors` في [تكوينات Purpur العالمية](configurations/purpur/world.md) ليعمل.**

{% endhint %}

#### `purpur.tnt.defuse`

- **الافتراضي**: `لا شيء`

يسمح للاعب بمنع انفجار TNT عن طريق التفاعل بالمقص.

{% hint style="info" %}

**يجب أن يكون `defuse-tnt-change` في [تكوينات Purpur العالمية](configurations/purpur/world.md) `0.0` أو أكبر ليعمل.**

{% endhint %}

### الصلاحيات المقررة

#### `plazma.bypass.ncr-require`

- **الافتراضي**: `لا شيء`

يسمح للاعب بالانضمام دون وجود تثبيت لمود [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**يجب تفعيل `no-chat-reports > require-install` في [تكوينات Plazma العالمية](configurations/plazma/world.md) ليعمل.**

{% endhint %}

***

[^1]: المشغل.

[^2]: مثال: `ender_dragon`
