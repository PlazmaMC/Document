---
description: Learn about the start arguments and system properties, me hearties.
---

# 🎛️ Arguments and Properties

Start acquisition and system attributes be values added to Plazma execution [commands](#user-content-fn-1)[^1], impacting Plazma's operation overall.

[Location to add to the command](#user-content-fn-2)[^2] will be divided into **start arguments** and **system properties** according to the instructions.

***

## System properties <a href="#id-1" id="id-1"></a>

System properties be values processed by the JVM before Plazma be initialized and entered before `-jar`, matey.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### How to use <a href="#id-1.1" id="id-1.1"></a>

System properties be entered as Java command arguments between `java` and `-jar`, me hearties.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` signifies that the argument be not embedded in the JVM but be an additional argument exclusive to Plazma, arrr,

If no value is entered for the property, the value will be fixed as [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Default Value**: `750`

Splits entities into multiple packets for transmission if they exceed the set value, arrr.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Default Value**: `8192`

Sets the maximum packet size the server can receive at once, arrr.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Default Value**: `False`

Disables Java version checking, me hearties.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

This could permanently damage world files and overall game mechanics, arrr.

Any issues caused by this be the responsibility of the user, and Plamza provides no support for it, arrr.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Default Value**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Default Value**: `80`

Sets the maximum length of characters that can be entered on one line of a sign, arrr.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Default Value**: `(world version) + 1`

Sets the version of world update information to initialize first, arrr.

Useful when needing to update large amounts of chunks but otherwise not used, arrr.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Default Value**: `True`

Enables processing of comments in YAML files, arrr.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Default Value**: `30`

If a player does not receive any data for the set amount of time in seconds, they be kicked from the server, arrr.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Clash**: `Plazma.disableConfigOptimization`

Fortify the initial setup more.

Activating this will make the server faster and safer, but it can have a significant impact on gameplay.

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolean`
- **Default Value**: `false`
- **Clash**: `Plazma.aggressiveOptimize`

Do not optimize the initial setup.

This uses the default configuration of Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Default Value**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolean`
- **Default Value**: `false`

Disable Plazma branding and use the vanilla default server favicon.

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolean`
- **Default Value**: `false`
- **Clash**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

This can significantly impact server safety and performance.

All issues arising from this property are the responsibility of the server administrator.
{% endhint %}

Provides the initial setup with the default values provided by Mojang.

Disables all vulnerability patches applied by Paper.

Vulnerability patches can be re-enabled in the Paper configuration or Plazma configuration.

#### `Plazma.vanillaize`

- **Type**: `Boolean`
- **Default**: `true`
- **Clash**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Set up the initial configuration closer to vanilla.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

Starts th' server with a demo world.

#### `eraseCache`

Removes any leftover cache files after world upgrade.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Disables th' graphical interface panel.

#### `nojline`

Disables JLine an' uses vanilla console.

#### `online-mode`

- **Alias**: `o`
- **Default**: `(Server Properties)`

Chooses whether t' authenticate players with Mojang authentication servers.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Default**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Sets th' location o' th' deprecated PaperSpigot configuration file.

This be used t' migrate existin' configurations t' a new configuration file an' be not used thereafter.

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

Sets th' location o' th' plugin folder.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Default**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Default**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Starts th' server in a complete vanilla state (safe mode).

#### `server-ip`

- **Alias**: `h`, `host`
- **Default**: `(Server Properties)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: `Level 2` or higher administrators are excluded.

[^14]: Internet Protocol, IP.
