---
description: Plazma로 직접 자신만의 서버를 만들어 보세요.
---

# 시작하기

## 0. 기본 요구 사항 <a href="#id-0" id="id-0"></a>

Plazma를 안정적으로 사용하기 위해선, 시스템이 다음과 같은 요구 사항을 충족해야 합니다.

|         | 최저 | 권장 |
|   ---   | ---- | --- |
| 아키텍처 | x64 |  -  |
|   RAM   | 8GB | 16GB |
| 저장공간 | 1GB | 8GB |
|   JRE   |  17 |  21 |

또한, 앞으로 파일을 열어 수정해야 하는 경우가 많아지므로, [Visual Studio Code](https://code.visualstudio.com/download)등의 편집기를 설치하는것을 권장합니다.

## 1. JRE 설치 <a href="#id-1" id="id-1"></a>

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JRE[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JRE를 설치해야 합니다.

### 1.1 JRE 유무 확인 <a href="#id-1.1" id="id-1.1"></a>

JRE가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 `cmd /k java --version`을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

```log
TODO
```

위와 같이 출력되지 않거나, 다음과 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

[^1]: Java Runtime Environment, Java 실행 환경.

[^2]: Plazma의 기반 Paper는 Spigot을 기반으로 하며, Spigot이 공식 서버 플랫폼을 기반으로 합니다.

[^3]: Windows 키 + R
