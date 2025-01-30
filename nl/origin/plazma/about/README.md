---
description: Ontdek wat Plazma voor een serverplatform is.
---

# ❓ Wat is Plazma?

- **Plazma** is een serverplatform gebaseerd op [Paper](https://github.com/PaperMC/Paper) dat alleen de voordelen van [Andromeda](https://github.com/EarendelArchived/Andromeda) en [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) overneemt.
- We streven altijd naar hoge stabiliteit, krachtige prestaties, snelle updates en uitgebreide functionaliteit.

## 📋 Doelstellingen van Plazma <a href="#id-1" id="id-1"></a>

- We streven ernaar een serverplatform te zijn met snelle updates en hoge stabiliteit.
- We streven ernaar om uitgebreide functionaliteit en krachtige prestaties te bieden die niet onderdoen voor modplatforms.
- We streven ernaar een vrij platform te creëren waarop ook vanilla patches kunnen worden aangepast.

## ⚙️ Belangrijkste kenmerken <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Snelste updates**\
   Met [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) blijven de patches van Plazma altijd up-to-date, waardoor het het snelste updateproces biedt onder de op Paper gebaseerde serverplatforms.
6. **Geoptimaliseerde standaard configuratiebestanden**\
   De standaard toegepaste configuratiebestanden zijn geoptimaliseerd, zodat u ze niet zelf hoeft te optimaliseren.
7. **Efficiënt werkende multithreading**\
   Door systeemmechanismen die niet gerelateerd zijn aan het spelmechanisme asynchroon te maken, wordt de server geoptimaliseerd om de vertraging te verminderen.
8. **Voorkomen van onnodig geheugengebruik**\
   Door vergelijkbare waarden samen te voegen, wordt de geheugenconsumptie verminderd.

## ✨ Gebruiksscenario's <a href="#id-3" id="id-3"></a>

- **Platform dat zelfs complexe plug-ins correct verwerkt**\
  Plazma wordt gebruikt op de server van ontwikkelaar [IPECTER](https://github.com/IPECTER). Ondanks de zelf ontwikkelde plug-ins die werken met NMS en reflectie, en het grote aantal uitgebreide datapacks, kan het meer dan 100 spelers ontvangen zonder prestatieverlies.
- **Platform dat snelle prestaties behoudt, zelfs op een RPG-server**\
  Op een enkel cluster konden 100 spelers stabiel blijven zonder TPS-verlaging, en op 4 clusters konden in totaal 250 spelers comfortabel spelen.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Veel gekozen platform door veel streamers**\
  Wordt gebruikt als een emmer voor kijkersparticipatie van veel streamers.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Download

U kunt Plazma downloaden vanaf de onderstaande pagina.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Meer informatie over ondersteunde versies?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot plug-ins en Paper, Pufferfish, Purpur plug-ins.

[^2]: Door Microsoft Corporation.

[^3]: Door het uitschakelen van het chatsysteem wordt de chat volledig op de server verwerkt en wordt het chattrackingmechanisme van Mojang geblokkeerd.

[^4]: Tijd die nodig is voor het systeemmechanisme om te werken, waarbij het spel tijdelijk wordt onderbroken.
