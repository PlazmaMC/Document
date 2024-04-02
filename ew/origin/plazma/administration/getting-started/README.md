---
description: Learn how to create a server with Plazma.
---

# 👟 Getting Started

To use Plazma stably, the system must meet the following requirements:

|               | Minimum | Recommended |
| :-----------: | ------: | ----------: |
|  Architecture |     x64 |           - |
|      RAM      |     8GB |        16GB |
| Storage Space |     1GB |         8GB |
|      JRE      |      17 |          21 |

For smooth configuration file editing, it is also good to install an editor like [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JRE Installation

As the name suggests, Minecraft: **"Java"** Edition is developed in Java, so it requires JRE[^1] to run.

Since Plazma is based on Mojang Studios' official server platform,[^2] you also need to install JRE to use Plazma.

### 1.1 Check for JRE

To check if JRE is installed on your system, type [`cmd /k java --version`](#user-content-fn-4)[^4] in the Run dialog and execute it.

If the output is as follows, proceed to [Step 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

If the output is not like the above, or if it is as follows, then JRE is either not installed or too outdated, so you need to perform [Step 1.2](setup.md#id-1.2).

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

### 1.2 JRE Installation

In this guide, we will use Azul Zulu as one of the types of JREs.

After installation, please redo [step 1.1](setup.md#id-1.1) to ensure that the installation is completed correctly.

{% tabs %}

{% tab title="Windows" %}

1. First, download **JDK 21** in `.msi` format from [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Run the downloaded installation wizard and click `Next`.
3. After activating `Set JAVA_HOME variable` in the menu displayed in the middle left of the window, click `Next`.
4. Press `Install` to complete the JRE installation.

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

Then, install JRE by running the following command in the terminal.

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

## 2. Plazma Download

Plazma provides various types of executable files.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

The following information is for developers or those curious about the characteristics of each type.\
If you are a regular user, you can skip to [step 3](setup.md#id-3) without any issues.

{% endhint %}

<details>

<summary>Learn more</summary>

The name of the executable file is determined as `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping type).jar`.

- **Mapping Type**\
  Mapping is a kind of map that connects the actual code of Minecraft with the obfuscated code.
  - **Reobf**\
    Reobfuscation, also known as Spigot mapping, is commonly used in most NMS plugins.\
    It will be discontinued starting from 1.20.5.
  - **Mojmap**\
    Mojang mapping, the vanilla Minecraft mapping.
- **Version Manager**\
  The version manager can be considered as a launcher for the server, which is necessary for running the server and patching server files.
  - **Paperclip**\
    Developed by the PaperMC team for Paper and other derivative platforms, it downloads libraries and applies patches to the server.
  - **Bundler**\
    The vanilla Minecraft version manager.

</details>

***

## 3. Creating a Startup Script

To easily start Plazma and automatically restart the server, you need to create a [startup script](#user-content-fn-6).

You can create a startup script via [Flags.sh](https://flags.sh). By entering only the [memory to be used by Plazma](#user-content-fn-8), the command will be automatically optimized.

You can download the startup script by clicking the bottom left download button.\
**Make sure the downloaded startup script matches your operating system.**

***

## 4. File Organization

Now, move the downloaded startup script and Plazma to a new folder.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Otherwise, Plazma or JRE may not function properly.

{% endhint %}

Now, run the startup script. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA Agreement

Once you run the startup script, a `eula.txt` file will be generated in the folder.

EULA[^9] is a license agreement that must be agreed upon by using the services of [Mojang Studios](#user-content-fn-10).

If you do not agree to the EULA, you cannot start the server, and violating the EULA may result in penalties such as account suspension. Refer to [sanctions](#user-content-fn-11).

To agree to the EULA, change `eula=false` to `eula=true` in the `eula.txt` file and save it.

***

## 6. Allow External Connections (Windows)

Modern operating systems block external access by default using **Firewalls** and **Routers** to prevent dangerous access from outside.

For Windows, since you allowed it in [step 3](setup.md#id-3), you just need to do port forwarding.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

If the router does not support UPnP, you need to search for information yourself as different routers have different panels.

Alternatively, you can also generate a temporary address using [Ngrok](https://ngrok.com/).
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Check the Need for Port Forwarding

Enter the following in the execution window and run it.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

If the output is `True`, you can finish here, but if it is `False`, you need to set up port forwarding.

### 6.2 Connect to the Server

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

The address to use when connecting to the server can be checked [here](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Then, when you restart the server, Plazma will automatically attempt port forwarding.

The success of UPnP will be based on the message output on the console, which will be displayed as `[UPnP] (message)`.

| Message                           | Meaning                            |
| --------------------------------- | ---------------------------------- |
| `Successfully opened port (port)` | Port forwarding successful.        |
| `Port (port) is already open`     | Another service is using the port. |
| `Failed to open port (port)`      | Port forwarding failed.            |
| `Service is unavailable`          | The router does not support UPnP.  |

When the server is shut down, Plazma automatically closes the port.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Download the `Windows (64-bit)` ZIP file from [Ngrok website](https://ngrok.com/download).
2. Put the downloaded Ngrok into the server folder.
3. Generate an authentication token from [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) as mentioned in [footnote 13](#user-content-fn-13).
4. Run the command displayed in the `Command Line` at the top of the execution script in the server folder.
5. Add `start /b ngrok tcp --region jp 25565` at the top and `taskkill /f /t /im ngrok.exe` at the bottom of the execution script.
6. At the top of the console, the address `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` indicates that `0.tcp.jp.ngrok.io:12345` is the server address.
7. Now you can connect from outside using this address.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

For example, when the following is displayed after running the command,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

You can connect to the server from your local machine by attempting to connect to the `192.168.3.7` displayed in the IPv4 address.

If the server and the game are running on the same PC, you can connect using `localhost`.

{% endtab %}
{% endtabs %}

## 7. Development Stage

If you have successfully started the server and it is running correctly, it is now time to customize the server.

Learn how to customize the server through the guide below.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java execution environment.

[^2]: Paper, based on Plazma, is based on Spigot, which is based on the official server platform.

[^3]: Windows key + R

[^4]: For Linux, use `java --version` in the terminal.

[^5]: JRE is one of the open-source projects, like Minecraft server platforms, there are various types.

[^6]: It is commonly known as a **launcher**.

[^7]: Enabling "Auto-restart" will automatically restart the server. You can exit by entering `Control + C`.

[^8]: It is not recommended to exceed more than half of the system's capacity.

    For example, when the total system memory capacity is 8GB, it is not recommended to set it above 4GB.

[^9]: End-User License Agreement, EULA. For more information, please check the [Minecraft website](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: In the case of South Korea, according to Article 32, Paragraph 1, Item 9 of the Game Industry Promotion Act, legal action can be taken by **Korea Microsoft Corporation**.

[^12]: Universal Plug & Play. Purpur included in Plazma automatically communicates with the router through this technology, so there is no need to directly forward ports as the server only opens ports when it is running.

[^13]: If you do not have an account, sign up for Ngrok using your Google or GitHub account.
