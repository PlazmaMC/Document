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

1. **Erős bővítmény ökoszisztéma**\
   [Paper](https://github.com/PaperMC/Paper) alapú, így
   az internetről letölthető legtöbb [legfrissebb bővítmény](#user-content-fn-1)[^1] megfelelően működik.
2. **Beállítás nélküli optimalizálás**\
   Az összes [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) patch benne van,
   néhány saját optimalizálással és beépített módokkal a legjobb teljesítményt nyújtja.
3. **A játék személyre szabása az Ön igényeinek megfelelően**\
   A [Purpur](https://github.com/PurpurMC/Purpur) a Plazma részeként lehetővé teszi a játék
   általános tulajdonságainak módosítását.
4. **Biztonságosan játszó szerver**\
   [A chat jelentések nélkül](https://github.com/Aizistral-Studios/No-Chat-Reports) a 1.19-től hozzáadott
   [Mojang](#user-content-fn-2)[^2] [chat jelentés rendszerének](#user-content-fn-3)[^3] letiltásával,\
   a diagnosztikai adatgyűjtő teljesen eltávolításával lehetőség van nyomonkövetés nélküli biztonságos szerveren játszani.
5. **Leggyorsabb frissítések**\
   [A Mindig Naprakész](https://github.com/PlazmaMC/AlwaysUpToDate) lehetővé teszi, hogy a Plazma beépített patch-ei mindig naprakészek legyenek, így a Paper alapú szerver platformok közül a leggyorsabb frissítéseket nyújtja.
6. **Alapvető konfigurációs fájl optimalizálás**\
   Az alapértelmezett konfigurációs fájlok optimalizáltak, így nem kell közvetlenül optimalizálnia a konfigurációs fájlokat.
7. **Rendszeratlagosan működő többszál**\
   Az olyan rendszermechanizmusokat, amelyek nem kapcsolódnak a játék mechanizmusaihoz, aszinkronizáljuk, hogy optimalizáljuk a szerver teljesítményét és csökkentsük a [késleltetési időt](#user-content-fn-4)[^4].
8. **Felesleges helyhasználat blokkolása**\
   Az azonos értékű adatokat egyesítjük, hogy csökkentsük a memóriahasználatot.

#### Ha többet szeretne megtudni a Plazmáról, látogasson el a következő oldalra: <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Használati esetek <a href="#id-3" id="id-3"></a>

- **Az összetett bővítményeket is megfelelően kezelő platform**\
  [IPECTER fejlesztő](https://github.com/IPECTER) szerverén a Plazma van használva.\
  Saját bővítmény, amely NMS és reflexióval működik, valamint bonyolult és nagy adatcsomagokat alkalmaz,\
  100 főnél több játékost is fogad anélkül, hogy a teljesítmény csökkenne.
- **Az RPG szerveren is gyors teljesítményt biztosító platform**\
  Egyetlen klaszterben 100 játékost sikerült stabilan fenntartani TPS csökkenés nélkül,\
  4 klaszterben összesen 250 játékos kellemesen játszhatott.
- **Fényt mutató chunk/entity platform**\
  A túlélő szerveren a chunkok és entitások kezelésekor korábban késések jelentkeztek, de a Plazmáról a Purpurra történő váltással sikerült csökkenteni a késéseket.
- **Sok streamer által választott platform**\
  Sok streamer nézőinek körében népszerű Bucketként használják.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Valós idejű Plazma felhasználói trendek</p></figcaption>
</figure>

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
