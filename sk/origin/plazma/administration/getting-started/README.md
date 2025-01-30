---
description: Zistite, ako vytvoriť server pomocou Plazma.
---

# 👟 Začnite

Pre stabilné používanie Plazma musí systém spĺňať nasledujúce požiadavky.

|                 | Minimálne | Odporúčané |
| :-------------: | --------- | ---------- |
|   Architektúra  | x64       | -          |
|       RAM       | 8GB       | 16GB       |
| Úložný priestor | 1GB       | 8GB        |
|       JDK       | 17        | 21         |

Na pohodlnú úpravu konfiguračných súborov je dobré nainštalovať editor ako [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Správny výstup" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' nie je interný ani externý príkaz, spustiteľný program alebo
súbor s príkazmi.
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

1. Najprv si stiahnite **JDK 21** vo formáte `.msi` z [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Spustite stiahnuté inštalačné sprievodcu a kliknite na `Ďalej`.
3. **V ľavom strede okna sa zobrazí ponuka, aktivujte `Nastaviť JAVA_HOME premennú`,** potom kliknite na `Ďalej`.
4. Kliknutím na `Inštalovať` dokončite inštaláciu JRE.
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

Potom spustite nasledujúci príkaz v termináli na inštaláciu JRE.

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

## 2. Stiahnutie Plazmy

Plazma ponúka rôzne typy spustiteľných súborov.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Zobraziť viac</summary>

Názov spustiteľného súboru je stanovený ako `plazma-(verzia manažéra)-1.20.4-R0.1-SNAPSHOT-(forma mapovania).jar`.

- **Forma mapovania**\
  Mapovanie je akýsi sprievodca medzi reálnym kódom Minecraftu a znečisteným kódom.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, mapovanie pre Vanilla Minecraft. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Štartovací skript môžete stiahnuť pomocou tlačidla na stiahnutie v ľavom dolnom rohu.\
**Skontrolujte, či stiahnutý štartovací skript zodpovedá vašej operačnej sústave.**

***

## 4. Upratanie súborov

Presuňte stiahnutý štartovací skript a Plazmu do nového priečinka.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Spustite štartovací skript. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Súhlas s EULA

Po prvom spustení štartovacieho skriptu sa v priečinku vytvorí `eula.txt`.

EULA[^9] je licenčná zmluva, ktorú musíte akceptovať pri používaní služieb [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Pre súhlas s EULA zmeňte v súbore `eula.txt` `eula=false` na `eula=true` a uložte zmeny.

***

## 6. Povolenie externého prístupu (Windows)

Moderne operačné systémy blokujú externé prístupy pomocou **firewallu** a **routeru**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Ak váš router nepodporuje UPnP, musíte si vyhľadať informácie pre jednotlivé panely routerov.

Alternatívne môžete vytvoriť dočasnú adresu pomocou [Ngrok](https://ngrok.com/).
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Overenie potreby port forwardingu

Zadajte a spustite nasledujúci príkaz do konzoly.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Ak výstup je `True`, nie je potrebné nič ďalej, ak je `False`, je potrebné nastaviť port forwarding.

### 6.2 Pripojenie na server

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Adresu na pripojenie na server môžete nájsť [tu](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Potom reštartujte server a Plazma automaticky skúsi nastaviť port forwarding.

Úspech UPnP záleží na správe zobrazených správ v konzole, kde sa zobrazí `[UPnP] (správa)`.

| Správa                              | Význam                                        |
| ----------------------------------- | --------------------------------------------- |
| `Úspešne otvorený port (port)`      | Port forwarding úspešný.      |
| `Port (port) je už otvorený`        | Iná služba používa daný port. |
| `Nepodarilo sa otvoriť port (port)` | Port forwarding zlyhal.       |
| `Služba nie je dostupná`            | Router nepodporuje UPnP.      |

Po vypnutí servera Plazma automaticky zatvorí port.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Stiahnite si ZIP súbor pre `Windows (64-bit)` z [Ngrok stránky](https://ngrok.com/download).
2. Vložte stiahnutý Ngrok do priečinka so serverom.
3. Na [Ngrok nástenke](https://dashboard.ngrok.com/get-started/your-authtoken) vygenerujte [autentifikačný token](#user-content-fn-13)[^13].
4. V serverovom priečinku spustite príkazy zobrazené v `Command Line`.
5. Na začiatok spustite príkaz `start /b ngrok tcp --region jp 25565` a na koniec pridajte `taskkill /f /t /im ngrok.exe`.
6. Adresa servera bude `0.tcp.jp.ngrok.io:12345` zobrazená v konzole ako `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`.
7. Teraz môžete pristupovať k adrese zvonka.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Napríklad, po vykonaní príkazu sa zobrazí nasledovné:

```log
Windows IP Configuration

Ethernet adapter Ethernet:

    Sufix pre DNS spojenie. . . . . . . :
    IPv4 adresa. . . . . . . . . : 192.168.3.7
    Maskovacia podsieť . . . . . . . : 255.255.255.0
    Predvolená brána . . . . . . : 192.168.3.1

```

Ak sa pokúsite pripojiť cez zobrazenú `192.168.3.7` IPv4 adresu, môžete sa pripojiť k serveru z lokálneho počítača.

Ak server a hra bežia na rovnakom PC, môžete sa pripojiť cez `localhost`.
{% endtab %}
{% endtabs %}

## 7. Rastúci

Ak ste úspešne spustili server a funguje správne, je čas prispôsobiť si server podľa vašich potrieb.

Zistite, ako prispôsobiť server pomocou nasledujúceho návodu.

{% content-ref url="dalsi-krok.md" %}
[dalsi-krok.md](dalsi-krok.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
