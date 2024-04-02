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
   基於[Paper](https://github.com/PaperMC/Paper)，大部分可在互聯網上下載的[最新插件](#user-content-fn-1)[^1]均能正常運作。
2. **無需設置的優化**\
   包含[Pufferfish](https://github.com/pufferfish-gg/Pufferfish)的所有補丁，並且內置了一些自身優化和模組，提供最佳性能。
3. **自定義遊戲**\
   包括在Plazma中的[Purpur](https://github.com/PurpurMC/Purpur)可修改遊戲的整體屬性。
4. **安全遊戲伺服器**\
   包含[No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)，可停用自1.19版起新增的Mojang[^2]的[聊天舉報系統](#user-content-fn-3)[^3]，並完全刪除診斷信息收集器，讓玩家能在無跟踪的安全伺服器上遊玩。
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

- **處理複雜插件的平台**\
  由開發者[IPECTER](https://github.com/IPECTER)的伺服器使用Plazma。 即使使用自家插件，運作依賴NMS和反射，以及大量複雜數據包，仍可在不降低性能的情況下接受100名以上的玩家。
- **在RPG伺服器上保持高性能的平台**\
  在單一集群中，能穩定容納100名玩家而不影響TPS，並且在4個集群中共有250名玩家可以順暢遊玩。
- **在區塊/實體方面展示光芒的平台**\
  將Purpur替換為Plazma後，成功減少大部分原有的區塊和實體處理延遲。
- **許多流行串流平台的選擇**\
  許多知名串流平台的觀眾選擇使用Plazma作為其服務器。

<figure><img src="https://camo.githubusercontent.com/22acffd515755c2cee2078a7697ff35351c5ec7148eb2806deedbe63df1c4ed7/68747470733a2f2f6273746174732e6f72672f7369676e6174757265732f7365727665722d696d706c656d656e746174696f6e2f506c617a6d612e737667" alt=""><figcaption><p>即時Plazma使用者趨勢</p></figcaption></figure>

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
