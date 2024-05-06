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

1. **Kraftfull ekosystem för tillägg**\
   [Baserat på Paper](https://github.com/PaperMC/Paper),
   fungerar de flesta [senaste tilläggen](#user-content-fn-1)[^1] som finns tillgängliga för nedladdning på internet korrekt.
2. **Optimering utan behov av inställningar**\
   Alla patchar från [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) är inkluderade,
   med inbyggd optimering och moddar för att ge optimal prestanda.
3. **Anpassa spelet efter dina önskemål**\
   [Purpur](https://github.com/PurpurMC/Purpur) som ingår i Plazma gör det möjligt att modifiera spelets övergripande egenskaper.
4. **Säkra servrar för spel**\
   Med [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) inkluderat kan du från 1.19 inaktivera
   [Mojangs](#user-content-fn-2)[^2] [chattanmälningssystem](#user-content-fn-3)[^3] och helt ta bort diagnosinsamling för att spela på en säker server utan spårning.
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

- **Plattform som korrekt hanterar komplexa tillägg**\
  Plazma används på servern av utvecklaren [IPECTER](https://github.com/IPECTER).\
  Med egna tillägg som fungerar med NMS och reflektion, samt omfattande datapaket, kan den hantera över 100 spelare utan prestandaförlust.
- **Plattform som bibehåller snabb prestanda även på RPG-servrar**\
  En enda kluster kunde hålla 100 spelare utan TPS-förlust, och med 4 kluster kunde totalt 250 spelare spela smidigt.
- **Plattform som lyser i chunkar/entiteter**\
  Genom att byta från Purpur till Plazma för servern för överlevnadsspel, kunde de minska större delen av fördröjningen som uppstod vid hantering av chunkar och entiteter.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Real-time Plazma användartrender">
</a>

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
