---
description: Ismerd meg, hogyan személyre szabhatod a szerveredet.
---

# 📶 Fejlődni

Azért használják a módosított szerverplatformot, például a Plazmát, és nem a Mojang Studios által biztosított hivatalos szerverplatformot, mert a legnagyobb előnye az erős felhasználói **testreszabhatóság** lehetősége.

Az alábbiakban látható néhány módja annak, hogyan lehet testreszabni és kihasználni a Plazmát.

## Konfiguráció módosítása <a href="#id-1" id="id-1"></a>

A Plazma testreszabásának leg alapvetőbb módja az, hogy módosítjuk a konfigurációt.

A Plazma erős konfigurációs beállításokat kínál a játék mechanizmusaitól az entitások tulajdonságaiig.

A Plazma konfigurációjával kapcsolatos részletekért tekintse meg az alábbi oldalt.

{% content-ref url="../reference/configurations/" %}
[konfigurációk](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**[Bizonyos adatcsomagok](#user-content-fn-2)[^2] esetén az első alkalmazás során nem biztos, hogy megfelelően alkalmazzák.**

Ebben az esetben ajánlott **2 alkalommal** újraindítani a szervert.

{% endhint %}

Az adatcsomagok könnyen megsérülhetnek a Minecraft frissítésekor.

Különösen, ha az adatcsomag teljesen megsérült, a szerver összeomolhat,
éppen ezért fontos a szerver frissítése előtt alaposan tesztelni.

{% hint style="info" %}

**A szerver indítóparancs után írja be a `safeMode` parancsot, hogy az összes adatcsomagot kikapcsolja, majd indítsa újra a szervert.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safemode)

{% endhint %}

Az alkalmazott adatcsomagokat a `/datapack list` parancs segítségével ellenőrizheti.

***

## Optimalizálás <a href="#id-4" id="id-4"></a>

A Plazmában sok optimalizálási javítás van. 또한, Plazma가 처음으로 시작되면 자동으로
구성을 최적화 하므로 [시작하기](./README.md) 설명서를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우,
아래 설명서를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

A proxy összeköti a szervereket, lehetővé teszi a játékosok számára, hogy további munka nélkül mozogjanak a szerverek között, illetve kommunikáljanak más szerverekkel.

További információk a biztonságos és helyes proxy beállításokról az alábbi oldalon találhatók.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Biztonság <a href="#id-5" id="id-5"></a>

A Minecraftban a modok fejlődése miatt könnyen elérhetővé válnak az [exploit motorok](#user-content-fn-3)[^3] online is.

Bár a legtöbb játékban a legtöbb exploit alapértelmezés szerint blokkolva van, az exploitok használata azon keresztül harmadik féltől származó betöltőkön keresztül nem blokkolt.

Ezért ha a szerver nyilvános, javasolt az anti-cheat bővítmények telepítése az exploitok használatának megakadályozására, valamint a proxy és az automatikus újraindítás, biztonsági mentés stb. konfigurálása, hogy a szerver leállása esetén gyorsan helyre lehessen állítani.

### Jogosultság beállítás <a href="#id-5.1" id="id-5.1"></a>

Néhány plugin admin parancsának megfelelő jogosultság nélkül is létezhetnek biztonsági rések.

Az ilyeneket korlátozni javasolt a [LuckPerms](https://luckperms.net/) vagy hasonló jogosultságkezelő pluginok használatával.

### X-Ray blokkolás <a href="#id-5.2" id="id-5.2"></a>

Az X-Ray az alapvető optimalizálási kliensben könnyen használható egyik exploit.

A Plazmában alapvetően blokkolható az X-Ray használata.

Az X-Ray blokkolásának módjáról és leírásáról az alábbi oldalon talál részletes információt.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

Ha csak bizonyos felhasználók férhetnek hozzá a szerverhez, akkor ajánlott a [Ngrok](./README.md#id-6.2) használata a [titkosított szerver cím](#user-content-fn-5)[^5] vagy whitelist beállítása más játékosok kizárására.

A szerver konzolján keresztül `/whitelist add <player>` paranccsal engedélyezheted a játékos csatlakozását, illetve `/whitelist remove <player>` paranccsal újra megtilthatod a csatlakozását.

A whitelist-re engedélyezett játékosok listájának megtekintéséhez használd a `/whitelist query` parancsot.

***

[^1]: Vagy a Minecraft: Bedrock kiadásának kiegészítője.

[^2]: Entitások hozzáadása stb.

[^3]: Általában "hack"-ként említik.

[^4]: Ha a konfiguráció nincs optimalizálva, vagy a Plazma elavult, vagy újonnan felfedezett exploitok vannak, előfordulhat, hogy nem blokkolódnak.

[^5]: A játékosok a Ngrok proxy szerveren keresztül csatlakoznak a szerverhez, és minden újraindításkor kiosztott Ngrok cím más lesz.
