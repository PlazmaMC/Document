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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Kõige kiiremad uuendused**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) hoiab Plazma kaasas olevad parandused alati ajakohasena, pakkudes kõige kiiremaid uuendusi Paperil põhinevate serveri platvormide hulgas.
6. **Vaikimisi konfiguratsioonifaili optimeerimine**\
   Vaikimisi rakendatud konfiguratsioonifail on optimeeritud, nii et te ei pea seda ise optimeerima.
7. **Süsteemselt toimiv mitmekeerneline**\
   Asünkroniseerib süsteemi mehhanismid, mis ei ole seotud mängu mehhanismidega, et optimeerida serverit ja vähendada [viivitusi](#user-content-fn-4)[^4].
8. **Tarbetu ruumi kasutamise blokeerimine**\
   Ühendab sarnase väärtusega andmed ühte, et vähendada mälukasutust.

## ✨ Kasutusjuhud <a href="#id-3" id="id-3"></a>

- **Iseseisvalt töötav platvorm, mis suudab korralikult töödelda keerulisi plugin-e**\
  Plazmat kasutatakse arendaja [IPECTER](https://github.com/IPECTER) serveris.\
  NMS ja peegeldusel põhinevad enda pluginad, keerulised ja mahukad andmepakid on laialdaselt rakendatud,\
  ning see võtab vastu üle 100 mängija ilma jõudluseta.
- **RPG-serveris säilitatakse kiire jõudlus**\
  Ühe klasteriga hoiti 100 mängijat stabiilselt ilma TPS-i languseta ning\
  4 klasteriga sai kokku 250 mängijat mängida sujuvalt.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Paljud voogedastajad valivad platvormi**\
  Paljud voogedastajad on selle valinud oma vaatajate osalusämbrina.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
