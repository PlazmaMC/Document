---
description: Saznajte kako stvoriti poslužitelj s Plazmom.
---

# 👟 Početak

Da biste pouzdano koristili Plazmu, sustav mora zadovoljiti sljedeće zahtjeve.

|                     | Minimalno | Preporučeno |
| :-----------------: | --------- | ----------- |
|     Arhitektura     | x64       | -           |
|         RAM         | 8GB       | 16GB        |
| Prostorni kapacitet | 1GB       | 8GB         |
|         JDK         | 17        | 21          |

Za glatku izmjenu konfiguracijskih datoteka, preporučuje se instalacija uređivača poput [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Ispravan ispis" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' je unutarnja ili vanjska naredba, izvršivi program, ili
skripta datoteka.
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

1. Prvo, preuzmite **JDK 21** u `.msi` formatu s [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Pokrenite preuzeti instalacijski čarobnjak i kliknite `Next`.
3. Nakon što se prikaže meni s lijeve strane prozora, aktivirajte `Set JAVA_HOME variable` i kliknite `Next`.
4. Kliknite `Install` kako biste dovršili instalaciju JRE-a.
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

Zatim, izvršite sljedeću naredbu u terminalu kako biste instalirali JRE.

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

## 2. Preuzimanje Plazme

Plazma pruža različite vrste izvršnih datoteka.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Saznajte više</summary>

Naziv izvršne datoteke je `plazma-(verzija upravitelja)-1.20.4-R0.1-SNAPSHOT-(oblik mapiranja).jar`.

- **Oblik mapiranja**\
  Mapiranje je vrsta karte koja povezuje stvarni kod Minecrafta s obfuskiranim kodom.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang mapiranje, mapiranje za Vanilla Minecraft. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Upravitelj verzijama**\
  Upravitelj verzijama je vrsta pokretača potrebnog za pokretanje poslužitelja koji služi kao biblioteka i primjenjuje zakrpe na datoteke poslužitelja.
  - **Paperclip**\
    Upravitelj razvijen od strane PaperMC tima za Paper i druge izvedene platforme, preuzima biblioteke i primjenjuje zakrpe na poslužitelj.
  - **Bundler**\
    Upravitelj verzijama za Vanilla Minecraft.

</details>

***

## 3. Izrada skripte za pokretanje

Da biste jednostavno pokrenuli Plazmu i omogućili automatsko ponovno pokretanje poslužitelja, morate napraviti [skriptu za pokretanje](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Možete preuzeti skriptu za pokretanje klikom na donji desni gumb za preuzimanje.\
**Provjerite je li preuzeta skripta za pokretanje kompatibilna s vašim operativnim sustavom.**

***

## 4. Organiziranje datoteka

Sada premjestite preuzetu skriptu za pokretanje i Plazmu u novi mapu.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Sada pokrenite skriptu za pokretanje. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA suglasnost

Nakon što jednom pokrenete skriptu za pokretanje, u mapi će se stvoriti `eula.txt` datoteka.

EULA[^9] je ugovor o licenciranju koji morate prihvatiti koristeći usluge [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Za prihvaćanje EULA-e, promijenite `eula=false` u `eula=true` u datoteci `eula.txt` i spremite promjene.

***

## 6. Dozvoljavanje vanjskih veza (Windows)

Moderne operativne sustave osiguravaju blokiranje vanjskih pristupa putem **firewalla** i **rutera**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Ako vaš router ne podržava UPnP, svaki router ima različite postavke pa ih morate istražiti sami.

Također, možete koristiti [Ngrok](https://ngrok.com/) za privremenu adresu.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Provjera potrebe za port forwardingom

Unesite i pokrenite sljedeću naredbu u naredbenom retku.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Ako rezultat bude `True`, možete završiti ovdje, inače morate postaviti port forwarding.

### 6.2 Povezivanje na poslužitelj

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Adresu za povezivanje na poslužitelj možete pronaći [ovdje](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Nakon toga, ponovno pokrenite poslužitelj i Plazma će automatski pokušati postaviti port forwarding.

Uspješnost UPnP-a ovisi o porukama koje se prikazuju u konzoli, a izgledaju kao `[UPnP] (poruka)`.

| Poruka                              | Značenje                                                  |
| ----------------------------------- | --------------------------------------------------------- |
| `Uspješno otvoren port (port)`      | Uspješno postavljanje port forwardinga.   |
| `Port (port) je već otvoren`        | Druga usluga već koristi taj port.        |
| `Neuspješno otvaranje porta (port)` | Neuspješno postavljanje port forwardinga. |
| `Usluga nije dostupna`              | Router ne podržava UPnP.                  |

Kada se poslužitelj zaustavi, Plazma automatski zatvara portove.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Preuzmite ZIP datoteku `Windows (64-bit)` s [Ngrok web stranice](https://ngrok.com/download).
2. Stavite preuzetu Ngrok datoteku u mapu poslužitelja.
3. Generirajte autentifikacijski token na [Ngrok nadzornoj ploči](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Izvršite naredbu prikazanu u `Command Line` na mapi poslužitelja.
5. Na vrhu izvršne skripte dodajte `start /b ngrok tcp --region jp 25565`, a na dnu dodajte `taskkill /f /t /im ngrok.exe`.
6. Adresa poslužitelja bit će `0.tcp.jp.ngrok.io:12345` prema poruci `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` koja se prikazuje u konzoli.
7. Sada možete pristupiti putem vanjske adrese.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Na primjer, nakon izvršavanja naredbe,

```log
Windows IP konfiguracija

Ethernet adapter Ethernet:

    Povezani DNS sufiks. . . . :
    IPv4 adresa. . . . . . . . . : 192.168.3.7
    Mrežna maska . . . . . . . : 255.255.255.0
    Zadani prolaz. . . . . . . : 192.168.3.1

```

Pokušajte se povezati na server s `192.168.3.7` koji je prikazan kao IPv4 adresa kako biste pristupili serveru s lokalnog računala.

Ako se server i igra izvršavaju na istom PC-ju, možete se povezati putem `localhost`.
{% endtab %}
{% endtabs %}

## 7. Rast

Ako je server uspješno pokrenut i ispravno funkcionira, sada je vrijeme da prilagodite server prema svojim potrebama.

Pročitajte dolje navedeni priručnik kako biste saznali kako prilagoditi poslužitelj.

{% content-ref url="sljedeci-korak.md" %}
[sljedeci-korak.md](sljedeci-korak.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Paper, temeljen na Plazmi, temelji se na Spigotu, koji je službeni server platforma.

[^3]: Windows tipka + R

[^4]: Za Linux korisnike, u terminalu upišite `java --version`

[^5]: JRE je jedan od open source projekata, slično kao Minecraft server platforme, postoji nekoliko vrsta.

[^6]: Općenito se naziva **launcher**.

[^7]: Aktiviranjem "Auto-restart" opcije server će se automatski ponovno pokrenuti. Možete završiti unosom `Control + C`.

[^8]: Nije preporučljivo premašiti više od polovice resursa sustava.

    Na primjer, ako je ukupni kapacitet memorije sustava 8GB, nije preporučljivo postaviti ga na više od 4GB.

[^9]: Ugovor o licenciranju za krajnjeg korisnika, EULA. Za više informacija posjetite [Minecraft web stranicu](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: Prema članku 32. stavku 1. točki 9. Zakona o poticanju industrije igara u Republici Koreji, moguće je pokrenuti sudski postupak protiv **Korejske Microsoft korporacije**.

[^12]: Universal Plug & Play. Purpur uključen u Plazmu automatski komunicira s usmjerivačem putem ovog tehnološkog rješenja, otvarajući vrata samo kada je poslužitelj pokrenut, stoga nije potrebno ručno postavljati prosljeđivanje vrata.

[^13]: U slučaju da nemate račun, registrirajte se na Ngrok putem Google ili GitHub računa.
