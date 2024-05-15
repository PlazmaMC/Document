---
description: 開始引数とシステム属性について調べてください。
---

# 🎛️ 引数と属性

시작 인수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로, Plazma의 작동에 전반적인 영향을 줍니다.

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 インス**と**システム属性**に分かれます。

***

## システム属性 <a href="#id-1" id="id-1"></a>

システム属性は`-jar`の前に入力され、Plazmaが初期化される前にJVMで処理される値です。

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **絶対に使用しないでください!**

{% endhint %}

### 使用方法 <a href="#id-1.1" id="id-1.1"></a>

システム属性は`java`と`-jar`の間にJavaコマンド引数として入力されます。

例えば、`Plazma.dummyProperty` 시스템 속성を適用しようとする場合、
次のように入力すると次のプロパティに`37`が入力され、Plazmaが初期化されます。

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`はその引数がJVMに組み込まれず、Plazmaに追加された専用の引数であることを示し、

属性に何の値も入力しない場合、値は[`true`で固定](#user-content-fn-3)[^3]されます。

{% hint style="info" %}

**Paperweight 계열 서버 プラットフォームは各プラットフォームごとにシステムの属性を区別するため、属性名に `.`を含んでいます。**

Windows Powershellなど一部のターミナルでは、このような引数を許可しないことがあるため、引数の両端に`"`を[追加する](#user-content-fn-4)[^4]必要があります。

{% endhint %}

### 全システム属性 <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **形式**: `Boolean`
- **デフォルト値**: `False`

使用中止された看板フォーマットを更新します。

#### `debug.entities`

- **形式**: `Boolean`
- **デフォルト値**: `False`

エンティティ情報に関連するデバッグログを有効にします。

#### `debug.rewriteForIDE`

- **形式**: `Boolean`
- **デフォルト値**: `False`

IDEでデバッグ情報を正しく読み込めるようにNMSリビジョンを無効化し、\
内部バージョン情報を自動的にリマップします。

#### `disable.watchdog`

- **形式**: `Boolean`
- **デフォルト値**: `False`

SpigotのWatchdog警告システムを無効化します。

#### `letMeReload`

- **形式**: `Boolean`
- **デフォルト値**: `False`

`/reload`コマンドの再確認メッセージを無効化します。

{% hint style="danger" %}

**`/reload` コマンドは非常に不安定なので、`/reload` 使用後に発生するサーバー内のすべての問題はユーザー自身にあります。**

プラグイン開発者でプラグインを更新する必要がある場合は、`/reload`の代わりにホットスワップを使用してください。

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **形式**: `Boolean`
- **デフォルト値**: `False`

標準入出力システムを使用するプラグインを無効化します。

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **形式**: `Boolean`
- **デフォルト値**: `False`

チャットコンポーネントで使用中止されたフォーマットが検出されると警告します。

#### `Paper.bypassHostCheck`

- **形式**: `Boolean`
- **デフォルト値**: `False`

プレイヤーがサーバーに接続する際、サーバーのパターン一致検証を無効化します。

#### `Paper.debugDynamicMissingKeys`

- **形式**: `Boolean`
- **デフォルト値**: `False`

NBTオブジェクトで欠落したキーに関するデバッグログを有効にします。

#### `Paper.debugInvalidSkullProfiles`

- **形式**: `Boolean`
- **デフォルト値**: `False`

不正なプロファイル情報を持つヘッドブロックのデバッグログを有効にします。

これはワールド内のすべての不正なヘッドブロックを位置とともにログします。

#### `Paper.disableChannelLimit`

- **形式**: `Boolean`
- **デフォルト値**: `False`

