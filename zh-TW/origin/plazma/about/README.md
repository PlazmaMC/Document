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

1. **強大的插件生態系統**\
   [Paper](https://github.com/PaperMC/Paper)以其為基礎，
   大多數可在網上下載的[最新插件](#user-content-fn-1)[^1]可以正常運作。
2. **無需設置的優化**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)包含所有修補程式，
   內置一些自身優化和模式，提供最佳性能。
3. **按需自定義的遊戲**\
   包含在Plazma中的[Purpur](https://github.com/PurpurMC/Purpur)可修改遊戲的整體屬性。
4. **安全遊玩的伺服器**\
   包含[No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)，可從1.19版起停用
   [Mojang](#user-content-fn-2)[^2]的[聊天舉報系統](#user-content-fn-3)[^3]，\
   完全刪除診斷信息收集器，可在無跟踪的安全伺服器上遊玩。
5. **最快的更新**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)確保Plazma的補丁始終保持最新，提供Paper基礎伺服器平台中最快的更新。
6. **優化的預設配置文件**\
   預設應用的配置文件已優化，無需自行優化配置文件。
7. **多線程運作**\
   通過異步化與遊戲機制無關的系統機制，減少[延遲時間](#user-content-fn-4)[^4]以優化伺服器。
8. **阻止不必要空間使用**\
   將具有相似值的數據合併為一個以減少內存使用。

#### 想了解更多關於Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ 應用案例 <a href="#id-3" id="id-3"></a>

- **能夠正確處理複雜插件的平台**\
  由開發者[IPECTER](https://github.com/IPECTER)的伺服器使用Plazma。\
  自身插件使用NMS和反射運作，應用了複雜和龐大的數據包，\
  即使有超過100名玩家，也能在沒有性能下降的情況下接受。
- **在RPG伺服器上保持快速性能的平台**\
  在單個集群中，100名玩家能夠穩定地保持TPS無下降，\
  在4個集群中，共有250名玩家可以愉快遊玩。
- **在區塊/實體中顯示光芒的平台**\
  將原本在處理區塊和實體時導致延遲的生存伺服器平台
  從Purpur更改為Plazma後，能夠減少大部分延遲。
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="實時 Plazma 使用者趨勢">
</a>

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
