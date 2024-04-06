---
description: روش ساخت سرور با استفاده از Plazma را بیاموزید.
---

# 👟 شروع

برای استفاده پایدار از Plazma، سیستم باید الزامات زیر را برآورده کند.

|                 | حداقل | توصیه شده |
| :-------------: | :---- | :-------- |
|      معماری     | x64   | -         |
|       RAM       | 8GB   | 16GB      |
| فضای ذخیره‌سازی | 1GB   | 8GB       |
|       JRE       | 17    | 21        |

برای ویرایش فایل‌های پلاگین به صورت صحیح، پیشنهاد می‌شود که [ویژوال استودیو کد](https://code.visualstudio.com/download) یا نرم‌افزارهای ویرایشگر دیگر را نصب کنید.

***

## 1. نصب JRE

همانطور که از نامش پیداست، Minecraft: **"Java"** Edition با استفاده از Java توسعه یافته است و برای اجرا نیازمند JRE[^1] می‌باشد.

Plazma بر اساس پلتفرم سرور رسمی Mojang Studios [ساخته شده است](#user-content-fn-2)[^2]، بنابراین برای استفاده از Plazma نیز باید JRE را نصب کنید.

### 1.1 بررسی وجود JRE

برای بررسی نصب بودن JRE در سیستم، در [پنجره اجرا](#user-content-fn-3)[^3] `cmd /k java --version` را وارد کرده و اجرا کنید.

اگر خروجی به شکل زیر باشد، به [مرحله 2](setup.md#id-2) بروید.

{% code title="خروجی صحیح" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

اگر خروجی به شکل زیر نباشد یا به شکل زیر باشد، یعنی JRE موجود نیست یا خیلی قدیمی است، بنابراین باید [مرحله 1.2](setup.md#id-1.2) را انجام دهید.

{% code title="JRE نصب نشده است" lineNumbers="true" %}

```log
'java' به عنوان دستور داخلی یا خارجی، برنامه قابل اجرا یا
فایل دسته‌ای قابل اجرا نیست.
```

{% endcode %}

{% code title="JRE خیلی قدیمی است" lineNumbers="true" %}

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

{% tab title="ویندوز" %}

1. 먼저, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) 에서 **JDK 21**을 `.msi` 형태로 다운로드 합니다.
2. 다운로드된 설치 마법사를 실행하고, `다음`을 클릭합니다.
3. **창 좌측 중앙에 표시되는 메뉴에서 `Set JAVA_HOME variable`을 활성화 한 후,** `다음`을 클릭합니다.
4. `설치`를 눌러 JRE 설치를 `완료`합니다.

{% پایان تب %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) **JDK 21** را از Azul Zulu به صورت فایل `.dmg` دانلود کرده و اجرا کنید تا JRE نصب شود.

{% پایان تب %}

{% tab title="دبیان/اوبونتو" %}

ابتدا، دستور زیر را در ترمینال اجرا کنید تا مخزن Azul Zulu به APT اضافه شود.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

그런 다음, 다음 명령어를 터미널에서 실행하여 JRE를 설치합니다.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% پایان تب %}

{% tab title="فدورا/RHEL" %}

می‌توانید با وارد کردن دستور زیر JRE را نصب کنید.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% پایان تب %}
{% پایان تب‌ها %}

***

## 2. Plazma 다운로드

Plazma에서는 여러 가지 형태의 실행 파일을 제공하고 있습니다.

{% hint style="warning" %}

**بیشتر موارد از `Reobf Paperclip` استفاده می‌شود.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](setup.md#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>자세히 알아보기</summary>

실행 파일의 이름은 `plazma-(버전 관리자)-1.20.4-R0.1-SNAPSHOT-(매핑 형태).jar` 로 정해집니다.

- **매핑 형태**\
  매핑은 Minecraft의 실제 코드와 난독화된 코드를 잇는 일종의 지도입니다.
  - **Reobf**\
    Reobfuscated (تجدید رمزگذاری), به عنوان Spigot Mapping نیز شناخته می‌شود و در اکثر افزونه‌های NMS استفاده می‌شود.\
    از نسخه 1.20.5 به بعد، استفاده از آن متوقف خواهد شد.
  - **Mojmap**\
    Mojang-mapped، مپینگ Minecraft وانیلایی است.
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

**نام پوشه باید بدون فاصله باشد و به انگلیسی تنظیم شود.**

그렇지 않으면 Plazma 또는 JRE가 올바르게 작동하지 않을 수 있습니다.

{% endhint %}

이제 시작 스크립트를 실행합니다. در ویندوز، <mark style="background-color:orange;">در پنجره انتخاب مجوز فایروال، حتماً گزینه **اجازه** را انتخاب کنید</mark>.

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

**این راهنما برای سیستم عامل ویندوز و [UPnP](#user-content-fn-12)[^12] وجود دارد که فرض شده است از آن استفاده می‌شود.**

라우터가 UPnP를 지원하지 않는 경우, 라우터 별로 패널이 다르므로, 직접 자료를 검색해야 합니다.

또는 [Ngrok](https://ngrok.com/)을 통해 임시 주소를 생성할 수도 있습니다.
{% endhint %}

{% hint style="warning" %}

**برای سیستم‌عامل‌های یونیکس (مانند لینوکس یا macOS)، به دلیل تفاوت در روش‌های تنظیمات برای هر سرویس فایروال، باید به صورت مستقیم جستجو کنید.**

{% endhint %}

### 6.1 포트 포워딩 필요 유무 확인

실행 창에 다음과 같이 입력하고 실행합니다.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

만약 출력이 `True`라면, 여기서 마쳐도 되지만, `False`라면 포트 포워딩을 설정해야 합니다.

### 6.2 서버에 접속

{% tabs %}

{% tab title="دسترسی از خارج" %}

اگر نیازی به پورت فوروارد نیست یا اگر پورت فوروارد را قبلاً موفقیت‌آمیز انجام داده‌اید، اکنون می‌توانید به سرور متصل شوید.

서버에 접속할 때 사용되는 주소는 [여기에서](https://ip.pe.kr/) 확인할 수 있습니다.

{% پایان تب %}

{% tab title="سعی برای انجام پورت فورواردینگ با استفاده از UPnP" %}

در `purpur.yml` پوشه سرور، `network.upnp-port-forwarding` را به `true` فعال کنید.

그런 다음, 서버를 재시작하면, Plazma가 자동으로 포트 포워딩을 시도합니다.

아래는 콘솔에 출력되는 메세지에 따른 UPnP 성공 여부이며, 콘솔에서는 `[UPnP] (메세지)` 와 같이 출력됩니다.

| 메세지                             | 의미                                   |
| ------------------------------- | ------------------------------------ |
| `Successfully opened port (포트)` | 포트포워딩 성공.            |
| `Port (포트) is already open`     | 다른 서비스가 해당 포트를 사용중임. |
| `Failed to open port (포트)`      | 포트포워딩 실패.            |
| `Service is unavailable`        | 라우터가 UPnP를 지원하지 않음.  |

서버가 종료되면 Plazma가 자동으로 포트를 닫습니다.

{% پایان تب %}

{% tab title="ایجاد آدرس موقت با استفاده از Ngrok" %}

روش استفاده از Ngrok برای تست‌های کوتاه مدت، بازی‌های چندنفره یا بازی با دوستان بسیار مفید است.

1. [Ngrok 홈페이지](https://ngrok.com/download)에서 `Windows (64-bit)` ZIP 파일을 다운로드 합니다.
2. 다운로드한 Ngrok을 서버 폴더에 넣습니다.
3. [Ngrok 대시보드](https://dashboard.ngrok.com/get-started/your-authtoken) 에서 [인증 토큰을 생성](#user-content-fn-13)[^13]합니다.
4. 서버 폴더에서 아래 `Command Line`에 표시되는 명령어를 실행합니다.
5. 실행 스크립트 가장 상단에 `start /b ngrok tcp --region jp 25565`, 최하단에 `taskkill /f /t /im ngrok.exe`를 추가합니다.
6. 콘솔 최상단에 표시된 `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` 에서, `0.tcp.jp.ngrok.io:12345`가 서버의 주소가 됩니다.
7. 이제 외부에서 해당 주소를 통해 접속할 수 있습니다.

{% پایان تب %}

{% tab title="اتصال از روی دستگاه محلی" %}

در صورت تمایل به اتصال از دستگاه محلی به سرور، می‌توانید با اجرای `cmd /k ipconfig` در پنجره اجرا، با استفاده از `آدرس IPv4` که نمایش داده می‌شود، به سرور متصل شوید.

예를 들어, 명령어 실행 후 다음과 같이 출력되었을 때,

```log
تنظیمات IP ویندوز

آداپتور اترنت:

    پسوند DNS متصل شده. . . . :
    آدرس IPv4. . . . . . . . . : 192.168.3.7
    ماسک زیرشبکه . . . . . . . : 255.255.255.0
    دروازه پیش فرض . . . . . . : 192.168.3.1

```

여기에서 IPv4 주소에 표시된 `192.168.3.7`로 접속을 시도하면 로컬에서 서버에 접속할 수 있습니다.

서버와 게임이 같은 PC에서 실행되는 경우, `localhost`로 접속할 수 있습니다.

{% پایان تب %}
{% پایان تب‌ها %}

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

[^9]: End-User License Agreement, 최종 사용자 사용권 계약. 자세한 내용은 [صفحه اصلی Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines) را بررسی کنید.

[^10]: شرکت مایکروسافت.

[^11]: با توجه به ماده 32 تبصره 1 بند 9 قانون ترویج صنعت بازی کره جنوبی، شرکت **مایکروسافت کره** می‌تواند شکایت قانونی کند.

[^12]: پلاگین و پخش یونیورسال. با توجه به اینکه Purpur که در Plazma شامل می‌شود، از طریق این تکنولوژی به صورت خودکار با روتر ارتباط برقرار می‌کند و تنها زمانی که سرور در حال اجرا است، پورت‌ها را باز می‌کند، بنابراین نیازی به انجام پورت فورواردینگ مستقیم نیست.

[^13]: در صورت عدم وجود حساب کاربری، از طریق حساب Google یا GitHub در Ngrok ثبت‌نام کنید.
