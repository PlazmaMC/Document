---
description: למענה על שאלות נפוצות, בדוק כאן.
---

# ⁉️ שאלות נפוצות

{% hint style="info" %}

**לא מוצאים את התשובה שחיפשתם?**

[שרת Discord רשמי](https://discord.gg/MmfC52K8A8) או [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) לשאול שאלות בקהילה!

{% endhint %}

### Plazma לא מתחיל

אם מופיע בקונסולה `no main manifest attribute, in plazma-(version).jar`,\
אז הקובץ שהורדתם הוא קובץ API לצורכי פיתוח, עליכם להוריד את **Reobf Paperweight** מעמוד ה-GitHub.

למידע נוסף, ראו את הדף הבא.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### אזהרה מופיעה בכל פעם שהשרת מתחיל לרוץ

Plazma מכיל תיקונים לא יציבים חלקים ולכן יש תמיד סיכוי לתקלות, על כן השרת מדפיס אזהרות כאלו בזמן הפעלתו.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

ניתן להשבית את ההודעות האלו באמצעות השימוש במאפיין המערכת [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

למידע נוסף, ראו את הדף הבא.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: זמין מגרסה 1.20.1 ומעלה
