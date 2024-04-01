---
description: Sturtz lurnin' abowt startin' args n' system properteez.
---

# 🎛️ Args n' properteez

Startin' vars n' system properteez be Plazma runnin' [commands used](#user-content-fn-1)[^1] t' append values t',
let Plazma change unchangeable values afta it be run.

Dependin' on where t' append t' commands, they be split int' **startin' args** n' **system properteez**.

***

## System properteez <a href="#id-1" id="id-1"></a>

System properteez be values processed in JVM afore Plazma initializes in front o' `-jar`.

{% hint style="warning" %}

### Changin' system properteez can alter Plazma n' JVM functionin', n' 't can 'ave a big impact on games!

If ye don' rightly know wha' each system propertee be doin', **NEVER USE IT!**
{% endhint %}

### Usage <a href="#id-1.1" id="id-1.1"></a>

System properteez be inputted as Java command args between `java` n' `-jar`.

Fer example, if ye be tryin' t' apply `Plazma.dummyProperty` system propertee,\
ye input `37` as next value, n' Plazma initializes.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indicates the arg be fer Plazma n' not built int' JVM,

If no value be inputted, value be fixed [`true`.](#user-content-fn-3)[^3]

{% hint style="info" %}

### Paperweight line o' server platforms 'ave `.` in propertee names t' differentiate system properteez per platform.

In some terminals like Windows Powershell, they may not allow these args, so ye need t' add `"` at both ends.

### All system properteez <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Type**: `Boolean`
- **Default**: `False`

Updatez deprecated sign formats.

#### `debug.entities`

- **Type**: `Boolean`
- **Default**: `False`

Enablez entity info debug logs.

#### `debug.rewriteForIDE`

- **Type**: `Boolean`
- **Default**: `False`

Disablez NMS revision t' correctly load debug info in IDE, n' automatically remaps internal version info.

#### `disable.watchdog`

- **Type**: `Boolean`
- **Default**: `False`

Disablez Spigot's Watchdog warnin' system.

#### `letMeReload`

- **Type**: `Boolean`
- **Default**: `False`

Disablez reconfirmation message o' `/reload` command.

{% hint style="danger" %}

### `/reload` command be very unstable, so any issues occurrin' after `/reload` be yer responsibility.

If ye be a plugin developer n' need t' update plugins, use hotswap instead o' `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolean`
- **Default**: `False`

Disablez plugins usin' standard input-output system.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolean`
- **Default**: `False`

Warns when discontinued format be detected in chat component.

#### `Paper.bypassHostCheck`

- **Type**: `Boolean`
- **Default**: `False`

Disablez server's pattern match verification when player connects.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolean`
- **Default**: `False`

Enablez debug logs fer missin' keys in NBT objects.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolean`
- **Default**: `False`

Enablez debug logs fer head blocks with invalid profiles.

This logs all invalid head blocks in world with their locations.

#### `Paper.disableChannelLimit`

- **Type**: `Boolean`
- **Default**: `False`

Disablez limit o' 128 plugin channels per player.[^5]

#### `Paper.disableClassPrioritization`

- **Type**: `Boolean`
- **Default**: `False`

Disablez plugin class prioritization system.

Useful when issues occur in plugin shade.

#### `Paper.disableFlushConsolidate`

- **Type**: `Boolean`
- **Default**: `False`

Disablez Netty flush consolidation system.

#### `Paper.excessiveTELimit`

- **Type**: `Integer`
- **Default**: `750`

If entities exceed set value, they be split into multiple packets fer transmission.

#### `Paper.filterThreshold`

- **Type**: `Integer`
- **Default**: `8192`

Sets size o' largest packet server can receive at once.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Default**: `False`

Disables Java version verification.

{% hint style="danger" %}

### This allows JVM t' attempt access t' non-existent code!

Worlds n' overall files can be permanently damaged, n' game mechanics can break down.

Any issues caused by this be yer responsibility, n' Plamza don't provide any support fer it.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Integer`
- **Default**: `64`

Sets limit on plugin channel[^6] names.

#### `Paper.maxSignLength`

- **Type**: `Integer`
- **Default**: `80`

Sets max length o' characters that can be entered on one line o' sign.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Integer`
- **Default**: `(world version) + 1`

Sets version o' initial world update info t' initialize.

Useful when large chunk updates be needed, but not used otherwise.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Default**: `True`

Enables processin' o' comments in YAML files.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Integer`
- **Default**: `30`

If player doesn't receive any data fer inputted time (seconds), they be kicked.

Normally, game[^7] keeps sendin' [heartbeat signal](#user-content-fn-8)[^8] t' server, so they don't get kicked, but if game stops respondin', server assumes crash n' kicks player without further processin'.

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolean`
- **Default**: `False`

Ignores comments in server properties.

#### `Paper.debug-sync-loads`

- **Type**: `Boolean`
- **Default**: `False`

Enables debug logs fer synchronized chunk writes.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolean`
- **Default**: `False`

Enables Minecraft's [default chunk writing system](#user-content-fn-10)[^10].

This writes each chunk sequentially, causin' significant performance degradation.

#### `Paper.explicit-flush`

- **Type**: `Boolean`
- **Default**: `False`

Enables Explicit Flushing o' network channels.

#### `Paper.strict-thread-checks`

- **Type**: `Boolean`
- **Default**: `False`

Always logs errors not occurin' in main thread.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolean`
- **Default**: `False`

Outputs warnin' if scheduled task has excessive wait time.

#### `Paperclip.patchOnly`

- **Type**: `Boolean`
- **Default**: `False`

If usin' default provided executin' file, only apply patch without startin' server.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolean`
- **Default**: `false`

{% hint style="warning" %}

### This property be movin' t' startin' args after 1.20.5.

{% endhint %}

Applies stricter initial configuration optimization durin' first start.

HAI WEN ACTIVAYT, SERVER GETS FASTER AN SAFER, BUT MAY BLOCK SUM MECHANICS OR HAS BIG IMPACT ON GAMEPLAY.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Default**: `false`

PLAZMA WEN INITIALIZES, HALTS WARNING MESSAGE[^11].

### 사용 중단된 속성 <a href="#id-1.3" id="id-1.3"></a>

아래 시스템 속성은 사용이 중단된 속성입니다.

#### `timings.bypassMax`

- **Type**: `Boolean`
- **Default**: `false`
- **사용 중단됨**: Timings가 Plazma에서 전면 제거된 후 부터

Aikar의 Timings API에 전송될 수 있는 값의 최대를 초과해도 되는지 결정합니다.

이렇게 하더라도 API에서 예외 처리되지 않으면 레이트 제한이 적용됩니다.

***

## 시작 인수 <a href="#id-2" id="id-2"></a>

시작 인수는 `-jar *.jar` 뒤에 입력되어 Plazma가 초기화되며 함께 처리되는 값입니다.

### 사용 방법 <a href="#id-2.1" id="id-2.1"></a>

시스템 속성은 `-jar *.jar` 뒤에 프로그램 명령 인수로써 입력됩니다.

예를 들어, `nogui` 시작 인수를 적용하려 하는 경우,\
다음과 같이 입력하면 Plazma가 초기화 중에 `nogui` 인수를 처리하게 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### 전체 시작 인수 <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **별칭**: `b`
- **기본값**: `bukkit.yml`

[Bukkit 구성 파일](../reference/configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **별칭**: `c`
- **기본값**: `commands.yml`

[Bukkit 명령어 구성 파일](../reference/configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **별칭**: `c`
- **기본값**: `server.properties`

[서버 속성](../reference/configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

데모 월드로 서버를 시작합니다.

#### `eraseCache`

월드 업그레이드 후 남은 캐시 파일을 제거합니다.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 [업그레이드](#user-content-fn-12)[^12] 합니다.

#### `help`

- **별칭**: `?`

Plazma의 전체 시작 인수와 설명을 출력합니다.

#### `initSettings`

구성 파일만 생성하고 서버를 종료합니다.

#### `jfrProfile`

JFR 프로필링을 활성화 합니다.

#### `max-players`

- **별칭**: `s`, `size`
- **기본값**: `(서버 속성)`

허용되는 최대 [플레이어](#user-content-fn-14)[^14] 수를 설정합니다.

#### `nogui`

그래픽 인터페이스 패널을 비활성화 합니다.

#### `nojline`

JLine을 비활성화 하고 바닐라 콘솔을 사용합니다.

#### `online-mode`

- **별칭**: `o`
- **기본값**: `(서버 속성)`

Mojang 인증 서버로 플레이어를 검증할지 선택합니다.

**Velocity 등 프록시를 사용하는 것이 아닌 경우 [EULA](../getting-started/README.md#id-5) 위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **별칭**: `paper`
- **기본값**: `paper.yml`

{% hint style="warning" %}

### 이 인수는 1.19.4 이후 사용이 중지되었습니다

{% endhint %}

사용 중지된 PaperSpigot 구성 파일의 위치를 설정합니다.

이는 기존 구성을 새 구성 파일로 이전하기 위해 사용되며, 그 이후에는 사용되지 않습니다.

#### `paper-settings-directory`

- **별칭**: `paper-dir`
- **기본값**: `config`

[Paper 구성 파일](../reference/configurations/paper/README.md)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **별칭**: `plazma-dir`

[Plazma 구성 파일](../reference/configurations/plazma/README.md)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **별칭**: `p`
- **기본값**: `plugins`

플러그인 폴더의 위치를 설정합니다.

#### `pufferfish-settings`

- **별칭**: `pufferfish`
- **기본값**: `pufferfish.yml`

[Pufferfish 구성 파일](../reference/configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **별칭**: `purpur`
- **기본값**: `purpur.yml`

[Purpur 구성 파일](../reference/configurations/purpur/README.md)의 이름 및 위치를 설정합니다.

#### `safeMode`

(안전 모드) 완전한 바닐라 상태로 서버를 시작합니다.

#### `server-ip`

- **별칭**: `h`, `host`
- **기본값**: `(서버 속성)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-13)[^13] 주소를 설정합니다.

#### `server-port`

- **별칭**: `p`, `port`
- **기본값**: `(서버 속성)`

서버의 포트를 설정합니다.

#### `server-name`

- **기본값**: `A Plazma Server`

서버의 이름을 설정합니다.

#### `spigot-settings`

- **별칭**: `S`
- **기본값**: `spigot.yml`

[Spigot 구성 파일](../reference/configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **별칭**: `v`

Plazma 버전을 출력합니다.

#### `world-dir`

- **별칭**: `W`, `universe`, `world-container`
- **기본값**: `(서버 폴더)`

월드 파일이 저장되는 위치를 설정합니다.

#### `world-name`

- **별칭**: `w`, `world`
- **기본값**: `(서버 속성)`

월드 파일의 이름을 설정합니다.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: 덧붙여지는 위치에 따라 인수를 처리하는 위치가 변경됩니다.

[^3]: 예를 들어, `Plazma.iKnowWhatIAmDoing`을 `true`로 설정(활성화) 하려는 경우, `-DPlazma.iKnowWhatIAmDoing=true` 대신 `-DPlazma.iKnowWhatIAmDoing` 만 입력해도 동일하게 작동합니다.

[^4]: 예를 들어, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: 이벤트 감지기.

[^6]: 이벤트 감지기.

[^7]: 클라이언트.

[^8]: 심장 박동처럼 서버와 정상적으로 연결 되어 있음을 알리는 신호.

[^9]: Purpur의 AFK 추방 기능을 사용하면 자리를 비운 플레이어도 추방할 수 있습니다.

[^10]: 동기 청크 작성 체계, Sync Chunk Write System.

[^11]: `WARNING! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.`

[^12]: 게임에서 `월드 최적화` 도 이와 같은 원리로 동작합니다.

[^13]: Internet Protocol, IP.

[^14]: `레벨 2` 이상의 관리자는 제외합니다.
