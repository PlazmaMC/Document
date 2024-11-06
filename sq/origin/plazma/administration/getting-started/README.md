---
description: Mësoni si të krijoni një server me Plazma.
---

# 👟 Filloni

Për të përdorur Plazma-n në mënyrë stabile, sistemi duhet të plotësojë këto kërkesa:

|                     | Minimumi | Rekomanduar |
| :-----------------: | -------- | ----------- |
|     Arkitektura     | x64      | -           |
|         RAM         | 8GB      | 16GB        |
| Hapësira e ruajtjes | 1GB      | 8GB         |
|         JDK         | 17       | 21          |

Për të bërë ndryshime të lehta në dosjet e konfigurimit, është gjithashtu e mirë të instaloni një redaktues si [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Shfaqja e saktë" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' nuk është një komandë, program i ekzekutueshëm i brendshëm ose i jashtëm, ose
skedar i shkëputur.
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

1. Fillimisht, shkarkoni **JDK 21** nga [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) në formatin `.msi`.
2. Ekzekutoni magjistrin e instalimit të shkarkuar dhe klikoni "Vazhdo".
3. Aktivizoni opsionin `Set JAVA_HOME variable` në mes të shiritit të menysë në të majtë dhe klikoni "Vazhdo".
4. Klikoni "Instalo" për të përfunduar instalimin e JRE.
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

Pastaj, instaloni JRE duke ekzekutuar komandën e mëposhtme në terminal.

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

## 2. Shkarkimi i Plazmasë

Plazma ofron një gamë të gjerë skedarësh ekzekutues.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Më shumë informacion</summary>

Emri i skedarit ekzekutues është `plazma-(menaxheri i versionit)-1.20.4-R0.1-SNAPSHOT-(forma e mapimit).jar`.

- **Forma e mapimit**\
  Mapimi është një lloj hartimi që lidh kodin real të Minecraft me kodin e zbehur.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapimi, është mapimi i Minecraft-it bazë. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Menaxheri i versionit**\
  Menaxheri i versionit është një lloj launcheri që nevojitet për të drejtuar serverin dhe për të patch-uar skedarët e serverit.
  - **Paperclip**\
    Zhvilluar nga ekipi i PaperMC për Paper dhe platformat e tjera të derivuara, shkarkon libraritë dhe aplikon patch-et në server.
  - **Bundler**\
    Menaxheri i versionit i Minecraft vanilla.

</details>

***

## 3. Krijimi i skriptit të fillimit

Për të filluar Plazmën lehtësisht dhe për të ristartuar serverin automatikisht, duhet të krijoni një [skript fillimi](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Mund të shkarkoni skriptin fillimi duke klikuar në butonin e shkarkimit në pjesën e poshtme të majtë.\
**Verifikoni se skripti i shkarkuar përputhet me sistemin tuaj operativ.**

***

## 4. Rregullimi i skedarëve

Tani lëvizni skriptin e fillimit të shkarkuar dhe Plazmën në një dosje të re.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Tani ekzekutoni skriptin e fillimit. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA Konsentimi

Pas ekzekutimit të skriptit fillimtar, do të krijohet një `eula.txt` në dosje.

EULA[^9] është një marrëveshje licensimi që duhet të pranohet duke përdorur shërbimet e [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Për të pranuar EULA-n, ndryshoni `eula=false` në `eula=true` në skedarin `eula.txt` dhe ruani ndryshimet.

***

## 6. Lejimi i hyrjes nga jashtë (Windows)

Sistemet moderne operative bllokojnë hyrjet e rrezikshme nga jashtë duke përdorur në mënyrë parazgjedhëse **firewall** dhe **ruter**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Nëse ruteri nuk e mbështet UPnP-në, për çdo ruter ka një panel të ndryshëm, kështu që duhet të kërkoni informata vetë.

Ose mund të përdorni [Ngrok](https://ngrok.com/) për të krijuar një adresë të përkohshme.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Verifikimi i nevojës për forwardim të portit

Shkruani dhe ekzekutoni si më poshtë në dritaren e ekzekutimit.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Nëse output-i është `True`, atëherë jeni gati, nëse është `False`, duhet të konfiguroni forwardimin e portit.

### 6.2 Hyrja në server

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Adresa për hyrjen në server mund të kontrollohet [këtu](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Pastaj, ristartoni serverin dhe Plazma do të provojë automatikisht të bëjë forwardimin e portit.

Suksesin e UPnP vlerësoni sipas mesazhit që shfaqet në konsolë, si `[UPnP] (mesazhi)`.

| Mesazhi                              | Kuptimi                                                 |
| ------------------------------------ | ------------------------------------------------------- |
| `Porti u hap me sukses (porti)`      | Forwardimi i portit është i suksesshëm. |
| `Porti (porti) është i hapur tashmë` | Një shërbim tjetër po përdor këtë port. |
| `Dështoi hapja e portit (porti)`     | Forwardimi i portit dështoi.            |
| `Shërbimi nuk është në dispozicion`  | Ruteri nuk e mbështet UPnP-në.          |

Kur serveri mbyllet, Plazma mbyll automatikisht portin.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Shkarkoni skedarin ZIP `Windows (64-bit)` nga [faqja zyrtare e Ngrok](https://ngrok.com/download).
2. Vendosni skedarin e shkarkuar të Ngrok në dosjen e serverit.
3. Në [panelin e Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) krijoni [tokenin e autorizimit](#user-content-fn-13)[^13].
4. Ekzekutoni komandën që shfaqet në dritaren e komandës në dosjen e serverit.
5. Shtoni `start /b ngrok tcp --region jp 25565` në pjesën më sipër të skriptit të ekzekutimit, dhe `taskkill /f /t /im ngrok.exe` në fund të tij.
6. Në pjesën më të sipërme të konsolës shfaqet `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`, ku `0.tcp.jp.ngrok.io:12345` do të jetë adresa e serverit.
7. Tani mund të lidheni nga jashtë përmes kësaj adrese.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Për shembull, pas ekzekutimit të komandës, nëse shfaqet si më poshtë,

```log
Konfigurimi i IP në Windows

Adapteri Ethernet Ethernet:

    Sufiksi DNS i lidhur. . . . :
    Adresa IPv4. . . . . . . . . : 192.168.3.7
    Maskë nënrede . . . . . . . : 255.255.255.0
    Gateway-i parazgjedhur . . . . . . : 192.168.3.1

```

Nëse provoni të lidheni me serverin nga lokal, mund të provoni të lidheni me adresën IPv4 që shfaqet si `192.168.3.7` këtu.

Nëse serveri dhe loja po ekzekutohen në të njëjtin PC, mund të lidheni me `localhost`.
{% endtab %}
{% endtabs %}

## 7. Të zhvillohemi

Pas fillimit të suksesshëm të serverit dhe funksionimit të duhur të tij, tani është koha për të personalizuar serverin.

Mësoni se si të personalizoni serverin duke lexuar udhëzimet më poshtë.

{% content-ref url="hapi-hapi.md" %}
[hapi-hapi.md](hapi-hapi.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Paperi i bazuar në Plazma është bazuar në Spigot dhe Spigot është platforma zyrtare e serverit.

[^3]: Tasti Windows + R

[^4]: Në rastin e Linuxit, në terminal shkruani `java --version`

[^5]: JRE është një projekt burim i hapur dhe ka shumë lloje si platforma e serverit Minecraft.

[^6]: Përgjithësisht njihet si **ekzekutor**.

[^7]: Nëse aktivizoni "Rivendosje automatike", serveri do të ri-startohet automatikisht. Mund të mbyllni duke shtypur `Control + C`.

[^8]: Nuk rekomandohet të kaloni gjysmën e sistemit.

    Për shembull, kur kapaciteti i përgjithshëm i memorjes së sistemit është 8GB, nuk rekomandohet ta vendosni më shumë se 4GB.

[^9]: Marrëveshja e Licencës për Përdoruesin e Fundit, marrëveshja e licencës për përdoruesin përfundimtar. Për informacione më të hollësishme, ju lutemi kontrolloni [faqen zyrtare të Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Korporata Microsoft.

[^11]: Në rastin e Republikës së Koreë, sipas nenit 32, paragrafi 1, nënparagrafi 9 të Ligjit për Promovimin e Industrisë së Lojërave, mund të bëhet denoncim ligjor nga **Korporata Microsoft e Koreas**.

[^12]: Universal Plug & Play. Purpur i përfshirë në Plazma komunikon automatikisht me ruterin dhe hap portën vetëm kur serveri është në ekzekutim, kështu që nuk ka nevojë për përcjellje portash manualisht.

[^13]: Nëse nuk keni llogari, regjistrohuni në Ngrok përmes llogarisë Google ose GitHub.
