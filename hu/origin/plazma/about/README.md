---
description: Ismerje meg, hogy mi is pontosan a Plazma szerver platform.
---

# ❓ Mi az a Plazma?

- **Plazma** a [Andromeda](https://github.com/EarendelArchived/Andromeda) és a [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) előnyeit hozza csak a [Paper](https://github.com/PaperMC/Paper) alapján létrehozott szerver platformról.
- Mindig igyekszünk magas stabilitást, erős teljesítményt, gyors frissítéseket és bőséges funkciókat nyújtani.

## 📋 A Plazma célja <a href="#id-1" id="id-1"></a>

- Azért dolgozunk, hogy olyan szerver platform legyünk, amely gyors frissítéseket és magas stabilitást nyújt.
- Azért dolgozunk, hogy bőséges funkciókat és erős teljesítményt nyújtsunk, ami nem marad el a mod platformoktól.
- Azért dolgozunk, hogy olyan szabad platformot hozzunk létre, amelyen a Vanilla patcheket is testreszabhatja.

## ⚙️ Főbb jellemzők <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Leggyorsabb frissítések**\
   [A Mindig Naprakész](https://github.com/PlazmaMC/AlwaysUpToDate) lehetővé teszi, hogy a Plazma beépített patch-ei mindig naprakészek legyenek, így a Paper alapú szerver platformok közül a leggyorsabb frissítéseket nyújtja.
6. **Alapvető konfigurációs fájl optimalizálás**\
   Az alapértelmezett konfigurációs fájlok optimalizáltak, így nem kell közvetlenül optimalizálnia a konfigurációs fájlokat.
7. **Rendszeratlagosan működő többszál**\
   Az olyan rendszermechanizmusokat, amelyek nem kapcsolódnak a játék mechanizmusaihoz, aszinkronizáljuk, hogy optimalizáljuk a szerver teljesítményét és csökkentsük a [késleltetési időt](#user-content-fn-4)[^4].
8. **Felesleges helyhasználat blokkolása**\
   Az azonos értékű adatokat egyesítjük, hogy csökkentsük a memóriahasználatot.

## ✨ Használati esetek <a href="#id-3" id="id-3"></a>

- **Az összetett bővítményeket is megfelelően kezelő platform**\
  [IPECTER fejlesztő](https://github.com/IPECTER) szerverén a Plazma van használva.\
  Saját bővítmény, amely NMS és reflexióval működik, valamint bonyolult és nagy adatcsomagokat alkalmaz,\
  100 főnél több játékost is fogad anélkül, hogy a teljesítmény csökkenne.
- **Az RPG szerveren is gyors teljesítményt biztosító platform**\
  Egyetlen klaszterben 100 játékost sikerült stabilan fenntartani TPS csökkenés nélkül,\
  4 klaszterben összesen 250 játékos kellemesen játszhatott.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Sok streamer által választott platform**\
  Sok streamer nézői részvételi vödörként választotta és használja.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Letöltés

A Plazmát letöltheti az alábbi oldalról.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Ha részletes információkat szeretne a támogatott verziókról, látogasson el ide:

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot bővítmények és Paper, Pufferfish, Purpur bővítmények.

[^2]: Microsoft Corporation.

[^3]: Ha kikapcsolja a csevegési jelentési rendszert, a csevegés csak a szerveren lesz feldolgozva, és megakadályozhatja a Mojang csevegési nyomkövetését.

[^4]: Azért, hogy a rendszermechanizmus működjön, a játék egy rövid ideig leáll.
