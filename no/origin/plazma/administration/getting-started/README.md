---
description: Lær hvordan du oppretter en server med Plazma.
---

# 👟 Kom i gang

For å bruke Plazma på en stabil måte, må systemet oppfylle følgende krav:

|               | Minimum | Anbefalt |
| :-----------: | ------: | -------: |
|   Arkitektur  |     x64 |        - |
|      RAM      |     8GB |     16GB |
| Lagringsplass |     1GB |      8GB |
|      JRE      |      17 |       21 |

For en smidig konfigurasjonsfilredigering, er det også bra å installere en redaktør som [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE-installasjon

Som navnet antyder, er Minecraft: **"Java"** Edition utviklet i Java, så for å kjøre den trenger du JRE[^1].

Siden Plazma er basert på Mojang Studios' offisielle serverplattform[^2], må du også installere JRE for å bruke Plazma.

### 1.1 Kontroller om JRE er installert

For å sjekke om JRE er installert på systemet, skriv inn [`cmd /k java --version`](#user-content-fn-4)[^4] i Kjør-vinduet og kjør det.

Hvis du ser følgende utdata, hopp til [trinn 2](setup.md#id-2).

{% code title="Riktig utskrift" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Hvis du ikke ser det ovennevnte, eller ser noe som nedenfor, betyr det at JRE ikke er installert eller er for gammel, og du må utføre [trinn 1.2](setup.md#id-1.2).

{% code title="JRE er ikke installert" lineNumbers="true" %}

```log
'java' er ikke et internt eller eksternt kommando, et kjørbart program eller en batchfil.
```

{% endcode %}

{% code title="JRE er for gammel" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Installer JRE

I denne veiledningen bruker vi Azul Zulu som en av JRE-variantene[^5].

Etter at du har installert det, utfør [trinn 1.1](setup.md#id-1.1) på nytt for å bekrefte at installasjonen var vellykket.

{% tabs %}

{% tab title="Windows" %}

1. Først laster du ned **JDK 21** fra [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) i `.msi`-format.
2. Kjør den nedlastede installasjonsveiviseren og klikk `Next`.
3. Aktiver `Set JAVA_HOME variable` fra menyen som vises midt på venstre side av vinduet, og klikk deretter `Next`.
4. Trykk på `Install` for å fullføre JRE-installasjonen.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) der **JDK 21** kan lastes ned som en `.dmg`-installasjonsveiviser fra og kjøres for å installere JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Legg til Azul Zulu-repositoriet i APT ved å kjøre følgende kommando i terminalen først.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Deretter installerer du JRE ved å kjøre følgende kommando i terminalen.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Du kan installere JRE ved å bruke følgende kommando.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma nedlasting

Plazma tilbyr forskjellige typer kjørbare filer.

{% hint style="warning" %}

**I de fleste tilfeller bruker du `Reobf Paperclip`.**

Nedenfor informasjonen er for utviklere eller de som er interessert i egenskapene til hver type.\
Hvis du er en vanlig bruker, kan du hoppe til [trinn 3](setup.md#id-3) uten problemer.

{% endhint %}

<details>

<summary>Les mer</summary>

Navnet på kjørefilen er `plazma-(versjonsbehandler)-1.20.4-R0.1-SNAPSHOT-(mappingtype).jar`.

- **Mappingtype**\
  Mapping er en slags veikart som knytter Minecrafts faktiske kode til obfuskert kode.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.5부터 사용이 종료될 예정입니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다.
- **Versjonsbehandler**\
  En versjonsbehandler er en launcher for serveren som trengs for å kjøre serveren og patche serverfiler.
  - **Paperclip**\
    Utviklet av PaperMC-teamet for Paper og andre avledede plattformer, laster ned biblioteker og bruker patcher på serveren.
  - **Bundler**\
    Vanilla Minecraft-versjonsbehandler.

</details>

***

## 3. Opprettelse av startskript

For enkel oppstart og automatisert omstart av serveren med Plazma, må du lage et [startskript](#user-content-fn-6)[^6].

Du kan generere et startskript via [Flags.sh](https://flags.sh). Når du har oppgitt [minnebruken til Plazma](#user-content-fn-8)[^8], vil kommandoen optimaliseres automatisk.

Du kan laste ned startskriptet ved å klikke på nedlastingsknappen nederst til venstre.\
**Sjekk om det nedlastede startskriptet samsvarer med operativsystemet ditt.**

***

## 4. Filopprydding

Flytt det nedlastede startskriptet og Plazma til en ny mappe.

{% hint style="warning" %}

**Mappenavnet må ikke inneholde mellomrom og må være på engelsk.**

Ellers kan Plazma eller JRE kanskje ikke fungere riktig.

{% endhint %}

Kjør startskriptet nå. For Windows må du <mark style="background-color:orange;">velge **Tillat** i brannmurtilgangsvinduet.</mark>

***

## 5. EULA-samtykke

Når du kjører startskriptet, opprettes en `eula.txt`-fil i mappen.

EULA[^9] er en lisensavtale du må godta for å bruke tjenestene til [Mojang Studios](#user-content-fn-10)[^10].

Hvis du ikke godtar EULA-en, kan du ikke starte serveren, og brudd på EULA-en kan føre til sanksjoner som suspensjon av kontoen, osv. [Les mer.](#user-content-fn-11)[^11]

Hvis du godtar EULA-en, endre `eula=false` til `eula=true` i `eula.txt`-filen og lagre endringene.

***

## 6. Tillat ekstern tilkobling (Windows)

Moderne operativsystemer blokkerer som standard ekstern tilgang for å forhindre farlige tilnærminger via brannmur og rutere.

For Windows, siden du har tillatt det i [trinn 3](setup.md#id-3), trenger du bare å konfigurere portvideresending.

{% hint style="info" %}

**Denne veiledningen antar at du bruker Windows-operativsystemet og en ruter som støtter [UPnP](#user-content-fn-12)[^12].**

Hvis ruteren ikke støtter UPnP, må du søke etter informasjon om konfigurering for ulike rutere.

Alternativt kan du bruke [Ngrok](https://ngrok.com/) for å opprette en midlertidig adresse.
{% endhint %}

{% hint style="warning" %}

**For (semi-)UNIX-baserte operativsystemer som Linux eller macOS, må du søke etter informasjon om hvordan du konfigurerer brannmuren for hver tjeneste, da prosedyrene vil variere.**

{% endhint %}

### 6.1 Sjekk om portvideresending er nødvendig

Skriv inn følgende i Kjør-vinduet og kjør det.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Hvis utdataen er `True`, er du ferdig her. Hvis den er `False`, må du konfigurere portvideresending.

### 6.2 Koble til serveren

{% tabs %}

{% tab title="Tilgang utenfra" %}

Hvis du ikke trenger portvideresending, eller allerede har konfigurert det, kan du nå koble til serveren.

Du kan finne adressen som brukes for å koble til serveren [her](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Deretter, når serveren startes på nytt, vil Plazma automatisk prøve å videresende porten.

Nedenfor er betydningen av meldingene som vises på konsollen for å indikere om UPnP var vellykket, og de vises som `[UPnP] (melding)` på konsollen.

| Melding                             | Betydning                                     |
| ----------------------------------- | --------------------------------------------- |
| `Porten ble åpnet vellykket (port)` | Videresending av porten var vellykket.        |
| `Porten (port) er allerede åpen`    | En annen tjeneste bruker allerede den porten. |
| `Kunne ikke åpne porten (port)`     | Videresending av porten mislyktes.            |
| `Tjenesten er utilgjengelig`        | Ruteren støtter ikke UPnP.                    |

Når serveren er stoppet, lukker Plazma automatisk porten.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Last ned ZIP-filen for `Windows (64-bit)` fra [Ngrok-nettsiden](https://ngrok.com/download).
2. Legg den nedlastede Ngrok-filen i servermappen.
3. Generer en godkjennelsestoken fra [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Kjør kommandoen som vises i `Command Line` i servermappen.
5. Legg til `start /b ngrok tcp --region jp 25565` øverst i kjøreskriptet, og `taskkill /f /t /im ngrok.exe` nederst.
6. Fra meldingen som vises øverst i konsollen, vil `0.tcp.jp.ngrok.io:12345` være serverens adresse.
7. Du kan nå koble til serveren eksternt ved hjelp av denne adressen.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

For eksempel, når du kjører kommandoen og får følgende utdata,

```log
Windows IP-konfigurasjon

Ethernet-adapter Ethernet:

    Tilkoblings-spesifikt DNS-suffiks. . . . :
    IPv4-adresse. . . . . . . . . : 192.168.3.7
    Nettverksmaske. . . . . . . . : 255.255.255.0
    Standard gateway. . . . . . . : 192.168.3.1

```

Du kan koble til serveren lokalt ved å bruke `192.168.3.7` som vises i IPv4-adressen her.

Hvis serveren og spillet kjører på samme PC, kan du koble til med `localhost`.

{% endtab %}
{% endtabs %}

## 7. Utviklingssteg

Når serveren er startet vellykket og fungerer som den skal, er det på tide å tilpasse serveren.

Lær hvordan du tilpasser serveren ved å følge guiden nedenfor.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java kjøretidsmiljø.

[^2]: Plazma, basert på Paper, som igjen er basert på Spigot, som er basert på den offisielle serverplattformen.

[^3]: Windows-tast + R

[^4]: For Linux, bruk `java --version` i terminalen.

[^5]: JRE er en av mange åpen kildekodeprosjekter, som Minecraft-serverplattformen.

[^6]: Det er vanligvis kjent som en **launcher**.

[^7]: Hvis du aktiverer "Auto-restart", vil serveren starte på nytt automatisk. Du kan avslutte ved å trykke `Control + C`.

[^8]: Det anbefales ikke å overskride halvparten av systemets minnekapasitet.

    For eksempel, hvis systemets totale minnekapasitet er 8GB, bør du ikke sette det høyere enn 4GB.

[^9]: End-User License Agreement, sluttbrukerlisensavtale. Se [Minecrafts nettsted](https://www.minecraft.net/ko-kr/usage-guidelines) for mer informasjon.

[^10]: Microsoft Corporation.

[^11]: I henhold til lov om fremme av spillindustrien i Korea, paragraf 32, punkt 9, kan du saksøke **Korea Microsoft Corporation**.

[^12]: Universal Plug & Play. Purpur inkludert i Plazma kommuniserer automatisk med ruteren via denne teknologien for å åpne porten bare når serveren kjører, så du trenger ikke å videresende porten manuelt.

[^13]: Hvis du ikke har en konto, kan du registrere deg på Ngrok med Google- eller GitHub-kontoen din.
