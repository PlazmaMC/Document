---
description: Zistite, ako prispôsobiť server používateľským preferenciám.
---

# 🎨 Používateľské nastavenie

Dôvodom, prečo používame upravenú serverovú platformu ako Plazma namiesto oficiálnej serverovej platformy poskytovanej spoločnosťou Mojang Studios, je možnosť veľmi silnej **personalizácie**.

Nižšie sú uvedené rôzne spôsoby, ako personalizovať a využívať Plazmu.

## Úprava konfigurácie <a href="#id-1" id="id-1"></a>

Najzákladnejším spôsobom, ako personalizovať Plazmu, je úprava konfigurácie.

Plazma poskytuje silné nastavenia konfigurácie od mechaniky hry po vlastnosti monštrum.

Pre viac informácií o konfiguráciách v Plazme navštívte nasledujúcu stránku.

{% content-ref url="../reference/configurations/" %}
[konfigurácie](../reference/configurations/)
{% endcontent-ref %}

## Použitie pluginov <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma podporuje všetky základné pluginy Paperu.**

V prípade pluginov Spigotu od verzie 1.20.5 sa môžu niektoré pluginy nesprávne správať kvôli zmenám v mapovaní Paperu. Avšak väčšina pluginov založených na Papere ako napríklad Paper, Pufferfish a Purpur by mali fungovať aj v Plazme. Ak by sa niektorý plugin nesprávne správal, ide o chybu v Plazme, preto nahláste [prosím](../diagnosis/plugins.md).

{% endhint %}

Je to hlavný dôvod, prečo používať Plazmu a zároveň najúčinnejší spôsob, ako prispôsobiť Plazmu pre používateľa.
Silný ekosystém pluginov Plazmy umožňuje jednoduchú personalizáciu servera.

Existuje niekoľko spôsobov, ako nájsť a stiahnuť pluginy. Niektoré pluginy sú nahrané na verejných úložiskách, zatiaľ čo iné sú nahrané na GitHub alebo na vlastné stránky.

{% hint style="caution" %}

**Pluginy majú priamy prístup k systému!**

Pred použitím pluginov vždy overte ich bezpečnosť pomocou služieb ako VirusTotal alebo stiahnite pluginy z dôveryhodných zdrojov.

{% endhint %}

Na stiahnutie pluginov je k dispozícii viacero služieb. Medzi ne patria [SpigotMC Fórum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) a ďalšie služby, ktoré pred zverejnením pluginov prechádzajú kontrolou a zabezpečujú, že sa šíria iba bezpečné pluginy.

### Aplikácia pluginov <a href="#id-2.1" id="id-2.1"></a>

Ak ste plugin stiahli, je čas ho aplikovať.

1. Pluginy sú vo formáte `.jar` alebo `Java Executable File`.\
   Niektoré pluginy môžu byť aj v archíve, v takom prípade
   rozbaľte archív a ak názov obsahuje `bukkit`, `spigot` alebo `paper`,
   použite súbor s príponou `fat`.
2. Stiahnutý súbor vložte do priečinka `plugins` vo vašom serverovom priečinku a (re)štartujte server.
3. Po spustení Plazmy sa na konzole zobrazí nový obsah.
   Toto znamená, že Plazma úspešne načítala pluginy.
4. Aj keď Plazma úspešne načíta pluginy, nemusia sa automaticky spustiť.
   Pomocou príkazu `/plugins` môžete zistiť, ktoré pluginy sú načítané na serveri.
   Ak meno nainštalovaného pluginu nie je <mark style="background-color:red;">červené</mark>, ale <mark style="background-color:green;">zelené</mark>, znamená to, že plugin bol úspešne načítaný.

Ak sa plugin nenačíta správne, nájdete riešenia na nasledujúcej stránke.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Použitie Datapackov <a href="#id-3" id="id-3"></a>

Datapacky sú spôsob, ako prispôsobiť Minecraft podobne ako [Resource Packs](#user-content-fn-1).

Pomocou Datapackov môžete pridávať nové skupiny bytostí a výzvy do hry a upravovať časť hry.

{% hint style="caution" %}

**Datapacky môžu poškodiť svet!**

Niektoré chybné datapacky môžu poškodiť svet a toto poškodenie je nezvratné.

Preto sa odporúča zálohovať svet pred aplikáciou Datapackov.

{% endhint %}

Datapacky sú dostupné na viacerých službách ako [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) a ďalšie.

Po stiahnutí Datapacku ho vložte do priečinka `datapacks` vo vašom serverovom priečinku.
Ak priečinok neexistuje, vytvorte ho a pridajte doň Datapack.

{% hint style="warning" %}

**Niektoré [Datapacky](#user-content-fn-2) sa môžu pri prvom použití nenačítať správne.**

V takom prípade sa odporúča server **2-krát** reštartovať.

{% endhint %}

Datapacky môžu byť ľahko poškodené pri aktualizácii verzie Minecraftu.

Najmä ak je Datapack úplne poškodený, môže spôsobiť pád servera, preto je dôležité pred aktualizáciou servera dôkladne testovať.

{% hint style="info" %}

**Po spustení servera s príkazom `safeMode` za serverom môžete vypnúť všetky Datapacky a znova spustiť server.**

[Pre viac informácií pozrite `Referencie > Argumenty`.](../reference/arguments.md)

{% endhint %}

Nainštalované Datapacky môžete overiť príkazom `/datapack list`.

***

[^1]: Alebo pomocou prídavného softvéru pre Minecraft: Bedrock Edition.

[^2]: Pridanie nových skupín bytostí a podobne.
