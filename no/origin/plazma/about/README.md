---
description: Plazma는 어떤 서버 플랫폼인지 알아보세요.
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
   Basert på [Paper](https://github.com/PaperMC/Paper), slik at de fleste [nyeste pluginene](#user-content-fn-1)[^1] som er tilgjengelige på internett, fungerer som de skal.
2. **Ingen konfigurasjonsoptimalisering nødvendig**\
   Inneholder alle patchene fra [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) og har noen interne optimaliseringer og modder for å gi den beste ytelsen.
3. **Tilpass spillet slik du vil**\
   [Purpur](https://github.com/PurpurMC/Purpur) som er inkludert i Plazma, lar deg endre spillets generelle egenskaper.
4. **Spill på en sikker server**\
   Inkluderer [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports), som lar deg deaktivere Mojangs[^2] [chat report system](#user-content-fn-3)[^3] som ble lagt til fra 1.19, og diagnostikkverktøyet er helt fjernet slik at du kan spille på en trygg server uten sporing.
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

- **En plattform som håndterer selv komplekse plugins riktig**\
  Plazma brukes på serveren til utvikleren [IPECTER](https://github.com/IPECTER). Med egne plugins som fungerer med NMS og refleksjon, og en stor mengde datapakker, kan den håndtere over 100 spillere uten ytelsesproblemer.
- **En plattform med rask ytelse selv på RPG-servere**\
  Har holdt 100 spillere på en enkelt klynge stabil uten TPS-fall, og på 4 klynger kunne 250 spillere spille jevnt.
- **En plattform som lyser i chunk/entity-behandling**\
  Ved å bytte fra Purpur til Plazma på en overlevelsesserver som tidligere hadde forsinkelser i chunk- og entity-behandling, kunne de redusere de fleste forsinkelsene.
- **Valgt av mange streamere**\
  Brukes av mange populære streamere som deres foretrukne serverbucket.

<figure><img src="https://camo.githubusercontent.com/22acffd515755c2cee2078a7697ff35351c5ec7148eb2806deedbe63df1c4ed7/68747470733a2f2f6273746174732e6f72672f7369676e6174757265732f7365727665722d696d706c656d656e746174696f6e2f506c617a6d612e737667" alt=""><figcaption><p>Sanntidsbrukerutvikling for Plazma</p></figcaption></figure>

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
