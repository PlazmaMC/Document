---
description: Lær hvordan du opretter en server med Plazma.
---

# 👟 Kom i gang

For at bruge Plazma på en stabil måde, skal dit system opfylde følgende krav:

|            | Minimum | Anbefalet |
| :--------: | ------: | --------: |
| Arkitektur |     x64 |         - |
|     RAM    |     8GB |      16GB |
| Lagerplads |     1GB |       8GB |
|     JRE    |      17 |        21 |

For nem redigering af konfigurationsfiler, er det også en god ide at installere en editor som [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE Installation

Som navnet antyder, kræver Minecraft: **"Java"** Edition JRE[^1] for at køre, da det er udviklet i Java.

Da Plazma er baseret på Mojang Studios' officielle serverplatform[^2], skal du også installere JRE for at bruge Plazma.

### 1.1 Kontrollering af JRE

For at kontrollere om JRE er installeret på dit system, skal du indtaste [`cmd /k java --version`](#user-content-fn-4)[^4] i en **Kør**-dialog og udføre kommandoen.

Hvis du får følgende output, skal du fortsætte til [trin 2](setup.md#id-2).

{% code title="Korrekt output" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Hvis du ikke får det rigtige output, eller hvis du får følgende output, betyder det at JRE enten ikke er installeret eller er for gammel, og du skal udføre [trin 1.2](setup.md#id-1.2).

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

I denne guide bruger vi Azul Zulu som en af JRE-typerne[^5].

Når installationen er færdig, skal du køre [trin 1.1](setup.md#id-1.1) igen for at kontrollere om installationen er korrekt.

{% tabs %}

{% tab title="Windows" %}

1. Først skal du downloade **JDK 21** i `.msi`-format fra [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Kør den downloadede installationsguide og klik på `Næste`.
3. Aktivér `Set JAVA_HOME variable` fra menuen i midten af vinduet og klik derefter på `Næste`.
4. Afslut installationen ved at klikke på `Installer` for at installere JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) download **JDK 21** som en `.dmg` fil fra installationsguiden og kør den for at installere JRE.

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

Følgende information er for udviklere eller dem der er interesseret i de forskellige formater.\
Hvis du er en almindelig bruger, kan du springe til [trin 3](setup.md#id-3) uden problemer.

{% endhint %}

<details>

<summary>Læs mere</summary>

Navnet på eksekverbar fil er `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping form).jar`.

- **Mapping Form**\
  Mapping er en slags kortlægning mellem Minecrafts faktiske kode og obfuskeringen af koden.
  - **Reobf**\
    Reobfuscation, også kendt som Spigot-mapping, bruges hovedsageligt i de fleste NMS-plugins.\
    Det vil blive udfaset fra version 1.20.5.
  - **Mojmap**\
    Mojang-mapping, Vanilla Minecraft-mapping.
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

Du kan oprette startscriptet ved hjælp af [Flags.sh](https://flags.sh).\
Indtast blot det ønskede hukommelsesforbrug til Plazma[^8], og kommandoen vil automatisk blive optimeret.

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

Hvis du ikke accepterer EULA, kan du ikke starte serveren, og hvis du overtræder EULA'en, kan du blive straffet med suspension af kontoen eller lignende [sanktioner](#user-content-fn-11)[^11].

For at acceptere EULA, skal du ændre `eula=false` til `eula=true` i `eula.txt`-filen og gemme ændringerne.

***

## 6. Tillad Ekstern Adgang (Windows)

Moderne operativsystemer blokerer som standard ekstern adgang fra firewall og router for at forhindre farlige tilgange udefra.

Da du allerede har tilladt det i [trin 3](setup.md#id-3) for Windows, behøver du kun at viderestille portene.

{% hint style="info" %}

**Denne vejledning antager, at du bruger Windows-operativsystemet og en router, der understøtter [UPnP](#user-content-fn-12)[^12].**

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

| Besked                                                   | Betydning                                              |
| -------------------------------------------------------- | ------------------------------------------------------ |
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
6. Fra 'Forwarding tcp\://0.tcp.jp.ngrok.io:12345 -> localhost:25565' i konsollen vil '0.tcp.jp.ngrok.io:12345' være serverens adresse.
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

## 7. Udviklingsfase

Når serveren er startet succesfuldt og kører korrekt, er det nu tid til at tilpasse serveren.

Lær hvordan du tilpasser serveren ved at følge denne vejledning.

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
