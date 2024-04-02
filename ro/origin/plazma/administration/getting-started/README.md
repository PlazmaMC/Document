---
description: Aflați cum să creați un server cu Plazma.
---

# 👟 Începeți

Pentru a utiliza Plazma în mod stabil, sistemul trebuie să îndeplinească următoarele cerințe.

|                   | Minim | Recomandat |
| :---------------: | ----: | ---------: |
|    Arhitectură    |   x64 |          - |
|        RAM        |   8GB |       16GB |
| Spațiu de stocare |   1GB |        8GB |
|        JRE        |    17 |         21 |

Pentru a modifica fișierele de configurare fără probleme, este recomandat să instalați un editor cum ar fi [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalarea JRE

După cum sugerează numele, Minecraft: **"Java"** Edition este dezvoltat în Java și necesită JRE[^1] pentru a fi executat.

Deoarece Plazma este bazat pe platforma oficială a serverelor Mojang Studios [^2], trebuie să instalați JRE pentru a utiliza Plazma.

### 1.1 Verificarea existenței JRE

Pentru a verifica dacă JRE este instalat pe sistem, introduceți [`cmd /k java --version`](#user-content-fn-4)[^4] în fereastra de comandă și executați comanda.

Dacă obțineți un rezultat similar, treceți la [Pasul 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Dacă nu obțineți acest rezultat sau obțineți unul similar cu cel de mai jos, înseamnă că JRE lipsește sau este prea vechi și trebuie să urmați [Pasul 1.2](setup.md#id-1.2).

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

### 1.2 Instalarea JRE

În acest ghid, vom utiliza Azul Zulu ca una dintre [variantele](#user-content-fn-5)[^5] de JRE.

După instalare, verificați din nou [Pasul 1.1](setup.md#id-1.1) pentru a confirma instalarea corectă.

{% tabs %}

{% tab title="Windows" %}

1. Descărcați JDK 21 de la [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) în format `.msi`.
2. Executați asistentul de instalare descărcat și faceți clic pe `Next`.
3. După ce activați `Set JAVA_HOME variable` din meniul afișat în mijlocul stânga al ferestrei, faceți clic pe `Next`.
4. Finalizați instalarea JRE făcând clic pe `Install`.

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

Apoi, instalați JRE-ul executând următoarea comandă în terminal.

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

## 2. Descărcarea Plazma

Plazma oferă diverse fișiere de executare.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Informațiile de mai jos sunt pentru dezvoltatori sau cei interesați de caracteristicile fiecărei forme.\
Pentru utilizatorii obișnuiți, nu este o problemă să săriți la [Pasul 3](setup.md#id-3).

{% endhint %}

<details>

<summary>Află mai multe</summary>

Numele fișierului de executare este `plazma-(managerul versiunii)-1.20.4-R0.1-SNAPSHOT-(formă de mapare).jar`.

- **Forma de mapare**\
  Maparea este o hartă care leagă codul real al Minecraft-ului de codul obfuscat.
  - **Reobf**\
    Reobfuscarea, cunoscută și sub numele de mapare Spigot, este folosită în mare parte în pluginurile NMS.\
    Va fi eliminată începând cu versiunea 1.20.5.
  - **Mojmap**\
    Maparea Mojang, este maparea Vanilla Minecraft-ului.
- **Managerul versiunii**\
  Managerul versiunii este un launcher al serverului care furnizează bibliotecile necesare pentru rularea serverului și aplică patch-uri pe fișierele serverului.
  - **Paperclip**\
    Dezvoltat de echipa PaperMC pentru Paper și alte platforme derivate, acesta descarcă bibliotecile și aplică patch-uri pe server.
  - **Bundler**\
    Managerul versiunii Vanilla Minecraft.

</details>

***

## 3. Crearea scriptului de pornire

Pentru a porni Plazma simplu și pentru a reporni automat serverul, trebuie să creați un [script de pornire](#user-content-fn-6)[^6].

Puteți genera scriptul de pornire folosind [Flags.sh](https://flags.sh).\
Introduceți doar memoria pe care doriți să o alocați pentru Plazma și comanda va fi optimizată automat.

Puteți descărca scriptul de pornire făcând clic pe butonul de descărcare din partea de jos stânga.\
**Asigurați-vă că scriptul de pornire descărcat este compatibil cu sistemul de operare al dvs.**

***

## 4. Curățarea fișierelor

Mută scriptul de pornire descărcat și Plazma într-un folder nou.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Altfel, Plazma sau JRE ar putea să nu funcționeze corect.

{% endhint %}

Executați scriptul de pornire. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. Acordarea EULA

După ce rulați scriptul de pornire o dată, un fișier `eula.txt` va fi creat în folder.

EULA[^9] este un acord de licență pe care trebuie să-l acceptați pentru a utiliza serviciile [Mojang Studios](#user-content-fn-10)[^10].

Dacă nu acceptați EULA, nu veți putea porni serverul și veți fi supus sancțiunilor, cum ar fi suspendarea contului, dacă încălcați EULA.

Pentru a accepta EULA, modificați `eula=false` în fișierul `eula.txt` în `eula=true` și salvați modificările.

***

## 6. Permiterea accesului extern (Windows)

Sistemele de operare moderne blochează accesul extern pentru a preveni accesul neautorizat prin intermediul **firewall-ului** și **router-ului**.

În cazul Windows-ului, deoarece ați permis deja în [Pasul 3](setup.md#id-3), trebuie doar să faceți port forwarding.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Dacă routerul dvs. nu suportă UPnP, va trebui să căutați informații specifice pentru fiecare router în parte.

De asemenea, puteți utiliza [Ngrok](https://ngrok.com/) pentru a genera o adresă temporară.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Verificarea necesității de port forwarding

Introduceți comanda următoare în fereastra de comandă și executați-o.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Dacă obțineți `True`, nu mai este necesar să faceți nimic, dar dacă obțineți `False`, va trebui să setați port forwarding-ul.

### 6.2 Conectarea la server

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Puteți găsi adresa folosită pentru a accesa serverul [aici](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Apoi, dacă reporniți serverul, Plazma va încerca automat să redirecționeze porturile.

Mai jos este un mesaj de succes sau eșec UPnP afișat în consolă, care va fi afișat ca `[UPnP] (mesaj)`.

| Mesaj                                       | Semnificație                            |
| ------------------------------------------- | --------------------------------------- |
| `Portul (port)` a fost deschis cu succes    | Redirecționare porturi reușită.         |
| `Portul (port) este deja deschis`           | Alt serviciu folosește deja acest port. |
| `Nu s-a reușit deschiderea portului (port)` | Redirecționarea porturilor a eșuat.     |
| `Serviciul nu este disponibil`              | Routerul nu suportă UPnP.               |

Când serverul este oprit, Plazma va închide automat portul.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Descărcați fișierul ZIP `Windows (64-bit)` de pe [site-ul Ngrok](https://ngrok.com/download).
2. Puneți fișierul Ngrok descărcat în dosarul serverului.
3. Generați un token de autentificare pe [Tabloul de bord Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Executați comanda afișată în linia de comandă din dosarul serverului.
5. Adăugați `start /b ngrok tcp --region jp 25565` în partea de sus a scriptului de pornire și `taskkill /f /t /im ngrok.exe` în partea de jos.
6. Adresa serverului va fi `0.tcp.jp.ngrok.io:12345` conform afișării de sus `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`.
7. Acum puteți accesa serverul de la distanță folosind această adresă.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

De exemplu, atunci când rulați comanda și obțineți următorul rezultat,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Puteți accesa serverul local folosind adresa IPv4 `192.168.3.7` afișată aici.

Dacă serverul și jocul rulează pe același PC, puteți accesa folosind `localhost`.

{% endtab %}
{% endtabs %}

## 7. Faza de dezvoltare

Dacă serverul a fost inițiat cu succes și funcționează corect, acum este momentul să îl personalizați.

Consultați ghidul pentru personalizarea serverului.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Mediu de executare Java, Java Runtime Environment.

[^2]: Paper, pe care se bazează Plazma, este bazat pe Spigot și Spigot se bazează pe platforma oficială a serverului.

[^3]: Tastele Windows + R

[^4]: Pentru Linux, rulați `java --version` în terminal

[^5]: JRE este un proiect open source și există diverse versiuni, asemănătoare cu platforma serverului Minecraft.

[^6]: Este cunoscut în mod obișnuit ca **launcher**.

[^7]: Activarea opțiunii "Repornire automată" va duce la repornirea automată a serverului. Puteți opri serverul tastând `Control + C`.

[^8]: Nu se recomandă alocarea a mai mult de jumătate din resursele sistemului.

    De exemplu, pentru un total de 8GB memorie RAM, nu este recomandat să alocați mai mult de 4GB.

[^9]: Acordul de licență pentru utilizatorul final, End-User License Agreement. Pentru detalii, consultați [site-ul Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Corporația Microsoft.

[^11]: În conformitate cu articolul 32 alineatul (1) punctul 9 din Legea privind promovarea industriei de jocuri video din Coreea, puteți acționa în justiție **Korea Microsoft Corporation**.

[^12]: Universal Plug & Play. Purpurul inclus în Plazma utilizează această tehnologie pentru a comunica automat cu routerul și a deschide porturile doar atunci când serverul rulează, eliminând necesitatea redirecționării manuale a porturilor.

[^13]: Dacă nu aveți un cont, vă puteți înregistra pe Ngrok folosind un cont Google sau GitHub.
