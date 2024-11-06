---
description: .안요보아에 권한의 Plazma
---

# 🛡️ 권한

권한은 서버 내 플레이어가 상호 작용 할 수 있는 범위를 설정하는 간단한 보안 도구입니다.

권한을 제대로 활용하고 쉽게 수정하려면 [LuckPerms](https://luckperms.net) 등의 플러그인을 사용해야 합니다.

***

## understand the basic permission system <a href="#id-1" id="id-1"></a>

Minecraft provides basic management permission groups.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **players**\
   the default permission group given to all players.
2. **mediator**\
   can ignore spawn protection.
3. **world administrator**\
   can use all commands and command blocks related to world management.\
   This is the default permission group applied to datapacks and command blocks.
4. **administrator**\
   can use all commands related to player management.
5. **super administrator**\
   can use all commands including server management.\
   This is the default permission group applied to the console and operators.

***

## set permissions <a href="#id-2" id="id-2"></a>

***

## full permissions <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **default**: `none`

allows players to `sneak and interact` with entities to mount them.

when mounted on an entity, players can control the entity's movement with the `movement keys` and jump or fly with the `jump key`.

`(Namespaced Key)` is the [Namespaced ID](#user-content-fn-2)[^2] of the entity.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **default**: `none`

allows players to use special abilities of entities while mounted on them.

not all entities have special abilities. refer below for all available special abilities.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

post your ideas on [Plazma Discord](https://plazmamc.org/discord) or [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>view currently available special abilities</summary>

- **`crepper`**\
  press the `jump key` to explode.\
  players with `allow.powered.creeper` permission can charge by holding down the `jump key`.
- **`dolphin`**\
  press the `jump key` to dash.
- **`phantom`**\
  press the `jump key` to shoot flames.
- **`wither`**\
  interact to shoot wither heads.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **default**: `world administrator`

allows the use of the [`/compass` command](commands.md#compass).

#### `bukkit.command.credits`

- **default**: `world administrator`

allows the use of the [`/credits (Player)` command](commands.md#credits).

adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.demo`

- **default**: `world administrator`

allows the use of the [`/demo (Player)` command](commands.md#demo).

adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.ping`

- **default**: `world administrator`

allows the use of the [`/ping (Player)` command](commands.md#ping).

adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.ram`

- **default**: `world administrator`

allows the use of the [`/ram` command](commands.md#ram).

#### `bukkit.command.rambar`

- **default**: `world administrator`

allows the use of the [`/rambar (Player)` command](commands.md#rambar).

adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.restart`

- **default**: `world administrator`

allows the use of the [`/restart` command](commands.md#restart).

#### `bukkit.command.tps`

- **default**: `world administrator`

allows the use of the [`/tps` command](commands.md#tps).

#### `bukkit.command.tpsbar`

- **default**: `world administrator`

allows the use of the [`/tpsbar (Player)` command](commands.md#tpsbar).

adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.timings`

- **default**: `world administrator`

allows the use of the [`/timings` command](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

check [Spark](https://spark.lucko.me/docs/Command-Usage) for similar functionality.
{% endhint %}

#### `bukkit.command.uptime`

- **default**: `world administrator`

allows the use of the [`/uptime` command](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **default**: `world administrator`

allows the use of the `/gamemode (GameMode) (Player)` command.

adding `.other` after the permission name allows it to be used by other players.

#### `paper.antixray.bypass`

- **default**: `none`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

this way, both sides can experience performance improvements.

> refer to the following page for X-Ray settings.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **default**: `none`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **default**: `none`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **default**: `none`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **default**: `none`

allows the use of [MiniMessage tags](https://docs.advntr.dev/minimessage/format.html) on anvils.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **default**: `none`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **default**: `none`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **default**: `none`

excludes players from being kicked for being idle.

#### `purpur.debug.f3n`

- **default**: `world administrator`

allows players to change game modes with `F3 + N` key combination.

does not work without permission for that game mode.

#### `purpur.drop.spawners`

- **default**: `none`

mining spawner blocks with configured items drops the spawner block.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **default**: `none`

changes the size of ender chests.

`(NumberString)` can be `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **default**: `none`

sɹǝɥ ǝɥʇıɯǝ ǝɥʇ ǝpɹɐɯɹǝıp ǝɥʇ ʇɐɥʇ ɹǝʌoɔ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `ɯǝlqɐɟ.ɯıouSɹǝʌɹǝ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

#### `ɯǝlqɐɟ.ɯǝupıuɹ_ʇɹıɔ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ `ɯoouʞɹıƃo sɹɹǝ ʇɹɹo ıɹɐɯ`ɐɥɐ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `ɯǝlqɐɟ.ǝɹɹoɯ.suǝɹɹɐ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ sɯoʞuǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `ɯǝlqɐɟ.ɯoɹʇɐl.ʇuıuɐı`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ ɯǝuǝɹ ɔɐʞǝ ɔɐɯoɹɯɯ ɥɐlɹǝsɐɯɹǝ ɥɐlɹǝ ɯǝɯʇoɹ ɯɐlɹo ɯǝɯʇoɹɹɐɯ

#### `ɯǝlqɐɟ.sııɯ.ɔoʇoɹ`

- **default**: `none`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `ɯǝlqɐɟ.sııɯ.ɔɯǝ`

- **default**: `none`

sɹǝpızıɯɐu ǝsɹǝɥʇɐɹ uıɐɯpouɯɐ ɔoɔı`(&o)` ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `ɯǝlqɐɟ.sııɯ.ʇsʇıl`

- **default**: `none`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `ɯǝlqɐɟ.tnt.ǝsıɯɯ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ ɔɐıʍ ɹoɔ `˙ɔoɹlǝ ɔoɔı`ɐɥɐ ɥɐlɹǝsɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### uǝpɹoɥ ǝsǝuıɯ ɯıouSǝɹ

#### `ɯlɐzɯɐ.ʎɐpuos.ɯɔɹ-ǝɹɹǝɐɔ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ [`oɔɥɐɔɹɯɯ`](https://modrinth.com/mod/no-chat-reports) ɯoɔıpıɹɐ ɐılɐıʇıɯǝ ıɥʇɐɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: ǝsǝɹɐ `uıɹǝp_ɔɹɐuıp`
