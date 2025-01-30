---
description: Discover how to make a server with Plazma.
---

# 👟 Gettin' Started

To use Plazma reliably, yer system must meet the followin' requirements.

|               | Minimum | Recommended |
| :-----------: | ------: | ----------: |
|  Architecture |     x64 |           - |
|      RAM      |     8GB |        16GB |
| Storage Space |     1GB |         8GB |
|      JRE      |      17 |          21 |

For smooth configuration file edits, it be good to install an editor like [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE Installation

As the name suggests, Minecraft: **"Java"** Edition be developed in Java, so ye need JRE[^1] to run it.

Plazma be based on Mojang Studios' official server platform, so ye also need to install JRE to use Plazma.

### 1.1 Checkin' for JRE

To check if JRE be installed on yer system, type [`cmd /k java --version`](#user-content-fn-4) in the Run window and run it.

If it be outputtin' like this, skip to [Step 2](setup.md#id-2).

{% code title="Correct Output" overflow="wrap" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

If it don't output like that, or if it be like this, then JRE be either not there or too old, so ye need to do [Step 1.2](setup.md#id-1.2).

{% code title="JRE not installed" overflow="wrap" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE bein' too ol'" overflow="wrap" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE Install

In this guide, we be usin' Azul Zulu as [one o' the types](#user-content-fn-5)[^5] o' JRE.

After ye be finishin' the install, run [step 1.1](setup.md#id-1.1) again t' make sure the install be completed correctly.

{% tabs %}
{% tab title="Windows" %}

1. First off, download **JDK 21** from [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) in `.msi` format.
2. Run the downloaded install wizard and click `Next`.
3. After activatin' `Set JAVA_HOME variable` in the menu displayed in the center-left o' the window, click `Next`.
4. Press `Install` t' complete the JRE install.
   {% endtab %}

{% tab title="macOS" %}
Download **JDK 21** in `.dmg` format from [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) and run the install wizard t' install JRE.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
First off, run the followin' command in the terminal t' add Azul Zulu repository t' APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Then, run the followin' command in the terminal t' install JRE.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}
Ye can install JRE by enterin' the followin' command.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma Download

Plazma offers various types o' executable files.

{% hint style="warning" %}

### In most cases, ye be usin' `Reobf Paperclip`.

The followin' be fer developers or those curious about the characteristics o' each type.\
If ye be a regular user, ye can skip t' [step 3](setup.md#id-3) without any issues.
{% endhint %}

<details>

<summary>Learn More</summary>

The name o' the executable file be `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mappin' type).jar`.

- **Mappin' Type**\
  Mappin' be a kind o' map that connects Minecraft's actual code with the obfuscated code.
  - **Reobf**\
    Reobfuscation, also known as Spigot mappin', be used in most NMS plugins.\
    It be scheduled t' be discontinued from 1.20.5 onwards.
  - **Mojmap**\
    Mojang mappin', the vanilla Minecraft mappin'.
- **Version Manager**\
  The version manager be a launcher necessary fer server operation, patchin' server files, and libraries.
  - **Paperclip**\
    Developed by the PaperMC team fer Paper and other derivative platforms, it downloads libraries and applies patches t' the server.
  - **Bundler**\
    The vanilla Minecraft version manager.

</details>

***

## 3. Start Script Creation

T' easily start Plazma and automatically restart the server, ye need t' create a [start script](#user-content-fn-6)[^6].

Ye can create the start script via [Flags.sh](https://flags.sh).\
Just enter the memory ye want t' use fer Plazma, and the command will be automatically optimized.

Ye can download the start script by clickin' the download button at the bottom left.\
**Make sure the downloaded start script matches yer operatin' system.**

***

## 4. File Organization

Now, move the downloaded start script and Plazma t' a new folder.

{% hint style="warning" %}

### The folder name must have no spaces and be set in English.

Otherwise, Plazma or JRE may not function correctly.
{% endhint %}

Now, run the start script. For Windows, <mark style="background-color:orange;">ye must</mark> select <mark style="background-color:orange;">**Allow**</mark> in the firewall permission prompt.

***

## 5. EULA Agreement

Once ye run the start script, a `eula.txt` file will be created in the folder.

The EULA[^9] be a license agreement ye must agree t' by usin' the services o' [Mojang Studios](#user-content-fn-10)[^10].

If ye do not agree t' the EULA, ye cannot start the server and may face sanctions such as account suspension fer violatin' the EULA.

T' agree t' the EULA, change `eula=false` in the `eula.txt` file t' `eula=true` and save it.

***

## 6. Allow External Connections (Windows)

Modern operatin' systems block external access by default t' prevent risky access from outside via the **firewall** and **router**.

Since ye allowed the firewall in [step 3](setup.md#id-3) fer Windows, ye just need t' do port forwardin'.

{% hint style="info" %}

### This guide assumes it be written fer Windows operatin' system and a router capable o' usin' [**UPnP**](#user-content-fn-12)[^12].

If yer router does not support UPnP, ye must search fer the specific panel fer each router, as they vary.

Alternatively, ye can use [Ngrok](https://ngrok.com/) t' generate a temporary address.
{% endhint %}

{% hint style="warning" %}

### Fer Linux or macOS, and other (semi-) UNIX-based operatin' systems, the method fer settin' up the firewall service varies, so ye must search fer the specific information.

{% endhint %}

### 6.1 Checkin' the Need fer Port Forwardin'

Enter the followin' in the run window and execute it.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

If the output be `True`, ye be good t' go, but if it be `False`, ye need t' set up port forwardin'.

### 6.2 Connectin' t' the Server

{% tabs %}
{% tab title="External Connection" %}
If port forwardin' be not needed or ye have already successfully set up port forwardin', ye can now connect t' the server.

The address t' connect t' the server can be found [here](https://ip.pe.kr/).
{% endtab %}

{% tab title="Attemptin' UPnP Port Forwardin'" %}
In the `purpur.yml` file in the server folder, enable `network.upnp-port-forwarding` t' `true`.

Then, after restartin' the server, Plazma will automatically attempt port forwardin'.

The success o' UPnP will be determined by the message output t' the console, which will be displayed as `[UPnP] (message)`.

| Message                           | Meanin'                             |
| --------------------------------- | ----------------------------------- |
| `Successfully opened port (port)` | Port forwardin' successful.         |
| `Port (port) is already open`     | Another service be usin' that port. |
| `Failed t' open port (port)`      | Port forwardin' failed.             |
| `Service be unavailable`          | The router does not support UPnP.   |

When the server shuts down, Plazma will automatically close the port.
{% endtab %}

{% tab title="Generatin' a Temporary Address with Ngrok" %}
Usin' Ngrok be useful fer short-term tests, collaborative play, or playin' with friends.

1. Download the `Windows (64-bit)` ZIP file from the [Ngrok website](https://ngrok.com/download).
2. Place the downloaded Ngrok in the server folder.
3. Generate an authentication token from the [Ngrok dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Run the command displayed in the `Command Line` section in the server folder.
5. Add `start /b ngrok tcp --region jp 25565` at the top o' the run script, and `taskkill /f /t /im ngrok.exe` at the bottom.
6. At the tippity top o' th' console be showin' `Forwardin' tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`, 'n `0.tcp.jp.ngrok.io:12345` becometh th' server's address.
7. Ye can now connect through that address from th' outside.
   {% endtab %}

{% tab title="Connectin' from Local" %}
If ye be tryin' t' connect t' th' server from yer local machine, ye can use th' `IPv4 Address` that be shown when runnin' `cmd /k ipconfig` in th' command prompt.

For example, if 'tis shown as follows after runnin' th' command,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Ye can connect t' th' server from yer local machine by attemptin' t' connect t' th' `192.168.3.7` shown in th' IPv4 address.

If th' server 'n th' game be runnin' on th' same PC, ye can connect usin' `localhost`.
{% endtab %}
{% endtabs %}

## 7. Evolution Stage

Once ye have successfully started th' server 'n 'tis runnin' properly, 'tis time t' customize th' server.

Learn how t' customize th' server through th' guide below.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java Execution Environment.

[^2]: Plazma's foundation Paper be based on Spigot, 'n Spigot be based on th' official server platform.

[^3]: Pressin' Windows key + R

[^4]: For Linux, in th' terminal type `java --version`

[^5]: JRE be one o' th' open-source projects, like Minecraft server platforms, there be various types.

[^6]: Usually known as a **launcher**.

[^7]: If ye enable "Auto-restart", th' server will restart automatically. Ye can end by pressin' `Control + C`.

[^8]: It be not advisable t' exceed more than half o' th' system's capacity.

    For instance, if ye be havin' a total system memory capacity o' 8GB, settin' it above 4GB be not bein' recommended.

[^9]: End-User License Agreement, Final User Use Covenant. For more details, check out [Minecraft website](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: In the case o' South Korea, under the Game Industry Promotion Act Article 32, Paragraph 1, Item 9, **Korea Microsoft Corporation** bein' able to pursue legal action.

[^12]: Universal Plug & Play. Plazma in Purpur be communicatin' automatically with the router through this technology, so there be no need to be doin' port forwardin' directly when the server be runnin', the port be openin' only when the server be runnin'.

[^13]: If ye don't have an account, sign up for Ngrok with yer Google or GitHub account.
