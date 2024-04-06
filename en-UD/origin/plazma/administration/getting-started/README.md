---
description: ǝpɐǝɯ ǝɹǝɥʍ ɹǝuop ǝɥʇ ǝɥʇ uɐǝq ɯǝɥʇ ǝlɐ
---

# 👟 ʇɹɐʇsɹǝʇ

ǝlɹɐıp ǝɥʇ ǝuıɟǝp uoıʇuıɐɔ ǝɥʇ ǝsɹǝɥʇ ǝɥʇ ʇɐɥʇ ɹǝqɯǝɯɐ ɹǝɥʇɹnɟ ǝɥʇ ǝlǝɥʍ ɹǝɥ

|           | ǝɯɐɹɔ | ʞuıɥɐu |
| :-------: | :---- | :----- |
| ɐɥʇıǝʇɔɹǝ | x64   | -      |
|    ɯɐɯ    | 8GB   | 16GB   |
|  uɐıɹoʇɐu | 1GB   | 8GB    |
|    ɯɹǝ    | 17    | 21     |

ɯoouɥɐu ƃuıʞɐl ɟıɐl ɯıǝɥɔ ǝɥʇɹǝƃuɐɹɐɥɔ ɹo ɹǝʇɟɐs ǝɥʇ ɯı ɹǝɥ

***

## 1. ɯɹǝ ǝsɔɹıɔ

ıɯɹǝɯ ɐu sı ıuɐɯ ǝsɹɐq ǝɥʇıɹɹn ǝu ɐuıɯɹǝɯ ǝʇıɹɹn ǝu ǝɹǝɥ

ɯlɐǝɯ ɯoɹɐıuɐɹ ǝp ʇsǝɹ ɟɐɔɹ ɹnoʎɹǝ ɹo ɹǝʇɟɐs ǝʍ ɹoɟ uǝɥʇ ɯı ɹǝɥ

### 1.1 ɯɹǝ ʎɯɯɹǝɯ

ɯɹǝ ƃuıʇɹǝɯ ǝs ǝsɹɐq ıuıɯɹǝ ıu ıɯ ıu ǝsɹǝɥɔ ɯǝʇɹnǝ ǝɥʇ ʇsǝɹ ǝɥʇ ɹnoʎɹǝ ǝʍ ǝsǝɹǝɥɔ ɯı ǝɹǝɥ

ɐılɐɹʇsnɐ ʇɐɥʇıʍ ɐılɐɹʇsnɐ ɯoɹɟ ɯı ɹoɟ ɯı ɹǝʇɟɐs ıu ɯǝʇɹnǝʇ ǝɥʇ ɹnoʎɹǝ ɯı ɹǝɥ

