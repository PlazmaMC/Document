---
description: Sužinokite apie Plazma teises.
---

# 🛡️ Teisės

Leidimai yra paprastas saugumo įrankis, nustatantis serverio žaidėjų sąveikos galimybės.

Norint tinkamai naudoti leidimus ir lengvai juos keisti, reikia naudoti įskiepius, pvz., [LuckPerms](https://luckperms.net).

***

## Suprasti pagrindinę leidimų sistemą <a href="#id-1" id="id-1"></a>

Minecraft teikia pagrindinius valdymo leidimų grupes.

[Administratorius](#user-content-fn-1)[^1] gali nustatyti operatorių ir komandų blokų leidimus, kuriuos galima keisti [serverio nustatymuose](configurations/property.md).

0. **Žaidėjas**\
   Paprastai tai yra priskiriamas visiems žaidėjams leidimų grupė.
1. **Tarpininkas**\
   Gali ignoruoti spawno apsaugą.
2. **Pasaulio valdytojas**\
   Gali naudoti visas komandas ir komandų blokus, susijusius su pasaulio valdymu.\
   Tai yra numatytasis leidimų grupė, taikomas duomenų paketams ir komandų blokams.
3. **Administratorius**\
   Gali naudoti visas komandas, susijusias su žaidėjų valdymu.
4. **Visagalis**\
   Gali naudoti visas komandas, įskaitant serverio valdymą.\
   Tai yra numatytasis leidimų grupė, taikomas konsolėje ir administratoriams.

***

## Leidimų nustatymas <a href="#id-2" id="id-2"></a>

***

## Visiški leidimai <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Numatytasis**: `None`

Leidžia žaidėjams šliaužti prie entiteto ir jį apeiti.

Kai sėdite ant entiteto, galite valdyti jo judėjimą naudodami `judėjimo klavišus` ir šokinėti arba skristi naudodami `šuolio klavišą`.

Į `(Namespaced Key)` įveskite entiteto [Namespaced ID](#user-content-fn-2)[^2].

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `(Entity) > ridable`.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Numatytasis**: `None`

Leidžia žaidėjams naudoti entiteto specialias funkcijas, kai jie sėdi ant jo.

Ne visiems entitetams yra leidžiama naudoti specialias funkcijas. Pilną specialių funkcijų sąrašą rasite žemiau.

{% hint style="info" %}

**Turite idėjų dėl specialių funkcijų?**

Paskelbkite savo idėjas [Plazma Discord](https://plazmamc.org/discord) arba [GitHub diskusijose](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Žiūrėti dabartines specialias funkcijas</summary>

- **`crepper`**\
  Paspaudus `šuolio klavišą`, jis sprogs.\
  Jei žaidėjas turi `allow.powered.creeper` leidimą, jis gali ilgai laikyti `šuolio klavišą`, kad įkrautų.
- **`dolphin`**\
  Paspaudus `šuolio klavišą`, jis puola.
- **`phantom`**\
  Paspaudus `šuolio klavišą`, jis išspjaudys ugnį.
- **`wither`**\
  Jei su juo sąveikaujate, jis iššaudys wither galvą.

</details>

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `(Entity) > ridable`.**

{% endhint %}

#### `bukkit.command.compass`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/compass` komandą](commands.md#compass).

#### `bukkit.command.credits`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/credits (Žaidėjas)` komandą](commands.md#credits).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.demo`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/demo (Žaidėjas)` komandą](commands.md#demo).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.ping`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/ping (Žaidėjas)` komandą](commands.md#ping).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.ram`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/ram` komandą](commands.md#ram).

#### `bukkit.command.rambar`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/rambar (Žaidėjas)` komandą](commands.md#rambar).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.restart`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/restart` komandą](commands.md#restart).

#### `bukkit.command.tps`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/tps` komandą](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/tpsbar (Žaidėjas)` komandą](commands.md#tpsbar).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.timings`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/timings` komandą](commands.md#timings).

{% hint style="įspėjimas" %}

**Ši komanda nebeveikia.**

Norėdami sužinoti apie panašias funkcijas, apsilankykite [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/uptime` komandą](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/gamemode (GameMode) (Žaidėjas)` komandą](commands.md#gamemode).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `paper.antixray.bypass`

- **Numatytasis**: `None`

Kai yra įjungtas [X-Ray blokavimas](../expert/xray.md), leidžia registruotiems žaidėjams naudoti X-Ray blokų aptemimo funkciją.

Tai leidžia abiem pusėms patirti našumo pagerėjimą.

> Norėdami sužinoti daugiau apie X-Ray nustatymus, apsilankykite žemiau pateiktame puslapyje.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Numatytasis**: `None`

{% hint style="įspėjimas" %}

Šis leidimas 1.20.5 versijoje bus pakeistas į `plazma.bypass.watchdog`.

{% endhint %}

#### `purpur.anvil.color`

- **Numatytasis**: `None`

Leidžia naudoti kalbos [spalvų kodavimą](https://minecraft.wiki/w/Formatting_codes#Color_codes) kalvėje.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `anvil > allow-colors`.**

{% endhint %}

#### `purpur.anvil.format`

- **Numatytasis**: `None`

Leidžia naudoti [stiliaus kodavimą](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) kalvėje.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `anvil > allow-colors`.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Numatytasis**: `None`

Leidžia naudoti [MiniMessage žymes](https://docs.advntr.dev/minimessage/format.html) kalvėje.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `anvil > allow-minimessages`.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Numatytasis**: `None`

Leidžia išjungti `kursyvinį tekstą` kalvėje naudojant [`&r` stiliaus kodą](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `anvil > allow-colors`.**

{% endhint %}

#### `purpur.book.color.sign`

- **Numatytasis**: `None`

Kai žaidėjas pasirašo knygą, taikomi [stiliaus kodai](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Numatytasis**: `None`

Išskiria žaidėją iš neaktyvių išmetimo sąrašo.

#### `purpur.debug.f3n`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia žaidėjui naudoti `F3 + N` klavišus keisti žaidimo režimą.

Veiks tik turint atitinkamą žaidimo režimo leidimą.

#### `purpur.drop.spawners`

- **Numatytasis**: `None`

Iškasant bloką, nustatytą konfigūracijoje, sukuria spawnerį.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `gameplay-mechanics > silk-touch`.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Numatytasis**: `None`

Keičia enderlado dydį.

Į `(NumberString)` galima įvesti `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `ender_chest > six-rows` ir `ender_chest > use-permissions-for-rows`.**

{% endhint %}

#### `purpur.inventory_totem`

- **Numatytasis**: `None`

Leidžia totemui veikti, net jei jis yra inventoriuje.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `totem-of-undying-works-in-inventory`.**

{% endhint %}

#### `purpur.joinFullServer`

- **Numatytasis**: `None`

Leidžia žaidėjui ignoruoti prisijungusių vartotojų limitą.

#### `purpur.mending_shift_click`

- **Numatytasis**: `None`

Leidžia žaidėjui remontuoti laikomą daiktą, kai jis `pasilenkia ir sąveikauja`.

{% hint style="info" %}

**Norint, kad tai veiktų, Purpur konfigūracijos faile (configurations/purpur/world.md) būtų įjungtas `shift-right-click-repairs-mending-points`.**

{% endhint %}

#### `purpur.place.spawners`

- **Numatytasis**: `None`

Leidžia žaidėjui įdiegti spawnerius.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) ši funkcija veikia tik tada, kai yra įjungta `gameplay-mechanics > silk-touch`.**

{% endhint %}

#### `purpur.portal.instant`

- **Numatytasis**: `None`

Leidžia žaidėjui iškart teleportuotis, kai jis naudoja Nether portalą.

#### `purpur.sign.color`

- **Numatytasis**: `None`

Leidžiama naudoti [spalvų kodą](https://minecraft.wiki/w/Formatting_codes#Color_codes) ženkleliuose.

{% hint style="info" %}

**Norint, kad veiktų, Purpur pasaulio konfigūracijoje [`sign > allow-colors`](configurations/purpur/world.md) turi būti įjungtas.**

{% endhint %}

#### `purpur.sign.magic`

- **Numatytasis**: `None`

Leidžiama naudoti kodavimo simbolį `(&o)` ant ženklelio.

{% hint style="info" %}

**Norint, kad veiktų, Purpur pasaulio konfigūracijoje [`sign > allow-colors`](configurations/purpur/world.md) turi būti įjungtas.**

{% endhint %}

#### `purpur.sign.style`

- **Numatytasis**: `None`

Leidžiama naudoti [stiliavimo kodą `(&o išskyrus)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) ant ženklelio.

{% hint style="info" %}

**Norint, kad veiktų, Purpur pasaulio konfigūracijoje [`sign > allow-colors`](configurations/purpur/world.md) turi būti įjungtas.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Numatytasis**: `None`

Leidžiama žaidėjui su švyturėliu `sąveikauti` ir išvengti TNT sprogimo.

{% hint style="info" %}

**[Purpur pasaulio konfigūracijoje](configurations/purpur/world.md) `defuse-tnt-change` turi būti ne mažesnis nei `0.0`, kad veiktų.**

{% endhint %}

### Suteikiamos numatomosios teisės

#### `plazma.bypass.ncr-require`

- **Numatytasis**: `None`

Leidžiama žaidėjui prisijungti neturint įdiegto [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) modifikacijos.

{% hint style="info" %}

**[Plazma pasaulio konfigūracijoje](configurations/plazma/world.md) reikia įjungti `no-chat-reports > require-install`, kad veiktų.**

{% endhint %}

***

[^1]: Operatorius.

[^2]: Pavyzdys: `ender_dragon`
