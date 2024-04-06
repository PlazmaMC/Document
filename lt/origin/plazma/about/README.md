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

1. **Galingas įskiepių ekosistema**\
   [Paper](https://github.com/PaperMC/Paper) pagrįstas,
   Dauguma [naujausių įskiepių](#user-content-fn-1)[^1] internete yra veikiantys.
2. **Nereikia jokių nustatymų, optimizavimas**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) visi patobulinimai yra įtraukti,
   Yra keletas vidinių optimizavimų ir modulių, kurie užtikrina geriausią veikimą.
3. **Žaidimas, kurį galite pritaikyti pagal savo norus**\
   [Purpur](https://github.com/PurpurMC/Purpur) Plazmoje leidžia koreguoti žaidimo bendruosius nustatymus.
4. **Saugus serveris žaidimui**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) yra įtrauktas, leidžiantis išjungti [Mojang](#user-content-fn-2)[^2] pridėtą [pranešimų apie pokalbius sistemą](#user-content-fn-3)[^3] nuo 1.19 versijos,
   Pašalinamas diagnostikos informacijos rinkiklis, todėl galite saugiai žaisti serveryje be stebėjimo.
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
  Plazma naudojama kūrėjo [IPECTER](https://github.com/IPECTER) serveryje.
  Naudodama NMS ir refleksiją veikiantys vidiniai įskiepiai, sudėtingi ir dideli duomenų paketai yra labai dažni,
  Ir vis tiek gali priimti daugiau nei 100 žaidėjų be veikimo mažėjimo.
- **Greitai veikianti platforma net RPG serveriuose**\
  Vienoje klasterio vietoje stabiliai išlaikė 100 žaidėjų be TPS mažėjimo, o
  4 klasteriuose iš viso 250 žaidėjų galėjo žaisti patogiai.
- **Platforma, kuri leidžia matyti šviesą iš chunk/entiteto**\
  Keičiant iš Purpur į Plazma, buvo sumažintas didžioji dalis vėlavimų, kurie atsirado tvarkant chunk'us ir entitetus ant iki šiol buvusio vėlavimų turinčio išlikimo serverio platformos.
- **Daugelio transliuotojų pasirinkta platforma**\
  Daugelis transliuotojų ir jų žiūrovų buvo pasirinkę naudoti šį kibirą.

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
