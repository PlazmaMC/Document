---
description: Сазнајте више о овлашћењима Плазме.
---

# 🛡️ Овлашћења

권한은 서버 내 플레이어가 상호 작용 할 수 있는 범위를 설정하는 간단한 보안 도구입니다.

권한을 제대로 활용하고 쉽게 수정하려면 [LuckPerms](https://luckperms.net) 등의 플러그인을 사용해야 합니다.

***

## Разумети основни систем дозвола <a href="#id-1" id="id-1"></a>

У Minecraft-у постоје основне групе дозвола за управљање.

Можете поставити дозволе за [администраторе](#user-content-fn-1)[^1] и командне блокове, које можете изменити у [подешавањима сервера](configurations/property.md).

0. **Играч**\
   Основна група дозвола која се обично додељује свим играчима.
1. **Посредник**\
   Може игнорисати спавање.
2. **Администратор света**\
   Може користити све команде и командне блокове повезане са управљањем светом.\
   Основна група дозвола која се примењује на датапакете и командне блокове.
3. **Администратор**\
   Може користити све команде повезане са управљањем играчима.
4. **Главни администратор**\
   Може користити све команде повезане са управљањем сервером.\
   Основна група дозвола која се примењује на конзолу и администраторе.

***

## Постављање дозвола <a href="#id-2" id="id-2"></a>

***

## Све дозволе <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Подразумевано**: `Ништа`

Дозвољава играчу да се спусти и упозна са ентитетом.

Када се на ентитету, може му управљати помоћу `клавише за кретање`, а може скакати или летети помоћу `клавише за скакање`.

У `(Namespaced Key)` се уноси [Namespaced ID](#user-content-fn-2)[^2] ентитета.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `(Entity) > ridable` активирано.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Подразумевано**: `Ништа`

Дозвољава играчу да користи специјалне способности ентитета када су на њима.

Сви ентитети немају доступне све специјалне способности. Погледајте које све специјалне способности су доступне испод.

{% hint style="info" %}

**Имате добру идеју за специјалну способност?**

Објавите идеју на [Plazma Discord](https://plazmamc.org/discord) или [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Погледајте тренутно доступне специјалне способности</summary>

- **`crepper`**\
  Када притиснете `клавиш за скакање`, ентитет експлодира.\
  Ако играч има дозволу `allow.powered.creeper`, може држати `клавиш за скакање` за пунење експлозије.
- **`dolphin`**\
  Када притиснете `клавиш за скакање`, ентитет навали напред.
- **`phantom`**\
  Када притиснете `клавиш за скакање`, ентитет пуца пламеном.
- **`wither`**\
  Када се `упусти` у ентитет, испаљује главу витера.

</details>

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `(Entity) > ridable` активирано.**

{% endhint %}

#### `bukkit.command.compass`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/compass` команде](commands.md#compass).

#### `bukkit.command.credits`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/credits (Играч)` команде](commands.md#credits).

Додавање `.other` на крај имена дозволе омогућава њено коришћење од стране других играча.

#### `bukkit.command.demo`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/demo (Играч)` команде](commands.md#demo).

Додавање `.other` на крај имена дозволе омогућава њено коришћење од стране других играча.

#### `bukkit.command.ping`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/ping (Играч)` команде](commands.md#ping).

Додавање `.other` на крај имена дозволе омогућава њено коришћење од стране других играча.

#### `bukkit.command.ram`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/ram` команде](commands.md#ram).

#### `bukkit.command.rambar`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/rambar (Играч)` команде](commands.md#rambar).

Додавање `.other` на крај имена дозволе омогућава њено коришћење од стране других играча.

#### `bukkit.command.restart`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/restart` команде](commands.md#restart).

#### `bukkit.command.tps`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/tps` команде](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/tpsbar (Играч)` команде](commands.md#tpsbar).

Додавање `.other` на крај имена дозволе омогућава њено коришћење од стране других играча.

#### `bukkit.command.timings`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/timings` команде](commands.md#timings).

{% hint style="warning" %}

**Ова команда је прекинута.**

Погледајте [Spark](https://spark.lucko.me/docs/Command-Usage) за сличне функције.

{% endhint %}

#### `bukkit.command.uptime`

- **Подразумевано**: `Администратор света`

Омогућава коришћење [`/uptime` команде](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Подразумевано**: `Администратор света`

Омогућава коришћење команде `/gamemode (GameMode) (Играч)`.

Додавање `.other` на крај имена дозволе омогућава њено коришћење од стране других играча.

#### `paper.antixray.bypass`

- **Подразумевано**: `Ништа`

Ако је активирано [блокирање X-Ray-a](../expert/xray.md), играчима са дозволом неће бити наметнуто замагљивање блокова за спречавање X-Ray-a.

Ово омогућава обојицама да искусе побољшање перформанси.

> За информације о подешавању X-Ray-а, погледајте доле наведену страницу.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Подразумевано**: `Ништа`

{% hint style="warning" %}

Ова дозвола ће бити промењена у `plazma.bypass.watchdog` у верзији 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Подразумевано**: `Ништа`

Омогућава коришћење [кодова боја](https://minecraft.wiki/w/Formatting_codes#Color_codes) на оруђу.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `anvil > allow-colors` активирано.**

{% endhint %}

#### `purpur.anvil.format`

- **Подразумевано**: `Ништа`

Омогућава коришћење [стилских кодова](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) на оруђу.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `anvil > allow-colors` активирано.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Подразумевано**: `Ништа`

Омогућава коришћење [MiniMessage тагова](https://docs.advntr.dev/minimessage/format.html) на оруђу.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `anvil > allow-minimessages` активирано.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Подразумевано**: `Ништа`

Омогућава искључивање `нагиба слова` помоћу стилских кодова `&r` на оруђу.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `anvil > allow-colors` активирано.**

{% endhint %}

#### `purpur.book.color.sign`

- **Подразумевано**: `Ништа`

Када играч потпише књигу, примењују се [стилски кодови](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Подразумевано**: `Ништа`

Искључује играче из избацивања због неактивности.

#### `purpur.debug.f3n`

- **Подразумевано**: `Администратор света`

Омогућава играчима да промене режим игре помоћу тастера `F3 + N`.

Ова функција не ради ако немате дозволу за тај режим игре.

#### `purpur.drop.spawners`

- **Подразумевано**: `Ништа`

Када копате спавање блокове са предметима по вашем избору, спавање блокови ће пасти.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `gameplay-mechanics > silk-touch` активирано.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Подразумевано**: `Ништа`

Мења величину ендер ковчега.

У `(NumberString)` можете унети `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `ender_chest > six-rows` и `ender_chest > use-permissions-for-rows` активирано.**

{% endhint %}

#### `purpur.inventory_totem`

- **Подразумевано**: `Ништа`

Дозволи да Тотем бесмртности ради у инвентару.

{% hint style="info" %}

**На [Пурпурној конфигурацији света](configurations/purpur/world.md) морате активирати `totem-of-undying-works-in-inventory` да бисте омогућили рад.**

{% endhint %}

#### `purpur.joinFullServer`

- **Подразумевано**: `Ништа`

Дозволи играчу да игнорише ограничење броја прикључених играча.

#### `purpur.mending_shift_click`

- **Подразумевано**: `Ништа`

Дозволи играчу да поправи предмет који држи када `припадне и интеракција`.

{% hint style="info" %}

**На [Пурпурној конфигурацији света](configurations/purpur/world.md) морате активирати `shift-right-click-repairs-mending-points` да бисте омогућили рад.**

{% endhint %}

#### `purpur.place.spawners`

- **Подразумевано**: `Ништа`

Дозволи играчу да постави спавер.

{% hint style="info" %}

**[Пурпурна конфигурација света](configurations/purpur/world.md) функционише само ако је `gameplay-mechanics > silk-touch` активирано.**

{% endhint %}

#### `purpur.portal.instant`

- **Подразумевано**: `Ништа`

Дозволи играчу да одмахну према Нетер порталу.

#### `purpur.sign.color`

- **Подразумевано**: `Ништа`

Дозволи коришћење [бојних кодова](https://minecraft.wiki/w/Formatting_codes#Color_codes) на табли.

{% hint style="info" %}

**На [Пурпурној конфигурацији света](configurations/purpur/world.md) морате активирати `sign > allow-colors` да бисте омогућили рад.**

{% endhint %}

#### `purpur.sign.magic`

- **Подразумевано**: `Ништа`

Дозволи коришћење кода за заштиту`(&o)` на табли.

{% hint style="info" %}

**На [Пурпурној конфигурацији света](configurations/purpur/world.md) морате активирати `sign > allow-colors` да бисте омогућили рад.**

{% endhint %}

#### `purpur.sign.style`

- **Подразумевано**: `Ништа`

Дозволи коришћење [стилских кодова `(&o искључено)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) на табли.

{% hint style="info" %}

**На [Пурпурној конфигурацији света](configurations/purpur/world.md) морате активирати `sign > allow-colors` да бисте омогућили рад.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Подразумевано**: `Ништа`

Дозволи играчу да спречи TNT експлозију `интеракцијом` маказама.

{% hint style="info" %}

**На [Пурпурној конфигурацији света](configurations/purpur/world.md) морате имати `defuse-tnt-change` веће од `0.0` да бисте омогућили рад.**

{% endhint %}

### Планирана дозвола

#### `plazma.bypass.ncr-require`

- **Подразумевано**: `Ништа`

Дозволи играчу да се прикључи чак и ако нема инсталиран мод [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**На [Плазма конфигурацији света](configurations/plazma/world.md) морате активирати `no-chat-reports > require-install` да бисте омогућили рад.**

{% endhint %}

***

[^1]: Оператор.

[^2]: На пример: `ender_dragon`
