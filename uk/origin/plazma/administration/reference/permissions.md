---
description: Дізнайтеся про дозволи Plazma.
---

# 🛡️ Дозволи

Права - це простий інструмент безпеки, який визначає область взаємодії гравців на сервері.

Для належного використання та легкої зміни прав вам потрібно використовувати плагіни, такі як [LuckPerms](https://luckperms.net).

***

## Розуміння базової системи прав <a href="#id-1" id="id-1"></a>

У Minecraft є базові групи прав для управління.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Гравець**\
   Це стандартна група прав, яку отримує кожен гравець.
2. **Посередник**\
   Може ігнорувати захист від спавну.
3. **Адміністратор світу**\
   Має доступ до всіх команд та командних блоків, що стосуються управління світом.\
   Це базова група прав для даних пакетів та командних блоків.
4. **Адміністратор**\
   Має доступ до всіх команд, пов'язаних з управлінням гравцями.
5. **Головний адміністратор**\
   Має доступ до всіх команд, включаючи управління сервером.\
   Це базова група прав для консолі та адміністраторів.

***

## Налаштування прав <a href="#id-2" id="id-2"></a>

***

## Повні права <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Стандартно**: `Немає`

Дозволяє гравцеві кататися на істоті, взаємодіючи з нею, коли він вгамується.

Після того як гравець сідає на істоту, він може керувати її рухами за допомогою клавіш переміщення та стрибати або літати за допомогою клавіші стрибка.

У `(Namespaced Key)` вказується [Namespaced ID](#user-content-fn-2)[^2] істоти.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Стандартно**: `Немає`

Дозволяє гравцю використовувати особливі вміння істоти, на якій він сидить.

Не всі істоти мають доступ до особливих вмінь. Дивіться список доступних особливих вмінь нижче.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Поділіться своїми ідеями на [Plazma Discord](https://plazmamc.org/discord) або [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions) !
{% кінець нагадування %}

<details>

<summary>Переглянути доступні особливі вміння</summary>

- **`crepper`**\
  При натисканні клавіші стрибка вибухає.\
  Якщо у гравця є право `allow.powered.creeper`, він може заряджати вибух, утримуючи клавішу стрибка.
- **`dolphin`**\
  При натисканні клавіші стрибка дельфін робить стрибок.
- **`phantom`**\
  При натисканні клавіші стрибка фантом випускає полум'я.
- **`wither`**\
  При взаємодії викидає голову відьмака.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/credits (Player)`](commands.md#credits).

Після назви права додайте `.other`, щоб надати можливість використовувати іншим гравцям.

#### `bukkit.command.demo`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/demo (Player)`](commands.md#demo).

Після назви права додайте `.other`, щоб надати можливість використовувати іншим гравцям.

#### `bukkit.command.ping`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/ping (Player)`](commands.md#ping).

Після назви права додайте `.other`, щоб надати можливість використовувати іншим гравцям.

#### `bukkit.command.ram`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/rambar (Player)`](commands.md#rambar).

Після назви права додайте `.other`, щоб надати можливість використовувати іншим гравцям.

#### `bukkit.command.restart`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/tpsbar (Player)`](commands.md#tpsbar).

Після назви права додайте `.other`, щоб надати можливість використовувати іншим гравцям.

#### `bukkit.command.timings`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/timings`](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Дізнайтеся більше про подібні команди на [Spark](https://spark.lucko.me/docs/Command-Usage).
{% кінець нагадування %}

#### `bukkit.command.uptime`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Стандартно**: `Адміністратор світу`

Дозволяє використовувати команду [`/gamemode (GameMode) (Player)`](commands.md#gamemode).

Після назви права додайте `.other`, щоб надати можливість використовувати іншим гравцям.

#### `paper.antixray.bypass`

- **Стандартно**: `Немає`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Це дозволяє покращити продуктивність обох сторін.

> Дізнайтеся більше про налаштування X-Ray на вказаній сторінці.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Стандартно**: `Немає`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% кінець нагадування %}

#### `purpur.anvil.color`

- **Стандартно**: `Немає`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Стандартно**: `Немає`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Стандартно**: `Немає`

Дозволяє використовувати [міні-повідомлення теги](https://docs.advntr.dev/minimessage/format.html) на наковальні.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Стандартно**: `Немає`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Стандартно**: `Немає`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Стандартно**: `Немає`

Виключає гравця з списку видалення за бездіяльність.

#### `purpur.debug.f3n`

- **Стандартно**: `Адміністратор світу`

Дозволяє гравцю змінювати режим гри за допомогою клавіші `F3 + N`.

Це працює тільки якщо у гравця є відповідне право.

#### `purpur.drop.spawners`

- **Стандартно**: `Немає`

Після видобування спавнера за допомогою встановлених у конфігурації предметів, спавнер буде випущено.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Стандартно**: `Немає`

Змінює розмір ендер-скрині.

У `(NumberString)` можна ввести `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Стандартно**: `Немає`

Дозволяє працювати з тотемом бессмертя, якщо він є в інвентарі.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Стандартно**: `Немає`

Дозволяє гравцю ігнорувати обмеження на кількість підключених користувачів.

#### `purpur.mending_shift_click`

- **Стандартно**: `Немає`

Дозволяє гравцю відремонтувати триманий предмет, коли він `присідає та взаємодіє`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Стандартно**: `Немає`

Дозволяє гравцю встановлювати спавнери.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Стандартно**: `Немає`

Забезпечує миттєве телепортування гравця після використання порталу до Незалежного Світу.

#### `purpur.sign.color`

- **Стандартно**: `Немає`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Стандартно**: `Немає`

Дозволяє використовувати коди затемнення на табличках `(&о)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Стандартно**: `Немає`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Стандартно**: `Немає`

Дозволяє гравцеві за допомогою ножиць `взаємодіяти` для запобігання вибуху TNT.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Представлені дозволи

#### `plazma.bypass.ncr-require`

- **Стандартно**: `Немає`

Дозволяє гравцеві підключатися навіть якщо модуль [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) не встановлено.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Оператор.

[^2]: Наприклад: `ender_dragon`
