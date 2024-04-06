---
description: Zjistěte, o jakou serverovou platformu se jedná.
---

# ❓ Co je Plazma?

- **Plazma** je serverová platforma založená na [Paper](https://github.com/PaperMC/Paper), která si bere výhody z [Andromeda](https://github.com/EarendelArchived/Andromeda) a [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Snažíme se poskytovat vysokou stabilitu, silný výkon, rychlé aktualizace a bohaté funkce.

## 📋 Cíle Plazmy <a href="#id-1" id="id-1"></a>

- Snažíme se stát serverovou platformou s rychlými aktualizacemi a vysokou stabilitou.
- Snažíme se poskytnout bohaté funkce a silný výkon, který není vůbec horší než u modových platforem.
- Snažíme se vytvořit svobodnou platformu, která umožňuje uživatelské úpravy i pro základní opravy.

## ⚙️ Hlavní rysy <a href="#id-2" id="id-2"></a>

1. **Silný ekosystém pluginů**\
   Díky základu [Paper](https://github.com/PaperMC/Paper) je schopna správně fungovat většina [nejnovějších pluginů](#user-content-fn-1)[^1] dostupných na internetu.
2. **Optimalizace bez potřeby nastavení**\
   Všechny opravy od [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) jsou zahrnuty, a díky vlastní optimalizaci a vestavěným módu poskytuje nejlepší výkon.
3. **Hra podle vašich představ**\
   [Purpur](https://github.com/PurpurMC/Purpur) obsažený v Plazmě vám umožňuje upravit vlastnosti hry.
4. **Bezpečný herní server**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) obsahuje možnost deaktivace [systému nahlášení chatu](#user-content-fn-3)[^3] od [Mojang](#user-content-fn-2)[^2], který byl přidán od verze 1.19, a kompletní odstranění sběrače diagnostických informací, což umožňuje hrát na serveru bez sledování.
5. **Nejrychlejší aktualizace**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) udržuje zahrnuté opravy Plazmy vždy aktuální, což zajišťuje nejrychlejší aktualizace mezi serverovými platformami založenými na Paper.
6. **Optimalizace základních konfiguračních souborů**\
   Výchozí konfigurační soubory jsou optimalizovány, takže nemusíte ručně optimalizovat konfigurační soubory.
7. **Systémové vlákno fungující systematicky**\
   Asynchronizací systémových mechanismů oddělených od herních mechanismů se snižuje [dočasná prodleva](#user-content-fn-4)[^4] a optimalizuje se server.
8. **Blokování nepotřebných prostorů**\
   Spojením podobných hodnot do jedné se snižuje využití paměti.

#### Chcete se o Plazmě dozvědět více? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Příklady využití <a href="#id-3" id="id-3"></a>

- **Platforma, která správně zpracovává i složité pluginy**\
  Plazma je používána na serveru vývojáře [IPECTER](https://github.com/IPECTER). I přes vlastní pluginy fungující pomocí NMS a reflexí, a velké množství datových balíčků, dokáže bez výpadků zvládnout více než 100 hráčů.
- **Platforma udržující rychlý výkon i na RPG serverech**\
  Na jednom clusteru bylo úspěšně udržováno 100 hráčů bez poklesu TPS a na 4 clusterech mohlo hrát celkem 250 hráčů pohodlně.
- **Platforma, která ukazuje světlo v oblasti chunků/entit**\
  Změnou z Purpur na Plazmu bylo možné snížit většinu prodlev při zpracování chunků a entit na serveru survivalu.
- **Platforma, kterou volí mnoho streamerů**\
  Je používána jako náhrada za Bucket pro mnoho populárních streamerů.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Plazma uživatelů v reálném čase Trend</p></figcaption>
</figure>

## ⬇️ Stáhnout

Na následující stránce si můžete stáhnout Plazmu.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Chcete vědět více o podporovaných verzích?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Pluginy pro Bukkit, CraftBukkit, Spigot a Paper, Pufferfish, Purpur.

[^2]: Patří pod společnost Microsoft Corporation.

[^3]: Deaktivací systému hlášení chatu je možné zamezit sledování chatu ze strany Mojangu a zpracování chatu pouze na serveru.

[^4]: Čas, kdy hra na chvíli zastaví svůj běh kvůli fungování systémových mechanismů.
