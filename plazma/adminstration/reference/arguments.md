---
description: 시작 인수와 시스템 속성에 대해 알아보세요.
---

# 🔄️ 인수와 속성

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,\
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[명령어에 덧붙이는 위치에](#user-content-fn-2)[^2] 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

## 시스템 속성

시스템 속성은 `-jar` 앞에 입력되어 Plazma가 초기화 되기 전 JVM에서 처리되는 값입니다.

{% hint style="warning" %}

시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### 사용 방법

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

### 전체 시스템 속성

#### `Plazma.iKnowWhatIAmDoing`

- **형태**: `Boolean`
- **기본값**: `false`

Plazma가 초기화될 때 출력되는 경고문을 억제할지 결정합니다.

#### `Plazma.aggressiveOptimize`

- **형태**: `Boolean`
- **기본값**: `false`

처음 시작시 적용되는 구성 최적화를 더 엄격하게 적용할지 결정합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만,
일부 기믹을 차단하거나 게임 플레이에 큰 영향을 줄 수 있습니다.

---

[^1]: `java (...) -jar server.jar (...)`

[^2]: 덧붙여지는 위치에 따라 인수를 처리하는 위치가 변경됩니다.

[^3]: Dedicated.

[^4]: 예를 들어, `Plazma.iKnowWhatIAmDoing`을 `true`로 설정(활성화) 하려는 경우, `-DPlazma.iKnowWhatIAmDoing=true` 대신 `-DPlazma.iKnowWhatIAmDoing` 만 입력해도 동일하게 작동합니다.

[^5]: 예를 들어, `"-DPlazma.iKnowWhatIAmDoing"`
