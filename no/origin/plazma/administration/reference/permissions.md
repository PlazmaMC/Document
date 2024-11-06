---
description: Få informasjon om tillatelsene til Plazma.
---

# 🛡️ Tillatelser

Tillatelse er et enkelt sikkerhetsverktøy som setter omfanget av samhandling mellom spillere på serveren.

For å bruke tillatelser skikkelig og enkelt endre dem, må du bruke tillegg som [LuckPerms](https://luckperms.net).

***

## Forstå grunnleggende tillatelsessystem <a href="#id-1" id="id-1"></a>

Minecraft tilbyr grunnleggende administrasjonsgrupper for tillatelser.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Spiller**\
   En grunnleggende tillatelsesgruppe som vanligvis gis til alle spillere.
2. **Moderator**\
   Kan ignorere spawnbeskyttelse.
3. **Verdensadministrator**\
   Kan bruke alle kommandoer og kommandoblokker relatert til verdensadministrasjon.\
   En grunnleggende tillatelsesgruppe som brukes som standard for datapakker og kommandoblokker.
4. **Administrator**\
   Kan bruke alle kommandoer relatert til spilleradministrasjon.
5. **Hovedadministrator**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standard**: `Ingen`

Tillater at spillere kan bruke enhetens spesialferdigheter mens de rir enheten.

Ikke alle enheters spesialferdigheter er tilgjengelige. Se nedenfor for en liste over tilgjengelige spesialferdigheter.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Dette gir fordeler for begge parter i form av ytelsesforbedringer.

> Se siden nedenfor for informasjon om hvordan du konfigurerer X-Ray.

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

Tillater bruk av [MiniMessage tags](https://docs.advntr.dev/minimessage/format.html) på ambolter.

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

Ekskluderer spillere fra å bli kastet ut for inaktivitet.

#### `purpur.debug.f3n`

- **Standard**: `Verdensadministrator`

Tillater spillere å endre spillmodus ved å bruke tastekombinasjonen `F3 + N`.

Fungerer bare hvis spilleren har tillatelse for den aktuelle spillmodusen.

#### `purpur.drop.spawners`

- **Standard**: `Ingen`

Hvis aktivert i konfigurasjonen, vil gruving av spawnerblokker med de angitte elementene slippe spawnerblokken.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standard**: `Ingen`

Endrer størrelsen på enderbrystet.

Mulige verdier for `(NumberString)` er `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Standard**: `Ingen`

Tillater at totem av udødelighet fungerer selv om den er i inventaret.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Standard**: `Ingen`

Spilleren tillates å ignorere begrensningen for antall tilkoblede brukere.

#### `purpur.mending_shift_click`

- **Standard**: `Ingen`

Spilleren tillates å reparere det holdte elementet ved å `snu seg ned og samhandle`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Standard**: `Ingen`

Spilleren tillates å installere spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Standard**: `Ingen`

Spilleren tillates å teleportere umiddelbart når de bruker Nether portal.

#### `purpur.sign.color`

- **Standard**: `Ingen`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Standard**: `Ingen`

Tillat bruk av obfuskasjonskoden `(&o)` på skilt.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.skilt.stil`

- **Standard**: `Ingen`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.desarmere`

- **Standard**: `Ingen`

Tillat spillere å forhindre TNT-eksplosjoner ved å `samhandle` med saks.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Forventede tillatelser

#### `plazma.omgå.ncr-krav`

- **Standard**: `Ingen`

Tillat spillere å koble til selv om de ikke har installert modulen [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operatør.

[^2]: Eksempel: `ender_dragon`
