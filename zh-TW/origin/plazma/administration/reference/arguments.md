---
description: 了解启动参数和系统属性。
---

# 🎛️ 启动参数和属性

開始入口和系統屬性是Plazma執行所使用的命令[^1]所附加的值，對Plazma的操作產生整體影響。

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## 系统属性 <a href="#id-1" id="id-1"></a>

系统属性是在`-jar`之前输入的值，在Plazma初始化之前由JVM处理。

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### 使用方法 <a href="#id-1.1" id="id-1.1"></a>

系统属性作为Java命令参数输入在`java`和`-jar`之间。

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`表示该参数不是JVM内置的，而是添加到Plazma的专用参数，

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정](#user-content-fn-3)[^3]됩니다.

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### 全部系统属性 <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **类型**: `布尔值`
- **默认值**: `False`

更新停用的标志格式。

#### `debug.entities`

- **类型**: `布尔值`
- **默认值**: `False`

启用与实体信息相关的调试日志。

#### `debug.rewriteForIDE`

- **类型**: `布尔值`
- **默认值**: `False`

为了正确加载IDE中的调试信息，禁用NMS修订，并自动重新映射内部版本信息。

#### `disable.watchdog`

- **类型**: `布尔值`
- **默认值**: `False`

禁用Spigot的看门狗警告系统。

#### `letMeReload`

- **类型**: `布尔值`
- **默认值**: `False`

禁用`/reload`命令的重新加载消息。

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

如果您是插件开发人员并且需要更新插件，请使用热交换而不是`/reload`。
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **类型**: `布尔值`
- **默认值**: `False`

禁用使用标准输入输出系统的插件。

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **类型**: `布尔值`
- **默认值**: `False`

检测到聊天组件中已停用的格式时发出警告。

#### `Paper.bypassHostCheck`

- **类型**: `布尔值`
- **默认值**: `False`

连接到服务器时禁用服务器的主机检查。

#### `Paper.debugDynamicMissingKeys`

- **类型**: `布尔值`
- **默认值**: `False`

启用对NBT对象中丢失键的调试日志。

#### `Paper.debugInvalidSkullProfiles`

- **类型**: `布尔值`
- **默认值**: `False`

启用对具有无效头骨配置文件的调试日志。

这将记录世界中所有无效的头骨配置文件及其位置。

#### `Paper.disableChannelLimit`

- **类型**: `布尔值`
- **默认值**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **类型**: `布尔值`
- **默认值**: `False`

禁用插件类优先级系统。

在插件Shade中遇到问题时很有用。

#### `Paper.disableFlushConsolidate`

- **类型**: `布尔值`
- **默认值**: `False`

禁用Netty刷新合并系统。

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **默认值**: `750`

如果实体超过设置的值，则将其分割为多个数据包进行传输。

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **默认值**: `8192`

设置服务器一次接收的最大数据包大小。

#### `Paper.ignoreJavaVersion`

- **类型**: `布尔值`
- **默认值**: `False`

禁用Java版本检查。

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

可能会永久损坏世界等文件，并破坏游戏的整个机制。

由此产生的所有问题由用户承担，Plamza不提供任何支持。
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **默认值**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **默认值**: `80`

设置牌子一行中可以输入的最大字符数。

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **默认值**: `(世界版本) + 1`

设置要首先初始化的世界更新信息的版本。

对于需要大量更新的区块很有用，但在其他情况下不使用。

#### `Paper.parseYamlCommentsByDefault`

- **类型**: `布尔值`
- **默认值**: `True`

启用处理YAML文件注释。

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **默认值**: `30`

当玩家在输入值（秒）后未收到任何数据时，将踢出玩家。

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **类型**: `布尔值`
- **默认值**: `False`

忽略服务器属性的注释。

#### `Paper.debug-sync-loads`

- **类型**: `布尔值`
- **默认值**: `False`

启用同步区块写入的调试日志。

#### `Paper.enable-sync-chunk-writes`

- **类型**: `布尔值`
- **默认值**: `False`

启用Minecraft的[默认区块写入系统](#user-content-fn-10)[^10]。

这将按顺序保存每个区块，导致严重的性能下降。

#### `Paper.explicit-flush`

- **类型**: `布尔值`
- **默认值**: `False`

启用网络通道的显式刷新。

#### `Paper.strict-thread-checks`

- **类型**: `布尔值`
- **默认值**: `False`

始终记录在主线程之外发生的错误。

#### `Paper.tickList-warn-on-excessive-delay`

- **类型**: `布尔值`
- **默认值**: `False`

如果预定任务具有过多等待时间，则输出警告。

#### `Paperclip.patchOnly`

- **类型**: `布尔值`
- **默认值**: `False`

使用默认提供的执行文件时，仅应用补丁而不启动服务器。

#### `Plazma.aggressiveOptimize`

- **类型**: `布尔值`
- **默认值**: `false`
- **衝突**：`Plazma.disableConfigOptimization`

加強初始化配置的優化。

啟用後，伺服器速度更快，更安全，但可能會對遊戲遊玩產生重大影響。

#### `Plazma.disableConfigOptimization`

- **类型**: `布尔值`
- **默认值**: `false`
- **衝突**：`Plazma.aggressiveOptimize`

不對初始化配置進行優化。

使用Paper的默認配置。

#### `Plazma.iKnowWhatIAmDoing`

- **类型**: `布尔值`
- **默认值**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **类型**: `布尔值`
- **默认值**: `false`

停用Plazma品牌，使用基本的Vanilla伺服器favicon。

#### `Plazma.useVanillaConfiguration`

- **类型**: `布尔值`
- **默认值**: `false`
- **衝突**：`Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

