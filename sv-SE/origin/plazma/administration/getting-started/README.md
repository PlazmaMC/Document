---
description: Lär dig hur man skapar en server med Plazma.
---

# 👟 Komma igång

För att använda Plazma stabilt måste systemet uppfylla följande krav.

|                 | Minimum | Rekommenderat |
| :-------------: | :------ | :------------ |
|    Arkitektur   | x64     | -             |
|       RAM       | 8GB     | 16GB          |
| Lagringsutrymme | 1GB     | 8GB           |
|       JRE       | 17      | 21            |

För en smidig konfigurationsfilredigering, rekommenderas att installera en redigerare som [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Installera JRE

Som namnet antyder är Minecraft: **"Java"** Edition utvecklad med Java och kräver JRE[^1] för att köras.

Eftersom Plazma är baserad på Mojang Studios officiella serverplattform[^2], måste JRE också installeras för att använda Plazma.

### 1.1 Kontrollera JRE-installationen

För att kontrollera om JRE är installerat på systemet, skriv in [`cmd /k java --version`](#user-content-fn-4)[^4] i Kör-fönstret och kör det.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Korrekt utmatning" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE är inte installerat" lineNumbers="true" %}

```log
'java' är inte ett internt eller externt kommando, ett körbart program eller
en satsfil.
```

{% endcode %}

{% code title="JRE är för gammalt" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Installera JRE

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. Ladda först ner **JDK 21** i `.msi`-format från [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Kör den nedladdade installationsguiden och klicka på `Nästa`.
3. Aktivera `Set JAVA_HOME variable` från menyn i mitten till vänster och klicka sedan på `Nästa`.
4. Klicka på `Install` för att slutföra JRE-installationen.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) laddar ner och kör installationsguiden för **JDK 21** i `.dmg` format för att installera JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Lägg först till Azul Zulu-förrådet i APT genom att köra följande kommando i terminalen.

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

Du kan installera JRE genom att köra följande kommando.

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

**I de flesta fall används `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Läs mer</summary>

Namnet på den körbara filen är `plazma-(versionshanterare)-1.20.4-R0.1-SNAPSHOT-(kartläggningsformat).jar`.

- **Kartläggningsformat**\
  Kartläggning är en slags karta som kopplar samman Minecrafts faktiska kod med förvanskad kod.
  - **Reobf**\
    Reobfuscated (återfördunklad), även känd som Spigot-mappning, används i de flesta NMS-plugins.\
    Kommer att sluta användas från och med 1.20.5.
  - **Mojmap**\
    Mojang-mappad, är en Vanilla Minecraft-mappning.
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

Genom [Flags.sh](https://flags.sh) kan du skapa startskript med [generering](#user-content-fn-7)[^7]. Ange bara det [minne som ska användas](#user-content-fn-8)[^8] i Plazma så optimeras kommandot automatiskt.

Ladda ner startskriptet genom att klicka på nedladdningsknappen längst ner till vänster.\
**Kontrollera att det nedladdade startskriptet matchar ditt operativsystem.**

***

## 4. Rensa filer

Flytta det nedladdade startskriptet och Plazma till en ny mapp.

{% hint style="warning" %}

**Mappnamnet ska alltid vara utan mellanslag och vara på engelska.**

Annars kan Plazma eller JRE fungera felaktigt.

{% endhint %}

Kör startskriptet nu. För Windows måste du i <mark style="background-color:orange;">brandväggens tillåtningsdialog välja **Tillåt**</mark>.

***

## 5. EULA-överenskommelse

När du har kört startskriptet en gång skapas en `eula.txt`-fil i mappen.

EULA[^9] är ett användaravtal som måste godkännas för att använda [Mojang Studios](#user-content-fn-10)[^10] tjänster.

{% hint style="warning" %}

Om du inte samtycker kan du inte starta servern och om du bryter mot EULA kan du bli [straffad](#user-content-fn-11)[^11] genom att kontot stängs av.

{% endhint %}

För att godkänna EULA, ändra `eula=false` till `eula=true` i `eula.txt` och spara ändringarna.

***

## 6. Tillåt extern anslutning (Windows)

Modernt operativsystem blockerar externa åtkomster som en säkerhetsåtgärd med brandväggar och routrar som standard.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Om routern inte stöder UPnP, varje router har olika paneler så du måste söka efter information själv.

Alternativt kan du använda [Ngrok](https://ngrok.com/) för att skapa en temporär adress.
{% endhint %}

{% hint style="warning" %}

**För operativsystem som Linux eller macOS (och liknande UNIX-system) kan inställningarna för brandvärdstjänster variera, så du måste söka efter information själv.**

{% endhint %}

### 6.1 Kontrollera om portöversättning behövs

Skriv in följande i Kör-fönstret och kör det.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Om utmatningen är `True` är du klar, om den är `False` behöver du ställa in portöversättning.

### 6.2 Anslut till servern

{% tabs %}

{% tab title="Extern anslutning" %}

Om port vidarebefordran inte behövs, eller om du redan har lyckats med port vidarebefordran, kan du nu ansluta till servern.

Adressen som används för att ansluta till servern kan hittas [här](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 port forwarding försök" %}

I 'purpur.yml' i servermappen, aktivera 'network.upnp-port-forwarding' till 'true'.

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

{% tab title="Skapa temporär adress med Ngrok" %}

Användning av Ngrok är användbart för kortvariga tester, deltagande eller att spela med vänner.

1. Ladda ner ZIP-filen `Windows (64-bit)` från [Ngroks hemsida](https://ngrok.com/download).
2. Placera den nedladdade Ngrok-filen i servermappen.
3. Skapa en [autentiserings token](#user-content-fn-13)[^13] från [Ngroks instrumentpanel](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Kör kommandot som visas i `Command Line` i servermappen.
5. Lägg till `start /b ngrok tcp --region jp 25565` längst upp i startskriptet, och `taskkill /f /t /im ngrok.exe` längst ner.
6. Från `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` i toppen av konsolen, är `0.tcp.jp.ngrok.io:12345` serverns adress.
7. Nu kan du ansluta externt via denna adress.

{% endtab %}

{% tab title="Anslutning från lokalt" %}

Om du försöker ansluta till servern lokalt, kan du använda 'IPv4 address' som visas genom att köra 'cmd /k ipconfig' i kommandotolken.

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

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="nasta-steg.md" %}
[nasta-steg.md](nasta-steg.md)
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
