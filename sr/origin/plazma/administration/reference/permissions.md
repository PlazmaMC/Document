---
description: Сазнајте више о овлашћењима Плазме.
---

# 🛡️ Овлашћења

권한은 서버 내 플레이어가 상호 작용 할 수 있는 범위를 설정하는 간단한 보안 도구입니다.

권한을 제대로 활용하고 쉽게 수정하려면 [LuckPerms](https://luckperms.net) 등의 플러그인을 사용해야 합니다.

***

## Разумети основни систем дозвола <a href="#id-1" id="id-1"></a>

У Minecraft-у постоје основне групе дозвола за управљање.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Играч**\
   Основна група дозвола која се обично додељује свим играчима.
2. **Посредник**\
   Може игнорисати спавање.
3. **Администратор света**\
   Може користити све команде и командне блокове повезане са управљањем светом.\
   Основна група дозвола која се примењује на датапакете и командне блокове.
4. **Администратор**\
   Може користити све команде повезане са управљањем играчима.
5. **Главни администратор**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Подразумевано**: `Ништа`

Дозвољава играчу да користи специјалне способности ентитета када су на њима.

Сви ентитети немају доступне све специјалне способности. Погледајте које све специјалне способности су доступне испод.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Ово омогућава обојицама да искусе побољшање перформанси.

> За информације о подешавању X-Ray-а, погледајте доле наведену страницу.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Подразумевано**: `Ништа`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Подразумевано**: `Ништа`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Подразумевано**: `Ништа`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Подразумевано**: `Ништа`

Омогућава коришћење [MiniMessage тагова](https://docs.advntr.dev/minimessage/format.html) на оруђу.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Подразумевано**: `Ништа`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Подразумевано**: `Ништа`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Подразумевано**: `Ништа`

Мења величину ендер ковчега.

У `(NumberString)` можете унети `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Подразумевано**: `Ништа`

Дозволи да Тотем бесмртности ради у инвентару.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Подразумевано**: `Ништа`

Дозволи играчу да игнорише ограничење броја прикључених играча.

#### `purpur.mending_shift_click`

- **Подразумевано**: `Ништа`

Дозволи играчу да поправи предмет који држи када `припадне и интеракција`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Подразумевано**: `Ништа`

Дозволи играчу да постави спавер.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Подразумевано**: `Ништа`

Дозволи играчу да одмахну према Нетер порталу.

#### `purpur.sign.color`

- **Подразумевано**: `Ништа`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Подразумевано**: `Ништа`

Дозволи коришћење кода за заштиту`(&o)` на табли.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Подразумевано**: `Ништа`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Подразумевано**: `Ништа`

Дозволи играчу да спречи TNT експлозију `интеракцијом` маказама.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Планирана дозвола

#### `plazma.bypass.ncr-require`

- **Подразумевано**: `Ништа`

Дозволи играчу да се прикључи чак и ако нема инсталиран мод [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Оператор.

[^2]: На пример: `ender_dragon`
