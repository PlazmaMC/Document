---
description: Leer hoe om die bediener aan te pas vir gebruikers.
---

# 🎨 Gebruikersaanpassing

Die rede waarom aangepaste bedienerplatforms soos Plazma gebruik word, sonder om die amptelike bedienerplatform wat deur Mojang Studios voorsien word, te gebruik, is dat dit die moontlikheid van sterk **aanpassing** bied.

Hieronder is verskeie maniere om Plazma aan te pas en te benut.

## Konfigurasie wysig <a href="#id-1" id="id-1"></a>

Die basiese metode om Plazma aan te pas is deur die konfigurasie te wysig.

Plazma bied kragtige konfigurasie-instellings, van die spel se meganika tot die eienskappe van monsters.

Raadpleeg die onderstaande bladsy vir 'n uiteensetting oor Plazma se konfigurasie.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## Plugin gebruik <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma ondersteun normaalweg alle op papier-gebaseerde plugins.**

Vir Spigot-plugins kan dit weens 'n verandering in die kartering vanaf 1.20.5 na Paper dalk nie behoorlik werk nie, maar
die meeste plugins wat op Paper, Pufferfish en Purpur gebaseer is, werk almal in Plazma,
en as dit nie behoorlik werk nie, is dit 'n fout in Plazma, so meld dit asseblief [hier.](../diagnosis/plugins.md)

{% endhint %}

Dit is 'n belangrike rede om Plazma te gebruik en die sterkste manier om Plazma te personaliseer.
Die kragtige plugin-ekosisteem van Plazma maak dit maklik om die bediener te personaliseer.

Daar is verskeie maniere om plugins te soek en af te laai. Sommige plugins word op openbare bergingsdiens opgelaai, terwyl ander op GitHub of hul eie webwerwe opgelaai word.

{% hint style="caution" %}

**Plugins kan direk tot die stelsel toegang verkry!**

Gebruik dienste soos VirusTotal om altyd te verseker dat plugins veilig is voordat dit toegepas word,
of laai plugins af van betroubare dienste.

{% endhint %}

Daar is verskeie dienste beskikbaar vir die aflaai van plugins. Onder andere dienste soos [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) keur plugins goed voordat dit opgelaai word, en verseker dat slegs veilige plugins versprei word.

### Pas 'n plugin toe <a href="#id-2.1" id="id-2.1"></a>

Nadat jy 'n plugin afgelaai het, is dit tyd om dit toe te pas.

1. Plugins is in `.jar`- of `Java-uitvoerbare lêer`-formaat.
   Sommige plugins is in 'n saamgepersde lêer, waar jy die saamgepersde lêer moet uitpak en gebruik as die lêer 'bukkit', 'spigot' of 'paper' in die naam het, en
   as daar 'fat' lêers saam is, gebruik die 'fat' lêer.
2. Plaas die afgelaai lêer in die `plugins`-vouer van die bediener en (her)begin die bediener.
3. As Plazma begin, sal daar nuwe inhoud op die konsole wees.
   Dit beteken dat Plazma die plugins suksesvol gelaai het.
4. Selfs al het Plazma die plugins suksesvol gelaai, kan dit wees dat die plugins nie begin het nie.
   Met die `/plugins`-bevel kan jy die plugins wat tans op die bediener gelaai is, sien.
   As die naam van die geïnstalleerde plugin nie in <mark style="background-color:red;">rooi</mark> nie, maar in <mark style="background-color:green;">groen</mark> is, is die plugin suksesvol gelaai.

As die plugin nie suksesvol gelaai het nie, kan jy op die volgende bladsy 'n oplossing vir die probleem vind.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Gebruik van datapakket <a href="#id-3" id="id-3"></a>

Datapakke is 'n manier om die spel aan te pas, soortgelyk aan hulpbronne-pakket.

Met datapakke kan jy nuwe entiteite en uitdagings by die spel voeg.

{% hint style="caution" %}

**Datapakke kan die wêreld beskadig!**

Sommige gebrekkige datapakke kan die wêreld beskadig en dit kan nie ongedaan gemaak word nie.

Dit word aanbeveel om die wêreld te rugsteun voordat datapakke toegepas word.

{% endhint %}

Datapakke kan ook van verskeie dienste afgelaai word, soos [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) en ander.

Plaas die datapakket in die `datapacks`-vouer van die bediener se wêreld as jy dit afgelaai het.
As die vouer nie bestaan nie, skep dit en voeg die datapakket toe.

{% hint style="warning" %}

**Sommige [datapakket](#user-content-fn-2) werk nie korrek nadat dit die eerste keer toegepas is nie.**

Dit word aanbeveel om die bediener **2 keer** te herlaai as dit nie korrek toegepas is nie.

{% endhint %}

Datapakket kan maklik beskadig word wanneer Minecraft opdateer.

Dit is belangrik om die bediener genoeg te toets voordat dit opdateer, omdat die bediener kan bots as die datapakket heeltemal beskadig is.

{% hint style="info" %}

**Na die bedieningsbevel kan jy `safeMode` agter die bediener se aanvangsbevel plaas om al die datapakket te deaktiveer voordat die bediener begin.**

[Vir meer inligting, sien `Verwysings > Argumente en eienskappe`.](../reference/arguments.md)

{% endhint %}

Bevestig die toegepaste datapakke met die `/datapack list`-bevel.

***

[^1]: Of Minecraft: Bedrock-uitgawe se byvoegings.

[^2]: Voeg entiteite en meer by.
