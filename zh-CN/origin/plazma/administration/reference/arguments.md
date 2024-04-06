---
description: 了解启动参数和系统属性。
---

# 🎛️ 参数和属性

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[命令中添加的位置](#user-content-fn-2)[^2]将被分为**起始参数**和**系统属性**。

***

## 系统属性 <a href="#id-1" id="id-1"></a>

系统属性是在 `-jar` 前输入的值，在Plazma初始化之前由JVM处理。

{% hint style="warning" %}

**修改系统属性可能会改变Plazma和JVM的运行方式，并可能对游戏产生重大影响！**

如果不确定每个系统属性的作用，请**绝对不要使用！**

{% endhint %}

### 用法 <a href="#id-1.1" id="id-1.1"></a>

系统属性作为Java命令参数输入，位于`java`和`-jar`之间。

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`表示该参数不是JVM内置的，而是附加到Plazma的专用参数，

如果未输入任何值，则值将被固定为[`true`](#user-content-fn-3)[^3]。

{% hint style="info" %}

**Paperweight系列服务器平台为了区分每个平台的系统属性，在属性名称中包含`.`。**

在某些终端（如Windows Powershell）中，可能不允许这些参数，因此必须在参数两端添加 `"`。

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

**`/reload`命令非常不稳定，因此使用`/reload`后导致的服务器内的所有问题将由用户自行承担。**

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

禁用每个玩家应用的128个插件[通道](#user-content-fn-5)[^5]的数量限制。

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

- **类型**: `整数`
- **默认值**: `750`

如果实体数量超过设置值，则分割为多个数据包进行传输。

#### `Paper.filterThreshold`

- **类型**: `整数`
- **默认值**: `8192`

设置服务器一次接收的最大数据包大小。

#### `Paper.ignoreJavaVersion`

- **类型**: `布尔值`
- **默认值**: `False`

禁用Java版本检查。

{% hint style="danger" %}

**这样做可能会导致JVM尝试访问不存在的代码！**

可能会永久损坏世界和其他文件，并使游戏机制崩溃。

由此导致的所有问题由用户自行承担，Plamza不提供任何支持。

{% endhint %}

#### `Paper.maxCustomChannelName`

- **类型**: `整数`
- **默认值**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **类型**: `整数`
- **默认值**: `80`

设置标志一行可输入的最大字符数。

#### `Paper.minPrecachedDatafixVersion`

- **类型**: `整数`
- **默认值**: `(world version) + 1`

设置要首先初始化的世界更新信息的版本。

对于需要大量更新块的情况很有用，但在其他情况下不使用。

#### `Paper.parseYamlCommentsByDefault`

- **类型**: `布尔值`
- **默认值**: `True`

启用默认情况下解析YAML文件的注释。

#### `Paper.playerConnection.keepAlive`

- **类型**: `整数`
- **默认值**: `30`

当玩家在指定时间内（以秒为单位）未收到任何数据时，将踢出玩家。

通常情况下，游戏会持续向服务器发送[心跳信号](#user-content-fn-8)[^8]，如果游戏没有响应，则被视为游戏崩溃，并且服务器将不再处理玩家并将其踢出。

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

{% hint style="warning" %}

**该属性将在1.20.5之后的启动参数中移动。**

{% endhint %}

更严格地应用于初始配置优化。

激活后，服务器会变得更快、更安全，但可能会阻止某些游戏机制或对游戏玩法产生重大影响。

#### `Plazma.iKnowWhatIAmDoing`

- **类型**: `布尔值`
- **默认值**: `false`

抑制Plazma初始化时显示的[警告](#user-content-fn-11)[^11]。

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

设置[Bukkit配置文件](../reference/configurations/bukkit.md)的名称和位置。

#### `command-settings`

- **别名**：`c`
- **默认值**：`commands.yml`

设置[Bukkit命令配置文件](../reference/configurations/bukkit.md)的名称和位置。

#### `config`

- **别名**：`c`
- **默认值**：`server.properties`

设置[服务器属性](../reference/configurations/property.md)文件的名称和位置。

#### `demo`

启动服务器到演示世界。

#### `eraseCache`

删除升级后剩余的缓存文件。

#### `forceUpgrade`

忽略版本并强制[升级](#user-content-fn-12)[^12]世界。

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

设置允许的最大[玩家](#user-content-fn-14)[^14]数量。

#### `nogui`

禁用图形界面面板。

#### `nojline`

禁用JLine并使用原始控制台。

#### `online-mode`

- **别名**：`o`
- **默认值**：`(服务器属性)`

选择是否要验证玩家到Mojang验证服务器。

**如果不使用Velocity等代理，可能会因违反[EULA](../getting-started/README.md#id-5)而受到制裁。**

#### `paper-settings`

- **别名**：`paper`
- **默认值**：`paper.yml`

{% hint style="warning" %}

**该参数已在1.19.4之后停止使用**

{% endhint %}

设置已停用的PaperSpigot配置文件位置。

此用于将现有配置迁移到新配置文件，之后不再使用。

#### `paper-settings-directory`

- **别名**：`paper-dir`
- **默认值**：`config`

设置包含[Paper配置文件](../reference/configurations/paper/README.md)的文件夹名称和位置。

#### `plazma-settings-directory`

- **别名**：`plazma-dir`

设置包含[Plazma配置文件](../reference/configurations/plazma/README.md)的文件夹名称和位置。

#### `plugins`

- **别名**：`p`
- **默认值**：`plugins`

设置插件文件夹的位置。

#### `pufferfish-settings`

- **别名**：`pufferfish`
- **默认值**：`pufferfish.yml`

设置[Pufferfish配置文件](../reference/configurations/pufferfish.md)的名称和位置。

#### `purpur-settings`

- **别名**：`purpur`
- **默认值**：`purpur.yml`

设置[Purpur配置文件](../reference/configurations/purpur/README.md)的名称和位置。

#### `safeMode`

以安全模式启动服务器，完全原始状态。

#### `server-ip`

- **别名**：`h`，`host`
- **默认值**：`(服务器属性)`

设置服务器的主机名或[Internet Protocol](#user-content-fn-13)[^13]地址。

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

设置[Spigot配置文件](../reference/configurations/spigot.md)的名称和位置。

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

[^13]: Internet协议，IP。

[^14]: 除了`级别 2`以上的管理员。
