---
description: Scopri gli argomenti di avvio e le proprietà di sistema.
---

# 🎛️ Argomenti di avvio e proprietà

Gli argomenti di avvio e le proprietà di sistema sono valori aggiunti al comando utilizzato per l'esecuzione di Plazma, che influenzano globalmente il funzionamento di Plazma.

In base alla posizione a cui si aggiungono i comandi (fn-2), verranno divisi in **argomento iniziale** e **attributi di sistema**.

***

## Proprietà di sistema <a href="#id-1" id="id-1"></a>

Le proprietà di sistema, inserite prima di `-jar`, sono valori elaborati dalla JVM prima dell'inizializzazione di Plazma.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Modalità d'uso <a href="#id-1.1" id="id-1.1"></a>

Le proprietà di sistema vengono inserite come argomenti di comando Java tra `java` e `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

Il prefisso `-D` indica che l'argomento non è integrato nella JVM ma è un argomento specifico aggiunto a Plazma,

Se non si inserisce alcun valore negli attributi, il valore sarà fissato a [`true`](fn-3).

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Proprietà di sistema complete <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Aggiorna i formati di cartelli dismessi.

#### `debug.entities`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Attiva i log di debug relativi alle informazioni sulle entità.

#### `debug.rewriteForIDE`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disabilita la revisione NMS per consentire un corretto caricamento delle informazioni di debug dall'IDE e riconfigura automaticamente le informazioni sulla versione interna.

#### `disable.watchdog`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva il sistema di avviso del Watchdog di Spigot.

#### `letMeReload`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva il messaggio di conferma del comando `/reload`.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Se sei uno sviluppatore di plugin e devi aggiornare un plugin, usa il ricaricamento a caldo anziché il comando `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva i plugin che utilizzano il sistema di input/output standard.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Avverte quando viene rilevato un formato obsoleto nella componente di chat.

#### `Paper.bypassHostCheck`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva la verifica della corrispondenza del modello del server quando un giocatore si connette al server.

#### `Paper.debugDynamicMissingKeys`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Attiva i log di debug per le chiavi mancanti negli oggetti NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Attiva i log di debug per i profili di teste non validi.

Questo logga tutte le teste non valide nella mappa del mondo insieme alla loro posizione.

#### `Paper.disableChannelLimit`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva il sistema di prioritizzazione delle classi dei plugin.

Utile in caso di problemi con i plugin shadow.

#### `Paper.disableFlushConsolidate`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva il sistema di consolidamento dei flush di Netty.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Valore predefinito**: `750`

Se le entità superano il valore impostato, vengono inviate in più pacchetti.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Valore predefinito**: `8192`

Imposta la dimensione massima del pacchetto che il server può ricevere in un'unica volta.

#### `Paper.ignoreJavaVersion`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva il controllo della versione di Java.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Ciò potrebbe danneggiare permanentemente file come il mondo e compromettere l'intero meccanismo di gioco.

Tutti i problemi derivanti dall'uso di questa opzione sono responsabilità dell'utente e Plamza non fornirà alcun supporto in tal senso.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Valore predefinito**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Valore predefinito**: `80`

Imposta la lunghezza massima di caratteri per linea sui cartelli.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Valore predefinito**: `(versione del mondo) + 1`

Imposta la versione delle informazioni di aggiornamento del mondo da inizializzare per prima.

È utile per aggiornare un gran numero di chunk, ma non viene utilizzato in altri casi.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valore predefinito**: `True`

Attiva il parsing dei commenti YAML di default.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Valore predefinito**: `30`

Espelle il giocatore se non riceve alcun dato per il tempo specificato (in secondi).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Ignora i commenti delle proprietà del server.

#### `Paper.debug-sync-loads`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Attiva i log di debug per la sincronizzazione del chunk.

#### `Paper.enable-sync-chunk-writes`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Abilita il sistema di scrittura di chunk sincronizzata predefinito di Minecraft.

Questo salva ogni chunk in ordine sequenziale, causando un notevole degrado delle prestazioni.

#### `Paper.explicit-flush`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Abilita il flushing esplicito dei canali di rete.

#### `Paper.strict-thread-checks`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Registra sempre gli errori che non si verificano nel thread principale.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Visualizza un avviso se un'operazione programmata ha un ritardo eccessivo.

#### `Paperclip.patchOnly`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Se si utilizza il file eseguibile predefinito, applica solo il patch senza avviare il server.

#### `Plazma.aggressiveOptimize`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`
- **Collisione**: `Plazma.disableConfigOptimization`

Ottimizza in modo più aggressivo la configurazione iniziale.

Attivando questa opzione, il server diventerà più veloce e sicuro, ma potrebbe influenzare notevolmente il gameplay.

#### `Plazma.disableConfigOptimization`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`
- **Collisione**: `Plazma.aggressiveOptimize`

