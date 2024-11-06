---
description: Lär dig hur man skapar en server med Plazma.
---

# 👟 Komma igång

För att använda Plazma stabilt måste systemet uppfylla följande krav.

|                 | Minimum | Rekommenderat |
| :-------------: | ------- | ------------- |
|    Arkitektur   | x64     | -             |
|       RAM       | 8GB     | 16GB          |
| Lagringsutrymme | 1GB     | 8GB           |
|       JDK       | 17      | 21            |

För en smidig konfigurationsfilredigering, rekommenderas att installera en redigerare som [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Korrekt utmatning" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' är inte ett internt eller externt kommando, ett körbart program eller
en satsfil.
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

1. Ladda först ner **JDK 21** i `.msi`-format från [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Kör den nedladdade installationsguiden och klicka på `Nästa`.
3. Aktivera `Set JAVA_HOME variable` från menyn i mitten till vänster och klicka sedan på `Nästa`.
4. Klicka på `Install` för att slutföra JRE-installationen.
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

Kör sedan följande kommando i terminalen för att installera JRE.

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

## 2. Ladda ner Plazma

Plazma erbjuder olika typer av körbara filer.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Läs mer</summary>

Namnet på den körbara filen är `plazma-(versionshanterare)-1.20.4-R0.1-SNAPSHOT-(kartläggningsformat).jar`.

- **Kartläggningsformat**\
  Kartläggning är en slags karta som kopplar samman Minecrafts faktiska kod med förvanskad kod.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mappad, är en Vanilla Minecraft-mappning. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Versionshanterare**\
  Versionshanteraren är en launcher för servern som behövs för att köra servern och patcha serverfiler.
  - **Paperclip**\
    Utvecklad av PaperMC-teamet för Paper och andra derivatplattformar, laddar ner bibliotek och tillämpar patcher på servern.
  - **Bundler**\
    Vanilla Minecraft versionshanterare.

</details>

***

## 3. Skapa startskript

För att enkelt starta Plazma och låta servern starta om automatiskt behöver du skapa ett [startskript](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Ladda ner startskriptet genom att klicka på nedladdningsknappen längst ner till vänster.\
**Kontrollera att det nedladdade startskriptet matchar ditt operativsystem.**

***

## 4. Rensa filer

Flytta det nedladdade startskriptet och Plazma till en ny mapp.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Kör startskriptet nu. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA-överenskommelse

När du har kört startskriptet en gång skapas en `eula.txt`-fil i mappen.

EULA[^9] är ett användaravtal som måste godkännas för att använda [Mojang Studios](#user-content-fn-10)[^10] tjänster.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

För att godkänna EULA, ändra `eula=false` till `eula=true` i `eula.txt` och spara ändringarna.

***

## 6. Tillåt extern anslutning (Windows)

Modernt operativsystem blockerar externa åtkomster som en säkerhetsåtgärd med brandväggar och routrar som standard.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Om routern inte stöder UPnP, varje router har olika paneler så du måste söka efter information själv.

Alternativt kan du använda [Ngrok](https://ngrok.com/) för att skapa en temporär adress.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Kontrollera om portöversättning behövs

Skriv in följande i Kör-fönstret och kör det.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Om utmatningen är `True` är du klar, om den är `False` behöver du ställa in portöversättning.

### 6.2 Anslut till servern

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Adressen som används för att ansluta till servern kan hittas [här](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Därefter, om servern startas om, kommer Plazma automatiskt att försöka vidarebefordra porten.

Nedan visas om UPnP lyckades enligt meddelandet som visas i konsolen, som kommer att vara i formatet `[UPnP] (meddelande)`.

| Meddelande                             | Betydelse                                                          |
| -------------------------------------- | ------------------------------------------------------------------ |
| `Porten (port)` öppnades framgångsrikt | Port vidarebefordran lyckades.                     |
| `Porten (port) är redan öppen`         | En annan tjänst använder redan den angivna porten. |
| `Misslyckades att öppna porten (port)` | Port vidarebefordran misslyckades.                 |
| `Tjänsten är inte tillgänglig`         | Routern stöder inte UPnP.                          |

När servern stängs av kommer Plazma automatiskt att stänga porten.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Ladda ner ZIP-filen `Windows (64-bit)` från [Ngroks hemsida](https://ngrok.com/download).
2. Placera den nedladdade Ngrok-filen i servermappen.
3. Skapa en [autentiserings token](#user-content-fn-13)[^13] från [Ngroks instrumentpanel](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Kör kommandot som visas i `Command Line` i servermappen.
5. Lägg till `start /b ngrok tcp --region jp 25565` längst upp i startskriptet, och `taskkill /f /t /im ngrok.exe` längst ner.
6. Från `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` i toppen av konsolen, är `0.tcp.jp.ngrok.io:12345` serverns adress.
7. Nu kan du ansluta externt via denna adress.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Till exempel, om följande visas efter att kommandot har körts,

```log
Windows IP-konfiguration

Ethernet-adapter Ethernet:

    Anslutnings-specifikt DNS-suffix. . . . . . . :
    IPv4-adress. . . . . . . . . . . . . . . . . : 192.168.3.7
    Nätmask. . . . . . . . . . . . . . . . . . . : 255.255.255.0
    Standard-gateway. . . . . . . . . . . . . . : 192.168.3.1

```

Försök att ansluta till servern lokalt med den IPv4-adress som visas som `192.168.3.7`.

Om servern och spelet körs på samma dator kan du ansluta via `localhost`.
{% endtab %}
{% endtabs %}

## 7. Utveckla

Om servern har startats framgångsrikt och fungerar korrekt, är det dags att anpassa servern efter dina behov.

Ta reda på hur du anpassar servern med hjälp av följande handledning.

{% content-ref url="nasta-steg.md" %}
[nasta-steg.md](nasta-steg.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Paper, som Plazma är baserat på, är i sin tur baserat på Spigot, som i sin tur är baserat på den officiella serverplattformen.

[^3]: Windows-tangent + R

[^4]: För Linux, kör `java --version` i terminalen.

[^5]: JRE är en öppen källkodsprojekt och finns i olika varianter, liknande Minecraft serverplattformen.

[^6]: Det är vanligtvis känt som en **launcher**.

[^7]: Genom att aktivera "Auto-start" kommer servern att starta om automatiskt. Du kan avsluta genom att trycka `Control + C`.

[^8]: Det rekommenderas inte att använda mer än hälften av systemets minne.

    Till exempel, om systemets totala minneskapacitet är 8GB, är det inte rekommenderat att använda mer än 4GB.

[^9]: End-User License Agreement, Slutanvändarlicensavtal. Kontrollera [Minecrafts hemsida](https://www.minecraft.net/ko-kr/usage-guidelines) för mer information.

[^10]: Microsoft Corporation.

[^11]: Enligt lag om spelindustrins främjande i Republiken Korea artikel 32 punkt 1 punkt 9, kan juridiska åtgärder vidtas av **Koreas Microsoft Corporation**.

[^12]: Universal Plug & Play. Purpur som ingår i Plazma kommunicerar automatiskt med routern via denna teknik för att endast öppna porten när servern körs, vilket eliminerar behovet av manuell port vidarebefordran.

[^13]: Om du inte har ett konto kan du registrera dig på Ngrok med ditt Google- eller GitHub-konto.
