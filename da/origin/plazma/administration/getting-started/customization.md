---
description: Lær hvordan du tilpasser serveren.
---

# 🎨 Brugerdefinering

Grunden til at bruge en ændret serverplatform som Plazma i stedet for den officielle serverplatform fra Mojang Studios er, at det giver mulighed for kraftig **brugerdefinering**.

Her er forskellige måder at tilpasse og bruge Plazma på.

## Konfigurationsændringer <a href="#id-1" id="id-1"></a>

Den mest grundlæggende måde at tilpasse Plazma på er ved at ændre konfigurationen.

Plazma tilbyder kraftfulde konfigurationsindstillinger, lige fra spillets mekanik til mobegenskaber.

Se nedenstående side for en beskrivelse af Plazmas konfigurationer.

{% content-ref url="../reference/configurations/" %}
[konfigurationer](../reference/configurations/)
{% endcontent-ref %}

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

**Nogle [datapakker](#user-content-fn-2) fungerer muligvis ikke korrekt ved første anvendelse.**

I så fald anbefales det at genstarte serveren **2 gange**.

{% endhint %}

Datapakker kan nemt blive beskadiget, når Minecraft opdateres.

Især hvis en datapakke er alvorligt beskadiget, kan det få serveren til at krashe, så det er vigtigt at teste serveren tilstrækkeligt, før du opdaterer.

{% hint style="info" %}

**Efter serverstartkommandoen kan du indtaste 'safeMode' for at deaktivere alle datapakker og derefter starte serveren.**

[Se 'Reference > Arguments' for flere detaljer.](../reference/arguments.md)

{% endhint %}

Du kan bekræfte, hvilke datapakker der er anvendt, ved at bruge kommandoen `/datapack list`.

***

[^1]: Eller Minecraft: Bedrock Editions add-ons.

[^2]: Tilføjelse af væsener og mere.
