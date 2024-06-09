---
description: Ontdek de rechten van Plazma.
---

# 🛡️ Rechten

Machtigingen zijn eenvoudige beveiligingstools die de reikwijdte van interactie van spelers binnen de server instellen.

Om machtigingen goed te gebruiken en gemakkelijk aan te passen, moet je plug-ins zoals [LuckPerms](https://luckperms.net) gebruiken.

***

## Begrijp het standaard machtigingssysteem <a href="#id-1" id="id-1"></a>

Minecraft biedt standaard beheermachtigingsgroepen.

Je kunt machtigingen instellen voor [beheerders](#user-content-fn-1)[^1] en commandoblokken, en deze aanpassen in de [servereigenschappen](configurations/property.md).

0. **Speler**\
   Dit is de standaard machtigingsgroep die aan alle spelers wordt gegeven.
1. **Bemiddelaar**\
   Kan spawnbescherming negeren.
2. **Wereldbeheerder**\
   Kan alle opdrachten en commandoblokken met betrekking tot wereldbeheer gebruiken.\
   Dit is de standaard toegepaste machtigingsgroep voor datapacks en commandoblokken.
3. **Beheerder**\
   Kan alle opdrachten met betrekking tot spelerbeheer gebruiken.
4. **Hoofdbeheerder**\
   Kan alle opdrachten, inclusief serverbeheer, gebruiken.\
   Dit is de standaard toegepaste machtigingsgroep voor consoles en beheerders.

***

## Machtigingen instellen <a href="#id-2" id="id-2"></a>

***

## Volledige machtigingen <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Standaard**: `Geen`

Staat spelers toe om te hurken en te interageren met entiteiten om ze te berijden.

Als je een entiteit berijdt, kun je met de beweegtoetsen de beweging van de entiteit besturen en met de springtoets springen of vliegen.

De [Namespaced ID](#user-content-fn-2)[^2] van de entiteit wordt ingevoerd in `(Namespaced Key)`.

{% hint style="info" %}

**Werkt alleen als `(Entity) > ridable` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standaard**: `Geen`

Staat spelers toe om de speciale vaardigheden van een entiteit te gebruiken terwijl ze deze berijden.

Niet alle speciale vaardigheden van entiteiten zijn beschikbaar. Raadpleeg hieronder voor een lijst van alle beschikbare speciale vaardigheden.

{% hint style="info" %}

**Heb je een goed idee voor een speciale vaardigheid?**

Plaats je ideeën op [Plazma Discord](https://plazmamc.org/discord) of [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions) a.u.b.!

{% endhint %}

<details>

<summary>Bekijk momenteel beschikbare speciale vaardigheden</summary>

- **`crepper`**\
  Als je op de springtoets drukt, explodeert het.\
  Als een speler de `allow.powered.creeper` machtiging heeft, kan hij de springtoets ingedrukt houden om op te laden.
- **`dolphin`**\
  Als je op de springtoets drukt, sprint je.
- **`phantom`**\
  Als je op de springtoets drukt, vuur je vlammen af.
- **`wither`**\
  Als je interactie hebt, schiet je Wither-schedels af.

</details>

{% hint style="info" %}

**Werkt alleen als `(Entity) > ridable` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/compass` commando](commands.md#compass) toe.

#### `bukkit.command.credits`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/credits (Speler)` commando](commands.md#credits) toe.

Als je `.other` achter de machtigingsnaam invoert, kun je andere spelers toestaan dit te gebruiken.

#### `bukkit.command.demo`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/demo (Speler)` commando](commands.md#demo) toe.

Als je `.other` achter de machtigingsnaam invoert, kun je andere spelers toestaan dit te gebruiken.

#### `bukkit.command.ping`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/ping (Speler)` commando](commands.md#ping) toe.

Als je `.other` achter de machtigingsnaam invoert, kun je andere spelers toestaan dit te gebruiken.

#### `bukkit.command.ram`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/ram` commando](commands.md#ram) toe.

#### `bukkit.command.rambar`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/rambar (Speler)` commando](commands.md#rambar) toe.

Als je `.other` achter de machtigingsnaam invoert, kun je andere spelers toestaan dit te gebruiken.

#### `bukkit.command.restart`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/restart` commando](commands.md#restart) toe.

#### `bukkit.command.tps`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/tps` commando](commands.md#tps) toe.

#### `bukkit.command.tpsbar`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/tpsbar (Speler)` commando](commands.md#tpsbar) toe.

Als je `.other` achter de machtigingsnaam invoert, kun je andere spelers toestaan dit te gebruiken.

#### `bukkit.command.timings`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/timings` commando](commands.md#timings) toe.

{% hint style="warning" %}

**Deze opdracht is stopgezet.**

Raadpleeg [Spark](https://spark.lucko.me/docs/Command-Usage) voor vergelijkbare commando's.

{% endhint %}

#### `bukkit.command.uptime`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/uptime` commando](commands.md#uptime) toe.

#### `minecraft.command.gamemode.(GameMode)`

- **Standaard**: `Wereldbeheerder`

Staat het gebruik van de [`/gamemode (GameMode) (Speler)` commando](commands.md#gamemode) toe.

Als je `.other` achter de machtigingsnaam invoert, kun je andere spelers toestaan dit te gebruiken.

#### `paper.antixray.bypass`

- **Standaard**: `Geen`

Als [X-Ray blokkering](../expert/xray.md) is ingeschakeld, worden spelers met deze machtiging niet onderworpen aan X-Ray blokkade van blokken.

Dit zorgt voor prestatieverbeteringen aan beide kanten.

> Raadpleeg de onderstaande pagina voor informatie over X-Ray-instellingen.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standaard**: `Geen`

{% hint style="warning" %}

Deze machtiging zal worden gewijzigd naar `plazma.bypass.watchdog` in 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Standaard**: `Geen`

Staat het gebruik van [kleurcodes](https://minecraft.wiki/w/Formatting_codes#Color_codes) op een aambeeld toe.

{% hint style="info" %}

**Werkt alleen als `anvil > allow-colors` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Standaard**: `Geen`

Staat het gebruik van [opmaakcodes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) op een aambeeld toe.

{% hint style="info" %}

**Werkt alleen als `anvil > allow-colors` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Standaard**: `Geen`

Staat het gebruik van [MiniMessage-tags](https://docs.advntr.dev/minimessage/format.html) op een aambeeld toe.

{% hint style="info" %}

**Werkt alleen als `anvil > allow-minimessages` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standaard**: `Geen`

Staat het uitschakelen van `cursief lettertype` met de [`&r` opmaakcode](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) op een aambeeld toe.

{% hint style="info" %}

**Werkt alleen als `anvil > allow-colors` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Standaard**: `Geen`

Zorgt ervoor dat opmaakcodes worden toegepast wanneer een speler een boek ondertekent.

#### `purpur.bypassIdleKick`

- **Standaard**: `Geen`

Voorkomt dat spelers worden uitgegooid vanwege inactiviteit.

#### `purpur.debug.f3n`

- **Standaard**: `Wereldbeheerder`

Staat spelers toe om met de toetscombinatie `F3 + N` de spelmodus te wijzigen.

Dit werkt alleen als de speler de juiste machtiging heeft.

#### `purpur.drop.spawners`

- **Standaard**: `Geen`

Als je een spawnerblok met het geconfigureerde item afbreekt, valt het spawnerblok naar beneden.

{% hint style="info" %}

**Werkt alleen als `gameplay-mechanics > silk-touch` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standaard**: `Geen`

Verandert de grootte van de ender-kist.

Je kunt `one`, `two`, `three`, `four`, `five`, `six` invoeren voor `(NumberString)`.

{% hint style="info" %}

**Werkt alleen als `ender_chest > six-rows` en `ender_chest > use-permissions-for-rows` zijn ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Standaard**: `Geen`

Staat toe dat de totem van onsterfelijkheid werkt, zelfs als deze in het inventaris van de speler zit.

{% hint style="info" %}

**Werkt alleen als `totem-of-undying-works-in-inventory` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Standaard**: `Geen`

De speler wordt toegestaan om de limiet van het aantal verbindingen te negeren.

#### `purpur.mending_shift_click`

- **Standaard**: `Geen`

De speler wordt toegestaan om een voorwerp te repareren wanneer hij `gebukt gaat en interageert`.

{% hint style="info" %}

**[Purpur wereldconfiguraties](configuraties/purpur/world.md) moeten `shift-rechtsklik-herstelt-mending-punten` activeren om te laten werken.**

{% endhint %}

#### `purpur.place.spawners`

- **Standaard**: `Geen`

De speler wordt toegestaan om spawners te plaatsen.

{% hint style="info" %}

**Werkt alleen als `gameplay-mechanics > silk-touch` is ingeschakeld in [Purpur wereldconfiguraties](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Standaard**: `Geen`

De speler wordt toegestaan om direct te teleporteren wanneer hij de Nether portal gebruikt.

#### `purpur.sign.color`

- **Standaard**: `Geen`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting_codes#Color_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.sign.magic`

- **Standaard**: `Geen`

Toestaan dat het ontcijferingscode`(&o)` op borden wordt gebruikt.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.sign.style`

- **Standaard**: `Geen`

Toestaan dat [opmaakcodes `(&o uitgesloten)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) op borden worden gebruikt.

{% hint style="info" %}

**[Purpur 세계별 구성](configurations/purpur/world.md)에서 `sign > allow-colors`를 활성화 해야 작동합니다.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Standaard**: `Geen`

Toestaan dat spelers met een schaar `wederzijds interactie` TNT-explosies kunnen voorkomen.

{% hint style="info" %}

**[Purpur wereldconfiguraties](configurations/purpur/world.md) moeten `defuse-tnt-change` van `0.0` of hoger hebben om te werken.**

{% endhint %}

### Geplande toestemmingen

#### `plazma.bypass.ncr-require`

- **Standaard**: `Geen`

Toestaan dat spelers kunnen verbinden zonder dat de [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod is geïnstalleerd.

{% hint style="info" %}

**[Plazma wereldconfiguraties](configurations/plazma/world.md) moeten `no-chat-reports > require-install` inschakelen om te werken.**

{% endhint %}

***

[^1]: Operator.

[^2]: Bijv.: `ender_dragon`
