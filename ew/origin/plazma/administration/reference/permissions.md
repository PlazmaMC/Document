---
description: Check out the permissions of Plazma.
---

# 🛡️ Permissions

Permission is a simple security tool that sets the scope for players to interact within the server.

To properly utilize and easily modify permissions, you should use plugins such as [LuckPerms](https://luckperms.net).

***

## Understanding the basic permission system <a href="#id-1" id="id-1"></a>

Minecraft provides basic management permission groups.

You can set permissions for [operators](#user-content-fn-1)[^1] and command blocks, and modify them in [server properties](configurations/property.md).

0. **Player**\
   A permission group given to all players by default.
1. **Mediator**\
   Can ignore spawn protection.
2. **World Administrator**\
   Can use all commands and command blocks related to world management.\
   Default permission group applied to datapacks and command blocks.
3. **Administrator**\
   Can use all commands related to player management.
4. **Super Administrator**\
   Can use all commands including server management.\
   Default permission group applied to console and operators.

***

## Setting permissions <a href="#id-2" id="id-2"></a>

***

## Full permissions <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Default**: `None`

Allows players to `sneak and interact` with entities to mount them.

When mounted on an entity, players can control the entity's movement with the `movement keys` and jump or fly with the `jump key`.

`(Namespaced Key)` corresponds to the [Namespaced ID](#user-content-fn-2)[^2] of the entity.

{% hint style="info" %}

**Only works if `(Entity) > ridable` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Default**: `None`

Allows players to use special abilities of entities while riding them.

Not all entities have available special abilities. Refer below for a list of all available special abilities.

{% hint style="info" %}

**Have a great idea for a special ability?**

Post your ideas on [Plazma Discord](https://plazmamc.org/discord) or [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>View currently available special abilities</summary>

- **`crepper`**\
  Explodes when the `jump key` is pressed.\
  If players have the `allow.powered.creeper` permission, they can hold down the `jump key` to charge it.
- **`dolphin`**\
  Dashes when the `jump key` is pressed.
- **`phantom`**\
  Shoots flames when the `jump key` is pressed.
- **`wither`**\
  Fires wither skulls when `interacted with`.

</details>

{% hint style="info" %}

**Only works if `(Entity) > ridable` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Default**: `World Administrator`

Allows the use of the [`/compass` command](commands.md#compass).

#### `bukkit.command.credits`

- **Default**: `World Administrator`

Allows the use of the [`/credits (Player)` command](commands.md#credits).

Adding `.other` after the permission name allows it to be used on other players.

#### `bukkit.command.demo`

- **Default**: `World Administrator`

Allows the use of the [`/demo (Player)` command](commands.md#demo).

Adding `.other` after the permission name allows it to be used on other players.

#### `bukkit.command.ping`

- **Default**: `World Administrator`

Allows the use of the [`/ping (Player)` command](commands.md#ping).

Adding `.other` after the permission name allows it to be used on other players.

#### `bukkit.command.ram`

- **Default**: `World Administrator`

Allows the use of the [`/ram` command](commands.md#ram).

#### `bukkit.command.rambar`

- **Default**: `World Administrator`

Allows the use of the [`/rambar (Player)` command](commands.md#rambar).

Adding `.other` after the permission name allows it to be used on other players.

#### `bukkit.command.restart`

- **Default**: `World Administrator`

Allows the use of the [`/restart` command](commands.md#restart).

#### `bukkit.command.tps`

- **Default**: `World Administrator`

Allows the use of the [`/tps` command](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Default**: `World Administrator`

Allows the use of the [`/tpsbar (Player)` command](commands.md#tpsbar).

Adding `.other` after the permission name allows it to be used on other players.

#### `bukkit.command.timings`

- **Default**: `World Administrator`

Allows the use of the [`/timings` command](commands.md#timings).

{% hint style="warning" %}

**This command has been discontinued.**

Check [Spark](https://spark.lucko.me/docs/Command-Usage) for similar functionalities.

{% endhint %}

#### `bukkit.command.uptime`

- **Default**: `World Administrator`

Allows the use of the [`/uptime` command](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Default**: `World Administrator`

Allows the use of the `/gamemode (GameMode) (Player)` command.

Adding `.other` after the permission name allows it to be used on other players.

#### `paper.antixray.bypass`

- **Default**: `None`

When [X-Ray blocking](../expert/xray.md) is enabled,
players with registered permissions will not obfuscate X-Ray block readings.

This benefits both sides in terms of performance enhancement.

> Refer to the following page for X-Ray setup instructions.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Default**: `None`

{% hint style="warning" %}

This permission will be changed to `plazma.bypass.watchdog` in 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Default**: `None`

Allows the use of [color codes](https://minecraft.wiki/w/Formatting_codes#Color_codes) on anvils.

{% hint style="info" %}

**Only works if `anvil > allow-colors` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Default**: `None`

Allows the use of [styling codes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) on anvils.

{% hint style="info" %}

**Only works if `anvil > allow-colors` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Default**: `None`

Allows the use of [MiniMessage tags](https://docs.advntr.dev/minimessage/format.html) on anvils.

{% hint style="info" %}

**Only works if `anvil > allow-minimessages` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Default**: `None`

Allows disabling `italic text` on anvils using the [`&r` styling code](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**Only works if `anvil > allow-colors` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Default**: `None`

Applies [styling codes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) when players sign books.

#### `purpur.bypassIdleKick`

- **Default**: `None`

Excludes players from being kicked for being idle.

#### `purpur.debug.f3n`

- **Default**: `World Administrator`

Allows players to change game modes using the `F3 + N` key combination.

This only works if the player has permission for that game mode.

#### `purpur.drop.spawners`

- **Default**: `None`

Dropping a spawner block with the configured item will drop the spawner block.

{% hint style="info" %}

**Only works if `gameplay-mechanics > silk-touch` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Default**: `None`

Changes the size of ender chests.

Allowed inputs for `(NumberString)` are `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Only works if `ender_chest > six-rows` and `ender_chest > use-permissions-for-rows` are enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Default**: `None`

Allow Totem of Undying to function even when in inventory.

{% hint style="info" %}

**In the [Purpur world configuration](configurations/purpur/world.md), `totem-of-undying-works-in-inventory` must be enabled for it to function.**

{% endhint %}

#### `purpur.joinFullServer`

- **Default**: `None`

Allow players to bypass the connection limit.

#### `purpur.mending_shift_click`

- **Default**: `None`

Allow players to repair held items by `sneaking and interacting`.

{% hint style="info" %}

**In the [Purpur world configuration](configurations/purpur/world.md), `shift-right-click-repairs-mending-points` must be enabled for it to function.**

{% endhint %}

#### `purpur.place.spawners`

- **Default**: `None`

Allow players to place spawners.

{% hint style="info" %}

**Only works if `gameplay-mechanics > silk-touch` is enabled in [Purpur world configurations](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Default**: `None`

Enable players to instantly teleport when using Nether portals.

#### `purpur.sign.color`

- **Default**: `None`

Allow the use of [color codes](https://minecraft.wiki/w/Formatting_codes#Color_codes) on signs.

{% hint style="info" %}

**In the [Purpur world configuration](configurations/purpur/world.md), `sign > allow-colors` must be enabled for it to function.**

{% endhint %}

#### `purpur.sign.magic`

- **Default**: `None`

Allow the use of obfuscation code `(&o)` on signs.

{% hint style="info" %}

**In the [Purpur world configuration](configurations/purpur/world.md), `sign > allow-colors` must be enabled for it to function.**

{% endhint %}

#### `purpur.sign.style`

- **Default**: `None`

Allow the use of [formatting codes `(&o excluded)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) on signs.

{% hint style="info" %}

**In the [Purpur world configuration](configurations/purpur/world.md), `sign > allow-colors` must be enabled for it to function.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Default**: `None`

Allow players to prevent TNT explosions by `interacting` with shears.

{% hint style="info" %}

**In the [Purpur world configuration](configurations/purpur/world.md), `defuse-tnt-change` must be `0.0` or higher for it to function.**

{% endhint %}

### Planned Permissions

#### `plazma.bypass.ncr-require`

- **Default**: `None`

Allow players to connect even without the [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod installed.

{% hint style="info" %}

**In the [Plazma world configuration](configurations/plazma/world.md), `no-chat-reports > require-install` must be enabled for it to function.**

{% endhint %}

***

[^1]: Operator.

[^2]: Example: `ender_dragon`
