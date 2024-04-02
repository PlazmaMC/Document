---
description: Lär dig hur man skapar en server med Plazma.
---

# 👟 Komma igång

För att använda Plazma stabilt måste systemet uppfylla följande krav.

|                 | Minimum | Rekommenderat |
| :-------------: | ------: | ------------: |
|    Arkitektur   |     x64 |             - |
|       RAM       |     8GB |          16GB |
| Lagringsutrymme |     1GB |           8GB |
|       JRE       |      17 |            21 |

För en smidig konfigurationsfilredigering, rekommenderas att installera en redigerare som [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Installera JRE

Som namnet antyder är Minecraft: **"Java"** Edition utvecklad med Java och kräver JRE[^1] för att köras.

Eftersom Plazma är baserad på Mojang Studios officiella serverplattform[^2], måste JRE också installeras för att använda Plazma.

### 1.1 Kontrollera JRE-installationen

För att kontrollera om JRE är installerat på systemet, skriv in [`cmd /k java --version`](#user-content-fn-4)[^4] i Kör-fönstret och kör det.

Om det visas som nedan, hoppa till [steg 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Om det inte visas som ovan eller visas som nedan, saknas JRE eller är för gammal, och du måste utföra [steg 1.2](setup.md#id-1.2).

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

### 1.2 Installera JRE

I den här guiden använder vi Azul Zulu som en av JRE-alternativen[^5].

Efter installationen, kontrollera igen genom att utföra [steg 1.1](setup.md#id-1.1) för att se om installationen har slutförts korrekt.

{% tabs %}

{% tab title="Windows" %}

1. Ladda först ner **JDK 21** i `.msi`-format från [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Kör den nedladdade installationsguiden och klicka på `Nästa`.
3. Aktivera `Set JAVA_HOME variable` från menyn i mitten till vänster och klicka sedan på `Nästa`.
4. Klicka på `Install` för att slutföra JRE-installationen.

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

Kör sedan följande kommando i terminalen för att installera JRE.

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

## 2. Ladda ner Plazma

Plazma erbjuder olika typer av körbara filer.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Följande information är för utvecklare eller de som är intresserade av specifika egenskaper för varje typ.\
Om du är en vanlig användare kan du hoppa till [steg 3](setup.md#id-3) utan problem.

{% endhint %}

<details>

<summary>Läs mer</summary>

Namnet på den körbara filen är `plazma-(versionshanterare)-1.20.4-R0.1-SNAPSHOT-(kartläggningsformat).jar`.

- **Kartläggningsformat**\
  Kartläggning är en slags karta som kopplar samman Minecrafts faktiska kod med förvanskad kod.
  - **Reobf**\
    Reobfuscation, även kallat Spigot-mappning, används främst i NMS-plugins.\
    Från och med 1.20.5 kommer det att sluta användas.
  - **Mojmap**\
    Mojang-mappning, Vanilla Minecraft-mappning.
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

Du kan skapa startskriptet via [Flags.sh](https://flags.sh).\
För Plazma, ange endast [minnesanvändning](#user-content-fn-8)[^8] och kommandot optimeras automatiskt.

Ladda ner startskriptet genom att klicka på nedladdningsknappen längst ner till vänster.\
**Kontrollera att det nedladdade startskriptet matchar ditt operativsystem.**

***

## 4. Rensa filer

Flytta det nedladdade startskriptet och Plazma till en ny mapp.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Annars kan Plazma eller JRE fungera felaktigt.

{% endhint %}

Kör startskriptet nu. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA-överenskommelse

När du har kört startskriptet en gång skapas en `eula.txt`-fil i mappen.

EULA[^9] är ett användaravtal som måste godkännas för att använda [Mojang Studios](#user-content-fn-10)[^10] tjänster.

Om du inte godkänner EULA kan du inte starta servern och om du bryter mot EULA kan du bli avstängd eller straffad på andra sätt [se här](#user-content-fn-11)[^11].

För att godkänna EULA, ändra `eula=false` till `eula=true` i `eula.txt` och spara ändringarna.

***

## 6. Tillåt extern anslutning (Windows)

Modernt operativsystem blockerar externa åtkomster som en säkerhetsåtgärd med brandväggar och routrar som standard.

För Windows, eftersom brandväggen tilläts i [steg 3](setup.md#id-3), behöver du bara vidarebefordra portar.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| Meddelande                             | Betydelse                                          |
| -------------------------------------- | -------------------------------------------------- |
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
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Försök att ansluta till servern lokalt med den IPv4-adress som visas som `192.168.3.7`.

Om servern och spelet körs på samma dator kan du ansluta via `localhost`.

{% endtab %}
{% endtabs %}

## 7. Utvecklingsfas

Om servern har startats framgångsrikt och fungerar korrekt, är det dags att anpassa servern efter dina behov.

Lär dig hur du anpassar servern genom följande guide.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java körningsmiljö.

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
