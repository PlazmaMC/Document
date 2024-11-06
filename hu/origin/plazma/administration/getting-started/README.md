---
description: Tudj meg többet arról, hogyan készíthetsz szervereket a Plazma segítségével.
---

# 👟 Kezdés

A Plazma stabil használatához a rendszernek az alábbi követelményeknek kell megfelelnie.

|              | Minimum | Ajánlott |
| :----------: | ------- | -------- |
| Architektúra | x64     | -        |
|      RAM     | 8GB     | 16GB     |
|    Tárhely   | 1GB     | 8GB      |
|      JDK     | 17      | 21       |

A könnyebb konfiguráció módosítás érdekében érdemes telepíteni olyan szerkesztőket, mint a [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Helyes kimenet" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Futtatókörnyezet Zulu21.32+17-CA (verzió: 21.0.2+13-LTS)
OpenJDK 64-bites Szerver VM Zulu21.32+17-CA (verzió: 21.0.2+13-LTS, vegyes mód, megosztás)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' nem ismert parancs, belső vagy külső parancs, futtatható program vagy
batch fájl.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Felismeretlen opció: --version
Hiba: Nem lehet létrehozni a Java virtuális gépet.
Hiba: Végzetes kivétel történt. A program leáll.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Először töltsd le az **JDK 21**-et az [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) oldalról `.msi` formátumban.
2. Futtasd a letöltött telepítő varázslót, majd kattints a `Next` gombra.
3. A megjelenő menüben a bal középső részen aktiváld a `Set JAVA_HOME variable` lehetőséget, majd kattints a `Next` gombra.
4. Nyomd meg az `Install` gombot az JRE telepítéséhez.
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

Ezután futtasd a következő parancsot a terminálban az JRE telepítéséhez.

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

## 2. Plazma letöltése

A Plazma többféle futtatható fájlt kínál.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>További információk</summary>

A futtatható fájl neve `plazma-(verzió kezelő)-1.20.4-R0.1-SNAPSHOT-(leképezési forma).jar`-ra van beállítva.

- **Leképezési forma**\
  A leképezés a Minecraft valós kódját és az obfuskált kódot összekötőfajta térkép.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang által leképezett, a Vanilla Minecraft leképezése. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Verzió kezelő**\
  A verzió kezelő egy olyan indító, amely a szerver futtatásához szükséges könyvtárakat és a szerver fájlokat patcheli.
  - **Paperclip**\
    A PaperMC csapata által fejlesztett kezelő a Paper és más származékokhoz, amely letölti a könyvtárakat és alkalmazza a javításokat a szerverre.
  - **Bundler**\
    A Vanilla Minecraft verzió kezelője.

</details>

***

## 3. Indító szkript létrehozása

A Plazmát egyszerűen elindíthatod és a szerver automatikusan újraindul, ha egy [indító szkriptet](#user-content-fn-6)[^6] hozol létre.

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

A bal alsó sarokban lévő Letöltés gombbal töltheted le az indító szkriptet.\
**Ellenőrizd, hogy a letöltött indító szkript megegyezik-e az operációs rendszereddel.**

***

## 4. Fájlok rendezése

Most már mozgasd a letöltött indító szkriptet és a Plazmát egy új mappába.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Most futtasd az indító szkriptet. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA elfogadása

Miután egyszer futtattad az indító szkriptet, a mappában létrejön az `eula.txt` fájl.

Az EULA[^9] egy olyan felhasználási szerződés, amelyet elfogadnod kell a [Mojang Studios](#user-content-fn-10)[^10] szolgáltatásainak használata során.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Az EULA elfogadásához módosítsd az `eula.txt` fájlban az `eula=false`-t `eula=true`-ra, majd mentsd el a változtatásokat.

***

## 6. Külső hozzáférés engedélyezése (Windows)

A modern operációs rendszerek alapértelmezetten blokkolják a külső hozzáférést a tűzfal és a router által, hogy megvédjenek a veszélyes hozzáférésektől.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Ha a router nem támogatja az UPnP-t, vagy a router típusától függően eltérő lehet a panel, akkor magadnak kell keresned információkat.

Vagy használhatsz az [Ngrok](https://ngrok.com/) segítségével ideiglenes címet.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Port forwarding szükségességének ellenőrzése

Írd be a Futtatás mezőbe az alábbiakat, majd nyomd meg az Enter billentyűt.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Ha a kimenet `True`, akkor elég ennyi, ha viszont `False`, akkor be kell állítani a port forwardingot.

### 6.2 Szerverhez való csatlakozás

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

A szerverhez való csatlakozáshoz használt cím [itt](https://ip.pe.kr/) található meg.
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Ezután a szerver újraindítása után a Plazma automatikusan megpróbálja a porttovábbítást.

Az alábbiakban az UPnP sikerességét jelző üzenetek találhatók, amelyek a konzolon `[UPnP] (üzenet)` formában jelennek meg.

| üzenet                                   | jelentés                                                           |
| ---------------------------------------- | ------------------------------------------------------------------ |
| `Sikeresen megnyitott port (port)`       | Porttovábbítás sikeres.                            |
| `A port (port) már nyitva van`           | Egy másik szolgáltatás használja már ezt a portot. |
| `Nem sikerült megnyitni a portot (port)` | Porttovábbítás sikertelen.                         |
| `A szolgáltatás nem elérhető`            | A router nem támogatja az UPnP-t.                  |

Amikor a szerver leáll, a Plazma automatikusan bezárja a portokat.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. [Ngrok weboldal](https://ngrok.com/download)-ról töltsd le a `Windows (64-bit)` ZIP fájlt.
2. Tedd a letöltött Ngrok-ot a szerver mappába.
3. [Ngrok vezérlőpult](https://dashboard.ngrok.com/get-started/your-authtoken)-ról hozz létre egy [hitelesítési token](#user-content-fn-13)[^13]-at.
4. Futtasd a szerver mappában az alábbi `Command Line`-on megjelenő parancsot.
5. A futtatási szkript legtetejére add hozzá `start /b ngrok tcp --region jp 25565`, a legalsó sorba pedig `taskkill /f /t /im ngrok.exe`-t.
6. A konzol tetején található `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`-nél a `0.tcp.jp.ngrok.io:12345` lesz a szerver címe.
7. Most már külsőleg is csatlakozhatsz ezen a címen keresztül.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Például, ha a parancs végrehajtása után a következőképpen jelenik meg a kimenet,

```log
Windows IP konfiguráció

Ethernet adapter Ethernet:

    Csatlakoztatott DNS keresztnév. . . . :
    IPv4 cím. . . . . . . . . : 192.168.3.7
    Alhálózati maszk . . . . . . . : 255.255.255.0
    Alapértelmezett átjáró . . . . . . : 192.168.3.1

```

Ha megpróbálja csatlakozni a `192.168.3.7` címen megadott IPv4 címen keresztül, akkor a helyi gépről csatlakozhat a szerverhez.

Ha a szerver és a játék ugyanazon a PC-n fut, akkor a `localhost`-on keresztül is csatlakozhat.
{% endtab %}
{% endtabs %}

## 7. Fejlődni

Ha sikeresen elindította a szervert, és a szerver megfelelően működik, most a szerver testreszabásának ideje van.

Ismerje meg, hogyan személyre szabhatja a szerver használatát az alábbi útmutató segítségével.

{% content-ref url="kovetkezo-lepes.md" %}
[kovetkezo-lepes.md](kovetkezo-lepes.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: A Plazma alapú Paper a Spigotra épül, és a Spigot az hivatalos szerver platformon alapul.

[^3]: Windows kulcs + R

[^4]: Linux esetén a `java --version` paranccsal a terminálban

[^5]: A JRE egy nyílt forráskódú projekt, például a Minecraft szerver platformhoz hasonlóan többféle változat létezik.

[^6]: Általában **hajtóműnek** nevezik.

[^7]: Az "Automatikus újraindítás" bekapcsolásával a szerver automatikusan újraindul. Beírhatja a `Control + C` parancsot a leállításhoz.

[^8]: Nem ajánlott a rendszer felének túllépése.

    Például ha a rendszer teljes memóriája 8 GB, akkor nem ajánlott 4 GB-nál többet beállítani.

[^9]: Végfelhasználói licencszerződés, End-User License Agreement. További részletekért kérjük, látogassa meg a [Minecraft honlapját](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: A Dél-Koreai játékipar támogatásáról szóló törvény 32. cikk (1) bekezdése (9) pontja alapján a **Korea Microsoft Corporation** jogi lépéseket tehet.

[^12]: Universal Plug & Play. A Purpur, amely a Plazmában található, automatikusan kommunikál a routerrel ezen a technológián keresztül, és csak akkor nyitja meg a portokat, amikor a szerver fut, ezért nincs szükség közvetlen portnyitásra.

[^13]: Ha nincs fiókja, regisztráljon a Google vagy a GitHub fiókján keresztül a Ngrokhoz.
