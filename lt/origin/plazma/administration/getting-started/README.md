---
description: Sužinokite, kaip sukurti serverį naudojant Plazma.
---

# 👟 Pradėti

Norėdami stabiliai naudoti Plazmą, sistema turi atitikti šiuos reikalavimus.

|                 | Minimalūs | Rekomenduojami |
| :-------------: | :-------- | :------------- |
|   Architektūra  | x64       | -              |
|       RAM       | 8 GB      | 16 GB          |
| Saugojimo erdvė | 1 GB      | 8 GB           |
|       JRE       | 17        | 21             |

Norint lengvai redaguoti konfigūracijos failus, gerai būtų įdiegti redaktorių, pvz., [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE diegimas

Kaip matyti iš pavadinimo, „Minecraft: **"Java"** Edition“ yra sukurtas naudojant Java, todėl paleidimui reikalingas JRE[^1].

Plazma yra paremta Mojang Studios oficialia serverio platforma, todėl norint naudoti Plazmą, taip pat reikia įdiegti JRE.

### 1.1 Patikrinkite, ar yra įdiegta JRE

Norėdami patikrinti, ar sistemoje yra įdiegta JRE, eikite į [vykdomąjį langą](#user-content-fn-3) ir įveskite [`cmd /k java --version`](#user-content-fn-4), tada paleiskite komandą.

Jei atspausdinsite kaip nurodyta, pereikite prie [2 žingsnio](#id-2).

{% code title="Teisingas išvestis" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Jei nespausdinsite kaip anksčiau arba jei spausdinsite kaip žemiau, reiškia, kad neturite arba per sena JRE, todėl turite atlikti [1.2 žingsnį](#id-1.2).

{% code title="JRE nėra įdiegtas" lineNumbers="true" %}

```log
'java' nėra vidinis arba išorinis komanda, vykdoma programa arba
vykdomasis failas.
```

{% endcode %}

{% code title="JRE yra per senas" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE diegimas

Šiame vadove naudojamas Azul Zulu kaip vieną iš JRE [tipų](#user-content-fn-5)[^5].

Baigus diegimą, patikrinkite, ar įdiegimas buvo atliktas teisingai, vėl atlikdami [1.1 žingsnį](#id-1.1).

{% tabs %}

{% tab title="Windows" %}

1. Pirmiausia, iš [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) parsisiųskite **JDK 21** kaip `.msi` failą.
2. Paleiskite atsisiųstą diegimo vediklį ir spustelėkite `Next`.
3. **Kairėje viduryje esančiame meniu pasirinkite `Set JAVA_HOME variable`,** tada spustelėkite `Next`.
4. Paspauskite `Install`, kad baigtumėte JRE diegimą.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) **JDK 21** įdiekite JRE, atsisiųsdami `.dmg` diegimo vedlį iš **Azul Zulu** svetainės ir vykdant jį.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Pirmiausia, įvykdykite šią komandą terminale, kad pridėtumėte **Azul Zulu** saugyklą į **APT**.

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

Įveskite šią komandą, kad galėtumėte įdiegti JRE.

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

**Daugumoje atvejų naudokite `Reobf Paperclip`.**

Šis turinys skirtas plėtototojams arba tiems, kurie nori sužinoti apie įvairius formų ypatumus.\
Jei esate paprastas vartotojas, galite praleisti [3 žingsnį](#id-3) be jokių problemų.

{% endhint %}

<details>

<summary>Skaityti daugiau</summary>

Vykdomojo failo pavadinimas yra `plazma-(versijos tvarkyklė)-1.20.4-R0.1-SNAPSHOT-(atvaizdavimo būdas).jar`.

- **Atvaizdavimo būdas**\
  Atvaizdavimas yra kaip žemėlapis, jungiantis „Minecraft“ realųjį kodą su užšifruotu kodu.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot mape, taip pat vadinama dauguma NMS įskiepių.\
    1.20.5bus nutrauktas naudojimas.
  - **Mojmap**\
    Mojang sudaryta žemėlapių sistema, skirta „Vanilla“ „Minecraft“ žemėlapiams.
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

[Flags.sh](https://flags.sh)galite [sukurti](#user-content-fn-7)[^7]pradinį scenarijų. Įvedę tik [naudojamą atmintį](#user-content-fn-8)[^8]Plazmoje, komandos automatiškai optimizuojamos.

Galite atsisiųsti paleidimo scenarijų spustelėdami apačioje esantį mygtuką.\
**Patikrinkite, ar atsisiųstas paleidimo scenarijus atitinka jūsų operacinę sistemą.**

***

## 4. Failų tvarkymas

Dabar perkelskite atsisiųstą paleidimo scenarijų ir Plazmą į naują aplanką.

{% hint style="įspėjimas" %}

**Aplanko pavadinimas turi būti be tarpų ir nurodytas anglų kalba.**

Kitu atveju Plazma ar JRE gali neteisingai veikti.

{% endhint %}

Dabar paleiskite paleidimo scenarijų. Windows atveju, <mark style="background-color:orange;">pasirinkite **Leisti** būtinai iš **Ugniasienės leidimų langas**</mark>.

***

## 5. EULA sutikimas

Paleidus scenarijų, aplankyme bus sukurtas `eula.txt` failas.

EULA[^9] yra sutartis, su kuria privalote sutikti naudodamiesi [Mojang Studios](#user-content-fn-10)[^10] paslaugomis.

{% hint style="įspėjimas" %}

Jei nesutinkate, negalėsite paleisti serverio ir galite patirti [sankcijas](#user-content-fn-11)[^11], įskaitant paskyros sustabdymą už EULA pažeidimą.

{% endhint %}

Norėdami sutikti su EULA, `eula=false` faile pakeiskite į `eula=true` ir išsaugokite.

***

## 6. Išorinės prieigos leidimas (Windows)

Šiuolaikinės operacinės sistemos numatytai blokuoja pavojingus išorinius prisijungimus ugniasienės ir maršrutizatoriaus lygmeniu.

Windows atveju, ugniasienė yra leista [3 žingsnyje](#id-3), todėl tereikia atlikti portų peradresavimą.

{% hint style="info" %}

**Šiame vadove numatyta, kad naudojamas Windows operacinė sistema ir maršrutizatorius, palaikantis [UPnP](#user-content-fn-12)[^12].**

Jei maršrutizatorius nepalaiko UPnP, reikės paieškoti informacijos apie konkrečią maršrutizatoriaus sąsają.

Taip pat galite naudoti [Ngrok](https://ngrok.com/) sukurti laikiną adresą.
{% endhint %}

{% hint style="įspėjimas" %}

**Linux arba macOS ir kitose (pusiau) UNIX operacinėse sistemose reikia nustatyti ugniasienės paslaugas, todėl turite patys ieškoti informacijos.**

{% endhint %}

### 6.1 Patikrinkite, ar reikalingas portų peradresavimas

Įveskite ir paleiskite šią komandą vykdymo lange.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jei išvestis yra `True`, galite sustoti, jei `False`, turėsite nustatyti portų peradresavimą.

### 6.2 Prisijungimas prie serverio

{% tabs %}

{% tab title="Išorinis prisijungimas" %}

Jei nereikia portų peradresavimo arba jau sėkmingai atlikote portų peradresavimą, dabar galite prisijungti prie serverio.

Prisijungimo adresas galite patikrinti [čia](https://ip.pe.kr/).

{% endtab %}

{% tab title="Bandykite naudoti UPnP portų peradresavimą" %}

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

[^13]: Jei neturite paskyros, užsiregistruokite į Ngrok naudodami „Google“ arba „GitHub“ paskyrą.