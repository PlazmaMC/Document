---
description: Leer hoe om die bediener aan te pas vir gebruikers.
---

# 📶 Ontwikkelingsfase

Die rede waarom aangepaste bedienerplatforms soos Plazma gebruik word, sonder om die amptelike bedienerplatform wat deur Mojang Studios voorsien word, te gebruik, is dat dit die moontlikheid van sterk **aanpassing** bied.

Hieronder is verskeie maniere om Plazma aan te pas en te benut.

## Konfigurasie wysig <a href="#id-1" id="id-1"></a>

Die basiese metode om Plazma aan te pas is deur die konfigurasie te wysig.

Plazma bied kragtige konfigurasie-instellings, van die spel se meganika tot die eienskappe van monsters.

Raadpleeg die onderstaande bladsy vir 'n uiteensetting oor Plazma se konfigurasie.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**[Sommige datapakke](#user-content-fn-2)[^2] kan aanvanklik nie korrek toegepas word nie.**

Dit word aanbeveel om die bediener **2 keer** te herlaai as dit nie korrek toegepas is nie.

{% endhint %}

Datapakket kan maklik beskadig word wanneer Minecraft opdateer.

Dit is belangrik om die bediener genoeg te toets voordat dit opdateer, omdat die bediener kan bots as die datapakket heeltemal beskadig is.

{% hint style="info" %}

**Na die bedieningsbevel kan jy `safeMode` agter die bediener se aanvangsbevel plaas om al die datapakket te deaktiveer voordat die bediener begin.**

[Vir meer inligting, sien `Verwysing > Argumente en eienskappe`](../reference/arguments.md#safeMode)

{% endhint %}

Bevestig die toegepaste datapakke met die `/datapack list`-bevel.

***

## Optimalisering <a href="#id-4" id="id-4"></a>

Plazma het baie optimaliseringspatches wat toegepas is. Verder, as Plazma vir die eerste keer begin, optimaliseer dit outomaties die konfigurasie, dus as jy die [Begin](./README.md) handleiding volg, is daar geen verdere optimaliseringswerk nodig nie.

Tog, as baie spelers aansluit of as die wêreld baie groot is, kan jy deur die volgende handleiding verdere optimaliseringswerk doen.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proksi <a href="#id-5" id="id-5"></a>

Proksi koppel bedieners aan mekaar en maak dit vir spelers moontlik om sonder addisionele werk van bediener te skuif of met ander bedieners te kommunikeer.

Vir inligting oor veilige en korrekte proksi-instellings, sien die volgende bladsy.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Veiligheid <a href="#id-5" id="id-5"></a>

Minecraft het so 'n gevorderde mods dat dit maklik is om 'n [swakheid-aanval-enjin](#user-content-fn-3)[^3] aanlyn te kry.

Meeste van die algemene swakhede wat in gewone speletjies uitgevoer kan word, is [basies geblokkeer](#user-content-fn-4)[^4], maar om swakhede aan te val deur 'n derde party-laaier word nie geblokkeer nie.

Dus, as die bediener oop is, word dit aanbeveel om anti-bedrog-inprop ensovoorts te installeer om swakhede te blokkeer, en om proksi en outomatiese herlaaiing, rugsteun, ens. te konfigureer sodat die bediener vinnig herstel kan word as dit af is.

### Toestemming instellings <a href="#id-5.1" id="id-5.1"></a>

Sommige inprop se administratiewe bevele het swakhede wat nie behoorlik ingestel is nie.

Dit word aanbeveel om 'n toestemmingbestuur-inprop soos [LuckPerms](https://luckperms.net/) te gebruik om die regte van gewone gebruikers te beperk.

### X-Ray blokkering <a href="#id-5.2" id="id-5.2"></a>

X-Ray is een van die swakhede wat maklik in basiese optimaliseringskliënte gebruik kan word.

Plazma bied 'n konfigurasie wat X-Ray standaard kan blokkeer.

Raadpleeg die volgende bladsy vir inligting oor hoe om X-Ray te blokkeer.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Witlys <a href="#id-5.3" id="id-5.3"></a>

As slegs sekere gebruikers toegang tot die bediener mag hê, word dit aanbeveel om [Ngrok](./README.md#id-6.2) te gebruik om 'n [versleutelde bedieneradres te gebruik](#user-content-fn-5)[^5], of om 'n witlys in te stel sodat ander spelers nie kan aansluit nie.

Jy kan spelerstoegang toelaat deur `/whitelist add <speler>` in die bedienerkonsole te gebruik, of jy kan spelerstoegang weer ontneem deur `/whitelist remove <speler>` te gebruik.

Gebruik `/whitelist query` om te sien watter spelers toegang het.

***

[^1]: Of Minecraft: Bedrock-uitgawe se byvoegings.

[^2]: Voeg entiteite en meer by.

[^3]: Gewoonlik genoem as "hacks".

[^4]: As die konfigurasie nie geoptimaliseer is nie, of as Plazma oud is, of as nuwe swakhede ontdek word, kan dit wees dat dit nie geblokkeer is nie.

[^5]: Spelers maak verbinding met die bediener deur die Ngrok-proksi-bedieners, en die Ngrok-adres wat by elke herlaaiing uitgereik word, verander.
