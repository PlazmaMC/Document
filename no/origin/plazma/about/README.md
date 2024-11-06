---
description: Finn ut hva Plazma serverplattformen er.
---

# ❓ Hva er Plazma?

- **Plazma** er en serverplattform basert på [Paper](https://github.com/PaperMC/Paper) som bare tar med seg fordelene fra [Andromeda](https://github.com/EarendelArchived/Andromeda) og [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Vi streber alltid etter å tilby høy stabilitet, kraftig ytelse, raske oppdateringer og et omfattende sett med funksjoner.

## 📋 Målene til Plazma <a href="#id-1" id="id-1"></a>

- Vi jobber hardt for å bli en serverplattform med raske oppdateringer og høy stabilitet.
- Vi jobber hardt for å tilby et omfattende sett med funksjoner og kraftig ytelse som ikke står tilbake for mod-plattformer.
- Vi jobber hardt for å lage en fri plattform hvor selv vaniljepakker kan tilpasses.

## ⚙️ Viktige funksjoner <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Raskeste oppdateringer**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) sørger for at Plazmas inkluderte patcher alltid er oppdatert, og tilbyr dermed de raskeste oppdateringene blant serverplattformene basert på Paper.
6. **Optimaliserte standardkonfigurasjonsfiler**\
   Standardkonfigurasjonsfilene er optimalisert slik at du ikke trenger å optimalisere dem manuelt.
7. **Systematisk flertrådsdrift**\
   Asynkroniserer systemmekanikk som ikke er relatert til spillmekanikken for å optimalisere serveren og redusere [ventetiden](#user-content-fn-4)[^4].
8. **Blokkerer unødvendig bruk av plass**\
   Samler sammen data med lignende verdier for å redusere minnebruken.

## ✨ Brukstilfeller <a href="#id-3" id="id-3"></a>

- **Behandler selv komplekse plugins riktig**\
  Plazma brukes på servere av utvikleren [IPECTER](https://github.com/IPECTER). Selv med egne plugins som fungerer med NMS og refleksjon, samt en stor mengde komplekse datapakker, kan den håndtere over 100 spillere uten ytelsesfall.
- **Opprettholder rask ytelse selv på RPG-servere**\
  Klarte å opprettholde 100 spillere på en enkelt kluster uten TPS-fall, og totalt 250 spillere på 4 klustre kunne spille komfortabelt uten problemer.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Mange strømmere har valgt plattformen**\
  Mange strømmere bruker den som en bøtte for seerengasjement.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Nedlasting

Du kan laste ned Plazma fra siden nedenfor.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Ønsker du mer informasjon om støttede versjoner?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot-plugins og Paper, Pufferfish, Purpur-plugins.

[^2]: Eies av Microsoft Corporation.

[^3]: Ved å deaktivere chat report system vil chatten kun behandles på serveren og Mojangs chat-sporing vil bli stoppet.

[^4]: Tiden det tar for systemmekanikken å fungere og for spillet å midlertidig fryse.
