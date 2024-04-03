---
description: Ta reda på hur du anpassar servern för användare.
---

# 📶 Utvecklingssteg

Anledningen till att man använder en modifierad serverplattform som Plazma istället för den officiella serverplattformen från Mojang Studios är att den ger möjlighet till kraftfull **anpassning**.

Här är olika sätt att anpassa och använda Plazma.

## Konfigurationsändring <a href="#id-1" id="id-1"></a>

Det mest grundläggande sättet att anpassa Plazma är att ändra konfigurationen.

Plazma erbjuder kraftfulla konfigurationsinställningar från spelets mekanik till monsterattribut.

Se nedan sida för information om Plazmas konfiguration.

{% content-ref url="../reference/configurations/" %}
[konfigurationer](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**[Vissa datapaket](#user-content-fn-2)[^2] kan inte tillämpas korrekt vid första tillämpningen.**

För att hantera detta rekommenderas att starta om servern **två gånger**.

{% endhint %}

Datapaket kan lätt skadas varje gång Minecraft uppdateras.

Särskilt om datapaketet är allvarligt skadat kan det leda till serverkollisioner, så det är viktigt att testa noggrant innan du uppdaterar servern.

{% hint style="info" %}

**Efter serverstartkommandot kan du skriva `safeMode` för att inaktivera alla datapaket och sedan starta om servern.**

För mer information, se `Referens > Argument och egenskaper`.](../reference/arguments.md#safeMode)

{% endhint %}

Du kan kontrollera vilka datapaket som har tillämpats med kommandot `/datapack list`.

***

## Optimering <a href="#id-4" id="id-4"></a>

Plazma har många optimeringspatchar. När Plazma först startas optimeras konfigurationen automatiskt, så om du följer [Starta](./README.md) -guiden behöver du inte göra ytterligare optimeringsåtgärder.

Men om många spelare ansluter eller om världen är stor, kan du genomföra ytterligare optimeringsåtgärder enligt nedan guide.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxyn ansluter servrar och låter spelare flytta mellan servrar eller kommunicera med andra servrar utan extra åtgärder.

Se nedanstående sida för information om säker och korrekt proxykonfiguration.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Säkerhet <a href="#id-5" id="id-5"></a>

Med Minecrafts utveckling är det lätt att hitta [sårbarhetsattacksmotorer](#user-content-fn-3)[^3] även online.

Många sårbarheter som är möjliga att utnyttja i vanliga spel är [grundläggande blockerade](#user-content-fn-4)[^4],
men att utnyttja sårbarheter med tredjepartsbelastare är inte blockerat.

Därför rekommenderas att installera anti-cheat-plugins och konfigurera proxy, automatisk omstart, säkerhetskopiering etc. om servern är offentlig för att förhindra sårbarhetsutnyttjande och snabbt återhämta sig om servern går ner.

### Behörighetsinställning <a href="#id-5.1" id="id-5.1"></a>

Vissa administratörskommandon från vissa plugins kan ha sårbarheter om behörigheterna inte är korrekt inställda.

Det rekommenderas att använda behörighetsplugins som [LuckPerms](https://luckperms.net/) för att begränsa vanliga användares behörigheter.

### X-Ray-blockering <a href="#id-5.2" id="id-5.2"></a>

X-Ray är en av de sårbarheter som är lätt att använda även med grundläggande optimerade klienter.

Plazma erbjuder en konfiguration för att blockera X-Ray som standard.

Se nedanstående sida för information om X-Ray-blockering.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Vitlista <a href="#id-5.3" id="id-5.3"></a>

Om endast vissa användare ska kunna ansluta till servern är det rekommenderat att använda [Ngrok](./README.md#id-6.2) för att använda en [obfuskerad serveradress](#user-content-fn-5)[^5] eller ställa in en vitlista för att förhindra andra spelare från att ansluta.

Via serverkonsolen kan du tillåta en spelares anslutning med `/whitelist add <spelare>` eller förbjuda en spelares anslutning med `/whitelist remove <spelare>`.

För att se vilka spelare som är vitlistade använd `/whitelist query`.

***

[^1]: Eller använda add-ons för Minecraft: Bedrock Edition.

[^2]: Lägg till nya entiteter och mer.

[^3]: Det kallas vanligtvis "hack".

[^4]: Om konfigurationen inte är optimerad, om Plazma är föråldrat eller om nya sårbarheter upptäcks kan de eventuellt inte vara blockerade.

[^5]: När spelare ansluter till servern görs det via en Ngrok-proxyserver och den utfärdade Ngrok-adressen ändras vid varje omstart.
