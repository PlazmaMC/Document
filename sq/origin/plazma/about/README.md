---
description: Mësoni më shumë për platformën e serverit Plazma.
---

# ❓ Çfarë është Plazma?

- **Plazma** është një platformë serveri bazuar në [Paper](https://github.com/PaperMC/Paper) që merr vetëm avantazhet nga [Andromeda](https://github.com/EarendelArchived/Andromeda) dhe [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Duke punuar për të siguruar gjithmonë stabilitet të lartë, performancë të fuqishme, përditësime të shpejta dhe një gamë të gjerë funksionalitetesh.

## 📋 Synimi i Plazma <a href="#id-1" id="id-1"></a>

- Duke punuar për të bërë platformën e serverit me përditësime të shpejta dhe stabilitet të lartë.
- Duke punuar për të ofruar një gamë të gjerë funksionalitetesh dhe performancë të fuqishme, si platforma e modit.
- Duke punuar për të krijuar një platformë të lirë që mund të përshtatet sipas patch-ave të Vanilla.

## ⚙️ Pika kryesore <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Përditësimi më i shpejtë**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) siguron që patch-et e përfshira në Plazma gjithmonë mbeten të përditësuara, duke ofruar një nga përditësimet më të shpejta në platformën e serverit të bazuar në Paper.
6. **Optimizimi i konfigurimit fillestar**\
   Konfiguracionet fillestare janë të optimizuara, duke ju kursyer nevojën për të optimizuar manualisht konfiguracionet.
7. **Funksionimi i organizuar me shumë threada**\
   Sistemi i përdorur për mekanizmat që nuk kanë lidhje me lojën është asinkron, duke zvogëluar kohën e vonuar dhe duke optimizuar serverin.
8. **Bllokimi i përdorimit të hapësirës së panevojshme**\
   Të dhënat me vlera të ngjashme janë të bashkuara për të zvogëluar përdorimin e memorjes.

## ✨ Rastet e përdorimit <a href="#id-3" id="id-3"></a>

- **Platforma që trajton shtojcat e komplikuara në mënyrë të saktë**\
  Plazma është e përdorur në serverin e [IPECTER](https://github.com/IPECTER) të zhvilluesit.\
  Me shtojcat e veta që funksionojnë me NMS dhe reflektim, dhe me një numër të madh të paketave të dhënash komplekse dhe të mëdha,\
  ëndërsa pranon më shumë se 100 lojtarë pa rënien e performancës.
- **Platforma që mbajti performancën e shpejtë edhe në serverët RPG**\
  Në një klaster të vetëm, 100 lojtarë janë mbajtur në mënyrë stabile pa rënien e TPS,\
  në 4 klasterë, një total prej 250 lojtarëve kanë luajtur në një mënyrë të këndshme.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Platforma e zgjedhur nga shumë transmetues**\
  Është zgjedhur si një ndërrues pjesëmarrësish nga shumë transmetues.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Shkarko

Në faqen më poshtë mund të shkarkoni Plazma.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Dëshironi të merrni informacione të detajuara për mbështetjen e versioneve?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Shtojcat e Bukkit, CraftBukkit, Spigot dhe Paper, Pufferfish, Purpur.

[^2]: Microsoft Corporation.

[^3]: Nëse deaktivizohet sistemi i raportimit të bisedave, biseda përpunohet vetëm në server duke parandaluar gjurmimin e bisedave nga Mojang.

[^4]: Koha kur loja ndalet për një moment për të lejuar funksionimin e mekanizmave të sistemit.
