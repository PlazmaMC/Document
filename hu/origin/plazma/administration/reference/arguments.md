---
description: Ismerje meg a kezdő paramétereket és rendszer tulajdonságait.
---

# 🎛️ Paraméterek és tulajdonságok

A kezdő argumentumok és rendszer tulajdonságok azok az értékek, amelyeket hozzá kell adni a Plazma futtatásához használt parancshoz [fn-1](#user-content-fn-1)[^1], és általánosságban befolyásolják a Plazma működését.

[A **kezdeti argumentumokra** és a **rendszer tulajdonságokra** oszlik az **utasításokhoz hozzáadott helyzet** alapján](#user-content-fn-2)[^2].

***

## Rendszer tulajdonság <a href="#id-1" id="id-1"></a>

A rendszer tulajdonságok az `-jar` előtt kerülnek be azon értékek közé, amelyeket a Plazma inicializálása előtt a JVM kezel.

{% hint style="warning" %}

**A Plazma és a JVM működése módosulhat a rendszer tulajdonságainak módosításával, ami jelentős hatással lehet a játékra!**

Ha nem biztos abban, hogy az egyes rendszer tulajdonságok milyen szerepet töltenek be, **soha ne használja őket!**

{% endhint %}

### Használati útmutató <a href="#id-1.1" id="id-1.1"></a>

A rendszer tulajdonságok a `java` és a `-jar` közötti Java parancsparaméterként kerülnek megadásra.

Például, ha a `Plazma.dummyProperty` rendszer tulajdonságot akarja alkalmazni,
akkor az alábbi módon beírva a következő tulajdonságba `37` kerül, amikor a Plazma inicializálódik.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

A `-D` azt jelzi, hogy ez a paraméter nem a JVM-be van beágyazva, hanem kizárólag a Plazmához hozzáadott saját paraméter.

Ha nem ad meg értéket a tulajdonságoknál, az érték [`true`-ra lesz rögzítve](#user-content-fn-3)[^3].

{% hint style="info" %}

**A Paperweight sorozatú szerver platform mindegyik platformon a tulajdonságok megkülönböztetése érdekében a tulajdonság nevébe `.`-t tartalmaz.**

Néhány terminálban, például a Windows Powershell-ben, lehet, hogy nem fogadja el ezeket az argumentumokat, ezért az argumentumok mindkét végéhez hozzá kell adni a `"` jelet [^4].

{% endhint %}

### Összes rendszer tulajdonság <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a lejárt jelzőtáblák formátumának frissítését.

#### `debug.entities`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Engedélyezi az entitásokhoz kapcsolódó hibakeresési naplókat.

#### `debug.rewriteForIDE`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Az IDE-ben a helyes verzióinformációk betöltéséhez letiltja az NMS átvizsgálást,\
éés automatikusan újra leképezi a belső verzióinformációkat.

#### `disable.watchdog`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a Spigot Watchdog figyelmeztetési rendszerét.

#### `letMeReload`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a `/reload` parancs megerősítő üzenetét.

{% hint style="danger" %}

**A `/reload` parancs nagyon instabil, ezért minden `/reload` használata után felmerülő probléma a felhasználó felelőssége.**

Ha fejlesztő vagy és frissítened kell a bővítményedet, használj inkább hotswapot a `/reload` helyett.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a standard input-output rendszert használó bővítményeket.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Figyelmeztet, ha elavult formázást észlel a csevegés komponensben.

#### `Paper.bypassHostCheck`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a szerverhez való csatlakozáskor a szerver mintázat ellenőrzését.

#### `Paper.debugDynamicMissingKeys`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Engedélyezi a hiányzó kulcsokkal kapcsolatos hibakeresési naplókat az NBT objektumokban.

#### `Paper.debugInvalidSkullProfiles`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Engedélyezi a hibás koponya profilokkal kapcsolatos hibakeresési naplókat.

Ez minden hibás koponya blokkot a világban a helyükkel együtt naplóz.

#### `Paper.disableChannelLimit`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a 128 db [csatorna](#user-content-fn-5)[^5] plugin alkalmazásának korlátozását játékosonként.

#### `Paper.disableClassPrioritization`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a plugin osztály prioritás rendszert.

Hasznos lehet problémák esetén a plugin shade-ben.

#### `Paper.disableFlushConsolidate`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a Netty flush konszolidációs rendszert.

#### `Paper.excessiveTELimit`

- **Forma**: `Integer`
- **Alapértelmezett**: `750`

Ha az entitások száma meghaladja ezt az értéket, több részre osztva küldi el őket.

#### `Paper.filterThreshold`

- **Forma**: `Integer`
- **Alapértelmezett**: `8192`

Beállítja a szerver által egyszerre fogadható maximális csomagméretet.

#### `Paper.ignoreJavaVersion`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Letiltja a Java verzió ellenőrzést.

{% hint style="danger" %}

**Ezzel a módszerrel a JVM hozzáférhet olyan kódrészhez, amely nem létezik!**

Ez állandóan károsíthatja a világ és más fájlokat, és a játék teljes mechanizmusát tönkreteheti.

Minden ebből eredő problémáért Ön a felelős, és a Plamza nem nyújt támogatást ezzel kapcsolatban.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Forma**: `Integer`
- **Alapértelmezett**: `64`

A plugin [csatorna](#user-content-fn-6)[^6] nevének korlátozását állítja be.

#### `Paper.maxSignLength`

- **Forma**: `Integer`
- **Alapértelmezett**: `80`

Beállítja a táblák egy sorára írható maximális karakterhosszt.

#### `Paper.minPrecachedDatafixVersion`

- **Forma**: `Integer`
- **Alapértelmezett**: `(világ verzió) + 1`

Beállítja az inicializálandó világfrissítési információ verzióját.

Hasznos lehet nagy mennyiségű chunk frissítésekor, de egyéb esetekben nem használatos.

#### `Paper.parseYamlCommentsByDefault`

- **Forma**: `Boolean`
- **Alapértelmezett**: `True`

Engedélyezi a YAML fájlok kommentjeinek feldolgozását.

#### `Paper.playerConnection.keepAlive`

- **Forma**: `Integer`
- **Alapértelmezett**: `30`

Ha a játékostól a megadott idő (másodperc) alatt nincs adatátvitel, akkor a játékost kirakja.

Általában a [játék](#user-content-fn-7)[^7] folyamatosan küld [szívverés jeleket](#user-content-fn-8)[^8] a szerverre, így nem lesz [kikapcsolva, de](#user-content-fn-9)[^9] ha a játék nem válaszol, összeütközésnek tekinti és többé nem kezeli a játékost a szerveren, hanem kirúgja.

#### `Paper.skipServerPropertiesComments`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

A szerver tulajdonságok kommentjeit figyelmen kívül hagyja.

#### `Paper.debug-sync-loads`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Engedélyezi a szinkron chunk írásának hibakeresési naplóit.

#### `Paper.enable-sync-chunk-writes`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Engedélyezi a Minecraft [alapértelmezett chunk írási rendszert](#user-content-fn-10)[^10].

Ez a chunkokat sorrendben menti, ami jelentős teljesítményveszteséget okoz.

#### `Paper.explicit-flush`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Engedélyezi a hálózati csatorna explicit kiürítését.

#### `Paper.strict-thread-checks`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Mindig naplózza a fő szálon nem előforduló hibákat.

#### `Paper.tickList-warn-on-excessive-delay`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Ha a késleltetés túl hosszú, figyelmeztetést ad a tervezett műveletekről.

#### `Paperclip.patchOnly`

- **Forma**: `Boolean`
- **Alapértelmezett**: `False`

Ha az alapértelmezett futtatható fájlt használja, csak a javítást alkalmazza a szerver indítása nélkül.

#### `Plazma.aggressiveOptimize`

- **Forma**: `Boolean`
- **Alapértelmezett**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Forma**: `Boolean`
- **Alapértelmezett**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Forma**: `Boolean`
- **Alapértelmezett**: `false`

Megakadályozza a Plazma inicializálásakor megjelenő [figyelmeztetéseket](#user-content-fn-11)[^11].

#### `Plazma.useVanillaFavicon`

- **Forma**: `Boolean`
- **Alapértelmezett**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Forma**: `Boolean`
- **Alapértelmezett**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

{% hint style="danger" %}

**해당 속성은 패치된 모든 취약점을 되돌립니다!**

이는 서버 안전 및 성능에 크게 영향을 줄 수 있습니다.

해당 속성을 사용하여 발생하는 모든 문제는 서버 관리자에게 있습니다.

{% endhint %}

초기 구성을 Mojang에서 제공하는 기본값으로 제공합니다.

이는 Paper에서 적용한 모든 취약점 패치를 비활성화 합니다.

취약점 패치는 Paper 구성 또는 Plazma 구성에서 다시 활성화 할 수 있습니다.

#### `Plazma.vanillaize`

- **Forma**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Használt tulajdonság <a href="#id-1.3" id="id-1.3"></a>

Az alábbi rendszer tulajdonság egy használt tulajdonság.

#### `timings.bypassMax`

- **Forma**: `Boolean`
- **Alapértelmezett**: `false`
- **Használt**: Timings a Plazma-ban történő teljes eltávolítása óta

Meghatározza, hogy az Aikar Timings API-ba elküldhető érték túllépheti-e a maximált.

Ha így teszel, és az API nem kezeli kivételesen, akkor a sebességkorlály alkalmazódik.

***

## Indítási argumentum <a href="#id-2" id="id-2"></a>

Az indítási argumentumok a `-jar *.jar` után kerülnek be, amikor a Plazma inicializálódik és együttesen kezelik őket.

### Használati útmutató <a href="#id-2.1" id="id-2.1"></a>

A rendszer tulajdonságokat a `-jar *.jar` után program parancs argumentumként adják meg.

Például, ha a `nogui` indítási argumentumot akarod alkalmazni, \
akkor az alábbi módon beírva a Plazma inicializálása közben a `nogui` argumentumot fogja kezelni.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Teljes indítási argumentumok <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Alapértelmezett**: `bukkit.yml`

Beállítja a [Bukkit konfigurációs fájl](../reference/configurations/bukkit.md) nevét és helyét.

#### `command-settings`

- **Alias**: `c`
- **Alapértelmezett**: `commands.yml`

Beállítja a [Bukkit parancs konfigurációs fájl](../reference/configurations/bukkit.md) nevét és helyét.

#### `config`

- **Alias**: `c`
- **Alapértelmezett**: `server.properties`

Beállítja a [szerver tulajdonságok](../reference/configurations/property.md) fájl nevét és helyét.

#### `demo`

A demó világgal indítja a szervert.

#### `eraseCache`

A világ frissítése után a megmaradt gyorsítótárazott fájlokat eltávolítja.

#### `forceUpgrade`

Figyelmen kívül hagyja a verziót és kényszerítetten [frissít](#user-content-fn-12)[^12] a világot.

#### `help`

- **Alias**: `?`

Kiírja a Plazma teljes indítási argumentumait és leírását.

#### `initSettings`

Csak a konfigurációs fájlokat hozza létre és leállítja a szervert.

#### `jfrProfile`

Aktiválja a JFR profilozást.

#### `max-players`

- **Alias**: `s`, `size`
- **Alapértelmezett**: `(szerver tulajdonságok)`

Beállítja a megengedett maximális [játékos](#user-content-fn-14)[^14] számot.

#### `nogui`

Letiltja a grafikus felhasználói felület panelt.

#### `nojline`

JLine-et kikapcsolva, és a vanília konzolt használja.

#### `online-mode`

- **Alias**: `o`
- **Alapértelmezett**: `(szerver tulajdonságok)`

Mojang hitelesítő szerverrel ellenőrzi a játékosokat.

**Ha nem használ Velocity vagy más proxy-t, akkor [EULA](../getting-started/README.md#id-5) megszegése miatt büntetésre kerülhet.**

#### `paper-beállítások`

- **Alias**: `paper`
- **Alapértelmezett**: `paper.yml`

{% hint style="warning" %}

**Ez az argumentum a 1.19.4 verziótól kezdve már nem használható!**

{% endhint %}

A használaton kívüli PaperSpigot konfigurációs fájl helyét állítja be.

Ez az előző konfiguráció áthelyezésére szolgál egy új konfigurációs fájlba, majd ezt követően már nem használható.

#### `paper-beállítások-mappája`

- **Alias**: `paper-mappa`
- **Alapértelmezett**: `config`

A [Paper konfigurációs fájl](../reference/configurations/paper/README.md) mappájának és helyének beállítása.

#### `plazma-beállítások-mappája`

- **Alias**: `plazma-mappa`

A [Plazma konfigurációs fájl](../reference/configurations/plazma/README.md) mappájának és helyének beállítása.

#### `bővítmények`

- **Alias**: `b`
- **Alapértelmezett**: `bővítmények`

A bővítmények mappájának beállítása.

#### `pufferfish-beállítások`

- **Alias**: `pufferfish`
- **Alapértelmezett**: `pufferfish.yml`

A [Pufferfish konfigurációs fájl](../reference/configurations/pufferfish.md) nevének és helyének beállítása.

#### `purpur-beállítások`

- **Alias**: `purpur`
- **Alapértelmezett**: `purpur.yml`

A [Purpur konfigurációs fájl](../reference/configurations/purpur/README.md) nevének és helyének beállítása.

#### `safeMode`

(Biztonságos mód) Teljesen vanília állapotban indítja a szervert.

#### `szerver-ip`

- **Alias**: `h`, `host`
- **Alapértelmezett**: `(szerver tulajdonságok)`

A szerver hosztjának nevét vagy [Internet Protocol](#user-content-fn-13)[^13] címét állítja be.

#### `szerver-port`

- **Alias**: `p`, `port`
- **Alapértelmezett**: `(szerver tulajdonságok)`

A szerver portját állítja be.

#### `szerver-név`

- **Alapértelmezett**: `Egy Plazma Szerver`

A szerver nevét állítja be.

#### `spigot-beállítások`

- **Alias**: `S`
- **Alapértelmezett**: `spigot.yml`

A [Spigot konfigurációs fájl](../reference/configurations/spigot.md) nevének és helyének beállítása.

#### `verzió`

- **Alias**: `v`

Plazma verzióját jeleníti meg.

#### `világ-mappa`

- **Alias**: `W`, `univerzum`, `világ-tartó`
- **Alapértelmezett**: `(szerver mappa)`

A világ fájlok mentési helyét állítja be.

#### `világ-név`

- **Alias**: `w`, `világ`
- **Alapértelmezett**: `(szerver tulajdonságok)`

A világ fájl nevét állítja be.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Az argumentumok kezelése a hozzáadott helytől függ.

[^3]: Például, ha be akarja állítani (aktiválni) a `Plazma.iKnowWhatIAmDoing`-ot `true`-ra, akkor csak a `-DPlazma.iKnowWhatIAmDoing`-ot kell megadnia, és ugyanúgy működni fog, mint a `-DPlazma.iKnowWhatIAmDoing=true`.

[^4]: Például, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Eseményfigyelő.

[^6]: Eseményfigyelő.

[^7]: Kliens.

[^8]: A szerverrel való megfelelő kapcsolatot jelző jelek, mint a szívverés.

[^9]: A Purpur AFK kick funkcióval még az inaktív játékosokat is kickelheti.

[^10]: Szinkron Chunk írási rendszer, Sync Chunk Write System.

[^11]: `FIGYELEM! Plazma váratlan problémákat okozhat, ezért előtte alaposan tesztelje, mielőtt nyilvános szerveren használná.`

[^12]: A játékban a `világ optimalizálás` is ugyanezen elven működik.

[^13]: Internet Protocol, IP.

[^14]: A `szint 2` vagy nagyobb szintű adminisztrátorokat kizárja.
