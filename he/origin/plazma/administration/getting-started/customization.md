---
description: ללמוד כיצד להתאים אישית את השרת.
---

# 🎨 התאמה אישית

הסיבה לשימוש בפלטפורמת השרת המותאמת כמו Plazma במקום בפלטפורמת השרת הרשמית שסופקה על ידי Mojang Studios היא היכולת החזקה להתאמה אישית שהיא מציעה.

להלן מספר דרכים להתאמה אישית ושימוש ב-Plazma.

## שינויי ההגדרות <a href="#id-1" id="id-1"></a>

הדרך הבסיסית ביותר להתאמה אישית של Plazma היא לשנות את ההגדרות.

Plazma מספקת הגדרות חזקות למשחק, כולל מנגנונים ותכונות של יצורים.

למידע נוסף על ההגדרות של Plazma ראה את הדף הבא.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## שימוש בתוספים <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma תומך בכל התוספים המבוססים על נייר.**

במקרה של תוסף Spigot, עקב שינויי המיפוי של Paper מגרסה 1.20.5, יתכן שחלקם לא יפעלו, אך רוב התוספים המבוססים על Paper כגון Paper, Pufferfish ו-Purpur יפעלו ב-Plazma, ואם הם לא פועלים כראוי זה תקלה ב-Plazma ויש לדווח [מיידית.](../diagnosis/plugins.md)

{% endhint %}

זהו הסיבה העיקרית לשימוש ב-Plazma והדרך החזקה ביותר להתאמה אישית של Plazma.
האקוסיסטם החזק של Plazma מאפשר לשרת להתאמה אישית בקלות.

ישנם מספר דרכים למציאת והורדת תוספים. קיימות מספר שיטות להורדת התוספים, כמה מתקיים בשירותי מאגרים פומביים וכמה עלולים להעלות את התוספים ל-GitHub או לאתרים משלהם.

{% hint style="caution" %}

**תוסף יכול לגשת למערכת ישירות!**

נא לוודא את ביטחונך תמיד לפני שמתקין תוסף, על ידי שימוש בשירותים כמו VirusTotal או הורדת התוסף משירותים אמינים.

{% endhint %}

ישנם מספר שירותים להורדת התוספים. ביניהם, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) ועוד, שירותים אלו עוברים תהליך שיקול והעלאת התוספים לפני שהם מוצעים להורדה, כך שרק התוספים הבטוחים מוצעים לשימוש.

### התקנת תוסף <a href="#id-2.1" id="id-2.1"></a>

לאחר הורדת התוסף, כעת תהיה ההזדמנות להתקין את התוסף.

1. התוסף מורכב מקובץ `.jar` או `Java Executable File`.\
   חלק מהתוספים מגיעים בתוך קובץ דחיסה, ובמקרים כאלו
   יש לפתוח את הדחיסה ולחפש אחר קובץ המכיל את `bukkit`, `spigot` או `paper` בשמו, ובמידה ויש קובץ המכיל `fat` יש להשתמש בקובץ זה.
2. יש להעביר את הקובץ שהורדת לתיקיית `plugins` שבתיקיית השרת ולאחר מכן לאתחל את השרת.
3. בהתחלת Plazma, יוצג תוכן חדש בקונסולה.
   זה מעיד על טעינה תקינה של התוספים על ידי Plazma.
4. אף אם Plazma טענה את התוספים בצורה תקינה, יתכן שהם לא הופעלו.
   ניתן לקרוא את רשימת התוספים שטענו על ידי השרת באמצעות הפקודה `/plugins`.
   אם שמות התוספים שהותקנו אינם בצבע <mark style="background-color:red;">אדום</mark>
   אלא בצבע <mark style="background-color:green;">ירוק</mark>, זה אומר שהתוספים נטענו בהצלחה.

אם התוספים לא נטענו בהצלחה, ניתן למצוא פתרונות בדף הבא.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## שימוש בחבילת מידע <a href="#id-3" id="id-3"></a>

חבילת המידע היא אמצעי התאמה אישית במיינקראפט, דומה לחבילות משאבים.

באמצעות חבילת מידע ניתן להוסיף קבוצות חייקים חדשות ואתגרים למשחק ולשנות חלקים במשחק.

{% hint style="caution" %}

**חבילת המידע עשויה לפגוע בעולם!**

חלק מחבילות המידע הקרוחות עשויות לפגוע בעולם ולא ניתן לשחזר את הנזק.

לכן, מומלץ לגבות את העולם לפני החלפת חבילת המידע.

{% endhint %}

ניתן להוריד חבילות מידע ממספר שירותים כגון [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) ועוד.

לאחר הורדת חבילת המידע, ניתן להכניס אותה לתיקיית `datapacks` בתיקיית העולם של השרת.
במקרה שאין תיקייה זו, ניתן ליצור אותה ולהוסיף את החבילה.

{% hint style="warning" %}

**לחלק [חבילות המידע](#user-content-fn-2) ייתכן שלא תתקבל התקנה תקינה בפעם הראשונה.**

למקרים כאלה מומלץ לאתחל את השרת **2 פעמים**.

{% endhint %}

חבילות המידע עשויות להיפגע בכל עדכון של Minecraft.

במיוחד, במקרה שהחבילה נפגעה לחלוטין, יש לבצע בדיקות מספיקות לפני העדכון כדי למנוע התנגשות בשרת.

{% hint style="info" %}

**ניתן להפעיל את השרת עם `safeMode` אחרי הפקודת ההפעלה כדי להשבית את כל חבילות המידע.**

[לפרטים נוספים ראו `רפרנס > ארגומנטים ומאפיינים`.](../reference/arguments.md)

{% endhint %}

ניתן לוודא את רשימת חבילות המידע שהופעלו בשרת על ידי הפקודה `/datapack list`.

***

[^1]: או על ידי Minecraft: Bedrock Edition's add-ons.

[^2]: הוספת קבוצות חייקים ועוד.
