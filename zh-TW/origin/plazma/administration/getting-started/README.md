---
description: 請了解如何使用Plazma創建服務器。
---

# 👟 開始

為了穩定使用Plazma，系統必須滿足以下要求。

|      |  最低 |   建議 |
| :--: | --: | ---: |
|  架構  | x64 |    - |
|  RAM | 8GB | 16GB |
| 儲存空間 | 1GB |  8GB |
|  JRE |  17 |   21 |

為了方便進行配置文件修改，建議安裝類似[Visual Studio Code](https://code.visualstudio.com/download)的編輯器。

***

## 1. 安裝JRE

正如名稱所示，Minecraft: **"Java"** Edition是使用Java開發的，為了運行，需要JRE[^1]。

由於Plazma是基於Mojang Studios的官方服務器平台[^2]，要使用Plazma也需要安裝JRE。

### 1.1 確認JRE是否已安裝

要檢查系統是否已安裝JRE，請在\[執行]視窗中輸入[`cmd /k java --version`](#user-content-fn-4)[^4]並運行。

如果輸出如下，請跳至[第2步](setup.md#id-2)。

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

如果輸出不符合上述要求，或者如下所示，則表示JRE不存在或者太舊，需要執行[1.2步驟](setup.md#id-1.2)。

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

### 1.2 安裝JRE

本指南將使用Azul Zulu作為JRE的一種[類型](#user-content-fn-5)[^5]。

安裝完成後，請重新執行[1.1步驟](setup.md#id-1.1)以確認安裝是否成功。

{% tabs %}

{% tab title="Windows" %}

1. 首先，從[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu)下載**JDK 21**的`.msi`安裝程序。
2. 運行下載的安裝精靈，然後點擊“下一步”。
3. 在左上角的菜單中啟用`Set JAVA_HOME variable`，然後點擊“下一步”。
4. 點擊“安裝”完成JRE的安裝。

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

然後，執行以下命令以安裝JRE。

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

## 2. 下載Plazma

Plazma提供多種形式的執行文件。

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

以下內容供開發人員或對各種形式感興趣的人參考。\
如果是一般用戶，可以跳過到[第3步](setup.md#id-3)。

{% endhint %}

<details>

<summary>了解更多</summary>

執行文件名為`plazma-(版本管理者)-1.20.4-R0.1-SNAPSHOT-(映射形式).jar`。

- **映射形式**\
  映射是將Minecraft的實際代碼與混淆代碼連接起來的一種地圖。
  - **Reobf**\
    重新混淆，也稱為Spigot映射，在大多數NMS插件中使用。\
    從1.20.5開始將停止使用。
  - **Mojmap**\
    Mojang映射，原始Minecraft映射。
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

可以透過[Flags.sh](https://flags.sh)來生成啟動腳本。\
只需輸入要用於Plazma的[記憶體](#user-content-fn-8)[^8]，命令將自動優化。

通過左下角的下載按鈕下載啟動腳本。\
**請確認下載的啟動腳本與您的操作系統相符。**

***

## 4. 整理文件

現在將下載的啟動腳本和Plazma移動到新文件夾中。

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

否則，Plazma或JRE可能無法正常運作。

{% endhint %}

現在執行啟動腳本。 Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA同意

執行啟動腳本後，文件夾中將生成`eula.txt`。

EULA[^9]是使用Mojang Studios的服務時必須同意的使用權協議。

如果不同意EULA，將無法啟動服務器，並且違反EULA可能導致帳戶被凍結等[懲罰](#user-content-fn-11)[^11]。

要同意EULA，請將`eula.txt`文件中的`eula=false`修改為`eula=true`，然後保存。

***

## 6. 允許外部訪問（Windows）

現代操作系統通常會阻止外部訪問以防止危險訪問。

對於Windows，由於在[第3步](setup.md#id-3)中已經允許防火牆，因此僅需進行端口轉發。

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

在此，您可以嘗試使用IPv4地址中顯示的 `192.168.3.7` 進行本地伺服器連接。

如果伺服器和遊戲在同一台PC上運行，則可以使用 `localhost` 進行連接。

{% endtab %}
{% endtabs %}

## 7. 進階階段

如果伺服器成功啟動並正常運行，現在輪到您自定義伺服器了。

通過以下指南了解如何自定義伺服器。

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java執行環境，Java執行環境。

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
