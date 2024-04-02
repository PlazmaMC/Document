---
description: Zistite viac o počiatočných argumentoch a systémových vlastnostiach.
---

# 🎛️ Argumenty a vlastnosti

Počiatočné argumenty a systémové vlastnosti sú hodnoty pridávané k [príkazom používaným pri spustení Plazmy](#user-content-fn-1)[^1], ktoré umožňujú zmeniť hodnoty, ktoré nemožno zmeniť po spustení Plazmy.

V závislosti na [mieste pridania k príkazu](#user-content-fn-2)[^2] sa rozlišujú na **počiatočné argumenty** a **systémové vlastnosti**.

***

## Systémová vlastnosť <a href="#id-1" id="id-1"></a>

Systémová vlastnosť je hodnota spracovaná v JVM pred inicializáciou Plazmy pred `-jar`.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### Použitie <a href="#id-1.1" id="id-1.1"></a>

Systémová vlastnosť sa zadáva ako Java argument medzi `java` a `-jar`.

Napríklad, ak chcete použiť systémovú vlastnosť `Plazma.dummyProperty`,
zadajte ju nasledovne a hodnota `37` bude pridaná do Plazmy po inicializácii.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` označuje, že tento argument nie je vstavaný do JVM, ale je špecifický pre Plazmu a

ak nezadáte žiadnu hodnotu, bude hodnota [`true` nastavená.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

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

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

Deaktivuje obmedzenie na 128 pluginových kanálov na hráča[^5].

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

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Môže to trvalo poškodiť súbory v hre a spôsobiť zlyhanie hry.

Všetky problémy spôsobené týmto opatrením sú plne zodpovednosťou používateľa a Plazma neposkytuje žiadnu podporu!

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Typ**: `Integer`
- **Predvolená hodnota**: `64`

Nastavuje obmedzenie názvu kanála pluginu[^6].

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

V bežných prípadoch hra[^7] neustále posiela [signály srdca](#user-content-fn-8)[^8] na server, takže [nedochádza k vyhodeniu,](#user-content-fn-9)[^9] ale ak hra nereaguje, server považuje hru za zhroucenú a prestane spracovávať hráča a vyhodí ho.

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

{% hint style="warning" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Pri prvom spustení sa prísnejšie uplatnia konfiguračné optimalizácie.

Ak je aktivovaný, server sa stane rýchlejším a bezpečnejším, ale môže blokovať niektoré hrateľné prvky alebo mať významný vplyv na hranie hry.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`

Potláča upozornenia[^11], ktoré sa zobrazujú pri inicializácii Plazmy.

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

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

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
