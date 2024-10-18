---
description: Plazmaの権限について調べてください。
---

# 🛡️ 権限

권한은 서버 내 플레이어가 상호 작용 할 수 있는 범위를 설정하는 간단한 보안 도구입니다.

권한을 제대로 활용하고 쉽게 수정하려면 [LuckPerms](https://luckperms.net) 등의 플러그인을 사용해야 합니다.

***

## 기본 권한 체계 이해하기 <a href="#id-1" id="id-1"></a>

Minecraft에서는 기본적인 관리 권한 그룹을 제공하고 있습니다.

[운영자](#user-content-fn-1)[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

0. **プレイヤー**\
   一般的にすべてのプレイヤーに与えられる権限グループです。
1. **調停者**\
   スポーン保護を無視することができます。
2. **ワールド管理者**\
   ワールド管理に関連するすべてのコマンドとコマンドブロックを使用できます。\
   データパックおよびコマンドブロックにデフォルトで適用される権限グループです。
3. **管理者**\
   プレイヤー管理に関連するすべてのコマンドを使用できます。
4. **総管理者**\
   サーバー管理を含むすべてのコマンドを使用できます。\
   コンソールおよび管理者にデフォルトで適用される権限グループです。

***

## 권한 설정하기 <a href="#id-2" id="id-2"></a>

***

## 全体の権限 <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **デフォルト**: `なし`

プレイヤーがエンティティに`しゃがんで相互作用`してエンティティに乗ることを許可します。

エンティティに乗ると、`移動キー`でエンティティの移動を操作でき、`ジャンプキー`でジャンプしたり飛べます。

`(Namespaced Key)`にはエンティティの[Namespaced ID](#user-content-fn-2)[^2]が入力されます。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`(Entity) > ridable`を有効にした場合のみ動作します。**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **デフォルト**: `なし`

プレイヤーがエンティティに乗っているとき、エンティティの特殊技能を使用できるようにします。

すべてのエンティティの特殊機能が利用可能というわけではありません。 利用可能な全ての特殊技術については以下を参照してください。

{% hint style="info" %}

**特殊技術に関する良いアイデアはありますか？**

[Plazma Discord](https://plazmamc.org/discord)または[GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)にアイデアを投稿してください！

{% endhint %}

<details>

<summary>現在利用可能な特殊技術を見る</summary>

- **`crepper`**\
  `ジャンプキー`を押すと爆発します。\
  プレイヤーが`allow.powered.creeper`権限を持っている場合、`ジャンプキー`を押し続けてチャージできます。
- **`dolphin`**\
  `ジャンプキー`を押すと突進します。
- **`phantom`**\
  `ジャンプキー`を押すと炎を発射します。
- **`wither`**\
  `相互作用`するとウィザーの頭を発射します。

</details>

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`(Entity) > ridable`を有効にした場合のみ動作します。**

{% endhint %}

#### `bukkit.command.compass`

- **デフォルト**: `ワールド管理者`

[`/compass`コマンド](commands.md#compass)の使用を許可します。

#### `bukkit.command.credits`

- **デフォルト**: `ワールド管理者`

[`/credits (Player)`コマンド](commands.md#credits)の使用を許可します。

권한名の後に`.other`を入力すると他のプレイヤーに使用できるように許可します。

#### `bukkit.command.demo`

- **デフォルト**: `ワールド管理者`

[`/demo (Player)`コマンド](commands.md#demo)の使用を許可します。

권한名の後に`.other`を入力すると他のプレイヤーに使用できるように許可します。

#### `bukkit.command.ping`

- **デフォルト**: `ワールド管理者`

[`/ping (Player)`コマンド](commands.md#ping)の使用を許可します。

권한名の後に`.other`を入力すると他のプレイヤーに使用できるように許可します。

#### `bukkit.command.ram`

- **デフォルト**: `ワールド管理者`

[`/ram`コマンド](commands.md#ram)の使用を許可します。

#### `bukkit.command.rambar`

- **デフォルト**: `ワールド管理者`

[`/rambar (Player)`コマンド](commands.md#rambar)の使用を許可します。

권한名の後に`.other`を入力すると他のプレイヤーに使用できるように許可します。

#### `bukkit.command.restart`

- **デフォルト**: `ワールド管理者`

[`/restart`コマンド](commands.md#restart)の使用を許可します。

#### `bukkit.command.tps`

- **デフォルト**: `ワールド管理者`

[`/tps`コマンド](commands.md#tps)の使用を許可します。

#### `bukkit.command.tpsbar`

- **デフォルト**: `ワールド管理者`

[`/tpsbar (Player)`コマンド](commands.md#tpsbar)の使用を許可します。

권한名の後に`.other`を入力すると他のプレイヤーに使用できるように許可します。

#### `bukkit.command.timings`

- **デフォルト**: `ワールド管理者`

[`/timings`コマンド](commands.md#timings)の使用を許可します。

{% hint style="warning" %}

**該当コマンドは使用が中止されました。**

類似の機能を持つコマンドについては、[Spark](https://spark.lucko.me/docs/Command-Usage)をご確認ください。

{% endhint %}

#### `bukkit.command.uptime`

- **デフォルト**: `ワールド管理者`

[`/uptime`コマンド](commands.md#uptime)の使用を許可します。

#### `minecraft.command.gamemode.(GameMode)`

- **デフォルト**: `ワールド管理者`

`/gamemode (GameMode) (Player)`コマンドの使用を許可します。

권한名の後に`.other`を入力すると他のプレイヤーに使用できるように許可します。

#### `paper.antixray.bypass`

- **デフォルト**: `なし`

[X-Rayブロック](../expert/xray.md)が有効な場合、登録されたプレイヤーにはX-Rayブロックの暗号化を行いません。

これにより、両者ともパフォーマンスが向上します。

> X-Rayの設定方法については、以下のページを参照してください。

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **デフォルト**: `なし`

{% hint style="warning" %}

該当権限は1.20.5で`plazma.bypass.watchdog`に変更される予定です。

{% endhint %}

#### `purpur.anvil.color`

- **デフォルト**: `なし`

金床で[色コード](https://minecraft.wiki/w/Formatting_codes#Color_codes)を使用できるようにします。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`anvil > allow-colors`を有効にする必要があります。**

{% endhint %}

#### `purpur.anvil.format`

- **デフォルト**: `なし`

金床で[スタイリングコード](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)を使用できるようにします。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`anvil > allow-colors`を有効にする必要があります。**

{% endhint %}

#### `purpur.anvil.minimessage`

- **デフォルト**: `なし`

金床で[MiniMessageタグ](https://docs.advntr.dev/minimessage/format.html)を使用できるようにします。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`anvil > allow-minimessages`を有効にする必要があります。**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **デフォルト**: `なし`

金床で[`&r`スタイリングコード](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)で`italic`を無効にできるようにします。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`anvil > allow-colors`を有効にする必要があります。**

{% endhint %}

#### `purpur.book.color.sign`

- **デフォルト**: `なし`

プレイヤーが本に署名すると[スタイリングコード](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)が適用されます。

#### `purpur.bypassIdleKick`

- **デフォルト**: `なし`

プレイヤーをアイドルキックの対象から除外します。

#### `purpur.debug.f3n`

- **デフォルト**: `ワールド管理者`

プレイヤーが`F3 + N`キーでゲームモードを変更できるようにします。

該当ゲームモードの権限がない場合は機能しません。

#### `purpur.drop.spawners`

- **デフォルト**: `なし`

構成で設定したアイテムでスポナーブロックを採掘するとスポナーブロックが落ちます。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`gameplay-mechanics > silk-touch`を有効にする必要があります。**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **デフォルト**: `なし`

エンダーチェストのサイズを変更します。

`(NumberString)`には`one`, `two`, `three`, `four`, `five`, `six`を入力できます。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`ender_chest > six-rows`および`ender_chest > use-permissions-for-rows`を有効にする必要があります。**

{% endhint %}

#### `purpur.inventory_totem`

- **デフォルト**: `なし`

不死のトーテムがインベントリにあっても機能するようにします。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`totem-of-undying-works-in-inventory`を有効にする必要があります。**

{% endhint %}

#### `purpur.joinFullServer`

- **デフォルト**: `なし`

プレイヤーが接続者数制限を無視するように許可します。

#### `purpur.mending_shift_click`

- **デフォルト**: `なし`

プレイヤーが`しゃがんで相互作用`すると、持っているアイテムを修理できるように許可します。

{% hint style="info" %}

**[Purpur ワールド構成](configurations/purpur/world.md)で`shift-right-click-repairs-mending-points`を有効にする必要があります。**

{% endhint %}

#### `purpur.place.spawners`

- **デフォルト**: `なし`

プレイヤーがスポナーを設置できるように許可します。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`gameplay-mechanics > silk-touch`を有効にする必要があります。**

{% endhint %}

#### `purpur.portal.instant`

- **デフォルト**: `なし`

プレイヤーがネザーポータルを使用した際、直ちにテレポートします。

#### `purpur.sign.color`

- **デフォルト**: `なし`

看板で[色コード](https://minecraft.wiki/w/Formatting_codes#Color_codes)を使用できるように許可します。

{% hint style="info" %}

**[Purpur ワールド構成](configurations/purpur/world.md)で `sign > allow-colors` を有効にする必要があります。**

{% endhint %}

#### `purpur.sign.magic`

- **デフォルト**: `なし`

표지판에 난독화 코드`(&o)`를使用できるように許可します。

{% hint style="info" %}

**[Purpur ワールド構成](configurations/purpur/world.md)で `sign > allow-colors` を有効にする必要があります。**

{% endhint %}

#### `purpur.sign.style`

- **デフォルト**: `なし`

표지판に[スタイリングコード`(&o除く)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes)を使用できるように許可します。

{% hint style="info" %}

**[Purpur ワールド構成](configurations/purpur/world.md)で `sign > allow-colors` を有効にする必要があります。**

{% endhint %}

#### `purpur.tnt.defuse`

- **デフォルト**: `なし`

プレイヤーがはさみで`相互作用`してTNTの爆発を防ぐことを許可します。

{% hint style="info" %}

**[Purpurワールド構成](configurations/purpur/world.md)で`defuse-tnt-change`が`0.0`以上である必要があります。**

{% endhint %}

### 提供予定権限

#### `plazma.bypass.ncr-require`

- **デフォルト**: `なし`

プレイヤーが[`NoChatReports`](https://modrinth.com/mod/no-chat-reports)モードがインストールされていなくても接続できるように許可します。

{% hint style="info" %}

**[Plazmaワールド構成](configurations/plazma/world.md)で`no-chat-reports > require-install`を有効にする必要があります。**

{% endhint %}

***

[^1]: Operator.

[^2]: 例:`ender_dragon`
