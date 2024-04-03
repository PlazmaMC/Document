---
description: Plazmaর সার্ভার তৈরি করার উপায় জানুন।
---

# 👟 শুরু করুন

Plazma একটি স্থিতিশীলভাবে ব্যবহার করতে, সিস্টেমটি নিম্নলিখিত প্রয়োজনীয়তা পূরণ করতে হবে।

|             | ন্যূনতম | পছন্দসূচী |
| :---------: | ------: | --------: |
| আর্কিটেকচার |     x64 |         - |
|    র‍্যাম   |     8GB |      16GB |
| সংরক্ষণাগার |     1GB |       8GB |
|     JRE     |      17 |        21 |

সঠিক কনফিগারেশন ফাইল সম্পাদনা করার জন্য, [Visual Studio Code](https://code.visualstudio.com/download) ইত্যাদি এডিটর ইনস্টল করা উচিত।

***

## 1. JRE ইনস্টল

নাম থেকেই বোঝা যায়, Minecraft: **"Java"** সংস্করণটি Java-তে তৈরি, চালানোর জন্য JRE[^1] প্রয়োজন।

Plazma Mojang Studios-এর অফিসিয়াল সার্ভার প্ল্যাটফর্ম [ভিত্তিক](#user-content-fn-2)[^2], Plazma ব্যবহার করার জন্যও JRE ইনস্টল করা উচিত।

### 1.1 JRE উপস্থিতি পরীক্ষা

সিস্টেমে JRE ইনস্টল করা আছে কি না তা যাচাই করতে, [এক্সিকিউট উইন্ডো](#user-content-fn-3)[^3] এ [`cmd /k java --version`](#user-content-fn-4)[^4] টাইপ করে এবং এটি চালান।

নিম্নলিখিত মত আউটপুট পেলে [2 তম ধাপ](setup.md#id-2) এ যান।

{% code title="সঠিক আউটপুট" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

উপরের মত আউটপুট না পেলে, বা নিম্নলিখিত মত পেলে JRE নাই বা খুব পুরানো, তাহলে [1.2 তম ধাপ](setup.md#id-1.2) টি পূরণ করতে হবে।

{% code title="JRE ইনস্টল করা হয়নি" lineNumbers="true" %}

```log
'java' একটি অভ্যন্তরীণ বা বাহ্যিক কমান্ড, ক্রিয়াশীল প্রোগ্রাম, বা ব্যাচ ফাইল নয়।
```

{% endcode %}

{% code title="JRE খুব পুরানো" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE 설치

본 가이드에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](setup.md#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. 먼저, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) 에서 **JDK 21**을 `.msi` 형태로 다운로드 합니다.
2. 다운로드된 설치 마법사를 실행하고, `다음`을 클릭합니다.
3. **창 좌측 중앙에 표시되는 메뉴에서 `Set JAVA_HOME variable`을 활성화 한 후,** `다음`을 클릭합니다.
4. `설치`를 눌러 JRE 설치를 `완료`합니다.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) থেকে **JDK 21** এ `.dmg` ফর্ম্যাটের ইনস্টলার ডাউনলোড করে JRE ইনস্টল করুন।

{% endtab %}

{% tab title="Debian/Ubuntu" %}

প্রথমে, নিচের কমান্ডটি টার্মিনালে চালানো যাবে Azul Zulu সংরক্ষণাগারে যোগ করার জন্য।

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

그런 다음, 다음 명령어를 터미널에서 실행하여 JRE를 설치합니다.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

JRE ইনস্টল করতে নিচের কমান্ডটি প্রবেশ করান।

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma 다운로드

Plazma에서는 여러 가지 형태의 실행 파일을 제공하고 있습니다.

{% hint style="warning" %}

**সাধারণভাবে `Reobf Paperclip` ব্যবহার করা হয়।**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](setup.md#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>자세히 알아보기</summary>

실행 파일의 이름은 `plazma-(버전 관리자)-1.20.4-R0.1-SNAPSHOT-(매핑 형태).jar` 로 정해집니다.

- **매핑 형태**\
  매핑은 Minecraft의 실제 코드와 난독화된 코드를 잇는 일종의 지도입니다.
  - **Reobf**\
    Reobfuscated (রিঅবফাইড), Spigot ম্যাপিং হিসেবেও পরিচিত এবং অধিকাংশ NMS প্লাগইনে ব্যবহৃত হয়।\
    1.20.5 থেকে ব্যবহার সমাপ্ত হবে।
  - **Mojmap**\
    Mojang-ম্যাপড, ভ্যানিলা Minecraft ম্যাপিং।
- **버전 관리자**\
  버전 관리자는 서버 구동에 필요한 라이브러리와, 서버 파일을 패치하는 서버의 런처라고 할 수 있습니다.
  - **Paperclip**\
    PaperMC 팀에서 Paper 및 기타 파생 플랫폼을 위해 개발한 관리자로, 라이브러리를 다운로드 하고 서버에 패치를 적용하는 역할을 합니다.
  - **Bundler**\
    바닐라 Minecraft 버전 관리자입니다.

</details>

***

## 3. 시작 스크립트 생성

Plazma를 간단하게 시작하고, 서버를 자동으로 재시작 하려면, [시작 스크립트](#user-content-fn-6)[^6]를 만들어야 합니다.

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 [생성할 수 있습니다.](#user-content-fn-7)[^7]\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

좌측 하단 다운로드 버튼을 통해 시작 스크립트를 다운로드 할 수 있습니다.\
**다운로드한 시작 스크립트가 자신의 운영체제와 동일한지 확인하세요.**

***

## 4. 파일 정리

이제 다운로드한 시작 스크립트와 Plazma를 새 폴더에 이동합니다.

{% hint style="warning" %}

**ফোল্ডারের নাম অবশ্যই স্পেস ছাড়া, ইংরেজিতে সেট করা হতে হবে।**

그렇지 않으면 Plazma 또는 JRE가 올바르게 작동하지 않을 수 있습니다.

{% endhint %}

이제 시작 스크립트를 실행합니다. Windows এর ক্ষেত্রে, <mark style="background-color:orange;">ফায়ারওয়াল অনুমতি নির্বাচন জন্য, অবশ্যই **অনুমতি** নির্বাচন করতে হবে</mark>।

***

## 5. EULA 동의

시작 스크립트를 한 번 실행하면, 폴더에 `eula.txt` 가 생성됩니다.

EULA[^9]는 [Mojang Studios](#user-content-fn-10)[^10]의 서비스를 이용함으로써 동의해야 하는 사용권 계약입니다.

EULA에 동의하지 않는 경우 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 [제재를 받을 수 있습니다.](#user-content-fn-11)[^11]

EULA에 동의하려면 `eula.txt` 파일의 `eula=false`를 `eula=true`로 수정하고 저장합니다.

***

## 6. 외부 접속 허용 (Windows)

현대 운영 체제는 외부에서 위험한 접근을 차단하기 위해, 기본적으로 **방화벽**과 **라우터**가 외부 접속을 차단하고 있습니다.

Windows의 경우, 방화벽은 [3 단계](setup.md#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**এই গাইডে Windows অপারেটিং সিস্টেম এবং [UPnP](#user-content-fn-12)[^12] ব্যবহার করা যাবে ম্যানে করে লেখা হয়েছে।**

라우터가 UPnP를 지원하지 않는 경우, 라우터 별로 패널이 다르므로, 직접 자료를 검색해야 합니다.

또는 [Ngrok](https://ngrok.com/)을 통해 임시 주소를 생성할 수도 있습니다.
{% endhint %}

{% hint style="warning" %}

**লিনাক্স বা macOS এবং অন্যান্য (অর্ধ) UNIX বিষয়ক অপারেটিং সিস্টেমে, ফায়ারওয়াল সেবাগুলির জন্য সেটিং পদ্ধতি ভিন্ন ভাবে থাকতে পারে, তাই আপনাকে স্বয়ংক্রিয়ভাবে তথ্য অনুসন্ধান করতে হবে।**

{% endhint %}

### 6.1 포트 포워딩 필요 유무 확인

실행 창에 다음과 같이 입력하고 실행합니다.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

만약 출력이 `True`라면, 여기서 마쳐도 되지만, `False`라면 포트 포워딩을 설정해야 합니다.

### 6.2 서버에 접속

{% tabs %}

{% tab title="বাহ্যিক সংযোগ" %}

পোর্ট ফরওয়ার্ডিং প্রয়োজন নেই বা ইতিমধ্যে পোর্ট ফরওয়ার্ডিং সফলভাবে করা হয়েছে তাহলে এখন সার্ভারে সংযোগ করতে পারবেন।

서버에 접속할 때 사용되는 주소는 [여기에서](https://ip.pe.kr/) 확인할 수 있습니다.

{% endtab %}

{% tab title="UPnP로 পোর্ট ফরওয়ার্ডিং চেষ্টা করা হচ্ছে" %}

সার্ভার ফোল্ডারের `purpur.yml` ফাইলে, `network.upnp-port-forwarding` এক্টিভেট করুন এবং `true` হিসেবে সেট করুন।

그런 다음, 서버를 재시작하면, Plazma가 자동으로 포트 포워딩을 시도합니다.

아래는 콘솔에 출력되는 메세지에 따른 UPnP 성공 여부이며, 콘솔에서는 `[UPnP] (메세지)` 와 같이 출력됩니다.

| 메세지                             | 의미                   |
| ------------------------------- | -------------------- |
| `Successfully opened port (포트)` | 포트포워딩 성공.            |
| `Port (포트) is already open`     | 다른 서비스가 해당 포트를 사용중임. |
| `Failed to open port (포트)`      | 포트포워딩 실패.            |
| `Service is unavailable`        | 라우터가 UPnP를 지원하지 않음.  |

서버가 종료되면 Plazma가 자동으로 포트를 닫습니다.

{% endtab %}

{% tab title="Ngrok দিয়ে অস্থায়ী ঠিকানা তৈরি করুন" %}

Ngrok ব্যবহার করা একটি ভাল উপায় যা সাময়িক পরীক্ষা, অংশগ্রহণমূলক বা বন্ধুদের সাথে খেলার জন্য উপকারী।

1. [Ngrok 홈페이지](https://ngrok.com/download)에서 `Windows (64-bit)` ZIP 파일을 다운로드 합니다.
2. 다운로드한 Ngrok을 서버 폴더에 넣습니다.
3. [Ngrok 대시보드](https://dashboard.ngrok.com/get-started/your-authtoken) 에서 [인증 토큰을 생성](#user-content-fn-13)[^13]합니다.
4. 서버 폴더에서 아래 `Command Line`에 표시되는 명령어를 실행합니다.
5. 실행 스크립트 가장 상단에 `start /b ngrok tcp --region jp 25565`, 최하단에 `taskkill /f /t /im ngrok.exe`를 추가합니다.
6. 콘솔 최상단에 표시된 `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` 에서, `0.tcp.jp.ngrok.io:12345`가 서버의 주소가 됩니다.
7. 이제 외부에서 해당 주소를 통해 접속할 수 있습니다.

{% endtab %}

{% tab title="লোকাল হোস্ট থেকে সংযোগ" %}

যদি আপনি সার্ভারে লোকাল হোস্ট থেকে সংযোগ করতে চান, তবে কমান্ড প্রম্পটে `cmd /k ipconfig` চালিয়ে আউটপুট হিসেবে প্রকাশিত `IPv4 ঠিকানা` দিয়ে সংযোগ করতে পারবেন।

예를 들어, 명령어 실행 후 다음과 같이 출력되었을 때,

```log
Windows IP কনফিগারেশন

ইথারনেট অ্যাডাপ্টার ইথারনেট:

    সংযুক্ত DNS সাফিক্স. . . . :
    IPv4 ঠিকানা. . . . . . . . . : 192.168.3.7
    সাবনেট মাস্ক . . . . . . . : 255.255.255.0
    ডিফল্ট গেটওয়ে . . . . . . : 192.168.3.1

```

여기에서 IPv4 주소에 표시된 `192.168.3.7`로 접속을 시도하면 로컬에서 서버에 접속할 수 있습니다.

서버와 게임이 같은 PC에서 실행되는 경우, `localhost`로 접속할 수 있습니다.

{% endtab %}
{% endtabs %}

## 7. 발전 단계

서버를 성공적으로 시작하고 서버가 올바르게 작동중이라면, 이제 서버를 사용자화 할 차례입니다.

아래 가이드를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java 실행 환경.

[^2]: Plazma의 기반 Paper는 Spigot을 기반으로 하며, Spigot이 공식 서버 플랫폼을 기반으로 합니다.

[^3]: Windows 키 + R

[^4]: Linux의 경우 터미널 에서 `java --version`

[^5]: JRE는 오픈 소스 프로젝트중 하나로, Minecraft 서버 플랫폼 처럼 여러 종류가 있습니다.

[^6]: 일반적으로 **구동기**라고 알려져 있습니다.

[^7]: "Auto-restart"를 활성화 하면 서버가 자동으로 재시작 됩니다. `Control + C`를 입력해 종료할 수 있습니다.

[^8]: 시스템의 절반 이상을 넘기는것은 권장하지 않습니다.

    예를 들어, 시스템 전체 메모리 용량이 8GB라고 했을 때, 4GB 이상으로 설정하는것은 권장되지 않습니다.

[^9]: End-User License Agreement, 최종 사용자 사용권 계약. অধিক তথ্যের জন্য [Minecraft ওয়েবসাইট](https://www.minecraft.net/ko-kr/usage-guidelines) দেখুন।

[^10]: মাইক্রোসফট কর্পোরেশন।

[^11]: বাংলাদেশের ক্ষেত্রে খেলার শিল্প উন্নয়ন আইন ৩২ ধারা ১ অনুচ্ছেদ ৯ অনুযায়ী **বাংলাদেশ মাইক্রোসফট কর্পোরেশন** কানুনীয়ভাবে অভিযোগ করতে পারে।

[^12]: ইউনিভার্সাল প্লাগ এন্ড প্লে প্লে। Plazma এ অন্তর্ভুক্ত Purpur এই প্রযুক্তি দ্বারা অটোমেটিকলি রাউটার এবং সার্ভারের সাথে যোগাযোগ করে, যেটি পোর্ট খোলার প্রয়োজন হলে কেবলমাত্র সার্ভার চালু থাকলে, তাই পোর্ট ফরোয়ার্ডিং সরাসরি করতে হবে না।

[^13]: অ্যাকাউন্ট না থাকলে Ngrok এ গুগল বা গিটহাব অ্যাকাউন্ট দিয়ে সাইন আপ করুন।
