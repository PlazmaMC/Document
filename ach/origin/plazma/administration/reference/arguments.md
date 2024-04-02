---
description: 시작 인수와 시스템 속성에 대해 알아보세요.
---

# 🎛️ 인수와 속성

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,\
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[명령어에 덧붙이는 위치에](#user-content-fn-2)[^2] 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## 시스템 속성 <a href="#id-1" id="id-1"></a>

시스템 속성은 `-jar` 앞에 입력되어 Plazma가 초기화 되기 전 JVM에서 처리되는 값입니다.

{% hint style="warning" %}

**Okiketo ki Plazma me JVM ma kicoyo atiru, onongo i giketo ma kicoyo!**

Ocako ki okiketo ki Plazma ma obedo ni ma yee, **kare dok itye!**

{% endhint %}

### 사용 방법 <a href="#id-1.1" id="id-1.1"></a>

시스템 속성은 `java` 와 `-jar` 사이에 Java 명령 인수로써 입력됩니다.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,\
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`는 해당 인수가 JVM에 내장되지 않고 Plazma에 추가된 전용 인수임을 나타내며,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정됩니다.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight me kare me server platform ma okiketo ki kare ma kicoyo, ki yee `.` ki nyingi ki okiketo.**

Windows Powershell me medo tye ki tukwan me terminal wange, onongo itye ki ikeno ki ikinnye ki `"` [tii.](#user-content-fn-4)[^4]

{% endhint %}

### 전체 시스템 속성 <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

사용 중지된 표지판 포맷을 업데이트 합니다.

#### `debug.entities`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

엔티티 정보 관련 디버그 로그를 활성화 합니다.

#### `debug.rewriteForIDE`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

IDE에서 디버그 정보를 올바르게 불러올 수 있도록 NMS 리비전을 비활성화 하고,\
내부 버전 정보를 자동으로 리맵합니다.

#### `disable.watchdog`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

Spigot의 Watchdog 경고 시스템을 비활성화 합니다.

#### `letMeReload`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

`/reload` 명령어의 재확인 메세지를 비활성화 합니다.

{% hint style="danger" %}

**`/reload` kwena ki bot bot ma itye, i /reload dong i yubu pi server, i dong i yubu me lubanga me user.**

플러그인 개발자이고 플러그인을 업데이트 해야 하는 경우, `/reload` 대신 핫스왑을 사용하세요.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

표준 입출력 체계를 사용하는 플러그인을 비활성화 합니다.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

채팅 컴포넌트에서 사용 중단된 포맷이 감지되면 경고합니다.

#### `Paper.bypassHostCheck`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

플레이어가 서버에 접속할 때 서버의 패턴 일치 검증을 비활성화 합니다.

#### `Paper.debugDynamicMissingKeys`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

NBT 오브젝트에서 누락된 키에 대한 디버그 로그를 활성화 합니다.

#### `Paper.debugInvalidSkullProfiles`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

잘못된 프로필 정보를 가진 머리 블록의 디버그 로그를 활성화 합니다.

이는 월드 내 모든 잘못된 머리 블록을 위치와 함께 로그합니다.

#### `Paper.disableChannelLimit`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

플러그인 클래스 우선 순위 체계를 비활성화 합니다.

플러그인 셰이드에서 문제가 발생한 경우 유용합니다.

#### `Paper.disableFlushConsolidate`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

Netty flush consolidation 체계를 비활성화 합니다.

#### `Paper.excessiveTELimit`

- **Cik mat**: `Integer`
- **기본값**: `750`

엔티티가 설정된 값보다 많으면 다중 패킷으로 분할하여 전송합니다.

#### `Paper.filterThreshold`

- **Cik mat**: `Integer`
- **기본값**: `8192`

서버가 한 번에 받을 수 있는 최대 패킷의 크기를 설정합니다.

#### `Paper.ignoreJavaVersion`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

Java 버전 확인을 비활성화 합니다.

{% hint style="danger" %}

**En aye JVM ma kicoyo me code ma pe i yubu!**

월드 등 전반적인 파일이 영구적으로 손상될 수 있으며, 게임의 전체 메커니즘이 망가지게 됩니다.

이를 사용하여 발생한 모든 문제는 본인이 책임지며, Plamza는 이에 대한 아무런 지원을 하지 않습니다.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Cik mat**: `Integer`
- **기본값**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Cik mat**: `Integer`
- **기본값**: `80`

표지판의 한 줄에 입력 가능한 글자의 최대 길이를 설정합니다.

#### `Paper.minPrecachedDatafixVersion`

- **Cik mat**: `Integer`
- **기본값**: `(월드 버전) + 1`

먼저 초기화할 월드 업데이트 정보의 버전을 설정합니다.

대량의 청크를 업데이트 해야 하는 경우 유용하지만, 그 외에 경우 사용되지 않습니다.

#### `Paper.parseYamlCommentsByDefault`

- **Cik mat**: `Boolean`
- **기본값**: `True`

YAML 파일의 주석의 처리를 활성화 합니다.

#### `Paper.playerConnection.keepAlive`

- **Cik mat**: `Integer`
- **기본값**: `30`

플레이어에게서 입력된 값(초) 만큼 아무런 데이터도 전송 받지 못했을 때, 플레이어를 추방합니다.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

서버 속성의 주석을 무시합니다.

#### `Paper.debug-sync-loads`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

동기 청크 작성의 디버그 로그를 활성화 합니다.

#### `Paper.enable-sync-chunk-writes`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

Minecraft의 [기본 청크 작성 체계](#user-content-fn-10)[^10]을 활성화 합니다.

이는 각 청크를 저장하는 것을 순서대로 진행하므로, 굉장한 성능 저하를 유발합니다.

#### `Paper.explicit-flush`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

네트워크 채널의 Explicit Flushing을 활성화 합니다.

#### `Paper.strict-thread-checks`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

메인 스레드에서 발생하지 않은 오류를 항상 로그합니다.

#### `Paper.tickList-warn-on-excessive-delay`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

예약된 작업이 과도한 대기 시간을 가질 경우 경고를 출력합니다.

#### `Paperclip.patchOnly`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `False`

기본 제공되는 실행 파일을 사용하는 경우, 서버를 시작하지 않고 패치만 적용합니다.

#### `Plazma.aggressiveOptimize`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `false`

{% hint style="warning" %}

**Okiketo ki i 1.20.5 ma i gengo ki i yee.**

{% endhint %}

처음 시작시 적용되는 구성 최적화를 더 엄격하게 적용합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 일부 기믹을 차단하거나 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

### 사용 중단된 속성 <a href="#id-1.3" id="id-1.3"></a>

아래 시스템 속성은 사용이 중단된 속성입니다.

#### `timings.bypassMax`

- **Cik mat**: `Boolean`
- **Kel ma kic**: `false`
- **Kicel ma kicel**: Timings ki Plazma ki ngec pe i tye ka cok

Gin ma Aikar Timings API ki i yam mek ikom ki Plazma

Keto kwede API ki i yam mek icwek i ngec pe tye ka cok, onongo kwanyo kwede ki lanyik

***

## Dwog ma en aye <a href="#id-2" id="id-2"></a>

Dwog ma en aye `-jar *.jar` ki ngec pe i tye ka cok, Plazma ki tye ka ngec me kenyo i kom

### Lok ma en aye <a href="#id-2.1" id="id-2.1"></a>

Dwog ma en aye `-jar *.jar` ki ngec pe i tye ka cok, ngom ma program ki tye ka ngec me kenyo i kom

Pi mara, `nogui` dwog ma en aye ki cok,\
ka i kom Plazma ki tye ka ngec me kenyo i kom `nogui` dwog ma en aye ki cok

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Dwog ma en aye pe <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Lok pa dano**: `b`
- **Kit ma en aye**: `bukkit.yml`

Lok ma nying [Dano me Bukkit](../reference/configurations/bukkit.md) ki tye ka cok

#### `command-settings`

- **Lok pa dano**: `c`
- **Kit ma en aye**: `commands.yml`

Lok ma nying [Dano me Bukit Kwany](../reference/configurations/bukkit.md) ki tye ka cok

#### `config`

- **Lok pa dano**: `c`
- **Kit ma en aye**: `server.properties`

Lok ma nying [Dano me Server](../reference/configurations/property.md) ki tye ka cok

#### `demo`

Dwog ma en aye kulu ki gengo me server

#### `eraseCache`

Dwog ma en aye kacel ki kare ma kacel mukene

#### `forceUpgrade`

Dwog ma en aye ki yam mek kwede mukene [Upgrde](#user-content-fn-12)[^12]

#### `help`

- **Lok pa dano**: `?`

Lok ma en aye pe kulu ki gengo me dwog ma en aye

#### `initSettings`

Dwog ma en aye ki gengo me kicel ma kicel kacel ki lobo

#### `jfrProfile`

JFR profiling ki gengo me cok

#### `max-players`

- **Lok pa dano**: `s`, `size`
- **Kit ma en aye**: `(dano me server)`

Kicel ma kicel me [Lacot](#user-content-fn-14)[^14] ki tye ka cok

#### `nogui`

Dwog ma en aye ki gengo me lok pa maleng

#### `nojline`

JLine ki gengo me lok pa maleng i yam mek mukene

#### `online-mode`

- **Lok pa dano**: `o`
- **Kit ma en aye**: `(dano me server)`

Kicel ki yam mek Mojang authentication server tye ka cok

**Kicel me Velocity dok Proksi ma kicel ma kicel [EULA](../getting-started/README.md#id-5) ki dogi ki tye ka cok.**

#### `paper-settings`

- **Lok pa dano**: `paper`
- **Kit ma en aye**: `paper.yml`

{% hint style="warning" %}

**En aye ikinnye ma i 1.19.4**

{% endhint %}

Kicel ma kicel me PaperSpigot dano ki tye ka cok

Kicel ma kicel me lok pa dano ma Plazma

#### `paper-settings-directory`

- **Lok pa dano**: `paper-dir`
- **Kit ma en aye**: `config`

Dano me [Paper](../reference/configurations/paper/README.md) ki tye ka cok ki kicel

#### `plazma-settings-directory`

- **Lok pa dano**: `plazma-dir`

Dano me [Plazma](../reference/configurations/plazma/README.md) ki tye ka cok ki kicel

#### `plugins`

- **Lok pa dano**: `p`
- **Kit ma en aye**: `plugins`

Lok ma nying me dano ki tye ka cok

#### `pufferfish-settings`

- **Lok pa dano**: `pufferfish`
- **Kit ma en aye**: `pufferfish.yml`

Dano me [Pufferfish](../reference/configurations/pufferfish.md) ki tye ka cok ki kicel

#### `purpur-settings`

- **Lok pa dano**: `purpur`
- **Kit ma en aye**: `purpur.yml`

Dano me [Purpur](../reference/configurations/purpur/README.md) ki tye ka cok ki kicel

#### `safeMode`

(Lok pa kicel) Kicel ma kicel me dok kwac me server

#### `server-ip`

- **Lok pa dano**: `h`, `host`
- **Kit ma en aye**: `(dano me server)`

Lok ma nying me dok kwac me server ki tye ka cok ki kicel

#### `server-port`

- **Lok pa dano**: `p`, `port`
- **Kit ma en aye**: `(dano me server)`

Lok ma nying me port ki tye ka cok ki kicel

#### `server-name`

- **Kit ma en aye**: `A Plazma Server`

Lok ma nying me ngom ki tye ka cok ki kicel

#### `spigot-settings`

- **Lok pa dano**: `S`
- **Kit ma en aye**: `spigot.yml`

Dano me [Spigot](../reference/configurations/spigot.md) ki tye ka cok ki kicel

#### `version`

- **Lok pa dano**: `v`

Plazma dong ki tye ka cok

#### `world-dir`

- **Lok pa dano**: `W`, `universe`, `world-container`
- **Kit ma en aye**: `(doki me server)`

Lok ma nying me doki ki tye ka cok ki kicel

#### `world-name`

- **Lok pa dano**: `w`, `world`
- **Kit ma en aye**: `(dano me server)`

Dwog ma en aye ki gengo me doki

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Keto kwede i kom ma en aye ki gengo me doki ki tye ka cok

[^3]: Pi mara, `Plazma.iKnowWhatIAmDoing` ki yam mek `true` ki dong i kom, `-DPlazma.iKnowWhatIAmDoing=true` ki tye ka cok ngene `-DPlazma.iKnowWhatIAmDoing` ki tye ka cok

[^4]: Pi mara, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Kit ma en acoya.

[^6]: Kit ma en acoya.

[^7]: Kiliyenti.

[^8]: Lok me bedo ki server ma tye ka romo itwero woko.

[^9]: Gin ma Purpur AFK kwanyo kede ki dong pe itye ka kwo kwanyo player.

[^10]: Sync Chunk Write System, Lok me gengo chunk me sync.

[^11]: `WARNING! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.`

[^12]: 게임에서 `월드 최적화` 도 이와 같은 원리로 동작합니다.

[^13]: Internet Protocol, IP.

[^14]: `레벨 2` 이상의 관리자는 제외합니다.
