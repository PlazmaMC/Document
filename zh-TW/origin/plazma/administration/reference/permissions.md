---
description: 了解Plazma的權限。
---

# 🛡️ 權限

權限是一種簡單的安全工具，用於設定伺服器內玩家可以互動的範圍。

為了正確使用權限並輕鬆修改，應使用像 [LuckPerms](https://luckperms.net) 這樣的插件。

***

## 了解基本權限系統 <a href="#id-1" id="id-1"></a>

在Minecraft中，提供了基本管理權限組。

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **玩家**\
   通常是給予所有玩家的權限組。
2. **調停者**\
   可以忽略重生保護。
3. **世界管理員**\
   可以使用與世界管理相關的所有指令和命令方塊。\
   這是應用於資料包和命令方塊的預設權限組。
4. **管理員**\
   可以使用與玩家管理相關的所有指令。
5. **總管理員**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **預設值**: `無`

當玩家騎乘實體時，允許使用實體的特殊技能。

並非所有實體的特殊功能都可以使用。 請參閱下方可用的所有特殊技能。

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

這樣雙方都可以獲得性能提升。

> 要了解X射線設置方法，請參閱下方頁面。

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **預設值**: `無`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **預設值**: `無`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **預設值**: `無`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **預設值**: `無`

允許在鐵砧上使用[MiniMessage標籤](https://docs.advntr.dev/minimessage/format.html)。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **預設值**: `無`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **預設值**: `無`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **預設值**: `無`

更改終界箱的大小。

可以輸入`one`、`two`、`three`、`four`、`five`、`six`到`(NumberString)`。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **預設值**: `無`

即使擁有不死圖騰，也允許其正常運作。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **預設值**: `無`

允許玩家忽略連接人數限制。

#### `purpur.mending_shift_click`

- **預設值**: `無`

允許玩家進行`下蹲互動`以修復手持物品。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **預設值**: `無`

允許玩家放置生成器。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **預設值**: `無`

當玩家使用下界傳送門時立即傳送。

#### `purpur.sign.color`

- **預設值**: `無`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **預設值**: `無`

允許在標誌上使用難讀碼`(&o)`。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **預設值**: `無`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **預設值**: `無`

允許玩家使用剪刀進行`互動`以阻止TNT爆炸。

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### 預定權限

#### `plazma.bypass.ncr-require`

- **預設值**: `無`

允許玩家即使未安裝[`NoChatReports`](https://modrinth.com/mod/no-chat-reports)模組也可以登入。

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: 操作者。

[^2]: 例如：`ender_dragon`
