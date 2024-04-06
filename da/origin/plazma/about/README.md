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

1. **Stærkt plugin-økosystem**\
   [Paper](https://github.com/PaperMC/Paper) er baseret på,
   så de fleste [nyeste plugins](#user-content-fn-1)[^1] tilgængelige på internettet fungerer korrekt.
2. **Ingen konfigurationsoptimering påkrævet**\
   Alle patches fra [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) er inkluderet,
   med nogle interne optimeringer og indbyggede tilstande, der giver den bedste ydeevne.
3. **Tilpas spillet efter dine ønsker**\
   [Purpur](https://github.com/PurpurMC/Purpur) inkluderet i Plazma giver mulighed for at ændre
   spillets overordnede egenskaber efter behov.
4. **En server der spiller sikkert**\
   [Ingen Chat Rapporter](https://github.com/Aizistral-Studios/No-Chat-Reports) er inkluderet fra 1.19, som deaktiverer [Mojang](#user-content-fn-2)[^2]'s [chatrapporteringssystem](#user-content-fn-3)[^3],\
   og fjerner fuldstændigt diagnostisk dataværktøj, så du kan spille på en sporløs sikker server.
5. **Hurtigste opdateringer**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) sikrer, at Plazmas inkluderede patches altid er opdaterede, hvilket giver de hurtigste opdateringer blandt Paper-baserede serverplatforme.
6. **Optimerede standardkonfigurationsfiler**\
   De medfølgende konfigurationsfiler er optimerede, så du ikke behøver at optimere dem manuelt.
7. **Effektivt multi-threaded drift**\
   Ved at asynkronisere systemmekanismer, der ikke er relateret til spillets mekanik, reduceres [latency](#user-content-fn-4)[^4] for at optimere serveren.
8. **Blokerer for unødvendig hukommelsesbrug**\
   Værdier med lignende data kombineres for at reducere hukommelsesforbruget.

#### Vil du vide mere om Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Anvendelseseksempler <a href="#id-3" id="id-3"></a>

- **En platform der korrekt håndterer komplekse plugins**\
  På udvikleren [IPECTER](https://github.com/IPECTER)'s server bruges Plazma.\
  Selv med egne plugins der fungerer med NMS og refleksion, samt store komplekse datapakker,\
  kan den modtage over 100 spillere uden ydeevneproblemer.
- **En platform der opretholder hurtig ydeevne selv på RPG-servere**\
  Det lykkedes at holde 100 spillere stabilt uden TPS-fald på en enkelt klynge,\
  og 250 spillere på 4 klynger kunne spille behageligt.
- **En platform der viser lys i chunk/entity**\
  Ved at skifte fra Purpur til Plazma på en overlevelsesserver, hvor der tidligere var forsinkelser i behandlingen af chunks og entities,\
  kunne de fleste forsinkelser reduceres markant.
- **En platform valgt af mange streamere**\
  Bruges som en bucket til seerengagement af mange streamere.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Real-time Plasma brugertendens</p></figcaption>
</figure>

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
