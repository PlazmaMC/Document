---
description: Learn about the authority of Plazma.
---

# 🛡️ Authority

Authority be a simple security tool on the server that sets the scope where players can interact with each other.

To properly utilize and easily modify authority, ye must use plugins like [LuckPerms](https://luckperms.net).

***

## Understanding the basic authority system <a href="#id-1" id="id-1"></a>

In Minecraft, basic management authority groups be provided.

[Operator](#user-content-fn-1)[^1] and command block permissions can be set, and modified in [server properties](configurations/property.md).

0. **Player**\
   Generally be the authority group given to all players.
1. **Mediator**\
   Can ignore spawn protection.
2. **World Administrator**\
   Can use all commands and command blocks related to world management.\
   Be the default authority group applied to datapacks and command blocks.
3. **Administrator**\
   Can use all commands related to player management.
4. **Super Administrator**\
   Can use all commands including server management.\
   Be the default authority group applied to console and operators.

***

## Setting authority <a href="#id-2" id="id-2"></a>

***

## All authority <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Default**: `None`

Allows players to mount entities by crouching and interacting with the entity.

When mounted on an entity, players can control the entity's movement with the movement keys and jump or fly with the jump key.

The [Namespaced ID](#user-content-fn-2)[^2] of the entity be entered in `(Namespaced Key)`.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `(Entity) > ridable` be enabled.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Default**: `None`

Allows players to use special abilities of entities while mounted on them.

Not all entities have accessible special abilities. Refer below for a list of all available special abilities.

{% hint style="info" %}

**Got a grand idea for a special ability?**

Post yer ideas on [Plazma Discord](https://plazmamc.org/discord) or [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>View currently available special abilities</summary>

- **`crepper`**\
  Explodes when the jump key be pressed.\
  If a player has the `allow.powered.creeper` authority, they can hold the jump key to charge.
- **`dolphin`**\
  Dashes when the jump key be pressed.
- **`phantom`**\
  Fires flames when the jump key be pressed.
- **`wither`**\
  Fires wither skulls when interacted with.

</details>

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `(Entity) > ridable` be enabled.**

{% endhint %}

#### `bukkit.command.compass`

- **Default**: `World Administrator`

Allows the use of the [`/compass` command](commands.md#compass).

#### `bukkit.command.credits`

- **Default**: `World Administrator`

Allows the use of the [`/credits (Player)` command](commands.md#credits).

By adding `.other` after the authority name, allows it to be used on other players.

#### `bukkit.command.demo`

- **Default**: `World Administrator`

Allows the use of the [`/demo (Player)` command](commands.md#demo).

By adding `.other` after the authority name, allows it to be used on other players.

#### `bukkit.command.ping`

- **Default**: `World Administrator`

Allows the use of the [`/ping (Player)` command](commands.md#ping).

By adding `.other` after the authority name, allows it to be used on other players.

#### `bukkit.command.ram`

- **Default**: `World Administrator`

Allows the use of the [`/ram` command](commands.md#ram).

#### `bukkit.command.rambar`

- **Default**: `World Administrator`

Allows the use of the [`/rambar (Player)` command](commands.md#rambar).

By adding `.other` after the authority name, allows it to be used on other players.

#### `bukkit.command.restart`

- **Default**: `World Administrator`

Allows the use of the [`/restart` command](commands.md#restart).

#### `bukkit.command.tps`

- **Default**: `World Administrator`

Allows the use of the [`/tps` command](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Default**: `World Administrator`

Allows the use of the [`/tpsbar (Player)` command](commands.md#tpsbar).

By adding `.other` after the authority name, allows it to be used on other players.

#### `bukkit.command.timings`

- **Default**: `World Administrator`

Allows the use of the [`/timings` command](commands.md#timings).

{% hint style="warning" %}

**This command has been discontinued.**

Check [Spark](https://spark.lucko.me/docs/Command-Usage) for similar commands.

{% endhint %}

#### `bukkit.command.uptime`

- **Default**: `World Administrator`

Allows the use of the [`/uptime` command](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Default**: `World Administrator`

Allows the use of the `/gamemode (GameMode) (Player)` command.

By adding `.other` after the authority name, allows it to be used on other players.

#### `paper.antixray.bypass`

- **Default**: `None`

If [X-Ray blocking](../expert/xray.md) be active, players with this authority won't undergo block obfuscation for X-Ray prevention.

This benefits both sides by enhancing performance.

> Refer to the page below to learn how to configure X-Ray settings.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Default**: `None`

{% hint style="warning" %}

This authority will be changed to `plazma.bypass.watchdog` in 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Default**: `None`

Allows the use of color codes on anvils.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `anvil > allow-colors` be enabled.**

{% endhint %}

#### `purpur.anvil.format`

- **Default**: `None`

Allows the use of styling codes on anvils.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `anvil > allow-colors` be enabled.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Default**: `None`

Allows the use of MiniMessage tags on anvils.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `anvil > allow-minimessages` be enabled.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Default**: `None`

Allows disabling `italicization` with the `&r` styling code on anvils.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `anvil > allow-colors` be enabled.**

{% endhint %}

#### `purpur.book.color.sign`

- **Default**: `None`

Applies styling codes when players sign books.

#### `purpur.bypassIdleKick`

- **Default**: `None`

Excludes players from being kicked for idle status.

#### `purpur.debug.f3n`

- **Default**: `World Administrator`

Allows players to change game modes with `F3 + N` key combination.

This only functions if the player has authority for that game mode.

#### `purpur.drop.spawners`

- **Default**: `None`

Dropping a spawner block with the configured item will drop the spawner block.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `gameplay-mechanics > silk-touch` be enabled.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Default**: `None`

Changes the size of ender chests.

`(NumberString)` can be `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `ender_chest > six-rows` and `ender_chest > use-permissions-for-rows` be enabled.**

{% endhint %}

#### `purpur.inventory_totem`

- **Default**: `None`

Allows totems of undying to function even when in the inventory.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `totem-of-undying-works-in-inventory` be enabled.**

{% endhint %}

#### `purpur.joinFullServer`

- **Default**: `None`

Allow the player to ignore the connection limit.

#### `purpur.mending_shift_click`

- **Default**: `None`

Allow the player to mend the item they are holding by `crouching and interacting`.

{% hint style="info" %}

**[Activate `shift-right-click-repairs-mending-points` in [Purpur World Configurations](configurations/purpur/world.md) for it to work.**

{% endhint %}

#### `purpur.place.spawners`

- **Default**: `None`

Allow the player to install spawners.

{% hint style="info" %}

**[Purpur World Configuration](configurations/purpur/world.md) only functions if `gameplay-mechanics > silk-touch` be enabled.**

{% endhint %}

#### `purpur.portal.instant`

- **Default**: `None`

Allow the player to teleport instantly when using the Nether portal.

#### `purpur.sign.color`

- **Default**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting_codes#Color_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.sign.magic`

- **Default**: `None`

Allow the use of obfuscation code `(&o)` on signs.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.sign.style`

- **Default**: `None`

Allow the use of [styling code `(&o excluded)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) on signs.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Default**: `None`

Allow players to `interact` with TNT using shears to prevent explosion.

{% hint style="info" %}

**The `defuse-tnt-change` in [Purpur world configuration](configurations/purpur/world.md) must be `0.0` or higher to function.**

{% endhint %}

### Planned permissions

#### `plazma.bypass.ncr-require`

- **Default**: `None`

Allow players to connect even if [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod is not installed.

{% hint style="info" %}

**To function, enable `no-chat-reports > require-install` in [Plazma world configuration](configurations/plazma/world.md).**

{% endhint %}

***

[^1]: Sailor.

[^2]: Example: `ender_dragon`
