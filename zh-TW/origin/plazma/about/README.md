---
description: 了解 Plazma 是什麼服務器平台。
---

# ❓ 什麼是Plazma?

- **Plazma**是基於[Andromeda](https://github.com/EarendelArchived/Andromeda)和[Fusion](https://github.com/RuinedTechnologyUnify/Fusion)的優點，以[Paper](https://github.com/PaperMC/Paper)為基礎的服務器平台。
- 我們致力於提供高度穩定性和強大性能、快速更新和豐富功能。

## 📋 Plazma的目標 <a href="#id-1" id="id-1"></a>

- 我們致力於成為一個擁有快速更新和高度穩定性的服務器平台。
- 我們致力於提供與模組平台不相上下的豐富功能和強大性能。
- 我們致力於創建一個可以自由定制甚至自訂Vanilla補丁的平台。

## ⚙️ 主要特點 <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **最快的更新**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)確保Plazma的補丁始終保持最新，提供Paper基礎伺服器平台中最快的更新。
6. **優化的預設配置文件**\
   預設應用的配置文件已優化，無需自行優化配置文件。
7. **多線程運作**\
   通過異步化與遊戲機制無關的系統機制，減少[延遲時間](#user-content-fn-4)[^4]以優化伺服器。
8. **阻止不必要空間使用**\
   將具有相似值的數據合併為一個以減少內存使用。

## ✨ 應用案例 <a href="#id-3" id="id-3"></a>

- **能夠正確處理複雜插件的平台**\
  由開發者[IPECTER](https://github.com/IPECTER)的伺服器使用Plazma。\
  自身插件使用NMS和反射運作，應用了複雜和龐大的數據包，\
  即使有超過100名玩家，也能在沒有性能下降的情況下接受。
- **在RPG伺服器上保持快速性能的平台**\
  在單個集群中，100名玩家能夠穩定地保持TPS無下降，\
  在4個集群中，共有250名玩家可以愉快遊玩。
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **許多串流媒體選擇的平台**\
  許多串流媒體的觀眾參與桶被選擇並使用。

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ 下載

您可以在以下頁面下載Plazma。

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### 想了解支援的版本詳情?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot插件以及Paper, Pufferfish, Purpur插件。

[^2]: 由Microsoft Corporation提供。

[^3]: 停用聊天舉報系統後，聊天將完全在伺服器上處理，防止Mojang的聊天追踪。

[^4]: 系統機制需要暫停遊戲以運作。
