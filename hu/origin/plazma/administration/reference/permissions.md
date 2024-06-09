---
description: Ismerje meg a Plazma engedélyeit.
---

# 🛡️ Engedély

Jogosultság egy egyszerű biztonsági eszköz, amely beállítja a szerveren belüli játékosok közötti interakció lehetőségeit.

A jogosultságok megfelelő kihasználásához és könnyű módosításához használni kell a [LuckPerms](https://luckperms.net) vagy hasonló bővítményeket.

***

## Alap jogosultság rendszer megértése <a href="#id-1" id="id-1"></a>

A Minecraft alapvető adminisztrációs jogosultság csoportokat biztosít.

[Adminisztrátor](#user-content-fn-1)[^1] és parancsblokk jogosultságokat állíthat be, módosíthatja a [szerver tulajdonságokat](configurations/property.md).

0. **Játékos**\
   Általában minden játékosnak rendelkezésére álló jogosultság csoport.
1. **Mediátor**\
   Figyelmen kívül hagyhatja a spawn védelmet.
2. **Világkezelő**\
   Minden világkezeléshez kapcsolódó parancsokat és parancsblokkokat használhat.\
   Ez az alapértelmezett jogosultság csoport a datapackokhoz és parancsblokkokhoz.
3. **Adminisztrátor**\
   Minden játékossal kapcsolatos parancsokat használhat.
4. **Főadminisztrátor**\
   Minden szerverkezeléshez kapcsolódó parancsot használhat.\
   Ez az alapértelmezett jogosultság csoport a konzolhoz és az adminisztrátorokhoz.

***

## Jogosultságok beállítása <a href="#id-2" id="id-2"></a>

***

## Összes jogosultság <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Alapértelmezett**: `None`

Engedélyezi a játékosoknak, hogy lehajolva és interakcióval felszálljanak az entitásra.

Ha felszáll az entitásra, akkor a `mozgás billentyűkkel` irányíthatja az entitás mozgását, és a `ugrás billentyűvel` ugorhat vagy repülhet.

A `(Namespaced Key)` helyére az entitás [Namespaced ID](#user-content-fn-2)[^2] kerül.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha az `(Entity) > ridable` engedélyezve van.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Alapértelmezett**: `None`

Engedélyezi a játékosoknak, hogy az entitáson ülve használhassák az entitás speciális képességeit.

Nem minden entitás speciális képessége használható. Az összes elérhető speciális képességet az alábbiakban találja.

{% hint style="info" %}

Van ötlete speciális képességekre?

Kérjük, ossza meg az ötleteit a [Plazma Discord](https://plazmamc.org/discord) vagy a [GitHub Beszélgetések](https://github.com/PlazmaMC/PlazmaBukkit/discussions) oldalon!

{% endhint %}

<details>

<összefoglalás>Elérhető speciális képességek megtekintése<!--összefoglalás-->

- **`crepper`**\
  Ha megnyomja az `ugrás gombot`, akkor felrobban.\
  Ha a játékos rendelkezik az `allow.powered.creeper` jogosultsággal, akkor tartsa lenyomva az `ugrás gombot` a töltéshez.
- **`dolphin`**\
  Ha megnyomja az `ugrás gombot`, akkor úszik.
- **`phantom`**\
  Ha megnyomja az `ugrás gombot`, akkor tüzet lövöldöz.
- **`wither`**\
  Ha `kölcsönhatásba lép`, akkor wither fejet lő ki.

</details>

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha az `(Entity) > ridable` engedélyezve van.**

{% endhint %}

#### `bukkit.command.compass`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/compass` parancs](commands.md#compass) használatát.

#### `bukkit.command.credits`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/credits (Játékos)` parancs](commands.md#credits) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.demo`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/demo (Játékos)` parancs](commands.md#demo) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.ping`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/ping (Játékos)` parancs](commands.md#ping) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.ram`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/ram` parancs](commands.md#ram) használatát.

#### `bukkit.command.rambar`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/rambar (Játékos)` parancs](commands.md#rambar) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.restart`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/restart` parancs](commands.md#restart) használatát.

#### `bukkit.command.tps`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/tps` parancs](commands.md#tps) használatát.

#### `bukkit.command.tpsbar`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/tpsbar (Játékos)` parancs](commands.md#tpsbar) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.timings`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/timings` parancs](commands.md#timings) használatát.

{% hint style="warning" %}

**Ez a parancs használata megszűnt.**

További hasonló parancsokért látogasson el a [Spark](https://spark.lucko.me/docs/Command-Usage) oldalra.

{% endhint %}

#### `bukkit.command.uptime`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/uptime` parancs](commands.md#uptime) használatát.

#### `minecraft.command.gamemode.(GameMode)`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/gamemode (GameMode) (Játékos)` parancs](commands.md#gamemode) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `paper.antixray.bypass`

- **Alapértelmezett**: `None`

Ha az [X-Ray blokkolás](../expert/xray.md) aktív, akkor a jogosultsággal rendelkező játékosoknak nem végzi el az X-Ray blokkok elhomályosítását.

Ezzel mindkét fél javulást tapasztalhat.

> Az X-Ray beállításokról további információért látogasson el az alábbi oldalra.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Alapértelmezett**: `None`

{% hint style="warning" %}

Ez a jogosultság a 1.20.5 verzióban `plazma.bypass.watchdog` -ra fog változni.

{% endhint %}

#### `purpur.anvil.color`

- **Alapértelmezett**: `None`

Lehetővé teszi a kovácsoló asztalon a [színkódok](https://minecraft.wiki/w/Formatting_codes#Color_codes) használatát.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha az `anvil > allow-colors` engedélyezve van.**

{% endhint %}

#### `purpur.anvil.format`

- **Alapértelmezett**: `None`

Lehetővé teszi a kovácsoló asztalon a [stílus kódok](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) használatát.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha az `anvil > allow-colors` engedélyezve van.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Alapértelmezett**: `None`

Lehetővé teszi a kovácsoló asztalon a [MiniMessage címkék](https://docs.advntr.dev/minimessage/format.html) használatát.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha az `anvil > allow-minimessages` engedélyezve van.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Alapértelmezett**: `None`

Lehetővé teszi a kovácsoló asztalon a [`&r` stílus kód](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) segítségével az `igazított szöveg` eltávolítását.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha az `anvil > allow-colors` engedélyezve van.**

{% endhint %}

#### `purpur.book.color.sign`

- **Alapértelmezett**: `None`

Ha a játékos aláírja a könyvet, akkor alkalmazza a [stílus kódokat](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Alapértelmezett**: `None`

Kizárja a játékost az inaktív állapotból történő kirúgásból.

#### `purpur.debug.f3n`

- **Alapértelmezett**: `Világkezelő`

Lehetővé teszi a játékos számára, hogy az `F3 + N` billentyűkombinációval változtassa a játék módot.

Csak akkor működik, ha nincs jogosultsága a megfelelő játékmódhoz.

#### `purpur.drop.spawners`

- **Alapértelmezett**: `None`

Ha az előre beállított tárggyal bányászik spawner blokkot, akkor a spawner blokkot elejti.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha a `gameplay-mechanics > silk-touch` engedélyezve van.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Alapértelmezett**: `None`

Megváltoztatja az ender láda méretét.

A `(NumberString)` helyére `one`, `two`, `three`, `four`, `five`, `six` írható.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha az `ender_chest > six-rows` és `ender_chest > use-permissions-for-rows` engedélyezve van.**

{% endhint %}

#### `purpur.inventory_totem`

- **Alapértelmezett**: `None`

Lehetővé teszi a visszatérő totem működését az inventáriumban.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha a `totem-of-undying-works-in-inventory` engedélyezve van.**

{% endhint %}

#### `purpur.joinFullServer`

- **Alapértelmezett**: `None`

A játékosnak engedélyezve van, hogy figyelmen kívül hagyja a csatlakozók számának korlátozását.

#### `purpur.mending_shift_click`

- **Alapértelmezett**: `None`

A játékosnak lehetősége van az `együttműködés lehajlására`, hogy megjavítsa a kezében lévő tárgyat.

{% hint style="info" %}

**A [Purpur világbeállítások](configurations/purpur/world.md)ban aktiválni kell a `shift-right-click-repairs-mending-points`-ot, hogy működjön.**

{% endhint %}

#### `purpur.place.spawners`

- **Alapértelmezett**: `None`

A játékosnak engedélyezve van a mobgenerálók telepítése.

{% hint style="info" %}

**[Purpur világbeállítások](configurations/purpur/world.md) esetén csak akkor működik, ha a `gameplay-mechanics > silk-touch` engedélyezve van.**

{% endhint %}

#### `purpur.portal.instant`

- **Alapértelmezett**: `None`

A játékosnak lehetősége van azonnal átugrani, amikor használja a Nether portált.

#### `purpur.sign.color`

- **Alapértelmezett**: `None`

표지판에 [színkódokat](https://minecraft.wiki/w/Formatting_codes#Color_codes) használhat.

{% hint style="info" %}

\*\*A **[Purpur világbeállításokban](configurations/purpur/world.md) aktiválnod kell a `sign > allow-colors`-ot, hogy működjön.**

{% endhint %}

#### `purpur.sign.magic`

- **Alapértelmezett**: `None`

표지판에 난독화 kód`(&o)` használatát engedélyezi.

{% hint style="info" %}

\*\*A **[Purpur világbeállításokban](configurations/purpur/world.md) aktiválnod kell a `sign > allow-colors`-ot, hogy működjön.**

{% endhint %}

#### `purpur.jel.stílus`

- **Alapértelmezett**: `None`

Táblákon [stílus kódok használata `(&o kivéve)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) engedélyezve.

{% hint style="info" %}

\*\*A **[Purpur világbeállításokban](configurations/purpur/world.md) aktiválnod kell a `sign > allow-colors`-ot, hogy működjön.**

{% endhint %}

#### `purpur.tnt.hatástalanít`

- **Alapértelmezett**: `None`

A játékosok `kölcsönhatás` használatával megakadályozhatják a TNT robbanását.

{% hint style="info" %}

**[Purpur világ konfiguráció](configurations/purpur/world.md) `hatástalanítás-tnt-változás` értéke legalább `0.0` kell legyen a működéshez.**

{% endhint %}

### Biztosított jog

#### `plazma.mellőzés.ncr-szükség`

- **Alapértelmezett**: `None`

A játékosoknak lehetőségük van a [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) módot telepítetlenül is csatlakozni.

{% hint style="info" %}

**[Plazma világ konfiguráció](configurations/plazma/world.md) `nincs-csevegés-jelentések > telepítés-szükséges` aktiválása szükséges a működéshez.**

{% endhint %}

***

[^1]: Operátor.

[^2]: Például: `ender_dragon`
