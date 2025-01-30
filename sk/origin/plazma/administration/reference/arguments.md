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
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Použitie <a href="#id-1.1" id="id-1.1"></a>

Systémová vlastnosť sa zadáva ako Java argument medzi `java` a `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` označuje, že tento argument nie je vstavaný do JVM, ale je špecifický pre Plazmu a

Ak nezadáte žiadnu hodnotu do vlastnosti, hodnota sa nastaví na [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Predvolená hodnota**: `750`

Ak entita presiahne stanovenú hodnotu, bude odoslaná ako viacero paketov.

#### `Paper.filterThreshold`

- **형태**: `Integer`
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

- **형태**: `Integer`
- **Predvolená hodnota**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Predvolená hodnota**: `80`

Nastavuje maximálnu dĺžku textu na jednom riadku tabule.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Predvolená hodnota**: `(verzia sveta) + 1`

Nastavuje verziu údajov, ktoré sa majú najskôr aktualizovať pri inicializácii sveta.

Užitočné pri hromadnom aktualizovaní blokov, inak sa nepoužíva.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `True`

Aktivuje spracovanie komentárov v YAML súboroch.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Predvolená hodnota**: `30`

Ak hráč neodosielal žiadne dáta počas určeného času (v sekundách), hráča vyhodí zo servera.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`

Deaktivuje značenie Plazma a používa základný serverový ikonu.

#### `Plazma.useVanillaConfiguration`

- **Typ**: `Boolean`
- **Predvolená hodnota**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

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
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Nastavuje počiatočnú konfiguráciu približne k základným hodnotám.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Predvolená hodnota**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Predvolená hodnota**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Spustí server v demo svete.

#### `eraseCache`

Odstráni zostávajúce cache súbory po aktualizácii sveta.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Vypne grafický rozhranie Plazmy.

#### `nojline`

Vypne JLine a použije základnú konzolu.

#### `online-mode`

- **Alias**: `o`
- **Predvolená hodnota**: `(vlastnosť servera)`

Určuje, či sa majú hráči overovať prostredníctvom Mojang autentizačných serverov.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

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

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Predvolená hodnota**: `plugins`

Nastavuje umiestnenie priečinka s pluginmi.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Predvolená hodnota**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Predvolená hodnota**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Spustí server v úplnom vanilla režime.

#### `server-ip`

- **Alias**: `h`, `host`
- **Predvolená hodnota**: `(vlastnosť servera)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: `Úroveň 2` alebo vyšší administrátori sú vylúčení.

[^14]: Internetový protokol, IP.
