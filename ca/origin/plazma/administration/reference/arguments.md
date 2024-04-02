---
description: Aprengui sobre els arguments d'inici i les propietats del sistema.
---

# 🎛️ Arguments d'inici i propietats

Els arguments d'inici i les propietats del sistema són valors afegits als [comandaments utilitzats](#user-content-fn-1)[^1] en l'execució de Plazma, permetent canviar valors que no es poden modificar després de l'execució de Plazma.

En funció de la [posició on s'afegeixen als comandaments](#user-content-fn-2)[^2], es divideixen en **arguments d'inici** i **proprietats del sistema**.

***

## Propietats del sistema <a href="#id-1" id="id-1"></a>

Les propietats del sistema es col·loquen davant de `-jar` i es processen pel JVM abans que Plazma s'inicialitzi.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### Ús <a href="#id-1.1" id="id-1.1"></a>

Les propietats del sistema s'introdueixen com a arguments de comandament de Java entre `java` i `-jar`.

Per exemple, si vol aplicar la propietat del sistema `Plazma.dummyProperty`, introduint `37` com a valor, es inicialitzarà Plazma de la següent manera.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indica que l'argument no està integrat al JVM sinó que és un argument exclusiu afegit a Plazma,

i si no s'indica cap valor, es fixarà a [`true` de manera predeterminada.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

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

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

Deshabilita la limitació de 128 canals de plugin per jugador[^5].

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

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Això pot causar danys permanents als arxius del món i provocar un mal funcionament general del joc.

L'usuari assumeix tota la responsabilitat dels problemes que puguin sorgir i Plamza no oferirà cap suport en aquest cas.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tipus**: `Enter`
- **Valor per defecte**: `64`

Estableix el límit de caràcters per als noms dels canals de plugins.

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

Normalment, el joc[^7] envia un [senyal de batut](#user-content-fn-8)[^8] al servidor de manera constant, per tant, no es desconnecta, però si el joc no respon, es considera que s'ha bloquejat i es desconnecta el jugador.

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

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Aplica una optimització de configuració més estricta en l'inici inicial.

En activar-ho, el servidor es torna més ràpid i segur, però pot bloquejar algunes mecàniques o tenir un gran impacte en el joc.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`

Suprimeix l'avís que es mostra en la inicialització de Plazma[^11].

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

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

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
