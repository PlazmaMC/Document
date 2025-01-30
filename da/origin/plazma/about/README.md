---
description: Lær mere om, hvad Plazma serverplatformen er.
---

# ❓ Hvad er Plazma?

- **Plazma** er en serverplatform baseret på [Paper](https://github.com/PaperMC/Paper), der kun bringer fordelene fra [Andromeda](https://github.com/EarendelArchived/Andromeda) og [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Vi stræber altid efter at levere høj stabilitet, kraftfuld ydeevne, hurtige opdateringer og omfattende funktioner.

## 📋 Mål for Plazma <a href="#id-1" id="id-1"></a>

- Vi arbejder hårdt for at blive en serverplatform med hurtige opdateringer og høj stabilitet.
- Vi stræber efter at tilbyde omfattende funktioner og kraftfuld ydeevne, ikke mindre end en modplatform.
- Vi arbejder på at skabe en fri platform, hvor selv Vanilla-patches kan tilpasses.

## ⚙️ Vigtigste funktioner <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Hurtigste opdateringer**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) sikrer, at Plazmas inkluderede patches altid er opdaterede, hvilket giver de hurtigste opdateringer blandt Paper-baserede serverplatforme.
6. **Optimerede standardkonfigurationsfiler**\
   De medfølgende konfigurationsfiler er optimerede, så du ikke behøver at optimere dem manuelt.
7. **Effektivt multi-threaded drift**\
   Ved at asynkronisere systemmekanismer, der ikke er relateret til spillets mekanik, reduceres [latency](#user-content-fn-4)[^4] for at optimere serveren.
8. **Blokerer for unødvendig hukommelsesbrug**\
   Værdier med lignende data kombineres for at reducere hukommelsesforbruget.

## ✨ Anvendelseseksempler <a href="#id-3" id="id-3"></a>

- **En platform der korrekt håndterer komplekse plugins**\
  På udvikleren [IPECTER](https://github.com/IPECTER)'s server bruges Plazma.\
  Selv med egne plugins der fungerer med NMS og refleksion, samt store komplekse datapakker,\
  kan den modtage over 100 spillere uden ydeevneproblemer.
- **En platform der opretholder hurtig ydeevne selv på RPG-servere**\
  Det lykkedes at holde 100 spillere stabilt uden TPS-fald på en enkelt klynge,\
  og 250 spillere på 4 klynger kunne spille behageligt.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Mange streamere har valgt platformen**\
  Det er blevet valgt som en spand til seerengagement af mange streamere.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Download

Du kan downloade Plazma fra nedenstående side.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Vil du have detaljer om understøttede versioner?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot-plugins og Paper, Pufferfish, Purpur-plugins.

[^2]: Ejet af Microsoft Corporation.

[^3]: Ved at deaktivere chat rapporteringssystemet kan chatten kun behandles på serveren og forhindre Mojangs chat sporing.

[^4]: Den tid, hvor spillet midlertidigt stopper for at lade systemmekanismer fungere.
