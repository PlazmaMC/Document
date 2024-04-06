---
description: Zistite viac o oprávneniach aplikácie Plazma.
---

# 🛡️ Oprávnenia

Oprávnenie je jednoduchý bezpečnostný nástroj na nastavenie rozsahu interakcie hráčov na serveri.

Na správne využívanie oprávnení a jednoduchú úpravu je potrebné použiť pluginy ako [LuckPerms](https://luckperms.net).

***

## Porozumenie základnému systému oprávnení <a href="#id-1" id="id-1"></a>

V Minecrafte sú k dispozícii základné správcovské skupiny oprávnení.

Je možné nastaviť oprávnenia pre [administrátorov](#user-content-fn-1)[^1] a príkazové bloky a upraviť ich v [nastaveniach servera](configurations/property.md).

0. **Hráč**\
   Je to skupina oprávnení, ktorá je bežne pridelená každému hráčovi.
1. **Mediátor**\
   Môže ignorovať ochranu spawnu.
2. **Správca sveta**\
   Môže používať všetky príkazy a príkazové bloky súvisiace so správou sveta.\
   Je to základná skupina oprávnení, ktorá sa automaticky aplikuje na datapacky a príkazové bloky.
3. **Administrátor**\
   Môže používať všetky príkazy súvisiace s riadením hráčov.
4. **Hlavný administrátor**\
   Môže používať všetky príkazy vrátane správy servera.\
   Je to základná skupina oprávnení, ktorá sa automaticky aplikuje na konzolu a administrátorov.

***

## Nastavenie oprávnení <a href="#id-2" id="id-2"></a>

***

## Celkové oprávnenia <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Predvolené**: `None`

Umožňuje hráčovi sedieť na entite a interagovať s ňou skrčením.

Keď hráč sedí na entite, môže ju ovládať pohybom klávesnice a skákať alebo lietať stlačením skoku.

V `(Namespaced Key)` sa zapisuje [Namespaced ID](#user-content-fn-2)[^2] entity.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `(Entity) > ridable`.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Predvolené**: `None`

Umožňuje hráčovi používať špeciálne schopnosti entity, na ktorej sedí.

Nie všetky entity majú dostupné špeciálne schopnosti. Pre zoznam všetkých dostupných špeciálnych schopností sa pozrite nižšie.

{% hint style="info" %}

**Máte nápady na špeciálne schopnosti?**

Zdieľajte svoje nápady na [Plazma Discord](https://plazmamc.org/discord) alebo [GitHub Diskusie](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Prezrite si aktuálne dostupné špeciálne schopnosti</summary>

- **`crepper`**\
  Pri stlačení klávesu skoku exploduje.\
  Ak hráč má oprávnenie `allow.powered.creeper`, môže držaním klávesu skoku nabíjať výbuch.
- **`dolphin`**\
  Pri stlačení klávesu skoku pláva rýchlejšie.
- **`phantom`**\
  Pri stlačení klávesu skoku vystreľuje plamene.
- **`wither`**\
  Pri interakcii vystreľuje hlavy withera.

</details>

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `(Entity) > ridable`.**

{% endhint %}

#### `bukkit.command.compass`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/compass` príkaz](commands.md#compass).

#### `bukkit.command.credits`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/credits (Hráč)` príkaz](commands.md#credits).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.demo`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/demo (Hráč)` príkaz](commands.md#demo).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.ping`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/ping (Hráč)` príkaz](commands.md#ping).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.ram`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/ram` príkaz](commands.md#ram).

#### `bukkit.command.rambar`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/rambar (Hráč)` príkaz](commands.md#rambar).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.restart`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/restart` príkaz](commands.md#restart).

#### `bukkit.command.tps`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/tps` príkaz](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/tpsbar (Hráč)` príkaz](commands.md#tpsbar).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.timings`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/timings` príkaz](commands.md#timings).

{% hint style="warning" %}

**Tento príkaz bol zastavený.**

Pre podobné príkazy sa pozrite na [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/uptime` príkaz](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/gamemode (GameMode) (Hráč)` príkaz](commands.md#gamemode).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `paper.antixray.bypass`

- **Predvolené**: `None`

Ak je aktívne blokovanie X-Ray, hráči s týmto oprávnením nebudú podliehať zatemneniu blokov X-Ray.

Týmto sa zlepší výkon pre obidve strany.

> Pre informácie o nastavení X-Ray pozrite nižšie uvedenú stránku.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Predvolené**: `None`

{% hint style="warning" %}

Toto oprávnenie sa v 1.20.5 zmení na `plazma.bypass.watchdog`.

{% endhint %}

#### `purpur.anvil.color`

- **Predvolené**: `None`

Umožňuje používať [farebné kódy](https://minecraft.wiki/w/Formatting_codes#Color_codes) na kovadle.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `anvil > allow-colors`.**

{% endhint %}

#### `purpur.anvil.format`

- **Predvolené**: `None`

Umožňuje používať [štýlovacie kódy](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na kovadle.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `anvil > allow-colors`.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Predvolené**: `None`

Umožňuje používať [MiniMessage značky](https://docs.advntr.dev/minimessage/format.html) na kovadle.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `anvil > allow-minimessages`.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Predvolené**: `None`

Umožňuje deaktivovať `kurzívu` textu pomocou štýlovacieho kódu `&r` na kovadle.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `anvil > allow-colors`.**

{% endhint %}

#### `purpur.book.color.sign`

- **Predvolené**: `None`

Umožňuje aplikovať [farebné kódy](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) pri podpise knihy hráča.

#### `purpur.bypassIdleKick`

- **Predvolené**: `None`

Vylučuje hráčov z vypnutia pri nečinnosti.

#### `purpur.debug.f3n`

- **Predvolené**: `Správca sveta`

Umožňuje hráčovi zmeniť herný režim klávesami `F3 + N`.

Funguje len ak má príslušné oprávnenie pre daný herný režim.

#### `purpur.drop.spawners`

- **Predvolené**: `None`

Pri ťažení bloku spawnu s nastaveným predmetom ho hráč vyhadzuje.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `gameplay-mechanics > silk-touch`.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Predvolené**: `None`

Mení veľkosť ender bedne.

V `(NumberString)` je možné zadať `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `ender_chest > six-rows` a `ender_chest > use-permissions-for-rows`.**

{% endhint %}

#### `purpur.inventory_totem`

- **Predvolené**: `None`

Umožňuje fungovanie totemu neumierania aj v prípade, že je v inventári.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `totem-of-undying-works-in-inventory`.**

{% endhint %}

#### `purpur.joinFullServer`

- **Predvolené**: `None`

Umožňuje hráčovi ignorovať obmedzenie počtu pripojených používateľov.

#### `purpur.mending_shift_click`

- **Predvolené**: `None`

Umožňuje hráčovi opraviť predmet, ktorý drží, keď `kľakne a interaguje`.

{% hint style="info" %}

\*\*Na aktiváciu je potrebné povoliť `shift-right-click-repairs-mending-points` v **[konfiguráciách Purpur sveta](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.place.spawners`

- **Predvolené**: `None`

Umožňuje hráčovi inštalovať spawnery.

{% hint style="info" %}

**Funguje len ak je v [nastaveniach Purpur sveta](configurations/purpur/world.md) aktivované `gameplay-mechanics > silk-touch`.**

{% endhint %}

#### `purpur.portal.instant`

- **Predvolené**: `None`

Umožňuje hráčovi okamžite sa presunúť pri použití Nether portálu.

#### `purpur.sign.color`

- **Predvolené**: `None`

Povoluje používanie [farbového kódu](https://minecraft.wiki/w/Formatting_codes#Color_codes) na tabuliach.

{% hint style="info" %}

**Na [konfiguráciu Purpur sveta](configurations/purpur/world.md) je potrebné povoliť `sign > allow-colors`, aby to fungovalo.**

{% endhint %}

#### `purpur.sign.magic`

- **Predvolené**: `None`

Povoliť použitie kódu znečitateľnosti `(&o)` na značkách.

{% hint style="info" %}

**Na [konfiguráciu Purpur sveta](configurations/purpur/world.md) je potrebné povoliť `sign > allow-colors`, aby to fungovalo.**

{% endhint %}

#### `purpur.sign.style`

- **Predvolené**: `None`

Povoliť použitie [formátovacích kódov `(&o excluded)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na značkách.

{% hint style="info" %}

**Na [konfiguráciu Purpur sveta](configurations/purpur/world.md) je potrebné povoliť `sign > allow-colors`, aby to fungovalo.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Predvolené**: `None`

Povoliť hráčovi zabrániť výbuchu TNT pomocou `interakcie` so špongiou.

{% hint style="info" %}

**V [konfiguráciách sveta Purpur](configurations/purpur/world.md) musí byť `defuse-tnt-change` väčšie ako `0.0`, aby fungovalo.**

{% endhint %}

### Plánované oprávnenia

#### `plazma.bypass.ncr-require`

- **Predvolené**: `None`

Povoliť hráčovi pripojiť sa aj keď nemá nainštalovaný mód [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**V [konfiguráciách sveta Plazma](configurations/plazma/world.md) je potrebné aktivovať `no-chat-reports > require-install`, aby to fungovalo.**

{% endhint %}

***

[^1]: Operátor.

[^2]: Napr.: `ender_dragon`
