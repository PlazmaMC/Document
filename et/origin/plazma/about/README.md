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

1. **Tugev plugin-ökosüsteem**\
   [Paber](https://github.com/PaperMC/Paper) põhineb,
   seega enamikul internetist allalaaditavatest [uusimatest plugin-dest](#user-content-fn-1)[^1] on normaalne toimimine.
2. **Optimeerimist pole vaja seadistada**\
   Kõik [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) parandused on kaasas,
   mõned sisemised optimeerimised ja moodulid tagavad parima jõudluse.
3. **Mäng, mida saate kohandada soovitud viisil**\
   Plazmas sisalduv [Purpur](https://github.com/PurpurMC/Purpur) võimaldab teil muuta
   mängu üldisi omadusi vastavalt soovile.
4. **Turvaline serverimängimine**\
   Sisaldab [Mingi jutu raporteid](https://github.com/Aizistral-Studios/No-Chat-Reports) alates 1.19-st,
   [Mojangi](#user-content-fn-2)[^2] [vestluse raporteerimise süsteem](#user-content-fn-3)[^3] saab keelata,\
   diagnostikaandur on täielikult eemaldatud, võimaldades mängida jälgimata turvalisel serveril.
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

- **Iseseisvalt töötav platvorm, mis suudab korralikult töödelda keerulisi plugin-e**\
  Plazmat kasutatakse arendaja [IPECTER](https://github.com/IPECTER) serveris.\
  NMS ja peegeldusel põhinevad enda pluginad, keerulised ja mahukad andmepakid on laialdaselt rakendatud,\
  ning see võtab vastu üle 100 mängija ilma jõudluseta.
- **RPG-serveris säilitatakse kiire jõudlus**\
  Ühe klasteriga hoiti 100 mängijat stabiilselt ilma TPS-i languseta ning\
  4 klasteriga sai kokku 250 mängijat mängida sujuvalt.
- **Platvorm, mis näitab valgust tükkides/üksustes**\
  Muutes varasemalt ellujäämisserveris esinevat viivitust tükkide ja üksuste töötlemisel
  Purpuri asemel Plazmaks, suudeti vähendada enamikku viivitusi.
- **Paljude voogude valitud platvorm**\
  Paljud voogedastajad on valinud kasutada seda ämbrina oma vaatajate jaoks.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Reaalajas Plazma kasutajate suundumused</p></figcaption>
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
