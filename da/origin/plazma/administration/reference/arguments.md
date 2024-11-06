---
description: Få kendskab til startargumenter og systemegenskaber.
---

# 🎛️ Argumenter og egenskaber

Startargumenter og systemegenskaber er værdier, der tilføjes kommandoer, der bruges til at køre Plazma, og de har en overordnet indvirkning på Plazmas funktion.

I henhold til **startargumenter** og **systemegenskaber** opdelt efter placeringen, der tilføjes til kommandoen (se [fn-2](#user-content-fn-2)).

***

## Systemegenskaber <a href="#id-1" id="id-1"></a>

Systemegenskaber, der indtastes foran `-jar`, behandles af JVM før Plazma initialiseres.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Brugsanvisning <a href="#id-1.1" id="id-1.1"></a>

Systemegenskaber indtastes som Java-kommandoargumenter mellem `java` og `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` angiver, at argumentet ikke er indbygget i JVM, men er et dedikeret argument til Plazma og

Hvis der ikke angives nogen værdi for egenskaben, vil værdien være fastsat til `true` (se [fn-3](#user-content-fn-3)).

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Standardværdi**: `750`

Opdeler entiteter i flere pakker, hvis de overstiger den angivne værdi.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Standardværdi**: `8192`

Indstiller størrelsen på den maksimale pakke, serveren kan modtage ad gangen.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolesk`
- **Standardværdi**: `Falsk`

Deaktiverer Java-versionkontrol.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Dette kan permanent beskadige filer som verdener og ødelægge spillets mekanik.

Enhver skade forårsaget af dette er dit eget ansvar, og Plamza yder ingen support i den henseende.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Standardværdi**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Standardværdi**: `80`

Indstiller den maksimale længde af tekst på et skiltlinje.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Standardværdi**: `(verdensversion) + 1`

Indstiller versionen for de første datafixes, der skal initialiseres.

Nyttig, hvis der er behov for at opdatere store mængder chunks, men ellers ikke bruges.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolesk`
- **Standardværdi**: `Sandt`

Aktiverer behandlingen af YAML-filkommentarer som standard.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Standardværdi**: `30`

Spilleren bliver kicket, hvis der ikke modtages nogen data i det angivne antal sekunder.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Konflikt**: `Plazma.disableConfigOptimization`

Øger den oprindelige konfiguration mere effektivt.

Aktivering vil få serveren til at køre hurtigere og mere sikkert, men det kan have en stor indvirkning på spiloplevelsen.

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolesk`
- **Standardværdi**: `false`
- **Konflikt**: `Plazma.aggressiveOptimize`

Optimerer ikke den oprindelige konfiguration så aggressivt.

Dette bruger standardkonfigurationen fra Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolesk`
- **Standardværdi**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolesk`
- **Standardværdi**: `false`

Deaktiverer Plazma branding og bruger en simpel vaniljeserver favicon.

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolesk`
- **Standardværdi**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Dette kan have stor indvirkning på serverens sikkerhed og ydeevne.

Enhver problem opstået ved brug af denne egenskab er serveradministratorens ansvar.
{% endhint %}

Giver den oprindelige konfiguration med standardværdier fra Mojang.

Dette deaktiverer alle sårbarhedspatches, som Paper har implementeret.

Sårbarhedspatches kan genaktiveres i Paper eller Plazma konfiguration.

#### `Plazma.vanillaize`

- **Type**: `Boolesk`
- **Standardværdi**: `true`
- **Konflikt**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Gør den oprindelige konfiguration mere vanilla-nær.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Standard**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Standard**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Starter serveren i demotilstand.

#### `eraseCache`

Fjerner eventuelle cache-filer efter en verdensopgradering.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Deaktiverer det grafiske brugergrænsefladepanel.

#### `nojline`

Deaktiver JLine og brug standard konsollen.

#### `online-mode`

- **Alias**: `o`
- **Standard**: `(serveregenskab)`

Vælg om spillerne skal valideres mod Mojangs godkendelsesserver.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Standardværdi**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Angiver placeringen af den deaktiverede PaperSpigot konfigurationsfil.

Denne bruges til at flytte eksisterende konfiguration til en ny fil og er ikke længere i brug.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standardværdi**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Standardværdi**: `plugins`

Angiver placeringen af plugins-mappen.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardværdi**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardværdi**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Starter serveren i fuld standardtilstand som om det var ren vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standard**: `(serveregenskab)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Administratorer på niveau 2 eller højere er undtaget.

[^14]: Internet Protocol, IP.
