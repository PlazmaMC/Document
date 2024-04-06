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

1. **Silný ekosystém doplňků**\
   [Paper](https://github.com/PaperMC/Paper) je založen na,
   což umožňuje většině [nejnovějších doplňků](#user-content-fn-1)[^1] stažených z internetu správně fungovat.
2. **Optimalizace bez nutnosti nastavení**\
   Všechny záplaty od [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) jsou zahrnuty a
   obsahuje některé vlastní optimalizace a módy, které poskytují nejlepší výkon.
3. **Hra přizpůsobená vašim představám**\
   [Purpur](https://github.com/PurpurMC/Purpur) zahrnutý v Plazma umožňuje upravit
   celkové vlastnosti hry podle vašich představ.
4. **Bezpečný herní server**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) obsahuje možnost deaktivace [systému nahlášení chatu](#user-content-fn-3)[^3] od [Mojangu](#user-content-fn-2)[^2], který byl přidán od verze 1.19,\
   což umožňuje hrát na serveru bez sledování a bez úplného odstranění sběrače diagnostických informací.
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

- **Platforma, která správně zpracovává složité pluginy**\
  Na serveru vývojáře [IPECTER](https://github.com/IPECTER) je používán Plazma.\
  I přes komplexní vlastní pluginy fungující pomocí NMS a reflexe, a velké množství datových balíčků,\
  je schopna obsluhovat více než 100 hráčů bez výrazného poklesu výkonu.
- **Platforma udržující rychlý výkon i na RPG serverech**\
  Na jednom clusteru bylo udržováno stabilní prostředí pro 100 hráčů bez poklesu TPS a na 4 clusterech bylo možné pohodlně hrát až 250 hráčů.
- **Platforma, která zlepšuje výkon v oblasti chunků a entit**\
  Přechodem ze serverové platformy Purpur na Plazma došlo k výraznému snížení zpoždění při zpracování chunků a entit na serveru survival.
- **Platforma vybraná mnoha streamery**\
  Je používána jako hlavní nástroj pro streamování mnoha streamery a jejich diváky.

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
