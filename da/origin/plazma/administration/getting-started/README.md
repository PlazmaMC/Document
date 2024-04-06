---
description: Lær hvordan du opretter en server med Plazma.
---

# 👟 Kom i gang

For at bruge Plazma på en stabil måde, skal dit system opfylde følgende krav:

|            | Minimum | Anbefalet |
| :--------: | :------ | :-------- |
| Arkitektur | x64     | -         |
|     RAM    | 8GB     | 16GB      |
| Lagerplads | 1GB     | 8GB       |
|     JRE    | 17      | 21        |

For nem redigering af konfigurationsfiler, er det også en god ide at installere en editor som [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE Installation

Som navnet antyder, kræver Minecraft: **"Java"** Edition JRE[^1] for at køre, da det er udviklet i Java.

Da Plazma er baseret på Mojang Studios' officielle serverplatform[^2], skal du også installere JRE for at bruge Plazma.

### 1.1 Kontrollering af JRE

For at kontrollere om JRE er installeret på dit system, skal du indtaste [`cmd /k java --version`](#user-content-fn-4)[^4] i en **Kør**-dialog og udføre kommandoen.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Korrekt output" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE er ikke installeret" lineNumbers="true" %}

```log
'java' er ikke et internt eller eksternt kommando, et kørbart program eller en
batchfil.
```

{% endcode %}

{% code title="JRE er for gammel" lineNumbers="true" %}

```log
Ukendt mulighed: --version
Fejl: Kunne ikke oprette Java Virtual Machine.
Fejl: Der opstod en fatal undtagelse. Programmet afsluttes.
```

{% endcode %}

### 1.2 JRE Installation

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. Først skal du downloade **JDK 21** i `.msi`-format fra [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Kør den downloadede installationsguide og klik på `Næste`.
3. Aktivér `Set JAVA_HOME variable` fra menuen i midten af vinduet og klik derefter på `Næste`.
4. Afslut installationen ved at klikke på `Installer` for at installere JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) download **JDK 21** som en `.dmg` fil fra installationsguiden og kør den for at installere JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Først skal du køre følgende kommando i terminalen for at tilføje Azul Zulu repository til APT.

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

Du kan installere JRE ved at indtaste følgende kommando.

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

**I de fleste tilfælde bruges `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Læs mere</summary>

Navnet på eksekverbar fil er `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping form).jar`.

- **Mapping Form**\
  Mapping er en slags kortlægning mellem Minecrafts faktiske kode og obfuskeringen af koden.
  - **Reobf**\
    Reobfuscated (genfortyndet), også kendt som Spigot-mapping, bruges i de fleste NMS-plugins.\
    Forventes at blive udfaset fra version 1.20.5 og fremefter.
  - **Mojmap**\
    Mojang-mapped, er vanilla Minecraft-mapping.
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

Du kan oprette en startskript via [Flags.sh](https://flags.sh) for at [generere](#user-content-fn-7)[^7]. Når du angiver det hukommelse, du vil bruge i Plazma, vil kommandoen automatisk blive optimeret.

Du kan downloade startscriptet ved at klikke på download-knappen nederst til venstre.\
**Sørg for at startscriptet er kompatibelt med dit operativsystem.**

***

## 4. Fil Oprydning

Flyt det downloadede startscript og Plazma til en ny mappe.

{% hint style="warning" %}

**Mappenavnet skal være uden mellemrum og skal være på engelsk.**

Ellers kan Plazma eller JRE muligvis ikke fungere korrekt.

{% endhint %}

Kør startscriptet nu. For Windows, <mark style="background-color:orange;">i firewall tilladelsesvinduet skal du vælge **Tillad**</mark>.

***

## 5. EULA Accept

Når du har kørt startscriptet en gang, vil der blive oprettet en `eula.txt`-fil i mappen.

EULA[^9] er en licensaftale, som du skal acceptere for at bruge tjenester fra [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

Hvis du ikke accepterer det, kan du ikke starte serveren, og hvis du overtræder EULA, kan du blive pålagt sanktioner, herunder suspension af kontoen.

{% endhint %}

For at acceptere EULA, skal du ændre `eula=false` til `eula=true` i `eula.txt`-filen og gemme ændringerne.

***

## 6. Tillad Ekstern Adgang (Windows)

Moderne operativsystemer blokerer som standard ekstern adgang fra firewall og router for at forhindre farlige tilgange udefra.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Hvis din router ikke understøtter UPnP, skal du søge information om hvordan du gør det, da panelet varierer fra router til router.

Alternativt kan du bruge [Ngrok](https://ngrok.com/) til at oprette en midlertidig adresse.
{% endhint %}

{% hint style="warning" %}

**For Linux eller macOS og andre (næsten) UNIX-baserede operativsystemer, da opsætningsmetoden for firewalltjenester varierer, skal du søge efter oplysninger selv.**

{% endhint %}

### 6.1 Kontrol af Nødvendighed for Portvideresendelse

Indtast følgende i Kør-dialogen og udfør kommandoen.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Hvis outputtet viser `True`, behøver du ikke gøre mere, men hvis det viser `False`, skal du konfigurere portvideresendelse.

### 6.2 Forbindelse til Serveren

{% tabs %}

{% tab title="Ekstern adgang" %}

Hvis port forwarding ikke er nødvendigt, eller hvis du allerede har konfigureret port forwarding korrekt, kan du nu oprette forbindelse til serveren.

Du kan finde den adresse, der bruges til at oprette forbindelse til serveren, [her](https://ip.pe.kr/).

{% endtab %}

{% tab title="Prøv at bruge UPnP til port forwarding" %}

I servermappen, aktiver `network.upnp-port-forwarding` til `true` i `purpur.yml`.

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

{% tab title="Opret midlertidig adresse med Ngrok" %}

Metoden med Ngrok er nyttig til midlertidige tests, samarbejde eller spil med venner.

1. Download ZIP-filen til 'Windows (64-bit)' fra [Ngrok's hjemmeside](https://ngrok.com/download).
2. Placer den downloadede Ngrok i servermappen.
3. Generer en godkendelsestoken fra [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Kør kommandoen, der vises i 'Command Line' i servermappen.
5. Tilføj 'start /b ngrok tcp --region jp 25565' øverst i kørselsskriptet og 'taskkill /f /t /im ngrok.exe' nederst.
6. Fra 'Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565' i konsollen vil '0.tcp.jp.ngrok.io:12345' være serverens adresse.
7. Nu kan du oprette forbindelse eksternt via denne adresse.

{% endtab %}

{% tab title="Forbindelse fra lokalt" %}

Hvis du vil oprette forbindelse til serveren lokalt, kan du bruge `cmd /k ipconfig` i kommandoprompten for at finde din `IPv4-adresse` og oprette forbindelse til den.

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

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="næste-trin.md" %}
[næste-trin.md](næste-trin.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java Runtime Environment.

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
