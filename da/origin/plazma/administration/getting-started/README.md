---
description: Lær hvordan du opretter en server med Plazma.
---

# 👟 Kom i gang

For at bruge Plazma på en stabil måde, skal dit system opfylde følgende krav:

|            | Minimum | Anbefalet |
| :--------: | ------- | --------- |
| Arkitektur | x64     | -         |
|     RAM    | 8GB     | 16GB      |
| Lagerplads | 1GB     | 8GB       |
|     JDK    | 17      | 21        |

For nem redigering af konfigurationsfiler, er det også en god ide at installere en editor som [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Korrekt output" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' er ikke et internt eller eksternt kommando, et kørbart program eller en
batchfil.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Ukendt mulighed: --version
Fejl: Kunne ikke oprette Java Virtual Machine.
Fejl: Der opstod en fatal undtagelse. Programmet afsluttes.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Først skal du downloade **JDK 21** i `.msi`-format fra [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Kør den downloadede installationsguide og klik på `Næste`.
3. Aktivér `Set JAVA_HOME variable` fra menuen i midten af vinduet og klik derefter på `Næste`.
4. Afslut installationen ved at klikke på `Installer` for at installere JRE.
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

Derefter skal du køre følgende kommando i terminalen for at installere JRE.

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

## 2. Plazma Download

Plazma tilbyder forskellige former for eksekverbare filer.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Læs mere</summary>

Navnet på eksekverbar fil er `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping form).jar`.

- **Mapping Form**\
  Mapping er en slags kortlægning mellem Minecrafts faktiske kode og obfuskeringen af koden.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, er vanilla Minecraft-mapping. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Version Manager**\
  Version Manager er en slags launcher, der er nødvendig for at køre serveren og patche serverfilerne.
  - **Paperclip**\
    Udviklet af PaperMC-teamet til Paper og andre afledte platforme, downloader biblioteker og anvender patches på serveren.
  - **Bundler**\
    Vanilla Minecraft version manager.

</details>

***

## 3. Oprettelse af Start Script

For at starte Plazma nemt og få serveren til automatisk at genstarte, skal du oprette et [start script](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Du kan downloade startscriptet ved at klikke på download-knappen nederst til venstre.\
**Sørg for at startscriptet er kompatibelt med dit operativsystem.**

***

## 4. Fil Oprydning

Flyt det downloadede startscript og Plazma til en ny mappe.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Kør startscriptet nu. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA Accept

Når du har kørt startscriptet en gang, vil der blive oprettet en `eula.txt`-fil i mappen.

EULA[^9] er en licensaftale, som du skal acceptere for at bruge tjenester fra [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

For at acceptere EULA, skal du ændre `eula=false` til `eula=true` i `eula.txt`-filen og gemme ændringerne.

***

## 6. Tillad Ekstern Adgang (Windows)

Moderne operativsystemer blokerer som standard ekstern adgang fra firewall og router for at forhindre farlige tilgange udefra.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Hvis din router ikke understøtter UPnP, skal du søge information om hvordan du gør det, da panelet varierer fra router til router.

Alternativt kan du bruge [Ngrok](https://ngrok.com/) til at oprette en midlertidig adresse.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Kontrol af Nødvendighed for Portvideresendelse

Indtast følgende i Kør-dialogen og udfør kommandoen.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Hvis outputtet viser `True`, behøver du ikke gøre mere, men hvis det viser `False`, skal du konfigurere portvideresendelse.

### 6.2 Forbindelse til Serveren

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Du kan finde den adresse, der bruges til at oprette forbindelse til serveren, [her](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Derefter, når serveren genstartes, vil Plazma automatisk forsøge at videresende porten.

Nedenfor er resultatet af UPnP ifølge meddelelsen, som vises i konsollen som '[UPnP] (besked)'.

| Besked                                                   | Betydning                                                              |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| 'Porten (port) blev åbnet med succes' | Portvideresendelse lykkedes.                           |
| 'Porten (port) er allerede åben'      | En anden tjeneste bruger allerede den pågældende port. |
| 'Kunne ikke åbne porten (port)'       | Portvideresendelse mislykkedes.                        |
| 'Tjenesten er utilgængelig'                              | Routeren understøtter ikke UPnP.                       |

Når serveren lukkes ned, lukker Plazma automatisk porten.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Download ZIP-filen til 'Windows (64-bit)' fra [Ngrok's hjemmeside](https://ngrok.com/download).
2. Placer den downloadede Ngrok i servermappen.
3. Generer en godkendelsestoken fra [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Kør kommandoen, der vises i 'Command Line' i servermappen.
5. Tilføj 'start /b ngrok tcp --region jp 25565' øverst i kørselsskriptet og 'taskkill /f /t /im ngrok.exe' nederst.
6. Fra 'Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565' i konsollen vil '0.tcp.jp.ngrok.io:12345' være serverens adresse.
7. Nu kan du oprette forbindelse eksternt via denne adresse.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

For eksempel, hvis følgende vises efter at kommandoen er kørt,

```log
Windows IP konfiguration

Ethernet-adapter Ethernet:

    Forbundet DNS-suffiks. . . . :
    IPv4-adresse. . . . . . . . : 192.168.3.7
    Subnetmaske. . . . . . . . : 255.255.255.0
    Standardgateway. . . . . . : 192.168.3.1

```

Kan du forsøge at oprette forbindelse til serveren lokalt ved at bruge '192.168.3.7', der vises som IPv4-adressen her.

Hvis serveren og spillet kører på samme PC, kan du oprette forbindelse ved at bruge 'localhost'.
{% endtab %}
{% endtabs %}

## 7. Udvikle sig

Når serveren er startet succesfuldt og kører korrekt, er det nu tid til at tilpasse serveren.

Lær, hvordan du tilpasser serveren ved at følge nedenstående vejledning.

{% content-ref url="næste-trin.md" %}
[næste-trin.md](næste-trin.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Plazma's baseret på Paper, som er baseret på Spigot, der igen er baseret på den officielle serverplatform.

[^3]: Windows-tast + R

[^4]: For Linux, brug 'java --version' i terminalen.

[^5]: JRE er et open source-projekt med flere varianter, ligesom Minecraft-serverplatformen.

[^6]: Det er generelt kendt som en **launcher**.

[^7]: Når 'Auto-genstart' er aktiveret, genstarter serveren automatisk. Du kan afslutte ved at indtaste 'Control + C'.

[^8]: Det anbefales ikke at overskride halvdelen af systemets hukommelse.

    For eksempel, hvis den samlede hukommelseskapacitet er 8 GB, anbefales det ikke at indstille den til over 4 GB.

[^9]: End-User License Agreement, Slutbrugerlicensaftale. Se [Minecraft's hjemmeside](https://www.minecraft.net/ko-kr/usage-guidelines) for flere oplysninger.

[^10]: Microsoft Corporation.

[^11]: I henhold til artikel 32, stk. 1, nr. 9 i loven om fremme af spilindustrien i Sydkorea, kan **Koreanske Microsoft Corporation** retsforfølges.

[^12]: Universal Plug & Play. Purpur inkluderet i Plazma kommunikerer automatisk med routeren via denne teknologi for at åbne porten, når serveren kører, så der er ikke behov for manuel portvideresendelse.

[^13]: Hvis du ikke har en konto, kan du tilmelde dig Ngrok ved hjælp af en Google- eller GitHub-konto.
