---
description: Sužinokite, kas yra Plazma serverio platforma.
---

# ❓ Kas yra Plazma?

- **Plazma** yra [Andromeda](https://github.com/EarendelArchived/Andromeda) ir [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) privalumus paveldėjęs [Paper](https://github.com/PaperMC/Paper) pagrindu veikianti serverio platforma.
- Visada stengiamės užtikrinti aukštą stabilumą, galingą veikimą, greitas atnaujinimo, taip pat suteikti daugybę funkcijų.

## 📋 Plazmos tikslas <a href="#id-1" id="id-1"></a>

- Stengiamės tapti serverio platforma su greitais atnaujinimais ir aukštu stabilumu.
- Stengiamės suteikti galingą veikimą ir daugybę funkcijų, panašių į modų platformą.
- Stengiamės sukurti laisvą platformą, kuri leistų pritaikyti net ir vanilinius patobulinimus.

## ⚙️ Svarbiausios funkcijos <a href="#id-2" id="id-2"></a>

1. **Galinga įskiepių ekosistema**\
   Remiantis [Paper](https://github.com/PaperMC/Paper), dauguma [naujausių įskiepių](#user-content-fn-1)[^1], kuriuos galima atsisiųsti iš interneto, veikia sklandžiai.
2. **Nereikalingų nustatymų optimizavimas**\
   Visi [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) patobulinimai yra įtraukti, o kai kurie patys optimizavimai ir modifikacijos užtikrina geriausią veikimą.
3. **Žaidimą galite pritaikyti pagal savo poreikius**\
   [Purpur](https://github.com/PurpurMC/Purpur), įtrauktas į Plazmą, leidžia redaguoti žaidimo bendruosius požymius.
4. **Saugus žaidimas serveriuose**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) yra įtrauktas, pradedant nuo 1.19, galite išjungti [Mojang](#user-content-fn-2)[^2] pridėtą [pranešimų apie pokalbius sistemą](#user-content-fn-3)[^3], ir visiškai pašalinti diagnostikos informacijos rinkiklį, leidžiantį žaisti saugiai be sekimo serveriuose.
5. **Greitieji atnaujinimai**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) užtikrina, kad Plazmos įtraukti patobulinimai visada būtų naujausi, siūlantys greičiausius atnaujinimus iš visų ant Paper pagrįstų serverių platformų.
6. **Numatyti konfigūracijos failai**\
   Numatytieji konfigūracijos failai jau optimizuoti, todėl jums nereikia jų patys optimizuoti.
7. **Sistemiškai veikiantis daugiagijų tvarkytis**\
   Asinchronizuojant mechanizmus, kurie nėra susiję su žaidimo mechanizmais, sumažinamas [delstumo laikas](#user-content-fn-4)[^4], optimizuojant serverį.
8. **Nenaudojamų vietų blokavimas**\
   Visus duomenis, turinčius panašius reikšmes, sujungiame į vieną, mažindami naudojamą atmintį.

#### Norite sužinoti daugiau apie Plazmą? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Panaudojimo atvejai <a href="#id-3" id="id-3"></a>

- **Platforma, kuri tinkamai tvarko sudėtingus įskiepius**\
  Plazma naudojama plėtojant programuotojo [IPECTER](https://github.com/IPECTER) serverius. Nors yra patys kurti įskiepiai, veikiantys su NMS ir refleksija, taip pat yra gausūs ir dideli duomenų rinkiniai, serveris gali priimti daugiau nei 100 žaidėjų be jokio veikimo sulėtėjimo.
- **RPG serveris su puikiu veikimu**\
  100 žaidėjų viename klasterio be TPS kritimo ir stabiliai veikiantis, taip pat 4 klasteriai, kuriuose iš viso 250 žaidėjų gali žaisti patogiai.
- **Platforma, kuri rodo šviesą iš chunk/entitetai**\
  Pakeitus serverio platformą nuo Purpur iki Plazma, buvo sumažintas didžioji dalis delsimo, kuris buvo susijęs su chunk ir entitetai tvarkymu serveryje.
- **Daugelio transliuotojų pasirinkta platforma**\
  Daugelis žinomų transliuotojų naudoja Plazmą savo žiūrovams skirtuose bucket serveriuose.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Realaus laiko Plazmos naudotojų tendencija</p></figcaption>
</figure>

## ⬇️ Parsisiųsti

Plazmą galite parsisiųsti iš apačioje pateikto puslapio.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Norite sužinoti daugiau apie palaikomas versijas?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot įskiepiai ir Paper, Pufferfish, Purpur įskiepiai.

[^2]: Priklauso nuo Microsoft Corporation.

[^3]: Išjungus pokalbių pranešimų sistemą, pokalbiai bus tvarkomi tik serveryje, neleisdami Mojang pokalbių sekimo.

[^4]: Laikas, kuriuo veikia sisteminis mechanizmas, ir žaidimas trumpam sustoja.
