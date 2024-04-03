---
description: Ismerd meg, hogyan személyre szabhatod a szerveredet.
---

# 🎨 Felhasználói testreszabás

Azért használják a módosított szerverplatformot, például a Plazmát, és nem a Mojang Studios által biztosított hivatalos szerverplatformot, mert a legnagyobb előnye az erős felhasználói **testreszabhatóság** lehetősége.

Az alábbiakban látható néhány módja annak, hogyan lehet testreszabni és kihasználni a Plazmát.

## Konfiguráció módosítása <a href="#id-1" id="id-1"></a>

A Plazma testreszabásának leg alapvetőbb módja az, hogy módosítjuk a konfigurációt.

A Plazma erős konfigurációs beállításokat kínál a játék mechanizmusaitól az entitások tulajdonságaiig.

A Plazma konfigurációjával kapcsolatos részletekért tekintse meg az alábbi oldalt.

{% content-ref url="../reference/configurations/" %}
[konfigurációk](../reference/configurations/)
{% endcontent-ref %}

## Bővítmények használata <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma támogatja az összes Papír alapú bővítményt.**

A Spigot bővítmények esetében a 1.20.5-től kezdve a Papír térképezési változása miatt néhány nem működhet megfelelően,
Azonban a Papír, Pufferfish és Purpur alapú bővítmények többsége a Plazmában is megfelelően működik,
Ha valamelyik nem működik megfelelően, az a Plazma hibája, ezért kérjük, azonnal [jelentse be.](../diagnosis/plugins.md)

{% endhint %}

A Plazma használatának fő oka és egyben a Plazma testreszabásának legerősebb módja.
A Plazma erős bővítmény ökoszisztémája lehetővé teszi a szerver könnyű testreszabását.

Számos módszer létezik a bővítmények keresésére és letöltésére. Néhány bővítményt
nyilvános tárolószolgáltatásokra töltik fel, míg másokat a GitHub-on vagy saját
webhelyükön töltenek fel.

{% hint style="caution" %}

**A bővítmények közvetlen hozzáférést biztosítanak a rendszerhez!**

Mindig ellenőrizze a bővítmény biztonságát a VirusTotal és hasonló szolgáltatásokkal, mielőtt alkalmazná,
vagy megbízható forrásból töltse le a bővítményt.

{% endhint %}

Számos szolgáltatás létezik a bővítmények letöltésére. Ezek közül a [SpigotMC Fórum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) és más szolgáltatások a bővítmények feltöltése előtt ellenőrzést végeznek, és az biztonságtalan bővítményeket azonnal kezelik, hogy csak biztonságos bővítmények legyenek forgalomban.

### Bővítmény alkalmazása <a href="#id-2.1" id="id-2.1"></a>

Ha letöltötte a bővítményt, most alkalmazhatja azt.

1. A bővítmények `.jar` vagy `Java végrehajtható fájl` formátumban vannak.\
   Néhány bővítmény tömörített fájlként van jelen, ilyen esetekben
   csomagolja ki, és ha a név tartalmazza a `bukkit`, `spigot` vagy `paper` szót,
   akkor a `fat` fájlt használja.
2. Helyezze át a letöltött fájlt a szerver mappájában található `plugins` mappába, majd indítsa újra a szervert.
3. Amikor a Plazma elindul, új tartalom jelenik meg a konzolon.
   Ez azt jelenti, hogy a Plazma sikeresen betöltötte a bővítményeket.
4. Még ha a Plazma sikeresen betöltötte a bővítményeket, előfordulhat, hogy nem sikerült elindítani azokat.
   A `/plugins` parancs segítségével lekérdezheti a jelenleg betöltött bővítményeket a szerveren.
   Ha a telepített bővítmények neve nem
   vörös, hanem
   zöld, az azt jelenti, hogy a bővítmények sikeresen betöltöttek.

Ha a bővítmények nem töltődtek be megfelelően, az alábbi oldalon találhat megoldásokat a problémákra.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Adatcsomag használata <a href="#id-3" id="id-3"></a>

Az adatcsomagok a Minecraft által alapértelmezett módon biztosított testreszabási lehetőségek, hasonlóan a [erőforrás csomagokhoz](#user-content-fn-1)[^1].

Az adatcsomagok lehetővé teszik új entitások és kihívások hozzáadását, valamint más játékbeli elemek módosítását.

{% hint style="caution" %}

**Az adatcsomagok károsíthatják a világot!**

Néhány hibás adatcsomag károsíthatja a világot, és ez visszafordíthatatlan.

Ezért ajánlott a világ biztonsági mentése az adatcsomagok alkalmazása előtt.

{% endhint %}

Az adatcsomagokat számos szolgáltatásról letöltheti, mint például a [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) és más szolgáltatások.

Ha letöltötte az adatcsomagot, helyezze azt a szerver világ mappájában található `datapacks` mappába az alkalmazáshoz.
Ha a mappa nem létezik, hozzon létre egyet az adatcsomagok hozzáadásához.

{% hint style="warning" %}

**Néhány [adatcsomag](#user-content-fn-2)[^2] esetén az első alkalmazás nem biztos, hogy sikeres lesz.**

Ebben az esetben ajánlott **2 alkalommal** újraindítani a szervert.

{% endhint %}

Az adatcsomagok könnyen megsérülhetnek a Minecraft frissítésekor.

Különösen, ha az adatcsomag teljesen megsérült, a szerver összeomolhat,
éppen ezért fontos a szerver frissítése előtt alaposan tesztelni.

{% hint style="info" %}

**A szerver indítóparancs után írja be a `safeMode` parancsot, hogy az összes adatcsomagot kikapcsolja, majd indítsa újra a szervert.**

[További információkért lásd a `Referencia > Argumentumok` részt.](../reference/arguments.md)

{% endhint %}

Az alkalmazott adatcsomagokat a `/datapack list` parancs segítségével ellenőrizheti.

***

[^1]: Vagy a Minecraft: Bedrock kiadásának kiegészítője.

[^2]: Entitások hozzáadása stb.
