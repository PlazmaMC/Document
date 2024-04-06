---
description: Learn about the start arguments and system properties, me hearties.
---

# 🎛️ Arguments and Properties

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[Location to add to the command](#user-content-fn-2)[^2] will be divided into **start arguments** and **system properties** according to the instructions.

***

## System properties <a href="#id-1" id="id-1"></a>

System properties be values processed by the JVM before Plazma be initialized and entered before `-jar`, matey.

{% hint style="warning" %}

**If ye be alterin' system attributes, it may change th' operation o' Plazma an' JVM, an' could have a major impact on th' game!**

If ye be not sure what each system attribute does, **never use it!**

{% endhint %}

### How to use <a href="#id-1.1" id="id-1.1"></a>

System properties be entered as Java command arguments between `java` and `-jar`, me hearties.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` signifies that the argument be not embedded in the JVM but be an additional argument exclusive to Plazma, arrr,

If no value is entered for the property, the value will be fixed as [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Paperweight series server platform be includin' a `.` in th' attribute name t' differentiate system attributes fer each platform.**

In some terminals such as Windows Powershell, these arguments may not be allowed, so `"` must be added to the ends of the arguments.[^4]

{% endhint %}

### All system properties <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Type**: `Boolean`
- **Default Value**: `False`

Updates discontinued sign formats, arrr.

#### `debug.entities`

- **Type**: `Boolean`
- **Default Value**: `False`

Enables debug logging related to entity information, matey.

#### `debug.rewriteForIDE`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables NMS revision to enable proper loading of debug information in the IDE, arrr, and automatically remaps internal version information, arrr.

#### `disable.watchdog`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables the Spigot Watchdog warning system, me hearties.

#### `letMeReload`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables the confirmation message for the `/reload` command, arrr.

{% hint style="danger" %}

**`/reload` command be very unstable, so any issues occurrin' in th' server after usin' `/reload` be on th' user themselves.**

If ye be a plugin developer and need to update a plugin, use hotswapping instead of `/reload`, arrr.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolean`
- **Default Value**: `False`

Disables plugins using the standard input/output system, arrr.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolean`
- **Default Value**: `False`

Issues a warning when legacy formatting be detected in chat components, arrr.

#### `Paper.bypassHostCheck`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables server pattern matching verification when players connect to the server, arrr.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolean`
- **Default Value**: `False`

Enables debug logging for missing keys in NBT objects, me hearties.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolean`
- **Default Value**: `False`

Enables debug logging for head blocks with invalid profile information, arrr.

Logs all invalid head blocks within the world with their locations, arrr.

#### `Paper.disableChannelLimit`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables the limit of 128 plugin [channels](#user-content-fn-5)[^5] applied per player.

#### `Paper.disableClassPrioritization`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables the plugin class prioritization system, arrr.

Useful if issues arise from plugin shading, arrr.

#### `Paper.disableFlushConsolidate`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables the Netty flush consolidation system, arrr.

#### `Paper.excessiveTELimit`

- **Type**: `Integer`
- **Default Value**: `750`

Splits entities into multiple packets for transmission if they exceed the set value, arrr.

#### `Paper.filterThreshold`

- **Type**: `Integer`
- **Default Value**: `8192`

Sets the maximum packet size the server can receive at once, arrr.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables Java version checking, me hearties.

{% hint style="danger" %}

**This may allow JVM t' attempt accessin' non-existent code!**

This could permanently damage world files and overall game mechanics, arrr.

Any issues caused by this be the responsibility of the user, and Plamza provides no support for it, arrr.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Integer`
- **Default Value**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Type**: `Integer`
- **Default Value**: `80`

Sets the maximum length of characters that can be entered on one line of a sign, arrr.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Integer`
- **Default Value**: `(world version) + 1`

Sets the version of world update information to initialize first, arrr.

Useful when needing to update large amounts of chunks but otherwise not used, arrr.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Default Value**: `True`

Enables processing of comments in YAML files, arrr.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Integer`
- **Default Value**: `30`

If a player does not receive any data for the set amount of time in seconds, they be kicked from the server, arrr.

In general, the [game](#user-content-fn-7)[^7] will continue to send [heartbeat signals](#user-content-fn-8)[^8] to the server, so players are not [kicked,](#user-content-fn-9)[^9] but if the game does not respond, it is considered a crash and the server will no longer handle the player and kick them.

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolean`
- **Default Value**: `False`

Ignores comments in server properties, arrr.

#### `Paper.debug-sync-loads`

- **Type**: `Boolean`
- **Default Value**: `False`

Enables debug logging for synchronous chunk loading, arrr.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolean`
- **Default Value**: `False`

Enables Minecraft's [default chunk writing system](#user-content-fn-10)[^10], matey.

This saves each chunk in order, causing significant performance degradation, arrr.

#### `Paper.explicit-flush`

- **Type**: `Boolean`
- **Default Value**: `False`

Enables Explicit Flushing for network channels, arrr.

#### `Paper.strict-thread-checks`

- **Type**: `Boolean`
- **Default Value**: `False`

Always logs errors that occur outside the main thread, arrr.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolean`
- **Default Value**: `False`

Outputs a warning if scheduled tasks have excessive wait times, arrr.

#### `Paperclip.patchOnly`

- **Type**: `Boolean`
- **Default Value**: `False`

When using the default provided executable, only applies patches without starting the server, arrr.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolean`
- **Default Value**: `false`

{% hint style="warning" %}

**This attribute be movin' t' start arguments after 1.20.5.**

{% endhint %}

Applies more stringent configuration optimization at the beginning, me hearties.

When activated, the server becometh faster and safer, but may blocketh some glitches or have a great impact on game play.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Default Value**: `false`

Suppresses the warning message displayed when Plazma is initialized.[^11]

### Discontinued booty <a href="#id-1.3" id="id-1.3"></a>

Below system booty be a discontinued booty.

#### `timings.bypassMax`

- **Type**: `Boolean`
- **Default Value**: `false`
- **Abandoned**: Timings bein' removed from Plazma front-end since

Determines if it be acceptable t' exceed th' maximum value that can be sent t' Aikar's Timings API.

Even if done so, if not handled by th' API, rate limitin' be applied.

***

## Startin' Arguments <a href="#id-2" id="id-2"></a>

Startin' Arguments be input after `-jar *.jar` fer Plazma initialization an' be processed together with it.

### Usin' Method <a href="#id-2.1" id="id-2.1"></a>

System properties be input as program command arguments after `-jar *.jar`.

For example, if ye be tryin' t' apply th' `nogui` startin' argument,\
enterin' as follows will make Plazma process th' `nogui` argument durin' initialization.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Total Startin' Arguments <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Default**: `bukkit.yml`

Sets th' name an' location of [Bukkit Configuration File](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Default**: `commands.yml`

Sets th' name an' location of [Bukkit Command Configuration File](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Default**: `server.properties`

Sets th' name an' location of [Server Properties](../reference/configurations/property.md) file.

#### `demo`

Starts th' server with a demo world.

#### `eraseCache`

Removes any leftover cache files after world upgrade.

#### `forceUpgrade`

Forces an upgrade o' th' world, ignorin' th' version.

#### `help`

- **Alias**: `?`

Displays Plazma's total startin' arguments an' descriptions.

#### `initSettings`

Only generates configuration files an' shuts down th' server.

#### `jfrProfile`

Enables JFR profiling.

#### `max-players`

- **Alias**: `s`, `size`
- **Default**: `(Server Properties)`

Sets th' maximum number o' [players](#user-content-fn-14).

#### `nogui`

Disables th' graphical interface panel.

#### `nojline`

Disables JLine an' uses vanilla console.

#### `online-mode`

- **Alias**: `o`
- **Default**: `(Server Properties)`

Chooses whether t' authenticate players with Mojang authentication servers.

**If not usin' Velocity or other proxies, may be sanctioned fer violatin' [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Default**: `paper.yml`

{% hint style="warning" %}

**This argument be deprecated after 1.19.4**

{% endhint %}

Sets th' location o' th' deprecated PaperSpigot configuration file.

This be used t' migrate existin' configurations t' a new configuration file an' be not used thereafter.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Default**: `config`

Sets th' name an' location o' th' folder where [Paper Configuration File](../reference/configurations/paper/README.md) be located.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Sets th' name an' location o' th' folder where [Plazma Configuration File](../reference/configurations/plazma/README.md) be located.

#### `plugins`

- **Alias**: `p`
- **Default**: `plugins`

Sets th' location o' th' plugin folder.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Default**: `pufferfish.yml`

Sets th' name an' location of [Pufferfish Configuration File](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Default**: `purpur.yml`

Sets th' name an' location of [Purpur Configuration File](../reference/configurations/purpur/README.md).

#### `safeMode`

Starts th' server in a complete vanilla state (safe mode).

#### `server-ip`

- **Alias**: `h`, `host`
- **Default**: `(Server Properties)`

Sets th' host name or [Internet Protocol](#user-content-fn-13) address of th' server.

#### `server-port`

- **Alias**: `p`, `port`
- **Default**: `(Server Properties)`

Sets th' port o' th' server.

#### `server-name`

- **Default**: `A Plazma Server`

Sets th' name o' th' server.

#### `spigot-settings`

- **Alias**: `S`
- **Default**: `spigot.yml`

Sets th' name an' location of [Spigot Configuration File](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Outputs th' Plazma version.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Default**: `(Server Folder)`

Sets th' location where world files be stored.

#### `world-name`

- **Alias**: `w`, `world`
- **Default**: `(Server Properties)`

Sets th' name o' th' world file.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Position where arguments be processed changes dependin' on where they be appended.

[^3]: For example, if ye be wantin' t' set (enable) `Plazma.iKnowWhatIAmDoing` t' `true`, enterin' `-DPlazma.iKnowWhatIAmDoing=true` be th' same as enterin' `-DPlazma.iKnowWhatIAmDoing`.

[^4]: For example, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Event detector.

[^6]: Event detector.

[^7]: Matey.

[^8]: Signal notifying that ye be properly connected to the server like a heartbeat.

[^9]: Using Purpur's AFK bootin' feature, ye can boot players who be away from their seats.

[^10]: Sync Chunk Write System, Matey.

[^11]: `WARNING! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.`

[^12]: In the game, `world optimization` also operates on the same principle.

[^13]: Internet Protocol, IP.

[^14]: `Level 2` or higher administrators are excluded.
