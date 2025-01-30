---
description: 了解Plazma的权限。
---

# 🛡️ 权限

权限是服务器内玩家可以互动的范围的简单安全工具。

要正确使用权限并轻松修改，请使用插件，如[LuckPerms](https://luckperms.net)。

***

## 理解基本权限系统 <a href="#id-1" id="id-1"></a>

Minecraft提供了基本的管理权限组。

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **玩家**\
   通常是赋予所有玩家的权限组。
2. **中介者**\
   可以忽略生成保护。
3. **世界管理员**\
   可以使用与世界管理相关的所有命令和命令方块。\
   是应用于数据包和命令方块的默认权限组。
4. **管理员**\
   可以使用与玩家管理相关的所有命令。
5. **总管理员**\
   可以使用包括服务器管理在内的所有命令。\
   是应用于控制台和管理员的默认权限组。

***

## 设置权限 <a href="#id-2" id="id-2"></a>

***

## 全部权限 <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **默认提供**: `无`

允许玩家`弯腰并互动`实体以骑乘实体。

骑乘实体后，可以使用`移动键`来控制实体的移动，使用`跳跃键`来跳跃或飞行。

`(Namespaced Key)`是实体的[命名空间ID](#user-content-fn-2)[^2]。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **默认提供**: `无`

允许玩家在骑乘实体时使用实体的特殊技能。

并非所有实体的特殊功能都可用。 请参考下面的所有可用特殊技能。

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

请在[Plazma Discord](https://plazmamc.org/discord)或[GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)上发布您的想法！
{% endhint %}

<details>

<summary>查看当前可用的特殊技能</summary>

- **`crepper`**\
  按下`跳跃键`会爆炸。\
  如果玩家拥有`allow.powered.creeper`权限，则可以按住`跳跃键`进行充能。
- **`dolphin`**\
  按下`跳跃键`会进行冲刺。
- **`phantom`**\
  按下`跳跃键`会发射火焰。
- **`wither`**\
  与其`互动`会发射凋零头。

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **默认提供**: `世界管理员`

允许使用[`/compass`命令](commands.md#compass)。

#### `bukkit.command.credits`

- **默认提供**: `世界管理员`

允许使用[`/credits (Player)`命令](commands.md#credits)。

在权限名后输入`.other`，可以允许其他玩家使用。

#### `bukkit.command.demo`

- **默认提供**: `世界管理员`

允许使用[`/demo (Player)`命令](commands.md#demo)。

在权限名后输入`.other`，可以允许其他玩家使用。

#### `bukkit.command.ping`

- **默认提供**: `世界管理员`

允许使用[`/ping (Player)`命令](commands.md#ping)。

在权限名后输入`.other`，可以允许其他玩家使用。

#### `bukkit.command.ram`

- **默认提供**: `世界管理员`

允许使用[`/ram`命令](commands.md#ram)。

#### `bukkit.command.rambar`

- **默认提供**: `世界管理员`

允许使用[`/rambar (Player)`命令](commands.md#rambar)。

在权限名后输入`.other`，可以允许其他玩家使用。

#### `bukkit.command.restart`

- **默认提供**: `世界管理员`

允许使用[`/restart`命令](commands.md#restart)。

#### `bukkit.command.tps`

- **默认提供**: `世界管理员`

允许使用[`/tps`命令](commands.md#tps)。

#### `bukkit.command.tpsbar`

- **默认提供**: `世界管理员`

允许使用[`/tpsbar (Player)`命令](commands.md#tpsbar)。

在权限名后输入`.other`，可以允许其他玩家使用。

#### `bukkit.command.timings`

- **默认提供**: `世界管理员`

允许使用[`/timings`命令](commands.md#timings)。

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

要了解类似功能的命令，请查看[Spark](https://spark.lucko.me/docs/Command-Usage)。
{% endhint %}

#### `bukkit.command.uptime`

- **默认提供**: `世界管理员`

允许使用[`/uptime`命令](commands.md#uptime)。

#### `minecraft.command.gamemode.(GameMode)`

- **默认提供**: `世界管理员`

允许使用`/gamemode (GameMode) (Player)`命令。

在权限名后输入`.other`，可以允许其他玩家使用。

#### `paper.antixray.bypass`

- **默认提供**: `无`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

这样双方都可以体验到性能的提升。

> 有关X射线设置的信息，请参考下面的页面。

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **默认提供**: `无`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **默认提供**: `无`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **默认提供**: `无`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **默认提供**: `无`

允许在铁砧上使用[MiniMessage标签](https://docs.advntr.dev/minimessage/format.html)。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **默认提供**: `无`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **默认提供**: `无`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **默认提供**: `无`

允许玩家免受空闲踢出的影响。

#### `purpur.debug.f3n`

- **默认提供**: `世界管理员`

允许玩家使用`F3 + N`键切换游戏模式。

如果没有相应游戏模式的权限，则不起作用。

#### `purpur.drop.spawners`

- **默认提供**: `无`

当使用配置中的物品挖掘刷怪笼时，会掉落刷怪笼。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **默认提供**: `无`

更改末影箱的大小。

可输入`one`、`two`、`three`、`four`、`five`、`six`到`(NumberString)`中。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **默认提供**: `无`

允许即使在库存中有不死图腾也起作用。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **默认提供**: `无`

允许玩家忽略连接限制。

#### `purpur.mending_shift_click`

- **默认提供**: `无`

允许玩家在`蹲下并互动`时修复手持物品。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **默认提供**: `无`

允许玩家放置刷怪笼。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **默认提供**: `无`

玩家使用下界传送门时立即传送。

#### `purpur.sign.color`

- **默认提供**: `无`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **默认提供**: `无`

允许在标志牌上使用混淆代码`(&o)`。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **默认提供**: `无`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **默认提供**: `无`

允许玩家通过`互动`使用剪刀阻止TNT爆炸。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### 预设权限

#### `plazma.bypass.ncr-require`

- **默认提供**: `无`

允许玩家即使未安装[`NoChatReports`](https://modrinth.com/mod/no-chat-reports)模组也可以连接。

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: 操作员。

[^2]: 例如：`ender_dragon`
