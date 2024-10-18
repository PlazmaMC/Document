---
description: Ta reda på behörigheterna för Plazma.
---

# 🛡️ Behörighet

Behörigheter är en enkel säkerhetsåtgärd som ställer in omfånget där spelare på servern kan interagera med varandra.

För att använda och enkelt redigera behörigheter bör du använda tillägg som [LuckPerms](https://luckperms.net).

***

## Förstå den grundläggande behörighetsstrukturen <a href="#id-1" id="id-1"></a>

I Minecraft finns det grundläggande administrativa behörighetsgrupper tillgängliga.

Det är möjligt att ställa in behörigheter för [operatörer](#user-content-fn-1)[^1] och kommandoblock samt att redigera dem i [serveregenskaper](configurations/property.md).

0. **Spelare**\
   En behörighetsgrupp som vanligtvis tilldelas alla spelare.
1. **Medlare**\
   Kan ignorera spawnskydd.
2. **Världsadministratör**\
   Har åtkomst till alla kommandon och kommandoblock som är relaterade till världshantering.\
   Detta är den grundläggande behörighetsgruppen för datapaket och kommandoblock.
3. **Administratör**\
   Har åtkomst till alla kommandon som är relaterade till spelarhantering.
4. **Superadministratör**\
   Har åtkomst till alla kommandon, inklusive serverhantering.\
   Detta är den grundläggande behörighetsgruppen för konsol och operatörer.

***

## Ställa in behörigheter <a href="#id-2" id="id-2"></a>

***

## Fullständiga behörigheter <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Standard**: `Inget`

Tillåter spelare att krypa och interagera med enheter för att rida dem.

När man rider enheten kan spelaren använda rörelsetangenterna för att styra enhetens rörelse och hoppa eller flyga med hoppknappen.

`(Namespaced Key)` är enhetens [Namespaced ID](#user-content-fn-2)[^2].

{% hint style="info" %}

**Funktioner endast om `(Entity) > ridable` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standard**: `Inget`

Tillåter spelaren att använda enhetens speciella färdigheter medan de rider enheten.

Inte alla enheter har tillgång till speciella färdigheter. Se nedan för en lista över alla tillgängliga speciella färdigheter.

{% hint style="info" %}

**Har du bra idéer för speciella färdigheter?**

Vänligen dela dina idéer på [Plazma Discord](https://plazmamc.org/discord) eller [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Se aktuella tillgängliga speciella färdigheter</summary>

- **`crepper`**\
  Exploderar när du trycker på hoppknappen.\
  Om spelaren har behörigheten `allow.powered.creeper` kan de ladda upp explosionen genom att hålla ned hoppknappen.
- **`dolphin`**\
  Rusar fram när du trycker på hoppknappen.
- **`phantom`**\
  Spottar eld när du trycker på hoppknappen.
- **`wither`**\
  Skjuter ut witherhuvuden när du interagerar med enheten.

</details>

{% hint style="info" %}

**Funktioner endast om `(Entity) > ridable` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/compass` kommandot](commands.md#compass).

#### `bukkit.command.credits`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/credits (Spelare)` kommandot](commands.md#credits).

Lägg till `.other` efter behörighetsnamnet för att tillåta andra spelare att använda det.

#### `bukkit.command.demo`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/demo (Spelare)` kommandot](commands.md#demo).

Lägg till `.other` efter behörighetsnamnet för att tillåta andra spelare att använda det.

#### `bukkit.command.ping`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/ping (Spelare)` kommandot](commands.md#ping).

Lägg till `.other` efter behörighetsnamnet för att tillåta andra spelare att använda det.

#### `bukkit.command.ram`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/ram` kommandot](commands.md#ram).

#### `bukkit.command.rambar`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/rambar (Spelare)` kommandot](commands.md#rambar).

Lägg till `.other` efter behörighetsnamnet för att tillåta andra spelare att använda det.

#### `bukkit.command.restart`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/restart` kommandot](commands.md#restart).

#### `bukkit.command.tps`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/tps` kommandot](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/tpsbar (Spelare)` kommandot](commands.md#tpsbar).

Lägg till `.other` efter behörighetsnamnet för att tillåta andra spelare att använda det.

#### `bukkit.command.timings`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/timings` kommandot](commands.md#timings).

{% hint style="warning" %}

**Detta kommando har avslutats.**

Kolla in [Spark](https://spark.lucko.me/docs/Command-Usage) för liknande funktioner.

{% endhint %}

#### `bukkit.command.uptime`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/uptime` kommandot](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Standard**: `Världsadministratör`

Tillåter användning av [`/gamemode (GameMode) (Spelare)` kommandot](commands.md#gamemode).

Lägg till `.other` efter behörighetsnamnet för att tillåta andra spelare att använda det.

#### `paper.antixray.bypass`

- **Standard**: `Inget`

Om [X-Ray blockering](../expert/xray.md) är aktiverad,
så kommer behörighetsregistrerade spelare inte att underkastas blockering av block X-Ray.

Detta ger fördelar för båda sidor genom att förbättra prestandan.

> För information om inställningar för X-Ray, se sidan nedan.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standard**: `Inget`

{% hint style="warning" %}

Denna behörighet kommer att bytas till `plazma.bypass.watchdog` i version 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Standard**: `Inget`

Tillåter användning av [färgkoder](https://minecraft.wiki/w/Formatting_codes#Color_codes) på städ.

{% hint style="info" %}

**Funktionen fungerar endast om `anvil > allow-colors` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Standard**: `Inget`

Tillåter användning av [formateringskoder](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) på städ.

{% hint style="info" %}

**Funktionen fungerar endast om `anvil > allow-colors` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Standard**: `Inget`

Tillåter användning av [MiniMessage taggar](https://docs.advntr.dev/minimessage/format.html) på städ.

{% hint style="info" %}

**Funktionen fungerar endast om `anvil > allow-minimessages` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standard**: `Inget`

Tillåter att inaktivera `kursiv stil` på städ med stylen `&r` från [formateringskoder](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**Funktionen fungerar endast om `anvil > allow-colors` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Standard**: `Inget`

Tillåter att tillämpa [formateringskoder](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) när spelaren signerar en bok.

#### `purpur.bypassIdleKick`

- **Standard**: `Inget`

Undantar spelare från att bli kastade ut på grund av inaktivitet.

#### `purpur.debug.f3n`

- **Standard**: `Världsadministratör`

Tillåter spelare att ändra spelarläget med tangentkombinationen `F3 + N`.

Funktionen fungerar endast om spelaren har behörigheten för det specifika spelläget.

#### `purpur.drop.spawners`

- **Standard**: `Inget`

Om spelaren bryter en spawnerblock med det konfigurerade verktyget kommer spawnerblocket att släppas.

{% hint style="info" %}

**Funktionen fungerar endast om `gameplay-mechanics > silk-touch` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standard**: `Inget`

Ändrar storleken på en enderbröst.

`(NumberString)` kan vara `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Funktionen fungerar endast om `ender_chest > six-rows` och `ender_chest > use-permissions-for-rows` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Standard**: `Inget`

Tillåter att det odödliga totemet fungerar även om det finns i inventariot.

{% hint style="info" %}

**Funktionen fungerar endast om `totem-of-undying-works-in-inventory` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Standard**: `Inget`

Tillåt spelaren att ignorera begränsningen för antalet anslutningar.

#### `purpur.mending_shift_click`

- **Standard**: `Inget`

Tillåt spelaren att reparera det hållna föremålet genom att `shift-klicka` interagera.

{% hint style="info" %}

**För att aktivera `shift-right-click-repairs-mending-points` i **[Purpur World Configurations](configurations/purpur/world.md)**.**

{% endhint %}

#### `purpur.place.spawners`

- **Standard**: `Inget`

Tillåt spelaren att placera spawner.

{% hint style="info" %}

**Funktionen fungerar endast om `gameplay-mechanics > silk-touch` är aktiverat i [Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Standard**: `Inget`

Låt spelaren teleportera direkt när de använder Nether Portal.

#### `purpur.sign.color`

- **Standard**: `Inget`

Tillåter användning av [färgkoder](https://minecraft.wiki/w/Formatting_codes#Color_codes) på skyltar.

{% hint style="info" %}

\*\*För att det ska fungera måste `sign > allow-colors` aktiveras i **[Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.magic`

- **Standard**: `Inget`

Tillåt användning av obfuscation-kod `(&o)` på skyltar.

{% hint style="info" %}

\*\*För att det ska fungera måste `sign > allow-colors` aktiveras i **[Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.style`

- **Standard**: `Inget`

Tillåt användning av [formateringskoder `(&o exkluderat)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) på skyltar.

{% hint style="info" %}

\*\*För att det ska fungera måste `sign > allow-colors` aktiveras i **[Purpur världskonfigurationen](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.tnt.defuse`

- **Standard**: `Inget`

Tillåt spelare att med `interaktion` med sax förhindra TNT-explosioner.

{% hint style="info" %}

**För att fungera måste `defuse-tnt-change` i [Purpur world configuration](configurations/purpur/world.md) vara `0.0` eller högre.**

{% endhint %}

### Planerad behörighet

#### `plazma.bypass.ncr-require`

- **Standard**: `Inget`

Tillåt spelare att ansluta även om de inte har modet [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) installerat.

{% hint style="info" %}

**För att fungera måste `no-chat-reports > require-install` vara aktiverat i [Plazma world configuration](configurations/plazma/world.md).**

{% endhint %}

***

[^1]: Operatör.

[^2]: Exempel: `ender_dragon`
