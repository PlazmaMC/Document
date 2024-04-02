---
description: درباره سوالات متداول بازدید کنید.
---

# ⁉️ سوالات متداول

{% hint style="info" %}

**آیا نمی‌توانید پاسخ دلخواه خود را پیدا کنید؟**

[سرور رسمی Discord](https://discord.gg/MmfC52K8A8) یا [مشکلات GitHub](https://github.com/PlazmaMC/PlazmaBukkit/issues) را برای پرسش‌های خود به جامعه ارسال کنید!

{% endhint %}

### پیامی نمایش داده شده و اجرا نمی شود

اگر پیام `no main manifest attribute, in plazma-(version).jar` در کنسول نمایش داده شده است،\
فایلی که دانلود کرده اید یک فایل API توسعه‌یافته است، باید **Reobf Paperweight** را از صفحه GitHub دانلود کنید.

برای اطلاعات بیشتر به صفحه زیر مراجعه کنید.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### هر بار که سرور راه‌اندازی می‌شود، یک هشدار نمایش داده می شود

Plazma شامل برخی از پچ‌های ناپایدار است و همیشه احتمال اشتباه وجود دارد، بنابراین این هشدارها را هنگام راه‌اندازی سرور چاپ می‌کند.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

این هشدار با استفاده از ویژگی سیستم [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] قابل غیرفعال سازی است.

برای اطلاعات بیشتر به صفحه زیر مراجعه کنید.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: قابل دسترس از نسخه 1.20.1
