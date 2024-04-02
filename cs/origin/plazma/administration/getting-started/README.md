---
description: Zjistěte, jak vytvořit server pomocí Plazma.
---

# 👟 Začínáme

Pro stabilní používání Plazmy musí systém splňovat následující požadavky.

|                | Minimální | Doporučené |
| :------------: | --------: | ---------: |
|  Architektura  |       x64 |          - |
|       RAM      |       8GB |       16GB |
| Úložný prostor |       1GB |        8GB |
|       JRE      |        17 |         21 |

Pro pohodlnou úpravu konfiguračních souborů je dobré nainstalovat editor jako [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalace JRE

Jak název napovídá, Minecraft: **"Java"** Edition je vyvíjen v Javě a ke spuštění je potřeba JRE[^1].

Plazma je oficiální serverová platforma od Mojang Studios [založená na tomto](#user-content-fn-2)[^2], proto je pro používání Plazmy nutné nainstalovat JRE.

### 1.1 Kontrola JRE

Pro ověření instalace JRE na systému zadejte do [spustitelného okna](#user-content-fn-3)[^3] příkaz [`cmd /k java --version`](#user-content-fn-4)[^4] a spusťte ho.

Pokud se zobrazí následující výstup, přeskočte na [2. krok](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Pokud se nezobrazí výstup jako výše, nebo se zobrazí následující, chybí JRE nebo je příliš zastaralý, a je třeba provést [1.2 krok](setup.md#id-1.2).

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

### 1.2 Instalace JRE

V tomto průvodci použijeme jednu z [verzí](#user-content-fn-5)[^5] JRE, konkrétně Azul Zulu.

Po dokončení instalace zkontrolujte správnost instalace opakováním [1.1 kroku](setup.md#id-1.1).

{% tabs %}

{% tab title="Windows" %}

1. Nejprve si stáhněte **JDK 21** ve formátu `.msi` z [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Spusťte stažené instalačního průvodce a postupujte kliknutím na `Další`.
3. V levém středu okna vyberte `Set JAVA_HOME variable`, potvrďte kliknutím na `Další`.
4. Kliknutím na `Instalovat` dokončete instalaci JRE.

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

Poté spusťte následující příkaz pro instalaci JRE.

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

## 2. Stažení Plazmy

Plazma nabízí různé verze spustitelných souborů.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Následující informace jsou pro vývojáře nebo zvídavé jedince ohledně jednotlivých verzí.\
Pro běžné uživatele je možné přeskočit na [3. krok](setup.md#id-3) bez problémů.

{% endhint %}

<details>

<summary>Více informací</summary>

Název spustitelného souboru je stanoven jako `plazma-(správce verzí)-1.20.4-R0.1-SNAPSHOT-(mapovací forma).jar`.

- **Mapovací forma**\
  Mapování slouží jako jakési spojení mezi skutečným kódem Minecraftu a obfuskovaným kódem.
  - **Reobf**\
    Reobfuskace, též známá jako Spigot mapování, je běžně používána v NMS zásuvných modulech.\
    Od verze 1.20.5 bude používání ukončeno.
  - **Mojmap**\
    Mapování od Mojang, základní mapování Minecraftu.
- **Správce verzí**\
  Správce verzí je jakýsi spouštěcí program pro server, který je nezbytný pro spuštění serveru a aplikování patchů na serverové soubory.
  - **Paperclip**\
    Správce od týmu PaperMC pro Paper a další odvozené platformy, který slouží ke stažení knihoven a aplikování patchů na server.
  - **Bundler**\
    Správce verzí pro běžný Minecraft.

</details>

***

## 3. Vytvoření startovacího skriptu

Pro snadné spuštění Plazmy a automatické restartování serveru je nutné vytvořit [startovací skript](#user-content-fn-6)[^6].

Pomocí [Flags.sh](https://flags.sh) lze vytvořit [startovací skript.](#user-content-fn-7)[^7]\
Pro Plazmu stačí zadat [paměť k použití](#user-content-fn-8)[^8], příkaz se automaticky optimalizuje.

Startovací skript lze stáhnout pomocí tlačítka pro stažení v levém dolním rohu.\
**Zkontrolujte, zda stažený startovací skript odpovídá vašemu operačnímu systému.**

***

## 4. Úklid souborů

Přesuňte stažený startovací skript a Plazmu do nové složky.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

V opačném případě Plazma nebo JRE nemusí správně fungovat.

{% endhint %}

Spusťte startovací skript. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. Souhlas s EULA

Po jednom spuštění startovacího skriptu se vytvoří soubor `eula.txt` ve složce.

EULA[^9] je smlouva o licenci, kterou musíte přijmout k využívání služeb [Mojang Studios](#user-content-fn-10)[^10].

Pokud nesouhlasíte s EULOU, nemůžete spustit server a porušení EULY může mít za následek sankce, jako je pozastavení účtu, atd. [může to být trestáno.](#user-content-fn-11)[^11]

Pro souhlas s EULOU upravte a uložte soubor `eula.txt` z `eula=false` na `eula=true`.

***

## 6. Povolení externího přístupu (Windows)

Moderní operační systémy blokují externí přístup pomocí základních funkcí jako jsou **firewall** a **router**.

V případě Windows, pokud jste povolili firewall v [3. kroku](setup.md#id-3), stačí provést pouze přesměrování portů.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Pokud váš router nepodporuje UPnP, každý router má jiné rozhraní, takže je třeba provést vlastní vyhledávání informací.

Alternativně můžete použít [Ngrok](https://ngrok.com/) k vytvoření dočasné adresy.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Kontrola potřeby přesměrování portů

Zadejte do spustitelného okna následující a spusťte ho.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Pokud je výstup `True`, není třeba nic dalšího, pokud je `False`, je třeba nastavit přesměrování portů.

### 6.2 Připojení k serveru

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Při připojení k serveru použijte adresu zde k dispozici: [zde](https://ip.pe.kr/)

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Poté restartujte server a Plazma automaticky zkusí přesměrovat porty.

Níže je uvedeno, zda bylo UPnP úspěšné podle zpráv na konzoli, které se zobrazí jako `[UPnP] (zpráva)`.

| Zpráva                              | Význam                              |
| ----------------------------------- | ----------------------------------- |
| `Port byl úspěšně otevřen (port)`   | Přesměrování portu bylo úspěšné.    |
| `Port (port) je již otevřený`       | Jiná služba již využívá tento port. |
| `Nepodařilo se otevřít port (port)` | Přesměrování portu selhalo.         |
| `Služba není dostupná`              | Směrovač nepodporuje UPnP.          |

Když je server vypnut, Plazma automaticky uzavře porty.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Stáhněte ZIP soubor `Windows (64-bit)` z [domovské stránky Ngrok](https://ngrok.com/download).
2. Umístěte stažený Ngrok do složky se serverem.
3. Na [Nástěnce Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) vytvořte [autentizační token](#user-content-fn-13)[^13].
4. Ve složce se serverem spusťte příkazy zobrazené v `Command Line`.
5. Přidejte `start /b ngrok tcp --region jp 25565` na začátek spouštěcího skriptu a `taskkill /f /t /im ngrok.exe` na konec.
6. Adresa serveru bude `0.tcp.jp.ngrok.io:12345` zobrazená na vrcholu konzole.
7. Nyní můžete přistupovat k serveru zvenčí pomocí této adresy.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Například, pokud se po spuštění příkazu zobrazí následující,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Pokus o připojení k serveru z lokální sítě můžete provést pomocí zobrazené `192.168.3.7` u IPv4 adresy.

Pokud server a hra běží na stejném počítači, můžete se připojit pomocí `localhost`.

{% endtab %}
{% endtabs %}

## 7. Fáze rozvoje

Pokud se server úspěšně spustil a správně funguje, je čas na jeho přizpůsobení.

Zjistěte, jak přizpůsobit server pomocí následujícího průvodce.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java běhové prostředí.

[^2]: Paper, na kterém je založen Plazma, je založen na Spigotu, který je oficiální platformou serveru.

[^3]: Kombinace kláves Windows + R

[^4]: V případě Linuxu zadejte v terminálu `java --version`

[^5]: JRE je jedním z open source projektů a existuje několik verzí podobně jako u platformy Minecraft serveru.

[^6]: Je obecně znám jako **spouštěč**.

[^7]: Pokud povolíte „Automatické restartování“, server se automaticky restartuje. Můžete ukončit pomocí `Control + C`.

[^8]: Není doporučeno překročit polovinu dostupného systémového paměti.

    Například, pokud je celková kapacita paměti systému 8 GB, není doporučeno nastavit více než 4 GB.

[^9]: Smlouva o koncovém uživatelském licenčním dohodě. Pro více informací se podívejte na [stránky Minecraftu](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Společnost Microsoft Corporation.

[^11]: V souladu s čl. 32 odst. 1 písm. i) zákona o podpoře herního průmyslu v Koreji může být **Korejská pobočka společnosti Microsoft** podána žaloba.

[^12]: Univerzální zásuvka a hraj. Purpur obsažený v Plazma komunikuje s routerem automaticky skrze tuto technologii a otevírá porty pouze tehdy, když je server spuštěn, takže není potřeba provádět přímé přesměrování portů.

[^13]: Pokud nemáte účet, zaregistrujte se do Ngrok pomocí účtu Google nebo GitHub.
