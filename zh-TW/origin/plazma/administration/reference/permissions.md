---
description: 了解Plazma的權限。
---

# 🛡️ 權限

權限是一種簡單的安全工具，用於設定伺服器內玩家可以互動的範圍。

為了正確使用權限並輕鬆修改，應使用像 [LuckPerms](https://luckperms.net) 這樣的插件。

***

## 了解基本權限系統 <a href="#id-1" id="id-1"></a>

在Minecraft中，提供了基本管理權限組。

可以設置[管理員](#user-content-fn-1)[^1]和命令方塊的權限，並在[伺服器屬性](configurations/property.md)中進行修改。

0. **玩家**\
   通常是給予所有玩家的權限組。
1. **調停者**\
   可以忽略重生保護。
2. **世界管理員**\
   可以使用與世界管理相關的所有指令和命令方塊。\
   這是應用於資料包和命令方塊的預設權限組。
3. **管理員**\
   可以使用與玩家管理相關的所有指令。
4. **總管理員**\
   可以使用包括伺服器管理在內的所有指令。\
   這是控制台和管理員的預設權限組。

***

## 設置權限 <a href="#id-2" id="id-2"></a>

***

## 完整權限 <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **預設值**: `無`

允許玩家蹲下並與實體互動以騎乘該實體。

騎乘實體後，可以使用`移動鍵`來控制實體移動，使用`跳躍鍵`來跳躍或飛行。

`(Namespaced Key)`是實體的[命名空間 ID](#user-content-fn-2)[^2]。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`(Entity) > ridable`時才有效。**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **預設值**: `無`

當玩家騎乘實體時，允許使用實體的特殊技能。

並非所有實體的特殊功能都可以使用。 請參閱下方可用的所有特殊技能。

{% hint style="info" %}

**有關特殊技能的好主意嗎？**

請在[Plazma Discord](https://plazmamc.org/discord)或[GitHub討論](https://github.com/PlazmaMC/PlazmaBukkit/discussions)上發布您的想法！

{% endhint %}

<details>

<summary>查看當前可用的特殊技能</summary>

- **`crepper`**\
  按下`跳躍鍵`會爆炸。\
  如果玩家擁有`allow.powered.creeper`權限，則可以長按`跳躍鍵`來充能。
- **`dolphin`**\
  按下`跳躍鍵`會衝刺。
- **`phantom`**\
  按下`跳躍鍵`會發射火焰。
- **`wither`**\
  與實體`互動`會發射凋零頭。

</details>

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`(Entity) > ridable`時才有效。**

{% endhint %}

#### `bukkit.command.compass`

- **預設值**: `世界管理員`

允許使用[`/compass`指令](commands.md#compass)。

#### `bukkit.command.credits`

- **預設值**: `世界管理員`

允許使用[`/credits (Player)`指令](commands.md#credits)。

在權限名後加入`.other`，可以允許其他玩家使用。

#### `bukkit.command.demo`

- **預設值**: `世界管理員`

允許使用[`/demo (Player)`指令](commands.md#demo)。

在權限名後加入`.other`，可以允許其他玩家使用。

#### `bukkit.command.ping`

- **預設值**: `世界管理員`

允許使用[`/ping (Player)`指令](commands.md#ping)。

在權限名後加入`.other`，可以允許其他玩家使用。

#### `bukkit.command.ram`

- **預設值**: `世界管理員`

允許使用[`/ram`指令](commands.md#ram)。

#### `bukkit.command.rambar`

- **預設值**: `世界管理員`

允許使用[`/rambar (Player)`指令](commands.md#rambar)。

在權限名後加入`.other`，可以允許其他玩家使用。

#### `bukkit.command.restart`

- **預設值**: `世界管理員`

允許使用[`/restart`指令](commands.md#restart)。

#### `bukkit.command.tps`

- **預設值**: `世界管理員`

允許使用[`/tps`指令](commands.md#tps)。

#### `bukkit.command.tpsbar`

- **預設值**: `世界管理員`

允許使用[`/tpsbar (Player)`指令](commands.md#tpsbar)。

在權限名後加入`.other`，可以允許其他玩家使用。

#### `bukkit.command.timings`

- **預設值**: `世界管理員`

允許使用[`/timings`指令](commands.md#timings)。

{% hint style="warning" %}

**該指令已停用。**

要了解類似功能的指令，請查看[Spark](https://spark.lucko.me/docs/Command-Usage)。

{% endhint %}

#### `bukkit.command.uptime`

- **預設值**: `世界管理員`

允許使用[`/uptime`指令](commands.md#uptime)。

#### `minecraft.command.gamemode.(GameMode)`

- **預設值**: `世界管理員`

允許使用`/gamemode (GameMode) (Player)`指令。

在權限名後加入`.other`，可以允許其他玩家使用。

#### `paper.antixray.bypass`

- **預設值**: `無`

當[X射線阻擋](../expert/xray.md)功能啟用時，
擁有權限的玩家將不會對X射線阻擋方塊進行混淆。

這樣雙方都可以獲得性能提升。

> 要了解X射線設置方法，請參閱下方頁面。

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **預設值**: `無`

{% hint style="warning" %}

該權限將在1.20.5中更改為`plazma.bypass.watchdog`。

{% endhint %}

#### `purpur.anvil.color`

- **預設值**: `無`

允許在鐵砧上使用[顏色代碼](https://minecraft.wiki/w/Formatting_codes#Color_codes)。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`anvil > allow-colors`時才有效。**

{% endhint %}

#### `purpur.anvil.format`

- **預設值**: `無`

允許在鐵砧上使用[樣式代碼](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`anvil > allow-colors`時才有效。**

{% endhint %}

#### `purpur.anvil.minimessage`

- **預設值**: `無`

允許在鐵砧上使用[MiniMessage標籤](https://docs.advntr.dev/minimessage/format.html)。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`anvil > allow-minimessages`時才有效。**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **預設值**: `無`

允許使用[`&r`樣式代碼](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)來取消`斜體`。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`anvil > allow-colors`時才有效。**

{% endhint %}

#### `purpur.book.color.sign`

- **預設值**: `無`

當玩家簽署書時應用[樣式代碼](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)。

#### `purpur.bypassIdleKick`

- **預設值**: `無`

排除玩家不被視為閒置被踢出的對象。

#### `purpur.debug.f3n`

- **預設值**: `世界管理員`

允許玩家使用`F3 + N`鍵來更改遊戲模式。

如果沒有相應的遊戲模式權限，則將無法運作。

#### `purpur.drop.spawners`

- **預設值**: `無`

挖掘配置中設置的物品時，將掉落創造蛋。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`gameplay-mechanics > silk-touch`時才有效。**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **預設值**: `無`

更改終界箱的大小。

可以輸入`one`、`two`、`three`、`four`、`five`、`six`到`(NumberString)`。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`ender_chest > six-rows`和`ender_chest > use-permissions-for-rows`時才有效。**

{% endhint %}

#### `purpur.inventory_totem`

- **預設值**: `無`

即使擁有不死圖騰，也允許其正常運作。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`totem-of-undying-works-in-inventory`時才有效。**

{% endhint %}

#### `purpur.joinFullServer`

- **預設值**: `無`

允許玩家忽略連接人數限制。

#### `purpur.mending_shift_click`

- **預設值**: `無`

允許玩家進行`下蹲互動`以修復手持物品。

{% hint style="info" %}

**在[Purpur世界配置](configurations/purpur/world.md)中啟用`shift-right-click-repairs-mending-points`才能正常運作。**

{% endhint %}

#### `purpur.place.spawners`

- **預設值**: `無`

允許玩家放置生成器。

{% hint style="info" %}

**僅在[Purpur世界配置](configurations/purpur/world.md)中啟用了`gameplay-mechanics > silk-touch`時才有效。**

{% endhint %}

#### `purpur.portal.instant`

- **預設值**: `無`

當玩家使用下界傳送門時立即傳送。

#### `purpur.sign.color`

- **預設值**: `無`

표지판上可以使用[顏色代碼](https://minecraft.wiki/w/Formatting_codes#Color_codes)。

{% hint style="info" %}

**在[Purpur 世界配置](configurations/purpur/world.md)中啟用`sign > allow-colors`才能正常運作。**

{% endhint %}

#### `purpur.sign.magic`

- **預設值**: `無`

允許在標誌上使用難讀碼`(&o)`。

{% hint style="info" %}

**在[Purpur 世界配置](configurations/purpur/world.md)中啟用`sign > allow-colors`才能正常運作。**

{% endhint %}

#### `purpur.sign.style`

- **預設值**: `無`

允許在標誌上使用[格式代碼 `(&o 除外)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)。

{% hint style="info" %}

**在[Purpur 世界配置](configurations/purpur/world.md)中啟用`sign > allow-colors`才能正常運作。**

{% endhint %}

#### `purpur.tnt.defuse`

- **預設值**: `無`

允許玩家使用剪刀進行`互動`以阻止TNT爆炸。

{% hint style="info" %}

**[Purpur 世界配置](configurations/purpur/world.md)中`defuse-tnt-change`必須大於等於`0.0`才能正常運作。**

{% endhint %}

### 預定權限

#### `plazma.bypass.ncr-require`

- **預設值**: `無`

允許玩家即使未安裝[`NoChatReports`](https://modrinth.com/mod/no-chat-reports)模組也可以登入。

{% hint style="info" %}

**[Plazma 世界配置](configurations/plazma/world.md)必須啟用`no-chat-reports > require-install`才能正常運作。**

{% endhint %}

***

[^1]: 操作者。

[^2]: 例如：`ender_dragon`
