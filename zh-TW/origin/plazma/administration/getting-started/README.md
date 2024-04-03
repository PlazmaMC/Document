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

{% code title="正確的輸出" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

如果輸出不符合上述要求，或者如下所示，則表示JRE不存在或者太舊，需要執行[1.2步驟](setup.md#id-1.2)。

{% code title="未安裝JRE" lineNumbers="true" %}

```log
'java'不是内部或外部命令，也不是可运行的程序或批处理文件。
```

{% endcode %}

{% code title="JRE過時" lineNumbers="true" %}

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

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) 從 **JDK 21**的`.dmg`形式安裝精靈下載並運行以安裝JRE。

{% endtab %}

{% tab title="Debian/Ubuntu" %}

首先，執行以下命令在終端中添加Azul Zulu存儲庫到APT。

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

可以輸入以下命令來安裝JRE。

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

**在大多數情況下，使用`Reobf Paperclip`。**

以下內容供開發人員或對各種形式感興趣的人參考。\
如果是一般用戶，可以跳過到[第3步](setup.md#id-3)。

{% endhint %}

<details>

<summary>了解更多</summary>

執行文件名為`plazma-(版本管理者)-1.20.4-R0.1-SNAPSHOT-(映射形式).jar`。

- **映射形式**\
  映射是將Minecraft的實際代碼與混淆代碼連接起來的一種地圖。
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.5부터 사용이 종료될 예정입니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다.
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

**文件夾名稱必須沒有空格，並且必須用英文設置。**

否則，Plazma或JRE可能無法正常運作。

{% endhint %}

現在執行啟動腳本。 對於Windows，<mark style="background-color:orange;">在防火牆允許選擇對話框中，必須選擇**允許**</mark>。

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

**本指南假設您使用Windows操作系統和可以使用UPnP的路由器。**

如果路由器不支持UPnP，則由於每個路由器的面板不同，您需要自行查找信息。

或者可以使用[Ngrok](https://ngrok.com/)生成臨時地址。
{% endhint %}

{% hint style="warning" %}

**對於Linux或macOS等(準)UNIX系統操作系統，由於每個防火牆服務的設置方法都不同，因此您需要自行搜索資料。**

{% endhint %}

### 6.1 檢查是否需要端口轉發

輸入以下命令並運行。

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

如果輸出為`True`，則可以結束，否則需要設置端口轉發。

### 6.2 連接到服務器

{% tabs %}

{% tab title="外部訪問" %}

如果不需要端口轉發，或者已經成功進行了端口轉發，現在可以連接到服務器。

連接到伺服器時使用的地址可以在[這裡](https://ip.pe.kr/)找到。

{% endtab %}

{% tab title="通過UPnP進行端口轉發嘗試" %}

在服務器文件夾的`purpur.yml`中，將`network.upnp-port-forwarding`設置為`true`。

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

{% tab title="使用Ngrok生成臨時地址" %}

使用Ngrok的方法對於短期測試、參與或與朋友一起玩非常有用。

1. 從[Ngrok官網](https://ngrok.com/download)下載 `Windows (64-bit)` ZIP檔案。
2. 將下載的Ngrok放入伺服器資料夾中。
3. 在[Ngrok儀表板](https://dashboard.ngrok.com/get-started/your-authtoken)上生成[授權令牌](#user-content-fn-13)[^13]。
4. 在伺服器資料夾中執行顯示在下方`Command Line`的命令。
5. 在執行腳本的最上方添加 `start /b ngrok tcp --region jp 25565`，在最底部添加 `taskkill /f /t /im ngrok.exe`。
6. 在控制台頂部顯示的 `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` 中，`0.tcp.jp.ngrok.io:12345`將成為伺服器的地址。
7. 現在您可以通過該地址從外部訪問。

{% endtab %}

{% tab title="從本地訪問" %}

如果您想從本地訪問服務器，可以在執行窗口中運行`cmd /k ipconfig`，然後使用輸出的`IPv4地址`進行訪問。

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

## 7. 進階階段

如果伺服器成功啟動並正常運行，現在輪到您自定義伺服器了。

通過以下指南了解如何自定義伺服器。

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
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
