---
description: Monyo me Plazma ki nyingi.
---

# 🛡️ Nyingi

Lok ma kwo ne pi server, pe olal ki player dong i kwo tic mukene iye kwede i pwonye kwede.

Lok ma kwo ne pi kwede, kicoyo kicoyo ka [LuckPerms](https://luckperms.net) ki dong i kwo tic.

***

## Kwede iye kwede Acelo <a href="#id-1" id="id-1"></a>

Minecraft ma kwo ne pi kwede iye kwede ma pwonye i kwo tic.

[Lok me iye](#user-content-fn-1)[^1] ki dong i kwo tic ma lok me [server](configurations/property.md) ma iye kwede.

0. **Player**\
   Kicoyo pa player me cok i kwo tic.
1. **Mediator**\
   Kicoyo pa kwo di gang me opwonyo.
2. **Lok me iye**\
   Kicoyo pa iye me kwo tic ma iye me [command block](configurations/property.md) ki dong i kwo tic.\
   Kicoyo pa data pack ma command block iye kwede me kwede i kwo tic.
3. **Admin**\
   Kicoyo pa player me cok ma iye me [command](configurations/property.md) ki dong i kwo tic.
4. **Admin mukene**\
   Kicoyo pa lok me server ki dong i kwo tic ma iye me [command](configurations/property.md) ki dong i kwo tic.\
   Kicoyo pa console mukene opwonyo me kwo tic.

***

## Kwo tic iye kwede <a href="#id-2" id="id-2"></a>

***

## Kwede iye kwede <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Lok me iye**: `pek`

Player mukene i entiti me `kwo coko` ki dong ma i entiti me kwo tic me iye me kwo tic.

Entiti me kwo coko, player mukene `kwo kwo` ki entiti me kwo coko ma, `kwo jump` ki dong ma iye kwo tic.

`(Namespaced Key)` ma entiti me [Namespaced ID](#user-content-fn-2)[^2] ki waco.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `(Entity) > ridable` ki gengo ma cok i kwo tic.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Lok me iye**: `pek`

Player mukene entiti me kwo coko, entiti me kwo tic me kwo tic ki dong i kwo tic.

Entiti me kwo coko mape kwo tic ki dong. Kwede iye kwede entiti me kwo tic ki gengo i kom.

{% hint style="info" %}

**Kwo tic ki gengo i kom meywe pe?**

[Plazma Discord](https://plazmamc.org/discord) wacel [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions) ki dong i kwo tic!

{% endhint %}

<details>

<summary>Cel ma iye i kwo tic ki gengo</summary>

- **`crepper`**\
  `kwo jump` ki dong ma kwo coko.\
  Player mukene `allow.powered.creeper` kwede i kwo tic, `kwo jump` ki dong ma kwo tic.
- **`dolphin`**\
  `kwo jump` ki dong ma kwo coko.
- **`phantom`**\
  `kwo jump` ki dong ma kwo coko.
- **`wither`**\
  `kwo coko` ma wither head ki dong ma kwo coko.

</details>

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `(Entity) > ridable` ki gengo ma cok i kwo tic.**

{% endhint %}

#### `bukkit.command.compass`

- **Lok me iye**: `Lok me iye mukene`

[`/compass` command](commands.md#compass) ki dong i kwo tic.

#### `bukkit.command.credits`

- **Lok me iye**: `Lok me iye mukene`

[`/credits (Player)` command](commands.md#credits) ki dong i kwo tic.

Kwede iye kwede `.other` wacel pe kwo tic iye kwede player mukene ki dong i kwo tic.

#### `bukkit.command.demo`

- **Lok me iye**: `Lok me iye mukene`

[`/demo (Player)` command](commands.md#demo) ki dong i kwo tic.

Kwede iye kwede `.other` wacel pe kwo tic iye kwede player mukene ki dong i kwo tic.

#### `bukkit.command.ping`

- **Lok me iye**: `Lok me iye mukene`

[`/ping (Player)` command](commands.md#ping) ki dong i kwo tic.

Kwede iye kwede `.other` wacel pe kwo tic iye kwede player mukene ki dong i kwo tic.

#### `bukkit.command.ram`

- **Lok me iye**: `Lok me iye mukene`

[`/ram` command](commands.md#ram) ki dong i kwo tic.

#### `bukkit.command.rambar`

- **Lok me iye**: `Lok me iye mukene`

[`/rambar (Player)` command](commands.md#rambar) ki dong i kwo tic.

Kwede iye kwede `.other` wacel pe kwo tic iye kwede player mukene ki dong i kwo tic.

#### `bukkit.command.restart`

- **Lok me iye**: `Lok me iye mukene`

[`/restart` command](commands.md#restart) ki dong i kwo tic.

#### `bukkit.command.tps`

- **Lok me iye**: `Lok me iye mukene`

[`/tps` command](commands.md#tps) ki dong i kwo tic.

#### `bukkit.command.tpsbar`

- **Lok me iye**: `Lok me iye mukene`

[`/tpsbar (Player)` command](commands.md#tpsbar) ki dong i kwo tic.

Kwede iye kwede `.other` wacel pe kwo tic iye kwede player mukene ki dong i kwo tic.

#### `bukkit.command.timings`

- **Lok me iye**: `Lok me iye mukene`

[`/timings` command](commands.md#timings) ki dong i kwo tic.

{% hint style="warning" %}

**Lok me iye mukene kwede i kwo tic.**

Kwede iye ki dong ma kwo tic ki gengo, wacel [Spark](https://spark.lucko.me/docs/Command-Usage) ki dong i kwo tic.

{% endhint %}

#### `bukkit.command.uptime`

- **Lok me iye**: `Lok me iye mukene`

[`/uptime` command](commands.md#uptime) ki dong i kwo tic.

#### `minecraft.command.gamemode.(GameMode)`

- **Lok me iye**: `Lok me iye mukene`

`/gamemode (GameMode) (Player)` command ki dong i kwo tic.

Kwede iye kwede `.other` wacel pe kwo tic iye kwede player mukene ki dong i kwo tic.

#### `paper.antixray.bypass`

- **Lok me iye**: `pek`

[X-Ray pek](../expert/xray.md) ki mukene, wacel
kwo tic mukene player me pek i kwo tic, X-Ray pek ki dong ma kwo tic.

Kwo tic ma iye me kwo tic iye kwede i kwo tic.

> X-Ray kwede iye ki dong ma iye mukene, wacel i kom pek ki dong i kwo tic.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Lok me iye**: `pek`

{% hint style="warning" %}

Kwo tic mukene 1.20.5 me `plazma.bypass.watchdog` wacel pek i kwo tic.

{% endhint %}

#### `purpur.anvil.color`

- **Lok me iye**: `pek`

Moru ma [color code](https://minecraft.wiki/w/Formatting_codes#Color_codes) ki mukene.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `anvil > allow-colors` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.anvil.format`

- **Lok me iye**: `pek`

Moru ma [styling code](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) ki mukene.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `anvil > allow-colors` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Lok me iye**: `pek`

Moru ma [MiniMessage tag](https://docs.advntr.dev/minimessage/format.html) ki mukene.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `anvil > allow-minimessages` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Lok me iye**: `pek`

Moru ma [`&r` styling code](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) ki mukene `italic` ki dong ma kwo tic.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `anvil > allow-colors` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.book.color.sign`

- **Lok me iye**: `pek`

Player mukene buk me cok, [styling code](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) ki dong ma kwo tic.

#### `purpur.bypassIdleKick`

- **Lok me iye**: `pek`

Player mukene kwo tic ki dong i kwo tic.

#### `purpur.debug.f3n`

- **Lok me iye**: `Lok me iye mukene`

Player mukene `F3 + N` key ki dong ma kwo tic.

Kwo tic mukene kwede iye ki dong ma kwo tic.

#### `purpur.drop.spawners`

- **Lok me iye**: `pek`

Gengo wacel waco item ma iye kwo coko, item ma iye kwo tic ki dong i kwo tic.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `gameplay-mechanics > silk-touch` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Lok me iye**: `pek`

Ender chest me cok iye kwo tic ki dong.

`(NumberString)` wacel `one`, `two`, `three`, `four`, `five`, `six` ki waco.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `ender_chest > six-rows` wacel `ender_chest > use-permissions-for-rows` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.inventory_totem`

- **Lok me iye**: `pek`

Totem me kwo tic ma iye me kwo tic ki dong i kwo tic.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `totem-of-undying-works-in-inventory` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.joinFullServer`

- **Lok me iye**: `pek`

Kica me kwanyo kwede kacel ma kicel i kare ma en aye.

#### `purpur.mending_shift_click`

- **Lok me iye**: `pek`

Kica me kwanyo kwede 'kwo cwek i cwek' ki kare ma en aye i kare ma en aye.

{% hint style="info" %}

**[Purpur kacel ma en aye](configurations/purpur/world.md) ki 'shift-right-click-repairs-mending-points' obedo i gengo.**

{% endhint %}

#### `purpur.place.spawners`

- **Lok me iye**: `pek`

Kica me kwanyo kwede kwo gengo ma kwo i kare ma en aye.

{% hint style="info" %}

**[Purpur kwede iye](configurations/purpur/world.md) me `gameplay-mechanics > silk-touch` wacel pek i kwo tic.**

{% endhint %}

#### `purpur.portal.instant`

- **Lok me iye**: `pek`

Kica me kwanyo kwede kwo nedi Nether ma kwede kwo kwede i kwede.

#### `purpur.sign.color`

- **Lok me iye**: `pek`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting_codes#Color_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.sign.magic`

- **Lok me iye**: `pek`

표지판에 난독화 코드`(&o)`를 사용할 수 있도록 허용합니다.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.sign.style`

- **Lok me iye**: `pek`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Lok me iye**: `pek`

플레이어가 가위로 `상호 작용`하여 TNT 폭발을 막을 수 있도록 허용합니다.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**

{% endhint %}

### 제공 예정 권한

#### `plazma.bypass.ncr-require`

- **Lok me iye**: `pek`

플레이어가 [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) 모드가 설치되어 있지 않아도 접속할 수 있도록 허용합니다.

{% hint style="info" %}

**[Plazma 세계별 구성](configurations/plazma/world.md)에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**

{% endhint %}

***

[^1]: Operator.

[^2]: 예: `ender_dragon`
