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

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Hvis du ikke ser det ovennevnte, eller ser noe som nedenfor, betyr det at JRE ikke er installert eller er for gammel, og du må utføre [trinn 1.2](setup.md#id-1.2).

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

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

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

다음 명령어를 입력하여 JRE를 설치할 수 있습니다.

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

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Nedenfor informasjonen er for utviklere eller de som er interessert i egenskapene til hver type.\
Hvis du er en vanlig bruker, kan du hoppe til [trinn 3](setup.md#id-3) uten problemer.

{% endhint %}

<details>

<summary>Les mer</summary>

Navnet på kjørefilen er `plazma-(versjonsbehandler)-1.20.4-R0.1-SNAPSHOT-(mappingtype).jar`.

- **Mappingtype**\
  Mapping er en slags veikart som knytter Minecrafts faktiske kode til obfuskert kode.
  - **Reobf**\
    Reobfuscation, også kjent som Spigot-mapping, brukes i de fleste NMS-plug-ins.\
    Det vil bli avsluttet fra 1.20.5.
  - **Mojmap**\
    Mojang-mapping, Vanilla Minecraft-mapping.
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

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Ellers kan Plazma eller JRE kanskje ikke fungere riktig.

{% endhint %}

Kjør startskriptet nå. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

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

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Hvis ruteren ikke støtter UPnP, må du søke etter informasjon om konfigurering for ulike rutere.

Alternativt kan du bruke [Ngrok](https://ngrok.com/) for å opprette en midlertidig adresse.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Sjekk om portvideresending er nødvendig

Skriv inn følgende i Kjør-vinduet og kjør det.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Hvis utdataen er `True`, er du ferdig her. Hvis den er `False`, må du konfigurere portvideresending.

### 6.2 Koble til serveren

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

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
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Du kan koble til serveren lokalt ved å bruke `192.168.3.7` som vises i IPv4-adressen her.

Hvis serveren og spillet kjører på samme PC, kan du koble til med `localhost`.

{% endtab %}
{% endtabs %}

## 7. Utviklingssteg

Når serveren er startet vellykket og fungerer som den skal, er det på tide å tilpasse serveren.

Lær hvordan du tilpasser serveren ved å følge guiden nedenfor.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
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
