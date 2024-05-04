---
description: Uurige, kuidas luua server Plazma abil.
---

# 👟 Alustamine

Plazma stabiilseks kasutamiseks peab süsteem vastama järgmistele nõuetele.

|               | Miinimum | Soovitatav |
| :-----------: | -------: | ---------: |
|  Arhitektuur  |      x64 |          - |
|      RAM      |      8GB |       16GB |
| Salvestusruum |      1GB |        8GB |
|      JRE      |       17 |         21 |

Sujuva konfiguratsioonifailide muutmise jaoks on soovitatav installida redaktorid nagu [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE installimine

Nagu nimest nähtub, on Minecraft: **"Java"** Edition arendatud Java abil ja selle käitamiseks on vajalik JRE[^1].

Kuna Plazma põhineb Mojang Studiosi ametlikul serveriplatvormil [^2], tuleb Plazma kasutamiseks installida ka JRE.

### 1.1 JRE olemasolu kontrollimine

JRE olemasolu süsteemis saab kontrollida, sisestades ja käivitades [käsuaknas](#user-content-fn-3) [`cmd /k java --version`](#user-content-fn-4).

Kui järgmine tulemus ilmub, liikuge [2. etappi](setup.md#id-2).

{% code title="Õige tulemus" overflow="wrap" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Kui sellist tulemust ei kuvata või kuvatakse järgmine, siis JRE puudub või see on liiga vana ning tuleb järgida [1.2 etappi](setup.md#id-1.2).

{% code title="JRE puudub" overflow="wrap" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE on liiga vana" overflow="wrap" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE install

Selles juhendis kasutatakse Azul Zulu JRE ühte tüüpi.

Pärast installimist kontrollige uuesti [1.1 samm](setup.md#id-1.1), et veenduda, kas installimine õnnestus.

{% tabs %}
{% tab title="Windows" %}

1. Esiteks laadige alla [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) **JDK 21** `.msi` vormingus.
2. Käivitage allalaaditud installimisviisard ja klõpsake „Edasi“.
3. **Aktiveerige menüüs „Seadke JAVA_HOME muutuja“ vasakul keskel** ja klõpsake seejärel „Järgmine“.
4. Vajutage nuppu „Install“ JRE installimiseks „Lõpeta“.
   {% endtab %}

{% tab title="macOS" %}
Laadige alla [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) **JDK 21** `.dmg` vormingus installimisviisard ja käivitage JRE installimine.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
Lisage kõigepealt APT-sse Azul Zulu depoo järgmise käsu abil.

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
JRE saate installida järgmise käsu abil.

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

### Enamasti kasutatakse `Reobf Paperclip`.

Allpool olev teave on mõeldud arendajatele või neile, kes on huvitatud erinevate vormide omadustest.\
Tavaline kasutaja võib [3. sammu](setup.md#id-3) vahele jätta ilma probleemideta.
{% endhint %}

<details>

<summary>Lisateave</summary>

Käivitatava faili nimi on `plazma-(versioonihaldur)-1.20.4-R0.1-SNAPSHOT-(kaardistamise vorm).jar`.

- **Kaardistamise vorm**\
  Kaardistamine on omamoodi kaart, mis ühendab Minecrafti tegeliku koodi ja obfuskeeritud koodi.
  - **Reobf**\
    Uuesti obfuskeerimine, tuntud ka kui Spigot kaardistamine, kasutatakse enamikus NMS pistikprogrammides.\
    Alates versioonist 1.20.5 lõpetatakse selle kasutamine.
  - **Mojmap**\
    Mojangi kaardistamine, vanilje Minecrafti kaardistamine.
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

[Flags.sh](https://flags.sh) abil saate luua käivitusskripti.\
Kui sisestate ainult [mälu, mida kasutada](#user-content-fn-8), optimeeritakse käsk automaatselt.

Käivitusskripti saate alla laadida all vasakus allnurgas oleva nupu abil.\
**Veenduge, et allalaaditud käivitusskript vastab teie operatsioonisüsteemile.**

***

## 4. Failide korraldamine

Liigutage nüüd allalaaditud käivitusskript ja Plazma uude kausta.

{% hint style="warning" %}

### Kausta nimi peab olema ilma tühikuteta ja olema inglise keeles.

Muidu Plazma või JRE ei pruugi korralikult töötada.
{% endhint %}

Käivitage nüüd käivitusskript. Windowsi korral peate <mark style="background-color:orange;">tulemüürivaliku aknas kindlasti</mark> valima <mark style="background-color:orange;">**Luba**</mark>.

***

## 5. EULA nõustamine

Kui käivitate käivitusskripti, luuakse kausta `eula.txt` fail.

EULA on [Mojang Studios](#user-content-fn-10) teenuste kasutamiseks vajalik litsentsileping, millega tuleb nõustuda.

Kui te ei nõustu EULA-ga, ei saa serverit käivitada ja EULA rikkumise korral võidakse rakendada [karistusi](#user-content-fn-11).

EULA nõustumiseks muutke `eula=false` failis `eula=true` ja salvestage see.

***

## 6. Välise ühenduse lubamine (Windows)

Kaasaegsed operatsioonisüsteemid blokeerivad vaikimisi välise juurdepääsu tulemüüri ja ruuteriga.

Windowsi korral, kuna tulemüür on lubatud [3. etapis](setup.md#id-3), piisab ainult portide edastamisest.

{% hint style="info" %}

### Käesolevas juhendis eeldatakse, et kasutate Windowsi operatsioonisüsteemi ja [**UPnP**](#user-content-fn-12) võimaldavat ruuterit.

Kui ruuter ei toeta UPnP-d, siis iga ruuteri paneel on erinev ja peate ise otsima teavet.

Samuti võite kasutada [Ngrok](https://ngrok.com/), et luua ajutine aadress.
{% endhint %}

{% hint style="warning" %}

### Linuxi või macOS-i ja muude (pool) UNIX-i süsteemide korral tuleb iga tulemüüri teenuse jaoks seadistusmeetodid erineda, seega peate ise otsima teavet.

{% endhint %}

### 6.1 Portide edastamise vajaduse kontrollimine

Sisestage ja käivitage järgmine käsk käivitusaknas.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Kui väljund on `True`, võite siin lõpetada, kuid kui see on `False`, peate seadistama portide edastamise.

### 6.2 Ühendus serveriga

{% tabs %}
{% tab title="Väliselt ühendamine" %}
Kui portide edastamine pole vajalik või kui olete juba portide edastamise edukalt seadistanud, saate nüüd serveriga ühendust võtta.

Serveriga ühenduse loomisel kasutatav aadress on võimalik kontrollida [siin](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP kaudu portide edastamise katse" %}
Muutke serveri kaustas `purpur.yml` `network.upnp-port-forwarding` väärtus `true`-ks.

Seejärel taaskäivitage server, et Plazma prooviks automaatselt portide edastamist.

Allpool on toodud UPnP edukuse kontrollimiseks konsoolile kuvatavad sõnumid, konsoolis kuvatakse `[UPnP] (sõnum)`.

| Sõnum                              | Tähendus                            |
| ---------------------------------- | ----------------------------------- |
| `Port (port) edukalt avatud`       | Portide edastamine õnnestus.        |
| `Port (port) on juba avatud`       | Muu teenus kasutab seda porti juba. |
| `Porti (port) ei õnnestunud avada` | Portide edastamine ebaõnnestus.     |
| `Teenus pole saadaval`             | Ruuter ei toeta UPnP-d.             |

Kui server peatub, sulgeb Plazma automaatselt pordid.
{% endtab %}

{% tab title="Ngrokiga ajutise aadressi loomine" %}
Ngrok on kasulik lühiajaliste testide, kogukondlike mängude või sõpradega mängimise jaoks.

1. Laadige alla [Ngrok veebisaidilt](https://ngrok.com/download) `Windows (64-bit)` ZIP-fail.
2. Pange allalaaditud Ngrok serveri kausta.
3. Looge [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) jaoks [autentimistoken](#user-content-fn-13).
4. Käivitage serveri kaustas kuvatav käsk käsureal.
5. Lisage käivitusskripti ülaossa `start /b ngrok tcp --region jp 25565`, allosas `taskkill /f /t /im ngrok.exe`.
6. Konsooli ülaosas kuvatud `Edastamine tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` korral on serveri aadressiks `0.tcp.jp.ngrok.io:12345`.
7. Nüüd saate selle aadressi kaudu väljastpoolt ühendust luua.
   {% endtab %}

{% tab title="Lokaalne ühendus" %}
Kui soovite serveriga ühendust luua kohalikult, saate käsurealt käivitada `cmd /k ipconfig` ja kasutada väljundis kuvatud `IPv4 aadressi` ühenduse loomiseks.

Näiteks, kui käivitamisel kuvatakse järgmine väljund,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Siis proovige ühendada kohalikult serveriga, kasutades IPv4 aadressil näidatud `192.168.3.7`.

Kui server ja mäng töötavad samal arvutil, saate ühenduda aadressil `localhost`.
{% endtab %}
{% endtabs %}

## 7. Edasimineku etapp

Kui server on edukalt käivitatud ja töötab korralikult, on aeg seda kasutajapõhiseks muuta.

Tutvuge alloleva juhendiga, kuidas serverit kohandada.

{% content-ref url="customization.md" %}
[kohandamine.md](kohandamine.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java käitamiskeskkond.

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