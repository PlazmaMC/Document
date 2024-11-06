---
description: Zistite viac o oprávneniach aplikácie Plazma.
---

# 🛡️ Oprávnenia

Oprávnenie je jednoduchý bezpečnostný nástroj na nastavenie rozsahu interakcie hráčov na serveri.

Na správne využívanie oprávnení a jednoduchú úpravu je potrebné použiť pluginy ako [LuckPerms](https://luckperms.net).

***

## Porozumenie základnému systému oprávnení <a href="#id-1" id="id-1"></a>

V Minecrafte sú k dispozícii základné správcovské skupiny oprávnení.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Hráč**\
   Je to skupina oprávnení, ktorá je bežne pridelená každému hráčovi.
2. **Mediátor**\
   Môže ignorovať ochranu spawnu.
3. **Správca sveta**\
   Môže používať všetky príkazy a príkazové bloky súvisiace so správou sveta.\
   Je to základná skupina oprávnení, ktorá sa automaticky aplikuje na datapacky a príkazové bloky.
4. **Administrátor**\
   Môže používať všetky príkazy súvisiace s riadením hráčov.
5. **Hlavný administrátor**\
   Môže používať všetky príkazy vrátane správy servera.\
   Je to základná skupina oprávnení, ktorá sa automaticky aplikuje na konzolu a administrátorov.

***

## Nastavenie oprávnení <a href="#id-2" id="id-2"></a>

***

## Celkové oprávnenia <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Predvolené**: `None`

Umožňuje hráčovi sedieť na entite a interagovať s ňou skrčením.

Keď hráč sedí na entite, môže ju ovládať pohybom klávesnice a skákať alebo lietať stlačením skoku.

V `(Namespaced Key)` sa zapisuje [Namespaced ID](#user-content-fn-2)[^2] entity.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Predvolené**: `None`

Umožňuje hráčovi používať špeciálne schopnosti entity, na ktorej sedí.

Nie všetky entity majú dostupné špeciálne schopnosti. Pre zoznam všetkých dostupných špeciálnych schopností sa pozrite nižšie.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Zdieľajte svoje nápady na [Plazma Discord](https://plazmamc.org/discord) alebo [GitHub Diskusie](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Prezrite si aktuálne dostupné špeciálne schopnosti</summary>

- **`crepper`**\
  Pri stlačení klávesu skoku exploduje.\
  Ak hráč má oprávnenie `allow.powered.creeper`, môže držaním klávesu skoku nabíjať výbuch.
- **`dolphin`**\
  Pri stlačení klávesu skoku pláva rýchlejšie.
- **`phantom`**\
  Pri stlačení klávesu skoku vystreľuje plamene.
- **`wither`**\
  Pri interakcii vystreľuje hlavy withera.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/compass` príkaz](commands.md#compass).

#### `bukkit.command.credits`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/credits (Hráč)` príkaz](commands.md#credits).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.demo`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/demo (Hráč)` príkaz](commands.md#demo).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.ping`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/ping (Hráč)` príkaz](commands.md#ping).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.ram`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/ram` príkaz](commands.md#ram).

#### `bukkit.command.rambar`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/rambar (Hráč)` príkaz](commands.md#rambar).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.restart`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/restart` príkaz](commands.md#restart).

#### `bukkit.command.tps`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/tps` príkaz](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/tpsbar (Hráč)` príkaz](commands.md#tpsbar).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `bukkit.command.timings`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/timings` príkaz](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Pre podobné príkazy sa pozrite na [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/uptime` príkaz](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Predvolené**: `Správca sveta`

Umožňuje používať [`/gamemode (GameMode) (Hráč)` príkaz](commands.md#gamemode).

Ak zadáte za názvom oprávnenia `.other`, môže ho používať aj iný hráč.

#### `paper.antixray.bypass`

- **Predvolené**: `None`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Týmto sa zlepší výkon pre obidve strany.

> Pre informácie o nastavení X-Ray pozrite nižšie uvedenú stránku.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Predvolené**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Predvolené**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Predvolené**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Predvolené**: `None`

Umožňuje používať [MiniMessage značky](https://docs.advntr.dev/minimessage/format.html) na kovadle.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Predvolené**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Predvolené**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Predvolené**: `None`

Vylučuje hráčov z vypnutia pri nečinnosti.

#### `purpur.debug.f3n`

- **Predvolené**: `Správca sveta`

Umožňuje hráčovi zmeniť herný režim klávesami `F3 + N`.

Funguje len ak má príslušné oprávnenie pre daný herný režim.

#### `purpur.drop.spawners`

- **Predvolené**: `None`

Pri ťažení bloku spawnu s nastaveným predmetom ho hráč vyhadzuje.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Predvolené**: `None`

Mení veľkosť ender bedne.

V `(NumberString)` je možné zadať `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Predvolené**: `None`

Umožňuje fungovanie totemu neumierania aj v prípade, že je v inventári.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Predvolené**: `None`

Umožňuje hráčovi ignorovať obmedzenie počtu pripojených používateľov.

#### `purpur.mending_shift_click`

- **Predvolené**: `None`

Umožňuje hráčovi opraviť predmet, ktorý drží, keď `kľakne a interaguje`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Predvolené**: `None`

Umožňuje hráčovi inštalovať spawnery.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Predvolené**: `None`

Umožňuje hráčovi okamžite sa presunúť pri použití Nether portálu.

#### `purpur.sign.color`

- **Predvolené**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Predvolené**: `None`

Povoliť použitie kódu znečitateľnosti `(&o)` na značkách.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Predvolené**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Predvolené**: `None`

Povoliť hráčovi zabrániť výbuchu TNT pomocou `interakcie` so špongiou.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Plánované oprávnenia

#### `plazma.bypass.ncr-require`

- **Predvolené**: `None`

Povoliť hráčovi pripojiť sa aj keď nemá nainštalovaný mód [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operátor.

[^2]: Napr.: `ender_dragon`
