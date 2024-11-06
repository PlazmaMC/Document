---
description: Uurige, kuidas luua server Plazma abil.
---

# 👟 Alustamine

Plazma stabiilseks kasutamiseks peab süsteem vastama järgmistele nõuetele.

|               | Miinimum | Soovitatav |
| :-----------: | -------- | ---------- |
|  Arhitektuur  | x64      | -          |
|      RAM      | 8GB      | 16GB       |
| Salvestusruum | 1GB      | 8GB        |
|      JDK      | 17       | 21         |

Sujuva konfiguratsioonifailide muutmise jaoks on soovitatav installida redaktorid nagu [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Õige väljund" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' pole sisemine ega väline käsk, käivitatav programm või
partiifail.
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

1. Esiteks laadige alla [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) **JDK 21** `.msi` vormingus.
2. Käivitage allalaaditud installimisviisard ja klõpsake „Edasi“.
3. **Aktiveerige menüüs „Seadke JAVA_HOME muutuja“ vasakul keskel** ja klõpsake seejärel „Järgmine“.
4. Vajutage nuppu „Install“ JRE installimiseks „Lõpeta“.
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

Seejärel installige JRE järgmise käsu abil terminalis.

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

## 2. Plazma allalaadimine

Plazma pakub mitmesuguseid käivitatavaid faile.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Lisateave</summary>

Käivitatava faili nimi on `plazma-(versioonihaldur)-1.20.4-R0.1-SNAPSHOT-(kaardistamise vorm).jar`.

- **Kaardistamise vorm**\
  Kaardistamine on omamoodi kaart, mis ühendab Minecrafti tegeliku koodi ja obfuskeeritud koodi.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-kaardistatud, see on Vanilla Minecrafti kaardistamine. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Versioonihaldur**\
  Versioonihaldur on serveri käivitamiseks vajalike raamatukogude ja serverifailidega pakkimise serveri käivitaja.
  - **Paperclip**\
    PaperMC meeskond on välja töötanud halduri Paper ja muudele platvormidele, mis laadivad alla raamatukogud ja rakendavad serverisse plaastreid.
  - **Pakendaja**\
    Vanilje Minecrafti versioonihaldur.

</details>

***

## 3. Käivitusskripti loomine

Plazma lihtsaks käivitamiseks ja serveri automaatseks taaskäivitamiseks peate looma [käivitusskripti](#user-content-fn-6).

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Käivitusskripti saate alla laadida all vasakus allnurgas oleva nupu abil.\
**Veenduge, et allalaaditud käivitusskript vastab teie operatsioonisüsteemile.**

***

## 4. Failide korraldamine

Liigutage nüüd allalaaditud käivitusskript ja Plazma uude kausta.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Käivitage nüüd käivitusskript. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA nõustamine

Kui käivitate käivitusskripti, luuakse kausta `eula.txt` fail.

EULA on [Mojang Studios](#user-content-fn-10) teenuste kasutamiseks vajalik litsentsileping, millega tuleb nõustuda.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

EULA nõustumiseks muutke `eula=false` failis `eula=true` ja salvestage see.

***

## 6. Välise ühenduse lubamine (Windows)

Kaasaegsed operatsioonisüsteemid blokeerivad vaikimisi välise juurdepääsu tulemüüri ja ruuteriga.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Kui ruuter ei toeta UPnP-d, siis iga ruuteri paneel on erinev ja peate ise otsima teavet.

Samuti võite kasutada [Ngrok](https://ngrok.com/), et luua ajutine aadress.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Portide edastamise vajaduse kontrollimine

Sisestage ja käivitage järgmine käsk käivitusaknas.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Kui väljund on `True`, võite siin lõpetada, kuid kui see on `False`, peate seadistama portide edastamise.

### 6.2 Ühendus serveriga

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Serveriga ühenduse loomisel kasutatav aadress on võimalik kontrollida [siin](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Seejärel taaskäivitage server, et Plazma prooviks automaatselt portide edastamist.

Allpool on toodud UPnP edukuse kontrollimiseks konsoolile kuvatavad sõnumid, konsoolis kuvatakse `[UPnP] (sõnum)`.

| Sõnum                              | Tähendus                                            |
| ---------------------------------- | --------------------------------------------------- |
| `Port (port) edukalt avatud`       | Portide edastamine õnnestus.        |
| `Port (port) on juba avatud`       | Muu teenus kasutab seda porti juba. |
| `Porti (port) ei õnnestunud avada` | Portide edastamine ebaõnnestus.     |
| `Teenus pole saadaval`             | Ruuter ei toeta UPnP-d.             |

Kui server peatub, sulgeb Plazma automaatselt pordid.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Laadige alla [Ngrok veebisaidilt](https://ngrok.com/download) `Windows (64-bit)` ZIP-fail.
2. Pange allalaaditud Ngrok serveri kausta.
3. Looge [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) jaoks [autentimistoken](#user-content-fn-13).
4. Käivitage serveri kaustas kuvatav käsk käsureal.
5. Lisage käivitusskripti ülaossa `start /b ngrok tcp --region jp 25565`, allosas `taskkill /f /t /im ngrok.exe`.
6. Konsooli ülaosas kuvatud `Edastamine tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` korral on serveri aadressiks `0.tcp.jp.ngrok.io:12345`.
7. Nüüd saate selle aadressi kaudu väljastpoolt ühendust luua.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Näiteks, kui käivitamisel kuvatakse järgmine väljund,

```log
Windows IP konfiguratsioon

Etherneti adapter Ethernet:

    Ühendatud DNS suffiks. . . . :
    IPv4 aadress. . . . . . . . . : 192.168.3.7
    Alamvõrgu mask . . . . . . . : 255.255.255.0
    Vaikimisi värav . . . . . . : 192.168.3.1

```

Siis proovige ühendada kohalikult serveriga, kasutades IPv4 aadressil näidatud `192.168.3.7`.

Kui server ja mäng töötavad samal arvutil, saate ühenduda aadressil `localhost`.
{% endtab %}
{% endtabs %}

## 7. Edasi areneda

Kui server on edukalt käivitatud ja töötab korralikult, on aeg seda kasutajapõhiseks muuta.

Tutvuge allpool oleva juhendiga, kuidas kohandada serverit.

{% content-ref url="järgmine-samm.md" %}
[järgmine-samm.md](järgmine-samm.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Plazma baasil paber kasutab Spigot'i ja Spigot tugineb ametlikule serveri platvormile.

[^3]: Windowsi klahv + R

[^4]: Linuxi puhul käsurealt `java --version`

[^5]: JRE on üks avatud lähtekoodiga projektidest ja sarnaselt Minecrafti serveri platvormiga on mitmeid erinevaid versioone.

[^6]: Tavaliselt tuntakse seda **käivitajana**.

[^7]: Kui aktiveerite „Automaatse taaskäivituse“, taaskäivitatakse server automaatselt. Väljumiseks sisestage `Control + C`.

[^8]: Soovitatav ei ole süsteemi üle poole koormata.

    Näiteks, kui süsteemi kogumälu maht on 8 GB, siis ei soovitata seda seada üle 4 GB.

[^9]: Lõppkasutaja litsentsileping, lõppkasutaja litsentsileping. Lisateabe saamiseks vaadake [Minecrafti kodulehte](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: Kui tegemist on Lõuna-Korea mängutööstuse edendamise seaduse § 32 lõike 1 punktiga 9, siis on võimalik esitada õiguslik kaebus **Korea Microsoft Corporation** vastu.

[^12]: Universaalne pistik & mängi. Plazma'ga lisatud Purpur suhtleb automaatselt ruuteriga selle tehnoloogia abil, avades pordi ainult siis, kui server töötab, nii et pole vaja otse portide edastamist teha.

[^13]: Kui teil pole kontot, registreeruge Ngrokis Google'i või GitHubi konto kaudu.
