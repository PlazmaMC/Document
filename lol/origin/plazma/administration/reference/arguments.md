---
description: Sturtz lurnin' abowt startin' args n' system properteez.
---

# 🎛️ Args n' properteez

시작 인수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로, Plazma의 작동에 전반적인 영향을 줍니다.

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## System properteez <a href="#id-1" id="id-1"></a>

System properteez be values processed in JVM afore Plazma initializes in front o' `-jar`.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Usage <a href="#id-1.1" id="id-1.1"></a>

System properteez be inputted as Java command args between `java` n' `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indicates the arg be fer Plazma n' not built int' JVM,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정](#user-content-fn-3)[^3]됩니다.

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Default**: `750`

If entities exceed set value, they be split into multiple packets fer transmission.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Default**: `8192`

Sets size o' largest packet server can receive at once.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Default**: `False`

Disables Java version verification.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Worlds n' overall files can be permanently damaged, n' game mechanics can break down.

Any issues caused by this be yer responsibility, n' Plamza don't provide any support fer it.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Default**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Default**: `80`

Sets max length o' characters that can be entered on one line o' sign.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Default**: `(world version) + 1`

Sets version o' initial world update info t' initialize.

Useful when large chunk updates be needed, but not used otherwise.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Default**: `True`

Enables processin' o' comments in YAML files.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Default**: `30`

If player doesn't receive any data fer inputted time (seconds), they be kicked.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **CRASH**: `Plazma.disableConfigOptimization`

initial config gets optimirezd stronker

wen activated, server gets faster n' safur but can haz big impact on game play

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolean`
- **Default**: `false`
- **CRASH**: `Plazma.aggressiveOptimize`

does not optimirez initial config

dis uses Paper's default config

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Default**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolean`
- **Default**: `false`

disables Plazma brandin n uses vanilla base server favicon

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolean`
- **Default**: `false`
- **CRASH**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

can haz big impact on server safur n performance

any issues caused by using dis attribute is on server admin
{% endhint %}

provides initial config wit default values provided by Mojang

disables all vulnerability patches applied by Paper

vulnerability patches can be re-enabled in Paper config or Plazma config

#### `Plazma.vanillaize`

- **Type**: `Boolean`
- **default**: `true`
- **CRASH**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

sets initial config closer to vanilla

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **별칭**: `c`
- **기본값**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **별칭**: `c`
- **기본값**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

데모 월드로 서버를 시작합니다.

#### `eraseCache`

월드 업그레이드 후 남은 캐시 파일을 제거합니다.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

그래픽 인터페이스 패널을 비활성화 합니다.

#### `nojline`

JLine을 비활성화 하고 바닐라 콘솔을 사용합니다.

#### `online-mode`

- **별칭**: `o`
- **기본값**: `(서버 속성)`

Mojang 인증 서버로 플레이어를 검증할지 선택합니다.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **별칭**: `paper`
- **기본값**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

사용 중지된 PaperSpigot 구성 파일의 위치를 설정합니다.

이는 기존 구성을 새 구성 파일로 이전하기 위해 사용되며, 그 이후에는 사용되지 않습니다.

#### `paper-settings-directory`

- **별칭**: `paper-dir`
- **기본값**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **별칭**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **별칭**: `p`
- **기본값**: `plugins`

플러그인 폴더의 위치를 설정합니다.

#### `pufferfish-settings`

- **별칭**: `pufferfish`
- **기본값**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **별칭**: `purpur`
- **기본값**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

(안전 모드) 완전한 바닐라 상태로 서버를 시작합니다.

#### `server-ip`

- **별칭**: `h`, `host`
- **기본값**: `(서버 속성)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: `레벨 2` 이상의 관리자는 제외합니다.

[^14]: Internet Protocol, IP.
