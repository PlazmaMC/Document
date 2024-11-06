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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Greitieji atnaujinimai**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) užtikrina, kad Plazmos įtraukti patobulinimai visada būtų naujausi, siūlantys greičiausius atnaujinimus iš visų ant Paper pagrįstų serverių platformų.
6. **Numatyti konfigūracijos failai**\
   Numatytieji konfigūracijos failai jau optimizuoti, todėl jums nereikia jų patys optimizuoti.
7. **Sistemiškai veikiantis daugiagijų tvarkytis**\
   Asinchronizuojant mechanizmus, kurie nėra susiję su žaidimo mechanizmais, sumažinamas [delstumo laikas](#user-content-fn-4)[^4], optimizuojant serverį.
8. **Nenaudojamų vietų blokavimas**\
   Visus duomenis, turinčius panašius reikšmes, sujungiame į vieną, mažindami naudojamą atmintį.

## ✨ Panaudojimo atvejai <a href="#id-3" id="id-3"></a>

- **Platforma, kuri tinkamai tvarko sudėtingus įskiepius**\
  Plazma naudojama kūrėjo [IPECTER](https://github.com/IPECTER) serveryje.
  Naudodama NMS ir refleksiją veikiantys vidiniai įskiepiai, sudėtingi ir dideli duomenų paketai yra labai dažni,
  Ir vis tiek gali priimti daugiau nei 100 žaidėjų be veikimo mažėjimo.
- **Greitai veikianti platforma net RPG serveriuose**\
  Vienoje klasterio vietoje stabiliai išlaikė 100 žaidėjų be TPS mažėjimo, o
  4 klasteriuose iš viso 250 žaidėjų galėjo žaisti patogiai.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Daugelis srauto platformų pasirinko**\
  Daugelis srauto žmonių žiūrovų dalyvavimo kibirą naudojama ir vertinama.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
