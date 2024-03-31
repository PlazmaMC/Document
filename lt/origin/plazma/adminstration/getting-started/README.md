---
description: Sužinokite, kaip sukurti serverį naudojant Plazma.
---

# 👟 Pradėti

Norėdami stabiliai naudoti Plazmą, sistema turi atitikti šiuos reikalavimus.

|                 | Minimalūs | Rekomenduojami |
| :-------------: | --------: | -------------: |
|   Architektūra  |       x64 |              - |
|       RAM       |      8 GB |          16 GB |
| Saugojimo erdvė |      1 GB |           8 GB |
|       JRE       |        17 |             21 |

Norint lengvai redaguoti konfigūracijos failus, gerai būtų įdiegti redaktorių, pvz., [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE diegimas

Kaip matyti iš pavadinimo, „Minecraft: **"Java"** Edition“ yra sukurtas naudojant Java, todėl paleidimui reikalingas JRE[^1].

Plazma yra paremta Mojang Studios oficialia serverio platforma, todėl norint naudoti Plazmą, taip pat reikia įdiegti JRE.

### 1.1 Patikrinkite, ar yra įdiegta JRE

Norėdami patikrinti, ar sistemoje yra įdiegta JRE, eikite į [vykdomąjį langą](#user-content-fn-3) ir įveskite [`cmd /k java --version`](#user-content-fn-4), tada paleiskite komandą.

Jei matote tokius rezultatus, eikite prie [2 žingsnio](setup.md#id-2).

{% code title="Teisingas rezultatas" overflow="wrap" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Jei nerodoma taip, arba matote šį rezultatą, reiškia, kad JRE nėra arba yra per senas, todėl turite vykdyti [1.2 žingsnį](setup.md#id-1.2).

{% code title="JRE neįdiegta" overflow="wrap" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE yra per senas" overflow="wrap" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE diegimas

Šiame vadove naudojamas Azul Zulu kaip [vienas iš variantų](#user-content-fn-5)[^5] JRE.

Įdiegus, patikrinkite, ar diegimas buvo sėkmingas, pakartodami [1.1 žingsnį](setup.md#id-1.1).

{% tabs %}
{% tab title="Windows" %}

1. Pirmiausia, iš [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) parsisiųskite **JDK 21** kaip `.msi` failą.
2. Paleiskite atsisiųstą diegimo vediklį ir spustelėkite `Next`.
3. **Kairėje viduryje esančiame meniu pasirinkite `Set JAVA_HOME variable`,** tada spustelėkite `Next`.
4. Paspauskite `Install`, kad baigtumėte JRE diegimą.
   {% endtab %}

{% tab title="macOS" %}
Iš [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) parsisiųskite **JDK 21** kaip `.dmg` failą ir įdiekite JRE.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
Pirma, terminale įvykdykite šią komandą, kad pridėtumėte Azul Zulu saugyklą į APT.

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
Galite įdiegti JRE naudodami šią komandą.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma atsisiuntimas

Plazma siūlo įvairių vykdomųjų failų variantų.

{% hint style="įspėjimas" %}

### Daugumai atvejų naudojamas `Reobf Paperclip`.

Ši informacija skirta kūrėjams arba tiems, kurie domisi kiekvienu variantu.\
Paprastiems vartotojams galima tiesiog praleisti ir pereiti prie [3 žingsnio](setup.md#id-3).
{% endhint %}

<details>

<summary>Skaityti daugiau</summary>

Vykdomojo failo pavadinimas yra `plazma-(versijos tvarkyklė)-1.20.4-R0.1-SNAPSHOT-(atvaizdavimo būdas).jar`.

- **Atvaizdavimo būdas**\
  Atvaizdavimas yra kaip žemėlapis, jungiantis „Minecraft“ realųjį kodą su užšifruotu kodu.
  - **Reobf**\
    Reobfuscation, taip pat žinomas kaip Spigot atvaizdavimas, daugiausia naudojamas NMS įskiepiuose.\
    Nuo 1.20.5 palaikymas bus nutrauktas.
  - **Mojmap**\
    Mojang atvaizdavimas, tai „vanilinis Minecraft“ atvaizdavimas.
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

Per [Flags.sh](https://flags.sh) galite [sukurti paleidimo scenarijų](#user-content-fn-7)[^7].\
Įvedus tik norimą atmintį Plazmoje, komanda automatiškai optimizuojama.

Galite atsisiųsti paleidimo scenarijų spustelėdami apačioje esantį mygtuką.\
**Patikrinkite, ar atsisiųstas paleidimo scenarijus atitinka jūsų operacinę sistemą.**

***

## 4. Failų tvarkymas

Dabar perkelskite atsisiųstą paleidimo scenarijų ir Plazmą į naują aplanką.

{% hint style="įspėjimas" %}

### Aplankas turi būti be tarpų ir sukonfigūruotas anglų kalba.

Kitu atveju Plazma ar JRE gali neteisingai veikti.
{% endhint %}

Dabar paleiskite paleidimo scenarijų. Windows atveju, <mark style="background-color:orange;">užtikrinkite, kad</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**leidžiama**</mark><mark style="background-color:orange;"> būtų pasirinkta</mark> atsiradus ugniasienės leidimo langui.

***

## 5. EULA sutikimas

Paleidus scenarijų, aplankyme bus sukurtas `eula.txt` failas.

EULA[^9] yra sutartis, su kuria privalote sutikti naudodamiesi [Mojang Studios](#user-content-fn-10)[^10] paslaugomis.

Nesutikus su EULA, negalėsite paleisti serverio, o pažeidus EULA gali būti taikomos [sankcijos](#user-content-fn-11)[^11], pvz., paskyros sustabdymas.

Norėdami sutikti su EULA, `eula=false` faile pakeiskite į `eula=true` ir išsaugokite.

***

## 6. Išorinės prieigos leidimas (Windows)

Šiuolaikinės operacinės sistemos numatytai blokuoja pavojingus išorinius prisijungimus ugniasienės ir maršrutizatoriaus lygmeniu.

Windows atveju, užteks tik atlikti [3 žingsnį](setup.md#id-3) ir nustatyti portų peradresavimą.

{% hint style="info" %}

### Šiame vadove daroma prielaida, kad naudojate Windows operacinę sistemą ir [**UPnP**](#user-content-fn-12)[^12] galintį maršrutizatorių.

Jei maršrutizatorius nepalaiko UPnP, reikės paieškoti informacijos apie konkrečią maršrutizatoriaus sąsają.

Taip pat galite naudoti [Ngrok](https://ngrok.com/) sukurti laikiną adresą.
{% endhint %}

{% hint style="įspėjimas" %}

### Linux arba macOS ir kitų (pseudonimo) UNIX operacinių sistemų atveju, nesaugumo tarnybos turi skirtingus nustatymus, todėl reikės ieškoti informacijos patiems.

{% endhint %}

### 6.1 Patikrinkite, ar reikalingas portų peradresavimas

Įveskite ir paleiskite šią komandą vykdymo lange.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jei išvestis yra `True`, galite sustoti, jei `False`, turėsite nustatyti portų peradresavimą.

### 6.2 Prisijungimas prie serverio

{% tabs %}
{% tab title="Iš išorės" %}
Jei portų peradresavimas nereikalingas arba jį jau sėkmingai atlikote, dabar galite prisijungti prie serverio.

Prisijungimo adresas galite patikrinti [čia](https://ip.pe.kr/).
{% endtab %}

{% tab title="Bandyti su UPnP portų peradresavimu" %}
Paleidus serverio aplankale `purpur.yml`, įjunkite `network.upnp-port-forwarding` parametrą į `true`.

Tada paleiskite serverį ir Plazma automatiškai bandys nustatyti portų peradresavimą.

Sėkmės UPnP atveju bus matoma pagal išvestį konsolėje, kurioje bus rodomas `[UPnP] (pranešimas)`.

| Pranešimas                                | Reikšmė                                  |
| ----------------------------------------- | ---------------------------------------- |
| `Sėkmingai atidarytas prievadas (portas)` | Portų peradresavimas sėkmingas.          |
| `Prievadas (portas) jau yra atviras`      | Kitas paslaugas jau naudoja šį prievadą. |
| `Nepavyko atidaryti prievado (portas)`    | Portų peradresavimas nepavyko.           |
| `Paslauga nepasiekiama`                   | Maršrutizatorius nepalaiko UPnP.         |

Uždarius serverį, Plazma automatiškai uždarys prievadą.
{% endtab %}

{% tab title="Ngrok naudojant laikiną adresą" %}
Ngrok metodas yra naudingas trumpalaikiams bandymams, bendradarbiavimui ar žaidimui su draugais.

1. Iš [Ngrok svetainės](https://ngrok.com/download) atsisiųskite `Windows (64-bit)` ZIP failą.
2. Įdėkite atsisiųstą Ngrok į serverio aplanką.
3. [Ngrok skydelis](https://dashboard.ngrok.com/get-started/your-authtoken) leidžia [sukurti autentifikacijos raktą](#user-content-fn-13)[^13].
4. Serverio aplanke įvykdykite komandą, kurią rodo `Command Line` skyriuje.
5. Paleidimo scenarijaus viršuje pridėkite `start /b ngrok tcp --region jp 25565`, o apačioje - `taskkill /f /t /im ngrok.exe`.
6. `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` yra rodomas konsolės viršuje, čia `0.tcp.jp.ngrok.io:12345` tampa serverio adresu.
7. Dabar galite prisijungti iš išorės naudodami šį adresą.
   {% endtab %}

{% tab title="Prisijungimas iš vietinės mašinos" %}
Jei norite prisijungti prie serverio iš vietinės mašinos, vykdymo lange paleiskite `cmd /k ipconfig` ir naudokite `IPv4 adresas`, kuris bus rodomas kaip prisijungimo adresas.

Pavyzdžiui, jei po komandos vykdymo atrodo taip,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Bandydami prisijungti prie serverio iš vietinės mašinos, naudokite `192.168.3.7`, kuris yra IPv4 adrese, kad prisijungtumėte.

Jei serveris ir žaidimas vyksta toje pačioje PC, galite prisijungti naudodami `localhost`.
{% endtab %}
{% endtabs %}

## 7. Evoliucijos etapas

Kai serveris sėkmingai paleistas ir veikia teisingai, dabar laikas pritaikyti serverį pagal savo poreikius.

Sužinokite, kaip pritaikyti serverį, sekdami šį vadovą.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java vykdymo aplinka, Java vykdymo aplinka.

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

[^13]: 계정이 없는 경우 Google 또는 GitHub 계정을 통해 Ngrok에 가입합니다.
