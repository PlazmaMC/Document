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
   A [Paper](https://github.com/PaperMC/Paper) alapján működik, így az internetről letölthető legtöbb [legújabb bővítmény](#user-content-fn-1)[^1] normálisan működik.
2. **Beállítás nélküli optimalizálás**\
   Minden [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) patch benne van, és néhány saját optimalizálást és módosítást tartalmaz, így kiváló teljesítményt nyújt.
3. **A játékot saját igényei szerint testreszabó platform**\
   A Plazmában található [Purpur](https://github.com/PurpurMC/Purpur) lehetővé teszi a játék általános tulajdonságainak módosítását.
4. **Biztonságos szerverjáték**\
   Tartalmazza a [Nincs Csevegési Jelentés](https://github.com/Aizistral-Studios/No-Chat-Reports) funkciót, amely lehetővé teszi a Mojang[^2] 1.19-tól bevezetett [csevegési jelentési rendszer](#user-content-fn-3)[^3] kikapcsolását, valamint teljesen eltávolítja a diagnosztikai adatgyűjtőt, így nyomkövetés nélküli biztonságos szerveren játszhat.
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

- **Még a bonyolult bővítményeket is helyesen kezelő platform**\
  Az [IPECTER](https://github.com/IPECTER) fejlesztő a szerverén használja a Plazmát. Saját bővítmények, amelyek NMS és reflexióval működnek, valamint bonyolult és nagyméretű adatcsomagokat alkalmaznak, mégis képesek több mint 100 játékost fogadni anélkül, hogy a teljesítmény csökkenne.
- **RPG szervereken is fenntartott gyors teljesítményű platform**\
  Egyetlen klaszteren belül több mint 100 játékost képes stabilan fenntartani TPS csökkenés nélkül, és 4 klaszteren összesen 250 játékos kényelmesen játszhat.
- **Fényt mutató platform a chunkokban/entitásokban**\
  A Purpurról a Plazmára történő áttéréssel jelentősen csökkenthetők a késések a túlélő szervereknél, amelyek a chunkokat és entitásokat kezelték.
- **Sok streamer által választott platform**\
  Sok népszerű streamer a Plazmát választotta a nézői számára, mint a Buckets.

<figure><img src="https://camo.githubusercontent.com/22acffd515755c2cee2078a7697ff35351c5ec7148eb2806deedbe63df1c4ed7/68747470733a2f2f6273746174732e6f72672f7369676e6174757265732f7365727665722d696d706c656d656e746174696f6e2f506c617a6d612e737667" alt=""><figcaption><p>Valós idejű Plazma felhasználói trendek</p></figcaption></figure>

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
