---
description: Scopri come creare un server con Plazma.
---

# 👟 Inizia

Per utilizzare Plazma in modo stabile, il sistema deve soddisfare i seguenti requisiti.

|                         | Minimo | Consigliato |
| :---------------------: | ------ | ----------- |
|       Architettura      | x64    | -           |
|           RAM           | 8GB    | 16GB        |
| Spazio di archiviazione | 1GB    | 8GB         |
|           JDK           | 17     | 21          |

Per facilitare la modifica dei file di configurazione, è consigliabile installare un editor come [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Output corretto" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' non è riconosciuto come comando interno o esterno,
un programma eseguibile o un file batch.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Opzione non riconosciuta: --version
Errore: Impossibile creare la Java Virtual Machine.
Errore: Si è verificata un'eccezione fatale. Il programma verrà chiuso.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Scarica il **JDK 21** in formato `.msi` da [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Esegui il file di installazione scaricato e clicca su `Avanti`.
3. Attiva `Imposta la variabile JAVA_HOME` dal menu visualizzato al centro sinistra della finestra e clicca su `Avanti`.
4. Clicca su `Installa` per completare l'installazione di JRE.
   {% endtab %}

{% tab title="macOS" %}
[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.
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
다음 명령어를 입력하여 JDK를 설치할 수 있습니다.

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
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Scopri di più</summary>

Il nome del file eseguibile è `plazma-(versione manager)-1.20.4-R0.1-SNAPSHOT-(forma di mappatura).jar`.

- **Forma di mappatura**\
  La mappatura è una sorta di mappa che collega il codice reale di Minecraft al codice offuscato.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, è la mappatura di base di Minecraft. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Puoi scaricare lo script di avvio facendo clic sul pulsante di download in basso a sinistra.\
**Assicurati che lo script di avvio scaricato sia compatibile con il tuo sistema operativo.**

***

## 4. Organizzazione dei file

Sposta lo script di avvio scaricato e Plazma in una nuova cartella.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Esegui lo script di avvio. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Accordo EULA

Dopo aver eseguito lo script di avvio una volta, verrà creato un file `eula.txt` nella cartella.

L'EULA[^9] è un accordo di licenza che devi accettare per utilizzare i servizi di [Mojang Studios](#user-content-fn-10).

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Per accettare l'EULA, modifica `eula=false` in `eula=true` nel file `eula.txt` e salva le modifiche.

***

## 6. Consentire l'accesso esterno (Windows)

I moderni sistemi operativi bloccano gli accessi esterni per motivi di sicurezza tramite il **firewall** e il **router** di default.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Se il tuo router non supporta UPnP, dovrai cercare informazioni specifiche poiché i pannelli dei router possono variare.

Puoi anche utilizzare [Ngrok](https://ngrok.com/) per generare un indirizzo temporaneo.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Verifica della necessità di port forwarding

Digita il seguente comando nel prompt e premi Invio.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IndirizzoIP -eq (Invoke-WebRequest "ifconfig.me").content"
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

| Messaggio                             | Significato                                                             |
| ------------------------------------- | ----------------------------------------------------------------------- |
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

Scopri come personalizzare il server seguendo le istruzioni di seguito.

{% content-ref url="prossimo-passo.md" %}
[prossimo-passo.md](prossimo-passo.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
