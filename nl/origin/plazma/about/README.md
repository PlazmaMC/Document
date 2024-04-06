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

1. **Krachtig plug-in ecosysteem**\
   Dankzij de basis van [Paper](https://github.com/PaperMC/Paper) werken de meeste [recente plug-ins](#user-content-fn-1)[^1] die op internet beschikbaar zijn naar behoren.
2. **Geoptimaliseerd zonder configuratie**\
   Alle patches van [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) zijn inbegrepen, met enkele interne optimalisaties en ingebouwde mods voor optimale prestaties.
3. **Aanpasbaar naar wens**\
   Met [Purpur](https://github.com/PurpurMC/Purpur) in Plazma kunt u de algehele eigenschappen van het spel aanpassen.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 [Mojang](#user-content-fn-2)[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며, 진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Snelste updates**\
   Met [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) blijven de patches van Plazma altijd up-to-date, waardoor het het snelste updateproces biedt onder de op Paper gebaseerde serverplatforms.
6. **Geoptimaliseerde standaard configuratiebestanden**\
   De standaard toegepaste configuratiebestanden zijn geoptimaliseerd, zodat u ze niet zelf hoeft te optimaliseren.
7. **Efficiënt werkende multithreading**\
   Door systeemmechanismen die niet gerelateerd zijn aan het spelmechanisme asynchroon te maken, wordt de server geoptimaliseerd om de vertraging te verminderen.
8. **Voorkomen van onnodig geheugengebruik**\
   Door vergelijkbare waarden samen te voegen, wordt de geheugenconsumptie verminderd.

#### Meer weten over Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Gebruiksscenario's <a href="#id-3" id="id-3"></a>

- **Platform dat zelfs complexe plug-ins correct verwerkt**\
  Plazma wordt gebruikt op de server van ontwikkelaar [IPECTER](https://github.com/IPECTER). Met eigen plug-ins die werken met NMS en reflectie, en een groot aantal complexe datapacks, kan het platform meer dan 100 spelers tegelijkertijd zonder prestatieverlies aan.
- **Platform dat snelle prestaties behoudt op RPG-servers**\
  Op een enkel cluster kon het platform 100 spelers zonder TPS-daling stabiel houden, en op 4 clusters konden in totaal 250 spelers comfortabel spelen.
- **Platform dat licht laat schijnen op chunks/entities**\
  Door over te stappen van Purpur naar Plazma voor het verwerken van chunks en entities op een survivalserver, kon het grootste deel van de vertraging worden verminderd.
- **Platform gekozen door vele streamers**\
  Veel bekende streamers gebruiken het als hun voorkeursbucket voor kijkers.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Real-time Plazma gebruikers trend</p></figcaption>
</figure>

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
