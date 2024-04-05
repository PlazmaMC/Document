---
description: Zistite viac o platforme Plazma.
---

# ❓ Čo je Plazma?

- **Plazma** je serverová platforma založená na [Paper](https://github.com/PaperMC/Paper), ktorá získava výhody z [Andromeda](https://github.com/EarendelArchived/Andromeda) a [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Snažíme sa vždy poskytovať vysokú stabilitu a výkonnosť, rýchle aktualizácie a bohaté funkcie.

## 📋 Ciele Plazmy <a href="#id-1" id="id-1"></a>

- Snažíme sa o rýchle aktualizácie a vytvorenie serverovej platformy s vysokou stabilitou.
- Snažíme sa poskytnúť bohaté funkcie a výkonnosť, ktorá sa nezaostáva za platformou pre módy.
- Snažíme sa vytvoriť voľnú platformu, ktorá umožňuje prispôsobiť aj patche pre vanilla.

## ⚙️ Kľúčové vlastnosti <a href="#id-2" id="id-2"></a>

1. **Silná ekosystém pluginov**\
   Založené na [Paper](https://github.com/PaperMC/Paper), takmer všetky [aktuálne pluginy](#user-content-fn-1)[^1] dostupné na internete fungujú správne.
2. **Optimalizácia bez potreby nastavenia**\
   Všetky záplaty od [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sú zahrnuté a obsahujú vlastné optimalizácie a módy, čo zabezpečuje najvyššiu úroveň výkonu.
3. **Hra prispôsobená podľa vašich predstáv**\
   [Purpur](https://github.com/PurpurMC/Purpur) zahrnutý v Plazme umožňuje upraviť celkové vlastnosti hry.
4. **Bezpečné hranie na serveri**\
   Súčasťou je [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports), ktorý umožňuje deaktivovať systém [Mojang](#user-content-fn-3)[^3] pre hlásenie chatu od verzie 1.19 a odstrániť zhromažďovač diagnostických informácií, čo umožňuje hrať na serveri bez sledovania.
5. **Najrýchlejšie aktualizácie**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) zabezpečuje, že záplaty v Plazme sú vždy aktuálne, čo z nej robí platformu s najrýchlejšími aktualizáciami medzi serverovými platformami založenými na Paper.
6. **Optimalizované základné konfiguračné súbory**\
   Prednastavené konfiguračné súbory sú optimalizované, takže nie je potrebné ich ďalej upravovať.
7. **Systémové vlákna fungujúce systematicky**\
   Asynchrónne spracovanie systémových mechanizmov mimo herné mechanizmy pomáha optimalizovať server tým, že znižuje [čas oneskorenia](#user-content-fn-4)[^4].
8. **Blokovanie zbytočného použitia pamäte**\
   Združenie dát s podobnými hodnotami do jedného záznamu znižuje spotrebu pamäte.

#### Chcete sa dozvedieť viac o Plazme? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Príklady využitia <a href="#id-3" id="id-3"></a>

- **Platforma, ktorá správne spracúva aj zložité pluginy**\
  Plazma je používaná na serveri vývojára [IPECTER](https://github.com/IPECTER), kde sú implementované vlastné pluginy fungujúce na NMS a reflexii, ako aj veľké množstvo dátových balíčkov. Aj napriek vysokému objemu komplexných a rozsiahlych dátových balíčkov a využitiu NMS a reflexie, je schopná bez problémov obslúžiť viac ako 100 hráčov bez poklesu výkonu.
- **Platforma s rýchlym výkonom aj na RPG serveroch**\
  Na jednom klastri dokázala udržať 100 hráčov bez poklesu TPS a na 4 klastroch mohlo hrať pohodlne celkovo 250 hráčov.
- **Platforma, kde sa svieti vo chvíli, keď sa spracúvajú chunky/entít**\
  Pre server prežitia, kde dochádzalo k oneskoreniu pri spracovaní chunkov a entít, bolo možné znížiť väčšinu oneskorení zmenou z Purpur na Plazmu.
- **Platforma, ktorú si vybrali mnohí streameri**\
  Je používaná mnohými streamermi na svojich serveroch pre divákov.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Živý trend používateľov Plazmy</p></figcaption>
</figure>

## ⬇️ Stiahnuť

Na nasledujúcej stránke si môžete stiahnuť Plazmu.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Chcete vedieť viac o podporovaných verziách?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Pluginy pre Bukkit, CraftBukkit, Spigot a záplaty pre Paper, Pufferfish, Purpur.

[^2]: Pod Microsoft Corporation.

[^3]: Ak deaktivujete systém na hlásenie chatu, chat bude spracovávaný iba na serveri a zabránite sledovaniu chatu od Mojangu.

[^4]: Čas, počas ktorého systémový mechanizmus funguje a hra je pozastavená.
