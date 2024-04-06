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

1. **Kraftig plugin-økosystem**\
   [Basert på](https://github.com/PaperMC/Paper) Paper, så fungerer de fleste [nyeste plugins](#user-content-fn-1)[^1] tilgjengelig for nedlasting på internett som de skal.
2. **Ingen behov for konfigurasjonsoptimalisering**\
   Inneholder alle patcher fra [Pufferfish](https://github.com/pufferfish-gg/Pufferfish), med noen interne optimaliseringer og moduler som gir optimal ytelse.
3. **Tilpass spillet slik du vil**\
   [Purpur](https://github.com/PurpurMC/Purpur) inkludert i Plazma lar deg endre spillens generelle egenskaper.
4. **Spill sikkert på serveren**\
   Inneholder [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) som lar deg deaktivere [Mojang](#user-content-fn-2)[^2]s [chat-rapporteringssystem](#user-content-fn-3)[^3] som ble lagt til fra 1.19. Diagnostiske informasjonssamlere er fullstendig fjernet, slik at du kan spille på en server uten spor og trygt.
5. **Raskeste oppdateringer**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) sørger for at Plazmas inkluderte patcher alltid er oppdatert, og tilbyr dermed de raskeste oppdateringene blant serverplattformene basert på Paper.
6. **Optimaliserte standardkonfigurasjonsfiler**\
   Standardkonfigurasjonsfilene er optimalisert slik at du ikke trenger å optimalisere dem manuelt.
7. **Systematisk flertrådsdrift**\
   Asynkroniserer systemmekanikk som ikke er relatert til spillmekanikken for å optimalisere serveren og redusere [ventetiden](#user-content-fn-4)[^4].
8. **Blokkerer unødvendig bruk av plass**\
   Samler sammen data med lignende verdier for å redusere minnebruken.

#### Ønsker du å lære mer om Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Brukstilfeller <a href="#id-3" id="id-3"></a>

- **Behandler selv komplekse plugins riktig**\
  Plazma brukes på servere av utvikleren [IPECTER](https://github.com/IPECTER). Selv med egne plugins som fungerer med NMS og refleksjon, samt en stor mengde komplekse datapakker, kan den håndtere over 100 spillere uten ytelsesfall.
- **Opprettholder rask ytelse selv på RPG-servere**\
  Klarte å opprettholde 100 spillere på en enkelt kluster uten TPS-fall, og totalt 250 spillere på 4 klustre kunne spille komfortabelt uten problemer.
- **Plattformen som viser lys i chunk/entity**\
  Ved å bytte fra Purpur til Plazma på en overlevelsesserver der det oppsto forsinkelser i behandlingen av chunk og entity, kunne de redusere de fleste forsinkelsene.
- **Valgt av mange streamere**\
  Brukes av mange streamers seerfellesskap som en foretrukket bøtte.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Sanntid Plazma brukertrender</p></figcaption>
</figure>

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
