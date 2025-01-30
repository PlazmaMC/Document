---
description: Learn about startup arguments and system properties.
---

# 🎛️ Arguments and Properties

The start arguments and system properties are values appended to the commands used for Plasma execution, influencing the overall operation of Plasma.

According to the **start argument** and **system properties** in the position added to the command (#user-content-fn-2)[^2], it will be divided.

***

## System Properties <a href="#id-1" id="id-1"></a>

System properties are values processed in the JVM before Plazma is initialized and entered in front of `-jar`.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Usage <a href="#id-1.1" id="id-1.1"></a>

System properties are entered as Java command arguments between `java` and `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indicates that the argument is an exclusive argument added to Plazma, not inherent to JVM,

If no value is entered for the property, the value is fixed as [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Full System Properties <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Type**: `Boolean`
- **Default**: `False`

Updates deprecated sign formats.

#### `debug.entities`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs related to entity information.

#### `debug.rewriteForIDE`

- **Type**: `Boolean`
- **Default**: `False`

Disables NMS revision to correctly load debug information in IDE, and automatically remaps internal version information.

#### `disable.watchdog`

- **Type**: `Boolean`
- **Default**: `False`

Disables Spigot's Watchdog warning system.

#### `letMeReload`

- **Type**: `Boolean`
- **Default**: `False`

Disables confirmation message for the `/reload` command.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

If you are a plugin developer and need to update a plugin, use hotswap instead of `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolean`
- **Default**: `False`

Disables plugins using standard input and output system.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolean`
- **Default**: `False`

Warns when deprecated formatting is detected in chat components.

#### `Paper.bypassHostCheck`

- **Type**: `Boolean`
- **Default**: `False`

Disables server's pattern matching verification when players connect to the server.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs for missing keys in NBT objects.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs for head blocks with invalid profile information.

Logs all incorrect head blocks in the world with their locations.

#### `Paper.disableChannelLimit`

- **Type**: `Boolean`
- **Default**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Type**: `Boolean`
- **Default**: `False`

Disables plugin class prioritization system.

Useful when issues arise in plugin shading.

#### `Paper.disableFlushConsolidate`

- **Type**: `Boolean`
- **Default**: `False`

Disables Netty flush consolidation system.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Default**: `750`

Splits entities into multiple packets if they exceed the set value.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Default**: `8192`

Sets the maximum packet size the server can receive at once.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Default**: `False`

Disables Java version check.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

World and overall files can be permanently corrupted, breaking the game's entire mechanics.

Any issues that arise from using this are the user's responsibility, and Plamza does not provide any support for it.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Default**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Default**: `80`

Sets the maximum length of characters that can be entered on a sign line.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Default**: `(world version) + 1`

Sets the version of initial world update information to be initialized first.

Useful when a large number of chunks need to be updated, but otherwise not used.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Default**: `True`

Enables processing of comments in YAML files.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Default**: `30`

Kicks players if no data is received from them for the specified time (in seconds).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolean`
- **Default**: `False`

Ignores server properties comments.

#### `Paper.debug-sync-loads`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs for synchronous chunk loading.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolean`
- **Default**: `False`

Enables Minecraft's [default chunk writing system](#user-content-fn-10)[^10].

This proceeds to save each chunk sequentially, causing significant performance degradation.

#### `Paper.explicit-flush`

- **Type**: `Boolean`
- **Default**: `False`

Enables explicit flushing of network channels.

#### `Paper.strict-thread-checks`

- **Type**: `Boolean`
- **Default**: `False`

Always logs errors that do not occur on the main thread.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolean`
- **Default**: `False`

Outputs a warning if scheduled tasks have excessive wait times.

#### `Paperclip.patchOnly`

- **Type**: `Boolean`
- **Default**: `False`

When using the default executable file, only applies patches without starting the server.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolean`
- **Default**: `false`
- **Conflict**: `Plazma.disableConfigOptimization`

Optimize the initial configuration more strongly.

Enabling this will make the server faster and safer, but it can have a significant impact on gameplay.

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolean`
- **Default**: `false`
- **Conflict**: `Plazma.aggressiveOptimize`

Do not optimize the initial configuration.

This makes it use Paper's default configuration.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Default**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolean`
- **Default**: `false`

Disable the Plazma branding and use the vanilla default server favicon.

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolean`
- **Default**: `false`
- **Conflict**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

This can have a significant impact on server safety and performance.

Any issues arising from this property are the responsibility of the server administrator.
{% endhint %}

Provides the initial configuration with the default values supplied by Mojang.

This disables all vulnerability patches applied by Paper.

Vulnerability patches can be re-enabled in either the Paper configuration or Plazma configuration.

#### `Plazma.vanillaize`

- **Type**: `Boolean`
- **Default**: `true`
- **Conflict**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Set the initial configuration closer to vanilla.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### The deprecated property <a href="#id-1.3" id="id-1.3"></a> is in use.

The following system property is a deprecated property.

#### `timings.bypassMax`

- **Type**: `Boolean`
- **Default**: `false`
- **Deprecated**: Timings has been removed from Plazma since

Determines if values exceeding the maximum that can be sent to Aikar's Timings API are allowed.

Even if done this way, rate limiting will be applied if not handled in the API.

***

## Start Arguments <a href="#id-2" id="id-2"></a>

Start arguments are entered after `-jar *.jar` to initialize Plazma and are processed together.

### Usage <a href="#id-2.1" id="id-2.1"></a>

System properties are entered as program command arguments after `-jar *.jar`.

For example, if you want to apply the `nogui` start argument,\
enter as follows for Plazma to process the `nogui` argument during initialization.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### All Start Arguments <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Default**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Default**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Default**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Starts the server with a demo world.

#### `eraseCache`

Removes leftover cache files after world upgrades.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Outputs the full start arguments and descriptions for Plazma.

#### `initSettings`

Only generates configuration files and shuts down the server.

#### `jfrProfile`

Enables JFR profiling.

#### `max-players`

- **Alias**: `s`, `size`
- **Default**: `(server properties)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Disables the graphical interface panel.

#### `nojline`

Disables JLine and uses vanilla console.

#### `online-mode`

- **Alias**: `o`
- **Default**: `(server properties)`

Selects whether to authenticate players with Mojang authentication servers.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Default**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Sets the location of the deprecated PaperSpigot configuration file.

Used to transfer existing configurations to new configuration files, and not used afterwards.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Default**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Default**: `plugins`

Sets the location of the plugins folder.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Default**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Default**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Starts the server in a completely vanilla state (Safe Mode).

#### `server-ip`

- **Alias**: `h`, `host`
- **Default**: `(server properties)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Default**: `(server properties)`

Sets the port of the server.

#### `server-name`

- **Default**: `A Plazma Server`

Sets the name of the server.

#### `spigot-settings`

- **Alias**: `S`
- **Default**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Outputs the Plazma version.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Default**: `(server folder)`

Sets the location where world files are saved.

#### `world-name`

- **Alias**: `w`, `world`
- **Default**: `(server properties)`

Sets the name of the world file.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: The location for processing arguments changes depending on the appended location.

[^3]: For example, if you want to set (enable) `Plazma.iKnowWhatIAmDoing` to `true`, entering `-DPlazma.iKnowWhatIAmDoing` alone will work the same as `-DPlazma.iKnowWhatIAmDoing=true`.

[^4]: For example, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Event detector.

[^6]: Event detector.

[^7]: Client.

[^8]: A signal indicating that the server is properly connected, like a heartbeat.

[^9]: Using Purpur's AFK kick feature, you can kick players who are away from their keyboards.

[^10]: Sync Chunk Write System.

[^11]: `WARNING! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.`

[^12]: In games, `world optimization` works on the same principle.

[^13]: Excluding administrators `level 2` and above.

[^14]: Internet Protocol, IP.
