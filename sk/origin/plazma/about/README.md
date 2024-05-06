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

1. **Silný ekosystém zásuvných modulov**\
   [Paper](https://github.com/PaperMC/Paper) je založený na,
   takmer všetky [najnovšie zásuvné moduly](#user-content-fn-1)[^1] dostupné na internete správne fungujú.
2. **Optimalizácia bez potreby nastavenia**\
   Všetky opravy [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sú zahrnuté a
   poskytuje vlastné optimalizácie a módy pre najlepší výkon.
3. **Hra prispôsobiteľná podľa vašich predstáv**\
   [Purpur](https://github.com/PurpurMC/Purpur) zahrnutý v Plazme umožňuje upravovať
   celkové vlastnosti hry podľa vašich predstáv.
4. **Bezpečné hranie na serveri**\
   Obsahuje [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) až od verzie 1.19
   kde je možné deaktivovať [systém hlásenia chatu](#user-content-fn-3)[^3] od [Mojangu](#user-content-fn-2)[^2],\
   zbierač diagnostických informácií je úplne odstránený, takže môžete hrať na serveri bez sledovania.
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

- **Platforma správne spracujúca aj zložité zásuvné moduly**\
  Plazma je používaná na serveroch vývojára [IPECTER](https://github.com/IPECTER).\
  Má vlastné zásuvné moduly fungujúce cez NMS a reflexiu, s veľkým množstvom veľkých dátových balíkov,\
  ajak pre viac ako 100 hráčov bez poklesu výkonu.
- **Platforma udržiavajúca rýchly výkon aj na RPG serveroch**\
  Na jednom zhluku udržala 100 hráčov bez poklesu TPS a na 4 zhlukoch mohlo 250 hráčov hrať plynulo.
- **Platforma, ktorá ukazuje svetlo vo fragmentoch a entitách**\
  Zmena platformy z Purpuru na Plazmu pre prevádzku servera prežitia, kde došlo k zníženiu väčšiny meškaní pri spracovaní fragmentov a entít.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Real-time Plazma user trend">
</a>

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
