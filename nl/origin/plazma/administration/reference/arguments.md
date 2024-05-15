---
description: Leer over de startargumenten en systeemeigenschappen.
---

# 🎛️ Argumenten en eigenschappen

De startparameters en systeemeigenschappen zijn waarden die worden toegevoegd aan de [opdracht die wordt gebruikt](#user-content-fn-1)[^1] voor het uitvoeren van Plazma, en hebben over het algemeen invloed op de werking van Plazma.

[De argumenten](#user-content-fn-2)[^2] worden verdeeld in **startparameters** en **systeemeigenschappen** volgens de toegevoegde positie van de opdracht.

***

## Systeemeigenschappen <a href="#id-1" id="id-1"></a>

Systeemeigenschappen worden voorafgaand aan de initialisatie van Plazma verwerkt in de JVM vóór `-jar`.

{% hint style="warning" %}

**Het wijzigen van systeemeigenschappen kan de werking van Plazma en JVM veranderen en kan een grote invloed hebben op het spel!**

Als je niet zeker weet welke rol elke systeemeigenschap speelt, **gebruik het dan absoluut niet!**

{% endhint %}

### Gebruik <a href="#id-1.1" id="id-1.1"></a>

Systeemeigenschappen worden ingevoerd als Java-opdrachtargumenten tussen `java` en `-jar`.

Bijvoorbeeld, als je de systeemeigenschap `Plazma.dummyProperty` wilt toepassen, wordt de volgende eigenschap ingesteld op `37` bij invoer, waardoor Plazma wordt geïnitialiseerd.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` geeft aan dat dit argument geen ingebouwd JVM-argument is maar een specifiek argument toegevoegd aan Plazma,

Als er geen waarden voor eigenschappen worden ingevoerd, wordt de waarde standaard ingesteld op [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**De Paperweight-serie serverplatforms gebruikt puntjes in de eigenschapsnamen om eigenschappen voor elk platform te onderscheiden.**

In sommige terminals zoals Windows Powershell kan het zijn dat deze argumenten niet worden geaccepteerd, dus moet je aan beide kanten van de argumenten `"` [toevoegen](#user-content-fn-4)[^4].

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

**Het gebruik van het `/reload` commando is zeer instabiel, dus alle problemen die zich voordoen na het gebruik van `/reload` zijn de verantwoordelijkheid van de gebruiker.**

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

Schakelt de limiet van 128 kanalen voor plug-ins die van toepassing zijn op elke speler [uit](#user-content-fn-5)[^5].

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

**Op deze manier kan JVM proberen toegang te krijgen tot niet-bestaande code!**

Dit kan leiden tot permanente schade aan de wereld en andere bestanden, en kan de werking van het spel volledig verstoren.

Alle problemen die voortvloeien uit het gebruik hiervan zijn de verantwoordelijkheid van de gebruiker en Plamza biedt geen ondersteuning hiervoor.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Integer`
- **Standaardwaarde**: `64`

Stelt de beperking in voor de naam van de plug-in [kanaal](#user-content-fn-6)[^6].

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

In de meeste gevallen blijft het [spel](#user-content-fn-7)[^7] voortdurend [hartslag signalen](#user-content-fn-8)[^8] naar de server sturen. Als het spel niet reageert, wordt het beschouwd als een crash en zal het de speler niet langer verwerken en zal de speler worden verbannen.

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
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`

Onderdrukt waarschuwingen die worden weergegeven bij het initialiseren van Plazma [uit](#user-content-fn-11)[^11].

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

{% hint style="danger" %}

**해당 속성은 패치된 모든 취약점을 되돌립니다!**

이는 서버 안전 및 성능에 크게 영향을 줄 수 있습니다.

해당 속성을 사용하여 발생하는 모든 문제는 서버 관리자에게 있습니다.

{% endhint %}

초기 구성을 Mojang에서 제공하는 기본값으로 제공합니다.

이는 Paper에서 적용한 모든 취약점 패치를 비활성화 합니다.

취약점 패치는 Paper 구성 또는 Plazma 구성에서 다시 활성화 할 수 있습니다.

#### `Plazma.vanillaize`

- **Type**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

**Dit argument is niet meer in gebruik na versie 1.19.4**

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
