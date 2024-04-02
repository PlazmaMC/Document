---
description: Scopri gli argomenti di avvio e le proprietà di sistema.
---

# 🎛️ Argomenti di avvio e proprietà

Gli argomenti di avvio e le proprietà di sistema sono valori aggiunti ai [comandi utilizzati](#user-content-fn-1)[^1] nell'esecuzione di Plazma, che consentono di modificare valori che non possono essere cambiati dopo l'esecuzione di Plazma.

In base alla [posizione in cui vengono aggiunti ai comandi](#user-content-fn-2)[^2], si distinguono tra **argomenti di avvio** e **proprietà di sistema**.

***

## Proprietà di sistema <a href="#id-1" id="id-1"></a>

Le proprietà di sistema, inserite prima di `-jar`, sono valori elaborati dalla JVM prima dell'inizializzazione di Plazma.

{% hint style="warning" %}

**La modifica delle proprietà di sistema potrebbe cambiare il funzionamento di Plazma e JVM e potrebbe avere un grande impatto sul gioco!**

Se non si conosce esattamente quale ruolo svolgono le singole proprietà di sistema, **non utilizzarle assolutamente!**

{% endhint %}

### Modalità d'uso <a href="#id-1.1" id="id-1.1"></a>

Le proprietà di sistema vengono inserite come argomenti di comando Java tra `java` e `-jar`.

Ad esempio, per applicare la proprietà di sistema `Plazma.dummyProperty`, inserire il valore `37` come segue per inizializzare Plazma.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

Il prefisso `-D` indica che l'argomento non è integrato nella JVM ma è un argomento specifico aggiunto a Plazma,

Se non viene fornito alcun valore, il valore sarà [`true` per impostazione predefinita.](#user-content-fn-3)[^3]

{% hint style="info" %}

**La piattaforma server della serie Paperweight include il carattere `.` nei nomi delle proprietà per distinguere le proprietà tra le varie piattaforme.**

In alcuni terminali come Windows Powershell, potrebbe non essere consentito l'utilizzo di questi argomenti, quindi è necessario aggiungere `"` all'inizio e alla fine degli argomenti. [^4]

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

Disattiva il limite di 128 canali di plugin per giocatore.[^5]

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

Imposta il limite del nome del canale del plugin.[^6]

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

Di solito, il gioco[^7] invia costantemente un [segnale di battito cardiaco](#user-content-fn-8)[^8] al server, quindi non viene espulso; tuttavia, se il gioco non risponde, viene considerato in crash e il server disconnette il giocatore.

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

{% hint style="warning" %}

**Questa proprietà sarà spostata agli argomenti di avvio dopo la versione 1.20.5.**

{% endhint %}

Applica un'ottimizzazione più rigorosa della configurazione all'avvio iniziale.

Attivando questo, il server diventerà più veloce e sicuro, ma potrebbe bloccare alcune meccaniche o influenzare pesantemente il gameplay.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valore predefinito**: `false`

Sopprime il messaggio di avvertimento[^11] visualizzato durante l'inizializzazione di Plazma.

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
