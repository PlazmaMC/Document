---
description: Leer hoe om 'n bediener met Plazma te skep.
---

# 👟 Begin

Om Plazma stabiel te gebruik, moet jou stelsel aan die volgende vereistes voldoen.

|             | Minimum | Aanbeveel |
| :---------: | :------ | :-------- |
| Argitektuur | x64     | -         |
|     RAM     | 8GB     | 16GB      |
|  Stoorplek  | 1GB     | 8GB       |
|     JRE     | 17      | 21        |

Om die konfigurasie lêer aanpassing vlot te doen, is dit ook goed om 'n redigeerder soos [Visual Studio Code](https://code.visualstudio.com/download) te installeer.

***

## 1. Installeer JRE

Soos die naam aandui, is Minecraft: **"Java"**-uitgawe in Java ontwikkel, en vir uitvoering is JRE[^1] nodig.

Aangesien Plazma op die amptelike bedienerplatform van Mojang Studios gebaseer is, moet JRE ook geïnstalleer word om Plazma te gebruik.

### 1.1 Kontroleer JRE beskikbaarheid

Om te sien of JRE op jou stelsel geïnstalleer is, voer `cmd /k java --version` in die [uitvoeringsvenster](#user-content-fn-3)[^3] in en voer dit uit.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Korrek afdruk" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime-omgewing Zulu21.32+17-CA (bou 21.0.2+13-LTS)
OpenJDK 64-biet Bediener-VM Zulu21.32+17-CA (bou 21.0.2+13-LTS, gemengde modus, deling)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE is nie geïnstalleer nie" lineNumbers="true" %}

```log
'java' is nie 'n interne of eksterne bevel, 'n uitvoerbare program, of
'n bat-lêer nie.
```

{% endcode %}

{% code title="JRE is te oud" lineNumbers="true" %}

```log
Onherkenbare opsie: --weergawe
Fout: Kon nie die Java Virtuele Masjien skep nie.
Fout: 'n fatale uitsondering het plaasgevind. Program sal afsluit.
```

{% endcode %}

### 1.2 Installeer JRE

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. Eerstens, laai **JDK 21** in `.msi`-formaat van [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) af.
2. Voer die afgelaaide installasiewizard uit en klik op `Volgende`.
3. Aktiveer `Set JAVA_HOME variable` in die middel van die venster aan die linkerkant en klik dan op `Volgende`.
4. Druk op `Installeer` om die JRE-installasie te voltooi.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) van **JDK 21** in `.dmg` formaat aflaai en uitvoer die installasie-wizard om JRE te installeer.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Voeg eers die Azul Zulu-opberging by APT deur die volgende bevel in die terminaal uit te voer.

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

JRE kan geïnstalleer word deur die volgende bevel in te voer.

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

