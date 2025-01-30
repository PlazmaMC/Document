---
description: Learn how to create a server with Plazma.
---

# 👟 Getting Started

To use Plazma stably, the system must meet the following requirements:

|               | Minimum | Recommended |
| :-----------: | ------- | ----------- |
|  Architecture | x64     | -           |
|      RAM      | 8GB     | 16GB        |
| Storage Space | 1GB     | 8GB         |
|      JDK      | 17      | 21          |

For smooth configuration file editing, it is also good to install an editor like [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Correct output" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' is not recognized as an internal or external command,
operable program or batch file.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. First, download **JDK 21** in `.msi` format from [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Run the downloaded installation wizard and click `Next`.
3. After activating `Set JAVA_HOME variable` in the menu displayed in the middle left of the window, click `Next`.
4. Press `Install` to complete the JRE installation.
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

Then, install JRE by running the following command in the terminal.

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

## 2. Plazma Download

Plazma provides various types of executable files.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Learn more</summary>

The name of the executable file is determined as `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping type).jar`.

- **Mapping Type**\
  Mapping is a kind of map that connects the actual code of Minecraft with the obfuscated code.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, the vanilla Minecraft mapping. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

You can download the startup script by clicking the bottom left download button.\
**Make sure the downloaded startup script matches your operating system.**

***

## 4. File Organization

Now, move the downloaded startup script and Plazma to a new folder.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Now, run the startup script. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA Agreement

Once you run the startup script, a `eula.txt` file will be generated in the folder.

EULA[^9] is a license agreement that must be agreed upon by using the services of [Mojang Studios](#user-content-fn-10).

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

To agree to the EULA, change `eula=false` to `eula=true` in the `eula.txt` file and save it.

***

## 6. Allow External Connections (Windows)

Modern operating systems block external access by default using **Firewalls** and **Routers** to prevent dangerous access from outside.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| Message                           | Meaning                                            |
| --------------------------------- | -------------------------------------------------- |
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
Windows IP Configuration

Ethernet Adapter Ethernet:

    Connected DNS Suffix. . . . :
    IPv4 Address. . . . . . . . : 192.168.3.7
    Subnet Mask . . . . . . . . : 255.255.255.0
    Default Gateway . . . . . . : 192.168.3.1

```

You can connect to the server from your local machine by attempting to connect to the `192.168.3.7` displayed in the IPv4 address.

If the server and the game are running on the same PC, you can connect using `localhost`.
{% endtab %}
{% endtabs %}

## 7. To develop

If you have successfully started the server and it is running correctly, it is now time to customize the server.

Learn how to customize the server through the following guide.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
