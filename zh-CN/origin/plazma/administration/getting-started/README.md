---
description: 了解如何使用Plazma创建服务器。
---

# 👟 开始

为了稳定地使用Plazma，系统必须满足以下要求。

|      | 最低  | 建议   |
| :--: | --- | ---- |
|  架构  | x64 | -    |
|  RAM | 8GB | 16GB |
| 存储空间 | 1GB | 8GB  |
|  JDK | 17  | 21   |

为了顺利修改配置文件，建议安装像[Visual Studio Code](https://code.visualstudio.com/download)这样的编辑器。

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="正确的输出" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java'不是内部或外部命令，也不是可运行的程序或批处理文件。
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

1. 首先，在[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu)上下载**JDK 21**的`.msi`安装程序。
2. 运行下载的安装向导，点击`下一步`。
3. 在左上角的菜单中激活`Set JAVA_HOME variable`，然后点击`下一步`。
4. 点击`安装`完成JRE安装。
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

然后，运行以下命令以安装JRE。

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

## 2. 下载Plazma

Plazma提供多种形式的可执行文件。

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>了解更多</summary>

执行文件的名称为`plazma-(版本管理器)-1.20.4-R0.1-SNAPSHOT-(映射形式).jar`。

- **映射形式**\
  映射是连接Minecraft实际代码和混淆代码的一种地图。
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang映射，即原始Minecraft映射。 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

通过底部的下载按钮下载启动脚本。\
**请确保下载的启动脚本与您的操作系统相匹配。**

***

## 4. 文件整理

现在将下载的启动脚本和Plazma移动到新文件夹中。

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

现在运行启动脚本。 Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. 同意EULA

运行启动脚本后，文件夹中将生成`eula.txt`。

EULA[^9]是使用[Mojang Studios](#user-content-fn-10)的服务时必须同意的许可协议。

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

要同意EULA，请将`eula.txt`文件中的`eula=false`修改为`eula=true`并保存。

***

## 6. 允许外部访问（Windows）

现代操作系统默认通过**防火墙**和**路由器**阻止外部访问以防止危险访问。

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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
Windows IP配置

以太网适配器 以太网:

    连接的 DNS 后缀. . . . . . . :
    IPv4 地址. . . . . . . . : 192.168.3.7
    子网掩码 . . . . . . . : 255.255.255.0
    默认网关 . . . . . . . : 192.168.3.1

```

尝试使用显示的`192.168.3.7`进行本地连接到服务器。

如果服务器和游戏在同一台PC上运行，则可以使用`localhost`进行连接。
{% endtab %}
{% endtabs %}

## 7。 发展

如果服务器成功启动并正常运行，则现在是个性化服务器的时候了。

请查看以下手册以了解如何个性化服务器。

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
