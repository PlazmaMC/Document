---
description: Kwon ma Plazma ki yoo kare ma server iye ki kwanyo.
---

# 👟 Cing i

Kwon ma Plazma ki tye kwede ngom me cwinywa, kadi sistema ki dong i kom bedo ma i kom.

|                 | Tye kwede | Tye kwede iye |
| :-------------: | --------: | ------------: |
|     Akitekci    |       x64 |             - |
|       RAM       |       8GB |          16GB |
| Dano me cwinywa |       1GB |           8GB |
|       JRE       |        17 |            21 |

Icwinywa me kwo koni i kit ma pe ngom, [Visual Studio Code](https://code.visualstudio.com/download) me iye ma kwo yee kwanyo woko iye.

***

## 1. JRE ki tye kwede

Dano i kom bedo, Minecraft: **"Java"** Edition pe tye kwede me Java, kadi iye JRE[^1] ki dong i pe ki tye kwede.

Plazma ni ki Mojang Studios ki [bedo ma pe iye](#user-content-fn-2)[^2], Plazma ki tye kwede ki JRE tye kwede.

### 1.1 JRE ki gitye iye

JRE ki dong i pe ki tye kwede, [kwanyo pe iye](#user-content-fn-3)[^3] ki gin [`cmd /k java --version`](#user-content-fn-4)[^4] ki tye kwede.

Tye kwede iye kwede ki gitye [2 ngom](setup.md#id-2) woko.

{% code title="Dano me cwinywa" overflow="wrap" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Kwon ma pe ki tye kwede, kadi ma iye kwanyo pe ki tye kwede, tye kwede iye, kadi [1.2 ngom](setup.md#id-1.2) ki tye kwede.

{% code title="JRE ki pe tye kwede" overflow="wrap" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE ki tye kwede" overflow="wrap" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE moko

Kwon gang ma JRE [miyo ni](#user-content-fn-5)[^5] Azul Zulu ki tye kwede.

Kwede ki tye, [1.1 dong](setup.md#id-1.1) kadi kwede ki tye kwede i kom put me kwede ni iye moko.

{% tabs %}
{% tab title="Windows" %}

1. Ka ki tye kwede ki JRE **JDK 21** me `.msi` kwede ma [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) ki download.
2. Jokkwa kwede ma gin ma, `Doki` ki cwalo.
3. **Lok me cwalo, `Set JAVA_HOME variable` ki gengo ngolo,** `Doki` ki cwalo.
4. Ki cwalo ki tye kwede JRE ki tye ki `kwede` ki tye kwede.
   {% endtab %}

{% tab title="macOS" %}
[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) ki download **JDK 21** ma `.dmg` kwede me tye JRE ki tye.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
Ka ki tye, calo kom me tye ki terminal ki gengo Azul Zulu repository me doki.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Kadi kwede, calo kom me tye ki terminal ki gengo JRE ki tye kwede.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}
Calo kom me tye ki terminal ki gengo JRE ki tye kwede.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma ki download

Plazma ki nyutu ma kwo poto me doki me tye kwede.

{% hint style="warning" %}

### Maco doki `Reobf Paperclip` ki gengo.

Kwo iyi kacel ma onongo ki iyi, [3 dong](setup.md#id-3) ki tye kwede ki tye kwede ki iye moko.
{% endhint %}

<details>

<summary>Yom me kwo</summary>

Poto me doki me kwede iyi `plazma-(kare me bedo)-1.20.4-R0.1-SNAPSHOT-(maping kacel).jar` ma onongo.

- **Maping kacel**\
  Maping iyi ni Minecraft ma kwo doki me cwiny me lukalala ki dong kwede.
  - **Reobf**\
    Reobfuscation, Spigot maping ma kwo doki ma ngec ki dong kwede.\
    1.20.5 woko i kom mukene.
  - **Mojmap**\
    Mojang maping, Minecraft maping iyi.
- **Kare me bedo**\
  Kare me bedo ni doki me cwiny me server ki doki me lukalala ki dong kwede.
  - **Paperclip**\
    PaperMC timo ki yom Paper mukene ki dong kwede, kare me bedo ni kwo download ma kwo cwalo me server.
  - **Bundler**\
    Minecraft kare me bedo ki dong kwede.

</details>

***

## 3. Lok ma cwalo ki gengo

Plazma ki yom ma kwo, server ki cwalo me cwiny ma kwo, [lok ma cwalo ki gengo](#user-content-fn-6)[^6] ki tye kwede.

[Flags.sh](https://flags.sh) ki tye kwede ki [yom ma kwo](#user-content-fn-7)[^7]\
Plazma ma [tito me memory](#user-content-fn-8)[^8] i kom kom iye kwo mukene iyi mukene.

Lok me tye kare dongo download ki gengo lok ma cwalo ki gengo.\
**Dongo download ki gengo tye kwede kare ma i kom yom me kare me bedo pe JRE ki tye kwede.**

***

## 4. Failo ki yom

Iyi dongo download ki gengo me Plazma ki weko i kom kwede ki tye ki tye kwede.

{% hint style="warning" %}

### Dongo me kwede tye i kom ma pe tye, calo ma cwalo ki gengo.

Bet ma Plazma pe JRE ki tye kwede ma pe tye, ki iye moko.
{% endhint %}

Iyi dongo download ki gengo me cwalo ki gengo. Windows tye, <mark style="background-color:orange;">Lok ma cwalo ki gengo ki tye, kare</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**lok ma cwalo**</mark><mark style="background-color:orange;"> ki tye</mark> ki iye moko.

***

## 5. EULA dok ma cwalo

Lok ma cwalo ki gengo, folder ki `eula.txt` ki tye kwede.

EULA[^9] ni [Mojang Studios](#user-content-fn-10)[^10] ki lok me dong ma pe tye kwede ki iye moko.

EULA ki tye kwede, server ki tye ki tye kwede. EULA ki yom me dong ma pe tye kwede, EULA ki kwede mukene pe i kom iye moko [tito me dong](#user-content-fn-11)[^11].

EULA ki kwede, `eula=false` me cwalo ki `eula=true` ki i kom ma cwalo.

***

## 6. Lok me yom dok ma cwalo (Windows)

Lok ma tye, lok me yom me cwiny me cwalo, **kare me cwalo** pe **router** ki tye kwede ki dong kwede.

Windows tye, kare me cwalo ki [3 dong](setup.md#id-3) ki tye kwede, polo me fowadi ki tye kwede.

{% hint style="info" %}

### Iyi kwede ma Windows kare me cwalo pe [**UPnP**](#user-content-fn-12)[^12] ki tye kwede ki dong kwede.

Router ki UPnP pe tye kwede, router ki yom ma pe tye, ngolo ma cwalo ki kwede.

Tye, [Ngrok](https://ngrok.com/) ki tye kwede ki dong kwede, ki iye moko.
{% endhint %}

{% hint style="warning" %}

### Linux woko macOS i kom (jun) UNIX pe, kare me cwalo ki dong kwede, router service ki yom me dong ma pe tye, ngolo ma cwalo ki kwede.

{% endhint %}

### 6.1 Polo me fowadi ki dong kwede ki tye kwede

Lok me tye kare ma cwalo ki dong kwede ki tye kwede, ki iye moko.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Maco cwalo ki tye `Keto` ma pe tye, `Keto` me fowadi ki tye kwede ki tye kwede ki iye moko.

### 6.2 Server ki yom

{% tabs %}
{% tab title="Yom ma fowadi" %}
Polo me fowadi ki tye ki dong kwede, ki iye moko.

Server ki yom ma fowadi ki dong kwede ki tye kwede ki dong kwede.
{% endtab %}

{% tab title="UPnP me fowadi ki dong kwede" %}
Server folder ki `purpur.yml` ki tye, `network.upnp-port-forwarding` me cwalo `keto` ki dong kwede.

Kadi kwede, server me cwalo ki dong kwede, Plazma ki yom me fowadi ki dong kwede.

Iyi ni dok ma pe tye, UPnP mukene pe i kom iye moko, i kom iye moko, i kom iye moko, i kom iye moko, i kom iye moko.

| Dok ma pe tye                   | Kwo mukene                                  |
| ------------------------------- | ------------------------------------------- |
| `Lok ma tye kare (kare)`        | Kare me fowadi mukene.                      |
| `Kare (kare) ki tye kwo mukene` | Doki me server ki tye ki dong kwede mukene. |
| `Lok ma tye kare (kare)`        | Kare me fowadi mukene.                      |
| `Doki ma pe tye kare`           | Router ki UPnP pe tye kwede.                |

Server ki tye, Plazma ki yom ma fowadi ki tye kwede.
{% endtab %}

{% tab title="Ngrok me yom me doki ma cwalo" %}
Ngrok ki tye ki kwede ki dong kwede, kwede kwede kwede.

1. [Ngrok homepage](https://ngrok.com/download) ki download `Windows (64-bit)` ZIP kwede.
2. Doki me download ki Ngrok ki server folder.
3. [Ngrok dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) ki tye ki [yom me dong](#user-content-fn-13)[^13].
4. Server folder ki doki me tye kare me dong ki dok ma cwalo.
5. Doki ma tye kwede ki dong kwede, `start /b ngrok tcp --region jp 25565` ma cwalo ki dong kwede, `taskkill /f /t /im ngrok.exe` ki yom ma pe tye.
6. Kare ma pe tye ki dong kwede kwo mukene, `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` ma cwalo ki dong kwede.
7. Iyi ni doki me i kom dong kwede ki tye kwede.
   {% endtab %}

{% tab title="Local acel kikwero" %}
Local acel kikwero me server, cwiny pa 'cmd /k ipconfig' ki cwinyo ngec 'IPv4 address' ma kikwero.

Kikwero, dok pa cwinyo ma cwinyo,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Kikwero ma '192.168.3.7' ma kikwero, kikwero me server, cwiny pa 'localhost' ma kikwero.

Server me game pa PC mamegi, 'localhost' ma kikwero.
{% endtab %}
{% endtabs %}

## 7. Lok ma itye

Server ki kwo kikwero, ki kwo kikwero me server ki dano.

Cwalo me Java Runtime Environment, Java Runtime.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java Runtime.

[^2]: Plazma ki kwo Paper ki kwo Spigot, ki kwo Spigot ki kwo server platform ki kwo.

[^3]: Windows key + R

[^4]: Linux ma cwinyo 'java --version' pa terminal

[^5]: JRE ni open source project mo, Minecraft server platform ki dong ma kwo.

[^6]: Kwede **dong ma kwo** ma kwo.

[^7]: Kwede 'Auto-restart' ki kwo server ki kwo kikwero. Cwalo 'Control + C' ki tye.

[^8]: Dyang ma en aye kikwero ki kwo pe i temo.

    Kikwero, dyang ma en aye memory capacity ki 8GB, 4GB ma kwo pe i temo.

[^9]: End-User License Agreement, Lok me kwo kikwero ki temo. Gin ma giketo ki [Minecraft lok ma en](https://www.minecraft.net/ko-kr/usage-guidelines) kacel iweko.

[^10]: Microsoft Corporation.

[^11]: Pa Uganda ma gin ma en i kit ma kwo tic ki lanyo me lawang i kano 32 me 1 me 9, **Korea Microsoft Corporation** ma en i kwo tic ki.

[^12]: Universal Plug & Play. Plazma ma Purpur kicel i ngom miyo ma Purpur ki tye ka kompyuta me router kicel i ngom, ki tye ka server ki gengo ma kicel ki nyutu woko dong i port, ki tye ka port forwarding ma en odok i kompyuta.

[^13]: En aco ni dong i Ngrok, i kompyuta ma en aco ni Google to GitHub, i Ngrok ki cok ma en aco.