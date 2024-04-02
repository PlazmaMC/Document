---
description: Mësoni si të krijoni një server me Plazma.
---

# 👟 Filloni

Për të përdorur Plazma-n në mënyrë stabile, sistemi duhet të plotësojë këto kërkesa:

|                     | Minimumi | Rekomanduar |
| :-----------------: | -------: | ----------: |
|     Arkitektura     |      x64 |           - |
|         RAM         |      8GB |        16GB |
| Hapësira e ruajtjes |      1GB |         8GB |
|         JRE         |       17 |          21 |

Për të bërë ndryshime të lehta në dosjet e konfigurimit, është gjithashtu e mirë të instaloni një redaktues si [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalimi i JRE-së

Siç mund të kuptohet nga emri, Minecraft: **"Java"** Edition është zhvilluar në Java, kështu që për ta ekzekutuar, ka nevojë për JRE[^1].

Pasiguria Plazma bazohet në platformën zyrtare të serverit të Mojang Studios [^2], prandaj për të përdorur Plazma-n, duhet të instalohet JRE.

### 1.1 Verifikimi i JRE-së

Për të verifikuar nëse JRE është i instaluar në sistemin tuaj, shkruani dhe ekzekutoni [`cmd /k java --version`](#user-content-fn-4)[^4] në dritaren e ekzekutimit.

Nëse shfaqet si më poshtë, kaloni në [2 hapat e ardhshëm](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Nëse nuk shfaqet si më poshtë ose si më poshtë, atëherë JRE nuk ekziston ose është shumë i vjetër, kështu që duhet të vazhdoni me [1.2 hapin](setup.md#id-1.2).

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

### 1.2 JRE instalimi

Në këtë udhëzues përdorim Azul Zulu si një [nga llojet](#user-content-fn-5)[^5] e JRE.

Pas instalimit, rishikoni hapin [1.1](setup.md#id-1.1) për të siguruar që instalimi është kryer me sukses.

{% tabs %}

{% tab title="Windows" %}

1. Fillimisht, shkarkoni **JDK 21** nga [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) në formatin `.msi`.
2. Ekzekutoni magjistrin e instalimit të shkarkuar dhe klikoni "Vazhdo".
3. Aktivizoni opsionin `Set JAVA_HOME variable` në mes të shiritit të menysë në të majtë dhe klikoni "Vazhdo".
4. Klikoni "Instalo" për të përfunduar instalimin e JRE.

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

Pastaj, instaloni JRE duke ekzekutuar komandën e mëposhtme në terminal.

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

## 2. Shkarkimi i Plazmasë

Plazma ofron një gamë të gjerë skedarësh ekzekutues.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Për ata që janë të interesuar për zhvilluesit ose për veçoritë e çdo lloji, informacioni më poshtë është për ta.\
Përdoruesit e zakonshëm mund të kalojnë në [hapat 3](setup.md#id-3) pa probleme.

{% endhint %}

<details>

<summary>Më shumë informacion</summary>

Emri i skedarit ekzekutues është `plazma-(menaxheri i versionit)-1.20.4-R0.1-SNAPSHOT-(forma e mapimit).jar`.

- **Forma e mapimit**\
  Mapimi është një lloj hartimi që lidh kodin real të Minecraft me kodin e zbehur.
  - **Reobf**\
    Rizbehja, njihet edhe si mapimi i Spigot dhe përdoret në shumicën e shtojcave NMS.\
    Nga versioni 1.20.5 do të ndalet përdorimi i tij.
  - **Mojmap**\
    Mapimi i Mojang, mapimi i Minecraft vanilla.
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

Mund të krijoni skriptin fillimi përmes [Flags.sh](https://flags.sh). Nëse jepni vetëm [memorien që do të përdoret](#user-content-fn-8)[^8] në Plazma, komanda do të optimizohet automatikisht.

Mund të shkarkoni skriptin fillimi duke klikuar në butonin e shkarkimit në pjesën e poshtme të majtë.\
**Verifikoni se skripti i shkarkuar përputhet me sistemin tuaj operativ.**

***

## 4. Rregullimi i skedarëve

Tani lëvizni skriptin e fillimit të shkarkuar dhe Plazmën në një dosje të re.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Në kundërt, Plazma ose JRE mund të mos funksionojnë siç duhet.

{% endhint %}

Tani ekzekutoni skriptin e fillimit. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA Konsentimi

Pas ekzekutimit të skriptit fillimtar, do të krijohet një `eula.txt` në dosje.

EULA[^9] është një marrëveshje licensimi që duhet të pranohet duke përdorur shërbimet e [Mojang Studios](#user-content-fn-10)[^10].

Nëse nuk pranoni EULA-n, nuk mund të filloni serverin dhe nëse shkelni EULA-n, mund të ndëshkoheni me pezullim të llogarisë etj. [sanksione.](#user-content-fn-11)[^11]

Për të pranuar EULA-n, ndryshoni `eula=false` në `eula=true` në skedarin `eula.txt` dhe ruani ndryshimet.

***

## 6. Lejimi i hyrjes nga jashtë (Windows)

Sistemet moderne operative bllokojnë hyrjet e rrezikshme nga jashtë duke përdorur në mënyrë parazgjedhëse **firewall** dhe **ruter**.

Për Windows, pasi që keni lejuar në [hapat 3](setup.md#id-3), duhet të bëni vetëm forwardimin e portit.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| Mesazhi                              | Kuptimi                                 |
| ------------------------------------ | --------------------------------------- |
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
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Nëse provoni të lidheni me serverin nga lokal, mund të provoni të lidheni me adresën IPv4 që shfaqet si `192.168.3.7` këtu.

Nëse serveri dhe loja po ekzekutohen në të njëjtin PC, mund të lidheni me `localhost`.

{% endtab %}
{% endtabs %}

## 7. Faza e zhvillimit

Pas fillimit të suksesshëm të serverit dhe funksionimit të duhur të tij, tani është koha për të personalizuar serverin.

Zbuloni se si të personalizoni serverin duke ndjekur udhëzimet më poshtë.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Ambienti i Ekzekutimit të Java-s.

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
