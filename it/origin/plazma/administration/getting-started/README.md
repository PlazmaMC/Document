---
description: Scopri come creare un server con Plazma.
---

# 👟 Inizia

Per utilizzare Plazma in modo stabile, il sistema deve soddisfare i seguenti requisiti.

|                         | Minimo | Consigliato |
| :---------------------: | -----: | ----------: |
|       Architettura      |    x64 |           - |
|           RAM           |    8GB |        16GB |
| Spazio di archiviazione |    1GB |         8GB |
|           JRE           |     17 |          21 |

Per facilitare la modifica dei file di configurazione, è consigliabile installare un editor come [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Installazione di JRE

Come indica il nome, Minecraft: **"Java"** Edition è sviluppato in Java e richiede JRE[^1] per essere eseguito.

Poiché Plazma si basa sulla piattaforma ufficiale dei server di Mojang Studios \[^(#user-content-fn-2)], è necessario installare JRE anche per utilizzare Plazma.

### 1.1 Verifica della presenza di JRE

Per verificare se JRE è installato nel sistema, digitare [`cmd /k java --version`](#user-content-fn-4) nella finestra di esecuzione e premere Invio.

Se viene visualizzato l'output corretto, passa al [Passaggio 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Se l'output non è come sopra o se appare come segue, significa che JRE non è installato o è troppo vecchio e devi seguire il [Passaggio 1.2](setup.md#id-1.2).

{% code title="JRE가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Installazione di JRE

In questa guida, useremo Azul Zulu come [una delle varianti](#user-content-fn-5) di JRE.

Dopo aver completato l'installazione, ripeti il [Passaggio 1.1](setup.md#id-1.1) per verificare che l'installazione sia avvenuta correttamente.

{% tabs %}

{% tab title="Windows" %}

1. Scarica il **JDK 21** in formato `.msi` da [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Esegui il file di installazione scaricato e clicca su `Avanti`.
3. Attiva `Imposta la variabile JAVA_HOME` dal menu visualizzato al centro sinistra della finestra e clicca su `Avanti`.
4. Clicca su `Installa` per completare l'installazione di JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

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

다음 명령어를 입력하여 JRE를 설치할 수 있습니다.

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

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Le informazioni seguenti sono per gli sviluppatori o per coloro interessati alle caratteristiche specifiche di ciascuna forma.\
Se sei un utente normale, puoi saltare al [Passaggio 3](setup.md#id-3) senza problemi.

{% endhint %}

<details>

<summary>Scopri di più</summary>

Il nome del file eseguibile è `plazma-(versione manager)-1.20.4-R0.1-SNAPSHOT-(forma di mappatura).jar`.

- **Forma di mappatura**\
  La mappatura è una sorta di mappa che collega il codice reale di Minecraft al codice offuscato.
  - **Reobf**\
    Reobfuscation, noto anche come mappatura Spigot, è utilizzato principalmente nei plugin NMS.\
    Dal 1.20.5 sarà deprecato.
  - **Mojmap**\
    Mappatura Mojang, mappatura di Minecraft vanilla.
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

Puoi generare lo script di avvio tramite [Flags.sh](https://flags.sh). Inserisci solo la [memoria da utilizzare](#user-content-fn-8) per Plazma e il comando verrà ottimizzato automaticamente.

Puoi scaricare lo script di avvio facendo clic sul pulsante di download in basso a sinistra.\
**Assicurati che lo script di avvio scaricato sia compatibile con il tuo sistema operativo.**

***

## 4. Organizzazione dei file

Sposta lo script di avvio scaricato e Plazma in una nuova cartella.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Altrimenti Plazma o JRE potrebbero non funzionare correttamente.

{% endhint %}

Esegui lo script di avvio. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. Accordo EULA

Dopo aver eseguito lo script di avvio una volta, verrà creato un file `eula.txt` nella cartella.

L'EULA[^9] è un accordo di licenza che devi accettare per utilizzare i servizi di [Mojang Studios](#user-content-fn-10).

Se non accetti l'EULA, non potrai avviare il server e potresti subire sanzioni come la sospensione dell'account in caso di violazione \[^(#user-content-fn-11)].

Per accettare l'EULA, modifica `eula=false` in `eula=true` nel file `eula.txt` e salva le modifiche.

***

## 6. Consentire l'accesso esterno (Windows)

I moderni sistemi operativi bloccano gli accessi esterni per motivi di sicurezza tramite il **firewall** e il **router** di default.

Poiché hai già consentito l'accesso nel [Passaggio 3](setup.md#id-3) su Windows, devi solo configurare il port forwarding.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Se il tuo router non supporta UPnP, dovrai cercare informazioni specifiche poiché i pannelli dei router possono variare.

Puoi anche utilizzare [Ngrok](https://ngrok.com/) per generare un indirizzo temporaneo.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Verifica della necessità di port forwarding

Digita il seguente comando nel prompt e premi Invio.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Se l'output è `True`, non è necessario fare altro. Se è `False`, devi configurare il port forwarding.

### 6.2 Connessione al server

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

L'indirizzo utilizzato per la connessione al server può essere verificato [qui](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Successivamente, al riavvio del server, Plazma proverà automaticamente a fare il forwarding della porta.

Di seguito vi è la conferma del successo del forwarding della porta in base al messaggio visualizzato sulla console, che apparirà come `[UPnP] (messaggio)`.

| Messaggio                             | Significato                                             |
| ------------------------------------- | ------------------------------------------------------- |
| `Porta aperta con successo (porta)`   | Forwarding della porta riuscito.                        |
| `Porta (porta) già aperta`            | Un altro servizio sta utilizzando la porta specificata. |
| `Impossibile aprire la porta (porta)` | Forwarding della porta fallito.                         |
| `Servizio non disponibile`            | Il router non supporta UPnP.                            |

Quando il server viene spento, Plazma chiude automaticamente le porte.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Scarica il file ZIP `Windows (64-bit)` da [Ngrok website](https://ngrok.com/download).
2. Posiziona il file Ngrok scaricato nella cartella del server.
3. Genera un token di autenticazione dal [dashboard di Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Esegui il comando visualizzato nella riga di comando nella cartella del server.
5. Aggiungi `start /b ngrok tcp --region jp 25565` all'inizio dello script di avvio e `taskkill /f /t /im ngrok.exe` alla fine.
6. Dalla console, l'indirizzo `0.tcp.jp.ngrok.io:12345` sarà l'indirizzo del server.
7. Ora è possibile connettersi esternamente utilizzando questo indirizzo.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Ad esempio, se dopo l'esecuzione del comando viene visualizzato:

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Provare a connettersi al server localmente utilizzando l'`192.168.3.7` indicato come indirizzo IPv4.

Se il server e il gioco sono eseguiti sullo stesso PC, è possibile connettersi utilizzando `localhost`.

{% endtab %}
{% endtabs %}

## 7. Fase successiva

Se il server è stato avviato con successo e funziona correttamente, è ora il momento di personalizzarlo.

Scopri come personalizzare il server seguendo la guida qui sotto.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
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
