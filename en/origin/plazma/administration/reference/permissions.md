---
description: Check the permissions of Plazma.
---

# 🛡️ Permission

Permissions are a simple security tool that sets the scope in which players on the server can interact with each other.

To properly utilize and easily modify permissions, you should use plugins like [LuckPerms](https://luckperms.net).

***

## Understanding the default permission system <a href="#id-1" id="id-1"></a>

In Minecraft, basic management permission groups are provided.

You can set permissions for [operators](#user-content-fn-1)[^1] and command blocks, and modify them in [server properties](configurations/property.md).

0. **Player**\
   This is the permission group typically given to all players.
1. **Mediator**\
   Can bypass spawn protection.
2. **World Administrator**\
   Can use all commands and command blocks related to world management.\
   This is the permission group applied by default to datapacks and command blocks.
3. **Administrator**\
   Can use all commands related to player management.
4. **Super Administrator**\
   Can use all commands including server management.\
   This is the permission group applied by default to the console and operators.

***

## Setting Permissions <a href="#id-2" id="id-2"></a>

***

## Full Permissions <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Default**: `none`

Allows players to mount entities by `crouching and interacting` with them.

When mounted on an entity, players can control the entity's movement with the `movement keys` and jump or fly with the `jump key`.

The [Namespaced ID](#user-content-fn-2)[^2] of the entity is entered in `(Namespaced Key)`.

{% hint style="info" %}

**Only works if `(Entity) > ridable` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Default**: `none`

Allows players to use special abilities of entities while mounted on them.

Not all entities have available special abilities. Refer below for a list of all available special abilities.

{% hint style="info" %}

**Have a great idea for a special ability?**

Post your ideas on [Plazma Discord](https://plazmamc.org/discord) or [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>View currently available special abilities</summary>

- **`crepper`**\
  Explodes when the `jump key` is pressed.\
  If the player has the `allow.powered.creeper` permission, they can hold down the `jump key` to charge it.
- **`dolphin`**\
  Dashes when the `jump key` is pressed.
- **`phantom`**\
  Shoots fire when the `jump key` is pressed.
- **`wither`**\
  Fires wither heads when `interacted with`.

</details>

{% hint style="info" %}

**Only works if `(Entity) > ridable` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Default**: `World Administrator`

Allows the use of the [`/compass` command](commands.md#compass).

#### `bukkit.command.credits`

- **Default**: `World Administrator`

Allows the use of the [`/credits (Player)` command](commands.md#credits).

Adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.demo`

- **Default**: `World Administrator`

Allows the use of the [`/demo (Player)` command](commands.md#demo).

Adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.ping`

- **Default**: `World Administrator`

Allows the use of the [`/ping (Player)` command](commands.md#ping).

Adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.ram`

- **Default**: `World Administrator`

Allows the use of the [`/ram` command](commands.md#ram).

#### `bukkit.command.rambar`

- **Default**: `World Administrator`

Allows the use of the [`/rambar (Player)` command](commands.md#rambar).

Adding `.other` after the permission name allows it to be used by other players.

#### `bukkit.command.restart`

- **Default**: `World Administrator`

Allows the use of the [`/restart` command](commands.md#restart).

#### `bukkit.command.tps`

- **Default**: `World Administrator`

Allows the use of the [`/tps` command](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Default**: `World Administrator`

Allows the use of the [`/tpsbar (Player)` command](commands.md#tpsbar).

Adding `.other` after the permission name allows it to be used by other players.

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

Adding `.other` after the permission name allows it to be used by other players.

#### `paper.antixray.bypass`

- **Default**: `none`

If [X-Ray blocking](../expert/xray.md) is enabled,
players with the registered permission will not obfuscate blocks for X-Ray blocking.

This improves performance for both sides.

> Refer to the page below for information on X-Ray configuration.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Default**: `none`

{% hint style="warning" %}

This permission will be changed to `plazma.bypass.watchdog` in 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Default**: `none`

Allows the use of color codes on anvils.

{% hint style="info" %}

**Only works if `anvil > allow-colors` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Default**: `none`

Allows the use of styling codes on anvils.

{% hint style="info" %}

**Only works if `anvil > allow-colors` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Default**: `none`

Allows the use of MiniMessage tags on anvils.

{% hint style="info" %}

**Only works if `anvil > allow-minimessages` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Default**: `none`

Allows disabling `italicize text` with the `&r` styling code on anvils.

{% hint style="info" %}

**Only works if `anvil > allow-colors` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Default**: `none`

Applies styling codes when players sign books.

#### `purpur.bypassIdleKick`

- **Default**: `none`

Excludes players from being kicked for idle status.

#### `purpur.debug.f3n`

- **Default**: `World Administrator`

Allows players to change game modes with the `F3 + N` key combination.

This only works if the player has permission for that game mode.

#### `purpur.drop.spawners`

- **Default**: `none`

Drops spawner blocks when mining them with the configured item.

{% hint style="info" %}

**Only works if `gameplay-mechanics > silk-touch` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Default**: `none`

Changes the size of ender chests.

`(NumberString)` can be `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Only works if `ender_chest > six-rows` and `ender_chest > use-permissions-for-rows` are enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Default**: `none`

Allows the totem of undying to function even when in the inventory.

{% hint style="info" %}

**Only works if `totem-of-undying-works-in-inventory` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Default**: `none`

Allows the player to ignore the connection limit.

#### `purpur.mending_shift_click`

- **Default**: `none`

Allows the player to repair the item they are holding by `sneak-right-clicking`.

{% hint style="info" %}

**You must enable `shift-right-click-repairs-mending-points` in the [Purpur world configurations](configurations/purpur/world.md) for it to work.**

{% endhint %}

#### `purpur.place.spawners`

- **Default**: `none`

Allows the player to place spawners.

{% hint style="info" %}

**Only works if `gameplay-mechanics > silk-touch` is enabled in [Purpur world settings](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Default**: `none`

Allows the player to instantly teleport when using the Nether portal.

#### `purpur.sign.color`

- **Default**: `none`

Allow the use of [color codes](https://minecraft.wiki/w/Formatting_codes#Color_codes) on signs.

{% hint style="info" %}

**In the [Purpur world configurations](configurations/purpur/world.md), `sign > allow-colors` must be enabled for it to work.**

{% endhint %}

#### `purpur.sign.magic`

- **Default**: `none`

Allow the use of obfuscation code `(&o)` on signs.

{% hint style="info" %}

**In the [Purpur world configurations](configurations/purpur/world.md), `sign > allow-colors` must be enabled for it to work.**

{% endhint %}

#### `purpur.sign.style`

- **Default**: `none`

Allow the use of [styling code `(&o excluded)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) on signs.

{% hint style="info" %}

**In the [Purpur world configurations](configurations/purpur/world.md), `sign > allow-colors` must be enabled for it to work.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Default**: `none`

Allow players to `interact` with shears to prevent TNT explosions.

{% hint style="info" %}

**The `defuse-tnt-change` in [Purpur world configurations](configurations/purpur/world.md) must be at least `0.0` to function.**

{% endhint %}

### Planned permissions

#### `plazma.bypass.ncr-require`

- **Default**: `none`

Allow players to connect even if the [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod is not installed.

{% hint style="info" %}

**Enable `no-chat-reports > require-install` in [Plazma world configurations](configurations/plazma/world.md) for it to function.**

{% endhint %}

***

[^1]: Operator.

[^2]: Example: `ender_dragon`