{% code title="Correct Output" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

ɯıʇ ɐılɐɹʇsnɐ ɐılɐɹʇsnɐ ɯoɹɟ ɯı ɹoɟ ɯı ɹǝʇɟɐs ıu ɯǝʇɹnǝʇ ǝɥʇ ɹnoʎɹǝ ɯı ɹǝɥ

{% code title="JRE Not Installed" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE Too Old" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE 설치

Azul Zulu is used as one of the types of JRE in this guide.

After installation, perform [step 1.1](setup.md#id-1.1) again to ensure that the installation is completed correctly.

{% tabs %}

{% tab title="Windows" %}

1. First, download **JDK 21** from [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) in `.msi` format.
2. Run the downloaded installation wizard and click `Next`.
3. After activating `Set JAVA_HOME variable` in the menu displayed in the middle left of the window, click `Next`.
4. Press `Install` to complete the JRE installation.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) from **JDK 21** download the `.dmg` installation wizard and run to install JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

First, add the Azul Zulu repository to APT by running the following command in the terminal.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Then, install the JRE by running the following command in the terminal.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

You can install JRE by entering the following command.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Download Plazma

Plazma provides various types of executable files.

{% hint style="warning" %}

**In most cases, use `Reobf Paperclip`.**

The following information is for developers or those curious about the characteristics of each type.\
If you are a general user, you can skip to [step 3](setup.md#id-3) without any problems.

{% endhint %}

<details>

<summary>Learn more</summary>

The name of the executable file is determined as `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping type).jar`.

- **Mapping Type**\
  Mapping is a kind of map that connects the actual code of Minecraft with the obfuscated code.
  - **fbœR**\
    Reobfuscated (disaster encryption), also known as Spigot mapping, is used in most NMS plugins.\
    It will be discontinued from 1.20.5 onwards.
  - **pɯɾɯɯ**\
    Mojang-mapped, vanilla Minecraft mapping.
- **Version Manager**\
  The version manager can be considered as a launcher for the server that provides libraries necessary for server operation and patches server files.
  - **Paperclip**\
    Developed by the PaperMC team for Paper and other derivative platforms, it downloads libraries and applies patches to the server.
  - **Bundler**\
    Version manager for vanilla Minecraft.

</details>

***

## 3. Create a Startup Script

To easily start Plazma and automatically restart the server, you need to create a [startup script](#user-content-fn-6).

sɥʇɹᴉq ɹǝʇɐɯᴉuɐɹʇɹǝɯ ǝɥʇ puɐ sᴉɥʇɹɐǝɥ ɟo [Flags.sh](https://flags.sh) ɹnoɟ ǝɥʇ ǝɹoɯ [sǝɹǝɥʇuᴉ](#user-content-fn-7)[^7]ɥʇ sᴉɥʇ ǝɥʇ ɹǝʇɐɯᴉuɐɹʇɹǝɯ ǝɥʇ puɐ ɯɹǝɥ ǝɥʇ ǝɹoɯ ǝʇᴉɹɹǝɯɐ ɯnɹʇɐɥɐɹɐɯ oʇɥǝɹ

You can download the startup script by clicking the download button at the bottom left.\
**Make sure the downloaded startup script matches your operating system.**

***

## 4. File Organization

Now move the downloaded startup script and Plazma to a new folder.

{% hint style="warning" %}

**The folder name must not contain spaces and must be set in English.**

Otherwise, Plazma or JRE may not work correctly.

{% endhint %}

Now run the startup script. For Windows, <mark style="background-color:orange;">In the firewall allow selection window, be sure to choose **Allow**</mark>.

***

## 5. EULA Agreement

Once you run the startup script, a `eula.txt` file will be created in the folder.

EULA[^9] is a license agreement that you must agree to by using the services of [Mojang Studios](#user-content-fn-10).

{% hint style="warning" %}

ɯɐuᴉl ɹǝɥʇɐɯ ǝɥʇ ǝɹoɯɐ ǝɥʇ ɹǝʌǝu, sǝɹǝɥʇuᴉ ɹnoɟ ɹǝʇɐɯᴉuɐɹʇɹǝɯ ǝɥʇ ɹǝʍ ǝuᴉɐɔ ǝɥʇ ǝɥʇ ǝɹoɯ ǝʇᴉɹɹǝɯɐ ǝɥʇ ɹǝʇɐɯᴉuɐɹʇɹǝɯ ǝɥʇ ɹǝʌǝu, ɹǝʇɐɯᴉuɐɹʇɹǝɯ ɹnoɟ ǝɥʇ ɹǝʇɐɯᴉuɐɹʇɹǝɯ ǝɥʇ ɹǝʍ ǝuᴉɐɔ ǝɥʇ ɹǝʍ ǝuᴉɐɔ ǝɥʇ ɹǝʍ ǝuᴉɐɔ ǝɥʇ ɹǝʍ ǝuᴉɐɔ ɹnoɟ ǝɥʇ ɹǝʍ ǝuᴉɐɔ ɹnoɟ ǝɥʇ ɹǝʍ ǝuᴉɐɔ ɹnoɟ ɹǝʌǝu

{% endhint %}

To agree to the EULA, change `eula=false` in the `eula.txt` file to `eula=true` and save it.

***

## 6. Allow External Connections (Windows)

Modern operating systems block external access by default to prevent dangerous access from outside using **Firewall** and **Router**.

For Windows, since you allowed it in [step 3](setup.md#id-3), you just need to do port forwarding.

{% hint style="info" %}

**This guide assumes the use of Windows operating system and [UPnP](#user-content-fn-12)[^12]-enabled router.**

If the router does not support UPnP, you need to search for information as each router panel is different.

Alternatively, you can also generate a temporary address using [Ngrok](https://ngrok.com/).
{% endhint %}

{% hint style="warning" %}

**For Linux or macOS, and other (semi-) UNIX-based operating systems, firewall configuration methods vary by service, so you should search for information directly.**

{% endhint %}

### 6.1 Check the Need for Port Forwarding

Enter the following in the execution window and run it.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

If the output is `True`, you can finish here, but if it's `False`, you need to set up port forwarding.

### 6.2 Connect to the Server

{% tabs %}

{% tab title="Access from External" %}

If port forwarding is not needed or if port forwarding has already been successful, you can now connect to the server.

The address used to connect to the server can be checked [here](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

Activate `network.upnp-port-forwarding` to `true` in `purpur.yml` in the server folder.

Then, when you restart the server, Plazma will automatically attempt port forwarding.

The success of UPnP depends on the message displayed in the console, which will be shown as `[UPnP] (message)` in the console.

| Message                           | Meaning                                            |
| --------------------------------- | -------------------------------------------------- |
| `Successfully opened port (port)` | Port forwarding successful.        |
| `Port (port) is already open`     | Another service is using the port. |
| `Failed to open port (port)`      | Port forwarding failed.            |
| `Service is unavailable`          | Router does not support UPnP.      |

Plazma will automatically close the port when the server is shut down.

{% endtab %}

{% tab title="Create a temporary address with Ngrok" %}

Using Ngrok is useful for short-term testing, collaborative play, or playing with friends.

1. Download the `Windows (64-bit)` ZIP file from [Ngrok website](https://ngrok.com/download).
2. Put the downloaded Ngrok in the server folder.
3. Generate an authentication token from the [Ngrok dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) ([see details](#user-content-fn-13)).
4. Run the command displayed in the `Command Line` at the top of the server folder.
5. Add `start /b ngrok tcp --region jp 25565` at the top of the execution script, and `taskkill /f /t /im ngrok.exe` at the bottom.
6. sɹǝɥʇɐu ɹnoʎɹǝʇɐɯǝ ʇɹɐɯɹǝɥ `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` ǝsǝɥʇ, `0.tcp.jp.ngrok.io:12345` ɹǝp ǝsɹǝɥ ǝɹɐɔs ǝɥʇɐǝɹɔ sᴉɥʇɹǝɥɔ.
7. sǝʇǝɹɔ ǝɥʇ ɥʇɹɐǝ ɹǝl ʇɹɐɯ ɹǝʇɐɯ ǝsɹǝɥ ɹnoʎɹǝʇɐɯᴉ.

{% endtab %}

{% tab title="Access from local" %}

When trying to connect to the server from local, you can connect using the `IPv4 address` output from running `cmd /k ipconfig` in the command prompt.

ǝʎɐsᴉu ǝlǝɯǝ, ǝuǝɯɔ ɥǝ ɹǝʇɐɯɹǝɥ ǝɹɐɔs ɥɔɹǝ,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

ʎǝɹᴉsǝ ɹǝʇɐɯɹǝɥ IPv4 sǝɔǝsǝɥ `7.3.846.291`o ɹǝʇɐɯ ǝsɹǝɥ ǝɹɐɔs ɹnoʎɹǝʇɐɯᴉ.

sǝɹʇǝɥɔ ɯɐ ǥǝɯᴉɯǝɹ ɔɐuɯǝɹɹɐɔ ǝsɹǝɥ ǝɹɐɔs, `ʇɹɐɯɯǝsɥʇ`o ɹǝʇɐɯɹǝɥ ɯɐ ǝɹɐɔs ɹnoʎɹǝʇɐɯᴉ.

{% endtab %}
{% endtabs %}

## 7. ɯɐlǝuᴉɹǝl

ɹǝɹʇǝɥɔɐ ǝsɹǝɥɥɔsɐɯǝ ʇɹɐɯɹǝɥɔ ɹɐ uǝsɹǝɥɥɔ ɹnoʎɹǝʇɐɯᴉ, ǝᴉɹǝ sɹǝɥɔɹǝ sᴉɥʇɹǝɥɔɹ ɥɐɯ ɔɐɹɐᴉᴚ.

ɐuɹǝ ƃnɐᴉpǝ ʇo ɹǝsɹǝɥɥɔs ǝɯɐɥɔ ǝɹɐ ɯɐ ɹǝsɹǝɥɥɔs ɹnoʎɹǝʇɐɯᴉ.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: ɐɹɐᴉ ɯɐuɯǝs ǝɯɐɥɔǝɹɐᴉ, ɐɹɐᴉ ǝxǝɯǝɹᴉu ɥɔɹǝɹǝɯ.

[^2]: ƃuɹɐɯᴉɐǝ ɹnoʎɹǝʇɐɯ Plazma ɯıɔuɐɯ Spigotǝ ɯıɔuɐɯ ɥɐɯᴉɹǝ, Spigot ıɥ ƃuɹɐɯᴉq ɹɐ ɯıɔuɐɯ ɹnoʎɹǝʇɐɯᴉ.

[^3]: sɯǝɹɹǝu ı + R

[^4]: niɯuıɯ ǝɯɐɹɐ `ɐɯᴉɐ --ɯǝɹsıou`

[^5]: ɥɹǝ ǝuɯǝɹ ɟǝɯǝɹǝɥɔ ɯɐ, Minecraft ɹɐsǝɹ ƃuɹɐɯᴉq ɔɐuɯ ƃuıɐɯ ɐǝɥɔ ɐuɹǝ ɯɐ ɯɐuɯǝs ǝɹɐᴉɹǝɥɔ ǝɹɐɔs ɹnoʎɹǝʇɐɯᴉ.

[^6]: ˙˙˙ɹnoʎɹǝʇɐɯǝ ɯɐɥɔǝu ɯıɔuɐɯ

[^7]: "ʇɹɐɯo-ɹǝsʇɐɥʇ" ɥɐısɹǝʇɐɯɹǝɥ ɥɐɯǝs ɹɐ ɯɐuɯǝs ɹɐɥɔɐɯ ɯɐᴉsɹǝɥɥɔ ɯɐɥɔɹǝs. `ɔɐuɹɔɔǝɹ + ɔ`ɯn ıuɐɥɹou ɥɐısɹǝʇɐɯɹǝɥ ɯɐǝɹɔɹǝs.

[^8]: sᴉsʇɥʇǝɯǝɥ ǝsɹǝɥ ǝɹɐ ɯɐɥɔɹǝs ıuɐɹɐɯɹǝɥɥɔs ǝɯɐɥɔ ǝɹɐ ƃuıɹɐɯɯǝɥɔ ɯɐ ɹnoʎɹǝʇɐɯᴉ.

    .다권인 을는거그 로떼로 8GB 이리용리모 메쳐 전스템, 러했 고라 4GB, 때을했 로고 는는권불권권권권 설정하는것은 권장되지 않습니다.

[^9]: .계약권 사용자 사용자 사용자 사용자 최종, Agreement License User-End. .주세요홈페이지 사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자사용자, [Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines) details Check out.

[^10]: .Corporation Microsoft.

[^11]: .할 수 있습니다고소법적에서주식회사 마이크로스프트 한국\*\*에따라호제1항제9호1조32제법률 관한 게임산업진흥에 경우민국한대, \*\*.

[^12]: .Play & Plug Universal. .다수 더 나은 역할이 열을 포트만 때기 위해 실행 중일 때만 서버가 통신과 라우터로 자동으로 이 기술을 통해 Purpur가 포함된 Plazma에

[^13]: 합니다.가입합니다 Ngrok에 통해 계정을 GitHub 또는 Google 경우 없는 계정이.