プレイヤーごとに適用される128個のプラグイン [チャネル](#user-content-fn-5)[^5]の数制限を無効にします。

#### `Paper.disableClassPrioritization`

- **形式**: `Boolean`
- **デフォルト値**: `False`

プラグインクラスの優先順位システムを無効にします。

プラグインシェードで問題が発生した場合に役立ちます。

#### `Paper.disableFlushConsolidate`

- **形式**: `Boolean`
- **デフォルト値**: `False`

Nettyフラッシュ統合システムを無効にします。

#### `Paper.excessiveTELimit`

- **形式**: `Integer`
- **デフォルト値**: `750`

エンティティが設定された値より多い場合は、複数パケットに分割して送信します。

#### `Paper.filterThreshold`

- **形式**: `Integer`
- **デフォルト値**: `8192`

サーバーが一度に受け取ることができる最大パケットのサイズを設定します。

#### `Paper.ignoreJavaVersion`

- **形式**: `Boolean`
- **デフォルト値**: `False`

Javaバージョンの確認を無効にします。

{% hint style="danger" %}

**このようにすると、JVMが存在しないコードにアクセスしようとすることがあります!**

ワールドなど全体のファイルが永続的に破損する可能性があり、ゲームの全体的なメカニズムが破壊されます。

これを使用して発生したすべての問題はユーザーが責任を負い、Plamzaはこれに関するいかなるサポートも提供しません。

{% endhint %}

#### `Paper.maxCustomChannelName`

- **形式**: `Integer`
- **デフォルト値**: `64`

プラグイン[チャネル](#user-content-fn-6)[^6]名の制限を設定します。

#### `Paper.maxSignLength`

- **形式**: `Integer`
- **デフォルト値**: `80`

看板の1行に入力できる文字の最大長を設定します。

#### `Paper.minPrecachedDatafixVersion`

- **形式**: `Integer`
- **デフォルト値**: `(ワールドバージョン) + 1`

最初に初期化するワールド更新情報のバージョンを設定します。

大量のチャンクを更新する必要がある場合に便利ですが、それ以外の場合は使用されません。

#### `Paper.parseYamlCommentsByDefault`

- **形式**: `Boolean`
- **デフォルト値**: `True`

YAMLファイルのコメントの処理を有効にします。

#### `Paper.playerConnection.keepAlive`

- **形式**: `Integer`
- **デフォルト値**: `30`

プレイヤーから入力された値(秒)だけデータを受信しなかった場合、プレイヤーを追放します。

一般的に、[ゲーム](#user-content-fn-7)[^7]はサーバーに引き続き[ハートビート信号](#user-content-fn-8)[^8]を送信するため、[追放されないが、](#user-content-fn-9)[^9]ゲームが応答しない場合、ゲームはクラッシュしたと見なされ、サーバーでもプレイヤーを処理せずに追放します。

#### `Paper.skipServerPropertiesComments`

- **形式**: `Boolean`
- **デフォルト値**: `False`

サーバー属性のコメントを無視します。

#### `Paper.debug-sync-loads`

- **形式**: `Boolean`
- **デフォルト値**: `False`

同期チャンク作成のデバッグログを有効にします。

#### `Paper.enable-sync-chunk-writes`

- **形式**: `Boolean`
- **デフォルト値**: `False`

Minecraftの[デフォルトチャンク作成システム](#user-content-fn-10)[^10]を有効にします。

これは各チャンクを順番に保存するため、著しいパフォーマンス低下を引き起こします。

#### `Paper.explicit-flush`

- **形式**: `Boolean`
- **デフォルト値**: `False`

ネットワークチャンネルの明示的なフラッシングを有効にします。

#### `Paper.strict-thread-checks`

- **形式**: `Boolean`
- **デフォルト値**: `False`

メインスレッドで発生しないエラーを常にログに記録します。

#### `Paper.tickList-warn-on-excessive-delay`

- **形式**: `Boolean`
- **デフォルト値**: `False`

予約されたタスクが過度の遅延を持つ場合、警告を出力します。

#### `Paperclip.patchOnly`

- **形式**: `Boolean`
- **デフォルト値**: `False`

デフォルトで提供される実行ファイルを使用する場合、サーバーを起動せずにパッチのみを適用します。

#### `Plazma.aggressiveOptimize`

- **形式**: `Boolean`
- **デフォルト値**: `false`
- **衝突**: `Plazma.disableConfigOptimization`

初期構成をより強力に最適化します。

有効にするとサーバーがより速く安全になりますが、ゲームプレイに大きな影響を与える可能性があります。

#### `Plazma.disableConfigOptimization`

- **形式**: `Boolean`
- **デフォルト値**: `false`
- **衝突**: `Plazma.aggressiveOptimize`

初期構成を最適化しません。

これはPaperのデフォルト構成を使用するようにします。

#### `Plazma.iKnowWhatIAmDoing`

- **形式**: `Boolean`
- **デフォルト値**: `false`

Plazmaが初期化される際に表示される[警告文](#user-content-fn-11)[^11]を抑制します。

#### `Plazma.useVanillaFavicon`

- **形式**: `Boolean`
- **デフォルト値**: `false`

Plazmaのブランディングを非アクティブ化し、バニラのデフォルトサーバーファビコンを使用するようにします。

#### `Plazma.useVanillaConfiguration`

- **形式**: `Boolean`
- **デフォルト値**: `false`
- **衝突**: `Plazma.disableConfigOptimization`

{% hint style="info" %}

**このプロパティはまだ開発中です。**

{% endhint %}

{% hint style="danger" %}

**このプロパティはパッチされたすべての脆弱性を元に戻します！**

これはサーバーの安全性とパフォーマンスに大きく影響を与える可能性があります。

このプロパティを使用して発生するすべての問題はサーバー管理者にあります。

{% endhint %}

初期構成をMojangが提供するデフォルト値で提供します。

これはPaperで適用されたすべての脆弱性パッチを非アクティブ化します。

脆弱性パッチはPaper構成またはPlazma構成で再度有効化できます。

#### `Plazma.vanillaize`

- **形式**: `Boolean`
- **デフォルト**: `true`
- **衝突**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**このプロパティはまだ開発中です。**

{% endhint %}

初期構成をバニラに近づけます。

これは基本的にサーバーパフォーマンスおよび安全に影響を与えない程度にのみ適用され、`Plazma.disableConfigOptimization` プロパティを使用する場合はバニラのデフォルト値を使用するよう構成されます。

### 廃止された属性 <a href="#id-1.3" id="id-1.3"></a>

以下のシステム属性は廃止されたものです。

#### `timings.bypassMax`

- **形式**: `Boolean`
- **デフォルト値**: `false`
- **廃止**: TimingsがPlazmaから完全に削除されてから

AikarのTimings APIに送信できる値の最大値を超えてもよいかどうかを決定します。

これを行ってもAPIで例外処理されない場合はレート制限が適用されます。

***

## 開始引数 <a href="#id-2" id="id-2"></a>

開始引数は`-jar *.jar`の後に入力され、Plazmaが初期化される際に一緒に処理される値です。

### 使用方法 <a href="#id-2.1" id="id-2.1"></a>

システム属性は`-jar *.jar`の後にプログラムのコマンド引数として入力されます。

例えば、`nogui`開始引数を適用しようとする場合、\
次のように入力するとPlazmaが初期化中に`nogui`引数を処理することになります。

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### 全体の開始引数 <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **エイリアス**: `b`
- **デフォルト**: `bukkit.yml`

[Bukkit構成ファイル](../reference/configurations/bukkit.md)の名前と位置を設定します。

#### `command-settings`

- **エイリアス**: `c`
- **デフォルト**: `commands.yml`

[Bukkitコマンド構成ファイル](../reference/configurations/bukkit.md)の名前と位置を設定します。

#### `config`

- **エイリアス**: `c`
- **デフォルト**: `server.properties`

[サーバー属性](../reference/configurations/property.md)ファイルの名前と位置を設定します。

#### `demo`

デモワールドでサーバーを起動します。

#### `eraseCache`

ワールドアップグレード後に残ったキャッシュファイルを削除します。

#### `forceUpgrade`

バージョンを無視してワールドを強制的に[アップグレード](#user-content-fn-12)[^12]します。

#### `help`

- **エイリアス**: `?`

Plazmaの全体の開始引数と説明を出力します。

#### `initSettings`

構成ファイルのみを生成してサーバーを終了します。

#### `jfrProfile`

JFRプロファイリングを有効化します。

#### `max-players`

- **エイリアス**: `s`, `size`
- **デフォルト**: `(サーバー属性)`

許容される最大[プレイヤー](#user-content-fn-14)[^14]数を設定します。

#### `nogui`

グラフィックインターフェースパネルを無効化します。

#### `nojline`

JLine을 비활성화 하고 바닐라 콘솔을使用します。

#### `online-mode`

- **별칭**: `o`
- **デフォルト**: `(サーバー属性)`

Mojang 인증 서버로 플레이어를 검증할지 선택します。

**Velocity 등 프록시를 사용하는 것이 아닌 경우 [EULA](../getting-started/README.md#id-5) 위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **별칭**: `paper`
- **기본值**: `paper.yml`

{% hint style="warning" %}

**この引数は1.19.4以降の使用が中止されました**

{% endhint %}

사용 중지된 PaperSpigot 구성 파일의 위치를 설정합니다。

이는 기존 구성을 새 구성 파일로 이전하기 위해 사용되며、その後には使用されません。

#### `paper-settings-directory`

- **별칭**: `paper-dir`
- **기본值**: `config`

[Paper 구성 파일](../reference/configurations/paper/README.md)が位置するフォルダの名前と位置を設定します。

#### `plazma-settings-directory`

- **별칭**: `plazma-dir`

[Plazma 구성 파일](../reference/configurations/plazma/README.md)が位置するフォルダの名前と位置を設定します。

#### `plugins`

- **별칭**: `p`
- **기본值**: `plugins`

プラグインフォルダの位置を設定します。

#### `pufferfish-settings`

- **별칭**: `pufferfish`
- **기본值**: `pufferfish.yml`

[Pufferfish 구성 파일](../reference/configurations/pufferfish.md)の名前と位置を設定します。

#### `purpur-settings`

- **별칭**: `purpur`
- **기본値**: `purpur.yml`

[Purpur 구성 파일](../reference/configurations/purpur/README.md)の名前と位置を設定します。

#### `safeMode`

(セーフモード) 完全なバニラ状態でサーバーを起動します。

#### `server-ip`

- **별칭**: `h`, `host`
- **デフォルト**: `(サーバー属性)`

サーバーのホスト名または[インターネットプロトコル](#user-content-fn-13)[^13]アドレスを設定します。

#### `server-port`

- **별칭**: `p`, `port`
- **デフォルト**: `(サーバー属性)`

サーバーのポートを設定します。

#### `server-name`

- **基本値**: `A Plazma Server`

サーバーの名前を設定します。

#### `spigot-settings`

- **별칭**: `S`
- **基本値**: `spigot.yml`

[Spigot構成ファイル](../reference/configurations/spigot.md)の名前と位置を設定します。

#### `version`

- **별칭**: `v`

Plazmaバージョンを出力します。

#### `world-dir`

- **별칭**: `W`, `universe`, `world-container`
- **基本値**: `(サーバーフォルダ)`

ワールドファイルが保存される位置を設定します。

#### `world-name`

- **별칭**: `w`, `world`
- **デフォルト**: `(サーバー属性)`

ワールドファイルの名前を設定します。

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: 追加された場所に応じて引数の処理位置が変更されます。

[^3]: たとえば、`Plazma.iKnowWhatIAmDoing`を`true`に設定(有効化)したい場合、`-DPlazma.iKnowWhatIAmDoing=true`ではなく`-DPlazma.iKnowWhatIAmDoing`だけを入力しても同様に機能します。

[^4]: たとえば、`"-DPlazma.iKnowWhatIAmDoing"`

[^5]: イベント検出器。

[^6]: イベント検出器。

[^7]: クライアント。

[^8]: 心拍のようにサーバーと正常に接続されていることを知らせる信号。

[^9]: PurpurのAFKキック機能を使用すると、離席中のプレイヤーもキックできます。

[^10]: 同期チャンク書き込みシステム、Sync Chunk Write System。

[^11]: `WARNING! Plazmaには予期せぬ問題が発生する可能性があるため、公開サーバーで使用する前に十分にテストしてください。`

[^12]: ゲームで`ワールド最適化`も同じ原理で動作します。

[^13]: Internet Protocol, IP。

[^14]: `レベル 2`以上の管理者は除外します。
