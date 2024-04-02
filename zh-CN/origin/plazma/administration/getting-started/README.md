---
description: 了解如何使用Plazma创建服务器。
---

# 👟 开始

为了稳定地使用Plazma，系统必须满足以下要求。

|      |  最低 |   建议 |
| :--: | --: | ---: |
|  架构  | x64 |    - |
|  RAM | 8GB | 16GB |
| 存储空间 | 1GB |  8GB |
|  JRE |  17 |   21 |

为了顺利修改配置文件，建议安装像[Visual Studio Code](https://code.visualstudio.com/download)这样的编辑器。

***

## 1. 安装JRE

正如其名称所示，Minecraft: **"Java"** Edition是使用Java开发的，运行需要JRE[^1]。

由于Plazma基于Mojang Studios的官方服务器平台[^2]，因此使用Plazma也需要安装JRE。

### 1.1 检查JRE是否已安装

要检查系统中是否已安装JRE，请在[运行窗口](#user-content-fn-3)中输入[`cmd /k java --version`](#user-content-fn-4)并运行。

如果显示如下内容，请跳过到[第2步](setup.md#id-2)。

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

如果没有显示如上内容，或者显示如下内容，则表示没有安装JRE或者太旧，请执行[1.2步骤](setup.md#id-1.2)。

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

### 1.2 安装JRE

本指南将使用Azul Zulu作为JRE的[一种类型](#user-content-fn-5)。

安装完成后，请重新执行[1.1步骤](setup.md#id-1.1)以确保安装正确完成。

{% tabs %}

{% tab title="Windows" %}

1. 首先，在[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu)上下载**JDK 21**的`.msi`安装程序。
2. 运行下载的安装向导，点击`下一步`。
3. 在左上角的菜单中激活`Set JAVA_HOME variable`，然后点击`下一步`。
4. 点击`安装`完成JRE安装。

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

然后，运行以下命令以安装JRE。

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

## 2. 下载Plazma

Plazma提供多种形式的可执行文件。

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

以下内容适用于对开发人员或不同形式的特性感兴趣的人。\
如果是普通用户，则跳过到[第3步](setup.md#id-3)也没有问题。

{% endhint %}

<details>

<summary>了解更多</summary>

执行文件的名称为`plazma-(版本管理器)-1.20.4-R0.1-SNAPSHOT-(映射形式).jar`。

- **映射形式**\
  映射是连接Minecraft实际代码和混淆代码的一种地图。
  - **Reobf**\
    重新混淆，也称为Spigot映射，在大多数NMS插件中使用。\
    从1.20.5开始将停止使用。
  - **Mojmap**\
    Mojang映射，原始Minecraft映射。
- **版本管理器**\
  版本管理器是运行服务器所需的库和修补服务器文件的启动器。
  - **Paperclip**\
    由PaperMC团队为Paper和其他衍生平台开发的管理器，负责下载库并应用补丁到服务器。
  - **Bundler**\
    原始Minecraft版本管理器。

</details>

***

## 3. 创建启动脚本

要简单启动Plazma并自动重新启动服务器，需要创建[启动脚本](#user-content-fn-6)。

您可以通过[Flags.sh](https://flags.sh)创建启动脚本。\
只需输入要用于Plazma的[内存](#user-content-fn-8)，命令将自动优化。

通过底部的下载按钮下载启动脚本。\
**请确保下载的启动脚本与您的操作系统相匹配。**

***

## 4. 文件整理

现在将下载的启动脚本和Plazma移动到新文件夹中。

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

否则，Plazma或JRE可能无法正常工作。

{% endhint %}

现在运行启动脚本。 Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. 同意EULA

运行启动脚本后，文件夹中将生成`eula.txt`。

EULA[^9]是使用[Mojang Studios](#user-content-fn-10)的服务时必须同意的许可协议。

如果不同意EULA，则无法启动服务器，并且违反EULA可能受到处罚，例如暂停帐户等[制裁](#user-content-fn-11)。

要同意EULA，请将`eula.txt`文件中的`eula=false`修改为`eula=true`并保存。

***

## 6. 允许外部访问（Windows）

现代操作系统默认通过**防火墙**和**路由器**阻止外部访问以防止危险访问。

对于Windows，由于在[第3步](setup.md#id-3)中已经允许了防火墙，因此只需进行端口转发。

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

如果路由器不支持UPnP，则由于每个路由器面板不同，您需要自行搜索资料。

或者，您可以通过[Ngrok](https://ngrok.com/)生成临时地址。
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 检查是否需要端口转发

输入以下内容并运行。

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

如果输出为`True`，则可以结束，否则需要设置端口转发。

### 6.2 连接服务器

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

连接服务器时使用的地址可以在[这里](https://ip.pe.kr/)进行确认。

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

然后，重新启动服务器后，Plazma将自动尝试进行端口转发。

以下是根据控制台输出的消息判断UPnP成功与否，控制台将显示`[UPnP] (消息)`。

| 消息            | 含义            |
| ------------- | ------------- |
| `成功打开端口 (端口)` | 端口转发成功。       |
| `端口 (端口)已打开`  | 另一个服务正在使用该端口。 |
| `无法打开端口 (端口)` | 端口转发失败。       |
| `服务不可用`       | 路由器不支持UPnP。   |

服务器关闭后，Plazma会自动关闭端口。

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. 从[Ngrok官网](https://ngrok.com/download)下载`Windows (64-bit)` ZIP文件。
2. 将下载的Ngrok放入服务器文件夹中。
3. 在[Ngrok仪表板](https://dashboard.ngrok.com/get-started/your-authtoken)上生成[授权令牌](#user-content-fn-13)[^13]。
4. 在服务器文件夹中运行显示在下方`Command Line`中的命令。
5. 在执行脚本的顶部添加`start /b ngrok tcp --region jp 25565`，在底部添加`taskkill /f /t /im ngrok.exe`。
6. 在控制台顶部显示的`Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`中，`0.tcp.jp.ngrok.io:12345`将成为服务器地址。
7. 现在可以通过该地址从外部访问。

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

例如，运行命令后，输出如下：

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

尝试使用显示的`192.168.3.7`进行本地连接到服务器。

如果服务器和游戏在同一台PC上运行，则可以使用`localhost`进行连接。

{% endtab %}
{% endtabs %}

## 7。 发展阶段

如果服务器成功启动并正常运行，则现在是个性化服务器的时候了。

通过以下指南了解如何个性化服务器。

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java运行环境，Java执行环境。

[^2]: Plazma基于Paper，而Paper基于Spigot，Spigot基于官方服务器平台。

[^3]: Windows键 + R

[^4]: 对于Linux，请在终端中运行`java --version`。

[^5]: JRE是一个开源项目，类似于Minecraft服务器平台，有多种类型。

[^6]: 通常被称为**运行器**。

[^7]: 启用"自动重启"将导致服务器自动重新启动。 可以使用`Control + C`来结束。

[^8]: 不建议超过系统的一半。

    例如，如果系统总内存容量为8GB，则不建议将其设置为4GB以上。

[^9]: 最终用户许可协议，EULA。 有关详细信息，请查看[Minecraft网站](https://www.minecraft.net/ko-kr/usage-guidelines)。

[^10]: 微软公司。

[^11]: 根据韩国游戏产业促进法第32条第1款第9号，**韩国微软有限公司**可以根据法律提起诉讼。

[^12]: 通用即插即用。 Plazma中包含的Purpur通过此技术自动与路由器通信，在服务器运行时仅打开端口，因此无需直接进行端口转发。

[^13]: 如果没有帐户，请通过Google或GitHub帐户注册Ngrok。
