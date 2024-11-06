---
description: تعرف على أذونات Plazma.
---

# 🛡️ أذونة

الصلاحيات هي أداة أمان بسيطة تحدد نطاق تفاعل اللاعب داخل الخادم.

يجب استخدام الإضافات مثل [LuckPerms](https://luckperms.net) للاستفادة الكاملة من الصلاحيات وتعديلها بسهولة.

***

## فهم نظام الصلاحيات الأساسي <a href="#id-1" id="id-1"></a>

يوفر Minecraft مجموعات صلاحيات إدارية أساسية.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **اللاعب**\
   هو مجموعة صلاحيات تُمنح عادة لجميع اللاعبين.
2. **الوسيط**\
   يمكن تجاهل حماية الانبعاث.
3. **مدير العالم**\
   يمكن استخدام جميع الأوامر وكتل الأوامر المتعلقة بإدارة العالم.\
   هو مجموعة صلاحيات تُطبق افتراضيًا على حزم البيانات وكتل الأوامر.
4. **المدير**\
   يمكن استخدام جميع الأوامر المتعلقة بإدارة اللاعبين.
5. **المدير العام**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **الافتراضي**: `لا شيء`

يسمح للاعب باستخدام مهارات الكيان أثناء ركوبه.

ليست جميع مهارات الكيان متاحة. يرجى الرجوع إلى القائمة الكاملة للمهارات الخاصة المتاحة.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

هذا سيؤدي إلى تحسين الأداء لكلا الجانبين.

> لمعرفة كيفية ضبط حظر الأشعة السينية، يرجى الرجوع إلى الصفحة التالية.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **الافتراضي**: `لا شيء`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **الافتراضي**: `لا شيء`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **الافتراضي**: `لا شيء`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **الافتراضي**: `لا شيء`

يسمح باستخدام علامات [MiniMessage](https://docs.advntr.dev/minimessage/format.html) في السنادي.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **الافتراضي**: `لا شيء`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **الافتراضي**: `لا شيء`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **الافتراضي**: `لا شيء`

يغير حجم صندوق النهاية.

يمكن إدخال `one`, `two`, `three`, `four`, `five`, `six` في `(NumberString)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **الافتراضي**: `لا شيء`

يسمح بعمل الصندوق الواقي حتى عند وجود توتم الخلود في المخزن.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **الافتراضي**: `لا شيء`

يسمح للاعب بتجاوز الحد الأقصى لعدد اللاعبين المتصلين.

#### `purpur.mending_shift_click`

- **الافتراضي**: `لا شيء`

يسمح للاعب بإصلاح العناصر التي يحملها عندما يكون `جلوسًا والتفاعل`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **الافتراضي**: `لا شيء`

يسمح للاعب بتثبيت مولدات الوحوش.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **الافتراضي**: `لا شيء`

يسمح للاعب بالانتقال على الفور عند استخدام بوابة النيذر.

#### `purpur.sign.color`

- **الافتراضي**: `لا شيء`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **الافتراضي**: `لا شيء`

يسمح باستخدام رمز التشويش `(&o)` على اللافتات.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **الافتراضي**: `لا شيء`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **الافتراضي**: `لا شيء`

يسمح للاعب بمنع انفجار TNT عن طريق التفاعل بالمقص.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### الصلاحيات المقررة

#### `plazma.bypass.ncr-require`

- **الافتراضي**: `لا شيء`

يسمح للاعب بالانضمام دون وجود تثبيت لمود [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: المشغل.

[^2]: مثال: `ender_dragon`