這可能會對伺服器的安全性和效能造成重大影響。

所有使用此屬性引起的問題應由伺服器管理員負責。
{% endhint %}

將初始化配置提供為Mojang提供的默認值。

將所有Paper應用的漏洞修補停用。

漏洞修補可重新在Paper配置或Plazma配置中啟用。

#### `Plazma.vanillaize`

- **类型**: `布尔值`
- **默認**：`true`
- **衝突**：`Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

將初始化配置設置為接近Vanilla。

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### 已停用屬性 <a href="#id-1.3" id="id-1.3"></a>

以下系統屬性已停用。

#### `timings.bypassMax`

- **类型**: `布尔值`
- **默认值**: `false`
- **已停用**: Timings自Plazma中完全移除後

決定是否可以超過Aikar的Timings API可接受的最大值。

即使這樣做，如果API未處理異常，將應用速率限制。

***

## 起始引數 <a href="#id-2" id="id-2"></a>

起始引數被輸入在 `-jar *.jar` 之後，Plazma將初始化並處理一起處理的值。

### 用法 <a href="#id-2.1" id="id-2.1"></a>

系統屬性被輸入為 `-jar *.jar` 之後的程序命令引數。

例如，如果要應用 `nogui` 起始引數，\
輸入以下內容將使Plazma在初始化期間處理 `nogui` 引數。

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### 完整起始引數 <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **別名**: `b`
- **預設值**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **別名**: `c`
- **預設值**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **別名**: `c`
- **預設值**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

啟動服務器到演示世界。

#### `eraseCache`

刪除升級後剩餘的快取文件。

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **別名**: `?`

顯示Plazma的完整啟動引數和說明。

#### `initSettings`

僅生成配置文件並關閉服務器。

#### `jfrProfile`

啟用JFR配置。

#### `max-players`

- **別名**: `s`, `size`
- **預設值**: `(服務器屬性)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

禁用圖形界面面板。

#### `nojline`

禁用JLine並使用原始控制台。

#### `online-mode`

- **別名**: `o`
- **預設值**: `(服務器屬性)`

選擇是否要通過Mojang驗證服務器驗證玩家。

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **別名**: `paper`
- **預設值**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

設置停用的PaperSpigot配置文件位置。

這是為了將現有配置轉移到新配置文件而使用的，之後將不再使用。

#### `paper-settings-directory`

- **別名**: `paper-dir`
- **預設值**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **別名**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **別名**: `p`
- **預設值**: `plugins`

設置插件文件夾的位置。

#### `pufferfish-settings`

- **別名**: `pufferfish`
- **預設值**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **別名**: `purpur`
- **預設值**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

以完全原始狀態啟動服務器（安全模式）。

#### `server-ip`

- **別名**: `h`, `host`
- **預設值**: `(服務器屬性)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **別名**: `p`, `port`
- **預設值**: `(服務器屬性)`

設置服務器的端口。

#### `server-name`

- **預設值**: `A Plazma Server`

設置服務器的名稱。

#### `spigot-settings`

- **別名**: `S`
- **預設值**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **別名**: `v`

顯示Plazma版本。

#### `world-dir`

- **別名**: `W`, `universe`, `world-container`
- **預設值**: `(服務器文件夾)`

設置存儲世界文件的位置。

#### `world-name`

- **別名**: `w`, `world`
- **預設值**: `(服務器屬性)`

設置世界文件的名稱。

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: 根據附加位置處理引數的位置會發生變化。

[^3]: 例如，如果要將 `Plazma.iKnowWhatIAmDoing` 設置為 `true`（啟用），則只需輸入 `-DPlazma.iKnowWhatIAmDoing` 與 `-DPlazma.iKnowWhatIAmDoing=true` 相同。

[^4]: 例如，`"-DPlazma.iKnowWhatIAmDoing"`

[^5]: 事件偵測器。

[^6]: 事件偵測器。

[^7]: 客戶端。

[^8]: 像心跳一樣向伺服器發送連接正常的信號。

[^9]: 使用Purpur的AFK踢出功能，即使玩家離開也可以進行踢出。

[^10]: 同步區塊寫入系統，Sync Chunk Write System。

[^11]: \`警告！ Plazma可能會導致意外問題，所以請務必在將其用於公共伺服器之前進行全面測試。

[^12]: 在遊戲中，`世界優化` 也遵循這個原則。

[^13]: 管理員排除`等級2`以上。

[^14]: 網際網路協定，IP。
