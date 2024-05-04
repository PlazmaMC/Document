---
description: Saznajte kako stvoriti poslužitelj s Plazmom.
---

# 👟 Početak

Da biste pouzdano koristili Plazmu, sustav mora zadovoljiti sljedeće zahtjeve.

|                     | Minimalno | Preporučeno |
| :-----------------: | --------: | ----------: |
|     Arhitektura     |       x64 |           - |
|         RAM         |       8GB |        16GB |
| Prostorni kapacitet |       1GB |         8GB |
|         JRE         |        17 |          21 |

Za glatku izmjenu konfiguracijskih datoteka, preporučuje se instalacija uređivača poput [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalacija JRE-a

Kao što ime sugerira, Minecraft: **"Java"** Edition je razvijen u Javi te za pokretanje zahtijeva JRE[^1].

Budući da je Plazma temeljena na službenoj platformi za poslužitelje Mojang Studiosa \[^(#user-content-fn-2)], za korištenje Plazme također je potrebna instalacija JRE-a.

### 1.1 Provjera JRE-a

Za provjeru je li JRE instaliran na sustavu, unesite [`cmd /k java --version`](#user-content-fn-4) u [prozor za pokretanje](#user-content-fn-3) i pokrenite naredbu.

Ako se prikaže sljedeći rezultat, preskočite na [2. korak](setup.md#id-2).

{% code title="Ispravan rezultat" overflow="wrap" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Ako se rezultat ne podudara ili se prikaže sljedeće, JRE nije instaliran ili je zastario te je potrebno izvršiti [1.2 korak](setup.md#id-1.2).

{% code title="JRE nije instaliran" overflow="wrap" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE je predugo star" overflow="wrap" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Instalacija JRE

U ovom vodiču koristimo Azul Zulu kao [jednu od vrsta](#user-content-fn-5)[^5] JRE-a.

Nakon instalacije, ponovno izvršite [korak 1.1](setup.md#id-1.1) kako biste provjerili je li instalacija uspješno dovršena.

{% tabs %}
{% tab title="Windows" %}

1. Prvo, preuzmite **JDK 21** u `.msi` formatu s [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Pokrenite preuzeti instalacijski čarobnjak i kliknite `Next`.
3. Nakon što se prikaže meni s lijeve strane prozora, aktivirajte `Set JAVA_HOME variable` i kliknite `Next`.
4. Kliknite `Install` kako biste dovršili instalaciju JRE-a.
   {% endtab %}

{% tab title="macOS" %}
Preuzmite **JDK 21** u `.dmg` formatu s [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) i izvršite instalaciju JRE-a.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
Prvo, izvršite sljedeću naredbu u terminalu kako biste dodali Azul Zulu repozitorij APT-u.

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
Možete instalirati JRE izvršavanjem sljedeće naredbe.

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

### U većini slučajeva koristite `Reobf Paperclip`.

Sljedeći sadržaj je namijenjen developerima ili onima koji su zainteresirani za karakteristike svake vrste.\
Ako ste obični korisnik, možete preskočiti na [korak 3](setup.md#id-3) bez problema.
{% endhint %}

<details>

<summary>Saznajte više</summary>

Naziv izvršne datoteke je `plazma-(verzija upravitelja)-1.20.4-R0.1-SNAPSHOT-(oblik mapiranja).jar`.

- **Oblik mapiranja**\
  Mapiranje je vrsta karte koja povezuje stvarni kod Minecrafta s obfuskiranim kodom.
  - **Reobf**\
    Reobfuscation, također poznato kao Spigot mapiranje, često se koristi u većini NMS dodataka.\
    Planira se prestanak upotrebe od verzije 1.20.5.
  - **Mojmap**\
    Mojang mapiranje, mapiranje za Vanilla Minecraft.
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

Možete generirati skriptu za pokretanje putem [Flags.sh](https://flags.sh).\
Samo unesite količinu memorije koju želite koristiti za Plazmu i naredba će se automatski optimizirati.

Možete preuzeti skriptu za pokretanje klikom na donji desni gumb za preuzimanje.\
**Provjerite je li preuzeta skripta za pokretanje kompatibilna s vašim operativnim sustavom.**

***

## 4. Organiziranje datoteka

Sada premjestite preuzetu skriptu za pokretanje i Plazmu u novi mapu.

{% hint style="warning" %}

### Naziv mape mora biti bez razmaka i postavljen na engleski jezik.

Inače, Plazma ili JRE možda neće ispravno raditi.
{% endhint %}

Sada pokrenite skriptu za pokretanje. Za Windows, <mark style="background-color:orange;">obavezno odaberite</mark> <mark style="background-color:orange;">**Allow**</mark> prilikom odabira prozora za odobrenje firewalla.

***

## 5. EULA suglasnost

Nakon što jednom pokrenete skriptu za pokretanje, u mapi će se stvoriti `eula.txt` datoteka.

EULA[^9] je ugovor o licenciranju koji morate prihvatiti koristeći usluge [Mojang Studios](#user-content-fn-10)[^10].

Ako ne prihvatite EULA-u, nećete moći pokrenuti poslužitelj, a kršenje EULA-e može rezultirati sankcijama poput suspenzije računa i sličnoj [kazni.](#user-content-fn-11)[^11]

Za prihvaćanje EULA-e, promijenite `eula=false` u `eula=true` u datoteci `eula.txt` i spremite promjene.

***

## 6. Dozvoljavanje vanjskih veza (Windows)

Moderne operativne sustave osiguravaju blokiranje vanjskih pristupa putem **firewalla** i **rutera**.

Za Windows, budući da ste omogućili portove u [koraku 3](setup.md#id-3), samo trebate postaviti port forwarding.

{% hint style="info" %}

### U ovom vodiču pretpostavljamo da koristite Windows operativni sustav i [**UPnP**](#user-content-fn-12)[^12] kompatibilni router.

Ako vaš router ne podržava UPnP, svaki router ima različite postavke pa ih morate istražiti sami.

Također, možete koristiti [Ngrok](https://ngrok.com/) za privremenu adresu.
{% endhint %}

{% hint style="warning" %}

### Za Linux ili macOS i ostale (polu) UNIX operativne sustave, postupci postavljanja firewalla ovise o usluzi pa ih morate istražiti sami.

{% endhint %}

### 6.1 Provjera potrebe za port forwardingom

Unesite i pokrenite sljedeću naredbu u naredbenom retku.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Ako rezultat bude `True`, možete završiti ovdje, inače morate postaviti port forwarding.

### 6.2 Povezivanje na poslužitelj

{% tabs %}
{% tab title="Vanjski pristup" %}
Ako ne trebate port forwarding ili ste već uspješno postavili port forwarding, možete se povezati na poslužitelj.

Adresu za povezivanje na poslužitelj možete pronaći [ovdje](https://ip.pe.kr/).
{% endtab %}

{% tab title="Pokušaj UPnP port forwardinga" %}
U datoteci `purpur.yml` poslužitelja, omogućite `network.upnp-port-forwarding` postavljanjem na `true`.

Nakon toga, ponovno pokrenite poslužitelj i Plazma će automatski pokušati postaviti port forwarding.

Uspješnost UPnP-a ovisi o porukama koje se prikazuju u konzoli, a izgledaju kao `[UPnP] (poruka)`.

| Poruka                              | Značenje                                  |
| ----------------------------------- | ----------------------------------------- |
| `Uspješno otvoren port (port)`      | Uspješno postavljanje port forwardinga.   |
| `Port (port) je već otvoren`        | Druga usluga već koristi taj port.        |
| `Neuspješno otvaranje porta (port)` | Neuspješno postavljanje port forwardinga. |
| `Usluga nije dostupna`              | Router ne podržava UPnP.                  |

Kada se poslužitelj zaustavi, Plazma automatski zatvara portove.
{% endtab %}

{% tab title="Generiranje privremene adrese putem Ngroka" %}
Korištenje Ngroka je korisno za privremene testove, zajedničko igranje ili igranje s prijateljima.

1. Preuzmite ZIP datoteku `Windows (64-bit)` s [Ngrok web stranice](https://ngrok.com/download).
2. Stavite preuzetu Ngrok datoteku u mapu poslužitelja.
3. Generirajte autentifikacijski token na [Ngrok nadzornoj ploči](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Izvršite naredbu prikazanu u `Command Line` na mapi poslužitelja.
5. Na vrhu izvršne skripte dodajte `start /b ngrok tcp --region jp 25565`, a na dnu dodajte `taskkill /f /t /im ngrok.exe`.
6. Adresa poslužitelja bit će `0.tcp.jp.ngrok.io:12345` prema poruci `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` koja se prikazuje u konzoli.
7. Sada možete pristupiti putem vanjske adrese.
   {% endtab %}

{% tab title="Pristup s lokalnog računala" %}
Ako pokušavate pristupiti serveru s lokalnog računala, možete se povezati putem `IPv4 adrese` koju ste dobili izvršavanjem `cmd /k ipconfig` u naredbenom retku.

Na primjer, nakon izvršavanja naredbe,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Pokušajte se povezati na server s `192.168.3.7` koji je prikazan kao IPv4 adresa kako biste pristupili serveru s lokalnog računala.

Ako se server i igra izvršavaju na istom PC-ju, možete se povezati putem `localhost`.
{% endtab %}
{% endtabs %}

## 7. Stadij razvoja

Ako je server uspješno pokrenut i ispravno funkcionira, sada je vrijeme da prilagodite server prema svojim potrebama.

Saznajte kako prilagoditi server putem donjeg vodiča.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java izvršno okruženje.

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