---
description: Zistite viac o počiatočných argumentoch a systémových vlastnostiach.
---

# 🎛️ Argumenty a vlastnosti

Začiatočné argumenty a vlastnosti systému predstavujú hodnoty, ktoré sa pridávajú k [príkazom používaným na spustenie Plazmy](#user-content-fn-1)[^1], čo celkovo ovplyvňuje fungovanie Plazmy.

[Pozícia pridania príkazu](#user-content-fn-2)[^2] rozdeľuje **štartový argument** a **vlastnosti systému**.

***

## Systémová vlastnosť <a href="#id-1" id="id-1"></a>

Systémová vlastnosť je hodnota spracovaná v JVM pred inicializáciou Plazmy pred `-jar`.

{% hint style="warning" %}

**Ak sa zmenia vlastnosti systému, môže to ovplyvniť fungovanie Plazmy a JVM a môže to mať veľký vplyv na hru!**

Ak neviete presne, akú úlohu zohráva každá vlastnosť systému, **určite ju nepoužívajte!**

{% endhint %}

### Použitie <a href="#id-1.1" id="id-1.1"></a>

Systémová vlastnosť sa zadáva ako Java argument medzi `java` a `-jar`.

Napríklad, ak sa snažíte použiť systémovú vlastnosť `Plazma.dummyProperty`,
po zadaniu nasledujúceho kódu sa hodnota `37` priradí k danej vlastnosti a Plazma sa inicializuje.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` označuje, že tento argument nie je vstavaný do JVM, ale je špecifický pre Plazmu a

Ak nezadáte žiadnu hodnotu do vlastnosti, hodnota sa nastaví na [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Platforma serverov z radu Paperweight obsahuje bodku `.` v názve vlastnosti na rozlišovanie vlastností systému pre každú platformu.**

V niektorých termináloch ako Windows Powershell nemusia byť tieto argumenty povolené, preto je potrebné pridať `"` na oboch koncoch argumentu [ako ochranu](#user-content-fn-4)[^4].

{% endhint %}

### Všetky systémové vlastnosti <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Aktualizuje zastaraný formát tabúľ.

#### `debug.entities`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Aktivuje záznamy debugovacích informácií o entitách.

#### `debug.rewriteForIDE`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje NMS revíziu pre IDE na správne načítanie debugovacích informácií a automatický remapovanie vnútorných verzií.

#### `disable.watchdog`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje systém upozornení Watchdog v Spigote.

#### `letMeReload`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje potvrdenie príkazu `/reload`.

{% hint style="danger" %}

**Príkaz `/reload` je veľmi nestabilný, preto všetky problémy v serveri po jeho použití sú zodpovednosťou používateľa.**

Ak ste vývojár pluginov a musíte aktualizovať pluginy, použite hotswap namiesto príkazu `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje pluginy, ktoré používajú štandardný výstup a vstup.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Upozorní pri detekcii zastaraného formátovania v chatových komponentoch.

#### `Paper.bypassHostCheck`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje overovanie vzoru servera pri pripájaní hráča.

#### `Paper.debugDynamicMissingKeys`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Aktivuje záznamy debugovacích informácií o chýbajúcich kľúčoch v NBT objektoch.

#### `Paper.debugInvalidSkullProfiles`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Aktivuje záznamy debugovacích informácií o neplatných profiloch lebiek.

Toto zaznamenáva všetky neplatné lebky v svete spolu s ich polohou.

#### `Paper.disableChannelLimit`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje obmedzenie na 128 kanálov [zásuvných modulov](#user-content-fn-5)[^5] aplikovaných na hráča.

#### `Paper.disableClassPrioritization`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje triedny prioritizačný systém pluginov.

Užitočné pri problémoch so zatienením pluginov.

#### `Paper.disableFlushConsolidate`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje systém zlučovania Netty flush.

#### `Paper.excessiveTELimit`

- **Typ**: `Integer`
- **Predvolená hodnota**: `750`

Ak entita presiahne stanovenú hodnotu, bude odoslaná ako viacero paketov.

#### `Paper.filterThreshold`

- **Typ**: `Integer`
- **Predvolená hodnota**: `8192`

Nastavuje maximálnu veľkosť paketu, ktorú server môže prijať naraz.

#### `Paper.ignoreJavaVersion`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Deaktivuje kontrolu verzie Javy.

{% hint style="danger" %}

**Týmto spôsobom sa môže JVM pokúsiť pristúpiť k neexistujúcemu kódu!**

Môže to trvalo poškodiť súbory v hre a spôsobiť zlyhanie hry.

Všetky problémy spôsobené týmto opatrením sú plne zodpovednosťou používateľa a Plazma neposkytuje žiadnu podporu!

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Typ**: `Integer`
- **Predvolená hodnota**: `64`

Nastavuje obmedzenie pre názov [kanála](#user-content-fn-6)[^6] pluginu.

#### `Paper.maxSignLength`

- **Typ**: `Integer`
- **Predvolená hodnota**: `80`

Nastavuje maximálnu dĺžku textu na jednom riadku tabule.

#### `Paper.minPrecachedDatafixVersion`

- **Typ**: `Integer`
- **Predvolená hodnota**: `(verzia sveta) + 1`

Nastavuje verziu údajov, ktoré sa majú najskôr aktualizovať pri inicializácii sveta.

Užitočné pri hromadnom aktualizovaní blokov, inak sa nepoužíva.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `True`

Aktivuje spracovanie komentárov v YAML súboroch.

#### `Paper.playerConnection.keepAlive`

- **Typ**: `Integer`
- **Predvolená hodnota**: `30`

Ak hráč neodosielal žiadne dáta počas určeného času (v sekundách), hráča vyhodí zo servera.

V bežnom prípade [hra](#user-content-fn-7)[^7] neprestáva posielať [srdcový impulz](#user-content-fn-8)[^8] na server, takže nie je vyhostená, ale ak hra prestane reagovať, server ju považuje za zlyhanú a prestane ju ďalej spracovávať a vyhostí hráča.

#### `Paper.skipServerPropertiesComments`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Ignoruje komentáre vlastností servera.

#### `Paper.debug-sync-loads`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Aktivuje záznamy debugovacích informácií o synchronizovaní chunkov.

#### `Paper.enable-sync-chunk-writes`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Aktivuje [štandardný systém zápisu chunkov](#user-content-fn-10)[^10] v Minecrafte.

Tento systém ukladá každý chunk postupne, čo spôsobuje veľký výkonový pokles.

#### `Paper.explicit-flush`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Aktivuje Explicit Flushing v sieťovom kanáli.

#### `Paper.strict-thread-checks`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Vždy zaznamenáva chyby, ktoré nevznikli v hlavnom vlákne.

#### `Paper.tickList-warn-on-excessive-delay`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Ak sú naplánované úlohy príliš dlho čakajú, vypíše sa varovanie.

#### `Paperclip.patchOnly`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `False`

Ak sa používa predvolený spustiteľný súbor, aplikuje sa iba záplatovanie bez spustenia servera.

#### `Plazma.aggressiveOptimize`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

Posilňuje optimalizáciu počiatočnej konfigurácie.

Jeho aktivácia spôsobuje, že server sa stáva rýchlejším a bezpečnejším, no môže mať výrazný vplyv na hrateľnosť hry.

#### `Plazma.disableConfigOptimization`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`
- **Konflikt**: `Plazma.aggressiveOptimize`

Neoptimalizuje počiatočnú konfiguráciu.

Toto nastavenie používa predvolenú konfiguráciu Paperu.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`

Potláča varovanie, ktoré sa zobrazuje pri inicializácii Plazmy [upozornenia](#user-content-fn-11)[^11].

#### `Plazma.useVanillaFavicon`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`

Deaktivuje značenie Plazma a používa základný serverový ikonu.

#### `Plazma.useVanillaConfiguration`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}

**Tento vlastnosť je stále vo vývoji.**

{% endhint %}

{% hint style="danger" %}

**Tento vlastnosť vráti všetky opravené chyby v patchoch!**

Toto môže mať veľký vplyv na bezpečnosť a výkon servera.

Všetky problémy, ktoré spôsobí použitie tejto vlastnosti sú zodpovednosťou správcu servera.

{% endhint %}

Poskytuje počiatočnú konfiguráciu s predvolenými hodnotami od Mojangu.

Toto deaktivuje všetky záplaty na chyby, ktoré boli aplikované v Paperi.

Chybové opravy môžu byť opäť aktivované v Paper konfigurácii alebo Plazma konfigurácii.

#### `Plazma.vanillaize`

- **Typ**: `Boolean`
- **Predvolené nastavenie**: `true`
- **Konflikt**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**Tento vlastnosť je stále vo vývoji.**

{% endhint %}

Nastavuje počiatočnú konfiguráciu približne k základným hodnotám.

Toto sa zvyčajne uplatňuje len v miere, ktorá nemá vplyv na výkon a bezpečnosť servera a keď je použitá vlastnosť `Plazma.disableConfigOptimization`, konfiguruje sa na základné hodnoty z vanilla.

### Použitá zastaraná vlastnosť <a href="#id-1.3" id="id-1.3"></a>

Nižšie uvedené systémové vlastnosti sú zastarané.

#### `timings.bypassMax`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`
- **OBSOLETE**: Po odstránení Timings z Plazma

Rozhoduje, či môže byť prekročená maximálna hodnota, ktorá sa môže posielať do Aikarho Timings API.

Ak nie je v API spracovaná výnimka, aplikuje sa obmedzenie rýchlosti.

***

## Argument štartu <a href="#id-2" id="id-2"></a>

Argument štartu je hodnota, ktorá sa zadáva za `-jar *.jar` a inicializuje sa spolu s Plazmou.

### Spôsob použitia <a href="#id-2.1" id="id-2.1"></a>

Systémové vlastnosti sa zadávajú ako programové argumenty za `-jar *.jar`.

Napríklad, ak chcete použiť argument štartu `nogui`,\
plazma bude tento argument spracovávať počas inicializácie nasledovne:

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Celkový argument štartu <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Predvolená hodnota**: `bukkit.yml`

Nastavuje názov a umiestnenie [konfiguračného súboru Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Predvolená hodnota**: `commands.yml`

Nastavuje názov a umiestnenie [konfiguračného súboru príkazov Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Predvolená hodnota**: `server.properties`

Nastavuje názov a umiestnenie [súboru vlastností servera](../reference/configurations/property.md).

#### `demo`

Spustí server v demo svete.

#### `eraseCache`

Odstráni zostávajúce cache súbory po aktualizácii sveta.

#### `forceUpgrade`

Vynúti [aktualizáciu](#user-content-fn-12)[^12] sveta bez ohľadu na verziu.

#### `help`

- **Alias**: `?`

Zobrazí všetky argumenty štartu a ich popis v Plazme.

#### `initSettings`

Vytvorí len konfiguračné súbory a vypne server.

#### `jfrProfile`

Aktivuje JFR profilovanie.

#### `max-players`

- **Alias**: `s`, `size`
- **Predvolená hodnota**: `(vlastnosť servera)`

Nastavuje maximálny počet [hráčov](#user-content-fn-14)[^14], ktorí sú povolení na serveri.

#### `nogui`

Vypne grafický rozhranie Plazmy.

#### `nojline`

Vypne JLine a použije základnú konzolu.

#### `online-mode`

- **Alias**: `o`
- **Predvolená hodnota**: `(vlastnosť servera)`

Určuje, či sa majú hráči overovať prostredníctvom Mojang autentizačných serverov.

**Ak nie je použitý Velocity alebo iný proxy, môže to byť porušením [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Predvolená hodnota**: `paper.yml`

{% hint style="warning" %}

**Tento argument bol po verzii 1.19.4 zastavený.**

{% endhint %}

Nastavuje umiestnenie [konfiguračného súboru PaperSpigot](../reference/configurations/paper/README.md), ktorý bol zastavený.

Slúži na prenesenie existujúcej konfigurácie do nového súboru a následne sa nepoužíva.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Predvolená hodnota**: `config`

Nastavuje názov a umiestnenie priečinka, kde sa nachádza [konfiguračný súbor Paper](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Nastavuje názov a umiestnenie priečinka, kde sa nachádza [konfiguračný súbor Plazma](../reference/configurations/plazma/README.md).

#### `plugins`

- **Alias**: `p`
- **Predvolená hodnota**: `plugins`

Nastavuje umiestnenie priečinka s pluginmi.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Predvolená hodnota**: `pufferfish.yml`

Nastavuje názov a umiestnenie [konfiguračného súboru Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Predvolená hodnota**: `purpur.yml`

Nastavuje názov a umiestnenie [konfiguračného súboru Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Spustí server v úplnom vanilla režime.

#### `server-ip`

- **Alias**: `h`, `host`
- **Predvolená hodnota**: `(vlastnosť servera)`

Nastavuje názov hostiteľa servera alebo [IP adresu](#user-content-fn-13)[^13].

#### `server-port`

- **Alias**: `p`, `port`
- **Predvolená hodnota**: `(vlastnosť servera)`

Nastavuje port servera.

#### `server-name`

- **Predvolená hodnota**: `A Plazma Server`

Nastavuje názov servera.

#### `spigot-settings`

- **Alias**: `S`
- **Predvolená hodnota**: `spigot.yml`

Nastavuje názov a umiestnenie [konfiguračného súboru Spigot](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Vypíše verziu Plazmy.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Predvolená hodnota**: `(priečinok servera)`

Nastavuje umiestnenie súborov sveta.

#### `world-name`

- **Alias**: `w`, `world`
- **Predvolená hodnota**: `(vlastnosť servera)`

Nastavuje názov súboru sveta.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Podľa umiestnenia pridaných argumentov sa mení miesto, kde sa argumenty spracovávajú.

[^3]: Napríklad, ak chcete nastaviť `Plazma.iKnowWhatIAmDoing` na `true`, môžete namiesto `-DPlazma.iKnowWhatIAmDoing=true` použiť len `-DPlazma.iKnowWhatIAmDoing` a stále to bude fungovať.

[^4]: Napríklad, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detektor udalostí.

[^6]: Detektor udalostí.

[^7]: Klient.

[^8]: Signál signalizujúci, že je server správne pripojený, podobne ako srdcový rytmus.

[^9]: Použitím funkcie AFK vyhadzovania v Purpure môžete vyhadzovať aj hráčov, ktorí sú neprítomní.

[^10]: Systém zápisu synchronizovaných blokov, Sync Chunk Write System.

[^11]: `VAROVANIE! Plazma môže spôsobiť neočakávané problémy, preto sa uistite, že ju dôkladne otestujete pred použitím na verejnom serveri.`

[^12]: V hre `svetová optimalizácia` funguje rovnakým spôsobom.

[^13]: Internetový protokol, IP.

[^14]: `Úroveň 2` alebo vyšší administrátori sú vylúčení.
