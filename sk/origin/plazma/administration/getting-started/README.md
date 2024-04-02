---
description: Zistite, ako vytvoriť server pomocou Plazma.
---

# 👟 Začnite

Pre stabilné používanie Plazma musí systém spĺňať nasledujúce požiadavky.

|                 | Minimálne | Odporúčané |
| :-------------: | --------: | ---------: |
|   Architektúra  |       x64 |          - |
|       RAM       |       8GB |       16GB |
| Úložný priestor |       1GB |        8GB |
|       JRE       |        17 |         21 |

Na pohodlnú úpravu konfiguračných súborov je dobré nainštalovať editor ako [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Inštalácia JRE

Ako názov napovedá, Minecraft: **"Java"** Edition je vyvíjaná v Jave a na jej spustenie je potrebný JRE[^1].

Plazma je oficiálna serverová platforma od Mojang Studios [založená na](#user-content-fn-2)[^2], preto aj pre použitie Plazma je potrebná inštalácia JRE.

### 1.1 Overenie JRE

Ak chcete overiť prítomnosť JRE v systéme, zadajte v [spustiteľnom okne](#user-content-fn-3)[^3] príkaz [`cmd /k java --version`](#user-content-fn-4)[^4] a spustite ho.

Ak sa zobrazí správny výstup, prejdite na [2. krok](setup.md#id-2).

{% code title="Správny výstup" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Ak sa výstup nezhoduje s vyššie uvedeným, alebo sa zobrazí nasledovné, znamená to, že JRE chýba alebo je príliš starý a je potrebné vykonať [1.2 krok](setup.md#id-1.2).

{% code title="JRE nie je nainštalované" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE je príliš staré" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Inštalácia JRE

V tomto sprievodcovi používame Azul Zulu ako [jednu z možností](#user-content-fn-5)[^5] pre JRE.

Po inštalácii skontrolujte, či bola inštalácia úspešne dokončená, opakovane vykonajte [krok 1.1](setup.md#id-1.1).

{% tabs %}

{% tab title="Windows" %}

1. Najprv si stiahnite **JDK 21** vo formáte `.msi` z [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Spustite stiahnuté inštalačné sprievodcu a kliknite na `Ďalej`.
3. **V ľavom strede okna sa zobrazí ponuka, aktivujte `Nastaviť JAVA_HOME premennú`,** potom kliknite na `Ďalej`.
4. Kliknutím na `Inštalovať` dokončite inštaláciu JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) - Stiahnite si **JDK 21** vo formáte `.dmg` a spustite inštalačného sprievodcu na inštaláciu JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Najprv spustite nasledujúci príkaz v termináli na pridanie úložiska Azul Zulu do APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Potom spustite nasledujúci príkaz v termináli na inštaláciu JRE.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Môžete nainštalovať JRE pomocou nasledujúceho príkazu.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Stiahnutie Plazmy

Plazma ponúka rôzne typy spustiteľných súborov.

{% hint style="warning" %}

**Väčšinou sa používa `Reobf Paperclip`.**

Informácie nižšie sú určené pre vývojárov alebo tých, ktorí sa zaujímajú o jednotlivé typy.\
Pre bežného používateľa nie je potrebné sa zaoberať [krokom 3](setup.md#id-3).

{% endhint %}

<details>

<summary>Zobraziť viac</summary>

Názov spustiteľného súboru je stanovený ako `plazma-(verzia manažéra)-1.20.4-R0.1-SNAPSHOT-(forma mapovania).jar`.

- **Forma mapovania**\
  Mapovanie je akýsi sprievodca medzi reálnym kódom Minecraftu a znečisteným kódom.
  - **Reobf**\
    Reobfuskácia, známa aj ako Spigot mapovanie, sa používa vo väčšine NMS pluginov.\
    Od verzie 1.20.5 sa prestane používať.
  - **Mojmap**\
    Mojang mapovanie, vanilla Minecraft mapovanie.
- **Manažér verzií**\
  Manažér verzií je akýsi sprievodca pre beh servera, ktorý je potrebný na spustenie knižníc a aktualizáciu serverových súborov.
  - **Paperclip**\
    Vyvinutý tímom PaperMC pre Paper a ďalšie odvodené platformy, slúži na sťahovanie knižníc a aplikovanie aktualizácií na server.
  - **Bundler**\
    Manažér verzií pre vanilla Minecraft.

</details>

***

## 3. Vytvorenie štartovacieho skriptu

Pre jednoduché spustenie Plazmy a automatické reštartovanie servera musíte vytvoriť [štartovací skript](#user-content-fn-6)[^6].

Pomocou [Flags.sh](https://flags.sh) môžete [vytvoriť štartovací skript.](#user-content-fn-7)[^7]\
Pri zadávaní pamäte pre Plazmu [(^8)](#user-content-fn-8)[^8] sa príkaz automaticky optimalizuje.

Štartovací skript môžete stiahnuť pomocou tlačidla na stiahnutie v ľavom dolnom rohu.\
**Skontrolujte, či stiahnutý štartovací skript zodpovedá vašej operačnej sústave.**

***

## 4. Upratanie súborov

Presuňte stiahnutý štartovací skript a Plazmu do nového priečinka.

{% hint style="warning" %}

**Názov priečinka musí byť bez medzier a musí byť v angličtine.**

Inak by Plazma alebo JRE mohli nesprávne fungovať.

{% endhint %}

Spustite štartovací skript. V prípade Windows musíte pri výbere <mark style="background-color:orange;">okna povolenia firewallu zvoliť možnosť **Povoliť**</mark>.

***

## 5. Súhlas s EULA

Po prvom spustení štartovacieho skriptu sa v priečinku vytvorí `eula.txt`.

EULA[^9] je licenčná zmluva, ktorú musíte akceptovať pri používaní služieb [Mojang Studios](#user-content-fn-10)[^10].

Ak nesúhlasíte s EULA, nemôžete spustiť server a v prípade porušenia EULA môžete čeliť sankciám, ako je uzavretie účtu a podobne [trestom.](#user-content-fn-11)[^11]

Pre súhlas s EULA zmeňte v súbore `eula.txt` `eula=false` na `eula=true` a uložte zmeny.

***

## 6. Povolenie externého prístupu (Windows)

Moderne operačné systémy blokujú externé prístupy pomocou **firewallu** a **routeru**.

V prípade Windows, keďže ste povolili firewall v [kroku 3](setup.md#id-3), stačí nastaviť port forwarding.

{% hint style="info" %}

**Tento sprievodca predpokladá, že používate operačný systém Windows a router, ktorý podporuje [UPnP](#user-content-fn-12)[^12].**

Ak váš router nepodporuje UPnP, musíte si vyhľadať informácie pre jednotlivé panely routerov.

Alternatívne môžete vytvoriť dočasnú adresu pomocou [Ngrok](https://ngrok.com/).
{% endhint %}

{% hint style="warning" %}

**Pre operačné systémy Linux alebo macOS a iné (polo) UNIXové systémy je potrebné vyhľadať informácie o nastavení firewallu pre jednotlivé služby.**

{% endhint %}

### 6.1 Overenie potreby port forwardingu

Zadajte a spustite nasledujúci príkaz do konzoly.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Ak výstup je `True`, nie je potrebné nič ďalej, ak je `False`, je potrebné nastaviť port forwarding.

### 6.2 Pripojenie na server

{% tabs %}

{% tab title="Prístup zvonku" %}

Ak nie je potrebné presmerovanie portov alebo ste už úspešne nastavili presmerovanie portov, môžete sa teraz pripojiť k serveru.

Adresu na pripojenie na server môžete nájsť [tu](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

V súbore `purpur.yml` v priečinku servera, aktivujte `network.upnp-port-forwarding` na hodnotu `true`.

Potom reštartujte server a Plazma automaticky skúsi nastaviť port forwarding.

Úspech UPnP záleží na správe zobrazených správ v konzole, kde sa zobrazí `[UPnP] (správa)`.

| Správa                              | Význam                        |
| ----------------------------------- | ----------------------------- |
| `Úspešne otvorený port (port)`      | Port forwarding úspešný.      |
| `Port (port) je už otvorený`        | Iná služba používa daný port. |
| `Nepodarilo sa otvoriť port (port)` | Port forwarding zlyhal.       |
| `Služba nie je dostupná`            | Router nepodporuje UPnP.      |

Po vypnutí servera Plazma automaticky zatvorí port.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Spôsob pomocou Ngrok je užitočný pre krátkodobé testovanie, spoluprácu alebo hranie s priateľmi.

1. Stiahnite si ZIP súbor pre `Windows (64-bit)` z [Ngrok stránky](https://ngrok.com/download).
2. Vložte stiahnutý Ngrok do priečinka so serverom.
3. Na [Ngrok nástenke](https://dashboard.ngrok.com/get-started/your-authtoken) vygenerujte [autentifikačný token](#user-content-fn-13)[^13].
4. V serverovom priečinku spustite príkazy zobrazené v `Command Line`.
5. Na začiatok spustite príkaz `start /b ngrok tcp --region jp 25565` a na koniec pridajte `taskkill /f /t /im ngrok.exe`.
6. Adresa servera bude `0.tcp.jp.ngrok.io:12345` zobrazená v konzole ako `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`.
7. Teraz môžete pristupovať k adrese zvonka.

{% endtab %}

{% tab title="로컬에서 접속" %}

Ak sa pokúšate pripojiť k serveru z lokálnej siete, môžete sa pripojiť cez `IPv4 adresu`, ktorú nájdete spustením príkazu `cmd /k ipconfig` v okne spustenia.

Napríklad, po vykonaní príkazu sa zobrazí nasledovné:

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Ak sa pokúsite pripojiť cez zobrazenú `192.168.3.7` IPv4 adresu, môžete sa pripojiť k serveru z lokálneho počítača.

Ak server a hra bežia na rovnakom PC, môžete sa pripojiť cez `localhost`.

{% endtab %}
{% endtabs %}

## 7. Stupeň rozvoja

Ak ste úspešne spustili server a funguje správne, je čas prispôsobiť si server podľa vašich potrieb.

Zistite, ako prispôsobiť server pomocou nasledujúceho sprievodcu.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime prostredie, Java Runtime Environment.

[^2]: Paper, na ktorom je založený Plazma, je založený na Spigot a Spigot je založený na oficiálnej platforme servera.

[^3]: Klávesová skratka Windows + R

[^4]: V prípade Linuxu použite v termináli príkaz `java --version`

[^5]: JRE je jedným z open source projektov a existuje viacero verzií ako napríklad Minecraft server platforma.

[^6]: Je všeobecne známe ako **spúšťač**.

[^7]: Ak povolíte „Automatické reštartovanie“, server sa automaticky reštartuje. Môžete ho ukončiť stlačením `Control + C`.

[^8]: Neprekračujte polovicu systému, nie je to odporúčané.

    Napríklad, keď je celková kapacita pamäte systému 8 GB, nie je odporúčané nastaviť ju na viac ako 4 GB.

[^9]: Zmluva o licencii koncového používateľa, End-User License Agreement. Pre viac informácií navštívte [domovskú stránku Minecraftu](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Spoločnosť Microsoft Corporation.

[^11]: V prípade Južnej Kórey je podľa zákona o podpore herného priemyslu § 32 ods. 1 písm. 9 možné podať právne námietky proti spoločnosti **Kórejská spoločnosť Microsoft**.

[^12]: Universal Plug & Play. Purpur zahrnutý v Plazme komunikuje s routrom automaticky cez túto technológiu a otvára porty len v prípade, že je server spustený, preto nie je potrebné manuálne nastavovať port forwarding.

[^13]: Ak nemáte účet, zaregistrujte sa na Ngrok cez účet Google alebo GitHub.
