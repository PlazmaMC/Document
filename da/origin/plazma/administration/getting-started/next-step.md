---
description: Lær hvordan du tilpasser serveren.
---

# 📶 Udvikle sig

Grunden til at bruge en ændret serverplatform som Plazma i stedet for den officielle serverplatform fra Mojang Studios er, at det giver mulighed for kraftig **brugerdefinering**.

Her er forskellige måder at tilpasse og bruge Plazma på.

## Konfigurationsændringer <a href="#id-1" id="id-1"></a>

Den mest grundlæggende måde at tilpasse Plazma på er ved at ændre konfigurationen.

Plazma tilbyder kraftfulde konfigurationsindstillinger, lige fra spillets mekanik til mobegenskaber.

Se nedenstående side for en beskrivelse af Plazmas konfigurationer.

{% content-ref url="../reference/configurations/" %}
[konfigurationer](../reference/configurations/)
{% endcontent-ref %}

***

## Brug af plugins <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma understøtter alle plugins baseret på Paper korrekt.**

For Spigot plugins kan der være nogle problemer med Paper's mappingændringer fra 1.20.5, men de fleste plugins baseret på Paper som f.eks. Paper, Pufferfish og Purpur fungerer korrekt i Plazma. Hvis de ikke fungerer korrekt, skyldes det en fejl i Plazma, så [venligst rapporter det med det samme.](../diagnosis/plugins.md)

{% endhint %}

At bruge Plazma er den primære årsag og den mest kraftfulde måde at tilpasse Plazma på.
Plazmas stærke plugin-økosystem gør det nemt at tilpasse serveren.

Der er flere måder at finde og downloade plugins på. Nogle plugins uploades til offentlige opbevaringstjenester, mens andre uploades til GitHub eller deres egne sider.

{% hint style="caution" %}

**Plugins kan få direkte adgang til systemet!**

Brug tjenester som VirusTotal til altid at kontrollere, om et plugin er sikkert, før du anvender det, eller download plugins fra pålidelige tjenester.

{% endhint %}

Der er flere tjenester til at downloade plugins. Tjenester som [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) gennemgår en godkendelsesproces, før plugins uploades, for at sikre at kun sikre plugins distribueres.

### Anvendelse af plugins <a href="#id-2.1" id="id-2.1"></a>

Når du har downloadet et plugin, er det nu tid til at anvende det.

1. Plugins er i form af `.jar` eller `Java Executable File`.\
   Nogle plugins kan være i en komprimeret fil, hvor du skal udpakke den og bruge filen, der indeholder 'bukkit', 'spigot' eller 'paper' i navnet, og hvis der er en fil med 'fat', skal du bruge den.
2. Placer den downloadede fil i servermappen 'plugins' og genstart (eller start) serveren.
3. Når Plazma starter, vises der nye oplysninger på konsollen.
   Dette betyder, at Plazma har indlæst pluginnet korrekt.
4. Selvom Plazma har indlæst pluginnet korrekt, kan det være, at pluginnet ikke starter.
   Ved at bruge kommandoen `/plugins` kan du se en liste over de aktuelt indlæste plugins på serveren.
   Hvis navnet på det installerede plugin ikke er <mark style="background-color:red;">rødt</mark>, men i stedet er <mark style="background-color:green;">grønt</mark>, er pluginnet indlæst korrekt.

Hvis et plugin ikke er indlæst korrekt, kan du finde løsninger på problemerne på følgende side.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Brug af datapakker <a href="#id-3" id="id-3"></a>

Datapakker er en måde at tilpasse Minecraft på, ligesom ressourcepakker.

Ved at bruge datapakker kan du tilføje nye grupper af væsener og udfordringer i spillet.

{% hint style="caution" %}

**Datapakker kan beskadige verdener!**

Nogle defekte datapakker kan beskadige verdener, og dette kan ikke fortrydes.

Det anbefales derfor at tage en sikkerhedskopi af verdenen, før du anvender datapakker.

{% endhint %}

Datapakker kan downloades fra flere tjenester som [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) og andre.

