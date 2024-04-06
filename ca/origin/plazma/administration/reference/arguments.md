---
description: Aprengui sobre els arguments d'inici i les propietats del sistema.
---

# 🎛️ Arguments d'inici i propietats

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[Posició afegida a la comanda](#user-content-fn-2)[^2] que es divideix en **paràmetres d'inici** i **proprietats del sistema**.

***

## Propietats del sistema <a href="#id-1" id="id-1"></a>

Les propietats del sistema es col·loquen davant de `-jar` i es processen pel JVM abans que Plazma s'inicialitzi.

{% hint style="warning" %}

**La modificació de les propietats del sistema pot alterar el funcionament de Plazma i JVM i pot tenir un gran impacte en el joc!**

Si no esteu segurs del paper de cada propietat del sistema, **mai l'utilitzeu!**

{% endhint %}

### Ús <a href="#id-1.1" id="id-1.1"></a>

Les propietats del sistema s'introdueixen com a arguments de comandament de Java entre `java` i `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indica que l'argument no està integrat al JVM sinó que és un argument exclusiu afegit a Plazma,

Si no s'introdueix cap valor als paràmetres, el valor es fixa a [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**La plataforma del servidor de la sèrie Paperweight inclou un punt `.` al nom de cada propietat per diferenciar les propietats de cada plataforma.**

En algunes terminals com ara Windows Powershell, pot ser que no s'acceptin aquests paràmetres, així que cal afegir `"` al principi i al final dels paràmetres [com a mesura de precaució](#user-content-fn-4)[^4].

{% endhint %}

### Totes les propietats del sistema <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Actualitza el format dels rètols obsolets.

#### `debug.entities`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Activa els registres de depuració relacionats amb la informació de les entitats.

#### `debug.rewriteForIDE`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita la revisió de NMS per aconseguir que la informació de depuració es carregui correctament a l'IDE i remaptegi automàticament la informació de la versió interna.

#### `disable.watchdog`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita el sistema d'advertències Watchdog de Spigot.

#### `letMeReload`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita el missatge de confirmació del comandament `/reload`.

{% hint style="danger" %}

**La comanda `/reload` és molt inestable, per tant, qualsevol problema que es produeixi al servidor després d'utilitzar `/reload` serà responsabilitat de l'usuari.**

Si ets un desenvolupador de plugins i necessites actualitzar un plugin, utilitza l'hotswap en lloc de `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita els plugins que fan servir el sistema d'entrada i sortida estàndard.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Adverteix quan es detecta un format obsolet en els components de xat.

#### `Paper.bypassHostCheck`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita la verificació de coincidència del patró del servidor quan un jugador es connecta.

#### `Paper.debugDynamicMissingKeys`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Activa els registres de depuració per a claus que falten en objectes NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Activa els registres de depuració per a perfils de crani incorrectes.

Això registra tots els blocs de crani incorrectes al món amb les seves coordenades.

#### `Paper.disableChannelLimit`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Desactiva la limitació de 128 canals de plugins aplicats per jugador.

#### `Paper.disableClassPrioritization`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita el sistema de prioritat de classes de plugins.

Útil en cas de problemes amb els plugins ombra.

#### `Paper.disableFlushConsolidate`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita la consolidació de Netty flush.

#### `Paper.excessiveTELimit`

- **Tipus**: `Enter`
- **Valor per defecte**: `750`

Divideix l'enviament d'entitats en paquets múltiples si supera el valor establert.

#### `Paper.filterThreshold`

- **Tipus**: `Enter`
- **Valor per defecte**: `8192`

Estableix la mida màxima del paquet que el servidor pot rebre a la vegada.

#### `Paper.ignoreJavaVersion`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Deshabilita la comprovació de la versió de Java.

{% hint style="danger" %}

**Això pot provocar que JVM intenti accedir a codi inexistent!**

Això pot causar danys permanents als arxius del món i provocar un mal funcionament general del joc.

L'usuari assumeix tota la responsabilitat dels problemes que puguin sorgir i Plamza no oferirà cap suport en aquest cas.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tipus**: `Enter`
- **Valor per defecte**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Tipus**: `Enter`
- **Valor per defecte**: `80`

Estableix la longitud màxima de caràcters per línia en els rètols.

#### `Paper.minPrecachedDatafixVersion`

- **Tipus**: `Enter`
- **Valor per defecte**: `(versió del món) + 1`

Estableix la versió de la informació de l'actualització del món que es carregarà primer.

Útil en casos on cal actualitzar una gran quantitat de chunks, però no s'utilitza en altres situacions.

#### `Paper.parseYamlCommentsByDefault`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Cert`

Activa el tractament dels comentaris YAML per defecte.

#### `Paper.playerConnection.keepAlive`

- **Tipus**: `Enter`
- **Valor per defecte**: `30`

Quan un jugador no envia cap dada durant el temps especificat (en segons), es desconnecta.

Normalment, el [joc](#user-content-fn-7)[^7] envia de manera constant senyals de [latitut](#user-content-fn-8)[^8] al servidor, pel que no s'expulsa cap jugador, però si el joc no respon es considera que ha col·lisionat i ja no es processa el jugador al servidor, expulsant-lo.

#### `Paper.skipServerPropertiesComments`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Ignora els comentaris de les propietats del servidor.

#### `Paper.debug-sync-loads`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Activa els registres de depuració de la càrrega sincronitzada de chunks.

#### `Paper.enable-sync-chunk-writes`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Activa el sistema de [càrrega de chunks per defecte](#user-content-fn-10)[^10] de Minecraft.

Això provoca una gran disminució del rendiment ja que es guarda cada chunk de manera seqüencial.

#### `Paper.explicit-flush`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Activa l'expulsió explícita dels canals de xarxa.

#### `Paper.strict-thread-checks`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Registra sempre els errors que no es produeixin al fil principal.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Mostra una advertència si les tasques programades tenen un retard excessiu.

#### `Paperclip.patchOnly`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Fals`

Aplica només el patch sense iniciar el servidor quan s'utilitza l'executable predeterminat.

#### `Plazma.aggressiveOptimize`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`

{% hint style="warning" %}

**Aquesta propietat es traslladarà com a argument d'inici des de la versió 1.20.5 en endavant.**

{% endhint %}

Aplica una optimització de configuració més estricta en l'inici inicial.

En activar-ho, el servidor es torna més ràpid i segur, però pot bloquejar algunes mecàniques o tenir un gran impacte en el joc.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`

Inhibeix els [avisos](#user-content-fn-11)[^11] que es mostren quan s'inicialitza Plazma.

### Propietat obsoleta <a href="#id-1.3" id="id-1.3"></a>

Les propietats del sistema següents són obsoletes.

#### `timings.bypassMax`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`
- **Obsolet**: Des de la retirada de Timings de Plazma

Determina si es pot superar el valor màxim que es pot enviar a l'API de Timings d'Aikar.

Si això es fa i l'API no gestiona l'excepció, s'aplicarà el límit de velocitat.

***

## Argument d'inici <a href="#id-2" id="id-2"></a>

L'argument d'inici es posa després de `-jar *.jar` per inicialitzar Plazma i es processa conjuntament amb aquest valor.

### Ús <a href="#id-2.1" id="id-2.1"></a>

Les propietats del sistema s'introdueixen com arguments de comandament després de `-jar *.jar`.

Per exemple, si es vol aplicar l'argument d'inici `nogui`,\
introduïu-ho com a continuació perquè Plazma processi l'argument `nogui` durant la inicialització.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argument d'inici complet <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Àlies**: `b`
- **Valor per defecte**: `bukkit.yml`

Configura el nom i la ubicació del [fitxer de configuració de Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Àlies**: `c`
- **Valor per defecte**: `commands.yml`

Configura el nom i la ubicació del [fitxer de configuració de comandes de Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Àlies**: `c`
- **Valor per defecte**: `server.properties`

Configura el nom i la ubicació del fitxer de [proprietats del servidor](../reference/configurations/property.md).

#### `demo`

Inicia el servidor com a món de demostració.

#### `eraseCache`

Elimina els fitxers de memòria cau restants després d'actualitzar el món.

#### `forceUpgrade`

Actualitza el món a la [versió més recent](#user-content-fn-12)[^12] ignorant la versió actual.

#### `help`

- **Àlies**: `?`

Mostra tots els arguments d'inici de Plazma juntament amb les seves descripcions.

#### `initSettings`

Crea només els fitxers de configuració i tanca el servidor.

#### `jfrProfile`

Activa el perfilatge JFR.

#### `max-players`

- **Àlies**: `s`, `size`
- **Valor per defecte**: `(proprietats del servidor)`

Configura el nombre màxim de [jugadors](#user-content-fn-14)[^14] permesos.

#### `nogui`

Desactiva el panell d'interfície gràfica.

#### `nojline`

Desactiva JLine i utilitza la consola de vanil·la.

#### `online-mode`

- **Àlies**: `o`
- **Valor per defecte**: `(proprietats del servidor)`

Selecciona si es validen els jugadors amb el servidor d'autenticació de Mojang.

**En cas de no utilitzar Velocity o un servidor intermediari, es poden imposar sancions per incomplir l'[EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Àlies**: `paper`
- **Valor per defecte**: `paper.yml`

{% hint style="warning" %}

**Aquest argument s'ha deixat de utilitzar des de la versió 1.19.4**

{% endhint %}

Configura la ubicació del fitxer de configuració de PaperSpigot obsolet.

S'utilitza per traslladar la configuració antiga a un nou fitxer de configuració i ja no es fa servir.

#### `paper-settings-directory`

- **Àlies**: `paper-dir`
- **Valor per defecte**: `config`

Configura el nom i la ubicació de la carpeta on es troba el [fitxer de configuració de Paper](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Àlies**: `plazma-dir`

Configura el nom i la ubicació de la carpeta on es troba el [fitxer de configuració de Plazma](../reference/configurations/plazma/README.md).

#### `plugins`

- **Àlies**: `p`
- **Valor per defecte**: `plugins`

Configura la ubicació de la carpeta de plugins.

#### `pufferfish-settings`

- **Àlies**: `pufferfish`
- **Valor per defecte**: `pufferfish.yml`

Configura el nom i la ubicació del [fitxer de configuració de Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Àlies**: `purpur`
- **Valor per defecte**: `purpur.yml`

Configura el nom i la ubicació del [fitxer de configuració de Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Inicia el servidor en mode segur, com si fos vanil·la.

#### `server-ip`

- **Àlies**: `h`, `host`
- **Valor per defecte**: `(proprietats del servidor)`

Configura el nom de l'amfitrió del servidor o l'adreça [IP](#user-content-fn-13)[^13].

#### `server-port`

- **Àlies**: `p`, `port`
- **Valor per defecte**: `(proprietats del servidor)`

Configura el port del servidor.

#### `server-name`

- **Valor per defecte**: `Un servidor de Plazma`

Configura el nom del servidor.

#### `spigot-settings`

- **Àlies**: `S`
- **Valor per defecte**: `spigot.yml`

Configura el nom i la ubicació del [fitxer de configuració de Spigot](../reference/configurations/spigot.md).

#### `version`

- **Àlies**: `v`

Mostra la versió de Plazma.

#### `world-dir`

- **Àlies**: `W`, `universe`, `world-container`
- **Valor per defecte**: `(carpeta del servidor)`

Configura la ubicació on es guarden els fitxers del món.

#### `world-name`

- **Àlies**: `w`, `world`
- **Valor per defecte**: `(proprietats del servidor)`

Configura el nom del fitxer del món.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Depenent de la ubicació afegida, la ubicació de processament dels arguments canvia.

[^3]: Per exemple, si voleu establir (activar) `Plazma.iKnowWhatIAmDoing` com a `true`, en lloc de introduir `-DPlazma.iKnowWhatIAmDoing=true`, només cal introduir `-DPlazma.iKnowWhatIAmDoing` i funcionarà igualment.

[^4]: Per exemple, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detector d'esdeveniments.

[^6]: Detector d'esdeveniments.

[^7]: Client.

[^8]: Senyal que indica que està connectat correctament al servidor com un batec de cor.

[^9]: Utilitzant la funció d'expulsió AFK de Purpur, també es pot expulsar els jugadors absents.

[^10]: Sistema de escriptura de trossos sincronitzat, Sync Chunk Write System.

[^11]: \`ATENCIÓ! Plazma pot causar problemes inesperats, així que assegureu-vos de provar-ho a fons abans de fer servir un servidor públic.

[^12]: Aquesta optimització de món al joc també funciona amb aquest mateix principi.

[^13]: Protocol d'Internet, IP.

[^14]: Els administradors de nivell 2 o superior estan exclosos.
