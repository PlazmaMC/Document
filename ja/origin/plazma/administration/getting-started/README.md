---
description: Plazmaでサーバーを作る方法を知ってください。
---

# 👟 始める

Plazmaを安定して使用するためには、システムが次の要件を満たしている必要があります。

|         | 最低  | 推奨   |
| :-----: | --- | ---- |
| アーキテクチャ | x64 | -    |
|   RAM   | 8GB | 16GB |
|  保存スペース | 1GB | 8GB  |
|   JDK   | 17  | 21   |

スムーズな構成ファイルの編集のために、[Visual Studio Code](https://code.visualstudio.com/download)などのエディタをインストールするのも良いでしょう。

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="正しい出力" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
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

1. まず、[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) から **JDK 21**を`.msi`形式でダウンロードします。
2. ダウンロードしたインストーラーを実行し、`次へ`をクリックします。
3. **ウィンドウの左中央に表示されるメニューから`Set JAVA_HOME variable`を有効にした後、**`次へ`をクリックします。
4. `インストール`を押してJREのインストールを`完了`します。
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

その後、次のコマンドをターミナルで実行してJREをインストールします。

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

## 2. Plazmaのダウンロード

Plazmaではさまざまな形式の実行ファイルが提供されています。

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>詳細を見る</summary>

実行ファイルの名前は`plazma-(バージョン管理者)-1.20.4-R0.1-SNAPSHOT-(マッピング形式).jar`に決まります。

- **マッピング形式**\
  マッピングはMinecraftの実際のコードと難読化されたコードをつなぐ一種の地図です。
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, バニラ Minecraft マッピングです。 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **バージョン管理者**\
  バージョン管理者はサーバー駆動に必要なライブラリと、サーバーファイルをパッチするサーバーのランチャーと言えます。
  - **Paperclip**\
    PaperMCチームがPaperおよび他の派生プラットフォームのために開発した管理者で、ライブラリをダウンロードし、サーバーにパッチを適用する役割を果たします。
  - **Bundler**\
    バニラMinecraftバージョン管理者です。

</details>

***

## 3. 開始スクリプトの作成

Plazmaを簡単に開始し、サーバーを自動的に再起動するには、[開始スクリプト](#user-content-fn-6)[^6]を作成する必要があります。

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

左下のダウンロードボタンをクリックして開始スクリプトをダウンロードできます。\
**ダウンロードした開始スクリプトが自身のオペレーティングシステムと同じか確認してください。**

***

## 4. ファイルの整理

今ダウンロードした開始スクリプトとPlazmaを新しいフォルダに移動します。

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

今、開始スクリプトを実行します。 Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA同意

開始スクリプトを一度実行すると、フォルダに`eula.txt`が作成されます。

EULA[^9]は[Mojang Studios](#user-content-fn-10)[^10]のサービスを利用することに同意する使用許諾契約です。

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

EULAに同意するには、`eula.txt`ファイルの`eula=false`を`eula=true`に変更して保存してください。

***

## 6. 外部アクセスを許可 (Windows)

現代のオペレーティングシステムは、外部からの危険なアクセスをブロックするために、基本的に**ファイアウォール**と**ルーター**が外部アクセスをブロックしています。

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

ルーターがUPnPをサポートしていない場合、ルーターごとにパネルが異なるため、直接情報を検索する必要があります。

または[Ngrok](https://ngrok.com/)を使用して一時的なアドレスを生成することもできます。
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 ポートフォワーディングの必要有無を確認

実行ウィンドウに以下のように入力して実行します。

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

出力が`True`であれば、ここで終了しても構いませんが、`False`であればポートフォワーディングを設定する必要があります。

### 6.2 サーバーに接続

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

サーバーに接続する際に使用されるアドレスは[こちら](https://ip.pe.kr/)で確認できます。
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

その後、サーバーを再起動すると、Plazmaが自動的にポートフォワーディングを試みます。

以下はコンソールに出力されるメッセージに応じたUPnPの成功または失敗です。コンソールでは`[UPnP] (メッセージ)`のように出力されます。

| メッセージ                            | 意味                   |
| -------------------------------- | -------------------- |
| `Successfully opened port (ポート)` | ポートフォワーディング成功。       |
| `Port (ポート) is already open`     | 他のサービスがそのポートを使用中です。  |
| `Failed to open port (ポート)`      | ポートフォワーディング失敗。       |
| `Service is unavailable`         | ルーターがUPnPをサポートしていない。 |

サーバーが終了するとPlazmaが自動的にポートを閉じます。
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. [Ngrokホームページ](https://ngrok.com/download)から`Windows (64-bit)`ZIPファイルをダウンロードします。
2. ダウンロードしたNgrokをサーバーフォルダに入れます。
3. [Ngrokダッシュボード](https://dashboard.ngrok.com/get-started/your-authtoken)から[認証トークンを生成](#user-content-fn-13)[^13]します。
4. サーバーフォルダで以下の`Command Line`に表示されるコマンドを実行します。
5. 実行スクリプト最上部に`start /b ngrok tcp --region jp 25565`、最下部に`taskkill /f /t /im ngrok.exe`を追加します。
6. コンソール最上部に表示される`Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`から、`0.tcp.jp.ngrok.io:12345`がサーバーのアドレスになります。
7. これで外部からそのアドレスを介して接続できます。
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

例えば、コマンド実行後に次のように出力された場合、

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

ここでIPv4アドレスに表示された`192.168.3.7`で接続を試みると、ローカルからサーバーに接続できます。

サーバーとゲームが同じPCで実行される場合、`localhost`で接続できます。
{% endtab %}
{% endtabs %}

## 7. 発展する

サーバーを成功裏に起動し、サーバーが正常に動作している場合は、これでサーバーをカスタマイズする番です。

以下の説明書でサーバーをカスタマイズする方法を確認してください。

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: PlazmaのベースであるPaperはSpigotをベースにしており、Spigotは公式サーバープラットフォームをベースにしています。

[^3]: Windowsキー + R

[^4]: Linuxの場合ターミナルで`java --version`

[^5]: JREはオープンソースプロジェクトの1つで、Minecraftサーバープラットフォームのようにさまざまな種類があります。

[^6]: 一般的に**ランタイム**として知られています。

[^7]: "Auto-restart"を有効にすると、サーバーが自動的に再起動されます。 `Control + C`を入力して終了できます。

[^8]: システムの半分以上を超えることは推奨されません。

    例えば、システム全体のメモリ容量が8GBの場合、4GB以上に設定することは推奨されません。

[^9]: End-User License Agreement、最終ユーザーライセンス契約。 詳細は[Minecraftホームページ](https://www.minecraft.net/ko-kr/usage-guidelines)をご確認ください。

[^10]: Microsoft Corporation。

[^11]: 韓国の場合、ゲーム産業振興に関する法律第32条第1項第9号に基づき**韓国マイクロソフト株式会社**から法的訴訟を行うことができます。

[^12]: Universal Plug & Play。 Plazmaに含まれるPurpurはこの技術を介して自動的にルーターと通信し、サーバーが実行中のみポートを開くため、ポートフォワーディングを直接行う必要はありません。

[^13]: アカウントがない場合はGoogleまたはGitHubアカウントを使用してNgrokにサインアップします。
