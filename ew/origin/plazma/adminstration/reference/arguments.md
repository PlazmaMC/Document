---
description: Learn about startup arguments and system properties.
---

# 🎛️ Arguments and Properties

Startup variables and system properties are values appended to the [commands used](#user-content-fn-1)[^1] in Plazma execution, allowing values that cannot be changed after Plazma has been executed to be changed.

Depending on the [location of the appendage](#user-content-fn-2)[^2], they are divided into **startup arguments** and **system properties**.

***

## System Properties <a href="#id-1" id="id-1"></a>

System properties are values processed in the JVM before Plazma is initialized and entered in front of `-jar`.

{% hint style="warning" %}

### Modifying system properties can change the operation of Plazma and JVM, potentially having a significant impact on the game!

If you are not sure what each system property does, **do not use it under any circumstances!**
{% endhint %}

### Usage <a href="#id-1.1" id="id-1.1"></a>

System properties are entered as Java command arguments between `java` and `-jar`.

For example, if you want to apply the `Plazma.dummyProperty` system property, entering as follows initializes Plazma with `37` in the next property.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indicates that the argument is an exclusive argument added to Plazma, not inherent to JVM,

and if no value is entered, the value is fixed to [`true.`](#user-content-fn-3)[^3]

{% hint style="info" %}

### The Paperweight series server platform includes a `.` in the property name to distinguish system properties for each platform.

In some terminals like Windows Powershell, these arguments may not be allowed, so `"` should be added to both ends of the argument.

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

### The `/reload` command is very unstable, so all issues occurring after `/reload` are the responsibility of the user.

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

Disables the limit of 128 plugin channels per player.

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

Disables Java version check.

{% hint style="danger" %}

### This may allow JVM to attempt to access non-existent code!

World and overall files can be permanently corrupted, breaking the game's entire mechanics.

Any issues that arise from using this are the user's responsibility, and Plamza does not provide any support for it.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Integer`
- **Default**: `64`

Sets the limit of plugin channel names.

#### `Paper.maxSignLength`

- **Type**: `Integer`
- **Default**: `80`

Sets the maximum length of characters that can be entered on a sign line.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Integer`
- **Default**: `(world version) + 1`

Sets the version of initial world update information to be initialized first.

Useful when a large number of chunks need to be updated, but otherwise not used.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Default**: `True`

Enables processing of comments in YAML files.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Integer`
- **Default**: `30`

Kicks players if no data is received from them for the specified time (in seconds).

Normally, the game[^7] continuously sends [heartbeat signals](#user-content-fn-8)[^8] to the server, so players are not kicked, but if the game stops responding, it is considered crashed and the player is kicked without further processing on the server.

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

{% hint style="warning" %}

### This property will be moved to startup arguments after 1.20.5.

{% endhint %}

Applies more stringent configuration optimizations at initial startup.

Activating it makes the server faster and more secure, but it may block some gimmicks or have a significant impact on game play.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Default**: `false`

Suppresses the warning[^11] displayed when Plazma is initialized.

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

Starts the server with a demo world.

#### `eraseCache`

Removes leftover cache files after world upgrades.

#### `forceUpgrade`

Forces an upgrade of the world, ignoring the version.

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

Sets the maximum number of allowed [players](#user-content-fn-14).

#### `nogui`

Disables the graphical interface panel.

#### `nojline`

Disables JLine and uses vanilla console.

#### `online-mode`

- **Alias**: `o`
- **Default**: `(server properties)`

Selects whether to authenticate players with Mojang authentication servers.

**Sanctions may apply for violating the [EULA](../getting-started/README.md#id-5) if not using Velocity or other proxies.**

#### `paper-settings`

- **Alias**: `paper`
- **Default**: `paper.yml`

{% hint style="warning" %}

### This argument has been deprecated since 1.19.4

{% endhint %}

Sets the location of the deprecated PaperSpigot configuration file.

Used to transfer existing configurations to new configuration files, and not used afterwards.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Default**: `config`

Sets the name and location of the folder containing the [Paper configuration files](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Sets the name and location of the folder containing the [Plazma configuration files](../reference/configurations/plazma/README.md).

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

Starts the server in a completely vanilla state (Safe Mode).

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

[^13]: Internet Protocol, IP.

[^14]: Excluding administrators `level 2` and above.
