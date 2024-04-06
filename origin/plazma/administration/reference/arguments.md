---
description: 시작 인수와 시스템 속성에 대해 알아보세요.
---

# 🎛️ 인수와 속성

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## 시스템 속성 <a href="#id-1" id="id-1"></a>

시스템 속성은 `-jar` 앞에 입력되어 Plazma가 초기화 되기 전 JVM에서 처리되는 값입니다.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### 사용 방법 <a href="#id-1.1" id="id-1.1"></a>

시스템 속성은 `java` 와 `-jar` 사이에 Java 명령 인수로써 입력됩니다.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`는 해당 인수가 JVM에 내장되지 않고 Plazma에 추가된 전용 인수임을 나타내며,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정](#user-content-fn-3)[^3]됩니다.

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야](#user-content-fn-4)[^4] 합니다.

{% endhint %}

### 전체 시스템 속성 <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

* **형태**: `Boolean`
* **기본값**: `False`

사용 중지된 표지판 포맷을 업데이트 합니다.

#### `debug.entities`

* **형태**: `Boolean`
* **기본값**: `False`

엔티티 정보 관련 디버그 로그를 활성화 합니다.

#### `debug.rewriteForIDE`

* **형태**: `Boolean`
* **기본값**: `False`

IDE에서 디버그 정보를 올바르게 불러올 수 있도록 NMS 리비전을 비활성화 하고,\
내부 버전 정보를 자동으로 리맵합니다.

#### `disable.watchdog`

* **형태**: `Boolean`
* **기본값**: `False`

Spigot의 Watchdog 경고 시스템을 비활성화 합니다.

#### `letMeReload`

* **형태**: `Boolean`
* **기본값**: `False`

`/reload` 명령어의 재확인 메세지를 비활성화 합니다.

{% hint style="danger" %}

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

플러그인 개발자이고 플러그인을 업데이트 해야 하는 경우, `/reload` 대신 핫스왑을 사용하세요.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

* **형태**: `Boolean`
* **기본값**: `False`

표준 입출력 체계를 사용하는 플러그인을 비활성화 합니다.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

* **형태**: `Boolean`
* **기본값**: `False`

채팅 컴포넌트에서 사용 중단된 포맷이 감지되면 경고합니다.

#### `Paper.bypassHostCheck`

* **형태**: `Boolean`
* **기본값**: `False`

플레이어가 서버에 접속할 때 서버의 패턴 일치 검증을 비활성화 합니다.

#### `Paper.debugDynamicMissingKeys`

* **형태**: `Boolean`
* **기본값**: `False`

NBT 오브젝트에서 누락된 키에 대한 디버그 로그를 활성화 합니다.

#### `Paper.debugInvalidSkullProfiles`

* **형태**: `Boolean`
* **기본값**: `False`

잘못된 프로필 정보를 가진 머리 블록의 디버그 로그를 활성화 합니다.

이는 월드 내 모든 잘못된 머리 블록을 위치와 함께 로그합니다.

#### `Paper.disableChannelLimit`

* **형태**: `Boolean`
* **기본값**: `False`

플레이어당 적용되는 128개의 플러그인 [채널](#user-content-fn-5)[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

* **형태**: `Boolean`
* **기본값**: `False`

플러그인 클래스 우선 순위 체계를 비활성화 합니다.

플러그인 셰이드에서 문제가 발생한 경우 유용합니다.

#### `Paper.disableFlushConsolidate`

* **형태**: `Boolean`
* **기본값**: `False`

Netty flush consolidation 체계를 비활성화 합니다.

#### `Paper.excessiveTELimit`

* **형태**: `Integer`
* **기본값**: `750`

엔티티가 설정된 값보다 많으면 다중 패킷으로 분할하여 전송합니다.

#### `Paper.filterThreshold`

* **형태**: `Integer`
* **기본값**: `8192`

서버가 한 번에 받을 수 있는 최대 패킷의 크기를 설정합니다.

#### `Paper.ignoreJavaVersion`

* **형태**: `Boolean`
* **기본값**: `False`

Java 버전 확인을 비활성화 합니다.

{% hint style="danger" %}

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

월드 등 전반적인 파일이 영구적으로 손상될 수 있으며, 게임의 전체 메커니즘이 망가지게 됩니다.

이를 사용하여 발생한 모든 문제는 본인이 책임지며, Plamza는 이에 대한 아무런 지원을 하지 않습니다.

{% endhint %}

#### `Paper.maxCustomChannelName`

* **형태**: `Integer`
* **기본값**: `64`

플러그인 [채널](#user-content-fn-5)[^5] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

* **형태**: `Integer`
* **기본값**: `80`

표지판의 한 줄에 입력 가능한 글자의 최대 길이를 설정합니다.

#### `Paper.minPrecachedDatafixVersion`

* **형태**: `Integer`
* **기본값**: `(월드 버전) + 1`

먼저 초기화할 월드 업데이트 정보의 버전을 설정합니다.

대량의 청크를 업데이트 해야 하는 경우 유용하지만, 그 외에 경우 사용되지 않습니다.

#### `Paper.parseYamlCommentsByDefault`

* **형태**: `Boolean`
* **기본값**: `True`

YAML 파일의 주석의 처리를 활성화 합니다.

#### `Paper.playerConnection.keepAlive`

* **형태**: `Integer`
* **기본값**: `30`

플레이어에게서 입력된 값(초) 만큼 아무런 데이터도 전송 받지 못했을 때, 플레이어를 추방합니다.

일반적인 경우, [게임](#user-content-fn-7)[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

* **형태**: `Boolean`
* **기본값**: `False`

서버 속성의 주석을 무시합니다.

#### `Paper.debug-sync-loads`

* **형태**: `Boolean`
* **기본값**: `False`

동기 청크 작성의 디버그 로그를 활성화 합니다.

#### `Paper.enable-sync-chunk-writes`

* **형태**: `Boolean`
* **기본값**: `False`

Minecraft의 [기본 청크 작성 체계](#user-content-fn-10)[^10]을 활성화 합니다.

이는 각 청크를 저장하는 것을 순서대로 진행하므로, 굉장한 성능 저하를 유발합니다.

#### `Paper.explicit-flush`

* **형태**: `Boolean`
* **기본값**: `False`

네트워크 채널의 Explicit Flushing을 활성화 합니다.

#### `Paper.strict-thread-checks`

* **형태**: `Boolean`
* **기본값**: `False`

메인 스레드에서 발생하지 않은 오류를 항상 로그합니다.

#### `Paper.tickList-warn-on-excessive-delay`

* **형태**: `Boolean`
* **기본값**: `False`

예약된 작업이 과도한 대기 시간을 가질 경우 경고를 출력합니다.

#### `Paperclip.patchOnly`

* **형태**: `Boolean`
* **기본값**: `False`

기본 제공되는 실행 파일을 사용하는 경우, 서버를 시작하지 않고 패치만 적용합니다.

#### `Plazma.aggressiveOptimize`

* **형태**: `Boolean`
* **기본값**: `false`

{% hint style="warning" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

처음 시작시 적용되는 구성 최적화를 더 엄격하게 적용합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 일부 기믹을 차단하거나 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.iKnowWhatIAmDoing`

* **형태**: `Boolean`
* **기본값**: `false`

Plazma가 초기화될 때 출력되는 [경고문](#user-content-fn-11)[^11]을 억제합니다.

### 사용 중단된 속성 <a href="#id-1.3" id="id-1.3"></a>

아래 시스템 속성은 사용이 중단된 속성입니다.

#### `timings.bypassMax`

* **형태**: `Boolean`
* **기본값**: `false`
* **사용 중단됨**: Timings가 Plazma에서 전면 제거된 후 부터

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

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

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
