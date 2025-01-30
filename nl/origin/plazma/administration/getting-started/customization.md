---
description: Leer hoe je de server kunt aanpassen aan de gebruiker.
---

# 🎨 Gebruiksaanpassing

De reden om aangepaste serverplatforms zoals Plazma te gebruiken in plaats van de officiële serverplatforms van Mojang Studios is dat het zeer **aanpasbaar** is.

Hier zijn verschillende manieren om Plazma aan te passen en te gebruiken.

## Configuratieaanpassingen <a href="#id-1" id="id-1"></a>

De meest fundamentele manier om Plazma aan te passen is door de configuratie aan te passen.

Plazma biedt krachtige configuratie-instellingen, van game-mechanismen tot eigenschappen van mobs.

Raadpleeg de onderstaande pagina voor uitleg over de configuratie van Plazma.

{% content-ref url="../reference/configurations/" %}
[configuraties](../reference/configurations/)
{% endcontent-ref %}

## Gebruik van plug-ins <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma ondersteunt alle op papier gebaseerde plug-ins.**

Voor Spigot-plug-ins kan het zijn dat sommige vanaf 1.20.5 vanwege de mappingveranderingen van Paper niet goed werken,
Maar de meeste plug-ins die zijn gebaseerd op Paper, Pufferfish en Purpur werken allemaal op Plazma,
Als een plug-in niet goed werkt, meld dit dan onmiddellijk als een fout van Plazma [hier.](../diagnosis/plugins.md)

{% endhint %}

Dit is de belangrijkste reden om Plazma te gebruiken en de krachtigste manier om Plazma aan te passen.
Het sterke plug-in ecosysteem van Plazma maakt het gemakkelijk om de server aan te passen.

Er zijn verschillende manieren om plug-ins te vinden en te downloaden. Sommige plug-ins worden geüpload naar openbare opslagservices, terwijl andere plug-ins worden geüpload naar GitHub of hun eigen websites.

{% hint style="caution" %}

**Plug-ins kunnen direct toegang krijgen tot het systeem!**

Controleer altijd of een plug-in veilig is voordat je deze toepast met behulp van services zoals VirusTotal,
Of download plug-ins van betrouwbare services.

{% endhint %}

Er zijn verschillende services beschikbaar om plug-ins te downloaden. Onder andere [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) bieden services waar plug-ins worden beoordeeld voordat ze worden geüpload, zodat alleen veilige plug-ins worden verspreid.

### Plug-ins toepassen <a href="#id-2.1" id="id-2.1"></a>

Als je een plug-in hebt gedownload, is het nu tijd om de plug-in toe te passen.

1. Plug-ins zijn beschikbaar als `.jar` of `Java Executable File`.\
   Sommige plug-ins zijn gecomprimeerd en moeten worden uitgepakt. In dat geval
   Als er een bestand met `bukkit`, `spigot` of `paper` in de naam zit en
   er is een bestand met `fat`, gebruik dan het `fat`-bestand.
2. Plaats het gedownloade bestand in de `plugins`-map van de server en start de server opnieuw op.
3. Wanneer Plazma start, zal er nieuwe inhoud op de console verschijnen.
   Dit betekent dat Plazma de plug-in succesvol heeft geladen.
4. Zelfs als Plazma de plug-in succesvol heeft geladen, kan het zijn dat de plug-in niet start.
   Met het commando `/plugins` kun je de momenteel geladen plug-ins op de server zien.
   Als de naam van de geïnstalleerde plug-in niet in <mark style="background-color:red;">rood</mark> maar in <mark style="background-color:green;">groen</mark> wordt weergegeven, is de plug-in succesvol geladen.

Als de plug-in niet succesvol is geladen, kun je op de volgende pagina oplossingen vinden voor het probleem.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Gebruik van datapacks <a href="#id-3" id="id-3"></a>

Datapacks zijn een manier om Minecraft aan te passen, vergelijkbaar met [Resource Packs](#user-content-fn-1).

Met datapacks kun je nieuwe entiteiten en uitdagingen toevoegen aan het spel en delen van het spel aanpassen.

{% hint style="caution" %}

**Datapacks kunnen werelden beschadigen!**

Sommige defecte datapacks kunnen werelden beschadigen en dit is onomkeerbaar.

Daarom wordt aanbevolen om een back-up te maken van de wereld voordat je datapacks toepast.

{% endhint %}

Datapacks zijn beschikbaar op verschillende services zoals [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) en andere services.

Als je een datapack hebt gedownload, kun je deze toepassen door deze in de `datapacks`-map van de server te plaatsen.
Maak de map aan als deze niet bestaat.

{% hint style="warning" %}

**Sommige [datapacks](#user-content-fn-2) werken mogelijk niet correct bij de eerste toepassing.**

In dat geval wordt aanbevolen de server **2 keer** opnieuw op te starten.

{% endhint %}

Datapacks kunnen gemakkelijk beschadigd raken bij elke update van Minecraft.

Vooral als een datapack ernstig beschadigd is, kan dit leiden tot servercrashes,
Daarom is het belangrijk om de server grondig te testen voordat je deze update.

{% hint style="info" %}

**Voeg `safeMode` toe achter het startcommando van de server om alle datapacks uit te schakelen voordat je de server start.**

Zie `Referentie > Argumenten en Eigenschappen` voor meer informatie.](../reference/arguments.md)

{% endhint %}

Je kunt de toegepaste datapacks controleren met het commando `/datapack list`.

***

[^1]: Of in Minecraft: Bedrock Edition met add-ons.

[^2]: Toevoeging van entiteiten en meer.
