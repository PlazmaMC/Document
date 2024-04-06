---
description: Få mere at vide om tilladelserne til Plazma.
---

# 🛡️ Tilladelser

Rettigheder er et simpelt sikkerhedsværktøj på serveren, der definerer omfanget af interaktion mellem spillere.

For at udnytte rettigheder korrekt og let kunne redigere dem, skal du bruge plugins som [LuckPerms](https://luckperms.net).

***

## Forståelse af grundlæggende rettighedssystem <a href="#id-1" id="id-1"></a>

Minecraft tilbyder grundlæggende administrative rettighedsgrupper.

Du kan konfigurere rettigheder for [administratorer](#user-content-fn-1)[^1] og kommandoblokke, og de kan ændres i [serveregenskaber](configurations/property.md).

0. **Spillere**\
   Er en standard rettighedsgruppe tildelt alle spillere.
1. **Mæglere**\
   Kan ignorere spawnbeskyttelse.
2. **Verdensadministratorer**\
   Kan bruge alle kommandoer og kommandoblokke relateret til verdensstyring.\
   Er en standard rettighedsgruppe for datapakker og kommandoblokke.
3. **Administratorer**\
   Kan bruge alle kommandoer relateret til spillerstyring.
4. **Superadministratorer**\
   Kan bruge alle kommandoer, inklusive serveradministration.\
   Er en standard rettighedsgruppe for konsollen og administratorer.

***

## Opsætning af rettigheder <a href="#id-2" id="id-2"></a>

***

## Fulde rettigheder <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Standard**: `Ingen`

Tillader spillere at 'sne' og interagere med enheder for at ride dem.

Når du rider enheden, kan du bruge 'bevægelsesknapperne' til at styre enhedens bevægelse og 'hoppeknappen' til at hoppe eller flyve.

I '(Namespaced Key)' indsættes enhedens [Namespaced ID](#user-content-fn-2)[^2].

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** har aktiveret `(Entity) > ridable`, fungerer det kun.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standard**: `Ingen`

Tillader spilleren at bruge en entitets specielle evner, mens de rider på entiteten.

Ikke alle entiteters specielle evner er tilgængelige. Se nedenfor for en liste over alle tilgængelige specielle evner.

{% hint style="info" %}

**Har du en god idé til en speciel evne?**

Post dine ideer på [Plazma Discord](https://plazmamc.org/discord) eller [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Se alle tilgængelige specielle evner</summary>

- **`crepper`**\
  Når du trykker på `hoppeknappen`, eksploderer den.\
  Hvis spilleren har tilladelsen `allow.powered.creeper`, kan du holde `hoppeknappen` nede for at oplade den.
- **`dolphin`**\
  Når du trykker på `hoppeknappen`, sprinter den.
- **`phantom`**\
  Når du trykker på `hoppeknappen`, skyder den ild.
- **`wither`**\
  Ved `interaktion` affyrer den wither-hovedet.

</details>

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** har aktiveret `(Entity) > ridable`, fungerer det kun.**

{% endhint %}

#### `bukkit.command.compass`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/compass` kommandoen](commands.md#compass).

#### `bukkit.command.credits`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/credits (Spiller)` kommandoen](commands.md#credits).

Hvis du indtaster `.other` efter tilladelsesnavnet, tillader det brugen til andre spillere.

#### `bukkit.command.demo`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/demo (Spiller)` kommandoen](commands.md#demo).

Hvis du indtaster `.other` efter tilladelsesnavnet, tillader det brugen til andre spillere.

#### `bukkit.command.ping`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/ping (Spiller)` kommandoen](commands.md#ping).

Hvis du indtaster `.other` efter tilladelsesnavnet, tillader det brugen til andre spillere.

#### `bukkit.command.ram`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/ram` kommandoen](commands.md#ram).

#### `bukkit.command.rambar`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/rambar (Spiller)` kommandoen](commands.md#rambar).

Hvis du indtaster `.other` efter tilladelsesnavnet, tillader det brugen til andre spillere.

#### `bukkit.command.restart`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/restart` kommandoen](commands.md#restart).

#### `bukkit.command.tps`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/tps` kommandoen](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/tpsbar (Spiller)` kommandoen](commands.md#tpsbar).

Hvis du indtaster `.other` efter tilladelsesnavnet, tillader det brugen til andre spillere.

#### `bukkit.command.timings`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/timings` kommandoen](commands.md#timings).

{% hint style="warning" %}

**Denne kommando er blevet afbrudt.**

Tjek [Spark](https://spark.lucko.me/docs/Command-Usage) for lignende funktioner.

{% endhint %}

#### `bukkit.command.uptime`

- **Standard givet**: `Verdensadministrator`

Tillader brug af [`/uptime` kommandoen](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Standard givet**: `Verdensadministrator`

Tillader brug af `/gamemode (GameMode) (Spiller)` kommandoen.

Hvis du indtaster `.other` efter tilladelsesnavnet, tillader det brugen til andre spillere.

#### `paper.antixray.bypass`

- **Standard**: `Ingen`

Hvis [X-Ray blokering](../expert/xray.md) er aktiveret,
vil tilladte spillere ikke gennemføre X-Ray blokeringsblokering på dem.

Dette giver forbedret ydeevne for begge parter.

> Se nedenstående side for at lære om X-Ray-indstillinger.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standard**: `Ingen`

{% hint style="warning" %}

Denne tilladelse vil blive ændret til `plazma.bypass.watchdog` i 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Standard**: `Ingen`

Tillader brug af farvekoder på ambolten med [farvekoder](https://minecraft.wiki/w/Formatting_codes#Color_codes).

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** skal `anvil > allow-colors` være aktiveret for at det virker.**

{% endhint %}

#### `purpur.anvil.format`

- **Standard**: `Ingen`

Tillader brug af formateringskoder på ambolten med [formateringskoder](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** skal `anvil > allow-colors` være aktiveret for at det virker.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Standard**: `Ingen`

Tillader brug af MiniMessage-tags på ambolten med [MiniMessage-tags](https://docs.advntr.dev/minimessage/format.html).

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** skal `anvil > allow-minimessages` være aktiveret for at det virker.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standard**: `Ingen`

Tillader deaktivering af `kursiv` med [`&r` formateringskode](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) på ambolten.

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** skal `anvil > allow-colors` være aktiveret for at det virker.**

{% endhint %}

#### `purpur.book.color.sign`

- **Standard**: `Ingen`

Anvend formateringskoder, når en spiller signerer en bog med farve.

#### `purpur.bypassIdleKick`

- **Standard**: `Ingen`

Ekskluderer spilleren fra at blive sparket for inaktivitet.

#### `purpur.debug.f3n`

- **Standard givet**: `Verdensadministrator`

Tillader spilleren at skifte spiltilstand ved at trykke på `F3 + N`-tasterne.

Det virker ikke, hvis spilleren ikke har tilladelse til den pågældende spiltilstand.

#### `purpur.drop.spawners`

- **Standard**: `Ingen`

Hvis du bryder en spawnerblok med den konfigurerede genstand, vil spawnerblokken falde ned.

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** skal `gameplay-mechanics > silk-touch` være aktiveret for at det virker.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standard**: `Ingen`

Ændrer størrelsen på en enderbryst.

Du kan indtaste `one`, `two`, `three`, `four`, `five`, `six` i `(NumberString)`.

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** skal `ender_chest > six-rows` og `ender_chest > use-permissions-for-rows` være aktiveret for at det virker.**

{% endhint %}

#### `purpur.inventory_totem`

- **Standard**: `Ingen`

Tillader, at totem af udødelighed fungerer, selvom det er i inventaret.

{% hint style="info" %}

**For at det fungerer, skal du aktivere `totem-of-undying-works-in-inventory` i [Purpur verdenskonfigurationer](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Standard**: `Ingen`

Tillad spilleren at ignorere serverens fulde kapacitet.

#### `purpur.mending_shift_click`

- **Standard**: `Ingen`

Tillad spilleren at reparere genstande ved at `trykke skifte og højreklikke` mens de er bøjet.

{% hint style="info" %}

**For at det fungerer, skal du aktivere `shift-right-click-repairs-mending-points` i [Purpur verdenskonfigurationer](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.place.spawners`

- **Standard**: `Ingen`

Tillad spilleren at placere spawner.

{% hint style="info" %}

**I **[Purpur World Configuration](configurations/purpur/world.md)** skal `gameplay-mechanics > silk-touch` være aktiveret for at det virker.**

{% endhint %}

#### `purpur.portal.instant`

- **Standard**: `Ingen`

Lad spilleren øjeblikkeligt teleportere, når de bruger Nether portalen.

#### `purpur.sign.color`

- **Standard**: `Ingen`

Tillad brug af [farvekoder](https://minecraft.wiki/w/Formatting_codes#Color_codes) på skilte.

{% hint style="info" %}

**For at det fungerer, skal du aktivere `sign > allow-colors` i [Purpur verdenskonfigurationer](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.magic`

- **Standard**: `Ingen`

Tillad brug af forvrængningskode `(&o)` på skilte.

{% hint style="info" %}

**For at det fungerer, skal du aktivere `sign > allow-colors` i [Purpur verdenskonfigurationer](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.style`

- **Standard**: `Ingen`

Tillad brug af [formateringskoder `(&o undtaget)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) på skilte.

{% hint style="info" %}

**For at det fungerer, skal du aktivere `sign > allow-colors` i [Purpur verdenskonfigurationer](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.tnt.defuse`

- **Standard**: `Ingen`

Tillad spilleren at forhindre TNT-eksplosion ved at `interagere` med saks.

{% hint style="info" %}

**For at det fungerer, skal `defuse-tnt-change` i [Purpur verdenskonfigurationer](configurations/purpur/world.md) være `0.0` eller højere.**

{% endhint %}

### Planlagte tilladelser

#### `plazma.bypass.ncr-require`

- **Standard**: `Ingen`

Tillad spilleren at deltage uden at have [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod installeret.

{% hint style="info" %}

**For at det fungerer, skal du aktivere `no-chat-reports > require-install` i [Plazma verdenskonfigurationer](configurations/plazma/world.md).**

{% endhint %}

***

[^1]: Operatør.

[^2]: F.eks.: `ender_dragon`
