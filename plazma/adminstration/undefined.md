---
description: Plazma로 직접 자신만의 서버를 만들어 보세요.
---

# 시작하기

## 1. JRE 설치 <a href="#id-1" id="id-1"></a>

{% hint style="info" %}
시스템에 JRE 또는 JDK가 설치되어 있는 경우 2단락부터 시작하세요.

Plazma는 최소 JRE 17 이상이어야 하며, JRE 21을 권장하고 있습니다.
{% endhint %}

이름에서 보이다시피, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JRE[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JRE를 설치해야 합니다.

### 1.1 JRE 유무 확인 <a href="#id-1.1" id="id-1.1"></a>

JRE가 시스템에 설치되어 있는지 확인하려면,

* Windows
  * [실행 창](#user-content-fn-3)[^3]에 `cmd /k java --version`을 입력하고 실행합니다.
* Linux/macOS 및 기타 (준) UNIX 체계
  * 터미널에서 `java --version` 을 실행합니다.

다음과  같이 출력되면 2단락으로 건너뜁니다.

```log
(OpenJDK) version "21.0.1"
```

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```



[^1]: Java Runtime Environment, Java 실행 환경.

[^2]: Plazma의 기반 Paper는 Spigot을 기반으로 하며, Spigot이 공식 서버 플랫폼을 기반으로 합니다.

[^3]: Windows 키 + R
