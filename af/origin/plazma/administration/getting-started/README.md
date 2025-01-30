---
description: Leer hoe om 'n bediener met Plazma te skep.
---

# 👟 Begin

Om Plazma stabiel te gebruik, moet jou stelsel aan die volgende vereistes voldoen.

|             | Minimum | Aanbeveel |
| :---------: | ------- | --------- |
| Argitektuur | x64     | -         |
|     RAM     | 8GB     | 16GB      |
|  Stoorplek  | 1GB     | 8GB       |
|     JDK     | 17      | 21        |

Om die konfigurasie lêer aanpassing vlot te doen, is dit ook goed om 'n redigeerder soos [Visual Studio Code](https://code.visualstudio.com/download) te installeer.

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Korrek afdruk" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime-omgewing Zulu21.32+17-CA (bou 21.0.2+13-LTS)
OpenJDK 64-biet Bediener-VM Zulu21.32+17-CA (bou 21.0.2+13-LTS, gemengde modus, deling)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' is nie 'n interne of eksterne bevel, 'n uitvoerbare program, of
'n bat-lêer nie.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Onherkenbare opsie: --weergawe
Fout: Kon nie die Java Virtuele Masjien skep nie.
Fout: 'n fatale uitsondering het plaasgevind. Program sal afsluit.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Eerstens, laai **JDK 21** in `.msi`-formaat van [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) af.
2. Voer die afgelaaide installasiewizard uit en klik op `Volgende`.
3. Aktiveer `Set JAVA_HOME variable` in die middel van die venster aan die linkerkant en klik dan op `Volgende`.
4. Druk op `Installeer` om die JRE-installasie te voltooi.
   {% endtab %}

{% tab title="macOS" %}
[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

```bash
sudo apt installeer gnupg ca-certificates curl --geen-aanbevolen-installatie --geen-aanbevolen-suggesties -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [onderteken-deur=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stabiel hoof" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Voer dan die volgende bevel in die terminaal uit om JRE te installeer.

```bash
sudo apt installeer --geen-aanbevolen-installatie --geen-aanbevolen-suggesties -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}
다음 명령어를 입력하여 JDK를 설치할 수 있습니다.

```bash
sudo dnf installeer -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf installeer -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma aflaai

Plazma bied verskeie uitvoerbaarleêrformate aan.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Meer inligting</summary>

Die uitvoerbaarleër se naam word bepaal as `plazma-(weergawe-bestuurder)-1.20.4-R0.1-SNAPSHOT-(karteringsvorm).jar`.

- **Karteringsvorm**\
  Kartering is 'n soort kaart wat die werklike en die vervloeiingskode van Minecraft met mekaar verbind.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-gekarteer, 'n vanilla Minecraft kartering. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Weergawe-bestuurder**\
  Die weergawe-bestuurder is 'n lêerbestuurder wat nodig is vir die bedryf van die bediener en wat die biblioteke en lêers op die bediener toepas.
  - **Paperclip**\
    Ontwikkel deur die PaperMC-span vir die bestuur van Paper en ander afgeleide platforms, laai biblioteke af en pas dit toe op die bediener.
  - **Bundler**\
    Die vanilje-Minecraft-weergawe-bestuurder.

</details>

***

## 3. Begin skripsie skep

Om Plazma maklik te begin en die bediener outomaties te herlaai, moet jy 'n [begin skripsie](#user-content-fn-6)[^6] skep.

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Jy kan die begin skripsie deur die onderste regterkant aflaai-knoppie aflaai.\
**Maak seker dat die afgelaaide begin skripsie ooreenstem met jou bedryfstelsel.**

***

## 4. Lêers opruim

Jy moet nou die afgelaaide begin skripsie en Plazma na 'n nuwe vouer skuif.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Voer die begin skripsie uit. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA-goedkeuring

Nadat jy die begin skripsie een keer uitgevoer het, word 'n `eula.txt`-lêer in die vouer geskep.

EULA[^9] is 'n gebruikerslisensie-ooreenkoms waarmee jy moet instem om van die dienste van [Mojang Studios](#user-content-fn-10)[^10] gebruik te maak.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Om met die EULA saam te stem, verander `eula=false` na `eula=true` in die `eula.txt`-lêer en stoor dit.

***

## 6. Toelaat van eksterne toegang (Windows)

Moderne bedryfstelsels blok standaard eksterne toegang om gevaarlike toegang te voorkom deur die **firewall** en **router**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

As jou router nie UPnP ondersteun nie, moet jy na die spesifieke paneel van jou router soek, aangesien dit vir elke router verskil.

Jy kan ook [Ngrok](https://ngrok.com/) gebruik om 'n tydelike adres te skep.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Kontroleer of port forwarding nodig is

Voer die volgende in die uitvoeringsvenster in en voer dit uit.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

As die uitset `True` is, is jy klaar, maar as dit `False` is, moet jy port forwarding instel.

### 6.2 Koppel aan die bediener

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Die adres wat gebruik word om met die bediener te verbind, kan hier bevestig word: [hier](https://ip.pe.kr/)
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Daarna, as jy die bediener herlaai, sal Plazma outomaties poort deurstuur probeer.

Hierdie is die sukses van UPnP volgens die boodskap wat op die konsole verskyn, en op die konsole sal dit soos `[UPnP] (boodskap)` wees.

| Boodskap                              | Betekenis                                                |
| ------------------------------------- | -------------------------------------------------------- |
| `Poort suksesvol oopgemaak (poort)`   | Poortdeurstuur suksesvol.                |
| `Poort (poort) is reeds oop`          | Ander diens gebruik reeds daardie poort. |
| `Misluk om poort oop te maak (poort)` | Poortdeurstuur misluk.                   |
| `Diens is nie beskikbaar nie`         | Router ondersteun nie UPnP nie.          |

As die bediener afgesluit word, sal Plazma outomaties die poort sluit.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Laai die `Windows (64-bit)` ZIP lêer vanaf die [Ngrok webwerf](https://ngrok.com/download) af.
2. Plaas die afgelaaide Ngrok in die bediener se gids.
3. Skep 'n outorisasie token by die [Ngrok dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Voer die opdrag wat in die `Command Line` in die bediener se gids verskyn, uit.
5. Voeg `start /b ngrok tcp --region jp 25565` by die boonste gedeelte van die uitvoeringskript en `taskkill /f /t /im ngrok.exe` by die onderste gedeelte by.
6. Die adres van die bediener sal wees `0.tcp.jp.ngrok.io:12345` soos aangedui deur die `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` boodskap op die konsole.
7. Jy kan nou van buite die bediener bereik deur die genoemde adres.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Byvoorbeeld, as die volgende na die uitvoering van die opdrag verskyn:

```log
Windows IP konfigurasie