Non ottimizza la configurazione iniziale in modo aggressivo.

Questo imposta l'uso della configurazione di base di Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`

Disabilita il marchio Plazma e utilizza l'icona del server di base della vaniglia.

#### `Plazma.useVanillaConfiguration`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`
- **Collisione**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Questo potrebbe influenzare notevolmente la sicurezza e le prestazioni del server.

Tutti i problemi derivanti dall'uso di questo attributo sono di responsabilità dell'amministratore del server.
{% endhint %}

Imposta la configurazione iniziale ai valori predefiniti forniti da Mojang.

Disabilita tutte le patch alle vulnerabilità applicate da Paper.

Le patch alle vulnerabilità possono essere riattivate nella configurazione di Paper o Plazma.

#### `Plazma.vanillaize`

- **Tipo**: `Boolean`
- **Valore predefinito**: `true`
- **Collisione**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Configura la configurazione iniziale per essere più vicina alla vaniglia.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Attributo obsoleto <a href="#id-1.3" id="id-1.3"></a>

Di seguito sono elencati gli attributi di sistema obsoleti.

#### `timings.bypassMax`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`
- **Obsoleto**: Dall'eliminazione di Timings da Plazma in poi

Determina se può essere superato il massimo valore che può essere inviato all'API di Timings di Aikar.

Anche in questo caso, se non gestito dalle eccezioni nell'API, verrà applicato un limite di velocità.

***

## Argomento di avvio <a href="#id-2" id="id-2"></a>

L'argomento di avvio viene inserito dopo `-jar *.jar` per inizializzare Plazma e viene elaborato insieme.

### Modalità d'uso <a href="#id-2.1" id="id-2.1"></a>

Gli attributi di sistema vengono inseriti come argomenti di comando di programma dopo `-jar *.jar`.

Ad esempio, se si desidera applicare l'argomento di avvio `nogui`,\
inserire come segue per far sì che Plazma elabori l'argomento `nogui` durante l'inizializzazione.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argomento di avvio completo <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Predefinito**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Predefinito**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Predefinito**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Avvia il server nel mondo demo.

#### `eraseCache`

Elimina i file di cache rimasti dopo l'aggiornamento del mondo.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Stampa tutti gli argomenti di avvio di Plazma e le relative descrizioni.

#### `initSettings`

Genera solo il file di configurazione e chiude il server.

#### `jfrProfile`

Attiva il profilo JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Predefinito**: `(server properties)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Disattiva il pannello dell'interfaccia grafica.

#### `nojline`

Disattiva JLine e utilizza la console vanilla.

#### `online-mode`

- **Alias**: `o`
- **Predefinito**: `(server properties)`

Seleziona se verificare i giocatori con il server di autenticazione Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Valore predefinito**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Imposta la posizione del file di configurazione PaperSpigot dismesso.

Viene utilizzato per trasferire la configurazione esistente in un nuovo file di configurazione e non sarà più utilizzato in futuro.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Valore predefinito**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Valore predefinito**: `plugins`

Imposta la posizione della cartella dei plugin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Valore predefinito**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Valore predefinito**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Avvia il server in uno stato completamente vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Predefinito**: `(server properties)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Predefinito**: `(server properties)`

Imposta la porta del server.

#### `server-name`

- **Valore predefinito**: `A Plazma Server`

Imposta il nome del server.

#### `spigot-settings`

- **Alias**: `S`
- **Valore predefinito**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Mostra la versione di Plazma.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Valore predefinito**: `(cartella del server)`

Imposta la posizione in cui vengono salvati i file del mondo.

#### `world-name`

- **Alias**: `w`, `world`
- **Predefinito**: `(server properties)`

Imposta il nome del file del mondo.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: La posizione aggiuntiva influisce sulla gestione degli argomenti.

[^3]: Ad esempio, se si desidera impostare (attivare) `Plazma.iKnowWhatIAmDoing` su `true`, invece di inserire `-DPlazma.iKnowWhatIAmDoing=true`, è sufficiente inserire `-DPlazma.iKnowWhatIAmDoing`.

[^4]: Ad esempio, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Rilevatore di eventi.

[^6]: Rilevatore di eventi.

[^7]: Client.

[^8]: Segnale che indica una connessione corretta con il server, simile ai battiti cardiaci.

[^9]: Con la funzione di espulsione AFK di Purpur è possibile espellere anche i giocatori inattivi.

[^10]: Sistema di scrittura di chunk sincronizzato, Sync Chunk Write System.

[^11]: `ATTENZIONE! Plazma potrebbe causare problemi inaspettati, assicurati di testarlo accuratamente prima di utilizzarlo su un server pubblico.`

[^12]: Anche l'`ottimizzazione del mondo` in gioco funziona allo stesso modo.

[^13]: Gli amministratori di `livello 2` o superiore sono esclusi.

[^14]: Protocollo Internet, IP.
