---
description: Scopri come creare un server con Plazma.
---

# 👟 Inizia

Per utilizzare Plazma in modo stabile, il sistema deve soddisfare i seguenti requisiti.

|                         | Minimo | Consigliato |
| :---------------------: | :----- | :---------- |
|       Architettura      | x64    | -           |
|           RAM           | 8GB    | 16GB        |
| Spazio di archiviazione | 1GB    | 8GB         |
|           JRE           | 17     | 21          |

Per facilitare la modifica dei file di configurazione, è consigliabile installare un editor come [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Installazione di JRE

Come indica il nome, Minecraft: **"Java"** Edition è sviluppato in Java e richiede JRE[^1] per essere eseguito.

Poiché Plazma si basa sulla piattaforma ufficiale dei server di Mojang Studios \[^(#user-content-fn-2)], è necessario installare JRE anche per utilizzare Plazma.

### 1.1 Verifica della presenza di JRE

Per verificare se JRE è installato nel sistema, digitare [`cmd /k java --version`](#user-content-fn-4) nella finestra di esecuzione e premere Invio.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Output corretto" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE non installato" lineNumbers="true" %}

```log
'java' non è riconosciuto come comando interno o esterno,
un programma eseguibile o un file batch.
```

{% endcode %}

{% code title="JRE troppo vecchio" lineNumbers="true" %}

```log
Opzione non riconosciuta: --version
Errore: Impossibile creare la Java Virtual Machine.
Errore: Si è verificata un'eccezione fatale. Il programma verrà chiuso.
```

{% endcode %}

### 1.2 Installazione di JRE

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. Scarica il **JDK 21** in formato `.msi` da [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Esegui il file di installazione scaricato e clicca su `Avanti`.
3. Attiva `Imposta la variabile JAVA_HOME` dal menu visualizzato al centro sinistra della finestra e clicca su `Avanti`.
4. Clicca su `Installa` per completare l'installazione di JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) scarica **JDK 21** in formato `.dmg` dal wizard di installazione e esegui per installare JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Aggiungi prima il repository Azul Zulu ad APT eseguendo il seguente comando nel terminale.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Successivamente, installa JRE eseguendo il comando seguente nel terminale.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Puoi installare JRE eseguendo il seguente comando.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Download di Plazma

Plazma offre vari file eseguibili tra cui scegliere.

{% hint style="warning" %}

**Nella maggior parte dei casi si utilizza `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Scopri di più</summary>

Il nome del file eseguibile è `plazma-(versione manager)-1.20.4-R0.1-SNAPSHOT-(forma di mappatura).jar`.

- **Forma di mappatura**\
  La mappatura è una sorta di mappa che collega il codice reale di Minecraft al codice offuscato.
  - **Reobf**\
    Reobfuscated (ricriptato), anche noto come mappatura Spigot, è utilizzato nella maggior parte dei plugin NMS.\
    Sarà interrotto l'uso a partire dalla versione 1.20.5.
  - **Mojmap**\
    Mojang-mapped, è la mappatura di base di Minecraft.
- **Version Manager**\
  Il version manager è un launcher del server che gestisce le librerie necessarie per l'avvio del server e patcha i file del server.
  - **Paperclip**\
    Sviluppato dal team di PaperMC per Paper e altre piattaforme derivate, scarica le librerie e applica le patch al server.
  - **Bundler**\
    Version manager di Minecraft vanilla.

</details>

***

## 3. Creazione dello script di avvio

Per avviare rapidamente Plazma e riavviare automaticamente il server, è necessario creare uno [script di avvio](#user-content-fn-6).

È possibile creare uno script di avvio tramite [Flags.sh](https://flags.sh) inserendo solo la [quantità di memoria da utilizzare](#user-content-fn-8)[^8] in Plazma, il comando verrà ottimizzato automaticamente.

Puoi scaricare lo script di avvio facendo clic sul pulsante di download in basso a sinistra.\
**Assicurati che lo script di avvio scaricato sia compatibile con il tuo sistema operativo.**

***

## 4. Organizzazione dei file

Sposta lo script di avvio scaricato e Plazma in una nuova cartella.

{% hint style="warning" %}

**Il nome della cartella deve essere senza spazi e in lingua inglese.**

Altrimenti Plazma o JRE potrebbero non funzionare correttamente.

{% endhint %}

Esegui lo script di avvio. Per Windows, durante la selezione di consenso del firewall, è necessario selezionare **Consenti**.

***

## 5. Accordo EULA

Dopo aver eseguito lo script di avvio una volta, verrà creato un file `eula.txt` nella cartella.

L'EULA[^9] è un accordo di licenza che devi accettare per utilizzare i servizi di [Mojang Studios](#user-content-fn-10).

{% hint style="warning" %}

In caso di mancato consenso, non sarà possibile avviare il server e potrebbero essere applicate [sanzioni](#user-content-fn-11)[^11] come la sospensione dell'account per violazione dell'EULA.

{% endhint %}

Per accettare l'EULA, modifica `eula=false` in `eula=true` nel file `eula.txt` e salva le modifiche.

***

## 6. Consentire l'accesso esterno (Windows)

I moderni sistemi operativi bloccano gli accessi esterni per motivi di sicurezza tramite il **firewall** e il **router** di default.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Se il tuo router non supporta UPnP, dovrai cercare informazioni specifiche poiché i pannelli dei router possono variare.

Puoi anche utilizzare [Ngrok](https://ngrok.com/) per generare un indirizzo temporaneo.
{% endhint %}

{% hint style="warning" %}

**Per sistemi operativi basati su (quasi) UNIX come Linux o macOS, i metodi di configurazione del firewall variano a seconda del servizio e richiedono una ricerca diretta.**

{% endhint %}

### 6.1 Verifica della necessità di port forwarding

Digita il seguente comando nel prompt e premi Invio.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IndirizzoIP -eq (Invoke-WebRequest "ifconfig.me").content"
```

Se l'output è `True`, non è necessario fare altro. Se è `False`, devi configurare il port forwarding.

### 6.2 Connessione al server

{% tabs %}

{% tab title="Accesso esterno" %}

Se non è necessario il forwarding delle porte o se è già stato configurato con successo, ora è possibile accedere al server.

L'indirizzo utilizzato per la connessione al server può essere verificato [qui](https://ip.pe.kr/).

{% endtab %}

{% tab title="Tentativo di forwarding delle porte con UPnP" %}

Nel file `purpur.yml` nella cartella del server, attiva `network.upnp-port-forwarding` su `true`.

Successivamente, al riavvio del server, Plazma proverà automaticamente a fare il forwarding della porta.

Di seguito vi è la conferma del successo del forwarding della porta in base al messaggio visualizzato sulla console, che apparirà come `[UPnP] (messaggio)`.

| Messaggio                             | Significato                                                             |
| ------------------------------------- | ----------------------------------------------------------------------- |
| `Porta aperta con successo (porta)`   | Forwarding della porta riuscito.                        |
| `Porta (porta) già aperta`            | Un altro servizio sta utilizzando la porta specificata. |
| `Impossibile aprire la porta (porta)` | Forwarding della porta fallito.                         |
| `Servizio non disponibile`            | Il router non supporta UPnP.                            |

Quando il server viene spento, Plazma chiude automaticamente le porte.

{% endtab %}

{% tab title="Creazione di un indirizzo temporaneo con Ngrok" %}

L'uso di Ngrok è utile per test temporanei, partite collaborative o giocare con gli amici.

1. Scarica il file ZIP `Windows (64-bit)` da [Ngrok website](https://ngrok.com/download).
2. Posiziona il file Ngrok scaricato nella cartella del server.
3. Genera un token di autenticazione dal [dashboard di Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Esegui il comando visualizzato nella riga di comando nella cartella del server.
5. Aggiungi `start /b ngrok tcp --region jp 25565` all'inizio dello script di avvio e `taskkill /f /t /im ngrok.exe` alla fine.
6. Dalla console, l'indirizzo `0.tcp.jp.ngrok.io:12345` sarà l'indirizzo del server.
7. Ora è possibile connettersi esternamente utilizzando questo indirizzo.

{% endtab %}

{% tab title="Accesso locale" %}

Se si desidera accedere al server da locale, è possibile farlo utilizzando l'`indirizzo IPv4` visualizzato eseguendo `cmd /k ipconfig` dalla finestra di esecuzione.

Ad esempio, se dopo l'esecuzione del comando viene visualizzato:

```log
Windows Configurazione IP

Adattatore Ethernet Ethernet:

    Suffisso DNS specifico per la connessione. . . . :
    Indirizzo IPv4. . . . . . . . . : 192.168.3.7
    Subnet mask . . . . . . . : 255.255.255.0
    Gateway predefinito . . . . . . : 192.168.3.1

```

Provare a connettersi al server localmente utilizzando l'`192.168.3.7` indicato come indirizzo IPv4.

Se il server e il gioco sono eseguiti sullo stesso PC, è possibile connettersi utilizzando `localhost`.

{% endtab %}
{% endtabs %}

## 7. Crescere

Se il server è stato avviato con successo e funziona correttamente, è ora il momento di personalizzarlo.

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="prossimo-passo.md" %}
[prossimo-passo.md](prossimo-passo.md)
{% endcontent-ref %}

***

[^1]: Ambiente di esecuzione Java, Java Runtime Environment.

[^2]: Paper, su cui si basa Plazma, è basato su Spigot e Spigot si basa sulla piattaforma ufficiale del server.

[^3]: Tasto Windows + R

[^4]: Per Linux, eseguire `java --version` nel terminale.

[^5]: JRE è uno dei progetti open source e ci sono diverse varianti come piattaforma del server Minecraft.

[^6]: Comunemente noto come **launcher**.

[^7]: Attivando l'opzione "Auto-riavvio", il server si riavvierà automaticamente. È possibile terminare premendo `Control + C`.

[^8]: Non è consigliabile superare la metà della capacità del sistema.

    Ad esempio, se la memoria totale del sistema è di 8GB, non è consigliabile impostarla su più di 4GB.

[^9]: Contratto di licenza per l'utente finale, End-User License Agreement. Per ulteriori informazioni, consulta il [sito web di Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: In Corea, in base all'articolo 32, paragrafo 1, punto 9 della legge sull'avanzamento dell'industria dei videogiochi, è possibile presentare un'azione legale presso **Korea Microsoft Corporation**.

[^12]: Universal Plug & Play. Purpur incluso in Plazma comunica automaticamente con il router tramite questa tecnologia per aprire solo le porte quando il server è in esecuzione, eliminando la necessità di fare il forwarding della porta manualmente.

[^13]: Se non si ha un account, è possibile registrarsi su Ngrok tramite un account Google o GitHub.
