---
description: Sužinokite, kaip sukurti serverį naudojant Plazma.
---

# 👟 Pradėti

Norėdami stabiliai naudoti Plazmą, sistema turi atitikti šiuos reikalavimus.

|                 | Minimalūs | Rekomenduojami |
| :-------------: | --------- | -------------- |
|   Architektūra  | x64       | -              |
|       RAM       | 8 GB      | 16 GB          |
| Saugojimo erdvė | 1 GB      | 8 GB           |
|       JDK       | 17        | 21             |

Norint lengvai redaguoti konfigūracijos failus, gerai būtų įdiegti redaktorių, pvz., [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Teisingas išvestis" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' nėra vidinis arba išorinis komanda, vykdoma programa arba
vykdomasis failas.
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

1. Pirmiausia, iš [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) parsisiųskite **JDK 21** kaip `.msi` failą.
2. Paleiskite atsisiųstą diegimo vediklį ir spustelėkite `Next`.
3. **Kairėje viduryje esančiame meniu pasirinkite `Set JAVA_HOME variable`,** tada spustelėkite `Next`.
4. Paspauskite `Install`, kad baigtumėte JRE diegimą.
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

Tada terminale įvykdykite šią komandą, kad įdiegtumėte JRE.

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

## 2. Plazma atsisiuntimas

Plazma siūlo įvairių vykdomųjų failų variantų.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Skaityti daugiau</summary>

Vykdomojo failo pavadinimas yra `plazma-(versijos tvarkyklė)-1.20.4-R0.1-SNAPSHOT-(atvaizdavimo būdas).jar`.

- **Atvaizdavimo būdas**\
  Atvaizdavimas yra kaip žemėlapis, jungiantis „Minecraft“ realųjį kodą su užšifruotu kodu.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang sudaryta žemėlapių sistema, skirta „Vanilla“ „Minecraft“ žemėlapiams. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Versijos tvarkyklė**\
  Versijos tvarkyklė yra būtina serverio paleidimui, taip pat ji yra serverio leistuvas, kuris leidžia atsisiųsti bibliotekas ir taikyti serverio failus.
  - **Paperclip**\
    PaperMC komandos sukurtas tvarkyklė, skirta „Paper“ ir kitų atitinkamų platformų, atsisiuntimui ir serverio atnaujinimui.
  - **Bundler**\
    „Vanilinis Minecraft“ versijos tvarkyklė.

</details>

***

## 3. Paleidimo scenarijaus kūrimas

Norėdami lengvai paleisti Plazmą ir automatiškai perkrauti serverį, turite sukurti [paleidimo scenarijų](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Galite atsisiųsti paleidimo scenarijų spustelėdami apačioje esantį mygtuką.\
**Patikrinkite, ar atsisiųstas paleidimo scenarijus atitinka jūsų operacinę sistemą.**

***

## 4. Failų tvarkymas

Dabar perkelskite atsisiųstą paleidimo scenarijų ir Plazmą į naują aplanką.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Dabar paleiskite paleidimo scenarijų. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA sutikimas

Paleidus scenarijų, aplankyme bus sukurtas `eula.txt` failas.

EULA[^9] yra sutartis, su kuria privalote sutikti naudodamiesi [Mojang Studios](#user-content-fn-10)[^10] paslaugomis.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Norėdami sutikti su EULA, `eula=false` faile pakeiskite į `eula=true` ir išsaugokite.

***

## 6. Išorinės prieigos leidimas (Windows)

Šiuolaikinės operacinės sistemos numatytai blokuoja pavojingus išorinius prisijungimus ugniasienės ir maršrutizatoriaus lygmeniu.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Jei maršrutizatorius nepalaiko UPnP, reikės paieškoti informacijos apie konkrečią maršrutizatoriaus sąsają.

Taip pat galite naudoti [Ngrok](https://ngrok.com/) sukurti laikiną adresą.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Patikrinkite, ar reikalingas portų peradresavimas

Įveskite ir paleiskite šią komandą vykdymo lange.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jei išvestis yra `True`, galite sustoti, jei `False`, turėsite nustatyti portų peradresavimą.

### 6.2 Prisijungimas prie serverio

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Prisijungimo adresas galite patikrinti [čia](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Tada paleiskite serverį ir Plazma automatiškai bandys nustatyti portų peradresavimą.

Sėkmės UPnP atveju bus matoma pagal išvestį konsolėje, kurioje bus rodomas `[UPnP] (pranešimas)`.

| Pranešimas                                | Reikšmė                                                  |
| ----------------------------------------- | -------------------------------------------------------- |
| `Sėkmingai atidarytas prievadas (portas)` | Portų peradresavimas sėkmingas.          |
| `Prievadas (portas) jau yra atviras`      | Kitas paslaugas jau naudoja šį prievadą. |
| `Nepavyko atidaryti prievado (portas)`    | Portų peradresavimas nepavyko.           |
| `Paslauga nepasiekiama`                   | Maršrutizatorius nepalaiko UPnP.         |

Uždarius serverį, Plazma automatiškai uždarys prievadą.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Iš [Ngrok svetainės](https://ngrok.com/download) atsisiųskite `Windows (64-bit)` ZIP failą.
2. Įdėkite atsisiųstą Ngrok į serverio aplanką.
3. [Ngrok skydelis](https://dashboard.ngrok.com/get-started/your-authtoken) leidžia [sukurti autentifikacijos raktą](#user-content-fn-13)[^13].
4. Serverio aplanke įvykdykite komandą, kurią rodo `Command Line` skyriuje.
5. Paleidimo scenarijaus viršuje pridėkite `start /b ngrok tcp --region jp 25565`, o apačioje - `taskkill /f /t /im ngrok.exe`.
6. `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` yra rodomas konsolės viršuje, čia `0.tcp.jp.ngrok.io:12345` tampa serverio adresu.
7. Dabar galite prisijungti iš išorės naudodami šį adresą.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Pavyzdžiui, jei po komandos vykdymo atrodo taip,

```log
Windows IP konfigūracija

Ethernet adapter Ethernet:

    Prijungtas DNS sufiksas. . . . :
    IPv4 adresas. . . . . . . . : 192.168.3.7
    Podtinklo kaukė . . . . . . . : 255.255.255.0
    Numatytasis šaltinis . . . . . . : 192.168.3.1

```

Bandydami prisijungti prie serverio iš vietinės mašinos, naudokite `192.168.3.7`, kuris yra IPv4 adrese, kad prisijungtumėte.

Jei serveris ir žaidimas vyksta toje pačioje PC, galite prisijungti naudodami `localhost`.
{% endtab %}
{% endtabs %}

## 7. Tobulėkite

Kai serveris sėkmingai paleistas ir veikia teisingai, dabar laikas pritaikyti serverį pagal savo poreikius.

Sužinokite, kaip pritaikyti serverį, peržiūrėdami žemiau pateiktą vadovą.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Paper, kuris yra pagrįstas Plazma, remiasi Spigot ir yra oficialus serverio platformos pagrindas.

[^3]: Windows klavišai + R

[^4]: Linux atveju terminale naudokite `java --version`

[^5]: JRE yra vienas iš atviro kodo projektų, kaip ir Minecraft serverio platforma, kuri turi daugybę variantų.

[^6]: Įprastai žinomas kaip **vykdyklė**.

[^7]: Įjungus „Automatinį paleidimą“, serveris automatiškai perkraunamas. Norėdami sustabdyti, įveskite `Control + C`.

[^8]: Nerekomenduojama viršyti daugiau nei pusės sistemos resursų.

    Pavyzdžiui, jei viso sistemos atminties talpa yra 8GB, nerekomenduojama nustatyti daugiau kaip 4GB.

[^9]: Galutinio vartotojo licencijavimo sutartis, End-User License Agreement. Daugiau informacijos rasite [Minecraft svetainėje](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: Pagal Korėjos žaidimų pramonės skatinimo įstatymo 32 straipsnio 1 dalies 9 punktą, **Korea Microsoft Corporation** gali teikti teisminę ieškinį.

[^12]: Universalus įtaisų jungimas ir grojimas, Universal Plug & Play. Purpur, įtrauktas į Plazma, automatiškai bendrauja su maršrutizatoriumi per šią technologiją, todėl nereikia tiesiogiai konfigūruoti portų persiuntimo, kai serveris veikia.

[^13]: Jei neturite paskyros, užsiregistruokite į Ngrok naudodami „Google“ arba „GitHub“ paskyrą.
