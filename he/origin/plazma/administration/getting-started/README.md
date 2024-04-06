---
description: למדו כיצד ליצור שרת באמצעות Plazma.
---

# 👟 התחלה

כדי להשתמש ב-Plazma באופן יציב, המערכת צריכה לעמוד בדרישות הבאות:

|            | מינימום | מומלץ |
| :--------: | :------ | :---- |
| ארכיטקטורה | x64     | -     |
|     RAM    | 8GB     | 16GB  |
|  שטח אחסון | 1GB     | 8GB   |
|     JRE    | 17      | 21    |

כדי לערוך קבצי תצורה בצורה חלקה, כדאי להתקין עורך כגון [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. התקנת JRE

כפי שניתן להבין מהשם, Minecraft: **"Java"** Edition פותח ב-Java, ולהריץ אותו נדרש JRE[^1].

Plazma מבוסס על פלטפורמת השרת הרשמית של Mojang Studios, ולכן על מנת להשתמש ב-Plazma יש להתקין גם JRE.

### 1.1 בדיקת התקנת JRE

כדי לוודא ש-JRE מותקן במערכת, יש להזין [`cmd /k java --version`](#user-content-fn-4) בחלון הפעולה ולהפעיל אותו.

כאשר הוא מוצג כך, עובר ל[שלב 2](#id-2).

{% code title="הפלט הנכון" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
סביבת הרצה OpenJDK Zulu21.32+17-CA (בנייה 21.0.2+13-LTS)
OpenJDK 64-Bit שרת VM Zulu21.32+17-CA (בנייה 21.0.2+13-LTS, מצב מעורב, שיתוף)
```

{% endcode %}

אם הוא לא מוצג כמו למעלה, או מוצג כך, זה אומר שאין JRE או שהוא ישן מדי, ועליך לבצע [שלב 1.2](#id-1.2).

{% code title="JRE לא מותקן" lineNumbers="true" %}

```log
'java' הוא פקודה פנימית או חיצונית, תוכנית הניתנת לביצוע, או
קובץ batch אינו זמין.
```

{% endcode %}

{% code title="JRE ישן מדי" lineNumbers="true" %}

```log
אפשרות לא מוכרת: --version
שגיאה: לא ניתן היה ליצור את מכונת ה-Java הווירטואלית.
שגיאה: שגיאה חמורה אירעה. התוכנית תיצא.
```

{% endcode %}

### 1.2 התקנת JRE

במדריך זה אנו משתמשים ב-Azul Zulu כאחת מ[הגרסאות](#user-content-fn-5)[^5] של JRE.

לאחר התקנה, נא לבצע שוב [שלב 1.1](#id-1.1) כדי לוודא שההתקנה הושלמה בהצלחה.

{% tabs %}

{% tab title="Windows" %}

1. התחל על ידי הורדת **JDK 21** בפורמט `.msi` מ-[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. הרץ את אשף ההתקנה שהורדת ולחץ על 'הבא'.
3. בתפריט המוצג במרכז השמאלי של החלון, הפעל את 'Set JAVA_HOME variable' ולאחר מכן לחץ על 'הבא'.
4. לחץ על 'התקן' כדי להשלים את התהליך של התקנת JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) מורידים את **JDK 21** בפורמט `.dmg` מהקישור ומריצים את אשף ההתקנה כדי להתקין JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

ראשית, מוסיפים את ספריית האחסון של Azul Zulu ל-APT על ידי הרצת הפקודה הבאה בטרמינל.

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

ניתן להתקין JRE על ידי הזנת הפקודה הבאה.

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

**ברוב המקרים משתמשים ב-`Reobf Paperclip`.**

התוכן הבא מיועד למפתחים או לאנשים שמעוניינים בתכנים המיוחדים של כל סוג.\
אם אתה משתמש רגיל, תוכל לדלג ל[שלב 3](#id-3) ללא בעיה.

{% endhint %}

<details>

<summary>자세히 알아보기</summary>

실행 파일의 이름은 `plazma-(버전 관리자)-1.20.4-R0.1-SNAPSHOT-(매핑 형태).jar` 로 정해집니다.

- **매핑 형태**\
  매핑은 Minecraft의 실제 코드와 난독화된 코드를 잇는 일종의 지도입니다.
  - **Reobf**\
    Reobfuscated (ריאובפוסקייטד), מפוצל מחדש ונקרא גם מפת Spigot, משמש ברוב התוספים של NMS.\
    השימוש בו יופסק מגרסה 1.20.5 והלאה.
  - **Mojmap**\
    מופת Mojang, מפת Minecraft הוונילית.
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

[Flags.sh](https://flags.sh)ניתן ליצירת סקריפט התחלה דרך\
[יצירה](#user-content-fn-7)[^7]. רק ציין את כמות הזיכרון לשימוש ב-Plazma והפקודה תתאותת אוטומטית.

좌측 하단 다운로드 버튼을 통해 시작 스크립트를 다운로드 할 수 있습니다.\
**다운로드한 시작 스크립트가 자신의 운영체제와 동일한지 확인하세요.**

***

## 4. 파일 정리

이제 다운로드한 시작 스크립트와 Plazma를 새 폴더에 이동합니다.

{% hint style="warning" %}

**שם התיקייה חייב להיות בלתי מכוון ובאנגלית.**

그렇지 않으면 Plazma 또는 JRE가 올바르게 작동하지 않을 수 있습니다.

{% endhint %}

이제 시작 스크립트를 실행합니다. ב-Windows, <mark style="background-color:orange;">בחלון בחירת הרשאות חומת האש, יש לבחור **התר** בהחלט</mark>.

***

## 5. EULA 동의

시작 스크립트를 한 번 실행하면, 폴더에 `eula.txt` 가 생성됩니다.

EULA[^9]는 [Mojang Studios](#user-content-fn-10)[^10]의 서비스를 이용함으로써 동의해야 하는 사용권 계약입니다.

{% hint style="warning" %}

אם אין הסכמה, לא ניתן להתחיל את השרת ואפשר לקבל [ענישות](#user-content-fn-11)[^11] כגון השהיית חשבון על עבירה ב-EULA.

{% endhint %}

EULA에 동의하려면 `eula.txt` 파일의 `eula=false`를 `eula=true`로 수정하고 저장합니다.

***

## 6. 외부 접속 허용 (Windows)

현대 운영 체제는 외부에서 위험한 접근을 차단하기 위해, 기본적으로 **방화벽**과 **라우터**가 외부 접속을 차단하고 있습니다.

במקרה של Windows, הגנת הגישה (פיירוול) כבר הופעלה ב[שלב 3](#id-3), נדרש רק פורוורד של פורטים.

{% hint style="info" %}

**מדריך זה נכתב בהנחה שיש לך מערכת הפעלה Windows ו-[UPnP](#user-content-fn-12)[^12] זמין בנתב שלך.**

라우터가 UPnP를 지원하지 않는 경우, 라우터 별로 패널이 다르므로, 직접 자료를 검색해야 합니다.

또는 [Ngrok](https://ngrok.com/)을 통해 임시 주소를 생성할 수도 있습니다.
{% endhint %}

{% hint style="warning" %}

**במערכות ההפעלה של Linux או macOS וכדומה (כמעט UNIX), יש לחפש אינפורמציה על הגדרת שירותי חומת האש באופן ישיר מאחר שהם שונים.**

{% endhint %}

### 6.1 포트 포워딩 필요 유무 확인

실행 창에 다음과 같이 입력하고 실행합니다.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

만약 출력이 `True`라면, 여기서 마쳐도 되지만, `False`라면 포트 포워딩을 설정해야 합니다.

### 6.2 서버에 접속

{% tabs %}

{% tab title="גישה מהחוץ" %}

אם אין צורך בהעברת פורטים או שכבר בוצעה העברת פורטים בהצלחה, ניתן כעת להתחבר לשרת.

서버에 접속할 때 사용되는 주소는 [여기에서](https://ip.pe.kr/) 확인할 수 있습니다.

{% endtab %}

{% tab title="ניסיון להפעיל פורטים עם UPnP" %}

בקובץ `purpur.yml` בתיקיית השרת, הפעל את `network.upnp-port-forwarding` על `true`.

그런 다음, 서버를 재시작하면, Plazma가 자동으로 포트 포워딩을 시도합니다.

아래는 콘솔에 출력되는 메세지에 따른 UPnP 성공 여부이며, 콘솔에서는 `[UPnP] (메세지)` 와 같이 출력됩니다.

| 메세지                             | 의미                                   |
| ------------------------------- | ------------------------------------ |
| `Successfully opened port (포트)` | 포트포워딩 성공.            |
| `Port (포트) is already open`     | 다른 서비스가 해당 포트를 사용중임. |
| `Failed to open port (포트)`      | 포트포워딩 실패.            |
| `Service is unavailable`        | 라우터가 UPnP를 지원하지 않음.  |

서버가 종료되면 Plazma가 자동으로 포트를 닫습니다.

{% endtab %}

{% tab title="יצירת כתובת זמנית עם Ngrok" %}

שימוש ב-Ngrok מתאים לבדיקות זמניות, משחקים קבוצתיים או שיתוף פעולה עם חברים.

1. [Ngrok 홈페이지](https://ngrok.com/download)에서 `Windows (64-bit)` ZIP 파일을 다운로드 합니다.
2. 다운로드한 Ngrok을 서버 폴더에 넣습니다.
3. [Ngrok 대시보드](https://dashboard.ngrok.com/get-started/your-authtoken) 에서 [인증 토큰을 생성](#user-content-fn-13)[^13]합니다.
4. 서버 폴더에서 아래 `Command Line`에 표시되는 명령어를 실행합니다.
5. 실행 스크립트 가장 상단에 `start /b ngrok tcp --region jp 25565`, 최하단에 `taskkill /f /t /im ngrok.exe`를 추가합니다.
6. 콘솔 최상단에 표시된 `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` 에서, `0.tcp.jp.ngrok.io:12345`가 서버의 주소가 됩니다.
7. 이제 외부에서 해당 주소를 통해 접속할 수 있습니다.

{% endtab %}

{% tab title="התחברות מקומית" %}

כאשר אתה מנסה להתחבר לשרת מהמחשב המקומי, תוכל להתחבר באמצעות כתובת `IPv4` שמופיעה בתוצאות `cmd /k ipconfig` בחלון ההרצה.

예를 들어, 명령어 실행 후 다음과 같이 출력되었을 때,

```log
Windows תצורת IP

מתאם Ethernet Ethernet:

    סיומת DNS מחוברת. . . . :
    כתובת IPv4. . . . . . . . . : 192.168.3.7
    מסכת תת-רשת . . . . . . . : 255.255.255.0
    שער ברירת מחדל . . . . . . : 192.168.3.1

```

여기에서 IPv4 주소에 표시된 `192.168.3.7`로 접속을 시도하면 로컬에서 서버에 접속할 수 있습니다.

서버와 게임이 같은 PC에서 실행되는 경우, `localhost`로 접속할 수 있습니다.

{% endtab %}
{% endtabs %}

## 7. להתפתח

서버를 성공적으로 시작하고 서버가 올바르게 작동중이라면, 이제 서버를 사용자화 할 차례입니다.

קרא את המדריך הבא כדי ללמוד כיצד להתאים אישית את השרת.

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

[^9]: End-User License Agreement, 최종 사용자 사용권 계약. 자세한 내용은 [Minecraft 홈페이지](https://www.minecraft.net/ko-kr/usage-guidelines)를 확인해 주세요.

[^10]: חברת מיקרוסופט.

[^11]: במקרה של קוריאה, ניתן להגיש תביעה משפטית מצד **חברת מיקרוסופט של קוריאה** על פי סעיף 9, סעיף 1, סעיף 32 של חוק הקידום התעשייתי של תעשיית המשחקים בקוריאה.

[^12]: כניסה ויציאה אוניברסלית. פורפור הכלול בפלאזמה מתקשר אוטומטית עם הראוטר דרך טכנולוגיה זו ומאפשר פתיחת פורטים רק כאשר השרת פועל, ולכן אין צורך לבצע הפניה ישירה של פורטים.

[^13]: במקרה שאין לך חשבון, נרשמים ל-Ngrok דרך חשבון Google או GitHub.
