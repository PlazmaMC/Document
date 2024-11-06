---
description: Få mere at vide om tilladelserne til Plazma.
---

# 🛡️ Tilladelser

Rettigheder er et simpelt sikkerhedsværktøj på serveren, der definerer omfanget af interaktion mellem spillere.

For at udnytte rettigheder korrekt og let kunne redigere dem, skal du bruge plugins som [LuckPerms](https://luckperms.net).

***

## Forståelse af grundlæggende rettighedssystem <a href="#id-1" id="id-1"></a>

Minecraft tilbyder grundlæggende administrative rettighedsgrupper.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Spillere**\
   Er en standard rettighedsgruppe tildelt alle spillere.
2. **Mæglere**\
   Kan ignorere spawnbeskyttelse.
3. **Verdensadministratorer**\
   Kan bruge alle kommandoer og kommandoblokke relateret til verdensstyring.\
   Er en standard rettighedsgruppe for datapakker og kommandoblokke.
4. **Administratorer**\
   Kan bruge alle kommandoer relateret til spillerstyring.
5. **Superadministratorer**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standard**: `Ingen`

Tillader spilleren at bruge en entitets specielle evner, mens de rider på entiteten.

Ikke alle entiteters specielle evner er tilgængelige. Se nedenfor for en liste over alle tilgængelige specielle evner.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Dette giver forbedret ydeevne for begge parter.

> Se nedenstående side for at lære om X-Ray-indstillinger.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standard**: `Ingen`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Standard**: `Ingen`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Standard**: `Ingen`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Standard**: `Ingen`

Tillader brug af MiniMessage-tags på ambolten med [MiniMessage-tags](https://docs.advntr.dev/minimessage/format.html).

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standard**: `Ingen`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Standard**: `Ingen`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standard**: `Ingen`

Ændrer størrelsen på en enderbryst.

Du kan indtaste `one`, `two`, `three`, `four`, `five`, `six` i `(NumberString)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Standard**: `Ingen`

Tillader, at totem af udødelighed fungerer, selvom det er i inventaret.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Standard**: `Ingen`

Tillad spilleren at ignorere serverens fulde kapacitet.

#### `purpur.mending_shift_click`

- **Standard**: `Ingen`

Tillad spilleren at reparere genstande ved at `trykke skifte og højreklikke` mens de er bøjet.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Standard**: `Ingen`

Tillad spilleren at placere spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Standard**: `Ingen`

Lad spilleren øjeblikkeligt teleportere, når de bruger Nether portalen.

#### `purpur.sign.color`

- **Standard**: `Ingen`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Standard**: `Ingen`

Tillad brug af forvrængningskode `(&o)` på skilte.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Standard**: `Ingen`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Standard**: `Ingen`

Tillad spilleren at forhindre TNT-eksplosion ved at `interagere` med saks.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Planlagte tilladelser

#### `plazma.bypass.ncr-require`

- **Standard**: `Ingen`

Tillad spilleren at deltage uden at have [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod installeret.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operatør.

[^2]: F.eks.: `ender_dragon`
