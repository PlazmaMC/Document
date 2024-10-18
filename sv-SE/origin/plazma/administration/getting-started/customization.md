---
description: Ta reda på hur du anpassar servern för användare.
---

# 🎨 Anpassning för användare

Anledningen till att man använder en modifierad serverplattform som Plazma istället för den officiella serverplattformen från Mojang Studios är att den ger möjlighet till kraftfull **anpassning**.

Här är olika sätt att anpassa och använda Plazma.

## Konfigurationsändring <a href="#id-1" id="id-1"></a>

Det mest grundläggande sättet att anpassa Plazma är att ändra konfigurationen.

Plazma erbjuder kraftfulla konfigurationsinställningar från spelets mekanik till monsterattribut.

Se nedan sida för information om Plazmas konfiguration.

{% content-ref url="../reference/configurations/" %}
[konfigurationer](../reference/configurations/)
{% endcontent-ref %}

## Användning av tillägg <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma stöder alla pluginer baserade på Papper på ett korrekt sätt.**

För Spigot-pluginer kan vissa inte fungera på grund av kartändringar från Papper från 1.20.5, men de flesta pluginer baserade på Papper, Pufferfish och Purpur fungerar även på Plazma. Om de inte fungerar korrekt är det ett fel med Plazma, så vänligen [rapportera det omedelbart.](../diagnosis/plugins.md)

{% endhint %}

Detta är en av de främsta anledningarna till att använda Plazma och den mest kraftfulla metoden för att anpassa Plazma.
Plazmas kraftfulla plugin-ekosystem gör det enkelt att anpassa servern.

Det finns olika sätt att hitta och ladda ner pluginer. Vissa pluginer laddas upp på offentliga lagringstjänster, medan andra laddas upp på GitHub eller egna webbplatser.

{% hint style="caution" %}

**Pluginer kan få direkt åtkomst till systemet!**

Använd VirusTotal eller liknande tjänster för att alltid kontrollera att en plugin är säker innan du använder den, eller ladda ner pluginen från en betrodd källa.

{% endhint %}

Det finns olika tjänster för att ladda ner pluginer. Bland dessa, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) är tjänster där pluginer granskas innan de laddas upp, vilket säkerställer att endast säkra pluginer distribueras.

### Tillämpa pluginer <a href="#id-2.1" id="id-2.1"></a>

När du har laddat ner en plugin är det dags att tillämpa den.

1. Pluginer finns som `.jar` eller `Java Executable File`. Vissa kan vara komprimerade, och i så fall ska du extrahera dem och använda filen som innehåller `bukkit`, `spigot` eller `papper` i namnet, samt filen med `fat` om det finns.
2. Placera den nedladdade filen i mappen `plugins` i serverns katalog och starta om servern.
3. När Plazma startar kommer det att finnas nytt innehåll i konsolen.
   Detta indikerar att Plazma har laddat pluginen korrekt.
4. Även om Plazma har laddat pluginen korrekt kanske pluginen inte startas.
   Använd kommandot `/plugins` för att visa vilka pluginer som är laddade på servern.
   Om namnet på en installerad plugin inte är <mark style="background-color:red;">rött</mark> utan <mark style="background-color:green;">grönt</mark>, har pluginen laddats korrekt.

Om en plugin inte har laddats korrekt kan du hitta lösningar på problemet på följande sida.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Användning av datapaket <a href="#id-3" id="id-3"></a>

Datapaket är ett sätt att anpassa Minecraft, liknande resurspaket.

Med datapaket kan du lägga till nya entiteter och utmaningar i spelet.

{% hint style="caution" %}

**Datapaket kan skada världen!**

Vissa felaktiga datapaket kan skada världen irreparabelt.

Det rekommenderas att säkerhetskopiera världen innan du tillämpar datapaket.

{% endhint %}

Datapaket kan också laddas ner från olika tjänster som [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) och andra.

När du har laddat ner datapaketet kan du placera det i mappen `datapacks` i serverns världskatalog.
Om mappen inte finns kan du skapa den och lägga till datapaketet där.

{% hint style="warning" %}

**Vissa [datapaket](#user-content-fn-2) kan inte tillämpas korrekt vid första försöket.**

För att hantera detta rekommenderas att starta om servern **två gånger**.

{% endhint %}

Datapaket kan lätt skadas varje gång Minecraft uppdateras.

Särskilt om datapaketet är allvarligt skadat kan det leda till serverkollisioner, så det är viktigt att testa noggrant innan du uppdaterar servern.

{% hint style="info" %}

**Efter serverstartkommandot kan du skriva `safeMode` för att inaktivera alla datapaket och sedan starta om servern.**

[Se `Referens > Argument och parametrar` för mer information.](../reference/arguments.md)

{% endhint %}

Du kan kontrollera vilka datapaket som har tillämpats med kommandot `/datapack list`.

***

[^1]: Eller använda add-ons för Minecraft: Bedrock Edition.

[^2]: Lägg till nya entiteter och mer.
