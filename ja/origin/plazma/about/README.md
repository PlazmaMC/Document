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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **最速のアップデート**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)はPlazmaの含まれるパッチが常に最新に保たれるようにして、Paperベースのサーバープラットフォームの中で最速のアップデートを提供しています。
6. **基本構成ファイルの最適化**\
   デフォルトで適用される構成ファイルが最適化されており、直接構成ファイルを最適化する必要がありません。
7. **体系的に動作するマルチスレッド**\
   ゲームのメカニズムと関係ないシステムメカニズムを非同期化して、[遅延時間](#user-content-fn-4)[^4]を減らし、サーバーを最適化します。
8. **不要なスペースの使用を防止**\
   似た値を持つデータをすべて1つにまとめてメモリ使用量を削減します。

## ✨ 活用事例 <a href="#id-3" id="id-3"></a>

- **複雑なプラグインも適切に処理するプラットフォーム**\
  開発者[IPECTER](https://github.com/IPECTER)のサーバーでPlazmaが使用されています。\
  NMSとリフレクションで動作する独自のプラグイン、複雑で巨大なデータパックが非常に多く適用されているにもかかわらず、\
  100人以上のプレイヤーをパフォーマンス低下なしに受け入れています。
- **RPGサーバーでも高速なパフォーマンスを維持するプラットフォーム**\
  単一クラスターで100人のプレイヤーをTPS低下なしに安定的に維持し、\
  4つのクラスターで合計250人のプレイヤーが快適にプレイすることができました。
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **多くのストリーマーが選んだプラットフォーム**\
  多くのストリーマーの視聴者参加用バケツとして選ばれて使用されています。

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
