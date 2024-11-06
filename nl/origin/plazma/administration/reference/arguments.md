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
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Gebruik <a href="#id-1.1" id="id-1.1"></a>

Systeemeigenschappen worden ingevoerd als Java-opdrachtargumenten tussen `java` en `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` geeft aan dat dit argument geen ingebouwd JVM-argument is maar een specifiek argument toegevoegd aan Plazma,

Als er geen waarden voor eigenschappen worden ingevoerd, wordt de waarde standaard ingesteld op [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Standaardwaarde**: `750`

Verdeelt entiteiten in meerdere pakketten als er meer zijn dan de ingestelde limiet.

#### `Paper.filterThreshold`

- **형태**: `Integer`
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

- **형태**: `Integer`
- **Standaardwaarde**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Standaardwaarde**: `80`

Stelt de maximale lengte in van tekst op een regel van een bord.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Standaardwaarde**: `(wereldversie) + 1`

Stelt de versie in van de wereldupdate-informatie die vooraf moet worden geïnitialiseerd.

Handig bij het updaten van grote hoeveelheden chunks maar anders niet gebruikt.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Standaardwaarde**: `True`

Activeert het verwerken van opmerkingen in YAML-bestanden standaard.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Standaardwaarde**: `30`

Als er gedurende de opgegeven tijd (in seconden) geen gegevens van de speler worden ontvangen, wordt de speler verwijderd.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Conflict**: `Plazma.disableConfigOptimization`

Optimaliseer de initiële configuratie sterker.

Als geactiveerd, zal de server sneller en veiliger worden, maar kan het een grote impact hebben op het spelplezier.

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`
- **Conflict**: `Plazma.aggressiveOptimize`

Optimaliseer de initiële configuratie niet.

Gebruik de standaardconfiguratie van Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`

Schakel de Plazma branding uit en gebruik de standaard server favicon van Vanilla.

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolean`
- **Standaardwaarde**: `false`
- **Conflict**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Dit kan aanzienlijke invloed hebben op de veiligheid en prestaties van de server.

Alle problemen die ontstaan door het gebruik van deze eigenschap zijn de verantwoordelijkheid van de serverbeheerder.
{% endhint %}

Voorzie de initiële configuratie van standaardwaarden verstrekt door Mojang.

Schakel alle kwetsbaarheidspatches die door Paper zijn toegepast uit.

Kwetsbaarheidspatches kunnen opnieuw worden geactiveerd in Paper-configuratie of Plazma-configuratie.

#### `Plazma.vanillaize`

- **Type**: `Boolean`
- **Standaardwaarde**: `true`
- **Conflict**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Configureer de initiële configuratie om dichter bij Vanilla te zijn.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Standaardwaarde**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Standaardwaarde**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Start de server in demomodus.

#### `eraseCache`

Verwijdert overgebleven cachebestanden na een wereldupgrade.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Schakelt het grafische gebruikersinterfacepaneel uit.

#### `nojline`

Schakelt JLine uit en gebruikt de standaardconsole.

#### `online-mode`

- **Alias**: `o`
- **Standaardwaarde**: `(servereigenschap)`

Kiest of spelers moeten worden geverifieerd via de Mojang-verificatieserver.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

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

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Standaardwaarde**: `plugins`

Stelt de locatie van de plug-inmap in.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standaardwaarde**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Standaardwaarde**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Start de server in de veilige modus, in een volledig standaardstatus.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standaardwaarde**: `(servereigenschap)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Beheerders van niveau 2 en hoger zijn uitgesloten.

[^14]: Internet Protocol, IP.
