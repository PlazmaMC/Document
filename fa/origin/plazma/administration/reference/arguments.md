---
description: 시작 인수와 시스템 속성에 대해 알아보세요.
---

# 🎛️ 인수와 속성

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,\
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[명령어에 덧붙이는 위치에](#user-content-fn-2)[^2] 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## 시스템 속성 <a href="#id-1" id="id-1"></a>

시스템 속성은 `-jar` 앞에 입력되어 Plazma가 초기화 되기 전 JVM에서 처리되는 값입니다.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### 사용 방법 <a href="#id-1.1" id="id-1.1"></a>

시스템 속성은 `java` 와 `-jar` 사이에 Java 명령 인수로써 입력됩니다.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,\
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`는 해당 인수가 JVM에 내장되지 않고 Plazma에 추가된 전용 인수임을 나타내며,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정됩니다.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

{% endhint %}

### 전체 시스템 속성 <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

사용 중지된 표지판 포맷을 업데이트 합니다.

#### `debug.entities`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

엔티티 정보 관련 디버그 로그를 활성화 합니다.

#### `debug.rewriteForIDE`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

IDE에서 디버그 정보를 올바르게 불러올 수 있도록 NMS 리비전을 비활성화 하고,\
내부 버전 정보를 자동으로 리맵합니다.

#### `disable.watchdog`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

Spigot의 Watchdog 경고 시스템을 비활성화 합니다.

#### `letMeReload`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

`/reload` 명령어의 재확인 메세지를 비활성화 합니다.

{% hint style="danger" %}

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

플러그인 개발자이고 플러그인을 업데이트 해야 하는 경우, `/reload` 대신 핫스왑을 사용하세요.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

표준 입출력 체계를 사용하는 플러그인을 비활성화 합니다.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

채팅 컴포넌트에서 사용 중단된 포맷이 감지되면 경고합니다.

#### `Paper.bypassHostCheck`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

플레이어가 서버에 접속할 때 서버의 패턴 일치 검증을 비활성화 합니다.

#### `Paper.debugDynamicMissingKeys`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

NBT 오브젝트에서 누락된 키에 대한 디버그 로그를 활성화 합니다.

#### `Paper.debugInvalidSkullProfiles`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

잘못된 프로필 정보를 가진 머리 블록의 디버그 로그를 활성화 합니다.

이는 월드 내 모든 잘못된 머리 블록을 위치와 함께 로그합니다.

#### `Paper.disableChannelLimit`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

플러그인 클래스 우선 순위 체계를 비활성화 합니다.

플러그인 셰이드에서 문제가 발생한 경우 유용합니다.

#### `Paper.disableFlushConsolidate`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

Netty flush consolidation 체계를 비활성화 합니다.

#### `Paper.excessiveTELimit`

- **نوع**: `Integer`
- **기본값**: `750`

엔티티가 설정된 값보다 많으면 다중 패킷으로 분할하여 전송합니다.

#### `Paper.filterThreshold`

- **نوع**: `Integer`
- **기본값**: `8192`

서버가 한 번에 받을 수 있는 최대 패킷의 크기를 설정합니다.

#### `Paper.ignoreJavaVersion`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

Java 버전 확인을 비활성화 합니다.

{% hint style="danger" %}

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

월드 등 전반적인 파일이 영구적으로 손상될 수 있으며, 게임의 전체 메커니즘이 망가지게 됩니다.

이를 사용하여 발생한 모든 문제는 본인이 책임지며, Plamza는 이에 대한 아무런 지원을 하지 않습니다.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **نوع**: `Integer`
- **기본값**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **نوع**: `Integer`
- **기본값**: `80`

표지판의 한 줄에 입력 가능한 글자의 최대 길이를 설정합니다.

#### `Paper.minPrecachedDatafixVersion`

- **نوع**: `Integer`
- **기본값**: `(월드 버전) + 1`

먼저 초기화할 월드 업데이트 정보의 버전을 설정합니다.

대량의 청크를 업데이트 해야 하는 경우 유용하지만, 그 외에 경우 사용되지 않습니다.

#### `Paper.parseYamlCommentsByDefault`

- **نوع**: `Boolean`
- **기본값**: `True`

YAML 파일의 주석의 처리를 활성화 합니다.

#### `Paper.playerConnection.keepAlive`

- **نوع**: `Integer`
- **기본값**: `30`

플레이어에게서 입력된 값(초) 만큼 아무런 데이터도 전송 받지 못했을 때, 플레이어를 추방합니다.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

서버 속성의 주석을 무시합니다.

#### `Paper.debug-sync-loads`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

동기 청크 작성의 디버그 로그를 활성화 합니다.

#### `Paper.enable-sync-chunk-writes`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

Minecraft의 [기본 청크 작성 체계](#user-content-fn-10)[^10]을 활성화 합니다.

이는 각 청크를 저장하는 것을 순서대로 진행하므로, 굉장한 성능 저하를 유발합니다.

#### `Paper.explicit-flush`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

네트워크 채널의 Explicit Flushing을 활성화 합니다.

#### `Paper.strict-thread-checks`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

메인 스레드에서 발생하지 않은 오류를 항상 로그합니다.

#### `Paper.tickList-warn-on-excessive-delay`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

هشدار صادر می‌شود اگر کار انتظاری زیادی داشته باشد.

#### `Paperclip.patchOnly`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `False`

در صورت استفاده از فایل اجرای پیش‌فرض، تنها پچ اعمال می‌شود بدون آغاز سرور.

#### `Plazma.aggressiveOptimize`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `false`

{% hint style="warning" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

بهینه‌سازی پیکربندی که در ابتدای راه‌اندازی اعمال می‌شود را به صورت دقیق‌تر اعمال می‌کند.

فعال کردن آن باعث افزایش سرعت و ایمنی سرور می‌شود، اما ممکن است برخی از جزئیات را مسدود کند یا تأثیر زیادی بر بازی‌پردازی بگذارد.

#### `Plazma.iKnowWhatIAmDoing`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `false`

پیام هشداری[^11] که هنگام مقدمات Plazma نمایش داده می‌شود را سرکوب می‌کند.

### ویژگی منسوخ‌شده <a href="#id-1.3" id="id-1.3"></a>

ویژگی‌های سیستم زیر از ویژگی‌های منسوخ‌شده است.

#### `timings.bypassMax`

- **نوع**: `Boolean`
- **مقدار پیش‌فرض**: `false`
- **توجه**: پس از حذف Timings از Plazma

تعیین می‌کند که آیا می‌توانید حداکثر مقداری را برای ارسال به Timings API Aikar تجاوز کنید یا خیر.

در صورتی که در API بدون استثنا پردازش نشود، محدودیت نرخ اعمال می‌شود.

***

## آرگومان شروع <a href="#id-2" id="id-2"></a>

آرگومان شروع باید پس از `-jar *.jar` وارد شود تا Plazma مقدارهای همراه را هنگام مقدماتی‌سازی پردازش کند.

### راهنمای استفاده <a href="#id-2.1" id="id-2.1"></a>

ویژگی‌های سیستم به عنوان آرگومان دستور برنامه پس از `-jar *.jar` وارد می‌شوند.

به عنوان مثال، اگر می‌خواهید آرگومان شروع `nogui` را اعمال کنید،\
به صورت زیر وارد کنید تا Plazma آرگومان `nogui` را در حین مقدماتی‌سازی پردازش کند.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### کل آرگومان‌های شروع <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **نام مستعار**: `b`
- **مقدار پیش‌فرض**: `bukkit.yml`

نام و مکان [فایل پیکربندی Bukkit](../reference/configurations/bukkit.md) را تنظیم می‌کند.

#### `command-settings`

- **نام مستعار**: `c`
- **مقدار پیش‌فرض**: `commands.yml`

نام و مکان [فایل پیکربندی دستورات Bukkit](../reference/configurations/bukkit.md) را تنظیم می‌کند.

#### `config`

- **نام مستعار**: `c`
- **مقدار پیش‌فرض**: `server.properties`

نام و مکان [فایل خصوصیات سرور](../reference/configurations/property.md) را تنظیم می‌کند.

#### `demo`

سرور را با جهت‌دهی به جهان دمو راه‌اندازی می‌کند.

#### `eraseCache`

پس از ارتقاء جهان، فایل‌های حافظه نهان باقی‌مانده را حذف می‌کند.

#### `forceUpgrade`

بدون توجه به نسخه، جهان را به‌طور اجباری [ارتقاء](#user-content-fn-12)[^12] می‌دهد.

#### `help`

- **نام مستعار**: `?`

تمام آرگومان‌های شروع Plazma و توضیحات آن‌ها را چاپ می‌کند.

#### `initSettings`

فقط فایل‌های پیکربندی را ایجاد می‌کند و سرور را خاموش می‌کند.

#### `jfrProfile`

پروفایل‌دهی JFR را فعال می‌کند.

#### `max-players`

- **نام مستعار**: `s`, `size`
- **مقدار پیش‌فرض**: `(ویژگی‌های سرور)`

حداکثر تعداد [بازیکن](#user-content-fn-14)[^14] مجاز را تنظیم می‌کند.

#### `nogui`

پنل رابط گرافیکی را غیرفعال می‌کند.

#### `nojline`

JLine را غیرفعال می‌کند و از کنسول وانیلایی استفاده می‌کند.

#### `online-mode`

- **نام مستعار**: `o`
- **مقدار پیش‌فرض**: `(ویژگی‌های سرور)`

تصمیم می‌گیرد که آیا با استفاده از سرور اعتبارسنجی Mojang بازیکنان را تأیید کند یا خیر.

**در صورت عدم استفاده از Velocity یا پروکسی‌های دیگر، ممکن است به دلیل نقض [EULA](../getting-started/README.md#id-5) تحریم شوید.**

#### `paper-settings`

- **نام مستعار**: `paper`
- **مقدار پیش‌فرض**: `paper.yml`

{% hint style="warning" %}

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

{% endhint %}

مکان فایل پیکربندی PaperSpigot که از کار افتاده است را تنظیم می‌کند.

این برای انتقال تنظیمات قدیمی به یک فایل پیکربندی جدید استفاده می‌شود و بعد از آن استفاده نمی‌شود.

#### `paper-settings-directory`

- **نام مستعار**: `paper-dir`
- **مقدار پیش‌فرض**: `config`

نام و مکان پوشه حاوی [فایل پیکربندی Paper](../reference/configurations/paper/README.md) را تنظیم می‌کند.

#### `plazma-settings-directory`

- **نام مستعار**: `plazma-dir`

نام و مکان پوشه حاوی [فایل پیکربندی Plazma](../reference/configurations/plazma/README.md) را تنظیم می‌کند.

#### `plugins`

- **نام مستعار**: `p`
- **مقدار پیش‌فرض**: `plugins`

مکان پوشه پلاگین‌ها را تنظیم می‌کند.

#### `pufferfish-settings`

- **نام مستعار**: `pufferfish`
- **مقدار پیش‌فرض**: `pufferfish.yml`

نام و مکان [فایل پیکربندی Pufferfish](../reference/configurations/pufferfish.md) را تنظیم می‌کند.

#### `purpur-settings`

- **نام مستعار**: `purpur`
- **مقدار پیش‌فرض**: `purpur.yml`

نام و مکان [فایل پیکربندی Purpur](../reference/configurations/purpur/README.md) را تنظیم می‌کند.

#### `safeMode`

سرور را به حالت وانیلایی کامل راه‌اندازی می‌کند.

#### `server-ip`

- **نام مستعار**: `h`, `host`
- **مقدار پیش‌فرض**: `(ویژگی‌های سرور)`

نام میزبان سرور یا آدرس پروتکل [اینترنت](#user-content-fn-13)[^13] را تنظیم می‌کند.

#### `server-port`

- **نام مستعار**: `p`, `port`
- **مقدار پیش‌فرض**: `(ویژگی‌های سرور)`

پورت سرور را تنظیم می‌کند.

#### `server-name`

- **مقدار پیش‌فرض**: `A Plazma Server`

نام سرور را تنظیم می‌کند.

#### `spigot-settings`

- **نام مستعار**: `S`
- **مقدار پیش‌فرض**: `spigot.yml`

نام و مکان [فایل پیکربندی Spigot](../reference/configurations/spigot.md) را تنظیم می‌کند.

#### `version`

- **نام مستعار**: `v`

نسخه Plazma را چاپ می‌کند.

#### `world-dir`

- **نام مستعار**: `W`, `universe`, `world-container`
- **مقدار پیش‌فرض**: `(پوشه سرور)`

مکان ذخیره فایل‌های جهان را تنظیم می‌کند.

#### `world-name`

- **نام مستعار**: `w`, `world`
- **مقدار پیش‌فرض**: `(ویژگی‌های سرور)`

نام فایل جهان را تنظیم می‌کند.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: مکان پردازش آرگومان‌ها تغییر می‌کند بر اساس موقعیت اضافه شده.

[^3]: به عنوان مثال، اگر می‌خواهید `Plazma.iKnowWhatIAmDoing` را به `true` تنظیم (فعال) کنید، به جای `-DPlazma.iKnowWhatIAmDoing=true` می‌توانید فقط `-DPlazma.iKnowWhatIAmDoing` را وارد کنید تا به همان شکل عمل کند.

[^4]: به عنوان مثال، `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: دیتکتور رویداد.

[^6]: دیتکتور رویداد.

[^7]: مشتری.

[^8]: نشانه ای که به طور مشابه به ضربان قلب، ارتباط صحیح با سرور را نشان می دهد.

[^9]: با استفاده از قابلیت اخراجی AFK Purpur، می توانید بازیکنان خالی صندلی را هم اخراج کنید.

[^10]: سیستم نوشتن چانک هماهنگ، سینک چانک رایت سیستم.

[^11]: هشدار! پلاسما ممکن است مشکلات غیر منتظره ای ایجاد کند، بنابراین حتماً قبل از استفاده از آن در سرور عمومی آن را به طور کامل تست کنید.\`

[^12]: در بازی `بهینه سازی جهانی` نیز به همین اصول عمل می کند.

[^13]: پروتکل اینترنت، IP.

[^14]: مدیران `سطح 2` به بالا مستثنی می شوند.
