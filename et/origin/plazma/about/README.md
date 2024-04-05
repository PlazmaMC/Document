---
description: Uurige, milline platvorm Plazma on.
---

# ❓ Mis on Plazma?

- **Plazma** on [Andromeda](https://github.com/EarendelArchived/Andromeda) ja [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) eelistega [Paper](https://github.com/PaperMC/Paper) platvormil põhinev serveri platvorm.
- Pakume pidevat stabiilsust ja võimsust, kiiret uuendamist ning ulatuslikke funktsioone.

## 📋 Plazma eesmärk <a href="#id-1" id="id-1"></a>

- Püüame saavutada kiiret uuendamist ja stabiilset serveri platvormi.
- Püüame pakkuda ulatuslikke funktsioone ja võimsust, mis ei jää maha moodi platvormist.
- Püüame luua vaba platvormi, mis võimaldab kohandada ka vanilje parandusi.

## ⚙️ Peamised funktsioonid <a href="#id-2" id="id-2"></a>

1. **Võimas pistikprogrammide ökosüsteem**\
   Põhineb [Paper](https://github.com/PaperMC/Paper) platvormil, mis võimaldab enamiku [uusimatest pistikprogrammidest](#user-content-fn-1)[^1] internetist alla laadida ja korralikult toimida.
2. **Optimeerimist ei nõua**\
   Sisaldab kõiki [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) parandusi ja mõningaid sisseehitatud optimeerimisi ja mooduleid, et pakkuda parimat jõudlust.
3. **Mäng, mida saate kohandada**\
   Kaasasolev [Purpur](https://github.com/PurpurMC/Purpur) võimaldab teil muuta mängu üldisi omadusi.
4. **Turvaline serverimäng**\
   Sisaldab [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports), mis võimaldab teil keelata Mojangi [vestluse raporteerimise süsteemi](#user-content-fn-3)[^3] alates 1.19-st, eemaldades täielikult diagnostika koguja ja mängides jälgimata turvalisel serveril.
5. **Kõige kiiremad uuendused**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) hoiab Plazma kaasas olevad parandused alati ajakohasena, pakkudes kõige kiiremaid uuendusi Paperil põhinevate serveri platvormide hulgas.
6. **Vaikimisi konfiguratsioonifaili optimeerimine**\
   Vaikimisi rakendatud konfiguratsioonifail on optimeeritud, nii et te ei pea seda ise optimeerima.
7. **Süsteemselt toimiv mitmekeerneline**\
   Asünkroniseerib süsteemi mehhanismid, mis ei ole seotud mängu mehhanismidega, et optimeerida serverit ja vähendada [viivitusi](#user-content-fn-4)[^4].
8. **Tarbetu ruumi kasutamise blokeerimine**\
   Ühendab sarnase väärtusega andmed ühte, et vähendada mälukasutust.

#### Kui soovite rohkem teada saada Plazma kohta? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Kasutusjuhud <a href="#id-3" id="id-3"></a>

- **Platvorm, mis suudab korralikult töödelda keerulisi pistikprogramme**\
  Plazmat kasutatakse arendaja [IPECTER](https://github.com/IPECTER) serveris. NMS ja peegeldusega töötav oma pistikprogramm, mis sisaldab palju keerukaid ja mahukaid andmepakette, suudab vastu võtta üle 100 mängija ilma jõudluseta.
- **RPG serveris säilitab kiire jõudluse platvorm**\
  Ühe klasterina suutis säilitada 100 mängijat ilma TPS-i languseta ning 4 klasteris kokku 250 mängijat said mängida sujuvalt.
- **Chunk/Entity valgust näitav platvorm**\
  Purpurist Plazmaks muutudes suutsime vähendada enamiku viivitusi, mis tulenesid varasemast Survival serveri platvormist chunkide ja entityde töötlemisel.
- **Paljude voogedastajate valitud platvorm**\
  Paljud populaarsed voogedastajad kasutavad Plazmat oma vaatajaskonna jaoks.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>실시간 Plazma 사용자 추이</p></figcaption>
</figure>

## ⬇️ Lae alla

Allpool saate alla laadida Plazma.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Kui soovite rohkem teada versioonide toetamise kohta?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot pistikprogrammid ja Paper, Pufferfish, Purpur pistikprogrammid.

[^2]: Allpool Microsoft Corporation.

[^3]: Kui deaktiveerite vestluse raporteerimise süsteemi, töödeldakse vestlusi täielikult serveris, takistades Mojangi vestluste jälgimist.

[^4]: Süsteemi mehhanismi toimimiseks peab mäng mõneks ajaks peatuma.