**Meeste gevalle gebruik `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Meer inligting</summary>

Die uitvoerbaarleër se naam word bepaal as `plazma-(weergawe-bestuurder)-1.20.4-R0.1-SNAPSHOT-(karteringsvorm).jar`.

- **Karteringsvorm**\
  Kartering is 'n soort kaart wat die werklike en die vervloeiingskode van Minecraft met mekaar verbind.
  - **Herhers**\
    Herherskik (재난독화), Spigot kartering genoem en word hoofsaaklik in die meeste NMS invoegtoepassings gebruik.\
    Dit sal vanaf 1.20.5 nie meer gebruik word nie.
  - **Mojmap**\
    Mojang-gekarteer, 'n vanilla Minecraft kartering.
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

[Vlae.sh](https://flags.sh) kan 'n begin skrip genereer deur net die geheue wat vir Plazma gebruik moet word in te voer. Die bevel word outomaties geoptimaliseer.

Jy kan die begin skripsie deur die onderste regterkant aflaai-knoppie aflaai.\
**Maak seker dat die afgelaaide begin skripsie ooreenstem met jou bedryfstelsel.**

***

## 4. Lêers opruim

Jy moet nou die afgelaaide begin skripsie en Plazma na 'n nuwe vouer skuif.

{% hint style="warning" %}

**Die vouernaam moet geen spasies hê en in Engels wees nie.**

Andersins kan Plazma of JRE moontlik nie korrek werk nie.

{% endhint %}

Voer die begin skripsie uit. Vir Windows, moet jy by die <mark style="background-color:orange;">firewall-toestemming kiesvenster, beslis **Toelaat** kies</mark>.

***

## 5. EULA-goedkeuring

Nadat jy die begin skripsie een keer uitgevoer het, word 'n `eula.txt`-lêer in die vouer geskep.

EULA[^9] is 'n gebruikerslisensie-ooreenkoms waarmee jy moet instem om van die dienste van [Mojang Studios](#user-content-fn-10)[^10] gebruik te maak.

{% hint style="warning" %}

Indien daar nie saamgestem word nie, kan die bediener nie begin nie, en as die EULA oortree word, kan daar sanksies soos rekeningopskorting weens oortredings wees.

{% endhint %}

Om met die EULA saam te stem, verander `eula=false` na `eula=true` in die `eula.txt`-lêer en stoor dit.

***

## 6. Toelaat van eksterne toegang (Windows)

Moderne bedryfstelsels blok standaard eksterne toegang om gevaarlike toegang te voorkom deur die **firewall** en **router**.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

As jou router nie UPnP ondersteun nie, moet jy na die spesifieke paneel van jou router soek, aangesien dit vir elke router verskil.

Jy kan ook [Ngrok](https://ngrok.com/) gebruik om 'n tydelike adres te skep.
{% endhint %}

{% hint style="warning" %}

**Vir Linux of macOS ens. (semi) UNIX-stelsels, moet jy vir elke firewalldiens afsonderlik navorsing doen aangesien die instellingsmetodes verskil.**

{% endhint %}

### 6.1 Kontroleer of port forwarding nodig is

Voer die volgende in die uitvoeringsvenster in en voer dit uit.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

As die uitset `True` is, is jy klaar, maar as dit `False` is, moet jy port forwarding instel.

### 6.2 Koppel aan die bediener

{% tabs %}

{% tab title="Eksterne toegang" %}

As daar geen port forwarding nodig is nie, of as jy reeds suksesvol port forwarding gedoen het, kan jy nou met die bediener verbind.

Die adres wat gebruik word om met die bediener te verbind, kan hier bevestig word: [hier](https://ip.pe.kr/)

{% endtab %}

{% tab title="UPnP vir Port Forwarding-poging" %}

In die `purpur.yml` van die bediener se lêer, aktiveer `network.upnp-port-forwarding` na `true`.

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

{% tab title="Ngrok temporary address creation" %}

Die metode met Ngrok is nuttig vir korttermyn toetse, deelname of speel saam met vriende.

1. Laai die `Windows (64-bit)` ZIP lêer vanaf die [Ngrok webwerf](https://ngrok.com/download) af.
2. Plaas die afgelaaide Ngrok in die bediener se gids.
3. Skep 'n outorisasie token by die [Ngrok dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Voer die opdrag wat in die `Command Line` in die bediener se gids verskyn, uit.
5. Voeg `start /b ngrok tcp --region jp 25565` by die boonste gedeelte van die uitvoeringskript en `taskkill /f /t /im ngrok.exe` by die onderste gedeelte by.
6. Die adres van die bediener sal wees `0.tcp.jp.ngrok.io:12345` soos aangedui deur die `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` boodskap op die konsole.
7. Jy kan nou van buite die bediener bereik deur die genoemde adres.

{% endtab %}

{% tab title="Verbinding vanaf plaaslike masjien" %}

As jy vanaf jou plaaslike masjien na die bediener wil verbind, kan jy die `IPv4 adres` wat uitgevoer word deur `cmd /k ipconfig` in die uitvoer venster, gebruik om te verbind.

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

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% inhoudsverwysing url="next-step.md" %}
[next-step.md](next-step.md)
{% endinhoudsverwysing %}

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