Ethernet-adapter Ethernet:

    Gekoppelde DNS-suffix. . . . :
    IPv4-adres. . . . . . . . . : 192.168.3.7
    Subnet-masker . . . . . . . : 255.255.255.0
    Standaard gateway . . . . . . : 192.168.3.1

```

Jy kan die bediener bereik deur die `192.168.3.7` adres wat in die IPv4 adres verskyn, te gebruik.

Indien die bediener en die spel op dieselfde rekenaar hardloop, kan jy met `localhost` verbind.
{% endtab %}
{% endtabs %}

## 7. Groei

As die bediener suksesvol begin het en behoorlik funksioneer, is dit nou tyd om die bediener aan te pas.

Leer hoe om die bediener aan te pas deur die volgende handleiding te volg.

{% inhoudsverwysing url="next-step.md" %}
[next-step.md](next-step.md)
{% endinhoudsverwysing %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Plazma se basis Papier is gegrond op Spigot, wat op sy beurt op die amptelike bediener platform gebaseer is.

[^3]: Windows sleutel + R

[^4]: Vir Linux, hardloop `java --version` in die terminal

[^5]: JRE is een van die oopbronprojekte en het verskeie variasies soos die Minecraft bediener platform.

[^6]: Dikwels bekend as 'n **aandrywer**.

[^7]: Deur 'Auto-herlaai' te aktiveer, sal die bediener outomaties herlaai. Jy kan die bediener stop deur `Control + C` in te tik.

[^8]: Dit word nie aanbeveel om meer as die helfte van die stelsel te gebruik nie.

    Byvoorbeeld, as die totale geheuekapasiteit van die stelsel 8GB is, word dit nie aanbeveel om meer as 4GB in te stel nie.

[^9]: Eindgebruikerlisensie-ooreenkoms, finale gebruikerslisensie-ooreenkoms. Vir meer inligting, besoek die [Minecraft webwerf](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: Volgens artikel 32(1)(9) van die Wet op die Bevordering van die Speelbedryf in Suid-Korea, kan regsstappe teen **Koreaanse Microsoft Corporation** geneem word.

[^12]: Universal Plug & Play. Purpur wat ingesluit is in Plazma kommunikeer outomaties met die router deur hierdie tegnologie om slegs die poort te open wanneer die bediener in werking is, wat beteken dat jy nie self poort deurstuur hoef te doen nie.

[^13]: Indien daar geen rekening is nie, kan jy by Ngrok registreer deur jou Google- of GitHub-rekening te gebruik.
