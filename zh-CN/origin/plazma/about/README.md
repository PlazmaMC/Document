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
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어,
   인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며,
   일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을
   수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된
   [Mojang](#user-content-fn-2)[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **最快的更新**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)确保Plazma的内置补丁始终保持最新，为基于Paper的服务器平台提供最快的更新速度。
6. **优化默认配置文件**\
   默认应用的配置文件已经优化，无需自行优化配置文件。
7. **多线程高效运行**\
   通过异步化与游戏机制无关的系统机制，减少[延迟时间](#user-content-fn-4)[^4]以优化服务器。
8. **阻止不必要的空间使用**\
   将具有相似值的数据合并为一个以减少内存使用。

#### 想了解更多关于Plazma的信息？ <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ 应用案例 <a href="#id-3" id="id-3"></a>

- **복잡한 플러그인도 올바르게 처리하는 플랫폼**\
  개발자 [IPECTER](https://github.com/IPECTER)의 서버에서 Plazma가 사용되고 있습니다.\
  NMS와 리플렉션으로 작동하는 자체 플러그인, 복잡하고 방대한 크기의 데이터팩이 굉장히 많이 적용되어 있음에도,\
  100명대 이상의 플레이어를 성능 하락 없이 받아들이고 있습니다.
- **RPG 서버에서도 빠른 성능을 유지한 플랫폼**\
  단일 클러스터에서 100명의 플레이어를 TPS 하락 없이 안정적으로 유지하였으며,\
  4개의 클러스터에서 총 250명의 플레이어가 쾌적하게 플레이 할 수 있었습니다.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을
  Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 첨여용 버킷으로 선택받아 사용되고 있습니다.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>实时Plazma用户趋势</p></figcaption>
</figure>

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
