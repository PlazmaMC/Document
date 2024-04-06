---
description: Uurige Plazma õigusi.
---

# 🛡️ Õigused

Õigused on lihtne turvavahend, mis määrab serveri mängijate vahelise suhtluse ulatuse.

Õiguste korralikuks kasutamiseks ja lihtsaks muutmiseks tuleks kasutada pistikprogramme nagu [LuckPerms](https://luckperms.net).

***

## Mõistke vaikimisi õiguste süsteemi <a href="#id-1" id="id-1"></a>

Minecraftis on vaikimisi haldusõiguste gruppe.

Saate määrata õigused [administraatorile](#user-content-fn-1)[^1] ja käsu plokkidele ning neid muuta [serveri atribuutides](configurations/property.md).

0. **Mängija**\
   Tavaline õiguste grupp, mis antakse tavaliselt kõigile mängijatele.
1. **Vahendaja**\
   Võib ignoreerida spawnpunktide kaitset.
2. **Maailma administraator**\
   Saab kasutada kõiki maailma haldamise ja sellega seotud käsklusi ning käsu plokke.\
   See on vaikimisi rakendatav õiguste grupp andmepakettidele ja käsu plokkidele.
3. **Administraator**\
   Saab kasutada kõiki mängijate haldamise ja sellega seotud käsklusi.
4. **Peakasutaja**\
   Saab kasutada kõiki serveri haldamise ja sellega seotud käsklusi.\
   See on vaikimisi rakendatav õiguste grupp konsoolile ja administraatoritele.

***

## Määrake õigused <a href="#id-2" id="id-2"></a>

***

## Kogu õigus <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Vaikimisi**: `Puudub`

Lubab mängijal kummarduda ja suhelda üksustega, et neile peale istuda.

Üksust peale istudes saate kasutada `liikumisklahve` selle liigutamiseks ja hüppamiseks või lendamiseks `hüppeklahviga`.

`(Namespaced Key)` tähistab üksuse [Namespaced ID](#user-content-fn-2)[^2].

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `(Entity) > ridable` on lubatud.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Vaikimisi**: `Puudub`

Lubab mängijal kasutada üksuse erilisi võimeid, kui ta sõidab üksusel.

Kõikide üksuste erivõimed ei pruugi olla saadaval. Vaadake kõikide saadaolevate erivõimete kohta allpool.

{% hint style="info" %}

**Kas teil on hea idee erivõimete kohta?**

Avaldage oma ideed [Plazma Discordis](https://plazmamc.org/discord) või [GitHubi aruteludes](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Vaadake praegu saadaolevaid erivõimeid</summary>

- **`creeper`**\
  Vajutades `hüppeklahvi` plahvatab.\
  Kui mängijal on lubatud `allow.powered.creeper` õigus, saab ta plahvatuse laadimiseks hoida `hüppeklahvi` all.
- **`delfiin`**\
  Vajutades `hüppeklahvi` teeb hüppe edasi.
- **`phantom`**\
  Vajutades `hüppeklahvi` tulistab tulekahju.
- **`wither`**\
  `Suhtlemisel` tulistab wither pea.

</details>

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `(Entity) > ridable` on lubatud.**

{% endhint %}

#### `bukkit.command.compass`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/compass` käsku](commands.md#compass).

#### `bukkit.command.credits`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/credits (Mängija)` käsku](commands.md#credits).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.demo`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/demo (Mängija)` käsku](commands.md#demo).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.ping`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/ping (Mängija)` käsku](commands.md#ping).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.ram`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/ram` käsku](commands.md#ram).

#### `bukkit.command.rambar`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/rambar (Mängija)` käsku](commands.md#rambar).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.restart`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/restart` käsku](commands.md#restart).

#### `bukkit.command.tps`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/tps` käsku](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/tpsbar (Mängija)` käsku](commands.md#tpsbar).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.timings`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/timings` käsku](commands.md#timings).

{% hint style="warning" %}

**See käsk on lõpetatud.**

Vaadake sarnaseid käsklusi [Sparki](https://spark.lucko.me/docs/Command-Usage) lehelt.

{% endhint %}

#### `bukkit.command.uptime`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/uptime` käsku](commands.md#uptime).

#### `minecraft.command.gamemode.(Mängurežiim)`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/gamemode (Mängurežiim) (Mängija)` käsku.

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `paper.antixray.bypass`

- **Vaikimisi**: `Puudub`

Kui [X-Ray blokeerimine](../expert/xray.md) on aktiveeritud, ei rakenda see blokeerimiseks mõeldud plokknähtamatust õigustega mängijatele.

See võimaldab mõlemal poolel paremat jõudlust kogeda.

> X-Ray seadistamiseks vaadake allpool olevat lehekülge.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Vaikimisi**: `Puudub`

{% hint style="warning" %}

See õigus muudetakse 1.20.5 versioonis ümber `plazma.bypass.watchdog`-iks.

{% endhint %}

#### `purpur.anvil.color`

- **Vaikimisi**: `Puudub`

Võimaldab kasutada sepikutel [värvikoode](https://minecraft.wiki/w/Formatting_codes#Color_codes).

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `anvil > allow-colors` on lubatud.**

{% endhint %}

#### `purpur.anvil.format`

- **Vaikimisi**: `Puudub`

Võimaldab kasutada sepikutel [stiilikoode](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `anvil > allow-colors` on lubatud.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Vaikimisi**: `Puudub`

Võimaldab kasutada sepikutel [MiniMessage sildid](https://docs.advntr.dev/minimessage/format.html).

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `anvil > allow-minimessages` on lubatud.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Vaikimisi**: `Puudub`

Võimaldab sepikutel [`&r` stiilikoode](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) keelata `kaldkirjas`.

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `anvil > allow-colors` on lubatud.**

{% endhint %}

#### `purpur.book.color.sign`

- **Vaikimisi**: `Puudub`

Kui mängija allkirjastab raamatu, rakendatakse [stiilikoode](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Vaikimisi**: `Puudub`

Võimaldab mängijal jääda passiivse väljaviskamise sihtrühmast välja.

#### `purpur.debug.f3n`

- **Vaikimisi**: `Maailma administraator`

Võimaldab mängijal kasutada mängurežiimi muutmiseks klahvikombinatsiooni `F3 + N`.

See ei tööta, kui puudub vastav mängurežiimi õigus.

#### `purpur.drop.spawners`

- **Vaikimisi**: `Puudub`

Kui kaevate konfigureeritud esemega spawneriploki, siis see kukub maha.

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `gameplay-mechanics > silk-touch` on lubatud.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Vaikimisi**: `Puudub`

Muudab Enderi kirstu suurust.

`(NumberString)` võib olla `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `ender_chest > six-rows` ja `ender_chest > use-permissions-for-rows` on lubatud.**

{% endhint %}

#### `purpur.inventory_totem`

- **Vaikimisi**: `Puudub`

Võimaldab toimida surematu käsna inventaris.

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `totem-of-undying-works-in-inventory` on lubatud.**

{% endhint %}

#### `purpur.joinFullServer`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse ignoreerida ühenduse piirangut.

#### `purpur.mending_shift_click`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse eseme remontimise võimaldamiseks `kummargil olles koostööd teha`.

{% hint style="info" %}

**[Purpuri maailma konfiguratsioonides](configurations/purpur/world.md) tuleb `shift-right-click-repairs-mending-points` aktiveerida, et see toimiks.**

{% endhint %}

#### `purpur.place.spawners`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse paigaldada spawnereid.

{% hint style="info" %}

**[Purpur maailma seadistustes](configurations/purpur/world.md) töötab see ainult siis, kui `gameplay-mechanics > silk-touch` on lubatud.**

{% endhint %}

#### `purpur.portal.instant`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse kohe pärast Netheri portaali kasutamist kohe teleporteeruda.

#### `purpur.sign.color`

- **Vaikimisi**: `Puudub`

Luba kasutada [värvikoode](https://minecraft.wiki/w/Formatting_codes#Color_codes) märkidel.

{% hint style="info" %}

\*\*`sign > allow-colors` tuleb aktiveerida **[Purpur maailma seadistustes](configurations/purpur/world.md), et see toimiks.**

{% endhint %}

#### `purpur.sign.magic`

- **Vaikimisi**: `Puudub`

Luba kasutada märkide kodeerimist `(&o)` märkidele.

{% hint style="info" %}

\*\*`sign > allow-colors` tuleb aktiveerida **[Purpur maailma seadistustes](configurations/purpur/world.md), et see toimiks.**

{% endhint %}

#### `purpur.sign.style`

- **Vaikimisi**: `Puudub`

Luba kasutada [stiilimärkide kodeerimist `(&o välja arvatud)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) märkidele.

{% hint style="info" %}

\*\*`sign > allow-colors` tuleb aktiveerida **[Purpur maailma seadistustes](configurations/purpur/world.md), et see toimiks.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Vaikimisi**: `Puudub`

Luba mängijal takistada TNT plahvatust `vastastikuse tegevusega` kääride abil.

{% hint style="info" %}

**[Purpur maailma konfiguratsioonides](configurations/purpur/world.md) peab `defuse-tnt-change` olema vähemalt `0.0`, et see toimiks.**

{% endhint %}

### Antud õigus tuleb.

#### `plazma.bypass.ncr-require`

- **Vaikimisi**: `Puudub`

Luba mängijal ühenduda isegi kui pole paigaldatud [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) moodulit.

{% hint style="info" %}

**[Plazma maailma konfiguratsioonides](configurations/plazma/world.md) tuleb aktiveerida `no-chat-reports > require-install`, et see toimiks.**

{% endhint %}

***

[^1]: Operaator.

[^2]: Näide: `ender_dragon`
