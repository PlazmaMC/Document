---
description: 了解启动参数和系统属性。
---

# 🎛️ 参数和属性

起始输入和系统属性是Plazma执行时附加到[用于执行的命令](#user-content-fn-1)[^1]的值，对Plazma的运行产生全面影响。

[命令中添加的位置](#user-content-fn-2)[^2]将被分为**起始参数**和**系统属性**。

***

## 系统属性 <a href="#id-1" id="id-1"></a>

系统属性是在 `-jar` 前输入的值，在Plazma初始化之前由JVM处理。

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### 用法 <a href="#id-1.1" id="id-1.1"></a>

系统属性作为Java命令参数输入，位于`java`和`-jar`之间。

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`表示该参数不是JVM内置的，而是附加到Plazma的专用参数，

如果未输入任何值，则值将被固定为[`true`](#user-content-fn-3)[^3]。

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

禁用NMS修订以便IDE正确加载调试信息，\
并自动重新映射内部版本信息。

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

如果您是插件开发者并需要更新插件，请使用热交换而不是`/reload`。
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **类型**: `布尔值`
- **默认值**: `False`

禁用使用标准输入/输出的插件。

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **类型**: `布尔值`
- **默认值**: `False`

检测到聊天组件中使用的停用格式时发出警告。

#### `Paper.bypassHostCheck`

- **类型**: `布尔值`
- **默认值**: `False`

禁用玩家连接到服务器时的主机匹配验证。

#### `Paper.debugDynamicMissingKeys`

- **类型**: `布尔值`
- **默认值**: `False`

启用对NBT对象中缺失键的调试日志。

#### `Paper.debugInvalidSkullProfiles`

- **类型**: `布尔值`
- **默认值**: `False`

启用对具有无效配置文件信息的头骨块的调试日志。

记录世界中所有无效头骨块的位置。

#### `Paper.disableChannelLimit`

- **类型**: `布尔值`
- **默认值**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **类型**: `布尔值`
- **默认值**: `False`

禁用插件类优先级系统。

在插件阴影中出现问题时很有用。

#### `Paper.disableFlushConsolidate`

- **类型**: `布尔值`
- **默认值**: `False`

禁用Netty刷新合并系统。

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **默认值**: `750`

如果实体数量超过设置值，则分割为多个数据包进行传输。

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

可能会永久损坏世界和其他文件，并使游戏机制崩溃。

由此导致的所有问题由用户自行承担，Plamza不提供任何支持。
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **默认值**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **默认值**: `80`

设置标志一行可输入的最大字符数。

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **默认值**: `(world version) + 1`

设置要首先初始化的世界更新信息的版本。

对于需要大量更新块的情况很有用，但在其他情况下不使用。

#### `Paper.parseYamlCommentsByDefault`

- **类型**: `布尔值`
- **默认值**: `True`

启用默认情况下解析YAML文件的注释。

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **默认值**: `30`

当玩家在指定时间内（以秒为单位）未收到任何数据时，将踢出玩家。

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **类型**: `布尔值`
- **默认值**: `False`

忽略服务器属性的注释。

#### `Paper.debug-sync-loads`

- **类型**: `布尔值`
- **默认值**: `False`

启用同步块写入的调试日志。

#### `Paper.enable-sync-chunk-writes`

- **类型**: `布尔值`
- **默认值**: `False`

启用Minecraft的[默认块写入系统](#user-content-fn-10)[^10]。

这会按顺序保存每个块，导致严重性能下降。

#### `Paper.explicit-flush`

- **类型**: `布尔值`
- **默认值**: `False`

启用网络通道的显式刷新。

#### `Paper.strict-thread-checks`

- **类型**: `布尔值`
- **默认值**: `False`

始终记录不是在主线程上发生的错误。

#### `Paper.tickList-warn-on-excessive-delay`

- **类型**: `布尔值`
- **默认值**: `False`

如果预定任务具有过多的延迟，将输出警告。

#### `Paperclip.patchOnly`

- **类型**: `布尔值`
- **默认值**: `False`

如果使用默认提供的执行文件，则仅应用补丁而不启动服务器。

#### `Plazma.aggressiveOptimize`

- **类型**: `布尔值`
- **默认值**: `false`
- **冲突**: `Plazma.disableConfigOptimization`

加强初始化配置优化。

启用后，服务器将更快更安全，但可能会对游戏玩法产生重大影响。

#### `Plazma.disableConfigOptimization`

- **类型**: `布尔值`
- **默认值**: `false`
- **冲突**: `Plazma.aggressiveOptimize`

不优化初始配置。

将使用Paper的默认配置。

#### `Plazma.iKnowWhatIAmDoing`

- **类型**: `布尔值`
- **默认值**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **类型**: `布尔值`
- **默认值**: `false`

禁用Plazma品牌，并使用原始服务器默认favicon。

#### `Plazma.useVanillaConfiguration`

- **类型**: `布尔值`
- **默认值**: `false`
- **冲突**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

这可能严重影响服务器的安全性和性能。

出现任何问题都由服务器管理员负责。
{% endhint %}

将初始配置设置为由Mojang提供的默认值。

将禁用Paper上应用的所有漏洞修补。

可以在Paper配置或Plazma配置中重新启用漏洞修补。

#### `Plazma.vanillaize`

- **类型**: `布尔值`
- **默认值**: `true`
- **冲突**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

将初始配置设置为接近原始。

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### 已停用的属性 <a href="#id-1.3" id="id-1.3"></a>

以下系统属性已停用。

#### `timings.bypassMax`

- **类型**: `布尔值`
- **默认值**: `false`
- **已停用**：自Plazma中删除Timings以来

决定是否可以超过Aikar的Timings API可发送的最大值。

即使如此，如果API未处理异常，则会应用速率限制。

***

## 起始参数 <a href="#id-2" id="id-2"></a>

起始参数是在`-jar *.jar`之后输入的，用于初始化Plazma并一起处理的值。

### 用法 <a href="#id-2.1" id="id-2.1"></a>

系统属性作为`-jar *.jar`后的程序命令参数输入。

例如，如果要应用`nogui`起始参数，\
请按以下方式输入，Plazma在初始化过程中将处理`nogui`参数。

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### 完整的起始参数 <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **别名**：`b`
- **默认值**：`bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **别名**：`c`
- **默认值**：`commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **别名**：`c`
- **默认值**：`server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

启动服务器到演示世界。

#### `eraseCache`

删除升级后剩余的缓存文件。

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **别名**：`?`

显示Plazma的完整启动参数和说明。

#### `initSettings`

仅创建配置文件并关闭服务器。

#### `jfrProfile`

启用JFR分析。

#### `max-players`

- **别名**：`s`，`size`
- **默认值**：`(服务器属性)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

禁用图形界面面板。

#### `nojline`

禁用JLine并使用原始控制台。

#### `online-mode`

- **别名**：`o`
- **默认值**：`(服务器属性)`

选择是否要验证玩家到Mojang验证服务器。

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **别名**：`paper`
- **默认值**：`paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

设置已停用的PaperSpigot配置文件位置。

此用于将现有配置迁移到新配置文件，之后不再使用。

#### `paper-settings-directory`

- **别名**：`paper-dir`
- **默认值**：`config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **别名**：`plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **别名**：`p`
- **默认值**：`plugins`

设置插件文件夹的位置。

#### `pufferfish-settings`

- **别名**：`pufferfish`
- **默认值**：`pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **别名**：`purpur`
- **默认值**：`purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

以安全模式启动服务器，完全原始状态。

#### `server-ip`

- **别名**：`h`，`host`
- **默认值**：`(服务器属性)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **别名**：`p`，`port`
- **默认值**：`(服务器属性)`

设置服务器的端口。

#### `server-name`

- **默认值**：`A Plazma Server`

设置服务器的名称。

#### `spigot-settings`

- **别名**：`S`
- **默认值**：`spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **别名**：`v`

输出Plazma版本。

#### `world-dir`

- **别名**：`W`，`universe`，`world-container`
- **默认值**：`(服务器文件夹)`

设置存储世界文件的位置。

#### `world-name`

- **别名**：`w`，`world`
- **默认值**：`(服务器属性)`

设置世界文件的名称。

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: 根据追加的位置处理参数的位置会发生变化。

[^3]: 例如，如果要将 `Plazma.iKnowWhatIAmDoing` 设置为 `true`（启用），只需输入 `-DPlazma.iKnowWhatIAmDoing`，而不是 `-DPlazma.iKnowWhatIAmDoing=true`，它将同样有效。

[^4]: 例如，`"-DPlazma.iKnowWhatIAmDoing"`

[^5]: 事件检测器。

[^6]: 事件检测器。

[^7]: 客户端。

[^8]: 像心跳一样向服务器发送连接正常的信号。

[^9]: 使用Purpur的AFK踢出功能，即使玩家离开也可以将其踢出。

[^10]: 同步区块写入系统，Sync Chunk Write System。

[^11]: \`警告！ Plazma可能会导致意外问题，因此请确保在将其用于公共服务器之前进行彻底测试。

[^12]: 在游戏中，“世界优化”也是按照这个原则运作的。

[^13]: 除了`级别 2`以上的管理员。

[^14]: Internet协议，IP。
