---
description: Zjistěte více o oprávněních aplikace Plazma.
---

# 🛡️ Oprávnění

Oprávnění jsou jednoduchým bezpečnostním nástrojem, který určuje rozsah, ve kterém mohou hráči na serveru vzájemně interagovat.

Pro správné využití oprávnění a snadnou úpravu je třeba použít pluginy jako [LuckPerms](https://luckperms.net).

***

## Porozumění základnímu systému oprávnění <a href="#id-1" id="id-1"></a>

V Minecraftu jsou poskytovány základní správcovské skupiny oprávnění.

Můžete nastavit oprávnění pro [administrátory](#user-content-fn-1)[^1] a příkazové bloky, které lze upravit v [vlastnostech serveru](configurations/property.md).

0. **Hráč**\
   Obecná skupina oprávnění, která je obvykle udělena všem hráčům.
1. **Prostředník**\
   Může ignorovat ochranu spawnu.
2. **Správce světa**\
   Může používat všechny příkazy a příkazové bloky související se správou světa.\
   Je to základní skupina oprávnění, která se vztahuje na datové balíčky a příkazové bloky.
3. **Administrátor**\
   Může používat všechny příkazy související s řízením hráčů.
4. **Hlavní správce**\
   Může používat všechny příkazy související se správou serveru.\
   Je to základní skupina oprávnění, která se vztahuje na konzoli a administrátory.

***

## Nastavení oprávnění <a href="#id-2" id="id-2"></a>

***

## Celková oprávnění <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Výchozí**: `None`

Umožňuje hráčům se `skrčit` a interagovat s entitami, aby mohli na ně nastoupit.

Pokud nastoupíte na entitu, můžete pomocí `kláves pro pohyb` ovládat pohyb entity a pomocí `kláves pro skok` skákat nebo létat.

Do `(Namespaced Key)` se zadává [Namespaced ID](#user-content-fn-2)[^2] entity.

{% hint style="info" %}

**V případě aktivace `(Entity) > ridable` v [konfiguracích Purpur světa](configurations/purpur/world.md) funguje pouze.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Výchozí**: `None`

Umožňuje hráči používat speciální schopnosti entity, když na ní jezdí.

Ne všechny entity mají dostupné speciální schopnosti. Pro seznam všech dostupných speciálních schopností se podívejte níže.

{% hint style="info" %}

**Máte nápad na speciální schopnost?**

Své nápady můžete sdílet na [Plazma Discordu](https://plazmamc.org/discord) nebo [GitHub Diskuzích](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Zobrazit všechny dostupné speciální schopnosti</summary>

- **`crepper`**\
  Při stisknutí `klávesy pro skok` exploduje.\
  Pokud hráč má oprávnění `allow.powered.creeper`, může držením `klávesy pro skok` nabít výbuch.
- **`dolphin`**\
  Při stisknutí `klávesy pro skok` se vrhne dopředu.
- **`phantom`**\
  Při stisknutí `klávesy pro skok` vystřelí plameny.
- **`wither`**\
  Při `interakci` vystřelí hlavu s Witherem.

</details>

{% hint style="info" %}

**V případě aktivace `(Entity) > ridable` v [konfiguracích Purpur světa](configurations/purpur/world.md) funguje pouze.**

{% endhint %}

#### `bukkit.command.compass`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/credits (Hráč)`](commands.md#credits).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.demo`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/demo (Hráč)`](commands.md#demo).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.ping`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/ping (Hráč)`](commands.md#ping).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.ram`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/rambar (Hráč)`](commands.md#rambar).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.restart`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/tpsbar (Hráč)`](commands.md#tpsbar).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.timings`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Tento příkaz byl zrušen.**

Pro informace o podobných příkazech se podívejte na [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu `/gamemode (GameMode) (Hráč)`.

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `paper.antixray.bypass`

- **Výchozí**: `None`

Pokud je aktivováno [blokování X-Ray](../expert/xray.md), neprovádí se zamaskování bloků pro hráče s oprávněním.

Tímto způsobem mohou obě strany zažít zlepšení výkonu.

> Pro informace o nastavení X-Ray se podívejte na následující stránku.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Výchozí**: `None`

{% hint style="warning" %}

Toto oprávnění se změní na `plazma.bypass.watchdog` ve verzi 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Výchozí**: `None`

Umožňuje používat [barevné kódy](https://minecraft.wiki/w/Formatting_codes#Color_codes) na kovadlech.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) musí být aktivováno `anvil > allow-colors`, aby fungovalo.**

{% endhint %}

#### `purpur.anvil.format`

- **Výchozí**: `None`

Umožňuje používat [stylizační kódy](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na kovadlech.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) musí být aktivováno `anvil > allow-colors`, aby fungovalo.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Výchozí**: `None`

Umožňuje používat [MiniMessage značky](https://docs.advntr.dev/minimessage/format.html) na kovadlech.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) musí být aktivováno `anvil > allow-minimessages`, aby fungovalo.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Výchozí**: `None`

Umožňuje deaktivovat `kurzivu` pomocí [`&r` stylizačního kódu](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na kovadlech.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) musí být aktivováno `anvil > allow-colors`, aby fungovalo.**

{% endhint %}

#### `purpur.book.color.sign`

- **Výchozí**: `None`

Při podpisu knihy se aplikují [stylizační kódy](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Výchozí**: `None`

Vylučuje hráče z cíle vyhazování za nečinnost.

#### `purpur.debug.f3n`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje hráči změnit herní režim pomocí klávesové zkratky `F3 + N`.

Pokud hráč nemá oprávnění pro tento herní režim, nebude fungovat.

#### `purpur.drop.spawners`

- **Výchozí**: `None`

Při těžbě spawnovacího bloku s nastaveným předmětem se spawnovací blok zahodí.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) musí být aktivováno `gameplay-mechanics > silk-touch`, aby fungovalo.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Výchozí**: `None`

Změní velikost Ender truhly.

Do `(NumberString)` lze zadat `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) musí být aktivováno `ender_chest > six-rows` a `ender_chest > use-permissions-for-rows`, aby fungovalo.**

{% endhint %}

#### `purpur.inventory_totem`

- **Výchozí**: `None`

Umožňuje fungování Totemu nesmrtelnosti i když je v inventáři.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) je třeba aktivovat `totem-of-undying-works-in-inventory`, aby fungovalo.**

{% endhint %}

#### `purpur.joinFullServer`

- **Výchozí**: `None`

Umožňuje hráčům ignorovat omezení na maximální počet připojených hráčů.

#### `purpur.mending_shift_click`

- **Výchozí**: `None`

Umožňuje hráčům opravit položku, kterou drží, když se `skloní a kliknou`.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) je třeba aktivovat `shift-right-click-repairs-mending-points`, aby fungovalo.**

{% endhint %}

#### `purpur.place.spawners`

- **Výchozí**: `None`

Umožňuje hráčům umístit spawnery.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) musí být aktivováno `gameplay-mechanics > silk-touch`, aby fungovalo.**

{% endhint %}

#### `purpur.portal.instant`

- **Výchozí**: `None`

Umožňuje hráčům okamžitě se přemístit, když použijí Nether portál.

#### `purpur.sign.color`

- **Výchozí**: `None`

Umožňuje používat [barevné kódy](https://minecraft.wiki/w/Formatting_codes#Color_codes) na cedulích.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) je třeba aktivovat `sign > allow-colors`, aby fungovalo.**

{% endhint %}

#### `purpur.sign.magic`

- **Výchozí**: `None`

Umožňuje používat kouzelné kódy `(&o)` na cedulích.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) je třeba aktivovat `sign > allow-colors`, aby fungovalo.**

{% endhint %}

#### `purpur.sign.style`

- **Výchozí**: `None`

Umožňuje používat [stylové kódy `(&o vyloučeno)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na cedulích.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) je třeba aktivovat `sign > allow-colors`, aby fungovalo.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Výchozí**: `None`

Umožňuje hráčům zabránit výbuchu TNT interakcí s ním pomocí nůžek.

{% hint style="info" %}

**V [konfiguracích Purpur světa](configurations/purpur/world.md) je třeba mít `defuse-tnt-change` nastaveno na `0.0` nebo vyšší, aby fungovalo.**

{% endhint %}

### Plánovaná oprávnění

#### `plazma.bypass.ncr-require`

- **Výchozí**: `None`

Umožňuje hráčům připojit se i bez nainstalovaného módu [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**V [konfiguracích Plazma světa](configurations/plazma/world.md) je třeba aktivovat `no-chat-reports > require-install`, aby fungovalo.**

{% endhint %}

***

[^1]: Operátor.

[^2]: Např.: `ender_dragon`
