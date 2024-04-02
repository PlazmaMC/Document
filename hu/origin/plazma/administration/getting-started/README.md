---
description: Tudj meg többet arról, hogyan készíthetsz szervereket a Plazma segítségével.
---

# 👟 Kezdés

A Plazma stabil használatához a rendszernek az alábbi követelményeknek kell megfelelnie.

|              | Minimum | Ajánlott |
| :----------: | ------: | -------: |
| Architektúra |     x64 |        - |
|      RAM     |     8GB |     16GB |
|    Tárhely   |     1GB |      8GB |
|      JRE     |      17 |       21 |

A könnyebb konfiguráció módosítás érdekében érdemes telepíteni olyan szerkesztőket, mint a [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE telepítése

Ahogy a nevéből is kikövetkeztethető, a Minecraft: **"Java"** Edition Java nyelven lett fejlesztve, így futtatásához szükség van a JRE[^1]-re.

Mivel a Plazma a Mojang Studios hivatalos szerverplatformján [alapul](#user-content-fn-2)[^2], a Plazma használatához szintén szükséges a JRE telepítése.

### 1.1 JRE jelenlétének ellenőrzése

Ha meg szeretnéd győződni arról, hogy a rendszeren telepítve van-e a JRE, írd be a Futtatás mezőbe a [`cmd /k java --version`](#user-content-fn-4)[^4] parancsot, majd nyomd meg az Enter billentyűt.

Ha az alábbiakhoz hasonló eredményt kapsz, ugorj a [2. lépésre](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Ha nem ez jelenik meg, vagy az alábbihoz hasonló, akkor nincs telepítve a JRE, vagy túl régi verzió van, tehát a [1.2. lépést](setup.md#id-1.2) kell végrehajtani.

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

### 1.2 JRE telepítése

Ebben a kézikönyvben az Azul Zulu-t használjuk az JRE egyik [fajtájaként](#user-content-fn-5)[^5].

Telepítés után ellenőrizd újra a [1.1. lépést](setup.md#id-1.1), hogy meggyőződj róla, hogy a telepítés sikeresen megtörtént.

{% tabs %}

{% tab title="Windows" %}

1. Először töltsd le az **JDK 21**-et az [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) oldalról `.msi` formátumban.
2. Futtasd a letöltött telepítő varázslót, majd kattints a `Next` gombra.
3. A megjelenő menüben a bal középső részen aktiváld a `Set JAVA_HOME variable` lehetőséget, majd kattints a `Next` gombra.
4. Nyomd meg az `Install` gombot az JRE telepítéséhez.

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

Ezután futtasd a következő parancsot a terminálban az JRE telepítéséhez.

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

## 2. Plazma letöltése

A Plazma többféle futtatható fájlt kínál.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Az alábbiak a fejlesztőknek vagy az egyes formák jellemzőivel kapcsolatos érdeklődőknek szólnak.\
Átlagos felhasználók számára nem probléma kihagyni a [3. lépést](setup.md#id-3).

{% endhint %}

<details>

<summary>További információk</summary>

A futtatható fájl neve `plazma-(verzió kezelő)-1.20.4-R0.1-SNAPSHOT-(leképezési forma).jar`-ra van beállítva.

- **Leképezési forma**\
  A leképezés a Minecraft valós kódját és az obfuskált kódot összekötőfajta térkép.
  - **Reobf**\
    Az újraobfuskálás, más néven Spigot leképezés, és a legtöbb NMS bővítményben használják.\
    A 1.20.5-től kezdve a használata befejeződik.
  - **Mojmap**\
    Mojang leképezés, a Vanilla Minecraft leképezése.
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

[Flags.sh](https://flags.sh) segítségével létrehozhatsz egy [indító szkriptet.](#user-content-fn-7)[^7]\
Csak add meg a Plazmához [használni kívánt memóriát](#user-content-fn-8)[^8], és a parancs automatikusan optimalizálódik.

A bal alsó sarokban lévő Letöltés gombbal töltheted le az indító szkriptet.\
**Ellenőrizd, hogy a letöltött indító szkript megegyezik-e az operációs rendszereddel.**

***

## 4. Fájlok rendezése

Most már mozgasd a letöltött indító szkriptet és a Plazmát egy új mappába.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Ellenkező esetben a Plazma vagy a JRE nem működhet megfelelően.

{% endhint %}

Most futtasd az indító szkriptet. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA elfogadása

Miután egyszer futtattad az indító szkriptet, a mappában létrejön az `eula.txt` fájl.

Az EULA[^9] egy olyan felhasználási szerződés, amelyet elfogadnod kell a [Mojang Studios](#user-content-fn-10)[^10] szolgáltatásainak használata során.

Ha nem fogadod el az EULA-t, nem tudod elindítani a szervert, és az EULA megsértése esetén a fiókod felfüggeszthetik vagy más [súlyos következményekkel járhat.](#user-content-fn-11)[^11]

Az EULA elfogadásához módosítsd az `eula.txt` fájlban az `eula=false`-t `eula=true`-ra, majd mentsd el a változtatásokat.

***

## 6. Külső hozzáférés engedélyezése (Windows)

A modern operációs rendszerek alapértelmezetten blokkolják a külső hozzáférést a tűzfal és a router által, hogy megvédjenek a veszélyes hozzáférésektől.

Windows esetén a tűzfalat már a [3. lépésben](setup.md#id-3) engedélyezted, tehát csak port forwardingra van szükség.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| üzenet                                   | jelentés                                           |
| ---------------------------------------- | -------------------------------------------------- |
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
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Ha megpróbálja csatlakozni a `192.168.3.7` címen megadott IPv4 címen keresztül, akkor a helyi gépről csatlakozhat a szerverhez.

Ha a szerver és a játék ugyanazon a PC-n fut, akkor a `localhost`-on keresztül is csatlakozhat.

{% endtab %}
{% endtabs %}

## 7. Fejlesztési szint

Ha sikeresen elindította a szervert, és a szerver megfelelően működik, most a szerver testreszabásának ideje van.

Ismerje meg, hogyan testresztheti a szervert az alábbi útmutató segítségével.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java futási környezet, Java Runtime Environment.

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
