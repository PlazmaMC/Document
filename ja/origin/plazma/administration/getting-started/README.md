---
description: Plazmaでサーバーを作る方法を知ってください。
---

# 👟 始める

Plazmaを安定して使用するためには、システムが次の要件を満たしている必要があります。

|         |  最低 |   推奨 |
| :-----: | --: | ---: |
| アーキテクチャ | x64 |    - |
|   RAM   | 8GB | 16GB |
|  保存スペース | 1GB |  8GB |
|   JRE   |  17 |   21 |

スムーズな構成ファイルの編集のために、[Visual Studio Code](https://code.visualstudio.com/download)などのエディタをインストールするのも良いでしょう。

***

## 1. JREのインストール

名前からもわかるように、Minecraft: **"Java"** Edition はJavaで開発されており、実行するためにはJRE[^1]が必要です。

PlazmaはMojang Studiosの公式サーバープラットフォームを[基にしているため](#user-content-fn-2)[^2]、Plazmaを使用するためにもJREをインストールする必要があります。

### 1.1 JREの有無を確認

JREがシステムにインストールされているかどうかを確認するには、[実行ウィンドウ](#user-content-fn-3)[^3]に [`cmd /k java --version`](#user-content-fn-4)[^4]を入力して実行します。

以下のように出力された場合は、[2ステップ](setup.md#id-2)に進んでください。

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

上記のように出力されない場合、または以下のように出力される場合は、JREがないか古すぎるため、[1.2ステップ](setup.md#id-1.2)を実行する必要があります。

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

### 1.2 JREのインストール

本ガイドではJREの[種類の一つ](#user-content-fn-5)[^5]としてAzul Zuluを使用します。

インストールが完了した後、[1.1ステップ](setup.md#id-1.1)をもう一度実行してインストールが正しく完了したか確認してください。

{% tabs %}

{% tab title="Windows" %}

1. まず、[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) から **JDK 21**を`.msi`形式でダウンロードします。
2. ダウンロードしたインストーラーを実行し、`次へ`をクリックします。
3. **ウィンドウの左中央に表示されるメニューから`Set JAVA_HOME variable`を有効にした後、**`次へ`をクリックします。
4. `インストール`を押してJREのインストールを`完了`します。

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

その後、次のコマンドをターミナルで実行してJREをインストールします。

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

## 2. Plazmaのダウンロード

Plazmaではさまざまな形式の実行ファイルが提供されています。

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

以下の内容は開発者または各形式の特性に興味がある方のためのものです。\
一般ユーザーであれば[3ステップ](setup.md#id-3)にスキップしても問題ありません。

{% endhint %}

<details>

<summary>詳細を見る</summary>

実行ファイルの名前は`plazma-(バージョン管理者)-1.20.4-R0.1-SNAPSHOT-(マッピング形式).jar`に決まります。

- **マッピング形式**\
  マッピングはMinecraftの実際のコードと難読化されたコードをつなぐ一種の地図です。
  - **Reobf**\
    Reobfuscation、Spigotマッピングとも呼ばれ、ほとんどのNMSプラグインで使用されます。\
    1.20.5から使用が終了される予定です。
  - **Mojmap**\
    Mojangマッピング、バニラMinecraftマッピングです。
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

[Flags.sh](https://flags.sh)を通じて開始スクリプトを[生成できます。](#user-content-fn-7)[^7]\
Plazmaに[使用するメモリ](#user-content-fn-8)[^8]だけ入力すれば、コマンドが自動的に最適化されます。

左下のダウンロードボタンをクリックして開始スクリプトをダウンロードできます。\
**ダウンロードした開始スクリプトが自身のオペレーティングシステムと同じか確認してください。**

***

## 4. ファイルの整理

今ダウンロードした開始スクリプトとPlazmaを新しいフォルダに移動します。

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

そうでないと、PlazmaまたはJREが正しく動作しない可能性があります。

{% endhint %}

今、開始スクリプトを実行します。 Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA同意

開始スクリプトを一度実行すると、フォルダに`eula.txt`が作成されます。

EULA[^9]は[Mojang Studios](#user-content-fn-10)[^10]のサービスを利用することに同意する使用許諾契約です。

EULAに同意しない場合、サーバーを開始することができず、EULAに違反するとアカウントが停止されるなどの[制裁を受ける可能性があります。](#user-content-fn-11)[^11]

EULAに同意するには、`eula.txt`ファイルの`eula=false`を`eula=true`に変更して保存してください。

***

## 6. 外部アクセスを許可 (Windows)

現代のオペレーティングシステムは、外部からの危険なアクセスをブロックするために、基本的に**ファイアウォール**と**ルーター**が外部アクセスをブロックしています。

Windowsの場合、ファイアウォールは[3ステップ](setup.md#id-3)で許可したので、ポートフォワーディングだけすればよいです。

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

## 7. 発展段階

サーバーを成功裏に起動し、サーバーが正常に動作している場合は、これでサーバーをカスタマイズする番です。

以下のガイドを通じてサーバーをカスタマイズする方法について知ってください。

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment、Java実行環境。

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
