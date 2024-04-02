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

{% code title="Helyes kimenet" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Ha nem ez jelenik meg, vagy az alábbihoz hasonló, akkor nincs telepítve a JRE, vagy túl régi verzió van, tehát a [1.2. lépést](setup.md#id-1.2) kell végrehajtani.

{% code title="JRE nincs telepítve" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE túl régi" lineNumbers="true" %}

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

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) -tól letölti a **JDK 21**-et, majd futtatja a `.dmg` telepítő varázslót a JRE telepítéséhez.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Először futtassa a következő parancsot a terminálban, hogy hozzáadja az Azul Zulu tárolót az APT-hez.

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

A JRE telepítéséhez adja ki a következő parancsot.

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

**Általában a `Reobf Paperclip`-et használják.**

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

**A mappaneveknek mindig szóköz nélkülieknek és angol nyelvűeknek kell lenniük.**

Ellenkező esetben a Plazma vagy a JRE nem működhet megfelelően.

{% endhint %}

Most futtasd az indító szkriptet. Windows esetén a <mark style="background-color:orange;">tűzfal engedélyezési ablakban mindenképpen válassza ki a **Engedélyezés**-t</mark>.

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

**Ez a útmutató a Windows operációs rendszerre és az [UPnP](#user-content-fn-12)[^12]-támogatott routerekre vonatkozik.**

Ha a router nem támogatja az UPnP-t, vagy a router típusától függően eltérő lehet a panel, akkor magadnak kell keresned információkat.

Vagy használhatsz az [Ngrok](https://ngrok.com/) segítségével ideiglenes címet.
{% endhint %}

{% hint style="warning" %}

**Linux vagy macOS vagy más (körülbelül) UNIX alapú operációs rendszerek esetén a tűzfal beállításai eltérőek lehetnek, ezért keresse meg a megfelelő információkat.**

{% endhint %}

### 6.1 Port forwarding szükségességének ellenőrzése

Írd be a Futtatás mezőbe az alábbiakat, majd nyomd meg az Enter billentyűt.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Ha a kimenet `True`, akkor elég ennyi, ha viszont `False`, akkor be kell állítani a port forwardingot.

### 6.2 Szerverhez való csatlakozás

{% tabs %}

{% tab title="Külső hozzáférés" %}

Ha nem szükséges port átirányítás, vagy már sikeresen végrehajtotta, most csatlakozhat a szerverhez.

A szerverhez való csatlakozáshoz használt cím [itt](https://ip.pe.kr/) található meg.

{% endtab %}

{% tab title="UPnP-n keresztül port átirányítás megpróbálása" %}

A `purpur.yml` fájlban a szerver mappájában, engedélyezd a `network.upnp-port-forwarding` beállítást `true` értékre.

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

{% tab title="Ngrok temporary address generation" %}

Az Ngrok módszer ideális rövid távú tesztekhez, közösségi játékokhoz vagy barátokkal való együttjátszáshoz.

1. [Ngrok weboldal](https://ngrok.com/download)-ról töltsd le a `Windows (64-bit)` ZIP fájlt.
2. Tedd a letöltött Ngrok-ot a szerver mappába.
3. [Ngrok vezérlőpult](https://dashboard.ngrok.com/get-started/your-authtoken)-ról hozz létre egy [hitelesítési token](#user-content-fn-13)[^13]-at.
4. Futtasd a szerver mappában az alábbi `Command Line`-on megjelenő parancsot.
5. A futtatási szkript legtetejére add hozzá `start /b ngrok tcp --region jp 25565`, a legalsó sorba pedig `taskkill /f /t /im ngrok.exe`-t.
6. A konzol tetején található `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`-nél a `0.tcp.jp.ngrok.io:12345` lesz a szerver címe.
7. Most már külsőleg is csatlakozhatsz ezen a címen keresztül.

{% endtab %}

{% tab title="Helyi hozzáférés" %}

Ha a szerverhez helyileg szeretnél csatlakozni, futtasd a `cmd /k ipconfig` parancsot a végrehajtás ablakában, majd a megjelenő `IPv4 cím`-re tudsz csatlakozni.

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
