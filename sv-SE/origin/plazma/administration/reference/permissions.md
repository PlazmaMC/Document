---
description: Ta reda på behörigheterna för Plazma.
---

# 🛡️ Behörighet

Behörigheter är en enkel säkerhetsåtgärd som ställer in omfånget där spelare på servern kan interagera med varandra.

För att använda och enkelt redigera behörigheter bör du använda tillägg som [LuckPerms](https://luckperms.net).

***

## Förstå den grundläggande behörighetsstrukturen <a href="#id-1" id="id-1"></a>

I Minecraft finns det grundläggande administrativa behörighetsgrupper tillgängliga.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Spelare**\
   En behörighetsgrupp som vanligtvis tilldelas alla spelare.
2. **Medlare**\
   Kan ignorera spawnskydd.
3. **Världsadministratör**\
   Har åtkomst till alla kommandon och kommandoblock som är relaterade till världshantering.\
   Detta är den grundläggande behörighetsgruppen för datapaket och kommandoblock.
4. **Administratör**\
   Har åtkomst till alla kommandon som är relaterade till spelarhantering.
5. **Superadministratör**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standard**: `Inget`

Tillåter spelaren att använda enhetens speciella färdigheter medan de rider enheten.

Inte alla enheter har tillgång till speciella färdigheter. Se nedan för en lista över alla tillgängliga speciella färdigheter.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Detta ger fördelar för båda sidor genom att förbättra prestandan.

> För information om inställningar för X-Ray, se sidan nedan.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standard**: `Inget`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Standard**: `Inget`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Standard**: `Inget`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Standard**: `Inget`

Tillåter användning av [MiniMessage taggar](https://docs.advntr.dev/minimessage/format.html) på städ.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standard**: `Inget`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Standard**: `Inget`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standard**: `Inget`

Ändrar storleken på en enderbröst.

`(NumberString)` kan vara `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Standard**: `Inget`

Tillåter att det odödliga totemet fungerar även om det finns i inventariot.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Standard**: `Inget`

Tillåt spelaren att ignorera begränsningen för antalet anslutningar.

#### `purpur.mending_shift_click`

- **Standard**: `Inget`

Tillåt spelaren att reparera det hållna föremålet genom att `shift-klicka` interagera.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Standard**: `Inget`

Tillåt spelaren att placera spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Standard**: `Inget`

Låt spelaren teleportera direkt när de använder Nether Portal.

#### `purpur.sign.color`

- **Standard**: `Inget`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Standard**: `Inget`

Tillåt användning av obfuscation-kod `(&o)` på skyltar.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Standard**: `Inget`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Standard**: `Inget`

Tillåt spelare att med `interaktion` med sax förhindra TNT-explosioner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Planerad behörighet

#### `plazma.bypass.ncr-require`

- **Standard**: `Inget`

Tillåt spelare att ansluta även om de inte har modet [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) installerat.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operatör.

[^2]: Exempel: `ender_dragon`
