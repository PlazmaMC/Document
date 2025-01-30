---
description: Aprengui sobre els arguments d'inici i les propietats del sistema.
---

# 🎛️ Arguments d'inici i propietats

Els arguments d'inici i les propietats del sistema són valors afegits a l'[ordre utilitzada per executar Plazma](#user-content-fn-1)[^1], i tenen un impacte general en el funcionament de Plazma.

[Posició afegida a la comanda](#user-content-fn-2)[^2] que es divideix en **paràmetres d'inici** i **proprietats del sistema**.

***

## Propietats del sistema <a href="#id-1" id="id-1"></a>

Les propietats del sistema es col·loquen davant de `-jar` i es processen pel JVM abans que Plazma s'inicialitzi.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Ús <a href="#id-1.1" id="id-1.1"></a>

Les propietats del sistema s'introdueixen com a arguments de comandament de Java entre `java` i `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indica que l'argument no està integrat al JVM sinó que és un argument exclusiu afegit a Plazma,

Si no s'introdueix cap valor als paràmetres, el valor es fixa a [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Valor per defecte**: `750`

Divideix l'enviament d'entitats en paquets múltiples si supera el valor establert.

#### `Paper.filterThreshold`

- **형태**: `Integer`
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

- **형태**: `Integer`
- **Valor per defecte**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Valor per defecte**: `80`

Estableix la longitud màxima de caràcters per línia en els rètols.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Valor per defecte**: `(versió del món) + 1`

Estableix la versió de la informació de l'actualització del món que es carregarà primer.

Útil en casos on cal actualitzar una gran quantitat de chunks, però no s'utilitza en altres situacions.

#### `Paper.parseYamlCommentsByDefault`

- **Tipus**: `Boolean`
- **Valor per defecte**: `Cert`

Activa el tractament dels comentaris YAML per defecte.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Valor per defecte**: `30`

Quan un jugador no envia cap dada durant el temps especificat (en segons), es desconnecta.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Conflicte**: `Plazma.disableConfigOptimization`

Optimitza la configuració inicial de forma més agressiva.

Activar això farà que el servidor sigui més ràpid i segur, però pot tenir un gran impacte en el joc.

#### `Plazma.disableConfigOptimization`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`
- **Conflicte**: `Plazma.aggressiveOptimize`

No optimitza la configuració inicial.

Això fa servir la configuració bàsica de Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`

Desactiva la marca Plazma i fa servir el favicon del servidor com a valor predeterminat de la vainilla.

#### `Plazma.useVanillaConfiguration`

- **Tipus**: `Boolean`
- **Valor per defecte**: `fals`
- **Conflicte**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Això pot tenir un gran impacte en la seguretat i el rendiment del servidor.

Totes les qüestions que es produeixin amb aquesta propietat són responsabilitat de l'administrador del servidor.
{% endhint %}

Fornir la configuració inicial amb els valors predeterminats de Mojang.

Això desactiva totes les correccions de vulnerabilitats aplicades a Paper.

Les correccions de vulnerabilitats es poden tornar a activar en la configuració de Paper o Plazma.

#### `Plazma.vanillaize`

- **Tipus**: `Boolean`
- **Valor predeterminat**: `true`
- **Conflicte**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Configura la configuració inicial per ser més semblant a la vainilla.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Àlies**: `c`
- **Valor per defecte**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Àlies**: `c`
- **Valor per defecte**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Inicia el servidor com a món de demostració.

#### `eraseCache`

Elimina els fitxers de memòria cau restants després d'actualitzar el món.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Desactiva el panell d'interfície gràfica.

#### `nojline`

Desactiva JLine i utilitza la consola de vanil·la.

#### `online-mode`

- **Àlies**: `o`
- **Valor per defecte**: `(proprietats del servidor)`

Selecciona si es validen els jugadors amb el servidor d'autenticació de Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

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

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Àlies**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Àlies**: `p`
- **Valor per defecte**: `plugins`

Configura la ubicació de la carpeta de plugins.

#### `pufferfish-settings`

- **Àlies**: `pufferfish`
- **Valor per defecte**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Àlies**: `purpur`
- **Valor per defecte**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Inicia el servidor en mode segur, com si fos vanil·la.

#### `server-ip`

- **Àlies**: `h`, `host`
- **Valor per defecte**: `(proprietats del servidor)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Els administradors de nivell 2 o superior estan exclosos.

[^14]: Protocol d'Internet, IP.
