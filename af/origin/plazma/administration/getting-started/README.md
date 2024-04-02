---
description: Leer hoe om 'n bediener met Plazma te skep.
---

# 👟 Begin

Om Plazma stabiel te gebruik, moet jou stelsel aan die volgende vereistes voldoen.

|             | Minimum | Aanbeveel |
| :---------: | ------: | --------: |
| Argitektuur |     x64 |         - |
|     RAM     |     8GB |      16GB |
|  Stoorplek  |     1GB |       8GB |
|     JRE     |      17 |        21 |

Om die konfigurasie lêer aanpassing vlot te doen, is dit ook goed om 'n redigeerder soos [Visual Studio Code](https://code.visualstudio.com/download) te installeer.

***

## 1. Installeer JRE

Soos die naam aandui, is Minecraft: **"Java"**-uitgawe in Java ontwikkel, en vir uitvoering is JRE[^1] nodig.

Aangesien Plazma op die amptelike bedienerplatform van Mojang Studios gebaseer is, moet JRE ook geïnstalleer word om Plazma te gebruik.

### 1.1 Kontroleer JRE beskikbaarheid

Om te sien of JRE op jou stelsel geïnstalleer is, voer `cmd /k java --version` in die [uitvoeringsvenster](#user-content-fn-3)[^3] in en voer dit uit.

As dit soos volg vertoon, spring na [Stap 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Indien dit nie so vertoon nie, of as dit soos hieronder vertoon, beteken dit dat JRE nie beskikbaar is of te oud is, en die [1.2-stap](setup.md#id-1.2) moet uitgevoer word.

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

### 1.2 Installeer JRE

In hierdie gids word Azul Zulu as een van die [tipes JRE](#user-content-fn-5)[^5] gebruik.

Na installasie, voer [Stap 1.1](setup.md#id-1.1) weer uit om te bevestig dat die installasie korrek voltooi is.

{% tabs %}

{% tab title="Windows" %}

1. Eerstens, laai **JDK 21** in `.msi`-formaat van [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) af.
2. Voer die afgelaaide installasiewizard uit en klik op `Volgende`.
3. Aktiveer `Set JAVA_HOME variable` in die middel van die venster aan die linkerkant en klik dan op `Volgende`.
4. Druk op `Installeer` om die JRE-installasie te voltooi.

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

Voer dan die volgende bevel in die terminaal uit om JRE te installeer.

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

## 2. Plazma aflaai

Plazma bied verskeie uitvoerbaarleêrformate aan.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Die volgende inligting is vir ontwikkelaars of diegene wat belangstel in die eienskappe van elke tipe.\
As jy 'n gewone gebruiker is, kan jy gerus [Stap 3](setup.md#id-3) oorslaan sonder probleme.

{% endhint %}

<details>

<summary>Meer inligting</summary>

Die uitvoerbaarleër se naam word bepaal as `plazma-(weergawe-bestuurder)-1.20.4-R0.1-SNAPSHOT-(karteringsvorm).jar`.

- **Karteringsvorm**\
  Kartering is 'n soort kaart wat die werklike en die vervloeiingskode van Minecraft met mekaar verbind.
  - **Reobf**\
    Reobfuscation, ook bekend as Spigot-kartering, word hoofsaaklik in die meeste NMS-invoegtoepassings gebruik.\
    Vanaf 1.20.5 sal dit nie meer gebruik word nie.
  - **Mojmap**\
    Mojang-kartering, die vanilje-Minecraft-kartering.
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

Jy kan 'n begin skripsie deur [Flags.sh](https://flags.sh) skep.\
Net voer jou [geheue wat gebruik moet word](#user-content-fn-8)[^8] in en die opdrag sal outomaties geoptimaliseer word.

Jy kan die begin skripsie deur die onderste regterkant aflaai-knoppie aflaai.\
**Maak seker dat die afgelaaide begin skripsie ooreenstem met jou bedryfstelsel.**

***

## 4. Lêers opruim

Jy moet nou die afgelaaide begin skripsie en Plazma na 'n nuwe vouer skuif.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Andersins kan Plazma of JRE moontlik nie korrek werk nie.

{% endhint %}

Voer die begin skripsie uit. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA-goedkeuring

Nadat jy die begin skripsie een keer uitgevoer het, word 'n `eula.txt`-lêer in die vouer geskep.

EULA[^9] is 'n gebruikerslisensie-ooreenkoms waarmee jy moet instem om van die dienste van [Mojang Studios](#user-content-fn-10)[^10] gebruik te maak.

As jy nie met die EULA saamstem nie, kan jy nie die bediener begin nie, en as jy die EULA oortree, kan jy gestraf word met die opskorting van jou rekening ens. [sanksies](#user-content-fn-11)[^11].

Om met die EULA saam te stem, verander `eula=false` na `eula=true` in die `eula.txt`-lêer en stoor dit.

***

## 6. Toelaat van eksterne toegang (Windows)

Moderne bedryfstelsels blok standaard eksterne toegang om gevaarlike toegang te voorkom deur die **firewall** en **router**.

Vir Windows, aangesien jy in [Stap 3](setup.md#id-3) die firewall toegelaat het, hoef jy net port forwarding te doen.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| Boodskap                              | Betekenis                                |
| ------------------------------------- | ---------------------------------------- |
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
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Jy kan die bediener bereik deur die `192.168.3.7` adres wat in die IPv4 adres verskyn, te gebruik.

Indien die bediener en die spel op dieselfde rekenaar hardloop, kan jy met `localhost` verbind.

{% endtab %}
{% endtabs %}

## 7. Ontwikkelingsfase

As die bediener suksesvol begin het en behoorlik funksioneer, is dit nou tyd om die bediener aan te pas.

Leer hoe om die bediener aan te pas deur die volgende gids te volg.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java uitvoeringsomgewing.

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
