---
description: Plazmaがどのようなサーバープラットフォームかを知ってください。
---

# ❓ Plazma란?

- **Plazma**は[Andromeda](https://github.com/EarendelArchived/Andromeda)と[Fusion](https://github.com/RuinedTechnologyUnify/Fusion)から利点だけを取り入れた[Paper](https://github.com/PaperMC/Paper)ベースのサーバープラットフォームです。
- 常に高い安定性と強力なパフォーマンス、迅速なアップデート、多機能を提供するために努力しています。

## 📋 Plazmaの目標 <a href="#id-1" id="id-1"></a>

- 迅速なアップデート、高い安定性を持つサーバープラットフォームとなるために努力しています。
- モッドプラットフォームに引けを取らない多機能と強力なパフォーマンスを提供するために努力しています。
- バニラのパッチもカスタマイズ可能な自由なプラットフォームを作るために努力しています。

## ⚙️ 主な特徴 <a href="#id-2" id="id-2"></a>

1. **強力なプラグインエコシステム**\
   [Paper](https://github.com/PaperMC/Paper)をベースにしており、インターネットでダウンロード可能なほとんどの[最新プラグイン](#user-content-fn-1)[^1]が正常に動作します。
2. **設定が不要な最適化**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)のすべてのパッチが含まれており、一部の独自の最適化とモッドが組み込まれているため、最高のパフォーマンスを提供します。
3. **自由にカスタマイズするゲーム**\
   Plazmaに含まれる[Purpur](https://github.com/PurpurMC/Purpur)はゲームの全般的な属性を変更できるようにします。
4. **安全にプレイするサーバー**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)が含まれており、1.19から追加されたMojang[^2]の[チャットレポートシステム](#user-content-fn-3)[^3]を無効化でき、診断情報収集機が完全に削除され、追跡のない安全なサーバーをプレイできます。
5. **最速のアップデート**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)はPlazmaの含まれるパッチが常に最新に保たれるようにして、Paperベースのサーバープラットフォームの中で最速のアップデートを提供しています。
6. **基本構成ファイルの最適化**\
   デフォルトで適用される構成ファイルが最適化されており、直接構成ファイルを最適化する必要がありません。
7. **体系的に動作するマルチスレッド**\
   ゲームのメカニズムと関係ないシステムメカニズムを非同期化して、[遅延時間](#user-content-fn-4)[^4]を減らし、サーバーを最適化します。
8. **不要なスペースの使用を防止**\
   似た値を持つデータをすべて1つにまとめてメモリ使用量を削減します。

#### Plazmaについてもっと知りたいですか？ <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ 活用事例 <a href="#id-3" id="id-3"></a>

- **複雑なプラグインも正しく処理するプラットフォーム**\
  開発者[IPECTER](https://github.com/IPECTER)のサーバーでPlazmaが使用されています。 NMSとリフレクションで動作する独自プラグイン、複雑で大規模なデータパックが多く適用されているにもかかわらず、
  100人以上のプレイヤーをパフォーマンス低下なしに受け入れています。
- **RPGサーバーでも高速なパフォーマンスを維持するプラットフォーム**\
  単一クラスターで100人のプレイヤーをTPS低下なしに安定的に維持し、4つのクラスターで合計250人のプレイヤーが快適にプレイできました。
- **チャンク/エンティティで光を放つプラットフォーム**\
  従来、チャンクやエンティティを処理する際に遅延が発生していたサバイバルサーバーのプラットフォームをPurpurからPlazmaに変更することで
  大部分の遅延を減らすことができました。
- **多くのストリーマーが選んだプラットフォーム**\
  多くの有名なストリーマーの視聴者向けバケツとして選ばれ、使用されています。

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>リアルタイムのPlazmaユーザー動向</p></figcaption>
</figure>

## ⬇️ ダウンロード

以下のページからPlazmaをダウンロードできます。

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### バージョンサポートに関する詳細情報を知りたいですか？

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit、CraftBukkit、SpigotプラグインおよびPaper、Pufferfish、Purpurプラグイン。

[^2]: 以下Microsoft Corporation。

[^3]: チャットレポートシステムを無効化すると、チャットがサーバー内でのみ処理され、Mojangのチャット追跡を防ぐことができます。

[^4]: システムメカニズムが作動するために一時的にゲームが停止する時間。
