---
description: 請了解如何使用Plazma創建服務器。
---

# 👟 開始

為了穩定使用Plazma，系統必須滿足以下要求。

|      | 最低  | 建議   |
| :--: | --- | ---- |
|  架構  | x64 | -    |
|  RAM | 8GB | 16GB |
| 儲存空間 | 1GB | 8GB  |
|  JDK | 17  | 21   |

為了方便進行配置文件修改，建議安裝類似[Visual Studio Code](https://code.visualstudio.com/download)的編輯器。

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="正確的輸出" lineNumbers="true" %}

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

1. 首先，從[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu)下載**JDK 21**的`.msi`安裝程序。
2. 運行下載的安裝精靈，然後點擊“下一步”。
3. 在左上角的菜單中啟用`Set JAVA_HOME variable`，然後點擊“下一步”。
4. 點擊“安裝”完成JRE的安裝。
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

然後，執行以下命令以安裝JRE。

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

## 2. 下載Plazma

Plazma提供多種形式的執行文件。

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>了解更多</summary>

執行文件名為`plazma-(版本管理者)-1.20.4-R0.1-SNAPSHOT-(映射形式).jar`。

- **映射形式**\
  映射是將Minecraft的實際代碼與混淆代碼連接起來的一種地圖。
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, 原版Minecraft映射。 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **版本管理者**\
  版本管理者是運行服務器所需的庫和修補服務器文件的啟動器。
  - **Paperclip**\
    由PaperMC團隊為Paper和其他衍生平台開發的管理者，負責下載庫並應用修補到服務器。
  - **Bundler**\
    原始Minecraft版本管理者。

</details>

***

## 3. 創建啟動腳本

要簡單啟動Plazma並自動重新啟動服務器，需要創建[啟動腳本](#user-content-fn-6)[^6]。

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

通過左下角的下載按鈕下載啟動腳本。\
**請確認下載的啟動腳本與您的操作系統相符。**

***

## 4. 整理文件

現在將下載的啟動腳本和Plazma移動到新文件夾中。

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

現在執行啟動腳本。 Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA同意

執行啟動腳本後，文件夾中將生成`eula.txt`。

EULA[^9]是使用Mojang Studios的服務時必須同意的使用權協議。

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

要同意EULA，請將`eula.txt`文件中的`eula=false`修改為`eula=true`，然後保存。

***

## 6. 允許外部訪問（Windows）

現代操作系統通常會阻止外部訪問以防止危險訪問。

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

如果路由器不支持UPnP，則由於每個路由器的面板不同，您需要自行查找信息。

或者可以使用[Ngrok](https://ngrok.com/)生成臨時地址。
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 檢查是否需要端口轉發

輸入以下命令並運行。

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

如果輸出為`True`，則可以結束，否則需要設置端口轉發。

### 6.2 連接到服務器

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

連接到伺服器時使用的地址可以在[這裡](https://ip.pe.kr/)找到。
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

然後重新啟動伺服器，Plazma將自動嘗試進行端口轉發。

以下是根據控制台輸出的消息來判斷UPnP是否成功，控制台將顯示類似`[UPnP]（消息）`的消息。

| 消息           | 意義           |
| ------------ | ------------ |
| `成功打開端口（端口）` | 端口轉發成功。      |
| `端口（端口）已打開`  | 另一服務正在使用該端口。 |
| `無法打開端口（端口）` | 端口轉發失敗。      |
| `服務不可用`      | 路由器不支援UPnP。  |

當伺服器關閉時，Plazma會自動關閉埠。
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. 從[Ngrok官網](https://ngrok.com/download)下載 `Windows (64-bit)` ZIP檔案。
2. 將下載的Ngrok放入伺服器資料夾中。
3. 在[Ngrok儀表板](https://dashboard.ngrok.com/get-started/your-authtoken)上生成[授權令牌](#user-content-fn-13)[^13]。
4. 在伺服器資料夾中執行顯示在下方`Command Line`的命令。
5. 在執行腳本的最上方添加 `start /b ngrok tcp --region jp 25565`，在最底部添加 `taskkill /f /t /im ngrok.exe`。
6. 在控制台頂部顯示的 `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` 中，`0.tcp.jp.ngrok.io:12345`將成為伺服器的地址。
7. 現在您可以通過該地址從外部訪問。
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

例如，當執行命令後，輸出如下：

```log
Windows IP配置

以太网适配器 以太网:

    连接的 DNS 后缀. . . . . . . :
    IPv4 地址. . . . . . . . . : 192.168.3.7
    子网掩码 . . . . . . . . : 255.255.255.0
    默认网关 . . . . . . . . : 192.168.3.1

```

在此，您可以嘗試使用IPv4地址中顯示的 `192.168.3.7` 進行本地伺服器連接。

如果伺服器和遊戲在同一台PC上運行，則可以使用 `localhost` 進行連接。
{% endtab %}
{% endtabs %}

## 7. 發展

如果伺服器成功啟動並正常運行，現在輪到您自定義伺服器了。

请查看以下说明书以了解如何个性化服务器。

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Plazma基於Spigot，而Spigot基於官方伺服器平台。

[^3]: Windows鍵 + R

[^4]: 對於Linux，可以在終端中運行 `java --version`。

[^5]: JRE是一個開源項目，類似Minecraft伺服器平台，有多種類型。

[^6]: 通常被稱為**運行器**。

[^7]: 啟用"自動重新啟動"後，伺服器將自動重新啟動。 您可以輸入`Control + C`來結束。

[^8]: 不建議超過系統的一半。

    例如，如果系統的總記憶體容量為8GB，則不建議設置超過4GB。

[^9]: 最終用戶許可協議，最終使用者授權協議。 請查看[Minecraft官網](https://www.minecraft.net/ko-kr/usage-guidelines)以獲得詳細信息。

[^10]: Microsoft Corporation。

[^11]: 根據韓國遊戲產業促進法第32條第1項第9號，**韓國微軟**可以根據法律提出訴訟。

[^12]: 通用即插即用。 Plazma附帶的Purpur通過這項技術與路由器自動通信，僅在伺服器運行時打開埠，因此無需直接進行埠轉發。

[^13]: 如果沒有帳戶，可以使用Google或GitHub帳戶註冊Ngrok。
