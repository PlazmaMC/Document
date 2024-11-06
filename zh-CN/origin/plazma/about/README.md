---
description: 了解 Plazma 是什么样的服务器平台。
---

# ❓ Plazma是什么？

- **Plazma**是基于[Paper](https://github.com/PaperMC/Paper)的服务器平台，汲取了[Andromeda](https://github.com/EarendelArchived/Andromeda)和[Fusion](https://github.com/RuinedTechnologyUnify/Fusion)的优点。
- 我们致力于提供高度稳定性、强大性能、快速更新和丰富功能。

## 📋 Plazma的目标 <a href="#id-1" id="id-1"></a>

- 我们努力成为一个快速更新、高度稳定的服务器平台。
- 我们努力提供与模组平台不相上下的丰富功能和强大性能。
- 我们努力创建一个可以自由定制甚至调整Vanilla补丁的平台。

## ⚙️ 主要特点 <a href="#id-2" id="id-2"></a>

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
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)确保Plazma的内置补丁始终保持最新，为基于Paper的服务器平台提供最快的更新速度。
6. **优化默认配置文件**\
   默认应用的配置文件已经优化，无需自行优化配置文件。
7. **多线程高效运行**\
   通过异步化与游戏机制无关的系统机制，减少[延迟时间](#user-content-fn-4)[^4]以优化服务器。
8. **阻止不必要的空间使用**\
   将具有相似值的数据合并为一个以减少内存使用。

## ✨ 应用案例 <a href="#id-3" id="id-3"></a>

- **能正确处理复杂插件的平台**\
  由开发者[IPECTER](https://github.com/IPECTER)的服务器使用Plazma。\
  使用NMS和反射运行的自制插件，应用了复杂和庞大的数据包，即使有100多名玩家，也能保持性能稳定。
- **在RPG服务器上保持快速性能的平台**\
  在单个集群中，保持100名玩家的TPS稳定，
  在4个集群中，总共250名玩家可以愉快地游玩。
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **许多主播选择的平台**\
  被许多主播的观众用作参与的桶。

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ 下载

您可以在下面的页面上下载Plazma。

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### 想了解版本支持的详细信息？

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit、CraftBukkit、Spigot插件以及Paper、Pufferfish、Purpur插件。

[^2]: 由Microsoft Corporation提供。

[^3]: 禁用聊天举报系统将使聊天完全在服务器上处理，阻止Mojang的聊天跟踪。

[^4]: 系统机制需要暂停游戏以运行。
