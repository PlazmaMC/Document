---
description: Lær om startargumenter og systemegenskaper.
---

# 🎛️ Argumenter og egenskaper

Startvariabler og systemegenskaper er verdier som legges til kommandoer som brukes til å kjøre Plazma,\
og lar deg endre verdier som ikke kan endres etter at Plazma er kjørt.

Avhengig av [hvor de legges til kommandoen,](#user-content-fn-1)\[^1] deles de inn i **startargumenter** og **systemegenskaper**.

***

## Systemegenskaper <a href="#id-1" id="id-1"></a>

Systemegenskaper legges til foran `-jar` og behandles av JVM før Plazma initialiseres.

{% hint style="warning" %}

**Hvis du endrer systemegenskaper, kan Plazma og JVMs funksjon endres, noe som kan ha stor innvirkning på spillet!**

Hvis du ikke er sikker på hva hver systemegenskap gjør, **ikke bruk den under noen omstendigheter!**

{% endhint %}

### Bruksanvisning <a href="#id-1.1" id="id-1.1"></a>

Systemegenskaper legges til som Java-kommandoargumenter mellom `java` og `-jar`.

For eksempel, hvis du vil bruke systemegenskapen `Plazma.dummyProperty`,\
og du legger til den som følger, vil verdien `37` legges til som neste egenskap og Plazma vil initialiseres.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indikerer at dette argumentet ikke er innebygd i JVM, men er et tilpasset argument for Plazma,

Hvis ingen verdi er angitt, blir verdien [`true` som standard.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight-serien serverplattformer har punktum i egenskapsnavnene for å skille systemegenskapene for hver plattform.**

Noen terminaler som Windows Powershell kan ikke godta disse argumentene, så du må legge til `"` i endene av argumentene. [^4]

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

**`/reload`-kommandoen er veldig ustabil, så alle problemer som oppstår etter bruk av `/reload` er brukerens ansvar.**

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

Deaktiverer grensen på 128 pluginkanaler per spiller[^5].

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

- **Type**: `Heltall`
- **Standardverdi**: `750`

Del opp enheter i flere pakker for overføring hvis antallet overstiger denne verdien.

#### `Paper.filterThreshold`

- **Type**: `Heltall`
- **Standardverdi**: `8192`

Setter maksimal størrelse på pakker som serveren kan motta.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolsk`
- **Standardverdi**: `False`

Deaktiverer Java-versjonskontrollen.

{% hint style="danger" %}

**Dette kan føre til at JVM prøver å få tilgang til ikke-eksisterende kode!**

Dette kan permanent skade filer i verden og ødelegge spillets mekanikk.

Enhver skade forårsaket av dette er brukerens ansvar, og Plamza gir ingen støtte for det.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Heltall`
- **Standardverdi**: `64`

Setter begrensningen for navn på plugin-kanaler[^6].

#### `Paper.maxSignLength`

- **Type**: `Heltall`
- **Standardverdi**: `80`

Setter maksimal lengde for tekst på et skilt.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Heltall`
- **Standardverdi**: `(verden versjon) + 1`

Setter versjonen for informasjon om verden som skal initialiseres først.

Nyttig for store mengder blokker som må oppdateres, men sjelden brukt ellers.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolsk`
- **Standardverdi**: `True`

Aktiverer behandling av kommentarer i YAML-filer som standard.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Heltall`
- **Standardverdi**: `30`

Kaster ut spillere som ikke sender data innen angitt tid (i sekunder).

Vanligvis sender spillet[^7] kontinuerlig [hjerteslagssignaler](#user-content-fn-8)[^8] til serveren, så spillere blir ikke kastet ut,\
men hvis spillet ikke svarer, antas det å ha krasjet og spilleren kastes ut.

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

{% hint style="warning" %}

**Denne egenskapen vil bli flyttet til startargumenter etter 1.20.5.**

{% endhint %}

Øker konfigurasjonsoptimaliseringen som brukes ved oppstart.

Når aktivert, vil serveren bli raskere og sikrere, men det kan blokkere noen funksjoner eller ha stor innvirkning på spillopplevelsen.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolsk`
- **Standardverdi**: `false`

Undertrykker advarsler[^11] som vises når Plazma initialiseres.

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

Setter navn og plassering for [Bukkit-konfigurasjonsfilen](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Standardverdi**: `commands.yml`

Setter navn og plassering for [Bukkit-kommandokonfigurasjonsfilen](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Standardverdi**: `server.properties`

Setter navn og plassering for [serveregenskapsfilen](../reference/configurations/property.md).

#### `demo`

Starter serveren i demomodus.

#### `eraseCache`

Fjerner gjenværende hurtigbufferfiler etter verdenoppgradering.

#### `forceUpgrade`

Tvinger oppgradering av verdenen, uavhengig av versjonen, [oppgradering](#user-content-fn-12)[^12].

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

Setter maksimalt tillatte antall [spillere](#user-content-fn-14)[^14].

#### `nogui`

Deaktiverer det grafiske grensesnittspanelet.

#### `nojline`

Deaktiver JLine og bruk vanlig konsoll.

#### `online-mode`

- **Alias**: `o`
- **Standardverdi**: `(serveregenskap)`

Velg om spillerne skal valideres mot Mojangs autentiseringsserver.

**Hvis du ikke bruker Velocity eller andre proxyer, kan du bli straffet for brudd på [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Standardverdi**: `paper.yml`

{% hint style="warning" %}

**Dette argumentet er ikke lenger i bruk etter 1.19.4.**

{% endhint %}

Setter plasseringen av den utdaterte PaperSpigot konfigurasjonsfilen.

Denne brukes til å flytte eksisterende konfigurasjon til en ny fil, og brukes ikke etter dette.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standardverdi**: `config`

Setter navn og plassering av mappen der [Paper konfigurasjonsfiler](../reference/configurations/paper/README.md) befinner seg.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Setter navn og plassering av mappen der [Plazma konfigurasjonsfiler](../reference/configurations/plazma/README.md) befinner seg.

#### `plugins`

- **Alias**: `p`
- **Standardverdi**: `plugins`

Setter plasseringen av plugin-mappen.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardverdi**: `pufferfish.yml`

Setter navn og plassering av [Pufferfish konfigurasjonsfilen](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardverdi**: `purpur.yml`

Setter navn og plassering av [Purpur konfigurasjonsfilen](../reference/configurations/purpur/README.md).

#### `safeMode`

Starter serveren i fullstendig vaniljemodus.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standardverdi**: `(serveregenskap)`

Setter vertens navn eller [Internet Protocol](#user-content-fn-13) adresse for serveren.

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

Setter navn og plassering av [Spigot konfigurasjonsfilen](../reference/configurations/spigot.md).

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

[^13]: Internet Protocol, IP.

[^14]: Administratorer på `nivå 2` eller høyere er unntatt.
