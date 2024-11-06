---
description: Ontdek de rechten van Plazma.
---

# 🛡️ Rechten

Machtigingen zijn eenvoudige beveiligingstools die de reikwijdte van interactie van spelers binnen de server instellen.

Om machtigingen goed te gebruiken en gemakkelijk aan te passen, moet je plug-ins zoals [LuckPerms](https://luckperms.net) gebruiken.

***

## Begrijp het standaard machtigingssysteem <a href="#id-1" id="id-1"></a>

Minecraft biedt standaard beheermachtigingsgroepen.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Speler**\
   Dit is de standaard machtigingsgroep die aan alle spelers wordt gegeven.
2. **Bemiddelaar**\
   Kan spawnbescherming negeren.
3. **Wereldbeheerder**\
   Kan alle opdrachten en commandoblokken met betrekking tot wereldbeheer gebruiken.\
   Dit is de standaard toegepaste machtigingsgroep voor datapacks en commandoblokken.
4. **Beheerder**\
   Kan alle opdrachten met betrekking tot spelerbeheer gebruiken.
5. **Hoofdbeheerder**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standaard**: `Geen`

Staat spelers toe om de speciale vaardigheden van een entiteit te gebruiken terwijl ze deze berijden.

Niet alle speciale vaardigheden van entiteiten zijn beschikbaar. Raadpleeg hieronder voor een lijst van alle beschikbare speciale vaardigheden.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Dit zorgt voor prestatieverbeteringen aan beide kanten.

> Raadpleeg de onderstaande pagina voor informatie over X-Ray-instellingen.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standaard**: `Geen`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Standaard**: `Geen`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Standaard**: `Geen`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Standaard**: `Geen`

Staat het gebruik van [MiniMessage-tags](https://docs.advntr.dev/minimessage/format.html) op een aambeeld toe.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standaard**: `Geen`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Standaard**: `Geen`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standaard**: `Geen`

Verandert de grootte van de ender-kist.

Je kunt `one`, `two`, `three`, `four`, `five`, `six` invoeren voor `(NumberString)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Standaard**: `Geen`

Staat toe dat de totem van onsterfelijkheid werkt, zelfs als deze in het inventaris van de speler zit.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Standaard**: `Geen`

De speler wordt toegestaan om de limiet van het aantal verbindingen te negeren.

#### `purpur.mending_shift_click`

- **Standaard**: `Geen`

De speler wordt toegestaan om een voorwerp te repareren wanneer hij `gebukt gaat en interageert`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Standaard**: `Geen`

De speler wordt toegestaan om spawners te plaatsen.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Standaard**: `Geen`

De speler wordt toegestaan om direct te teleporteren wanneer hij de Nether portal gebruikt.

#### `purpur.sign.color`

- **Standaard**: `Geen`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Standaard**: `Geen`

Toestaan dat het ontcijferingscode`(&o)` op borden wordt gebruikt.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Standaard**: `Geen`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Standaard**: `Geen`

Toestaan dat spelers met een schaar `wederzijds interactie` TNT-explosies kunnen voorkomen.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Geplande toestemmingen

#### `plazma.bypass.ncr-require`

- **Standaard**: `Geen`

Toestaan dat spelers kunnen verbinden zonder dat de [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod is geïnstalleerd.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Bijv.: `ender_dragon`
