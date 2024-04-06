---
description: Få informasjon om tillatelsene til Plazma.
---

# 🛡️ Tillatelser

Tillatelse er et enkelt sikkerhetsverktøy som setter omfanget av samhandling mellom spillere på serveren.

For å bruke tillatelser skikkelig og enkelt endre dem, må du bruke tillegg som [LuckPerms](https://luckperms.net).

***

## Forstå grunnleggende tillatelsessystem <a href="#id-1" id="id-1"></a>

Minecraft tilbyr grunnleggende administrasjonsgrupper for tillatelser.

Du kan sette tillatelser for [administratorer](#user-content-fn-1)[^1] og kommandoblokker, og endre dem i [serverinnstillinger](configurations/property.md).

0. **Spiller**\
   En grunnleggende tillatelsesgruppe som vanligvis gis til alle spillere.
1. **Moderator**\
   Kan ignorere spawnbeskyttelse.
2. **Verdensadministrator**\
   Kan bruke alle kommandoer og kommandoblokker relatert til verdensadministrasjon.\
   En grunnleggende tillatelsesgruppe som brukes som standard for datapakker og kommandoblokker.
3. **Administrator**\
   Kan bruke alle kommandoer relatert til spilleradministrasjon.
4. **Hovedadministrator**\
   Kan bruke alle kommandoer, inkludert serveradministrasjon.\
   En grunnleggende tillatelsesgruppe som brukes som standard for konsollen og administratorer.

***

## Sette tillatelser <a href="#id-2" id="id-2"></a>

***

## Fullstendige tillatelser <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Standard**: `Ingen`

Tillater at spillere kan `bøye seg ned og samhandle` med enheter for å ri dem.

Når du rir enheten, kan du bruke `bevegelsesknapper` til å styre enhetens bevegelse og bruke `hoppetasten` for å hoppe eller fly.

`(Namespaced Key)` er den [Namespaced ID](#user-content-fn-2)[^2] til enheten.

{% hint style="info" %}

**Fungerer bare hvis `(Entity) > ridable` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standard**: `Ingen`

Tillater at spillere kan bruke enhetens spesialferdigheter mens de rir enheten.

Ikke alle enheters spesialferdigheter er tilgjengelige. Se nedenfor for en liste over tilgjengelige spesialferdigheter.

{% hint style="info" %}

Har du gode ideer til spesialferdigheter?

Legg ut ideene dine på [Plazma Discord](https://plazmamc.org/discord) eller [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Se tilgjengelige spesialferdigheter nå</summary>

- **`crepper`**\
  Når du trykker på `hoppetasten`, eksploderer den.\
  Hvis spilleren har tillatelsen `allow.powered.creeper`, kan du holde nede `hoppetasten` for å lade den opp.
- **`dolphin`**\
  Når du trykker på `hoppetasten`, sprinter den.
- **`phantom`**\
  Når du trykker på `hoppetasten`, skyter den ut flammer.
- **`wither`**\
  Når du `samhandler` med den, skyter den ut wither-hoder.

</details>

{% hint style="info" %}

**Fungerer bare hvis `(Entity) > ridable` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/compass` kommandoen](commands.md#compass).

#### `bukkit.command.credits`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/credits (Spiller)` kommandoen](commands.md#credits).

Legger til `.other` bak tillatelsesnavnet for å tillate andre spillere å bruke det.

#### `bukkit.command.demo`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/demo (Spiller)` kommandoen](commands.md#demo).

Legger til `.other` bak tillatelsesnavnet for å tillate andre spillere å bruke det.

#### `bukkit.command.ping`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/ping (Spiller)` kommandoen](commands.md#ping).

Legger til `.other` bak tillatelsesnavnet for å tillate andre spillere å bruke det.

#### `bukkit.command.ram`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/ram` kommandoen](commands.md#ram).

#### `bukkit.command.rambar`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/rambar (Spiller)` kommandoen](commands.md#rambar).

Legger til `.other` bak tillatelsesnavnet for å tillate andre spillere å bruke det.

#### `bukkit.command.restart`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/restart` kommandoen](commands.md#restart).

#### `bukkit.command.tps`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/tps` kommandoen](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/tpsbar (Spiller)` kommandoen](commands.md#tpsbar).

Legger til `.other` bak tillatelsesnavnet for å tillate andre spillere å bruke det.

#### `bukkit.command.timings`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/timings` kommandoen](commands.md#timings).

{% hint style="warning" %}

**Denne kommandoen er ikke lenger tilgjengelig.**

Se [Spark](https://spark.lucko.me/docs/Command-Usage) for lignende funksjoner.

{% endhint %}

#### `bukkit.command.uptime`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/uptime` kommandoen](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Standard**: `Verdensadministrator`

Tillater bruk av [`/gamemode (GameMode) (Spiller)` kommandoen](commands.md#gamemode).

Legger til `.other` bak tillatelsesnavnet for å tillate andre spillere å bruke det.

#### `paper.antixray.bypass`

- **Standard**: `Ingen`

Når [X-Ray blokkering](../expert/xray.md) er aktivert, vil spillere med tillatelsen ikke bli påvirket av blokkering av X-Ray blokker.

Dette gir fordeler for begge parter i form av ytelsesforbedringer.

> Se siden nedenfor for informasjon om hvordan du konfigurerer X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standard**: `Ingen`

{% hint style="warning" %}

Denne tillatelsen vil bli endret til `plazma.bypass.watchdog` i versjon 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Standard**: `Ingen`

Tillater bruk av [fargekoder](https://minecraft.wiki/w/Formatting_codes#Color_codes) på ambolter.

{% hint style="info" %}

**Fungerer bare hvis `anvil > allow-colors` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Standard**: `Ingen`

Tillater bruk av [stilingskoder](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) på ambolter.

{% hint style="info" %}

**Fungerer bare hvis `anvil > allow-colors` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Standard**: `Ingen`

Tillater bruk av [MiniMessage tags](https://docs.advntr.dev/minimessage/format.html) på ambolter.

{% hint style="info" %}

**Fungerer bare hvis `anvil > allow-minimessages` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standard**: `Ingen`

Tillater deaktivering av `kursiv` med [`&r` stilingskode](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) på ambolter.

{% hint style="info" %}

**Fungerer bare hvis `anvil > allow-colors` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Standard**: `Ingen`

Gjør det mulig for spillere å bruke [stilingskoder](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) når de signerer bøker.

#### `purpur.bypassIdleKick`

- **Standard**: `Ingen`

Ekskluderer spillere fra å bli kastet ut for inaktivitet.

#### `purpur.debug.f3n`

- **Standard**: `Verdensadministrator`

Tillater spillere å endre spillmodus ved å bruke tastekombinasjonen `F3 + N`.

Fungerer bare hvis spilleren har tillatelse for den aktuelle spillmodusen.

#### `purpur.drop.spawners`

- **Standard**: `Ingen`

Hvis aktivert i konfigurasjonen, vil gruving av spawnerblokker med de angitte elementene slippe spawnerblokken.

{% hint style="info" %}

**Fungerer bare hvis `gameplay-mechanics > silk-touch` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standard**: `Ingen`

Endrer størrelsen på enderbrystet.

Mulige verdier for `(NumberString)` er `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Fungerer bare hvis `ender_chest > six-rows` og `ender_chest > use-permissions-for-rows` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Standard**: `Ingen`

Tillater at totem av udødelighet fungerer selv om den er i inventaret.

{% hint style="info" %}

**Fungerer bare hvis `totem-of-undying-works-in-inventory` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Standard**: `Ingen`

Spilleren tillates å ignorere begrensningen for antall tilkoblede brukere.

#### `purpur.mending_shift_click`

- **Standard**: `Ingen`

Spilleren tillates å reparere det holdte elementet ved å `snu seg ned og samhandle`.

{% hint style="info" %}

**[Purpur verdenskonfigurasjoner](configurations/purpur/world.md) må aktiveres for `shift-right-click-repairs-mending-points` for å fungere.**

{% endhint %}

#### `purpur.place.spawners`

- **Standard**: `Ingen`

Spilleren tillates å installere spawner.

{% hint style="info" %}

**Fungerer bare hvis `gameplay-mechanics > silk-touch` er aktivert i [Purpur verdenskonfigurasjonen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Standard**: `Ingen`

Spilleren tillates å teleportere umiddelbart når de bruker Nether portal.

#### `purpur.sign.color`

- **Standard**: `Ingen`

Tillater bruk av [fargekoder](https://minecraft.wiki/w/Formatting_codes#Color_codes) på skilt.

{% hint style="info" %}

\*\*For at det skal fungere, må `sign > allow-colors` være aktivert i **[Purpur-verdenskonfigurasjoner](configurations/purpur/world.md)**.

{% endhint %}

#### `purpur.sign.magic`

- **Standard**: `Ingen`

Tillat bruk av obfuskasjonskoden `(&o)` på skilt.

{% hint style="info" %}

\*\*For at det skal fungere, må `sign > allow-colors` være aktivert i **[Purpur-verdenskonfigurasjoner](configurations/purpur/world.md)**.

{% endhint %}

#### `purpur.skilt.stil`

- **Standard**: `Ingen`

Tillat bruk av [formateringskoder `(&o ekskludert)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) på skilt.

{% hint style="info" %}

\*\*For at det skal fungere, må `sign > allow-colors` være aktivert i **[Purpur-verdenskonfigurasjoner](configurations/purpur/world.md)**.

{% endhint %}

#### `purpur.tnt.desarmere`

- **Standard**: `Ingen`

Tillat spillere å forhindre TNT-eksplosjoner ved å `samhandle` med saks.

{% hint style="info" %}

**[Purpur verdenskonfigurasjon](konfigurasjoner/purpur/world.md) må ha `defuse-tnt-change` på `0.0` eller høyere for at dette skal fungere.**

{% endhint %}

### Forventede tillatelser

#### `plazma.omgå.ncr-krav`

- **Standard**: `Ingen`

Tillat spillere å koble til selv om de ikke har installert modulen [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**[Plazma verdenskonfigurasjon](konfigurasjoner/plazma/world.md) må ha aktivert `no-chat-reports > require-install` for at dette skal fungere.**

{% endhint %}

***

[^1]: Operatør.

[^2]: Eksempel: `ender_dragon`
