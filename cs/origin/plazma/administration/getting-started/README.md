---
description: Zjistěte, jak vytvořit server pomocí Plazma.
---

# 👟 Začínáme

Pro stabilní používání Plazmy musí systém splňovat následující požadavky.

|                | Minimální | Doporučené |
| :------------: | --------- | ---------- |
|  Architektura  | x64       | -          |
|       RAM      | 8GB       | 16GB       |
| Úložný prostor | 1GB       | 8GB        |
|       JDK      | 17        | 21         |

Pro pohodlnou úpravu konfiguračních souborů je dobré nainstalovat editor jako [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Správný výstup" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (sestavení 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (sestavení 21.0.2+13-LTS, smíšený režim, sdílení)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' není rozpoznávaným vnitřním nebo externím příkazem, spustitelným programem nebo
souborem dávkových příkazů.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Nerozpoznaná volba: --version
Chyba: Nelze vytvořit virtuální stroj Java.
Chyba: Došlo k fatální výjimce. Program se ukončí.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Nejprve si stáhněte **JDK 21** ve formátu `.msi` z [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Spusťte stažené instalačního průvodce a postupujte kliknutím na `Další`.
3. V levém středu okna vyberte `Set JAVA_HOME variable`, potvrďte kliknutím na `Další`.
4. Kliknutím na `Instalovat` dokončete instalaci JRE.
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

Poté spusťte následující příkaz pro instalaci JRE.

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

## 2. Stažení Plazmy

Plazma nabízí různé verze spustitelných souborů.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Více informací</summary>

Název spustitelného souboru je stanoven jako `plazma-(správce verzí)-1.20.4-R0.1-SNAPSHOT-(mapovací forma).jar`.

- **Mapovací forma**\
  Mapování slouží jako jakési spojení mezi skutečným kódem Minecraftu a obfuskovaným kódem.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, mapování používané v běžném Minecraftu. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Startovací skript lze stáhnout pomocí tlačítka pro stažení v levém dolním rohu.\
**Zkontrolujte, zda stažený startovací skript odpovídá vašemu operačnímu systému.**

***

## 4. Úklid souborů

Přesuňte stažený startovací skript a Plazmu do nové složky.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Spusťte startovací skript. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Souhlas s EULA

Po jednom spuštění startovacího skriptu se vytvoří soubor `eula.txt` ve složce.

EULA[^9] je smlouva o licenci, kterou musíte přijmout k využívání služeb [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Pro souhlas s EULOU upravte a uložte soubor `eula.txt` z `eula=false` na `eula=true`.

***

## 6. Povolení externího přístupu (Windows)

Moderní operační systémy blokují externí přístup pomocí základních funkcí jako jsou **firewall** a **router**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| Zpráva                              | Význam                                              |
| ----------------------------------- | --------------------------------------------------- |
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
Windows IP konfigurace

Ethernetový adaptér Ethernet:

    Připojené DNS přípony. . . . :
    IPv4 adresa. . . . . . . . . : 192.168.3.7
    Maskování podsítě. . . . . . . : 255.255.255.0
    Výchozí brána. . . . . . . : 192.168.3.1

```

Pokus o připojení k serveru z lokální sítě můžete provést pomocí zobrazené `192.168.3.7` u IPv4 adresy.

Pokud server a hra běží na stejném počítači, můžete se připojit pomocí `localhost`.
{% endtab %}
{% endtabs %}

## 7. Růst

Pokud se server úspěšně spustil a správně funguje, je čas na jeho přizpůsobení.

Pro zpřiznění serveru se podívejte na následující příručku.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
