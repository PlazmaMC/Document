---
description: Selvitä, miten luodaan palvelin Plazma-sovelluksella.
---

# 👟 Aloita

Plazman vakaa käyttö vaatii, että järjestelmä täyttää seuraavat vaatimukset.

|               | Vähimmäisvaatimukset | Suositellut |
| :-----------: | :------------------- | :---------- |
| Arkkitehtuuri | x64                  | -           |
|   RAM-muisti  | 8GB                  | 16GB        |
| Tallennustila | 1GB                  | 8GB         |
|      JRE      | 17                   | 21          |

Sujuvan asetustiedoston muokkauksen varmistamiseksi on hyvä asentaa muokkausohjelma, kuten [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE:n asennus

Kuten nimestä voi päätellä, Minecraft: **"Java"** Edition on kehitetty Javalla, joten sen käyttö edellyttää JRE[^1].

Koska Plazma perustuu Mojang Studiosin viralliseen palvelin alustaan \[^(#user-content-fn-2)][^2], JRE:n on oltava asennettuna Plazman käyttöä varten.

### 1.1 JRE:n läsnäolon tarkistaminen

Jos haluat tarkistaa, onko JRE asennettu järjestelmään, kirjoita ja suorita komento [`cmd /k java --version`](#user-content-fn-4)[^4] Suorita-ikkunassa.

Jos näyttöön tulee seuraavaa, siirry [2. vaiheeseen](setup.md#id-2).

{% code title="Oikea tuloste" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Jos näyttöön ei tule vastaavaa tai se näyttää seuraavalta, JRE:tä ei ole asennettu tai se on liian vanha, joten sinun on suoritettava [1.2 vaihe](setup.md#id-1.2).

{% code title="JRE ei ole asennettu" lineNumbers="true" %}

```log
'java' on sisäinen tai ulkoinen komento, suoritettava ohjelma tai
erätaulukko.
```

{% endcode %}

{% code title="JRE on liian vanha" lineNumbers="true" %}

```log
Tunnistamaton vaihtoehto: --version
Virhe: Java Virtual Machine -ympäristön luominen ei onnistunut.
Virhe: Vakava poikkeus on tapahtunut. Ohjelma sulkeutuu.
```

{% endcode %}

### 1.2 JRE:n asennus

Tässä oppaassa käytetään yhtenä JRE:n [versioista](#user-content-fn-5)[^5] Azul Zulua.

Asennuksen jälkeen suorita [1.1 vaihe](setup.md#id-1.1) uudelleen varmistaaksesi, että asennus on suoritettu oikein.

{% tabs %}

{% tab title="Windows" %}

1. Lataa ensin [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) ja asenna **JDK 21** `.msi`-muodossa.
2. Suorita ladattu asennusvelho ja napsauta `Seuraava`.
3. Aktivoi `Aseta JAVA_HOME-muuttuja` vasemman keskellä olevasta valikosta ja napsauta sitten `Seuraava`.
4. Klikkaa `Asenna` JRE:n asentamiseksi ja valitse `Valmis`.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) asentaa **JDK 21** `.dmg` muodossa olevan asennusvelhon lataamisen jälkeen ja suorittamisen avulla asentaa JRE:n.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Ensinnäkin, suorita seuraava komento terminaalissa lisätäksesi Azul Zulu-varaston APT:hen.

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

Voit asentaa JRE:n seuraavalla komennolla.

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

**Useimmissa tapauksissa käytetään `Reobf Paperclip`-ohjelmaa.**

Alla olevat tiedot on tarkoitettu kehittäjille tai niille, jotka ovat kiinnostuneita kustakin muodosta.\
Jos olet tavallinen käyttäjä, voit ohittaa [3. vaiheen](setup.md#id-3) ilman ongelmia.

{% endhint %}

<details>

<summary>Lisätietoja</summary>

Suoritustiedoston nimi on `plazma-(versionhallinta)-1.20.4-R0.1-SNAPSHOT-(kartoitusmuoto).jar`.

- **Kartoitusmuoto**\
  Kartoitus yhdistää Minecraftin todellisen koodin ja käännetyn koodin eräänlaiseksi kartaksi.
  - **Reobf**\
    Uudelleenhämmennetty (재난독화), tunnetaan myös nimellä Spigot-maalaus ja sitä käytetään suurimmassa osassa NMS-liitännäisiä.\
    Käyttö päättyy versiosta 1.20.5 alkaen.
  - **Mojmap**\
    Mojangin määrittämä, vanilja Minecraft -kartoitus.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 [생성](#user-content-fn-7)[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Voit ladata käynnistyskomentosarjan napsauttamalla vasemmassa alakulmassa olevaa Lataa-painiketta.\
**Varmista, että ladattu käynnistyskomentosarja vastaa omaa käyttöjärjestelmääsi.**

***

## 4. Tiedostojen järjestely

Siirrä nyt ladattu käynnistyskomentosarja ja Plazma uuteen kansioon.

{% hint style="warning" %}

**Kansion nimen on oltava ilman välilyöntejä ja sen on oltava englanniksi.**

Muuten Plazma tai JRE eivät ehkä toimi oikein.

{% endhint %}

Käynnistä nyt käynnistyskomentosarja. Windowsissa, <mark style="background-color:orange;">palomuurin sallimisvalintaikkunassa on aina valittava **Salli**</mark>.

***

## 5. EULA:n hyväksyminen

Kun käynnistyskomentosarja on suoritettu kerran, kansioon luodaan `eula.txt`-tiedosto.

EULA[^9] on sopimus, joka on hyväksyttävä käyttämällä [Mojang Studiosin](#user-content-fn-10)[^10] palveluita.

{% hint style="warning" %}

만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 [제재](#user-content-fn-11)[^11]를 받을 수 있습니다.

{% endhint %}

Hyväksyäksesi EULA:n muuta `eula.txt`-tiedoston `eula=false` muotoon `eula=true` ja tallenna se.

***

## 6. Ulkoisen yhteyden salliminen (Windows)

Nykyiset käyttöjärjestelmät estävät oletusarvoisesti vaarallisen ulkoisen pääsyn estääkseen sitä palomuurilla ja reitittimellä.

Windowsissa palomuuri on jo sallittu [3. vaiheessa](setup.md#id-3), joten sinun tarvitsee vain tehdä portinohjaus.

{% vinkki tyyli="info" %}

**Tässä oppaassa oletetaan, että käytössäsi on Windows-käyttöjärjestelmä ja [UPnP](#user-content-fn-12)[^12] -yhteensopiva reititin.**

Jos reititin ei tue UPnP:tä, sinun on etsittävä tietoa erikseen, koska paneelit vaihtelevat reitittäin.

Voit myös luoda väliaikaisen osoitteen [Ngrok](https://ngrok.com/) kautta.
{% endhint %}

{% hint style="warning" %}

**Linuxissa tai macOS:ssä ja muissa (puoli) UNIX-käyttöjärjestelmissä palomuurin asetukset vaihtelevat palvelun mukaan, joten sinun on etsittävä tietoa itse.**

{% endhint %}

### 6.1 Portinohjauksen tarpeen tarkistus

Kirjoita ja suorita seuraava komento Suorita-ikkunassa.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jos tuloste on `True`, voit lopettaa tässä, mutta jos se on `False`, sinun on tehtävä portinohjaus.

### 6.2 Yhteys palvelimeen

{% tabs %}

{% tab title="Ulkoisesta yhteydestä" %}

Jos et tarvitse portinohjausta tai olet jo onnistunut tekemään sen, voit nyt yhdistää palvelimeen.

Palvelimelle yhdistettäessä käytettävä osoite voidaan tarkistaa [täältä](https://ip.pe.kr/).

{% endtab %}

{% tab title="Yritä UPnP-portinohjausta" %}

Aktivoi `network.upnp-port-forwarding` `true` arvoksi `purpur.yml`-tiedostossa palvelimen kansiosta.

Tämän jälkeen, jos käynnistät palvelimen uudelleen, Plazma yrittää automaattisesti portinohjausta.

Alla oleva viesti kertoo UPnP:n onnistumisesta ja konsolissa se näkyy muodossa `[UPnP] (viesti)`.

| Viesti                                   | Merkitys                                                    |
| ---------------------------------------- | ----------------------------------------------------------- |
| `Portti (portti) avattiin onnistuneesti` | Portinohjaus onnistui.                      |
| `Portti (portti) on jo avoinna`          | Toinen palvelu käyttää jo kyseistä porttia. |
| `Portin (portti) avaaminen epäonnistui`  | Portinohjaus epäonnistui.                   |
| `Palvelu ei ole käytettävissä`           | Reititin ei tue UPnP:tä.    |

Palvelimen sammuttua Plazma sulkee portin automaattisesti.

{% endtab %}

{% tab title="Väliaikaisen osoitteen luominen Ngrokilla" %}

Ngrokia käytetään lyhytaikaisiin testauksiin, yhteisölliseen pelaamiseen tai ystävien kanssa pelaamiseen.

1. Lataa [Ngrokin verkkosivustolta](https://ngrok.com/download) `Windows (64-bit)` ZIP-tiedosto.
2. Sijoita ladattu Ngrok palvelimen kansioon.
3. Luo [autentikointitunnus](https://dashboard.ngrok.com/get-started/your-authtoken) Ngrokin hallintapaneelissa.
4. Suorita palvelimen kansiosta näytettävä komento `Command Line`.
5. Lisää suoritusskriptin ylimpään kohtaan `start /b ngrok tcp --region jp 25565`, alimpaan kohtaan `taskkill /f /t /im ngrok.exe`.
6. Konsolissa näytettävästä `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` osoitteesta `0.tcp.jp.ngrok.io:12345` on palvelimen osoite.
7. Nyt voit yhdistää ulkoisesti kyseiseen osoitteeseen.

{% endtab %}

{% tab title="Paikallinen yhteys" %}

Jos haluat yhdistää paikallisesti palvelimeen, voit käyttää `cmd /k ipconfig` -komentoa suorituskentässä ja yhdistää `IPv4-osoitteeseen` tulosteen perusteella.

Esimerkiksi, kun komento on suoritettu, ja tuloste on seuraavanlainen,

```log
Windows IP konfiguraatio

Ethernet-sovitin Ethernet:

    Yhdistetty DNS-etuliite. . . . :
    IPv4-osoite. . . . . . . . . : 192.168.3.7
    Aliverkon peite . . . . . . . : 255.255.255.0
    Oletusyhdyskäytävä . . . . . . : 192.168.3.1

```

Yritä yhdistää paikallisesti palvelimeen käyttämällä `192.168.3.7` IPv4-osoitetta.

Jos palvelin ja peli toimivat samalla tietokoneella, voit yhdistää käyttäen `localhost` osoitetta.

{% endtab %}
{% endtabs %}

## 7. 발전하기

Kun palvelin on onnistuneesti käynnistetty ja toimii oikein, on aika mukauttaa palvelinta.

Katso ohjeet palvelimen mukauttamiseen.

{% content-ref url="seuraava-askel.md" %}
[seuraava-askel.md](seuraava-askel.md)
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
