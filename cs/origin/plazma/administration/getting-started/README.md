---
description: Zjistěte, jak vytvořit server pomocí Plazma.
---

# 👟 Začínáme

Pro stabilní používání Plazmy musí systém splňovat následující požadavky.

|                | Minimální | Doporučené |
| :------------: | :-------- | :--------- |
|  Architektura  | x64       | -          |
|       RAM      | 8GB       | 16GB       |
| Úložný prostor | 1GB       | 8GB        |
|       JRE      | 17        | 21         |

Pro pohodlnou úpravu konfiguračních souborů je dobré nainstalovat editor jako [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalace JRE

Jak název napovídá, Minecraft: **"Java"** Edition je vyvíjen v Javě a ke spuštění je potřeba JRE[^1].

Plazma je oficiální serverová platforma od Mojang Studios [založená na tomto](#user-content-fn-2)[^2], proto je pro používání Plazmy nutné nainstalovat JRE.

### 1.1 Kontrola JRE

Pro ověření instalace JRE na systému zadejte do [spustitelného okna](#user-content-fn-3)[^3] příkaz [`cmd /k java --version`](#user-content-fn-4)[^4] a spusťte ho.

Pokud se zobrazí následující výstup, přeskočte na [2. krok](setup.md#id-2).

{% code title="Správný výstup" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (sestavení 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (sestavení 21.0.2+13-LTS, smíšený režim, sdílení)
```

{% endcode %}

Pokud se nezobrazí výstup jako výše, nebo se zobrazí následující, chybí JRE nebo je příliš zastaralý, a je třeba provést [1.2 krok](setup.md#id-1.2).

{% code title="JRE není nainstalováno" lineNumbers="true" %}

```log
'java' není rozpoznávaným vnitřním nebo externím příkazem, spustitelným programem nebo
souborem dávkových příkazů.
```

{% endcode %}

{% code title="JRE je příliš zastaralé" lineNumbers="true" %}

```log
Nerozpoznaná volba: --version
Chyba: Nelze vytvořit virtuální stroj Java.
Chyba: Došlo k fatální výjimce. Program se ukončí.
```

{% endcode %}

### 1.2 Instalace JRE

V tomto průvodci použijeme jednu z [verzí](#user-content-fn-5)[^5] JRE, konkrétně Azul Zulu.

Po dokončení instalace zkontrolujte správnost instalace opakováním [1.1 kroku](setup.md#id-1.1).

{% tabs %}

{% tab title="Windows" %}

1. Nejprve si stáhněte **JDK 21** ve formátu `.msi` z [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Spusťte stažené instalačního průvodce a postupujte kliknutím na `Další`.
3. V levém středu okna vyberte `Set JAVA_HOME variable`, potvrďte kliknutím na `Další`.
4. Kliknutím na `Instalovat` dokončete instalaci JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) stáhněte JDK 21 ve formátu `.dmg` a spusťte instalační průvodce pro instalaci JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Nejprve spusťte následující příkaz v terminálu k přidání úložiště Azul Zulu do APT.

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

Můžete nainstalovat JRE zadáním následujícího příkazu.

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

**Většinou se používá `Reobf Paperclip`.**

Následující informace jsou pro vývojáře nebo zvídavé jedince ohledně jednotlivých verzí.\
Pro běžné uživatele je možné přeskočit na [3. krok](setup.md#id-3) bez problémů.

{% endhint %}

<details>

<summary>Více informací</summary>

Název spustitelného souboru je stanoven jako `plazma-(správce verzí)-1.20.4-R0.1-SNAPSHOT-(mapovací forma).jar`.

- **Mapovací forma**\
  Mapování slouží jako jakési spojení mezi skutečným kódem Minecraftu a obfuskovaným kódem.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot mapování, které je také nazýváno jako Spigot mapování, se používá většinou v NMS pluginů.\
    Od verze 1.20.5 bude jeho používání ukončeno.
  - **Mojmap**\
    Mojang-mapped, mapování používané v běžném Minecraftu.
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

**Název složky musí být bez mezer a nastaven v angličtině.**

V opačném případě Plazma nebo JRE nemusí správně fungovat.

{% endhint %}

Spusťte startovací skript. Pro Windows vyberte v okně s výběrem povolení firewallu <mark style="background-color:orange;">volbu **Povolit**</mark>.

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

**Tento průvodce je psán za předpokladu, že používáte operační systém Windows a [UPnP](#user-content-fn-12)[^12] na směrovači.**

Pokud váš router nepodporuje UPnP, každý router má jiné rozhraní, takže je třeba provést vlastní vyhledávání informací.

Alternativně můžete použít [Ngrok](https://ngrok.com/) k vytvoření dočasné adresy.
{% endhint %}

{% hint style="warning" %}

**Pro operační systémy Linux nebo macOS a další (polo) UNIXové systémy je nutné vyhledat informace o nastavení firewallu pro jednotlivé služby.**

{% endhint %}

### 6.1 Kontrola potřeby přesměrování portů

Zadejte do spustitelného okna následující a spusťte ho.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Pokud je výstup `True`, není třeba nic dalšího, pokud je `False`, je třeba nastavit přesměrování portů.

### 6.2 Připojení k serveru

{% tabs %}

{% tab title="Přístup zvenčí" %}

Pokud není potřeba port forwardingu nebo již byl úspěšně nastaven, můžete se nyní připojit k serveru.

Při připojení k serveru použijte adresu zde k dispozici: [zde](https://ip.pe.kr/)

{% endtab %}

{% tab title="Pokus o port forwarding pomocí UPnP" %}

V souboru `purpur.yml` na serverovém adresáři aktivujte `network.upnp-port-forwarding` na hodnotu `true`.

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

{% tab title="Vytvoření dočasné adresy pomocí Ngrok" %}

Použití Ngrok je užitečné pro krátkodobé testování, spolupráci nebo hraní s přáteli.

1. Stáhněte ZIP soubor `Windows (64-bit)` z [domovské stránky Ngrok](https://ngrok.com/download).
2. Umístěte stažený Ngrok do složky se serverem.
3. Na [Nástěnce Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) vytvořte [autentizační token](#user-content-fn-13)[^13].
4. Ve složce se serverem spusťte příkazy zobrazené v `Command Line`.
5. Přidejte `start /b ngrok tcp --region jp 25565` na začátek spouštěcího skriptu a `taskkill /f /t /im ngrok.exe` na konec.
6. Adresa serveru bude `0.tcp.jp.ngrok.io:12345` zobrazená na vrcholu konzole.
7. Nyní můžete přistupovat k serveru zvenčí pomocí této adresy.

{% endtab %}

{% tab title="Připojení z lokálního zařízení" %}

Pokud se chcete připojit k serveru z lokálního zařízení, můžete použít `cmd /k ipconfig` v příkazovém okně pro připojení pomocí `IPv4 adresy`, která je uvedena výstupem.

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

## 7. Fáze rozvoje

Pokud se server úspěšně spustil a správně funguje, je čas na jeho přizpůsobení.

Zjistěte, jak přizpůsobit server pomocí následujícího průvodce.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
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