Når du har downloadet en datapakke, kan du anvende den ved at placere den i mappen 'datapacks' i serverens verden.
Opret mappen, hvis den ikke allerede findes.

{% hint style="warning" %}

**I nogle tilfælde kan visse datapakker[^2] muligvis ikke anvendes korrekt ved første anvendelse.**

I så fald anbefales det at genstarte serveren **2 gange**.

{% endhint %}

Datapakker kan nemt blive beskadiget, når Minecraft opdateres.

Især hvis en datapakke er alvorligt beskadiget, kan det få serveren til at krashe, så det er vigtigt at teste serveren tilstrækkeligt, før du opdaterer.

{% hint style="info" %}

**Efter serverstartkommandoen kan du indtaste 'safeMode' for at deaktivere alle datapakker og derefter starte serveren.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safemode)

{% endhint %}

Du kan bekræfte, hvilke datapakker der er anvendt, ved at bruge kommandoen `/datapack list`.

***

## Optimering <a href="#id-4" id="id-4"></a>

Der er blevet anvendt mange optimeringspatches på Plazma. 또한, Plazma가 처음으로 시작되면 자동으로
구성을 최적화 하므로 [시작하기](./README.md) 설명서를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우,
아래 설명서를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxy muliggør forbindelse mellem servere og tillader spillere at bevæge sig mellem servere eller kommunikere med andre servere uden ekstra arbejde.

Se nedenstående side for information om sikker og korrekt proxykonfiguration.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Sikkerhed <a href="#id-5" id="id-5"></a>

Da Minecraft-mods er blevet mere avancerede, er det nemt at finde [sårbarhedsangrebsmotorer](#user-content-fn-3) online.

De fleste sårbarheder, der er mulige i almindelige spil, er [grundlæggende blokeret](#user-content-fn-4) som standard, men angreb på sårbarheder via tredjepartsindlæsere er ikke blokeret.

Derfor anbefales det at installere anti-snyde-plugins og konfigurere proxy, automatisk genstart, backup osv., hvis serveren er offentlig tilgængelig, for at blokere for sårbarhedsudnyttelse og muliggøre hurtig genopretning i tilfælde af nedbrud.

### Tilladelsesindstillinger <a href="#id-5.1" id="id-5.1"></a>

Nogle plugins' administratorkommandoer kan have sårbarheder, hvis tilladelserne ikke er korrekt konfigureret.

Det anbefales at bruge tillægsadministration plugins som [LuckPerms](https://luckperms.net/) til at begrænse almindelige brugeres tilladelser.

### X-Ray blokering <a href="#id-5.2" id="id-5.2"></a>

X-Ray er en af de sårbarheder, der nemt kan udnyttes selv på grundlæggende optimerede klienter.

Plazma tilbyder en konfiguration, der som standard kan blokere X-Ray.

Se nedenstående side for metoden til X-Ray blokering og yderligere forklaring.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

Hvis kun visse brugere skal kunne tilslutte sig serveren, anbefales det at bruge [Ngrok](./README.md#id-6.2) til at bruge en [obskureret serveradresse](#user-content-fn-5) eller indstille en whitelist for at forhindre andre spillere i at tilslutte sig.

Du kan tillade en spillers forbindelse via '/whitelist add <spiller>' i serverkonsollen eller forbyde en spillers forbindelse igen via '/whitelist remove <spiller>'.

Brug '/whitelist query' for at se, hvilke spillere der har tilladelse til at tilslutte sig.

***

[^1]: Eller Minecraft: Bedrock Editions add-ons.

[^2]: Tilføjelse af væsener og mere.

[^3]: Generelt kaldes det 'cheating'.

[^4]: Hvis konfigurationen ikke er optimeret, hvis Plazma er forældet, eller hvis der er nye sårbarheder, kan de muligvis ikke være blokeret.

[^5]: Når en spiller tilslutter sig serveren, sker det via en Ngrok proxyserver, og den tildelte Ngrok-adresse ændres ved hver genstart.
