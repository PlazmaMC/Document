---
description: Ontdek wat Plazma voor een serverplatform is.
---

# ❓ Wat is Plazma?

- **Plazma** is een serverplatform gebaseerd op [Paper](https://github.com/PaperMC/Paper) dat alleen de voordelen van [Andromeda](https://github.com/EarendelArchived/Andromeda) en [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) overneemt.
- We streven altijd naar hoge stabiliteit, krachtige prestaties, snelle updates en uitgebreide functionaliteit.

## 📋 Doelstellingen van Plazma <a href="#id-1" id="id-1"></a>

- We streven ernaar een serverplatform te zijn met snelle updates en hoge stabiliteit.
- We streven ernaar om uitgebreide functionaliteit en krachtige prestaties te bieden die niet onderdoen voor modplatforms.
- We streven ernaar een vrij platform te creëren waarop ook vanilla patches kunnen worden aangepast.

## ⚙️ Belangrijkste kenmerken <a href="#id-2" id="id-2"></a>

1. **Krachtig ecosysteem van plug-ins**\
   [Paper](https://github.com/PaperMC/Paper) als basis, waardoor de meeste [nieuwste plug-ins](#user-content-fn-1)[^1] die beschikbaar zijn op internet normaal werken.
2. **Geen instellingen nodig voor optimalisatie**\
   Alle patches van [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) zijn inbegrepen, met enkele interne optimalisaties en modi voor optimale prestaties.
3. **Pas het spel aan naar wens**\
   [Purpur](https://github.com/PurpurMC/Purpur) inbegrepen in Plazma stelt u in staat om de algehele eigenschappen van het spel aan te passen.
4. **Speel veilig op de server**\
   Met [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) kunt u het [chatrapportagesysteem](#user-content-fn-3)[^3] van [Mojang](#user-content-fn-2)[^2] dat is toegevoegd vanaf 1.19 uitschakelen, en de diagnosegegevensverzamelaar volledig verwijderen om op een traceervrije veilige server te spelen.
5. **Snelste updates**\
   Met [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) blijven de patches van Plazma altijd up-to-date, waardoor het het snelste updateproces biedt onder de op Paper gebaseerde serverplatforms.
6. **Geoptimaliseerde standaard configuratiebestanden**\
   De standaard toegepaste configuratiebestanden zijn geoptimaliseerd, zodat u ze niet zelf hoeft te optimaliseren.
7. **Efficiënt werkende multithreading**\
   Door systeemmechanismen die niet gerelateerd zijn aan het spelmechanisme asynchroon te maken, wordt de server geoptimaliseerd om de vertraging te verminderen.
8. **Voorkomen van onnodig geheugengebruik**\
   Door vergelijkbare waarden samen te voegen, wordt de geheugenconsumptie verminderd.

#### Meer weten over Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Gebruiksscenario's <a href="#id-3" id="id-3"></a>

- **Platform dat zelfs complexe plug-ins correct verwerkt**\
  Plazma wordt gebruikt op de server van ontwikkelaar [IPECTER](https://github.com/IPECTER). Ondanks de zelf ontwikkelde plug-ins die werken met NMS en reflectie, en het grote aantal uitgebreide datapacks, kan het meer dan 100 spelers ontvangen zonder prestatieverlies.
- **Platform dat snelle prestaties behoudt, zelfs op een RPG-server**\
  Op een enkel cluster konden 100 spelers stabiel blijven zonder TPS-verlaging, en op 4 clusters konden in totaal 250 spelers comfortabel spelen.
- **Platform dat licht werpt op chunks/entities**\
  Door over te schakelen van Purpur naar Plazma voor de server van een overlevingsserver waar vertragingen optraden bij het verwerken van chunks en entities, kon het merendeel van de vertragingen worden verminderd.
- **Platform gekozen door veel streamers**\
  Het wordt gebruikt als de emmer voor kijkers van veel streamers.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Real-time Plazma gebruikers trend</p></figcaption>
</figure>

## ⬇️ Download

U kunt Plazma downloaden vanaf de onderstaande pagina.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Meer informatie over ondersteunde versies?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot plug-ins en Paper, Pufferfish, Purpur plug-ins.

[^2]: Door Microsoft Corporation.

[^3]: Door het uitschakelen van het chatsysteem wordt de chat volledig op de server verwerkt en wordt het chattrackingmechanisme van Mojang geblokkeerd.

[^4]: Tijd die nodig is voor het systeemmechanisme om te werken, waarbij het spel tijdelijk wordt onderbroken.
