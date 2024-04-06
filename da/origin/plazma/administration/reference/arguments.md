---
description: Få kendskab til startargumenter og systemegenskaber.
---

# 🎛️ Argumenter og egenskaber

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

I henhold til **startargumenter** og **systemegenskaber** opdelt efter placeringen, der tilføjes til kommandoen (se [fn-2](#user-content-fn-2)).

***

## Systemegenskaber <a href="#id-1" id="id-1"></a>

Systemegenskaber, der indtastes foran `-jar`, behandles af JVM før Plazma initialiseres.

{% hint style="warning" %}

**Når du ændrer systemegenskaber, kan Plazma og JVM's adfærd ændres, hvilket kan have stor indflydelse på spillet!**

Hvis du ikke er sikker på, hvad hver systemegenskab gør, **må du under ingen omstændigheder bruge det!**

{% endhint %}

### Brugsanvisning <a href="#id-1.1" id="id-1.1"></a>

Systemegenskaber indtastes som Java-kommandoargumenter mellem `java` og `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` angiver, at argumentet ikke er indbygget i JVM, men er et dedikeret argument til Plazma og

Hvis der ikke angives nogen værdi for egenskaben, vil værdien være fastsat til `true` (se [fn-3](#user-content-fn-3)).

{% hint style="info" %}

**Paperweight-serverplatformen af hver type har punktum i egenskabsnavnet for at adskille systemegenskaberne fra hinanden.**

Nogle terminaler som f.eks. Windows Powershell tillader muligvis ikke disse argumenter, så det kan være nødvendigt at tilføje `"` i begge ender af argumentet (se [fn-4](#user-content-fn-4)).

{% endhint %}

### Alle systemegenskaber <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Opdaterer deaktiverede skiltformater.

#### `debug.entities`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Aktiverer debuglogs for entitetsinformation.

#### `debug.rewriteForIDE`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer NMS-revisionen for at kunne indlæse debugoplysninger korrekt i IDE'en og remapper automatisk interne versionsoplysninger.

#### `disable.watchdog`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer Spigots watchdog-advarselssystem.

#### `letMeReload`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer bekræftelsesbeskeden for `/reload`-kommandoen.

{% hint style="danger" %}

**`/reload`-kommandoen er meget ustabil, så alle problemer, der opstår efter brug af `/reload`, er brugerens eget ansvar.**

Hvis du er pluginudvikler og skal opdatere et plugin, skal du bruge hotswap i stedet for `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer brugen af standard input/output-systemet for plugins.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Advarer, når forældet formatering opdages i chatkomponenter.

#### `Paper.bypassHostCheck`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer validering af serverens mønster, når en spiller opretter forbindelse til serveren.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Aktiverer debuglogs for manglende nøgler i NBT-objekter.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Aktiverer debuglogs for ugyldige kranieprofiler.

Dette logger placeringen af alle ugyldige kranieblokke i verden.

#### `Paper.disableChannelLimit`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiver begrænsningen på antallet af 128 plugin-kanaler, der gælder for hver spiller (se [fn-5](#user-content-fn-5)).

#### `Paper.disableClassPrioritization`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer prioritering af pluginklasser.

Nyttig, hvis der er problemer med plugin-shading.

#### `Paper.disableFlushConsolidate`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer Netty's flush-consolidation-system.

#### `Paper.excessiveTELimit`

- **Type**: `Heltal`
- **Standardværdi**: `750`

Opdeler entiteter i flere pakker, hvis de overstiger den angivne værdi.

#### `Paper.filterThreshold`

- **Type**: `Heltal`
- **Standardværdi**: `8192`

Indstiller størrelsen på den maksimale pakke, serveren kan modtage ad gangen.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer Java-versionkontrol.

{% hint style="danger" %}

**Dette kan muligvis forsøge at tilgå kode, der ikke eksisterer i JVM!**

Dette kan permanent beskadige filer som verdener og ødelægge spillets mekanik.

Enhver skade forårsaget af dette er dit eget ansvar, og Plamza yder ingen support i den henseende.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Heltal`
- **Standardværdi**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Type**: `Heltal`
- **Standardværdi**: `80`

Indstiller den maksimale længde af tekst på et skiltlinje.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Heltal`
- **Standardværdi**: `(verdensversion) + 1`

Indstiller versionen for de første datafixes, der skal initialiseres.

Nyttig, hvis der er behov for at opdatere store mængder chunks, men ellers ikke bruges.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolesk`
- **Standardværdi**: `Sandt`

Aktiverer behandlingen af YAML-filkommentarer som standard.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Heltal`
- **Standardværdi**: `30`

Spilleren bliver kicket, hvis der ikke modtages nogen data i det angivne antal sekunder.

Normalt sender spillet fortsat et hjerteslagssignal til serveren, så spilleren ikke bliver udvist, men hvis spillet ikke svarer, betragtes det som en kollision, og serveren vil ikke længere behandle spilleren og vil udvise dem (se [fn-7](#user-content-fn-7), [fn-8](#user-content-fn-8), [fn-9](#user-content-fn-9)).

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Ignorerer kommentarer i serveregenskaberne.

#### `Paper.debug-sync-loads`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Aktiverer debuglogs for synkroniseret chunkgenerering.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Aktiverer Minecrafts [standard chunkgenereringssystem](#user-content-fn-10)[^10].

Dette gemmer hver chunk sekventielt, hvilket kan forårsage betydelig ydeevnenedgang.

#### `Paper.explicit-flush`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Aktiverer eksplisit flushing af netværkskanaler.

#### `Paper.strict-thread-checks`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Logger altid fejl, der ikke opstår på hovedtråden.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Advarer, hvis planlagte opgaver har overdreven ventetid.

#### `Paperclip.patchOnly`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Anvend kun patch uden at starte serveren, når du bruger den medfølgende eksekverbare fil.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolesk`
- **Standardværdi**: `false`

{% hint style="warning" %}

**Denne egenskab vil blive flyttet til startargumenter efter 1.20.5.**

{% endhint %}

Øger konfigurationsoptimeringen, der anvendes ved første start, mere strengt.

Når aktiveret, vil serveren blive hurtigere og mere sikker, men det kan blokere visse mekanismer eller have stor indflydelse på spiloplevelsen.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolesk`
- **Standardværdi**: `false`

Undertryk advarslen, der vises, når Plazma initialiseres (se [fn-11](#user-content-fn-11)).

### Afbrydende egenskab <a href="#id-1.3" id="id-1.3"></a>

Følgende systemegenskaber er afbrudte egenskaber.

#### `timings.bypassMax`

- **Type**: `Boolesk`
- **Standardværdi**: `false`
- **Afbrydet brug**: Timings blev fjernet fra Plazma

Bestemmer, om værdier, der sendes til Aikars Timings API, kan overstige det maksimale.

Selvom dette er tilfældet, vil ratebegrænsning blive anvendt, hvis der ikke håndteres undtagelser i API'en.

***

## Startargument <a href="#id-2" id="id-2"></a>

Startargumenter indtastes efter `-jar *.jar` for at initialisere Plazma og behandles sammen med det.

### Brugsanvisning <a href="#id-2.1" id="id-2.1"></a>

Systemegenskaber indtastes som programkommandoargumenter efter `-jar *.jar`.

Hvis du f.eks. vil anvende startargumentet `nogui`,\
skal du indtaste det som vist nedenfor, så Plazma kan behandle `nogui`-argumentet under initialiseringen.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Samlede startargumenter <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Standard**: `bukkit.yml`

Indstiller navn og placering af [Bukkit-konfigurationsfilen](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Standard**: `commands.yml`

Indstiller navn og placering af [Bukkit-kommandokonfigurationsfilen](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Standard**: `server.properties`

Indstiller navn og placering af [serveregenskabsfilen](../reference/configurations/property.md).

#### `demo`

Starter serveren i demotilstand.

#### `eraseCache`

Fjerner eventuelle cache-filer efter en verdensopgradering.

#### `forceUpgrade`

Opgraderer verdenen tvunget, uanset versionen, [se opgradering](#user-content-fn-12)[^12].

#### `help`

- **Alias**: `?`

Udskriver alle Plazmas startargumenter og beskrivelser.

#### `initSettings`

Opretter kun konfigurationsfiler og afslutter serveren.

#### `jfrProfile`

Aktiverer JFR-profilering.

#### `max-players`

- **Alias**: `s`, `size`
- **Standard**: `(serveregenskab)`

Indstiller det maksimale antal tilladte [spillere](#user-content-fn-14)[^14].

#### `nogui`

Deaktiverer det grafiske brugergrænsefladepanel.

#### `nojline`

Deaktiver JLine og brug standard konsollen.

#### `online-mode`

- **Alias**: `o`
- **Standard**: `(serveregenskab)`

Vælg om spillerne skal valideres mod Mojangs godkendelsesserver.

**Hvis du ikke bruger Velocity eller andre proxier, kan du blive sanktioneret for at overtræde [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Standardværdi**: `paper.yml`

{% hint style="warning" %}

**Dette argument er blevet stoppet med at blive brugt efter 1.19.4**

{% endhint %}

Angiver placeringen af den deaktiverede PaperSpigot konfigurationsfil.

Denne bruges til at flytte eksisterende konfiguration til en ny fil og er ikke længere i brug.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standardværdi**: `config`

Angiver navn og placering af mappen, hvor [Paper konfigurationsfiler](../reference/configurations/paper/README.md) er placeret.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Angiver navn og placering af mappen, hvor [Plazma konfigurationsfiler](../reference/configurations/plazma/README.md) er placeret.

#### `plugins`

- **Alias**: `p`
- **Standardværdi**: `plugins`

Angiver placeringen af plugins-mappen.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardværdi**: `pufferfish.yml`

Angiver navn og placering af [Pufferfish konfigurationsfilen](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardværdi**: `purpur.yml`

Angiver navn og placering af [Purpur konfigurationsfilen](../reference/configurations/purpur/README.md).

#### `safeMode`

Starter serveren i fuld standardtilstand som om det var ren vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standard**: `(serveregenskab)`

Angiver serverens værtsnavn eller [Internet Protocol](#user-content-fn-13) adresse.

#### `server-port`

- **Alias**: `p`, `port`
- **Standard**: `(serveregenskab)`

Angiver serverens portnummer.

#### `server-name`

- **Standardværdi**: `A Plazma Server`

Angiver serverens navn.

#### `spigot-settings`

- **Alias**: `S`
- **Standardværdi**: `spigot.yml`

Angiver navn og placering af [Spigot konfigurationsfilen](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Viser Plazma versionen.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Standardværdi**: `(servermappe)`

Angiver placeringen hvor verdensfilerne gemmes.

#### `world-name`

- **Alias**: `w`, `world`
- **Standard**: `(serveregenskab)`

Angiver navnet på verdensfilen.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Afhængigt af positionen behandles argumenterne anderledes.

[^3]: For eksempel, hvis du vil aktivere `Plazma.iKnowWhatIAmDoing` til `true`, fungerer det på samme måde, hvis du kun indtaster `-DPlazma.iKnowWhatIAmDoing`, i stedet for `-DPlazma.iKnowWhatIAmDoing=true`.

[^4]: For eksempel, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Event detector.

[^6]: Event detector.

[^7]: Client.

[^8]: Et signal der indikerer, at forbindelsen til serveren fungerer korrekt, ligesom et hjerteslag.

[^9]: Med Purpurs AFK kick-funktion kan også spillere, der er inaktive, blive sparket.

[^10]: Sync Chunk Write System, synkroniseret chunk-skrivesystem.

[^11]: `ADVARSEL! Plazma kan forårsage uventede problemer, så sørg for at teste det grundigt, før du bruger det på en offentlig server.`

[^12]: I spillet fungerer 'verdensoptimering' på samme måde.

[^13]: Internet Protocol, IP.

[^14]: Administratorer på niveau 2 eller højere er undtaget.
