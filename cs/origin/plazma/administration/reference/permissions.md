---
description: Zjistěte více o oprávněních aplikace Plazma.
---

# 🛡️ Oprávnění

Oprávnění jsou jednoduchým bezpečnostním nástrojem, který určuje rozsah, ve kterém mohou hráči na serveru vzájemně interagovat.

Pro správné využití oprávnění a snadnou úpravu je třeba použít pluginy jako [LuckPerms](https://luckperms.net).

***

## Porozumění základnímu systému oprávnění <a href="#id-1" id="id-1"></a>

V Minecraftu jsou poskytovány základní správcovské skupiny oprávnění.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Hráč**\
   Obecná skupina oprávnění, která je obvykle udělena všem hráčům.
2. **Prostředník**\
   Může ignorovat ochranu spawnu.
3. **Správce světa**\
   Může používat všechny příkazy a příkazové bloky související se správou světa.\
   Je to základní skupina oprávnění, která se vztahuje na datové balíčky a příkazové bloky.
4. **Administrátor**\
   Může používat všechny příkazy související s řízením hráčů.
5. **Hlavní správce**\
   Může používat všechny příkazy související se správou serveru.\
   Je to základní skupina oprávnění, která se vztahuje na konzoli a administrátory.

***

## Nastavení oprávnění <a href="#id-2" id="id-2"></a>

***

## Celková oprávnění <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Výchozí**: `None`

Umožňuje hráčům se `skrčit` a interagovat s entitami, aby mohli na ně nastoupit.

Pokud nastoupíte na entitu, můžete pomocí `kláves pro pohyb` ovládat pohyb entity a pomocí `kláves pro skok` skákat nebo létat.

Do `(Namespaced Key)` se zadává [Namespaced ID](#user-content-fn-2)[^2] entity.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Výchozí**: `None`

Umožňuje hráči používat speciální schopnosti entity, když na ní jezdí.

Ne všechny entity mají dostupné speciální schopnosti. Pro seznam všech dostupných speciálních schopností se podívejte níže.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Své nápady můžete sdílet na [Plazma Discordu](https://plazmamc.org/discord) nebo [GitHub Diskuzích](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Zobrazit všechny dostupné speciální schopnosti</summary>

- **`crepper`**\
  Při stisknutí `klávesy pro skok` exploduje.\
  Pokud hráč má oprávnění `allow.powered.creeper`, může držením `klávesy pro skok` nabít výbuch.
- **`dolphin`**\
  Při stisknutí `klávesy pro skok` se vrhne dopředu.
- **`phantom`**\
  Při stisknutí `klávesy pro skok` vystřelí plameny.
- **`wither`**\
  Při `interakci` vystřelí hlavu s Witherem.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/credits (Hráč)`](commands.md#credits).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.demo`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/demo (Hráč)`](commands.md#demo).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.ping`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/ping (Hráč)`](commands.md#ping).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.ram`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/rambar (Hráč)`](commands.md#rambar).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.restart`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/tpsbar (Hráč)`](commands.md#tpsbar).

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `bukkit.command.timings`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/timings`](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Pro informace o podobných příkazech se podívejte na [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje použití příkazu `/gamemode (GameMode) (Hráč)`.

Pokud za oprávněním následuje `.other`, umožňuje použití jinému hráči.

#### `paper.antixray.bypass`

- **Výchozí**: `None`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Tímto způsobem mohou obě strany zažít zlepšení výkonu.

> Pro informace o nastavení X-Ray se podívejte na následující stránku.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Výchozí**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Výchozí**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Výchozí**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Výchozí**: `None`

Umožňuje používat [MiniMessage značky](https://docs.advntr.dev/minimessage/format.html) na kovadlech.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Výchozí**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Výchozí**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Výchozí**: `None`

Vylučuje hráče z cíle vyhazování za nečinnost.

#### `purpur.debug.f3n`

- **Výchozí poskytovatel**: `Správce světa`

Umožňuje hráči změnit herní režim pomocí klávesové zkratky `F3 + N`.

Pokud hráč nemá oprávnění pro tento herní režim, nebude fungovat.

#### `purpur.drop.spawners`

- **Výchozí**: `None`

Při těžbě spawnovacího bloku s nastaveným předmětem se spawnovací blok zahodí.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Výchozí**: `None`

Změní velikost Ender truhly.

Do `(NumberString)` lze zadat `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Výchozí**: `None`

Umožňuje fungování Totemu nesmrtelnosti i když je v inventáři.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Výchozí**: `None`

Umožňuje hráčům ignorovat omezení na maximální počet připojených hráčů.

#### `purpur.mending_shift_click`

- **Výchozí**: `None`

Umožňuje hráčům opravit položku, kterou drží, když se `skloní a kliknou`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Výchozí**: `None`

Umožňuje hráčům umístit spawnery.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Výchozí**: `None`

Umožňuje hráčům okamžitě se přemístit, když použijí Nether portál.

#### `purpur.sign.color`

- **Výchozí**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Výchozí**: `None`

Umožňuje používat kouzelné kódy `(&o)` na cedulích.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Výchozí**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Výchozí**: `None`

Umožňuje hráčům zabránit výbuchu TNT interakcí s ním pomocí nůžek.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Plánovaná oprávnění

#### `plazma.bypass.ncr-require`

- **Výchozí**: `None`

Umožňuje hráčům připojit se i bez nainstalovaného módu [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operátor.

[^2]: Např.: `ender_dragon`
