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

**La modifica delle proprietà di sistema potrebbe cambiare il funzionamento di Plazma e JVM e potrebbe avere un grande impatto sul gioco!**

Se non si conosce esattamente quale ruolo svolgono le singole proprietà di sistema, **non utilizzarle assolutamente!**

{% endhint %}

### Modalità d'uso <a href="#id-1.1" id="id-1.1"></a>

Le proprietà di sistema vengono inserite come argomenti di comando Java tra `java` e `-jar`.

Ad esempio, se si desidera applicare la proprietà di sistema `Plazma.dummyProperty`, inserendo il seguente valore, `37` verrà inserito nella proprietà successiva e Plazma verrà inizializzato.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

Il prefisso `-D` indica che l'argomento non è integrato nella JVM ma è un argomento specifico aggiunto a Plazma,

Se non si inserisce alcun valore negli attributi, il valore sarà fissato a [`true`](fn-3).

{% hint style="info" %}

**La piattaforma server della serie Paperweight include il carattere `.` nei nomi delle proprietà per distinguere le proprietà tra le varie piattaforme.**

In alcuni terminali come Windows Powershell potrebbe non essere consentito l'uso di questi argomenti, quindi è necessario aggiungere `"` ai bordi degli argomenti (fn-4).

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

**Il comando `/reload` è molto instabile, quindi tutti i problemi che si verificano dopo l'uso di `/reload` sono di responsabilità dell'utente.**

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

Disabilita il limite di 128 canali di plugin applicabili per giocatore (fn-5).

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

- **Tipo**: `Integer`
- **Valore predefinito**: `750`

Se le entità superano il valore impostato, vengono inviate in più pacchetti.

#### `Paper.filterThreshold`

- **Tipo**: `Integer`
- **Valore predefinito**: `8192`

Imposta la dimensione massima del pacchetto che il server può ricevere in un'unica volta.

#### `Paper.ignoreJavaVersion`

- **Tipo**: `Boolean`
- **Valore predefinito**: `False`

Disattiva il controllo della versione di Java.

{% hint style="danger" %}

**Questo potrebbe consentire a JVM di tentare di accedere a codice inesistente!**

Ciò potrebbe danneggiare permanentemente file come il mondo e compromettere l'intero meccanismo di gioco.

Tutti i problemi derivanti dall'uso di questa opzione sono responsabilità dell'utente e Plamza non fornirà alcun supporto in tal senso.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tipo**: `Integer`
- **Valore predefinito**: `64`

Imposta il limite del nome del canale del plugin[^6].

#### `Paper.maxSignLength`

- **Tipo**: `Integer`
- **Valore predefinito**: `80`

Imposta la lunghezza massima di caratteri per linea sui cartelli.

#### `Paper.minPrecachedDatafixVersion`

- **Tipo**: `Integer`
- **Valore predefinito**: `(versione del mondo) + 1`

Imposta la versione delle informazioni di aggiornamento del mondo da inizializzare per prima.

È utile per aggiornare un gran numero di chunk, ma non viene utilizzato in altri casi.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valore predefinito**: `True`

Attiva il parsing dei commenti YAML di default.

#### `Paper.playerConnection.keepAlive`

- **Tipo**: `Integer`
- **Valore predefinito**: `30`

Espelle il giocatore se non riceve alcun dato per il tempo specificato (in secondi).

Di solito, il [gioco](fn-7) invia continuamente un [segnale di battito cardiaco](fn-8) al server, quindi non verrai [espulso,](fn-9) ma se il gioco non risponde, verrai considerato in conflitto e verrai espulso dal server senza ulteriori elaborazioni del giocatore.

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
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`

Sopprime il [messaggio di avvertimento](fn-11) visualizzato durante l'inizializzazione di Plazma.

#### `Plazma.useVanillaFavicon`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`
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

- **Tipo**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

Imposta il nome e la posizione del [file di configurazione di Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Predefinito**: `commands.yml`

Imposta il nome e la posizione del [file di configurazione dei comandi di Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Predefinito**: `server.properties`

Imposta il nome e la posizione del file di [proprietà del server](../reference/configurations/property.md).

#### `demo`

Avvia il server nel mondo demo.

#### `eraseCache`

Elimina i file di cache rimasti dopo l'aggiornamento del mondo.

#### `forceUpgrade`

Aggiorna forzatamente il mondo ignorando la versione[^12].

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

Imposta il numero massimo di [giocatori](#user-content-fn-14).

#### `nogui`

Disattiva il pannello dell'interfaccia grafica.

#### `nojline`

Disattiva JLine e utilizza la console vanilla.

#### `online-mode`

- **Alias**: `o`
- **Predefinito**: `(server properties)`

Seleziona se verificare i giocatori con il server di autenticazione Mojang.

**Se non si utilizzano proxy come Velocity, potrebbero esserci sanzioni per violazione dell'[EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Valore predefinito**: `paper.yml`

{% hint style="warning" %}

**Questo argomento è stato dismesso dopo la versione 1.19.4**

{% endhint %}

Imposta la posizione del file di configurazione PaperSpigot dismesso.

Viene utilizzato per trasferire la configurazione esistente in un nuovo file di configurazione e non sarà più utilizzato in futuro.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Valore predefinito**: `config`

Imposta il nome e la posizione della cartella in cui si trova il [file di configurazione Paper](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Imposta il nome e la posizione della cartella in cui si trova il [file di configurazione Plazma](../reference/configurations/plazma/README.md).

#### `plugins`

- **Alias**: `p`
- **Valore predefinito**: `plugins`

Imposta la posizione della cartella dei plugin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Valore predefinito**: `pufferfish.yml`

Imposta il nome e la posizione del [file di configurazione Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Valore predefinito**: `purpur.yml`

Imposta il nome e la posizione del [file di configurazione Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Avvia il server in uno stato completamente vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Predefinito**: `(server properties)`

Imposta il nome host del server o l'indirizzo IP [Internet Protocol](#user-content-fn-13)[^13].

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

Imposta il nome e la posizione del [file di configurazione Spigot](../reference/configurations/spigot.md).

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

[^13]: Protocollo Internet, IP.

[^14]: Gli amministratori di `livello 2` o superiore sono esclusi.
