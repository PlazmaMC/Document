---
description: Leer hoe je een server maakt met Plazma.
---

# 👟 Aan de slag

Om Plazma stabiel te gebruiken, moet het systeem aan de volgende vereisten voldoen.

|              | Minimum | Aanbevolen |
| :----------: | ------: | ---------: |
| Architectuur |     x64 |          - |
|      RAM     |     8GB |       16GB |
| Opslagruimte |     1GB |        8GB |
|      JRE     |      17 |         21 |

Voor soepel bestandsbewerkingen, is het ook goed om een editor zoals [Visual Studio Code](https://code.visualstudio.com/download) te installeren.

***

## 1. JRE installatie

Zoals de naam al aangeeft, is Minecraft: **"Java"** Edition ontwikkeld in Java en heeft het JRE[^1] nodig om uit te voeren.

Omdat Plazma gebaseerd is op het officiële serverplatform van Mojang Studios, moet ook JRE worden geïnstalleerd om Plazma te gebruiken.

### 1.1 Controleer JRE

Om te controleren of JRE op het systeem is geïnstalleerd, voert u [`cmd /k java --version`](#user-content-fn-4)[^4] uit in het uitvoervenster.

Als het volgende wordt weergegeven, ga dan naar [Stap 2](setup.md#id-2).

{% code title="Juiste uitvoer" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Als dit niet wordt weergegeven, of als het volgende wordt weergegeven, ontbreekt JRE of is het te oud, dus moet [Stap 1.2](setup.md#id-1.2) worden uitgevoerd.

{% code title="JRE niet geïnstalleerd" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE verouderd" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE installatie

In deze handleiding wordt Azul Zulu gebruikt als een van de soorten JRE.

Na installatie, controleer opnieuw met [Stap 1.1](setup.md#id-1.1) om te zien of de installatie correct is voltooid.

{% tabs %}

{% tab title="Windows" %}

1. Download eerst **JDK 21** in `.msi` formaat van [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Voer de gedownloade installatiewizard uit en klik op 'Volgende'.
3. Activeer 'Set JAVA_HOME variable' in het menu links van het midden van het venster en klik op 'Volgende'.
4. Voltooi de JRE-installatie door op 'Installeren' te klikken.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) installeert **JDK 21** door de `.dmg` installatiewizard te downloaden en uit te voeren om JRE te installeren.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Voeg eerst de Azul Zulu-repository toe aan APT door het volgende commando in de terminal uit te voeren.

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

U kunt JRE installeren door het volgende commando in te voeren.

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

**Meestal wordt `Reobf Paperclip` gebruikt.**

De volgende informatie is voor ontwikkelaars of degenen die geïnteresseerd zijn in de kenmerken van elk type.\
Voor gewone gebruikers is het overslaan naar [Stap 3](setup.md#id-3) geen probleem.

{% endhint %}

<details>

<summary>Meer informatie</summary>

De naam van het uitvoerbare bestand is `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping type).jar`.

- **Mapping type**\
  Mapping is een soort kaart die het echte code van Minecraft verbindt met de geobfusceerde code.
  - **Reobf**\
    Reobfuscation, ook wel bekend als Spigot mapping, wordt voornamelijk gebruikt in de meeste NMS-plugins.\
    Vanaf 1.20.5 zal het niet meer worden gebruikt.
  - **Mojmap**\
    Mojang mapping, de mapping van Vanilla Minecraft.
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

U kunt een startscript maken via [Flags.sh](https://flags.sh). Voer alleen de [geheugenlimiet](#user-content-fn-8)[^8] in en de opdracht wordt automatisch geoptimaliseerd.

U kunt het startscript downloaden via de knop linksonder.\
**Controleer of het gedownloade startscript overeenkomt met uw besturingssysteem.**

***

## 4. Bestandsopruiming

Verplaats nu het gedownloade startscript en Plazma naar een nieuwe map.

{% hint style="warning" %}

**De mapnaam moet geen spaties bevatten en in het Engels zijn ingesteld.**

Anders werken Plazma of JRE mogelijk niet correct.

{% endhint %}

Voer nu het startscript uit. Voor Windows moet u in het <mark style="background-color:orange;">toestemmingsvenster van de firewall **Toestaan** selecteren</mark>.

***

## 5. EULA accepteren

Na het uitvoeren van het startscript wordt er een 'eula.txt' bestand in de map gemaakt.

EULA[^9] is een gebruiksrechtovereenkomst waarbij u akkoord moet gaan met het gebruik van de diensten van [Mojang Studios](#user-content-fn-10)[^10].

Zonder akkoord te gaan met de EULA kunt u de server niet starten en bij schending van de EULA kunt u sancties zoals accountopschorting krijgen, enzovoort.]\(#user-content-fn-11)[^11]

Om akkoord te gaan met de EULA, wijzigt u `eula=false` naar `eula=true` in het `eula.txt` bestand en slaat u het op.

***

## 6. Extern toegang toestaan (Windows)

Moderne besturingssystemen blokkeren standaard externe toegang met behulp van de **firewall** en **router**.

Voor Windows, omdat u in [Stap 3](setup.md#id-3) de firewall hebt toegestaan, hoeft u alleen nog maar port forwarding te doen.

{% hint style="info" %}

**Deze handleiding is geschreven onder de veronderstelling dat u Windows-besturingssysteem en een router die [UPnP](#user-content-fn-12)[^12] ondersteunt gebruikt.**

Als uw router UPnP niet ondersteunt, heeft elke router een ander paneel, dus u moet zelf informatie opzoeken.

U kunt ook [Ngrok](https://ngrok.com/) gebruiken om een tijdelijk adres te genereren.
{% endhint %}

{% hint style="warning" %}

**Voor besturingssystemen zoals Linux of macOS (bijna) UNIX, omdat de instellingen per firewall-service verschillen, moet u zelf informatie opzoeken.**

{% endhint %}

### 6.1 Controleer of port forwarding nodig is

Voer het volgende in het uitvoervenster in en voer het uit.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Als de uitvoer 'True' is, is het goed, maar als het 'False' is, moet u port forwarding instellen.

### 6.2 Verbinding maken met de server

{% tabs %}

{% tab title="Toegang van buitenaf" %}

Als poortdoorsturing niet nodig is of als u al met succes poortdoorsturing heeft ingesteld, kunt u nu verbinding maken met de server.

Het adres dat wordt gebruikt om verbinding te maken met de server, kan hier worden gecontroleerd: [hier](https://ip.pe.kr/)

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Na het opnieuw starten van de server zal Plazma automatisch proberen port forwarding te doen.

Hieronder staat of UPnP succesvol was op basis van de berichten die op de console worden weergegeven, op de console wordt het als `[UPnP] (bericht)` weergegeven.

| Bericht                           | Betekenis                                |
| --------------------------------- | ---------------------------------------- |
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
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

U kunt verbinding maken met de server vanaf uw lokale machine door verbinding te maken met het `192.168.3.7` dat wordt weergegeven als IPv4-adres.

Als de server en het spel op dezelfde pc worden uitgevoerd, kunt u verbinding maken met `localhost`.

{% endtab %}
{% endtabs %}

## 7. Development Stage

Als de server succesvol is gestart en correct werkt, is het nu tijd om de server aan te passen.

Leer hoe u de server kunt aanpassen via de onderstaande gids.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java uitvoeringsomgeving.

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
