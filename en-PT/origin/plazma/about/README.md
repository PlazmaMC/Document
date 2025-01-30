---
description: Find out what kind o' server platform Plazma be.
---

# ❓ What be Plazma?

- **Plazma** be [Andromeda](https://github.com/EarendelArchived/Andromeda) and [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) advantages only be taken from [Paper](https://github.com/PaperMC/Paper) base o' server platform.
- Always high stability and powerful performance, quick updates, be strive t' provide vast features.

## 📋 Plazma's goal <a href="#id-1" id="id-1"></a>

- Strive t' be a server platform with quick updates and high stability.
- Strive t' provide vast features and powerful performance not inferior t' mod platforms.
- Strive t' create a free platform that can be customized even vanilla patches.

## ⚙️ Main features <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Fastest updates**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) ensures that Plazma's included patches be always kept up t' date, providin' the fastest updates among Paper-based server platforms.
6. **Optimized default configuration files**\
   The default configuration files be optimized, so ye don't need t' optimize the configuration files yerself.
7. **Systematically operate multi-threaded**\
   Asynchronize system mechanisms unrelated t' the game's mechanisms t' reduce [latency](#user-content-fn-4)[^4] and optimize the server.
8. **Block unnecessary space usage**\
   Combine all data with similar values into one t' reduce memory usage.

## ✨ Use cases <a href="#id-3" id="id-3"></a>

- **Platform handlin' complex plugins correctly**\
  Plazma be used on developer [IPECTER](https://github.com/IPECTER)'s server.\
  With self-plugins operatin' with NMS an' reflection, extensive an' complex data packs be heavily applied,\
  acceptin' over 100 players without performance degradation.
- **Platform maintainin' fast performance on RPG servers**\
  Stably maintainin' 100 players on a single cluster without TPS drops, an' allowin' a pleasant play experience fer 250 players on 4 clusters.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Many streamers be choosin' th' platform**\
  Many streamers' viewers be choosin' it as a bucket fer participation.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Download

Ye can download Plazma from the page below.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### If ye be wantin' detailed information about version support?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot plugins and Paper, Pufferfish, Purpur plugins.

[^2]: Below be Microsoft Corporation.

[^3]: Disablin' the chat report system allows chat t' be processed only on the server, preventin' Mojang's chat tracking.

[^4]: Time when the game pauses momentarily for the system mechanism t' operate.
