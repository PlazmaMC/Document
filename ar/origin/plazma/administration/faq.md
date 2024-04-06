---
description: تعرف على الأسئلة المتكررة.
---

# ⁉️ الأسئلة المتكررة

{% hint style="info" %}

**هل لم تجد الإجابة التي تبحث عنها؟**

[الخادم الرسمي لديسكورد](https://discord.gg/MmfC52K8A8) أو من خلال [مناقشات GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions)، جرب أن تسأل المجتمع!

{% endhint %}

### لا يمكن بدء Plazma

إذا ظهرت `no main manifest attribute, in plazma-(version).jar` على الكونسول،\
فإن الملف الذي تم تنزيله هو ملف API للتطوير، يجب عليك تنزيل **Reobf Paperweight** من صفحة GitHub.

يرجى الرجوع إلى الصفحة التالية لمزيد من التفاصيل.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### تظهر تحذيرات عند بدء تشغيل الخادم

يحتوي Plazma على بعض التصحيحات غير المستقرة وقد تعمل بشكل غير صحيح دائمًا، لذا يتم طباعة تحذيرات مثل هذه عند بدء تشغيل الخادم.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

يمكن تعطيل هذه التحذيرات باستخدام خاصية النظام [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

يرجى الرجوع إلى الصفحة التالية لمزيد من التفاصيل.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: متاحة اعتبارًا من الإصدار 1.20.1
