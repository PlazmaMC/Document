---
description: Lär dig mer om vad Plazma är för serverplattform.
---

# ❓ Vad är Plazma?

- **Plazma** är en serverplattform baserad på [Paper](https://github.com/PaperMC/Paper) som endast tar med fördelarna från [Andromeda](https://github.com/EarendelArchived/Andromeda) och [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Vi strävar alltid efter att erbjuda hög stabilitet, kraftfull prestanda, snabba uppdateringar och omfattande funktioner.

## 📋 Målet med Plazma <a href="#id-1" id="id-1"></a>

- Vi strävar efter att bli en serverplattform med snabba uppdateringar och hög stabilitet.
- Vi strävar efter att erbjuda omfattande funktioner och kraftfull prestanda liknande en modplattform.
- Vi strävar efter att skapa en fri plattform där även Vanilla-patches kan anpassas.

## ⚙️ Huvudfunktioner <a href="#id-2" id="id-2"></a>

1. **Kraftfullt plugin-ekosystem**\
   Baserat på [Paper](https://github.com/PaperMC/Paper), vilket gör att de flesta [senaste plugins](#user-content-fn-1)[^1] som finns att ladda ner på internet fungerar korrekt.
2. **Optimering utan behov av konfiguration**\
   Inkluderar alla patchar från [Pufferfish](https://github.com/pufferfish-gg/Pufferfish), samt intern optimering och inbyggda moddar för att ge bästa prestanda.
3. **Anpassa spelet som du vill**\
   [Purpur](https://github.com/PurpurMC/Purpur) som ingår i Plazma möjliggör ändringar av spelets övergripande egenskaper.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 [Mojang](#user-content-fn-2)[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며, 진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Snabbast uppdateringar**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) ser till att Plazmas medföljande patchar alltid är uppdaterade, vilket ger de snabbaste uppdateringarna bland serverplattformar baserade på Paper.
6. **Optimerade standardkonfigurationsfiler**\
   Standardkonfigurationsfilerna är optimerade så att du inte behöver optimera dem manuellt.
7. **Effektivt flertrådat system**\
   Asynkronisering av systemmekanismer som inte påverkar spelets mekanik minskar [latens](#user-content-fn-4)[^4] och optimerar servern.
8. **Blockera användning av onödig plats**\
   Sammanfogar data med liknande värden för att minska minnesanvändningen.

#### Vill du veta mer om Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Användningsfall <a href="#id-3" id="id-3"></a>

- **En plattform som hanterar även komplexa plugins korrekt**\
  Plazma används på servern av utvecklaren [IPECTER](https://github.com/IPECTER). Med egna plugins som fungerar med NMS och reflektion, samt stora och komplexa datapaket, kan servern hantera över 100 spelare utan prestandaförlust.
- **En plattform med snabb prestanda även på RPG-servrar**\
  Har bibehållit stabiliteten med över 100 spelare på en enda kluster och möjliggjort smidig spelande för totalt 250 spelare på 4 kluster.
- **En plattform som lyser i chunkar/entiteter**\
  Genom att byta från Purpur till Plazma för en överlevnadsserver som tidigare hade fördröjningar i hanteringen av chunkar och entiteter kunde de minska de flesta fördröjningarna.
- **En plattform vald av många streamers**\
  Används av många populära streamers som deras förstahandsval för att spela med sina tittare.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Realtids Plazma användarutveckling</p></figcaption>
</figure>

## ⬇️ Ladda ner

På följande sida kan du ladda ner Plazma.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Vill du ha mer information om vilka versioner som stöds?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot-plugins och Paper, Pufferfish, Purpur-plugins.

[^2]: Tillhör Microsoft Corporation.

[^3]: Genom att inaktivera chattrapporteringssystemet kan chatten endast hanteras på servern och Mojangs chattracking kan förhindras.

[^4]: Tiden då spelet stannar för att systemmekanismer ska fungera.
