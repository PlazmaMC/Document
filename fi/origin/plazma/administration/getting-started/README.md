---
description: Selvitä, miten luodaan palvelin Plazma-sovelluksella.
---

# 👟 Aloita

Plazman vakaa käyttö vaatii, että järjestelmä täyttää seuraavat vaatimukset.

|               | Vähimmäisvaatimukset | Suositellut |
| :-----------: | -------------------- | ----------- |
| Arkkitehtuuri | x64                  | -           |
|   RAM-muisti  | 8GB                  | 16GB        |
| Tallennustila | 1GB                  | 8GB         |
|      JDK      | 17                   | 21          |

Sujuvan asetustiedoston muokkauksen varmistamiseksi on hyvä asentaa muokkausohjelma, kuten [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Oikea tuloste" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' on sisäinen tai ulkoinen komento, suoritettava ohjelma tai
erätaulukko.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Tunnistamaton vaihtoehto: --version
Virhe: Java Virtual Machine -ympäristön luominen ei onnistunut.
Virhe: Vakava poikkeus on tapahtunut. Ohjelma sulkeutuu.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Lataa ensin [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) ja asenna **JDK 21** `.msi`-muodossa.
2. Suorita ladattu asennusvelho ja napsauta `Seuraava`.
3. Aktivoi `Aseta JAVA_HOME-muuttuja` vasemman keskellä olevasta valikosta ja napsauta sitten `Seuraava`.
4. Klikkaa `Asenna` JRE:n asentamiseksi ja valitse `Valmis`.
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

Asenna sitten JRE suorittamalla seuraava komento terminaalissa.

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

## 2. Plazman lataaminen

Plazma tarjoaa useita erilaisia suoritustiedostoja.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Lisätietoja</summary>

Suoritustiedoston nimi on `plazma-(versionhallinta)-1.20.4-R0.1-SNAPSHOT-(kartoitusmuoto).jar`.

- **Kartoitusmuoto**\
  Kartoitus yhdistää Minecraftin todellisen koodin ja käännetyn koodin eräänlaiseksi kartaksi.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojangin määrittämä, vanilja Minecraft -kartoitus. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Voit ladata käynnistyskomentosarjan napsauttamalla vasemmassa alakulmassa olevaa Lataa-painiketta.\
**Varmista, että ladattu käynnistyskomentosarja vastaa omaa käyttöjärjestelmääsi.**

***

## 4. Tiedostojen järjestely

Siirrä nyt ladattu käynnistyskomentosarja ja Plazma uuteen kansioon.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Käynnistä nyt käynnistyskomentosarja. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA:n hyväksyminen

Kun käynnistyskomentosarja on suoritettu kerran, kansioon luodaan `eula.txt`-tiedosto.

EULA[^9] on sopimus, joka on hyväksyttävä käyttämällä [Mojang Studiosin](#user-content-fn-10)[^10] palveluita.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Hyväksyäksesi EULA:n muuta `eula.txt`-tiedoston `eula=false` muotoon `eula=true` ja tallenna se.

***

## 6. Ulkoisen yhteyden salliminen (Windows)

Nykyiset käyttöjärjestelmät estävät oletusarvoisesti vaarallisen ulkoisen pääsyn estääkseen sitä palomuurilla ja reitittimellä.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Jos reititin ei tue UPnP:tä, sinun on etsittävä tietoa erikseen, koska paneelit vaihtelevat reitittäin.

Voit myös luoda väliaikaisen osoitteen [Ngrok](https://ngrok.com/) kautta.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Portinohjauksen tarpeen tarkistus

Kirjoita ja suorita seuraava komento Suorita-ikkunassa.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jos tuloste on `True`, voit lopettaa tässä, mutta jos se on `False`, sinun on tehtävä portinohjaus.

### 6.2 Yhteys palvelimeen

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Palvelimelle yhdistettäessä käytettävä osoite voidaan tarkistaa [täältä](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

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

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Lataa [Ngrokin verkkosivustolta](https://ngrok.com/download) `Windows (64-bit)` ZIP-tiedosto.
2. Sijoita ladattu Ngrok palvelimen kansioon.
3. Luo [autentikointitunnus](https://dashboard.ngrok.com/get-started/your-authtoken) Ngrokin hallintapaneelissa.
4. Suorita palvelimen kansiosta näytettävä komento `Command Line`.
5. Lisää suoritusskriptin ylimpään kohtaan `start /b ngrok tcp --region jp 25565`, alimpaan kohtaan `taskkill /f /t /im ngrok.exe`.
6. Konsolissa näytettävästä `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` osoitteesta `0.tcp.jp.ngrok.io:12345` on palvelimen osoite.
7. Nyt voit yhdistää ulkoisesti kyseiseen osoitteeseen.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

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

## 7. Kehittyä

Kun palvelin on onnistuneesti käynnistetty ja toimii oikein, on aika mukauttaa palvelinta.

Katso alla olevasta oppaasta, miten voit mukauttaa palvelinta.

{% content-ref url="seuraava-askel.md" %}
[seuraava-askel.md](seuraava-askel.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
