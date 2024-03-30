---
description: Plazma로 직접 자신만의 서버를 만들어 보세요.
---

# 시작하기

{% hint style="warning" %}
Plazma를 사용하기 위해선 x64, JRE 17 이상이어야 합니다.

안정적이고 쾌적한 경험을 위하여, JRE 21을 사용하는것을 권장합니다.
{% endhint %}

## 1. JRE 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JRE[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JRE를 설치해야 합니다.

### 1.1 JRE 유무 확인

JRE가 시스템에 설치되어 있는지 확인하려면,

* Windows
  * [실행 창](#user-content-fn-3)[^3]에 `cmd /k java --version`을 입력하고 실행합니다.
* Linux/macOS 및 기타 준 UNIX 체계
  * 터미널에서 `java --version` 을 실행합니다.

다음과 같이 출력되면 2단락으로 건너뜁니다.

```log
TODO
```

위와 같이 출력되지 않거나, 다음과 같이 출력되면 JRE가 없거나 너무 오래되었으므로, 1.2단락을 수행해야 합니다.

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

```log
TODO
```

### 1.2 JRE 설치

본 가이드에서는 JRE의 종류[^4] 중 하나로 Azul Zulu를 사용합니다.

설치를 완료한 후, 1.1단락을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

#### Windows
1. 먼저, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts&os=windows&architecture=x86-64-bit&package=jdk#zulu) 에서 **JDK 21**을 `.msi` 형태로 다운로드 합니다.
2. 다운로드된 설치 마법사를 실행하고, `다음`을 클릭합니다.
3. **__창 좌측 중앙에 표시되는 메뉴에서 `Set JAVA_HOME variable`을 활성화[^5] 한 후,__** `다음`을 클릭합니다.
4. `설치`를 눌러 JRE 설치를 `완료`합니다.

#### macOS
1. 먼저, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts&os=macos&architecture=x86-64-bit&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태로 다운로드 합니다.
2. 다운로드된 설치 마법사를 실행하여 JRE를 설치합니다.

#### Linux (Ubuntu/Debian 계열, APT)

먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

그런 다음, 다음 명령어를 터미널에서 실행하여 JRE를 설치합니다.

{% hint style="info" %}
본 가이드에서는 리눅스 환경에 창 관리자가 설치되어 있지 않음을 가정하고 작성되었습니다.

GUI 환경을 사용하려면 `-headless` 를 제거하세요.
{% endhint %}

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

#### Linux (Fedora/RHEL 계열, DNF)

다음 명령어를 입력하여 JRE를 설치할 수 있습니다.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

[^1]: Java Runtime Environment, Java 실행 환경.

[^2]: Plazma의 기반 Paper는 Spigot을 기반으로 하며, Spigot이 공식 서버 플랫폼을 기반으로 합니다.

[^3]: Windows 키 + R

[^4]: JRE는 오픈 소스로, Minecraft처럼 여러 가지 실행 환경이 존재합니다.

[^5]: 꽃표(X)가 아닌 다른 아이콘(일반적으로 상하단과 같은 아이콘)을 선택합니다.
