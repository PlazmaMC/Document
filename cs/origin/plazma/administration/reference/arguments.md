---
description: Zjistěte více o počátečních argumentech a vlastnostech systému.
---

# 🎛️ Argumenty a vlastnosti

Začáteční argumenty a vlastnosti systému jsou hodnoty přidávané k [příkazům používaným k spuštění Plazmy](#user-content-fn-1)[^1], které mají celkový vliv na chod Plazmy.

[Při přidání do pozice příkazu](#user-content-fn-2)[^2] se rozdělí na **vstupní argumenty** a **systémové vlastnosti**.

***

## Vlastnosti systému <a href="#id-1" id="id-1"></a>

Vlastnosti systému jsou hodnoty zpracované v JVM před inicializací Plazmy zadané před `-jar`.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Použití <a href="#id-1.1" id="id-1.1"></a>

Vlastnosti systému se zadávají jako argumenty Java mezi `java` a `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` označuje, že tento argument není vestavěný v JVM, ale je přidaný pouze pro Plazmu,

Pokud nezadáte žádnou hodnotu do vlastnosti, bude hodnota nastavena na [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Výchozí hodnota**: `750`

Pokud je entit více, než je nastaveno, rozdělí se na více paketů k odeslání.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Výchozí hodnota**: `8192`

Nastavuje maximální velikost paketu, kterou server může přijmout najednou.

#### `Paper.ignoreJavaVersion`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `False`

Deaktivuje kontrolu verze Javy.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Může dojít k trvalému poškození souborů ve světě a selhání celé herní mechaniky.

Všechny problémy způsobené tímto jsou vaší zodpovědností a Plazma neposkytuje žádnou podporu v této věci.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Výchozí hodnota**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Výchozí hodnota**: `80`

Nastavuje maximální délku textu na jednom řádku značky.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Výchozí hodnota**: `(verze světa) + 1`

Nastavuje verzi informací o aktualizaci světa pro inicializaci.

Užitečné pro hromadné aktualizace, jinak není používáno.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `True`

Aktivuje zpracování komentářů v YAML souborech.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Výchozí hodnota**: `30`

Pokud hráč nepošle žádná data po dobu nastavenou v sekundách, hráč je vyhozen.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Konflikt**: `Plazma.disableConfigOptimization`

Zesiluje počáteční konfiguraci.

Aktivací se server stane rychlejším a bezpečnějším, ale může mít velký vliv na hraní her.

#### `Plazma.disableConfigOptimization`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `false`
- **Konflikt**: `Plazma.aggressiveOptimize`

Neprovádí optimalizaci počáteční konfigurace.

Tím se použije výchozí konfigurace Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `false`

Deaktivuje Plazma značení a nastaví použití základního faviconu serveru.

#### `Plazma.useVanillaConfiguration`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Může to mít velký vliv na bezpečnost a výkon serveru.

Problémy způsobené touto vlastností jsou zodpovědností správce serveru.
{% endhint %}

Nastaví počáteční konfiguraci na výchozí hodnoty poskytované Mojangem.

Následkem je deaktivace všech záplatovaných zranitelností prováděných v Paperu.

Záplatované zranitelnosti mohou být znovu aktivovány v konfiguraci Paper nebo Plazmy.

#### `Plazma.vanillaize`

- **Typ**: `Boolean`
- **Výchozí hodnota**: `true`
- **Konflikt**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Nastaví počáteční konfiguraci blízko k základu.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Výchozí hodnota**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Výchozí hodnota**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Spustí server v demonstračním světě.

#### `eraseCache`

Odstraní zbývající cache soubory po aktualizaci světa.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Vypne grafický uživatelský panel.

#### `nojline`

Deaktivujte JLine a použijte konzoli Vanilla.

#### `online-mode`

- **Alias**: `o`
- **Výchozí hodnota**: `(serverové vlastnosti)`

Vyberte, zda chcete ověřovat hráče u Mojang ověřovacího serveru.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Výchozí hodnota**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Nastavuje umístění deaktivovaného konfiguračního souboru PaperSpigot.

Používá se k přesunu stávající konfigurace do nového souboru a poté už není používán.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Výchozí hodnota**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Výchozí hodnota**: `plugins`

Nastavuje umístění složky s pluginy.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Výchozí hodnota**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Výchozí hodnota**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Spustí server v režimu Vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Výchozí hodnota**: `(serverové vlastnosti)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Administrátoři nad `úrovní 2` jsou vyloučeni.

[^14]: Internetový protokol, IP.
