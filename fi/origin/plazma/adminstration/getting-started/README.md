---
description: Selvitä, miten luodaan palvelin Plazma-sovelluksella.
---

# 👟 Aloita

Plazman vakaa käyttö vaatii, että järjestelmä täyttää seuraavat vaatimukset.

|               | Vähimmäisvaatimukset | Suositellut |
| :-----------: | -------------------: | ----------: |
| Arkkitehtuuri |                  x64 |           - |
|   RAM-muisti  |                  8GB |        16GB |
| Tallennustila |                  1GB |         8GB |
|      JRE      |                   17 |          21 |

Sujuvan asetustiedoston muokkauksen varmistamiseksi on hyvä asentaa muokkausohjelma, kuten [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE:n asennus

Kuten nimestä voi päätellä, Minecraft: **"Java"** Edition on kehitetty Javalla, joten sen käyttö edellyttää JRE[^1].

Koska Plazma perustuu Mojang Studiosin viralliseen palvelin alustaan \[^(#user-content-fn-2)][^2], JRE:n on oltava asennettuna Plazman käyttöä varten.

### 1.1 JRE:n läsnäolon tarkistaminen

Jos haluat tarkistaa, onko JRE asennettu järjestelmään, kirjoita ja suorita komento [`cmd /k java --version`](#user-content-fn-4)[^4] Suorita-ikkunassa.

Jos näyttöön tulee seuraavaa, siirry [2. vaiheeseen](setup.md#id-2).

{% code title="Oikea tulos" overflow="wrap" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Jos näyttöön ei tule vastaavaa tai se näyttää seuraavalta, JRE:tä ei ole asennettu tai se on liian vanha, joten sinun on suoritettava [1.2 vaihe](setup.md#id-1.2).

{% code title="JRE ei ole asennettu" overflow="wrap" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE on liian vanha" overflow="wrap" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE:n asennus

Tässä oppaassa käytetään yhtenä JRE:n [versioista](#user-content-fn-5)[^5] Azul Zulua.

Asennuksen jälkeen suorita [1.1 vaihe](setup.md#id-1.1) uudelleen varmistaaksesi, että asennus on suoritettu oikein.

{% tabs %}
{% tab title="Windows" %}

1. Lataa ensin [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) ja asenna **JDK 21** `.msi`-muodossa.
2. Suorita ladattu asennusvelho ja napsauta `Seuraava`.
3. Aktivoi `Aseta JAVA_HOME-muuttuja` vasemman keskellä olevasta valikosta ja napsauta sitten `Seuraava`.
4. Klikkaa `Asenna` JRE:n asentamiseksi ja valitse `Valmis`.
   {% endtab %}

{% tab title="macOS" %}
Lataa [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) ja asenna **JDK 21** `.dmg`-muodossa.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
Lisää ensin Azul Zulun varasto APT:hen suorittamalla seuraava komento terminaalissa.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Asenna sitten JRE suorittamalla seuraava komento terminaalissa.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}
Voit asentaa JRE:n suorittamalla seuraavan komennon.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazman lataaminen

Plazma tarjoaa useita erilaisia suoritustiedostoja.

{% hint style="warning" %}

### Useimmiten käytetään `Reobf Paperclip`-tiedostoa.

Alla olevat tiedot on tarkoitettu kehittäjille tai niille, jotka ovat kiinnostuneita kustakin muodosta.\
Jos olet tavallinen käyttäjä, voit ohittaa [3. vaiheen](setup.md#id-3) ilman ongelmia.
{% lopeta vinkki %}

<details>

<summary>Lisätietoja</summary>

Suoritustiedoston nimi on `plazma-(versionhallinta)-1.20.4-R0.1-SNAPSHOT-(kartoitusmuoto).jar`.

- **Kartoitusmuoto**\
  Kartoitus yhdistää Minecraftin todellisen koodin ja käännetyn koodin eräänlaiseksi kartaksi.
  - **Reobf**\
    Uudelleenkoodaus, jota kutsutaan myös Spigot-kartoitukseksi ja jota käytetään suurimmassa osassa NMS-liitännäisistä.\
    Sitä ei enää käytetä 1.20.5:stä alkaen.
  - **Mojmap**\
    Mojang-kartoitus, joka on Vanilla Minecraftin kartoitus.
- **Versionhallinta**\
  Versionhallinta on palvelimen käynnistämiseen tarvittava kirjasto ja palvelimen tiedostojen korjaaja.
  - **Paperclip**\
    PaperMC-tiimi kehitti Paperin ja muut johdetut alustat, jotka lataavat kirjastoja ja soveltavat korjauksia palvelimelle.
  - **Bundler**\
    Vanilla Minecraftin versionhallinta.

</details>

***

## 3. Käynnistyskomentosarjan luominen

Plazman käynnistämiseksi helposti ja palvelimen automaattiseksi uudelleenkäynnistämiseksi sinun on luotava [käynnistyskomentosarja](#user-content-fn-6).[^6]

Voit luoda käynnistyskomentosarjan [Flags.sh](https://flags.sh) kautta.\
Syötä vain käytettävä muisti \[^(#user-content-fn-8)][^8], ja komento optimoidaan automaattisesti.

Voit ladata käynnistyskomentosarjan napsauttamalla vasemmassa alakulmassa olevaa Lataa-painiketta.\
**Varmista, että ladattu käynnistyskomentosarja vastaa omaa käyttöjärjestelmääsi.**

***

## 4. Tiedostojen järjestely

Siirrä nyt ladattu käynnistyskomentosarja ja Plazma uuteen kansioon.

{% hint style="warning" %}

### Kansion nimen on oltava ilman välilyöntejä ja asetettava englanniksi.

Muuten Plazma tai JRE eivät ehkä toimi oikein.
{% lopeta vinkki %}

Käynnistä nyt käynnistyskomentosarja. Windowsissa <mark style="background-color:orange;">salli palomuurin valintaikkunassa ehdottomasti</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**Salli**</mark><mark style="background-color:orange;">.</mark>

***

## 5. EULA:n hyväksyminen

Kun käynnistyskomentosarja on suoritettu kerran, kansioon luodaan `eula.txt`-tiedosto.

EULA[^9] on sopimus, joka on hyväksyttävä käyttämällä [Mojang Studiosin](#user-content-fn-10)[^10] palveluita.

Jos et hyväksy EULA:a, et voi käynnistää palvelinta, ja jos rikot EULA:a, voit saada rangaistuksia, kuten tilin sulkemisen \[^(#user-content-fn-11)][^11].

Hyväksyäksesi EULA:n muuta `eula.txt`-tiedoston `eula=false` muotoon `eula=true` ja tallenna se.

***

## 6. Ulkoisen yhteyden salliminen (Windows)

Nykyiset käyttöjärjestelmät estävät oletusarvoisesti vaarallisen ulkoisen pääsyn estääkseen sitä palomuurilla ja reitittimellä.

Windowsissa palomuuri on jo sallittu [3. vaiheessa](setup.md#id-3), joten sinun tarvitsee vain tehdä portinohjaus.

{% vinkki tyyli="info" %}

### Tässä oppaassa oletetaan, että käytät Windows-käyttöjärjestelmää ja [**UPnP**](#user-content-fn-12)[^12]-tukea omaavaa reititintä.

Jos reititin ei tue UPnP:tä, sinun on etsittävä tietoa erikseen, koska paneelit vaihtelevat reitittäin.

Voit myös luoda väliaikaisen osoitteen [Ngrok](https://ngrok.com/) kautta.
{% lopeta vinkki %}

{% hint style="warning" %}

### Linuxissa tai macOS:ssa ja muissa (puoli) UNIX-käyttöjärjestelmissä palomuuripalvelujen asetukset vaihtelevat, joten sinun on etsittävä tietoa erikseen.

{% lopeta vinkki %}

### 6.1 Portinohjauksen tarpeen tarkistus

Kirjoita ja suorita seuraava komento Suorita-ikkunassa.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jos tuloste on `True`, voit lopettaa tässä, mutta jos se on `False`, sinun on tehtävä portinohjaus.

### 6.2 Yhteys palvelimeen

{% tabs %}
{% tab title="Ulkoisesti" %}
Jos et tarvitse portinohjausta tai olet jo onnistunut siinä, voit nyt yhdistää palvelimeen.

Palvelimelle yhdistettäessä käytettävä osoite voidaan tarkistaa [täältä](https://ip.pe.kr/).
{% endtab %}

{% tab title="Yritetään UPnP-portinohjausta" %}
Palvelimen kansiossa `purpur.yml`, ota `network.upnp-port-forwarding` käyttöön asettamalla se arvoon `true`.

Tämän jälkeen, jos käynnistät palvelimen uudelleen, Plazma yrittää automaattisesti portinohjausta.

Alla oleva viesti kertoo UPnP:n onnistumisesta ja konsolissa se näkyy muodossa `[UPnP] (viesti)`.

| Viesti                                   | Merkitys                                    |
| ---------------------------------------- | ------------------------------------------- |
| `Portti (portti) avattiin onnistuneesti` | Portinohjaus onnistui.                      |
| `Portti (portti) on jo avoinna`          | Toinen palvelu käyttää jo kyseistä porttia. |
| `Portin (portti) avaaminen epäonnistui`  | Portinohjaus epäonnistui.                   |
| `Palvelu ei ole käytettävissä`           | Reititin ei tue UPnP:tä.                    |

Palvelimen sammuttua Plazma sulkee portin automaattisesti.
{% endtab %}

{% tab title="Tilapäisen osoitteen luominen Ngrokilla" %}
Ngrokin käyttö on hyödyllistä lyhytaikaiseen testaukseen, yhteistyöhön tai pelaamiseen ystävien kanssa.

1. Lataa [Ngrokin verkkosivustolta](https://ngrok.com/download) `Windows (64-bit)` ZIP-tiedosto.
2. Sijoita ladattu Ngrok palvelimen kansioon.
3. Luo [autentikointitunnus](https://dashboard.ngrok.com/get-started/your-authtoken) Ngrokin hallintapaneelissa.
4. Suorita palvelimen kansiosta näytettävä komento `Command Line`.
5. Lisää suoritusskriptin ylimpään kohtaan `start /b ngrok tcp --region jp 25565`, alimpaan kohtaan `taskkill /f /t /im ngrok.exe`.
6. Konsolissa näytettävästä `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` osoitteesta `0.tcp.jp.ngrok.io:12345` on palvelimen osoite.
7. Nyt voit yhdistää ulkoisesti kyseiseen osoitteeseen.
   {% endtab %}

{% tab title="Yhdistäminen paikallisesti" %}
Jos yrität yhdistää palvelimeen paikallisesti, voit käyttää `cmd /k ipconfig` komentoa ja yhdistää `IPv4-osoitteeseen`.

Esimerkiksi, kun komento on suoritettu, ja tuloste on seuraavanlainen,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Yritä yhdistää paikallisesti palvelimeen käyttämällä `192.168.3.7` IPv4-osoitetta.

Jos palvelin ja peli toimivat samalla tietokoneella, voit yhdistää käyttäen `localhost` osoitetta.
{% endtab %}
{% endtabs %}

## 7. Kehitysvaihe

Kun palvelin on onnistuneesti käynnistetty ja toimii oikein, on aika mukauttaa palvelinta.

Katso ohjeet palvelimen mukauttamiseen.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java-suoritusympäristö.

[^2]: Paperin perustana toimiva Plazma perustuu Spigotiin, joka puolestaan perustuu viralliseen palvelinplatformiin.

[^3]: Windows-näppäin + R

[^4]: Linuxissa voit tarkistaa Java-version komennolla `java --version`

[^5]: JRE on yksi avoimen lähdekoodin projekteista, jota on erilaisia versioita, kuten Minecraft palvelinplatformilla.

[^6]: Yleisesti tunnetaan **käynnistäjänä**.

[^7]: Kun "Auto-restart" on aktivoitu, palvelin käynnistyy automaattisesti uudelleen. Voit sulkea palvelimen syöttämällä `Control + C`.

[^8]: Suositellaan välttämään yli puolet järjestelmän resursseista.

    Esimerkiksi, jos järjestelmän kokonaismuistin määrä on 8GB, ei suositella asettamaan yli 4GB.

[^9]: End-User License Agreement, loppukäyttäjän lisenssisopimus. Lisätietoja löytyy [Minecraftin verkkosivuilta](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: Korealaisen lainsäädännön mukaan peliteollisuuden edistämisestä annetun lain 32 §:n 1 momentin 9 kohdan mukaan **Korean Microsoft Corporation** voi nostaa oikeudellisen syytteen.

[^12]: Universal Plug & Play. Plazmaan sisältyvä Purpur kommunikoi automaattisesti reitittimen kanssa tämän tekniikan avulla, joten sinun ei tarvitse tehdä portinohjausta suoraan, koska portti avataan vain silloin, kun palvelin on käynnissä.

[^13]: Jos sinulla ei ole tiliä, rekisteröidy Ngrokkiin Google- tai GitHub-tilin kautta.