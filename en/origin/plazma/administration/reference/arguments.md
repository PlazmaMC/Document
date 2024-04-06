---
description: Learn about startup arguments and system properties.
---

# 🎛️ Arguments and Properties

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

According to the **start argument** and **system properties** divided by the position added to the command (#user-content-fn-2)[^2].

***

## System properties <a href="#id-1" id="id-1"></a>

System properties inputted before `-jar` are processed in the JVM before Plazma initialization.

{% hint style="warning" %}

**Modifying system properties can change the operation of Plazma and JVM, and can have a significant impact on the game!**

If you are not sure what each system property does, **do not use it under any circumstances!**

{% endhint %}

### Usage <a href="#id-1.1" id="id-1.1"></a>

System properties are inputted as Java command arguments between `java` and `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indicates that the argument is an exclusive argument added to Plazma, not embedded in the JVM,

If no value is entered for the property, the value is fixed to [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**The Paperweight server platform includes a `.` in the property name to distinguish system properties for each platform.**

In some terminals such as Windows Powershell, these arguments may not be allowed, so `"` should be added to both ends of the argument (#user-content-fn-4)[^4].

{% endhint %}

### Complete System Properties <a href="#id-1.2" id="id-1.2"></a>

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

Disables NMS revision in IDE to correctly load debug information, and automatically remaps internal version information.

#### `disable.watchdog`

- **Type**: `Boolean`
- **Default**: `False`

Disables Spigot's Watchdog warning system.

#### `letMeReload`

- **Type**: `Boolean`
- **Default**: `False`

Disables confirmation message for the `/reload` command.

{% hint style="danger" %}

**The `/reload` command is very unstable, so any issues that occur after using `/reload` are the responsibility of the user themselves.**

If you are a plugin developer and need to update a plugin, use hotswapping instead of `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolean`
- **Default**: `False`

Disables plugins using standard input/output system.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolean`
- **Default**: `False`

Warns when deprecated formatting is detected in chat components.

#### `Paper.bypassHostCheck`

- **Type**: `Boolean`
- **Default**: `False`

Disables server pattern matching verification when players connect to the server.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs for missing keys in NBT objects.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs for skull blocks with invalid profile information.

Logs all invalid skull blocks in the world with their locations.

#### `Paper.disableChannelLimit`

- **Type**: `Boolean`
- **Default**: `False`

Disable the limit of 128 plugin [channels](#user-content-fn-5)[^5] applied per player.

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

- **Type**: `Integer`
- **Default**: `750`

Splits entities into multiple packets if they exceed the set value.

#### `Paper.filterThreshold`

- **Type**: `Integer`
- **Default**: `8192`

Sets the maximum packet size the server can receive at once.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Default**: `False`

Disables Java version verification.

{% hint style="danger" %}

**This may allow JVM to attempt to access non-existent code!**

Files and overall game mechanics can be permanently damaged, causing the game to break.

Any issues caused by this are the user's responsibility, and Plamza does not provide any support for it.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Integer`
- **Default**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Type**: `Integer`
- **Default**: `80`

Sets the maximum length of characters that can be entered on one line of a sign.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Integer`
- **Default**: `(world version) + 1`

Sets the version of initial world update information to be initialized.

Useful when updating a large number of chunks, but otherwise not used.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Default**: `True`

Enables processing of comments in YAML files.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Integer`
- **Default**: `30`

Kicks players if no data is received from them for the entered value (in seconds).

In general, the [game](#user-content-fn-7)[^7] continues to send [heartbeat signals](#user-content-fn-8)[^8] to the server, so players are not [kicked,](#user-content-fn-9)[^9] but if the game does not respond, it is considered a crash and the server will no longer process the player and kick them.

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolean`
- **Default**: `False`

Ignores comments in server properties.

#### `Paper.debug-sync-loads`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs for synchronous chunk loading.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolean`
- **Default**: `False`

Enables Minecraft's [default chunk writing system](#user-content-fn-10)[^10].

This proceeds to save each chunk in order, causing significant performance degradation.

#### `Paper.explicit-flush`

- **Type**: `Boolean`
- **Default**: `False`

Enables Explicit Flushing for network channels.

#### `Paper.strict-thread-checks`

- **Type**: `Boolean`
- **Default**: `False`

Always logs errors not occurring on the main thread.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolean`
- **Default**: `False`

Outputs a warning if scheduled tasks have excessive wait time.

#### `Paperclip.patchOnly`

- **Type**: `Boolean`
- **Default**: `False`

When using the default provided executable, only applies patches without starting the server.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolean`
- **Default**: `false`

{% hint style="warning" %}

**This property will be moved to start arguments after 1.20.5.**

{% endhint %}

Applies stricter configuration optimization at the initial startup.

Activating it makes the server faster and safer, but it may block some gimmicks or have a significant impact on gameplay.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Default**: `false`

Suppress the warning message displayed when Plazma is initialized (#user-content-fn-11)[^11].

### Obsolete attribute <a href="#id-1.3" id="id-1.3"></a>

The following system attribute is obsolete.

#### `timings.bypassMax`

- **Type**: `Boolean`
- **Default**: `false`
- **Deprecated**: Since Timings was completely removed from Plazma

Determines whether exceeding the maximum value that can be sent to Aikar's Timings API is allowed.

Even if done so, rate limiting will be applied if not handled in the API.

***

## Start Argument <a href="#id-2" id="id-2"></a>

The start argument is entered after `-jar *.jar` to initialize Plazma and is processed together.

### Usage <a href="#id-2.1" id="id-2.1"></a>

System attributes are entered as program command arguments after `-jar *.jar`.

For example, if you want to apply the `nogui` start argument,\
enter as follows to have Plazma process the `nogui` argument during initialization.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Full Start Argument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Default**: `bukkit.yml`

Sets the name and location of the [Bukkit configuration file](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Default**: `commands.yml`

Sets the name and location of the [Bukkit command configuration file](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Default**: `server.properties`

Sets the name and location of the [server properties](../reference/configurations/property.md) file.

#### `demo`

Starts the server in demo world.

#### `eraseCache`

Removes remaining cache files after world upgrade.

#### `forceUpgrade`

Forces upgrading the world regardless of version.

#### `help`

- **Alias**: `?`

Outputs all start arguments and descriptions of Plazma.

#### `initSettings`

Creates configuration files only and shuts down the server.

#### `jfrProfile`

Enables JFR profiling.

#### `max-players`

- **Alias**: `s`, `size`
- **Default**: `(server properties)`

Sets the maximum number of allowed [players](#user-content-fn-14).

#### `nogui`

Disables the graphical interface panel.

#### `nojline`

Disables JLine and uses vanilla console.

#### `online-mode`

- **Alias**: `o`
- **Default**: `(server properties)`

Selects whether to verify players with Mojang authentication server.

**May be sanctioned for violating the [EULA](../getting-started/README.md#id-5) if not using Velocity or other proxies.**

#### `paper-settings`

- **Alias**: `paper`
- **Default**: `paper.yml`

{% hint style="warning" %}

**This argument has been deprecated after 1.19.4**

{% endhint %}

Sets the location of the deprecated PaperSpigot configuration file.

Used to transfer existing configurations to a new configuration file, and is no longer used afterwards.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Default**: `config`

Sets the name and location of the folder where [Paper configuration files](../reference/configurations/paper/README.md) are located.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Sets the name and location of the folder where [Plazma configuration files](../reference/configurations/plazma/README.md) are located.

#### `plugins`

- **Alias**: `p`
- **Default**: `plugins`

Sets the location of the plugins folder.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Default**: `pufferfish.yml`

Sets the name and location of the [Pufferfish configuration file](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Default**: `purpur.yml`

Sets the name and location of the [Purpur configuration file](../reference/configurations/purpur/README.md).

#### `safeMode`

Starts the server in a completely vanilla state (safe mode).

#### `server-ip`

- **Alias**: `h`, `host`
- **Default**: `(server properties)`

Sets the host name or [Internet Protocol](#user-content-fn-13) address of the server.

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

Sets the name and location of the [Spigot configuration file](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Outputs the Plazma version.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Default**: `(server folder)`

Sets the location where world files are stored.

#### `world-name`

- **Alias**: `w`, `world`
- **Default**: `(server properties)`

Sets the name of the world file.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: The processing location of the acquisition changes depending on the attached location.

[^3]: For example, if you want to set `Plazma.iKnowWhatIAmDoing` to `true` (activate), instead of entering `-DPlazma.iKnowWhatIAmDoing=true`, entering `-DPlazma.iKnowWhatIAmDoing` will work the same way.

[^4]: For example, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Event detector.

[^6]: Event detector.

[^7]: Client.

[^8]: A signal indicating that the server is properly connected like a heartbeat.

[^9]: Using Purpur's AFK kick feature, you can kick players who are away from their keyboards.

[^10]: Sync Chunk Write System.

[^11]: `WARNING! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.`

[^12]: In the game, `world optimization` also operates on the same principle.

[^13]: Internet Protocol, IP.

[^14]: Administrators above `level 2` are excluded.
