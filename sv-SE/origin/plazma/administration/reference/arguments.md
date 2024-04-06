---
description: Lär dig om startargument och systemegenskaper.
---

# 🎛️ Argument och egenskaper

Startvariabler och systemegenskaper är värden som läggs till [kommandon som används](#user-content-fn-1)[^1] för att ändra värden som inte kan ändras efter att Plazma har startats.

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

Om du till exempel vill använda systemegenskapen `Plazma.dummyProperty`,
då initieras Plazma med värdet `37` efter att du har angett det som följande.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indikerar att det är ett dedikerat argument för Plazma och inte en inbyggd JVM-argument,

Om inga värden anges för egenskaperna kommer de att vara [`true` som standardvärde](#user-content-fn-3)[^3].

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

I vissa terminaler som Windows Powershell kan dessa argument inte vara tillåtna, så du måste lägga till `"` i början och slutet av argumenten [för att undvika](#user-content-fn-4)[^4].

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

Inaktivera begränsningen av antalet kanaler för 128 plugin per [spelare](#user-content-fn-5)[^5].

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

- **Typ**: `Integer`
- **Standardvärde**: `750`

Dela upp entiteter i flera paket om de är fler än det angivna värdet.

#### `Paper.filterThreshold`

- **Typ**: `Integer`
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

- **Typ**: `Integer`
- **Standardvärde**: `64`

Ställ in begränsningen för namnen på plugin [kanaler](#user-content-fn-5)[^5].

#### `Paper.maxSignLength`

- **Typ**: `Integer`
- **Standardvärde**: `80`

Ställer in max längd för text på en skyltlinje.

#### `Paper.minPrecachedDatafixVersion`

- **Typ**: `Integer`
- **Standardvärde**: `(world version) + 1`

Ställer in versionen för uppdateringsinformation som ska initialiseras först.

Användbart vid massuppdatering av chunkar men annars sällan använt.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Standardvärde**: `True`

Aktiverar hantering av YAML-filkommentarer som standard.

#### `Paper.playerConnection.keepAlive`

- **Typ**: `Integer`
- **Standardvärde**: `30`

Spelaren kastas ut om ingen data har mottagits inom den angivna tiden (i sekunder).

Vanligtvis fortsätter [spelet](#user-content-fn-7)[^7] att skicka [hjärtslagsignaler](#user-content-fn-8)[^8] till servern, så om spelet inte svarar betraktas det som kraschat och spelaren kommer att bli utkastad utan att vara [bannad](#user-content-fn-9)[^9].

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

{% hint style="warning" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Ökar konfigurationsoptimeringarna som tillämpas vid första starten.

När du aktiverar det blir servern snabbare och säkrare, men det kan blockera vissa funktioner eller påverka spelupplevelsen negativt.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Standardvärde**: `false`

Hämmar varningsmeddelandet som visas när Plazma [initialiseras](#user-content-fn-11)[^11].

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

Ange namn och plats för [Bukkit-konfigurationsfilen](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Standardvärde**: `commands.yml`

Ange namn och plats för [Bukkit-kommandokonfigurationsfilen](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Standardvärde**: `server.properties`

Ange namn och plats för [serveregenskapsfilen](../reference/configurations/property.md).

#### `demo`

Startar servern i demovärlden.

#### `eraseCache`

Tar bort eventuella cache-filer som finns kvar efter en världsuppdatering.

#### `forceUpgrade`

Tvingar uppgradering av världen utan att ta hänsyn till versionen ([^12]).

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

Ställer in det maximala antalet tillåtna [spelare](#user-content-fn-14).

#### `nogui`

Inaktiverar den grafiska användargränssnittspanelen.

#### `nojline`

Inaktiverar JLine och använder en vanlig konsol istället.

#### `online-mode`

- **Alias**: `o`
- **Standardvärde**: `(serveregenskaper)`

Väljer om spelare ska verifieras mot Mojangs autentiseringsservrar.

**Om du inte använder Velocity eller en proxy kan du bli straffad för att bryta mot [EULA](../getting-started/README.md#id-5).**

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

Ställer in namn och plats för mappen där [Paper-konfigurationsfilen](../reference/configurations/paper/README.md) finns.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Ställer in namn och plats för mappen där [Plazma-konfigurationsfilen](../reference/configurations/plazma/README.md) finns.

#### `plugins`

- **Alias**: `p`
- **Standardvärde**: `plugins`

Ställer in platsen för plugin-mappen.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardvärde**: `pufferfish.yml`

Ställer in namn och plats för [Pufferfish-konfigurationsfilen](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardvärde**: `purpur.yml`

Ställer in namn och plats för [Purpur-konfigurationsfilen](../reference/configurations/purpur/README.md).

#### `safeMode`

Startar servern i fullständigt vaniljläge (säkert läge).

#### `server-ip`

- **Alias**: `h`, `host`
- **Standardvärde**: `(serveregenskaper)`

Ställer in serverns värdnamn eller [IP-adress](#user-content-fn-13).

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

Ställer in namn och plats för [Spigot-konfigurationsfilen](../reference/configurations/spigot.md).

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

[^13]: Internetprotokoll, IP.

[^14]: Administratörer över `nivå 2` är undantagna.
