---
description: Kwon ma Plazma ki yoo kare ma server iye ki kwanyo.
---

# 👟 Cing i

Kwon ma Plazma ki tye kwede ngom me cwinywa, kadi sistema ki dong i kom bedo ma i kom.

|                 | Tye kwede | Tye kwede iye |
| :-------------: | --------- | ------------- |
|     Akitekci    | x64       | -             |
|       RAM       | 8GB       | 16GB          |
| Dano me cwinywa | 1GB       | 8GB           |
|       JDK       | 17        | 21            |

Icwinywa me kwo koni i kit ma pe ngom, [Visual Studio Code](https://code.visualstudio.com/download) me iye ma kwo yee kwanyo woko iye.

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Kicel ma kicel" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' ki i kwo woko me kic me kic, me kic matwero, kun o ma
bati file ma pe i kom.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Ka ki tye kwede ki JRE **JDK 21** me `.msi` kwede ma [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) ki download.
2. Jokkwa kwede ma gin ma, `Doki` ki cwalo.
3. **Lok me cwalo, `Set JAVA_HOME variable` ki gengo ngolo,** `Doki` ki cwalo.
4. Ki cwalo ki tye kwede JRE ki tye ki `kwede` ki tye kwede.
   {% endtab %}

{% tab title="macOS" %}
[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Kadi kwede, calo kom me tye ki terminal ki gengo JRE ki tye kwede.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}
다음 명령어를 입력하여 JDK를 설치할 수 있습니다.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma ki download

Plazma ki nyutu ma kwo poto me doki me tye kwede.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Yom me kwo</summary>

Poto me doki me kwede iyi `plazma-(kare me bedo)-1.20.4-R0.1-SNAPSHOT-(maping kacel).jar` ma onongo.

- **Maping kacel**\
  Maping iyi ni Minecraft ma kwo doki me cwiny me lukalala ki dong kwede.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Kare me bedo**\
  Kare me bedo ni doki me cwiny me server ki doki me lukalala ki dong kwede.
  - **Paperclip**\
    PaperMC timo ki yom Paper mukene ki dong kwede, kare me bedo ni kwo download ma kwo cwalo me server.
  - **Bundler**\
    Minecraft kare me bedo ki dong kwede.

</details>

***

## 3. Lok ma cwalo ki gengo

Plazma ki yom ma kwo, server ki cwalo me cwiny ma kwo, [lok ma cwalo ki gengo](#user-content-fn-6)[^6] ki tye kwede.

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Lok me tye kare dongo download ki gengo lok ma cwalo ki gengo.\
**Dongo download ki gengo tye kwede kare ma i kom yom me kare me bedo pe JRE ki tye kwede.**

***

## 4. Failo ki yom

Iyi dongo download ki gengo me Plazma ki weko i kom kwede ki tye ki tye kwede.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Iyi dongo download ki gengo me cwalo ki gengo. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA dok ma cwalo

Lok ma cwalo ki gengo, folder ki `eula.txt` ki tye kwede.

EULA[^9] ni [Mojang Studios](#user-content-fn-10)[^10] ki lok me dong ma pe tye kwede ki iye moko.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

EULA ki kwede, `eula=false` me cwalo ki `eula=true` ki i kom ma cwalo.

***

## 6. Lok me yom dok ma cwalo (Windows)

Lok ma tye, lok me yom me cwiny me cwalo, **kare me cwalo** pe **router** ki tye kwede ki dong kwede.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Router ki UPnP pe tye kwede, router ki yom ma pe tye, ngolo ma cwalo ki kwede.

Tye, [Ngrok](https://ngrok.com/) ki tye kwede ki dong kwede, ki iye moko.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Polo me fowadi ki dong kwede ki tye kwede

Lok me tye kare ma cwalo ki dong kwede ki tye kwede, ki iye moko.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Maco cwalo ki tye `Keto` ma pe tye, `Keto` me fowadi ki tye kwede ki tye kwede ki iye moko.

### 6.2 Server ki yom

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Server ki yom ma fowadi ki dong kwede ki tye kwede ki dong kwede.
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Kadi kwede, server me cwalo ki dong kwede, Plazma ki yom me fowadi ki dong kwede.

Iyi ni dok ma pe tye, UPnP mukene pe i kom iye moko, i kom iye moko, i kom iye moko, i kom iye moko, i kom iye moko.

| Dok ma pe tye                   | Kwo mukene                                                  |
| ------------------------------- | ----------------------------------------------------------- |
| `Lok ma tye kare (kare)`        | Kare me fowadi mukene.                      |
| `Kare (kare) ki tye kwo mukene` | Doki me server ki tye ki dong kwede mukene. |
| `Lok ma tye kare (kare)`        | Kare me fowadi mukene.                      |
| `Doki ma pe tye kare`           | Router ki UPnP pe tye kwede.                |

Server ki tye, Plazma ki yom ma fowadi ki tye kwede.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. [Ngrok homepage](https://ngrok.com/download) ki download `Windows (64-bit)` ZIP kwede.
2. Doki me download ki Ngrok ki server folder.
3. [Ngrok dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) ki tye ki [yom me dong](#user-content-fn-13)[^13].
4. Server folder ki doki me tye kare me dong ki dok ma cwalo.
5. Doki ma tye kwede ki dong kwede, `start /b ngrok tcp --region jp 25565` ma cwalo ki dong kwede, `taskkill /f /t /im ngrok.exe` ki yom ma pe tye.
6. Kare ma pe tye ki dong kwede kwo mukene, `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` ma cwalo ki dong kwede.
7. Iyi ni doki me i kom dong kwede ki tye kwede.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Kikwero, dok pa cwinyo ma cwinyo,

```log
Windows IP gang

Ethernet Adapter Ethernet:

    DNS suffix kun kikwero. . . . :
    IPv4 Address. . . . . . . . : 192.168.3.7
    Subnet Mask . . . . . . . : 255.255.255.0
    Default Gateway . . . . . . : 192.168.3.1

```

Kikwero ma '192.168.3.7' ma kikwero, kikwero me server, cwiny pa 'localhost' ma kikwero.

Server me game pa PC mamegi, 'localhost' ma kikwero.
{% endtab %}
{% endtabs %}

## 7. Keto kwede

Server ki kwo kikwero, ki kwo kikwero me server ki dano.

Kwo ikit ma pe waco server.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Plazma ki kwo Paper ki kwo Spigot, ki kwo Spigot ki kwo server platform ki kwo.

[^3]: Windows key + R

[^4]: Linux ma cwinyo 'java --version' pa terminal

[^5]: JRE ni open source project mo, Minecraft server platform ki dong ma kwo.

[^6]: Kwede **dong ma kwo** ma kwo.

[^7]: Kwede 'Auto-restart' ki kwo server ki kwo kikwero. Cwalo 'Control + C' ki tye.

[^8]: Dyang ma en aye kikwero ki kwo pe i temo.

    Kikwero, dyang ma en aye memory capacity ki 8GB, 4GB ma kwo pe i temo.

[^9]: End-User License Agreement, Lok me kwo kikwero ki temo. Gin ma giketo ki [Minecraft lok ma en](https://www.minecraft.net/ko-kr/usage-guidelines) kacel iweko.

[^10]: Microsoft Corporation.

[^11]: Pa Uganda ma gin ma en i kit ma kwo tic ki lanyo me lawang i kano 32 me 1 me 9, **Korea Microsoft Corporation** ma en i kwo tic ki.

[^12]: Universal Plug & Play. Plazma ma Purpur kicel i ngom miyo ma Purpur ki tye ka kompyuta me router kicel i ngom, ki tye ka server ki gengo ma kicel ki nyutu woko dong i port, ki tye ka port forwarding ma en odok i kompyuta.

[^13]: En aco ni dong i Ngrok, i kompyuta ma en aco ni Google to GitHub, i Ngrok ki cok ma en aco.
