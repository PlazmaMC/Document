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

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### 使用方法 <a href="#id-1.1" id="id-1.1"></a>

システム属性は`java`と`-jar`の間にJavaコマンド引数として入力されます。

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`はその引数がJVMに組み込まれず、Plazmaに追加された専用の引数であることを示し、

属性に何の値も入力しない場合、値は[`true`で固定](#user-content-fn-3)[^3]されます。

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **デフォルト値**: `750`

エンティティが設定された値より多い場合は、複数パケットに分割して送信します。

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **デフォルト値**: `8192`

サーバーが一度に受け取ることができる最大パケットのサイズを設定します。

#### `Paper.ignoreJavaVersion`

- **形式**: `Boolean`
- **デフォルト値**: `False`

Javaバージョンの確認を無効にします。

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

ワールドなど全体のファイルが永続的に破損する可能性があり、ゲームの全体的なメカニズムが破壊されます。

これを使用して発生したすべての問題はユーザーが責任を負い、Plamzaはこれに関するいかなるサポートも提供しません。
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **デフォルト値**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **デフォルト値**: `80`

看板の1行に入力できる文字の最大長を設定します。

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **デフォルト値**: `(ワールドバージョン) + 1`

最初に初期化するワールド更新情報のバージョンを設定します。

大量のチャンクを更新する必要がある場合に便利ですが、それ以外の場合は使用されません。

#### `Paper.parseYamlCommentsByDefault`

- **形式**: `Boolean`
- **デフォルト値**: `True`

YAMLファイルのコメントの処理を有効にします。

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **デフォルト値**: `30`

プレイヤーから入力された値(秒)だけデータを受信しなかった場合、プレイヤーを追放します。

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **形式**: `Boolean`
- **デフォルト値**: `false`

Plazmaのブランディングを非アクティブ化し、バニラのデフォルトサーバーファビコンを使用するようにします。

#### `Plazma.useVanillaConfiguration`

- **形式**: `Boolean`
- **デフォルト値**: `false`
- **衝突**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

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
**해당 속성은 아직 개발중입니다.**
{% endhint %}

初期構成をバニラに近づけます。

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **エイリアス**: `c`
- **デフォルト**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **エイリアス**: `c`
- **デフォルト**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

デモワールドでサーバーを起動します。

#### `eraseCache`

ワールドアップグレード後に残ったキャッシュファイルを削除します。

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

グラフィックインターフェースパネルを無効化します。

#### `nojline`

JLine을 비활성화 하고 바닐라 콘솔을使用します。

#### `online-mode`

- **별칭**: `o`
- **デフォルト**: `(サーバー属性)`

Mojang 인증 서버로 플레이어를 검증할지 선택します。

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **별칭**: `paper`
- **기본值**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

사용 중지된 PaperSpigot 구성 파일의 위치를 설정합니다。

이는 기존 구성을 새 구성 파일로 이전하기 위해 사용되며、その後には使用されません。

#### `paper-settings-directory`

- **별칭**: `paper-dir`
- **기본值**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **별칭**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **별칭**: `p`
- **기본值**: `plugins`

プラグインフォルダの位置を設定します。

#### `pufferfish-settings`

- **별칭**: `pufferfish`
- **기본值**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **별칭**: `purpur`
- **기본値**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

(セーフモード) 完全なバニラ状態でサーバーを起動します。

#### `server-ip`

- **별칭**: `h`, `host`
- **デフォルト**: `(サーバー属性)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: `レベル 2`以上の管理者は除外します。

[^14]: Internet Protocol, IP。
