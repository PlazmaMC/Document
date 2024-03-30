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
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

위와 같이 출력되지 않거나, 다음과 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

### 1.2 JRE 설치 <a href="#id-1.2" id="id-1.2"></a>

본 가이드에서는 JRE의 종류[^4] 중 하나로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

<details>

<summary>Windows</summary>

1. 먼저, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts&os=windows&architecture=x86-64-bit&package=jdk#zulu) 에서 **JDK 21**을 `.msi` 형태로 다운로드 합니다.
2. 다운로드된 설치 마법사를 실행하고, `다음`을 클릭합니다.
3. **__창 좌측 중앙에 표시되는 메뉴에서 `Set JAVA_HOME variable`을 활성화[^5] 한 후,__** `다음`을 클릭합니다.
4. `설치`를 눌러 JRE 설치를 `완료`합니다.

</details>

<details>

<summary>macOS</summary>

1. 먼저, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts&os=macos&architecture=x86-64-bit&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태로 다운로드 합니다.
2. 다운로드된 설치 마법사를 실행하여 JRE를 설치합니다.

</details>

<details>

<summary>Linux (Debian, Ubuntu 등 APT 계열)</summary>

먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

그런 다음, 다음 명령어를 터미널에서 실행하여 JRE를 설치합니다.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

</details>

<details>

<summary>Linux (Fedora, RHEL 등 DNF 계열)</summary>

다음 명령어를 입력하여 JRE를 설치할 수 있습니다.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

</details>

## 2. Plazma 다운로드

## 3. 시작 스크립트 생성 <a href="#id-3" id="id-3"></a>

Plazma를 간단하게 시작하고, 서버를 자동으로 재시작 하려면, [시작 스크립트](#user-content-fn-6)[^6]를 만들어야 합니다.

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 [생성할 수 있습니다.](#user-content-fn-7)[^7]
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

좌측 하단 다운로드 버튼을 통해 시작 스크립트를 다운로드 할 수 있습니다.

이제 다운로드한 시작 스크립트와 Plazma를 새 폴더에 이동합니다.

{% hint style="warning" %}
시작 스크립트가 자신의 운영 체제와 동일한지 확인하세요.

폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.
그렇지 않으면 Plazma 또는 JRE가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

이제 시작 스크립트를 실행합니다. Windows의 경우, 방화벽 허용 선택 창이 표시되면, 반드시 **허용**을 선택해야 합니다.

[^1]: Java Runtime Environment, Java 실행 환경.

[^2]: Plazma의 기반 Paper는 Spigot을 기반으로 하며, Spigot이 공식 서버 플랫폼을 기반으로 합니다.

[^3]: Windows 키 + R

[^4]: JRE는 오픈 소스로, Minecraft처럼 여러 가지 실행 환경이 존재합니다.

[^5]: 꽃표(X)가 아닌 다른 아이콘(일반적으로 상하단과 같은 아이콘)을 선택합니다.

[^6]: 일반적으로 "구동기"라고 알려져 있습니다.

[^7]: "Auto-restart"를 활성화 하면 서버가 자동으로 재시작 됩니다. `Control + C`를 입력해 종료할 수 있습니다.

[^8]: 시스템의 절반 이상을 넘기는것은 추천되지 않습니다. 예를 들어, 시스템 전체 메모리 용량이 8GB라고 했을 때, 4GB 이상으로 설정하는것은 권장되지 않습니다.

[^9]: End-User License Agreement, 최종 사용자 사용권 계약. 자세한 내용은 [Minecraft 홈페이지](https://www.minecraft.net/ko-kr/usage-guidelines)를 확인해 주세요.

[^10]: Universal Plug & Play. Plazma에 포함된 Purpur가 이 기술을 통해 자동으로 라우터와 통신하여 서버가 실행 중일 때만 포트를 열기 때문에, 포트 포워딩을 직접 할 필요가 없습니다.
