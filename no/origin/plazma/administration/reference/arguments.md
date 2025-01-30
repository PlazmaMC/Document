---
description: Lær om startargumenter og systemegenskaper.
---

# 🎛️ Argumenter og egenskaper

Startargumenter og systemegenskaper er verdier som legges til kommandoene som brukes til å kjøre Plazma[^1], og de har generell innvirkning på Plazmas funksjon.

[Plassering av tilleggskommandoer](#user-content-fn-2)[^2] vil dele dem inn i **startargumenter** og **systemegenskaper** i henhold til.

***

## Systemegenskaper <a href="#id-1" id="id-1"></a>

Systemegenskaper legges til foran `-jar` og behandles av JVM før Plazma initialiseres.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Bruksanvisning <a href="#id-1.1" id="id-1.1"></a>

Systemegenskaper legges til som Java-kommandoargumenter mellom `java` og `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indikerer at dette argumentet ikke er innebygd i JVM, men er et tilpasset argument for Plazma,

Hvis ingen verdier er angitt for egenskapene, vil verdiene være [`true` som standard](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Alle systemegenskaper <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Oppdaterer utdaterte skiltformater.

#### `debug.entities`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Aktiverer debuglogger for entitetsinformasjon.

#### `debug.rewriteForIDE`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer NMS-revisjonen for å tillate riktig lasting av debuginformasjon i IDE,\
og remapper automatisk interne versjonsinformasjoner.

#### `disable.watchdog`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer Spigots Watchdog-varslingssystem.

#### `letMeReload`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer bekreftelsesmeldingen for `/reload`-kommandoen.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Hvis du er pluginutvikler og må oppdatere pluginen din, bruk heller hotswapping i stedet for `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer plugins som bruker standard inndata/utdata-system.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Advarer når utdaterte formater oppdages i chatkomponenter.

#### `Paper.bypassHostCheck`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer serverens vertskontroll ved tilkobling av spillere.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Aktiverer debuglogger for manglende nøkler i NBT-objekter.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Aktiverer debuglogger for ugyldige hodeskalleprofiler.

Logger alle feilaktige hodeskalleblokker i verden med posisjon.

#### `Paper.disableChannelLimit`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer prioriteringssystemet for plugin-klasser.

Nyttig ved problemer med pluginskygging.

#### `Paper.disableFlushConsolidate`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer Netty-flush-konsolideringssystemet.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Standardverdi**: `750`

Del opp enheter i flere pakker for overføring hvis antallet overstiger denne verdien.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Standardverdi**: `8192`

Setter maksimal størrelse på pakker som serveren kan motta.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer Java-versjonskontrollen.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Dette kan permanent skade filer i verden og ødelegge spillets mekanikk.

Enhver skade forårsaket av dette er brukerens ansvar, og Plamza gir ingen støtte for det.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Standardverdi**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Standardverdi**: `80`

Setter maksimal lengde for tekst på et skilt.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Standardverdi**: `(verden versjon) + 1`

Setter versjonen for informasjon om verden som skal initialiseres først.

Nyttig for store mengder blokker som må oppdateres, men sjelden brukt ellers.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolsk`
- **Standardverdi**: `True`

Aktiverer behandling av kommentarer i YAML-filer som standard.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Standardverdi**: `30`

Kaster ut spillere som ikke sender data innen angitt tid (i sekunder).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Ignorerer kommentarer i serverens egenskaper.

#### `Paper.debug-sync-loads`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Aktiverer debuglogger for synkrone chunk-operasjoner.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Aktiverer Minecrafts [standard chunk-writing-system](#user-content-fn-10)[^10].

Dette lagrer hver chunk i en sekvensiell rekkefølge, noe som kan forårsake betydelig ytelsesnedgang.

#### `Paper.explicit-flush`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Aktiverer eksplisitt tømming av nettverkskanaler.

#### `Paper.strict-thread-checks`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Logger alltid feil som ikke oppstår i hovedtråden.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Advarer hvis planlagte oppgaver har overdreven ventetid.

#### `Paperclip.patchOnly`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Når du bruker standard kjørbare filer, vil den bare bruke patching uten å starte serveren.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolsk`
- **Standardverdi**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

Styrker den initielle konfigurasjonsoptimaliseringen.

Når aktivert, kan serveren bli raskere og sikrere, men det kan ha stor innvirkning på spillopplevelsen.

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolsk`
- **Standardverdi**: `false`
- **Konflikt**: `Plazma.aggressiveOptimize`

Unngår optimalisering av den initielle konfigurasjonen.

Dette setter opp bruken av Paper's standardkonfigurasjon.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolsk`
- **Standardverdi**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolsk`
- **Standardverdi**: `false`

Deaktiverer Plazma-merkevaren og bruker vanlig serverfaneikon.

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolsk`
- **Standardverdi**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Dette kan ha stor innvirkning på serverens sikkerhet og ytelse.

Alle problemer som oppstår ved bruk av denne egenskapen, er landsbygd vaktmesterens ansvar.
{% endhint %}

Setter opp den initiale konfigurasjonen til standardverdiene som tilbys av Mojang.

Deaktiverer alle sårbarhetsfiksene implementert av Paper.

Sårbarhetsfikser kan reaktiveres i Paper- eller Plazma-konfigurasjonen.

#### `Plazma.vanillaize`

- **Type**: `Boolsk`
- **Standardverdi**: `true`
- **Konflikt**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Setter den initiale konfigurasjonen nærmere til vanilje.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Egenskapen er ikke lenger i bruk <a href="#id-1.3" id="id-1.3"></a>

Følgende systemegenskaper er ikke lenger i bruk.

#### `timings.bypassMax`

- **Type**: `Boolsk`
- **Standardverdi**: `false`
- **Ikke lenger i bruk**: Timings ble fjernet fra Plazma

Bestemmer om verdier som sendes til Aikar's Timings API kan overskride maksimumsgrensen.

Selv om dette er tilfelle, vil en hastighetsbegrensning bli pålagt hvis det ikke håndteres som et unntak i API-en.

***

## Startargument <a href="#id-2" id="id-2"></a>

Startargumentet legges inn etter `-jar *.jar` for å initialisere Plazma og behandles sammen med det.

### Bruksanvisning <a href="#id-2.1" id="id-2.1"></a>

Systemegenskaper legges inn som programkommandoargumenter etter `-jar *.jar`.

For eksempel, hvis du vil bruke startargumentet `nogui`,\
kan du skrive det på følgende måte for at Plazma skal behandle `nogui`-argumentet under initialiseringen.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Fullstendig startargument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Standardverdi**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Standardverdi**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Standardverdi**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Starter serveren i demomodus.

#### `eraseCache`

Fjerner gjenværende hurtigbufferfiler etter verdenoppgradering.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Skriver ut alle startargumentene og beskrivelsene for Plazma.

#### `initSettings`

Oppretter kun konfigurasjonsfilen og avslutter serveren.

#### `jfrProfile`

Aktiverer JFR-profilering.

#### `max-players`

- **Alias**: `s`, `size`
- **Standardverdi**: `(serveregenskap)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Deaktiverer det grafiske grensesnittspanelet.

#### `nojline`

Deaktiver JLine og bruk vanlig konsoll.

#### `online-mode`

- **Alias**: `o`
- **Standardverdi**: `(serveregenskap)`

Velg om spillerne skal valideres mot Mojangs autentiseringsserver.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Standardverdi**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Setter plasseringen av den utdaterte PaperSpigot konfigurasjonsfilen.

Denne brukes til å flytte eksisterende konfigurasjon til en ny fil, og brukes ikke etter dette.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standardverdi**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Standardverdi**: `plugins`

Setter plasseringen av plugin-mappen.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardverdi**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardverdi**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Starter serveren i fullstendig vaniljemodus.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standardverdi**: `(serveregenskap)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Standardverdi**: `(serveregenskap)`

Setter porten for serveren.

#### `server-name`

- **Standardverdi**: `A Plazma Server`

Setter navnet på serveren.

#### `spigot-settings`

- **Alias**: `S`
- **Standardverdi**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Viser Plazma-versjonen.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Standardverdi**: `(servermappen)`

Setter plasseringen der verdensfilene lagres.

#### `world-name`

- **Alias**: `w`, `world`
- **Standardverdi**: `(serveregenskap)`

Setter navnet på verdensfilen.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Endrer argumentbehandling avhengig av tilleggslokasjonen.

[^3]: For eksempel, hvis du vil aktivere `Plazma.iKnowWhatIAmDoing` til `true`, trenger du bare å skrive `-DPlazma.iKnowWhatIAmDoing` i stedet for `-DPlazma.iKnowWhatIAmDoing=true`.

[^4]: For eksempel, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Event Detector.

[^6]: Event Detector.

[^7]: Client.

[^8]: Signal som indikerer at serveren er korrekt tilkoblet, som et hjerteslag.

[^9]: Med Purpurs AFK-kick-funksjon kan du kicke spillere som er inaktive.

[^10]: Sync Chunk Write System.

[^11]: `WARNING! Plazma kan forårsake uventede problemer, så sørg for å teste grundig før du bruker det på en offentlig server.`

[^12]: I spillet fungerer `world optimization` på samme måte.

[^13]: Administratorer på `nivå 2` eller høyere er unntatt.

[^14]: Internet Protocol, IP.
