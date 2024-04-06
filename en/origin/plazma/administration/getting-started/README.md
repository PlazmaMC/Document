---
description: Learn how to create a server with Plazma.
---

# 👟 Getting Started

To use Plazma reliably, the system must meet the following requirements.

|               | Minimum | Recommended |
| :-----------: | :------ | :---------- |
|  Architecture | x64     | -           |
|      RAM      | 8GB     | 16GB        |
| Storage space | 1GB     | 8GB         |
|      JRE      | 17      | 21          |

For smooth configuration file editing, it is also recommended to install an editor such as [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE Installation

As the name suggests, Minecraft: "Java" Edition is developed in Java, so it requires JRE[^1] to run.

Since Plazma is based on Mojang Studios' official server platform[^2], JRE must be installed to use Plazma.

### 1.1 Check for JRE

To check if JRE is installed on the system, type [`cmd /k java --version`](#user-content-fn-4)[^4] in the Run window and run it.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Correct Output" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE Not Installed" lineNumbers="true" %}

```log
'java' is not recognized as an internal or external command,
operable program or batch file.
```

{% endcode %}

{% code title="JRE Too Old" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE Installation

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. First, download **JDK 21** in `.msi` format from [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Run the downloaded installer and click `Next`.
3. After activating `Set JAVA_HOME variable` from the menu displayed in the center left of the window, click `Next`.
4. Click `Install` to complete the JRE installation.

{% endtab %}

{% tab title="macOS" %}

Download the **JDK 21** in `.dmg` format from [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) and run the installation wizard to install JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

First, run the following command in the terminal to add Azul Zulu repository to APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Then, install JRE by running the following command in the terminal.

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

## 2. Plazma Download

Plazma offers various forms of executable files.

{% hint style="warning" %}

**In most cases, use `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Learn More</summary>

The executable file is named `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping type).jar`.

- **Mapping Type**\
  Mapping is a kind of map that connects Minecraft's actual code with obfuscated code.
  - **Reobf**\
    Reobfuscated, also known as Spigot mapping, is used in most NMS plugins.\
    It will be discontinued starting from 1.20.5.
  - **Mojmap**\
    Mojang-mapped, vanilla Minecraft mapping.
- **Version Manager**\
  The version manager can be considered as the launcher of the server, which is necessary for running the server and patching server files.
  - **Paperclip**\
    Developed by the PaperMC team for Paper and other derivative platforms, it downloads libraries and applies patches to the server.
  - **Bundler**\
    The vanilla Minecraft version manager.

</details>

***

## 3. Creating a Start Script

To easily start Plazma and automatically restart the server, you need to create a [start script](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh) allows you to generate a startup script by entering only the [memory to use](#user-content-fn-8)[^8] in Plazma, the command will be automatically optimized.

You can download the start script by clicking the bottom left download button.\
**Make sure the downloaded start script matches your operating system.**

***

## 4. File Cleanup

Now move the downloaded start script and Plazma to a new folder.

{% hint style="warning" %}

**The folder name must not contain spaces and must be in English.**

Otherwise, Plazma or JRE may not function correctly.

{% endhint %}

Now run the start script. For Windows, <mark style="background-color:orange;">in the firewall permission prompt, make sure to select **Allow**</mark>.

***

## 5. EULA Agreement

Once you run the start script, an `eula.txt` file will be generated in the folder.

EULA[^9] is a license agreement that you must agree to by using the services of [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

If you do not agree, you cannot start the server, and if you violate the EULA, you may receive [sanctions](#user-content-fn-11)[^11] such as account suspension.

{% endhint %}

To agree to the EULA, change `eula=false` to `eula=true` in the `eula.txt` file and save it.

***

## 6. Allow External Connections (Windows)

Modern operating systems block external access by default to prevent unauthorized access from outside using **firewalls** and **routers**.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

If your router does not support UPnP, you will need to search for information as panel layouts vary by router.

Alternatively, you can use [Ngrok](https://ngrok.com/) to generate a temporary address.
{% endhint %}

{% hint style="warning" %}

**For Linux or macOS (Unix-like) operating systems, firewall configuration methods vary by service, so you need to search for information directly.**

{% endhint %}

### 6.1 Check the Need for Port Forwarding

Enter the following in the Run window and run it.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

If the output is `True`, you can stop here, but if it is `False`, you need to set up port forwarding.

### 6.2 Connect to the Server

{% tabs %}

{% tab title="Accessing from External" %}

If port forwarding is not needed or has already been successfully set up, you can now connect to the server.

The address used to connect to the server can be checked [here](https://ip.pe.kr/)

{% endtab %}

{% tab title="Attempting port forwarding with UPnP" %}

In the `purpur.yml` of the server folder, enable `network.upnp-port-forwarding` to `true`.

Then, when you restart the server, Plazma will automatically attempt port forwarding.

Below is the indication of UPnP success based on the message output to the console, which will be displayed as `[UPnP] (message)` in the console.

| Message                           | Meaning                                                       |
| --------------------------------- | ------------------------------------------------------------- |
| `Successfully opened port (port)` | Port forwarding successful.                   |
| `Port (port) is already open`     | Another service is currently using that port. |
| `Failed to open port (port)`      | Port forwarding failed.                       |
| `Service is unavailable`          | The router does not support UPnP.             |

When the server shuts down, Plazma automatically closes the port.

{% endtab %}

{% tab title="Creating temporary address with Ngrok" %}

Using Ngrok is useful for short-term testing, collaborative play, or playing with friends.

1. Download the `Windows (64-bit)` ZIP file from [Ngrok website](https://ngrok.com/download).
2. Put the downloaded Ngrok into the server folder.
3. Generate an authentication token at [Ngrok dashboard](https://dashboard.ngrok.com/get-started/your-authtoken)[^13].
4. Execute the command displayed in the `Command Line` in the server folder.
5. Add `start /b ngrok tcp --region jp 25565` at the top of the execution script, and `taskkill /f /t /im ngrok.exe` at the bottom.
6. In the console, the address `0.tcp.jp.ngrok.io:12345` shown at the top will be the server's address.
7. Now you can connect from external sources using this address.

{% endtab %}

{% tab title="Connecting from local" %}

If you are trying to connect to the server from local, you can connect using the `IPv4 address` output from running `cmd /k ipconfig` in the command prompt.

For example, if the output displays as follows after executing the command,

```log
Windows IP Configuration

Ethernet Adapter Ethernet:

    Connected DNS Suffix. . . . :
    IPv4 Address. . . . . . . . : 192.168.3.7
    Subnet Mask . . . . . . . . : 255.255.255.0
    Default Gateway . . . . . . : 192.168.3.1

```

When attempting to connect to the server locally, you can connect using the `192.168.3.7` displayed in the IPv4 address here.

If the server and the game are running on the same PC, you can connect using `localhost`.

{% endtab %}
{% endtabs %}

## 7. Grow

If the server starts successfully and is operating correctly, it is time to customize the server.

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java Execution Environment.

[^2]: Paper, the foundation of Plazma, is based on Spigot, which is based on the official server platform.

[^3]: Windows key + R

[^4]: For Linux, use `java --version` in the terminal.

[^5]: JRE is one of the open-source projects, similar to Minecraft server platforms.

[^6]: Generally known as **launcher**.

[^7]: Enabling "Auto-restart" will automatically restart the server. You can exit by entering `Control + C`.

[^8]: It is not recommended to exceed more than half of the system.

    For example, if the total system memory capacity is 8GB, it is not recommended to set it above 4GB.

[^9]: End-User License Agreement, EULA. Please refer to [Minecraft website](https://www.minecraft.net/ko-kr/usage-guidelines) for more details.

[^10]: Microsoft Corporation.

[^11]: In South Korea, according to Article 32, Paragraph 1, Item 9 of the Act on the Promotion of the Game Industry, legal action can be taken by **Korean Microsoft Corporation**.

[^12]: Universal Plug & Play. Purpur included in Plazma communicates with the router automatically through this technology to open ports only when the server is running, eliminating the need to manually port forward.

[^13]: If you do not have an account, sign up for Ngrok using your Google or GitHub account.
