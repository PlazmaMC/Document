---
description: Lär dig om startargument och systemegenskaper.
---

# 🎛️ Argument och egenskaper

Startargument och systemegenskaper är värden som läggs till [kommandon som används](#user-content-fn-1)[^1] för att köra Plazma, vilket i sin tur påverkar Plazmas funktion.

[Plats för tillägg till kommandon](#user-content-fn-2)[^2] kommer att delas upp i **startargument** och **systemegenskaper** enligt detta.

***

## Systemegenskaper <a href="#id-1" id="id-1"></a>

Systemegenskaper är värden som behandlas av JVM innan Plazma initialiseras och placeras framför `-jar`.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Användning <a href="#id-1.1" id="id-1.1"></a>

Systemegenskaper anges som Java-kommandon mellan `java` och `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indikerar att det är ett dedikerat argument för Plazma och inte en inbyggd JVM-argument,

Om inga värden anges för egenskaperna kommer de att vara [`true` som standardvärde](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Alla systemegenskaper <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Uppdaterar avstängda skyltformat.

#### `debug.entities`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Aktiverar debuggloggar för entitetsinformation.

#### `debug.rewriteForIDE`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar NMS-revision för att korrekt ladda felsökningsinformation i IDE, och omkartlägger automatiskt intern versionsinformation.

#### `disable.watchdog`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar Spigots Watchdog-varningssystem.

#### `letMeReload`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar bekräftelsemeddelandet för `/reload`-kommandot.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Om du är en pluginutvecklare och behöver uppdatera en plugin, använd hotswap istället för `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar pluginer som använder standard in- och utmatning.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Varnar när avbrutet format upptäcks i chattkomponenter.

#### `Paper.bypassHostCheck`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar verifiering av servermönster när en spelare ansluter till servern.

#### `Paper.debugDynamicMissingKeys`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Aktiverar felsökningsloggar för saknade nycklar i NBT-objekt.

#### `Paper.debugInvalidSkullProfiles`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Aktiverar felsökningsloggar för felaktiga huvudprofiler.

Detta loggar alla felaktiga huvuden i världen med deras positioner.

#### `Paper.disableChannelLimit`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar prioritering av plugin-klasser.

Användbart vid problem med plugin-skuggning.

#### `Paper.disableFlushConsolidate`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar Netty-flushkonsolideringssystemet.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Standardvärde**: `750`

Dela upp entiteter i flera paket om de är fler än det angivna värdet.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Standardvärde**: `8192`

Ställer in den maximala storleken på paket som servern kan ta emot åt gången.

#### `Paper.ignoreJavaVersion`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Inaktiverar Java-versionkontroll.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Det kan permanent skada världar och filer samt förstöra spelets mekanik.

Alla problem som uppstår efter detta är användarens ansvar och Plazma ger inget stöd för detta.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Standardvärde**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Standardvärde**: `80`

Ställer in max längd för text på en skyltlinje.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Standardvärde**: `(world version) + 1`

Ställer in versionen för uppdateringsinformation som ska initialiseras först.

Användbart vid massuppdatering av chunkar men annars sällan använt.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Standardvärde**: `True`

Aktiverar hantering av YAML-filkommentarer som standard.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Standardvärde**: `30`

Spelaren kastas ut om ingen data har mottagits inom den angivna tiden (i sekunder).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Ignorerar kommentarer i serveregenskaper.

#### `Paper.debug-sync-loads`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Aktiverar debuggloggar för synkroniserad chunkskapande.

#### `Paper.enable-sync-chunk-writes`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Aktiverar Minecrafts [standard chunkskapande system](#user-content-fn-10)[^10].

Detta leder till en betydande prestandaförsämring eftersom varje chunk sparas i tur och ordning.

#### `Paper.explicit-flush`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Aktiverar explicit flushing för nätverkskanaler.

#### `Paper.strict-thread-checks`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Loggar alltid fel som uppstår utanför huvudtråden.

#### `Paper.tickList-warn-on-excessive-delay`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Ger varning om schemalagda uppgifter har för stor fördröjning.

#### `Paperclip.patchOnly`

- **Typ**: `Boolean`
- **Standardvärde**: `False`

Om du använder den medföljande körbara filen tillämpas endast patcher utan att starta servern.

#### `Plazma.aggressiveOptimize`

- **Typ**: `Boolean`
- **Standardvärde**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

Optimerar den ursprungliga konfigurationen mer kraftfullt.

Aktivering gör att servern blir snabbare och säkrare, men kan ha stor påverkan på spelupplevelsen.

#### `Plazma.disableConfigOptimization`

- **Typ**: `Boolean`
- **Standardvärde**: `false`
- **Konflikt**: `Plazma.aggressiveOptimize`

Optimerar inte den ursprungliga konfigurationen.

Detta innebär att använda Pappers grundläggande konfiguration.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Standardvärde**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Typ**: `Boolean`
- **Standardvärde**: `false`

Inaktiverar Plazma-varumärket och använder en vanlig serverfavicon.

#### `Plazma.useVanillaConfiguration`

- **Typ**: `Boolean`
- **Standardvärde**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Detta kan i hög grad påverka serverns säkerhet och prestanda.

Alla problem som uppstår med denna egenskap är serveradministratörens ansvar.
{% endhint %}

Förser den ursprungliga konfigurationen med standardvärden från Mojang.

Detta inaktiverar alla patchar för sårbarheter som Paper har implementerat.

Sårbarhetspatchar kan återaktiveras i Paper-konfigurationen eller Plazma-konfigurationen.

#### `Plazma.vanillaize`

- **Typ**: `Boolean`
- **Standardvärde**: `true`
- **Konflikt**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Justerar den ursprungliga konfigurationen för att vara närmare en vanlig konfiguration.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Avbruten egenskap <a href="#id-1.3" id="id-1.3"></a>

Följande systemegenskaper är avbrutna egenskaper.

#### `timings.bypassMax`

- **Typ**: `Boolean`
- **Standardvärde**: `false`
- **Avbruten användning**: Timings har tagits bort från Plazma sedan

Bestämmer om det är tillåtet att överskrida det maximala värdet som kan skickas till Aikars Timings API.

Om detta inte hanteras av API:et, kommer en hastighetsbegränsning att tillämpas.

***

## Startargument <a href="#id-2" id="id-2"></a>

Startargumentet anges efter `-jar *.jar` för att initialisera Plazma och bearbetas tillsammans med det.

### Användning <a href="#id-2.1" id="id-2.1"></a>

Systemegenskaper anges som programkommandon efter `-jar *.jar`.

Till exempel, om du vill använda startargumentet `nogui`,\
ska du ange det på följande sätt så att Plazma kan bearbeta `nogui`-argumentet under initialiseringen.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Fullständiga startargument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Standardvärde**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Standardvärde**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Standardvärde**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Startar servern i demovärlden.

#### `eraseCache`

Tar bort eventuella cache-filer som finns kvar efter en världsuppdatering.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Skriver ut alla startargument och deras beskrivningar för Plazma.

#### `initSettings`

Skapar endast konfigurationsfilen och stänger av servern.

#### `jfrProfile`

Aktiverar JFR-profileringsläget.

#### `max-players`

- **Alias**: `s`, `size`
- **Standardvärde**: `(serveregenskaper)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Inaktiverar den grafiska användargränssnittspanelen.

#### `nojline`

Inaktiverar JLine och använder en vanlig konsol istället.

#### `online-mode`

- **Alias**: `o`
- **Standardvärde**: `(serveregenskaper)`

Väljer om spelare ska verifieras mot Mojangs autentiseringsservrar.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Standardvärde**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Ställer in platsen för den avbrutna PaperSpigot-konfigurationsfilen.

Används för att överföra befintlig konfiguration till en ny fil och används inte längre efter detta.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standardvärde**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Standardvärde**: `plugins`

Ställer in platsen för plugin-mappen.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardvärde**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardvärde**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Startar servern i fullständigt vaniljläge (säkert läge).

#### `server-ip`

- **Alias**: `h`, `host`
- **Standardvärde**: `(serveregenskaper)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Standardvärde**: `(serveregenskaper)`

Ställer in serverns port.

#### `server-name`

- **Standardvärde**: `A Plazma Server`

Ställer in serverns namn.

#### `spigot-settings`

- **Alias**: `S`
- **Standardvärde**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Skriver ut Plazma-versionen.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Standardvärde**: `(servermapp)`

Ställer in platsen där världsfiler sparas.

#### `world-name`

- **Alias**: `w`, `world`
- **Standardvärde**: `(serveregenskaper)`

Ställer in namnet på världsfilen.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Beroende på den bifogade platsen ändras platsen för att hantera parametrar.

[^3]: Till exempel, om du vill ställa in `Plazma.iKnowWhatIAmDoing` till `true` (aktivera), fungerar det på samma sätt att bara ange `-DPlazma.iKnowWhatIAmDoing` istället för `-DPlazma.iKnowWhatIAmDoing=true`.

[^4]: Till exempel, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Händelsedetektor.

[^6]: Händelsedetektor.

[^7]: Klient.

[^8]: Ett signal som indikerar att servern är korrekt ansluten, liknande hjärtslag.

[^9]: Med Purpurs AFK-utkastningsfunktion kan även frånvarande spelare kastas ut.

[^10]: Sync Chunk Write System, system för synkron skapande av segment.

[^11]: `VARNING! Plazma kan orsaka oväntade problem, så se till att testa det noggrant innan du använder det på en offentlig server.`

[^12]: I spelet fungerar även `världsoptimering` enligt samma princip.

[^13]: Administratörer över `nivå 2` är undantagna.

[^14]: Internetprotokoll, IP.
