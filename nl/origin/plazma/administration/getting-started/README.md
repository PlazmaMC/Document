---
description: Leer hoe je een server maakt met Plazma.
---

# 👟 Aan de slag

Om Plazma stabiel te gebruiken, moet het systeem aan de volgende vereisten voldoen.

|              | Minimum | Aanbevolen |
| :----------: | ------- | ---------- |
| Architectuur | x64     | -          |
|      RAM     | 8GB     | 16GB       |
| Opslagruimte | 1GB     | 8GB        |
|      JDK     | 17      | 21         |

Voor soepel bestandsbewerkingen, is het ook goed om een editor zoals [Visual Studio Code](https://code.visualstudio.com/download) te installeren.

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Juiste uitvoer" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' is geen interne of externe opdracht, uitvoerbaar programma of
batchbestand.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Download eerst **JDK 21** in `.msi` formaat van [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Voer de gedownloade installatiewizard uit en klik op 'Volgende'.
3. Activeer 'Set JAVA_HOME variable' in het menu links van het midden van het venster en klik op 'Volgende'.
4. Voltooi de JRE-installatie door op 'Installeren' te klikken.
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

Installeer vervolgens JRE door de volgende opdrachten in de terminal uit te voeren.

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

## 2. Plazma downloaden

Plazma biedt verschillende soorten uitvoerbare bestanden aan.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Meer informatie</summary>

De naam van het uitvoerbare bestand is `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping type).jar`.

- **Mapping type**\
  Mapping is een soort kaart die het echte code van Minecraft verbindt met de geobfusceerde code.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-gemapt, is de mapping voor Vanilla Minecraft. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Version manager**\
  De versiebeheerder is een soort launcher die nodig is voor het draaien van de server en het patchen van serverbestanden.
  - **Paperclip**\
    Ontwikkeld door het PaperMC-team voor Paper en andere afgeleide platforms, downloadt bibliotheken en past patches toe op de server.
  - **Bundler**\
    De Vanilla Minecraft-versiebeheerder.

</details>

***

## 3. Startscript maken

Om Plazma eenvoudig te starten en de server automatisch opnieuw te starten, moet u een [startscript](#user-content-fn-6)[^6] maken.

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

U kunt het startscript downloaden via de knop linksonder.\
**Controleer of het gedownloade startscript overeenkomt met uw besturingssysteem.**

***

## 4. Bestandsopruiming

Verplaats nu het gedownloade startscript en Plazma naar een nieuwe map.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Voer nu het startscript uit. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA accepteren

Na het uitvoeren van het startscript wordt er een 'eula.txt' bestand in de map gemaakt.

EULA[^9] is een gebruiksrechtovereenkomst waarbij u akkoord moet gaan met het gebruik van de diensten van [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Om akkoord te gaan met de EULA, wijzigt u `eula=false` naar `eula=true` in het `eula.txt` bestand en slaat u het op.

***

## 6. Extern toegang toestaan (Windows)

Moderne besturingssystemen blokkeren standaard externe toegang met behulp van de **firewall** en **router**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Als uw router UPnP niet ondersteunt, heeft elke router een ander paneel, dus u moet zelf informatie opzoeken.

U kunt ook [Ngrok](https://ngrok.com/) gebruiken om een tijdelijk adres te genereren.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Controleer of port forwarding nodig is

Voer het volgende in het uitvoervenster in en voer het uit.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Als de uitvoer 'True' is, is het goed, maar als het 'False' is, moet u port forwarding instellen.

### 6.2 Verbinding maken met de server

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Het adres dat wordt gebruikt om verbinding te maken met de server, kan hier worden gecontroleerd: [hier](https://ip.pe.kr/)
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Na het opnieuw starten van de server zal Plazma automatisch proberen port forwarding te doen.

Hieronder staat of UPnP succesvol was op basis van de berichten die op de console worden weergegeven, op de console wordt het als `[UPnP] (bericht)` weergegeven.

| Bericht                           | Betekenis                                                |
| --------------------------------- | -------------------------------------------------------- |
| `Poort succesvol geopend (poort)` | Port forwarding succesvol.               |
| `Poort (poort) is al geopend`     | Een andere service gebruikt de poort al. |
| `Kon poort niet openen (poort)`   | Port forwarding mislukt.                 |
| `Service is niet beschikbaar`     | De router ondersteunt geen UPnP.         |

Wanneer de server wordt afgesloten, sluit Plazma automatisch de poort.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Download het ZIP-bestand `Windows (64-bit)` van de [Ngrok-website](https://ngrok.com/download).
2. Plaats de gedownloade Ngrok in de servermap.
3. Genereer een [verificatietoken](#user-content-fn-13) op [Ngrok-dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Voer de opdrachten uit die worden weergegeven in de `Command Line` van de servermap.
5. Voeg `start /b ngrok tcp --region jp 25565` toe aan het bovenste gedeelte van het uitvoeringsscript en `taskkill /f /t /im ngrok.exe` aan de onderkant.
6. Het adres van de server wordt `0.tcp.jp.ngrok.io:12345` zoals weergegeven in `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` in de console.
7. Nu kunt u via dit adres van buitenaf verbinding maken.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Bijvoorbeeld, als het volgende wordt weergegeven na het uitvoeren van de opdracht,

```log
Windows IP-configuratie

Ethernet-adapter Ethernet:

    Verbindingsspecifieke DNS-achtervoegsel. . . . :
    IPv4-adres. . . . . . . . . : 192.168.3.7
    Subnetmasker. . . . . . . . : 255.255.255.0
    Standaardgateway. . . . . . : 192.168.3.1

```

U kunt verbinding maken met de server vanaf uw lokale machine door verbinding te maken met het `192.168.3.7` dat wordt weergegeven als IPv4-adres.

Als de server en het spel op dezelfde pc worden uitgevoerd, kunt u verbinding maken met `localhost`.
{% endtab %}
{% endtabs %}

## 7. Ontwikkelen

Als de server succesvol is gestart en correct werkt, is het nu tijd om de server aan te passen.

Leer hoe u de server kunt aanpassen met behulp van de volgende handleiding.

{% content-ref url="volgende-stap.md" %}
[volgende-stap.md](volgende-stap.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Paper, de basis van Plazma, is gebaseerd op Spigot, dat op zijn beurt is gebaseerd op het officiële serverplatform van Spigot.

[^3]: Windows-toets + R

[^4]: Voor Linux, voer `java --version` uit in de terminal.

[^5]: JRE is een van de open-source projecten, vergelijkbaar met Minecraft-serverplatforms.

[^6]: Het staat bekend als een **launcher**.

[^7]: Als u 'Automatisch opnieuw opstarten' inschakelt, wordt de server automatisch opnieuw opgestart. U kunt afsluiten door `Control + C` in te voeren.

[^8]: Het wordt niet aanbevolen om meer dan de helft van het systeemgeheugen toe te wijzen.

    Bijvoorbeeld, als het totale geheugen van het systeem 8 GB is, wordt het niet aanbevolen om meer dan 4 GB toe te wijzen.

[^9]: Eindgebruikerslicentieovereenkomst, EULA. Raadpleeg de [Minecraft-website](https://www.minecraft.net/ko-kr/usage-guidelines) voor meer informatie.

[^10]: Microsoft Corporation.

[^11]: Volgens artikel 32, lid 1, punt 9 van de Wet op de bevordering van de game-industrie in Zuid-Korea, kan **Korea Microsoft Corporation** juridische stappen ondernemen.

[^12]: Universal Plug & Play. Plazma bevat Purpur die automatisch communiceert met de router via deze technologie en alleen poorten opent wanneer de server actief is, waardoor directe port forwarding niet nodig is.

[^13]: Als je geen account hebt, meld je dan aan bij Ngrok met een Google- of GitHub-account.
