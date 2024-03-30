---
description: 시작 인수와 시스템 속성에 대해 알아보세요.
---

# 🔄️ 인수와 속성

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,\
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[명령어에 덧붙이는 위치에](#user-content-fn-2)[^2] 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

## 시스템 속성 <a href="#id-1" id="id-1"></a>

시스템 속성은 `-jar` 앞에 입력되어 Plazma가 초기화 되기 전 JVM에서 처리되는 값입니다.

{% hint style="warning" %}

시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### 사용 방법 <a href="#id-1.1" id="id-1.1"></a>

시스템 속성은 `java` 와 `-jar` 사이에 Java 명령 인수로써 입력됩니다.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,\
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`는 해당 인수가 JVM에 내장되지 않고 Plazma에 추가된 전용[^3] 인수임을 나타내며,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정됩니다.](#user-content-fn-4)[^4]

{% hint style="warning" %}

Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-5)[^5]

{% endhint %}

### 전체 시스템 속성 <a href="#id-1.2" id="id-1.2"></a>

#### `Plazma.iKnowWhatIAmDoing`

- **형태**: `Boolean`
- **기본값**: `false`

Plazma가 초기화될 때 출력되는 경고문[^6]을 억제합니다.

#### `Plazma.aggressiveOptimize`

- **형태**: `Boolean`
- **기본값**: `false`

{% hint style="warning" %}

해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.

{% endhint %}

처음 시작시 적용되는 구성 최적화를 더 엄격하게 적용합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만,
일부 기믹을 차단하거나 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `letMeReload`

- **형태**: `Boolean`
- **기본값**: `False`

`/reload` 명령어의 재확인 메세지를 비활성화 합니다.

{% hint style="warning" %}

`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.

플러그인 개발자이고 플러그인을 업데이트 해야 하는 경우, `/reload` 대신 핫스왑을 사용하세요.

{% endhint %}

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnWhenLegacyFormattingDetected" id="warnWhenLegacyFormattingDetected"></a>

- **형태**: `Boolean`
- **기본값**: `False`

채팅 컴포넌트에서 사용 중단된 포맷이 감지되면 경고합니다.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **기본값**: `30`

플레이어에게서 입력된 값(초) 만큼 아무런 데이터도 전송 받지 못했을 때, 플레이어를 추방합니다.

일반적인 경우, 게임[^7]은 서버로 계속해서 하트비트[^8] 신호를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9]\
게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.disableChannelLimit`

- **형태**: `Boolean`
- **기본값**: `False`

플레이어당 적용되는 128개의 플러그인 채널(리스너)의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **형태**: `Boolean`
- **기본값**: `False`

플러그인 클래스 우선 순위 체계를 비활성화 합니다.

플러그인 셰이드에서 문제가 발생한 경우 유용합니다.

#### `Paper.disableFlushConsolidate`

- **형태**: `Boolean`
- **기본값**: `False`

Netty flush consolidation 체계를 비활성화 합니다.

#### `Paper.debugDynamicMissingKeys`

- **형태**: `Boolean`
- **기본값**: `False`

NBT 오브젝트에서 누락된 키에 대한 디버그 로그를 활성화 합니다.

### 사용 중단된 속성 <a href="#id-1.3" id="id-1.3"></a>

아래 시스템 속성은 사용이 중단된 속성입니다.

#### `timings.bypassMax`

- **형태**: `Boolean`
- **기본값**: `false`
- **사용 중단됨**: Timings가 Plazma에서 전면 제거된 후 부터

Aikar의 Timings API에 전송될 수 있는 값의 최대를 초과해도 되는지 결정합니다.

이렇게 하더라도 API에서 예외 처리되지 않으면 레이트 제한이 적용됩니다.

---

[^1]: `java (...) -jar server.jar (...)`

[^2]: 덧붙여지는 위치에 따라 인수를 처리하는 위치가 변경됩니다.

[^3]: Dedicated.

[^4]: 예를 들어, `Plazma.iKnowWhatIAmDoing`을 `true`로 설정(활성화) 하려는 경우, `-DPlazma.iKnowWhatIAmDoing=true` 대신 `-DPlazma.iKnowWhatIAmDoing` 만 입력해도 동일하게 작동합니다.

[^5]: 예를 들어, `"-DPlazma.iKnowWhatIAmDoing"`
