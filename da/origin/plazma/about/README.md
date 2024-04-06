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
   Da det er baseret på [Paper](https://github.com/PaperMC/Paper), fungerer de fleste [nyeste plugins](#user-content-fn-1)[^1] fra internettet korrekt.
2. **Optimering uden behov for konfiguration**\
   Alle patches fra [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) er inkluderet, og med intern optimering og indbyggede mods tilbyder den den bedste ydeevne.
3. **Spil, som du vil**\
   [Purpur](https://github.com/PurpurMC/Purpur) inkluderet i Plazma giver mulighed for at ændre spillets overordnede egenskaber.
4. **Sikker spilserver**\
   [Ingen chatrapporter](https://github.com/Aizistral-Studios/No-Chat-Reports) er inkluderet, så fra 1.19 kan du deaktivere [Mojang](#user-content-fn-2)[^2]'s [chatrapportsystem](#user-content-fn-3)[^3] og fjerne diagnostikopsamleren helt for at spille på en sikker server uden sporbarhed.
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

- **En platform, der korrekt håndterer komplekse plugins**\
  Plazma bruges på udvikleren [IPECTER](https://github.com/IPECTER)'s server. Selv med egne plugins, der fungerer med NMS og refleksion, samt komplekse og store datapakker, håndterer den over 100 spillere uden ydeevneforringelse.
- **En platform, der opretholder hurtig ydeevne på RPG-servere**\
  Den har holdt 100 spillere på en enkelt klynge stabilt uden TPS-fald og tillod 250 spillere på 4 klynger at spille behageligt.
- **En platform, der lyser i chunk/entity-behandling**\
  Ved at skifte fra Purpur til Plazma på en overlevelsesserver, hvor der tidligere var forsinkelser i chunk- og entity-behandling, kunne de fleste forsinkelser reduceres.
- **Valgt af mange streamere**\
  Det bruges som en bucket til mange populære streamers seertal.

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
