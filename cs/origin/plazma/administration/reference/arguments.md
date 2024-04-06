---
description: Zjistěte více o počátečních argumentech a vlastnostech systému.
---

# 🎛️ Argumenty a vlastnosti

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[Při přidání do pozice příkazu](#user-content-fn-2)[^2] se rozdělí na **vstupní argumenty** a **systémové vlastnosti**.

***

## Vlastnosti systému <a href="#id-1" id="id-1"></a>

Vlastnosti systému jsou hodnoty zpracované v JVM před inicializací Plazmy zadané před `-jar`.

{% hint style="warning" %}

**Úpravou systémových vlastností se může změnit chování Plazma a JVM a může mít velký vliv na hru!**

Pokud nevíte přesně, jaká role je přiřazena každé systémové vlastnosti, **nepoužívejte ji!**

{% endhint %}

### Použití <a href="#id-1.1" id="id-1.1"></a>

Vlastnosti systému se zadávají jako argumenty Java mezi `java` a `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` označuje, že tento argument není vestavěný v JVM, ale je přidaný pouze pro Plazmu,

Pokud nezadáte žádnou hodnotu do vlastnosti, bude hodnota nastavena na [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Serverová platforma řady Paperweight obsahuje tečku v názvu vlastnosti k oddělení systémových vlastností pro každou platformu.**

V některých terminálech, jako je Windows Powershell, nemusí být tyto argumenty povoleny, takže je třeba na obou koncích argumentu přidat `"` [doplněk](#user-content-fn-4)[^4].

{% endhint %}

### Všechny vlastnosti systému <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Aktualizuje zastaralý formát značek.

#### `debug.entities`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Aktivuje debug logy související s informacemi o entitách.

#### `debug.rewriteForIDE`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje NMS revizi pro správné načítání informací v IDE a automaticky přemapuje interní verze.

#### `disable.watchdog`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje watchdog systém v Spigotu.

#### `letMeReload`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje potvrzovací zprávu pro příkaz `/reload`.

{% hint style="danger" %}

**Příkaz `/reload` je velmi nestabilní, takže veškeré problémy ve hře po jeho použití jsou zodpovědností uživatele.**

Pokud jste vývojář pluginů a potřebujete aktualizovat plugin, použijte místo `/reload` horkou výměnu.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje pluginy používající standardní vstup a výstup.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Upozorní na zastaralý formátovací kód v chatu.

#### `Paper.bypassHostCheck`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje ověřování vzoru serveru při připojení hráče.

#### `Paper.debugDynamicMissingKeys`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Aktivuje debug logy pro chybějící klíče v objektech NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Aktivuje debug logy pro neplatné profily lebek.

Toto zaznamenává všechny neplatné lebky v světě s jejich polohou.

#### `Paper.disableChannelLimit`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje omezení na 128 pluginů [kanálu](#user-content-fn-5)[^5] aplikovaných na hráče.

#### `Paper.disableClassPrioritization`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje prioritizaci tříd pluginů.

Užitečné při problémech s pluginy vytvořenými pomocí Shade.

#### `Paper.disableFlushConsolidate`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje Netty systém konsolidace flush.

#### `Paper.excessiveTELimit`

- **Typ**: `Integer`
- **Výchozí hodnota**: `750`

Pokud je entit více, než je nastaveno, rozdělí se na více paketů k odeslání.

#### `Paper.filterThreshold`

- **Typ**: `Integer`
- **Výchozí hodnota**: `8192`

Nastavuje maximální velikost paketu, kterou server může přijmout najednou.

#### `Paper.ignoreJavaVersion`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje kontrolu verze Javy.

{% hint style="danger" %}

**Tímto způsobem může JVM pokusit se přistupovat k neexistujícímu kódu!**

Může dojít k trvalému poškození souborů ve světě a selhání celé herní mechaniky.

Všechny problémy způsobené tímto jsou vaší zodpovědností a Plazma neposkytuje žádnou podporu v této věci.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Typ**: `Integer`
- **Výchozí hodnota**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Typ**: `Integer`
- **Výchozí hodnota**: `80`

Nastavuje maximální délku textu na jednom řádku značky.

#### `Paper.minPrecachedDatafixVersion`

- **Typ**: `Integer`
- **Výchozí hodnota**: `(verze světa) + 1`

Nastavuje verzi informací o aktualizaci světa pro inicializaci.

Užitečné pro hromadné aktualizace, jinak není používáno.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `True`

Aktivuje zpracování komentářů v YAML souborech.

#### `Paper.playerConnection.keepAlive`

- **Typ**: `Integer`
- **Výchozí hodnota**: `30`

Pokud hráč nepošle žádná data po dobu nastavenou v sekundách, hráč je vyhozen.

Obvykle [hra](#user-content-fn-7)[^7] pravidelně posílá [srdeční signál](#user-content-fn-8)[^8] na server, takže není [vyhozena,](#user-content-fn-9)[^9] ale pokud hra nereaguje, považuje se to za kolizi a hráče již server nezpracovává a vyhazuje.

#### `Paper.skipServerPropertiesComments`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Ignoruje komentáře v serverových vlastnostech.

#### `Paper.debug-sync-loads`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Aktivuje debug logy pro synchronizované zápisy chunků.

#### `Paper.enable-sync-chunk-writes`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Aktivuje [základní systém zápisu chunků](#user-content-fn-10)[^10] v Minecraftu.

Toto ukládá každý chunk postupně, což může zpomalit výkon.

#### `Paper.explicit-flush`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Aktivuje Explicit Flushing síťového kanálu.

#### `Paper.strict-thread-checks`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Vždy zaznamenává chyby, které nejsou vyvolány hlavním vláknem.

#### `Paper.tickList-warn-on-excessive-delay`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Vypíše varování, pokud plánovaná úloha má nadměrné zpoždění.

#### `Paperclip.patchOnly`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Pokud používáte výchozí spustitelný soubor, aplikuje pouze patch, ale nezahájí server.

#### `Plazma.aggressiveOptimize`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `false`

{% hint style="warning" %}

**Tato vlastnost bude přesunuta jako startovací argument po verzi 1.20.5.**

{% endhint %}

Při prvním spuštění se přísněji uplatní optimalizace konfigurace.

Aktivací se server stane rychlejším a bezpečnějším, ale může blokovat některé funkce nebo výrazně ovlivnit hraní hry.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `false`

Potlačuje [varování](#user-content-fn-11)[^11], které se zobrazuje při inicializaci Plazmy.

### Zastaralý atribut <a href="#id-1.3" id="id-1.3"></a>

Následující systémový atribut je zastaralý.

#### `timings.bypassMax`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `false`
- **Zastaralé**: Timings byly odstraněny z Plazmy

Rozhoduje, zda může být překročena maximální hodnota, která může být odeslána do Aikarova Timings API.

Pokud není v API zpracováno výjimky, bude uplatněno omezení rychlosti.

***

## Počáteční argument <a href="#id-2" id="id-2"></a>

Počáteční argument je hodnota, která se zadá za `-jar *.jar` při inicializaci Plazmy.

### Použití <a href="#id-2.1" id="id-2.1"></a>

Systémový atribut se zadává jako programový argument za `-jar *.jar`.

Pokud například chcete použít počáteční argument `nogui`,\
vytvořte vstup takto a Plazma bude zpracovávat argument `nogui` během inicializace.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Celkový počáteční argument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Výchozí hodnota**: `bukkit.yml`

Nastavuje název a umístění [konfiguračního souboru Bukkitu](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Výchozí hodnota**: `commands.yml`

Nastavuje název a umístění [konfiguračního souboru příkazů Bukkitu](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Výchozí hodnota**: `server.properties`

Nastavuje název a umístění [souboru vlastností serveru](../reference/configurations/property.md).

#### `demo`

Spustí server v demonstračním světě.

#### `eraseCache`

Odstraní zbývající cache soubory po aktualizaci světa.

#### `forceUpgrade`

Vynutí [aktualizaci](#user-content-fn-12)[^12] světa bez ohledu na verzi.

#### `help`

- **Alias**: `?`

Vypíše všechny počáteční argumenty a jejich popis v Plazmě.

#### `initSettings`

Vytvoří pouze konfigurační soubory a vypne server.

#### `jfrProfile`

Aktivuje JFR profilování.

#### `max-players`

- **Alias**: `s`, `size`
- **Výchozí hodnota**: `(serverové vlastnosti)`

Nastavuje maximální počet [hráčů](#user-content-fn-14)[^14] povolených na serveru.

#### `nogui`

Vypne grafický uživatelský panel.

#### `nojline`

Deaktivujte JLine a použijte konzoli Vanilla.

#### `online-mode`

- **Alias**: `o`
- **Výchozí hodnota**: `(serverové vlastnosti)`

Vyberte, zda chcete ověřovat hráče u Mojang ověřovacího serveru.

**Pokud nepoužíváte Velocity nebo jiný proxy, může to být porušení [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Výchozí hodnota**: `paper.yml`

{% hint style="warning" %}

**Tento argument byl zrušen po verzi 1.19.4.**

{% endhint %}

Nastavuje umístění deaktivovaného konfiguračního souboru PaperSpigot.

Používá se k přesunu stávající konfigurace do nového souboru a poté už není používán.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Výchozí hodnota**: `config`

Nastavuje název a umístění složky, kde jsou uloženy [konfigurační soubory Paper](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Nastavuje název a umístění složky, kde jsou uloženy [konfigurační soubory Plazma](../reference/configurations/plazma/README.md).

#### `plugins`

- **Alias**: `p`
- **Výchozí hodnota**: `plugins`

Nastavuje umístění složky s pluginy.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Výchozí hodnota**: `pufferfish.yml`

Nastavuje název a umístění [konfiguračního souboru Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Výchozí hodnota**: `purpur.yml`

Nastavuje název a umístění [konfiguračního souboru Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Spustí server v režimu Vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Výchozí hodnota**: `(serverové vlastnosti)`

Nastavuje název hostitele serveru nebo [IP adresu](#user-content-fn-13).

#### `server-port`

- **Alias**: `p`, `port`
- **Výchozí hodnota**: `(serverové vlastnosti)`

Nastavuje port serveru.

#### `server-name`

- **Výchozí hodnota**: `A Plazma Server`

Nastavuje název serveru.

#### `spigot-settings`

- **Alias**: `S`
- **Výchozí hodnota**: `spigot.yml`

Nastavuje název a umístění [konfiguračního souboru Spigot](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Vypíše verzi Plazmy.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Výchozí hodnota**: `(server folder)`

Nastavuje umístění souborů světa.

#### `world-name`

- **Alias**: `w`, `world`
- **Výchozí hodnota**: `(serverové vlastnosti)`

Nastavuje název souboru světa.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Zpracování argumentů se mění podle umístění doplnění.

[^3]: Například, pokud chcete nastavit `Plazma.iKnowWhatIAmDoing` na `true` (aktivováno), stačí zadat `-DPlazma.iKnowWhatIAmDoing` místo `-DPlazma.iKnowWhatIAmDoing=true`, a bude fungovat stejně.

[^4]: Například, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detektor událostí.

[^6]: Detektor událostí.

[^7]: Klient.

[^8]: Signál oznamující, že je klient úspěšně připojen k serveru, jako srdeční tep.

[^9]: Pomocí funkce vyhoštění AFK v Purpur můžete vyhodit i hráče, kteří jsou neaktivní.

[^10]: Synchronizační systém zápisu bloků, Sync Chunk Write System.

[^11]: `VAROVÁNÍ! Plazma může způsobit neočekávané problémy, takže si ji pečlivě otestujte před použitím na veřejném serveru.`

[^12]: Ve hře funguje `optimalizace světa` na stejném principu.

[^13]: Internetový protokol, IP.

[^14]: Administrátoři nad `úrovní 2` jsou vyloučeni.
