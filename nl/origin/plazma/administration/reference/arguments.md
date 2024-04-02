---
description: Leer over de startargumenten en systeemeigenschappen.
---

# 🎛️ Argumenten en eigenschappen

Startvariabelen en systeemeigenschappen zijn waarden die worden toegevoegd aan de [opdrachten](#user-content-fn-1)[^1] die worden gebruikt bij het uitvoeren van Plazma, waardoor het mogelijk is om waarden te wijzigen die niet kunnen worden gewijzigd nadat Plazma is gestart.

Afhankelijk van de [locatie waar de opdracht wordt toegevoegd](#user-content-fn-2)[^2], worden ze verdeeld in **startargumenten** en **systeemeigenschappen**.

***

## Systeemeigenschappen <a href="#id-1" id="id-1"></a>

Systeemeigenschappen worden voorafgaand aan de initialisatie van Plazma verwerkt in de JVM vóór `-jar`.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### Gebruik <a href="#id-1.1" id="id-1.1"></a>

Systeemeigenschappen worden ingevoerd als Java-opdrachtargumenten tussen `java` en `-jar`.

Bijvoorbeeld, als u de systeemeigenschap `Plazma.dummyProperty` wilt toepassen, wordt de volgende eigenschap als `37` ingevoerd en wordt Plazma geïnitialiseerd.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` geeft aan dat dit argument geen ingebouwd JVM-argument is maar een specifiek argument toegevoegd aan Plazma,

als er geen waarde voor de eigenschap wordt ingevoerd, wordt de waarde [`true` vastgezet.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

{% endhint %}

### Alle systeemeigenschappen <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Bijwerken van stopgezette bordopmaak.

#### `debug.entities`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Activeer debuglogs voor entiteitsinformatie.

#### `debug.rewriteForIDE`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt NMS-revisie uit voor correct laden van debuginformatie in IDE en remapt automatisch interne versie-informatie.

#### `disable.watchdog`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt het Watchdog-waarschuwingssysteem van Spigot uit.

#### `letMeReload`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt de bevestigingsberichten voor de `/reload`-opdracht uit.

{% hint style="danger" %}

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Als u een plug-inontwikkelaar bent en uw plug-ins moet bijwerken, gebruik dan hotswapping in plaats van `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt plug-ins die standaard in- en uitvoer gebruiken uit.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Waarschuwt wanneer verouderde opmaak wordt gedetecteerd in chatcomponenten.

#### `Paper.bypassHostCheck`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt de serverpatroonvalidatie uit wanneer een speler verbinding maakt met de server.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Activeert debuglogs voor ontbrekende sleutels in NBT-objecten.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Activeert debuglogs voor hoofdblokken met ongeldige profielinformatie.

Logt alle ongeldige hoofdblokken in de wereld samen met hun locatie.

#### `Paper.disableChannelLimit`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt de limiet van 128 plug-inkanalen per speler uit.

#### `Paper.disableClassPrioritization`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt het prioriteren van plug-inklassen uit.

Handig bij problemen met plug-inshades.

#### `Paper.disableFlushConsolidate`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt Netty flush consolidation uit.

#### `Paper.excessiveTELimit`

- **Type**: `Integer`
- **Standaardwaarde**: `750`

Verdeelt entiteiten in meerdere pakketten als er meer zijn dan de ingestelde limiet.

#### `Paper.filterThreshold`

- **Type**: `Integer`
- **Standaardwaarde**: `8192`

Stelt de maximale grootte van pakketten in die de server tegelijk kan ontvangen.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Schakelt Java-versiecontrole uit.

{% hint style="danger" %}

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Dit kan leiden tot permanente schade aan de wereld en andere bestanden, en kan de werking van het spel volledig verstoren.

Alle problemen die voortvloeien uit het gebruik hiervan zijn de verantwoordelijkheid van de gebruiker en Plamza biedt geen ondersteuning hiervoor.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Integer`
- **Standaardwaarde**: `64`

Stelt de limiet in voor de naam van plug-inkanalen.

#### `Paper.maxSignLength`

- **Type**: `Integer`
- **Standaardwaarde**: `80`

Stelt de maximale lengte in van tekst op een regel van een bord.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Integer`
- **Standaardwaarde**: `(wereldversie) + 1`

Stelt de versie in van de wereldupdate-informatie die vooraf moet worden geïnitialiseerd.

Handig bij het updaten van grote hoeveelheden chunks maar anders niet gebruikt.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Standaardwaarde**: `True`

Activeert het verwerken van opmerkingen in YAML-bestanden standaard.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Integer`
- **Standaardwaarde**: `30`

Als er gedurende de opgegeven tijd (in seconden) geen gegevens van de speler worden ontvangen, wordt de speler verwijderd.

Normaal gesproken blijft het spel[^7] hartslagsignalen naar de server sturen, dus [wordt de speler niet verwijderd,](#user-content-fn-8)[^8] maar als het spel niet reageert, wordt aangenomen dat het is vastgelopen en wordt de speler verwijderd zonder verdere verwerking op de server.

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Negeert opmerkingen in servereigenschappen.

#### `Paper.debug-sync-loads`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Activeert debuglogs voor synchronisatie van chunks.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Activeert het standaard chunk-schrijfsysteem van Minecraft.]\(#user-content-fn-10)[^10]

Dit slaat elk chunk op in volgorde van verwerking, wat resulteert in aanzienlijke prestatievermindering.

#### `Paper.explicit-flush`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Activeert Explicit Flushing voor netwerkkanalen.

#### `Paper.strict-thread-checks`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Registreert altijd fouten die niet op de hoofdthread optreden.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Geeft een waarschuwing als geplande taken te lang moeten wachten.

#### `Paperclip.patchOnly`

- **Type**: `Boolean`
- **Standaardwaarde**: `False`

Wanneer u de standaard uitvoerbaar gebruikt, past u alleen patches toe zonder de server te starten.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`

{% hint style="warning" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Past strengere configuratie-optimalisaties toe bij de eerste start.

Als u het activeert, zal de server sneller en veiliger worden, maar het kan sommige glitches blokkeren of een grote invloed hebben op het gamen.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`

Onderdrukt de waarschuwing[^11] die wordt weergegeven wanneer Plazma wordt geïnitialiseerd.

### Gebruikte eigenschap <a href="#id-1.3" id="id-1.3"></a> is stopgezet

De volgende systeemeigenschappen zijn stopgezet.

#### `timings.bypassMax`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`
- **Stopgezet**: Timings is verwijderd uit Plazma sinds

Beslist of de waarde die naar Aikar's Timings API wordt gestuurd de maximale waarde mag overschrijden.

Als dit niet wordt afgehandeld in de API, wordt er een snelheidslimiet toegepast.

***

## Startargument <a href="#id-2" id="id-2"></a>

Het startargument wordt na `-jar *.jar` ingevoerd om Plazma te initialiseren en samen te verwerken.

### Gebruiksaanwijzing <a href="#id-2.1" id="id-2.1"></a>

Systeemeigenschappen worden ingevoerd als programmacommando-argumenten achter `-jar *.jar`.

Bijvoorbeeld, als u het startargument `nogui` wilt toepassen,\
voert u het als volgt in, zodat Plazma het argument `nogui` verwerkt tijdens de initialisatie.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Volledig startargument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Standaardwaarde**: `bukkit.yml`

Stelt de naam en locatie van het [Bukkit configuratiebestand](../reference/configurations/bukkit.md) in.

#### `command-settings`

- **Alias**: `c`
- **Standaardwaarde**: `commands.yml`

Stelt de naam en locatie van het [Bukkit commando configuratiebestand](../reference/configurations/bukkit.md) in.

#### `config`

- **Alias**: `c`
- **Standaardwaarde**: `server.properties`

Stelt de naam en locatie van het [servereigenschappen](../reference/configurations/property.md) bestand in.

#### `demo`

Start de server in demomodus.

#### `eraseCache`

Verwijdert overgebleven cachebestanden na een wereldupgrade.

#### `forceUpgrade`

Forceert een [upgrade](#user-content-fn-12)[^12] van de wereld, ongeacht de versie.

#### `help`

- **Alias**: `?`

Geeft alle startargumenten en beschrijvingen van Plazma weer.

#### `initSettings`

Maakt alleen de configuratiebestanden aan en sluit de server af.

#### `jfrProfile`

Activeert JFR-profilering.

#### `max-players`

- **Alias**: `s`, `size`
- **Standaardwaarde**: `(servereigenschap)`

Stelt het maximale aantal [spelers](#user-content-fn-14)[^14] in dat is toegestaan.

#### `nogui`

Schakelt het grafische gebruikersinterfacepaneel uit.

#### `nojline`

Schakelt JLine uit en gebruikt de standaardconsole.

#### `online-mode`

- **Alias**: `o`
- **Standaardwaarde**: `(servereigenschap)`

Kiest of spelers moeten worden geverifieerd via de Mojang-verificatieserver.

**Als u geen Velocity of andere proxy gebruikt, kunt u worden gestraft voor het schenden van de [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Standaardwaarde**: `paper.yml`

{% hint style="warning" %}

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

{% endhint %}

Stelt de locatie in van het stopgezette PaperSpigot configuratiebestand.

Dit wordt gebruikt om oude configuratie naar een nieuw bestand te migreren en wordt daarna niet meer gebruikt.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standaardwaarde**: `config`

Stelt de naam en locatie in van de map waarin [Paper configuratiebestanden](../reference/configurations/paper/README.md) zich bevinden.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Stelt de naam en locatie in van de map waarin [Plazma configuratiebestanden](../reference/configurations/plazma/README.md) zich bevinden.

#### `plugins`

- **Alias**: `p`
- **Standaardwaarde**: `plugins`

Stelt de locatie van de plug-inmap in.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standaardwaarde**: `pufferfish.yml`

Stelt de naam en locatie in van het [Pufferfish configuratiebestand](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Standaardwaarde**: `purpur.yml`

Stelt de naam en locatie in van het [Purpur configuratiebestand](../reference/configurations/purpur/README.md).

#### `safeMode`

Start de server in de veilige modus, in een volledig standaardstatus.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standaardwaarde**: `(servereigenschap)`

Stelt de hostnaam van de server of het [Internet Protocol](#user-content-fn-13)[^13] adres in.

#### `server-port`

- **Alias**: `p`, `port`
- **Standaardwaarde**: `(servereigenschap)`

Stelt de poort van de server in.

#### `server-name`

- **Standaardwaarde**: `Een Plazma Server`

Stelt de naam van de server in.

#### `spigot-settings`

- **Alias**: `S`
- **Standaardwaarde**: `spigot.yml`

Stelt de naam en locatie in van het [Spigot configuratiebestand](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Geeft de Plazma-versie weer.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Standaardwaarde**: `(servermap)`

Stelt de locatie in waar wereldbestanden worden opgeslagen.

#### `world-name`

- **Alias**: `w`, `world`
- **Standaardwaarde**: `(servereigenschap)`

Stelt de naam van het wereldbestand in.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Afhankelijk van de toegevoegde locatie zal de locatie die de overname verwerkt veranderen.

[^3]: Bijvoorbeeld, als u `Plazma.iKnowWhatIAmDoing` op `true` wilt instellen (activeren), werkt het invoeren van `-DPlazma.iKnowWhatIAmDoing` in plaats van `-DPlazma.iKnowWhatIAmDoing=true` hetzelfde.

[^4]: Bijvoorbeeld, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Event detector.

[^6]: Event detector.

[^7]: Client.

[^8]: Een signaal dat aangeeft dat de server normaal verbonden is, zoals een hartslag.

[^9]: Met de AFK-kickfunctie van Purpur kunt u zelfs afwezige spelers verwijderen.

[^10]: Synchronisatie van chunk schrijfsysteem, Sync Chunk Write System.

[^11]: `WAARSCHUWING! Plazma kan onverwachte problemen veroorzaken, dus zorg ervoor dat u het grondig test voordat u het op een openbare server gebruikt.`

[^12]: In het spel werkt 'wereldoptimalisatie' op dezelfde manier.

[^13]: Internet Protocol, IP.

[^14]: Beheerders van niveau 2 en hoger zijn uitgesloten.
