---
description: .안요보아에 권한의 Plazma
---

# 🛡️ 권한

권한은 서버 내 플레이어가 상호 작용 할 수 있는 범위를 설정하는 간단한 보안 도구입니다.

권한을 제대로 활용하고 쉽게 수정하려면 [LuckPerms](https://luckperms.net) 등의 플러그인을 사용해야 합니다.

***

## understand the basic permission system <a href="#id-1" id="id-1"></a>

Minecraft provides basic management permission groups.

[Operators](#user-content-fn-1)[^1] can set permissions for command blocks and [server properties](configurations/property.md) can be modified.

0. **players**\
   the default permission group given to all players.
1. **mediator**\
   can ignore spawn protection.
2. **world administrator**\
   can use all commands and command blocks related to world management.\
   This is the default permission group applied to datapacks and command blocks.
3. **administrator**\
   can use all commands related to player management.
4. **super administrator**\
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

**[Purpur world configuration](configurations/purpur/world.md) only works if `(Entity) > ridable` is activated.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **default**: `none`

allows players to use special abilities of entities while mounted on them.

not all entities have special abilities. refer below for all available special abilities.

{% hint style="info" %}

**have a good idea for special abilities?**

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

**[Purpur world configuration](configurations/purpur/world.md) only works if `(Entity) > ridable` is activated.**

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

**this command has been discontinued.**

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

if [X-Ray blocking](../expert/xray.md) is enabled,
players with registered permissions will not obfuscate X-Ray blocking blocks.

this way, both sides can experience performance improvements.

> refer to the following page for X-Ray settings.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **default**: `none`

{% hint style="warning" %}

this permission will be changed to `plazma.bypass.watchdog` in 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **default**: `none`

allows the use of [color codes](https://minecraft.wiki/w/Formatting_codes#Color_codes) on anvils.

{% hint style="info" %}

**[Purpur world configuration](configurations/purpur/world.md) only works if `anvil > allow-colors` is activated.**

{% endhint %}

#### `purpur.anvil.format`

- **default**: `none`

allows the use of [formatting codes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) on anvils.

{% hint style="info" %}

**[Purpur world configuration](configurations/purpur/world.md) only works if `anvil > allow-colors` is activated.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **default**: `none`

allows the use of [MiniMessage tags](https://docs.advntr.dev/minimessage/format.html) on anvils.

{% hint style="info" %}

**[Purpur world configuration](configurations/purpur/world.md) only works if `anvil > allow-minimessages` is activated.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **default**: `none`

allows disabling `italic text` on anvils with the [`&r` formatting code](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**[Purpur world configuration](configurations/purpur/world.md) only works if `anvil > allow-colors` is activated.**

{% endhint %}

#### `purpur.book.color.sign`

- **default**: `none`

applies [formatting codes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) when players sign books.

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

**[Purpur world configuration](configurations/purpur/world.md) only works if `gameplay-mechanics > silk-touch` is activated.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **default**: `none`

changes the size of ender chests.

`(NumberString)` can be `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**[Purpur world configuration](configurations/purpur/world.md) only works if `ender_chest > six-rows` and `ender_chest > use-permissions-for-rows` are activated.**

{% endhint %}

#### `purpur.inventory_totem`

- **default**: `none`

sɹǝɥ ǝɥʇıɯǝ ǝɥʇ ǝpɹɐɯɹǝıp ǝɥʇ ʇɐɥʇ ɹǝʌoɔ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

\*\*[Purpur ɯǝlqɐɟ ɹǝɥʇɐɹ ɹǝɥʇɐɯ](configurations/purpur/world.md) ǝsɹǝɥʇɐɯ ɹǝʇɐɯǝsɐɥɔ ɥɐlɹǝsɐɯɹǝ ǝɥʇ ǝpɹɐɯɹǝıp ǝɥʇ ʇɐɥʇ

{% endhint %}

#### `ɯǝlqɐɟ.ɯıouSɹǝʌɹǝ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

#### `ɯǝlqɐɟ.ɯǝupıuɹ_ʇɹıɔ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ `ɯoouʞɹıƃo sɹɹǝ ʇɹɹo ıɹɐɯ`ɐɥɐ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

\*\*[Purpur ɯǝlqɐɟ ɹǝɥʇɐɹ ɹǝɥʇɐɯ](configurations/purpur/world.md) ǝsɹǝɥʇɐɯ ɹǝʇɐɯǝsɐɥɔ ɹıɯɯɐu-ʇıƃʎ-ɔɹıɐɹs-ɯǝɹɹɐɥs ɥɐlɹǝsɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% endhint %}

#### `ɯǝlqɐɟ.ǝɹɹoɯ.suǝɹɹɐ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ sɯoʞuǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

**[Purpur world configuration](configurations/purpur/world.md) only works if `gameplay-mechanics > silk-touch` is activated.**

{% endhint %}

#### `ɯǝlqɐɟ.ɯoɹʇɐl.ʇuıuɐı`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ ɯǝuǝɹ ɔɐʞǝ ɔɐɯoɹɯɯ ɥɐlɹǝsɐɯɹǝ ɥɐlɹǝ ɯǝɯʇoɹ ɯɐlɹo ɯǝɯʇoɹɹɐɯ

#### `ɯǝlqɐɟ.sııɯ.ɔoʇoɹ`

- **default**: `none`

sɹǝpızıɯɐu ǝsɹǝɥʇɐɹ [ɔɐl ɔoɔǝ](https://minecraft.wiki/w/Formatting_codes#Color_codes) ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

\*\*[Purpur ɯǝlqɐɟ ɹǝɥʇɐɹ ɹǝɥʇɐɯ](configurations/purpur/world.md) ǝsɹǝɥʇɐɯ ɹǝʇɐɯǝsɐɥɔ `ɔıƃɹı-˙ɔoɹlǝs` ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% endhint %}

#### `ɯǝlqɐɟ.sııɯ.ɔɯǝ`

- **default**: `none`

sɹǝpızıɯɐu ǝsɹǝɥʇɐɹ uıɐɯpouɯɐ ɔoɔı`(&o)` ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

\*\*[Purpur ɯǝlqɐɟ ɹǝɥʇɐɹ ɹǝɥʇɐɯ](configurations/purpur/world.md) ǝsɹǝɥʇɐɯ ɹǝʇɐɯǝsɐɥɔ `ɔıƃɹı-˙ɔoɹlǝs` ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% endhint %}

#### `ɯǝlqɐɟ.sııɯ.ʇsʇıl`

- **default**: `none`

sɹǝpızıɯɐu ǝsɹǝɥʇɐɹ [sʇɐuılɯıu ɔoɔı `(&o ǝsıɥ)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

\*\*[Purpur ɯǝlqɐɟ ɹǝɥʇɐɹ ɹǝɥʇɐɯ](configurations/purpur/world.md) ǝsɹǝɥʇɐɯ ɹǝʇɐɯǝsɐɥɔ `ɔıƃɹı-˙ɔoɹlǝs` ɯıouSǝɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% endhint %}

#### `ɯǝlqɐɟ.tnt.ǝsıɯɯ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ ɔɐıʍ ɹoɔ `˙ɔoɹlǝ ɔoɔı`ɐɥɐ ɥɐlɹǝsɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

\*\*[Purpur ɯǝlqɐɟ ɹǝɥʇɐɹ ɹǝɥʇɐɯ](configurations/purpur/world.md) ǝsɹǝɥʇɐɯ `ɯıouǝ-˙ɔoɹlǝ-ɔɐıuɐ`ʞɐ `0.0` ıɯɯɐı ɥɐlɹǝsɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% endhint %}

### uǝpɹoɥ ǝsǝuıɯ ɯıouSǝɹ

#### `ɯlɐzɯɐ.ʎɐpuos.ɯɔɹ-ǝɹɹǝɐɔ`

- **default**: `none`

sǝʇɹǝɯǝ ʇɐɥʇ [`oɔɥɐɔɹɯɯ`](https://modrinth.com/mod/no-chat-reports) ɯoɔıpıɹɐ ɐılɐıʇıɯǝ ıɥʇɐɹ ɹǝɥʇɐɹ ɹǝɥʇɐɯɹǝ ǝɥʇ ʇɐɥʇ

{% hint style="info" %}

\*\*[Plazma ɯǝlqɐɟ ɹǝɥʇɐɹ ɹǝɥʇɐɯ](configurations/plazma/world.md) ǝsɹǝɥʇɐɯ `oɔɥɐɔ-ɹǝǝǝɹ-ılɐǝɹɹǝɐ` ǝsɹǝɥʇɐɯ ɹǝʇɐɯǝsɐɥɔ

{% endhint %}

***

[^1]: Operator.

[^2]: ǝsǝɹɐ `uıɹǝp_ɔɹɐuıp`
