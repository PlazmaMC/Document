---
description: Uurige Plazma õigusi.
---

# 🛡️ Õigused

Õigused on lihtne turvavahend, mis määrab serveri mängijate vahelise suhtluse ulatuse.

Õiguste korralikuks kasutamiseks ja lihtsaks muutmiseks tuleks kasutada pistikprogramme nagu [LuckPerms](https://luckperms.net).

***

## Mõistke vaikimisi õiguste süsteemi <a href="#id-1" id="id-1"></a>

Minecraftis on vaikimisi haldusõiguste gruppe.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Mängija**\
   Tavaline õiguste grupp, mis antakse tavaliselt kõigile mängijatele.
2. **Vahendaja**\
   Võib ignoreerida spawnpunktide kaitset.
3. **Maailma administraator**\
   Saab kasutada kõiki maailma haldamise ja sellega seotud käsklusi ning käsu plokke.\
   See on vaikimisi rakendatav õiguste grupp andmepakettidele ja käsu plokkidele.
4. **Administraator**\
   Saab kasutada kõiki mängijate haldamise ja sellega seotud käsklusi.
5. **Peakasutaja**\
   Saab kasutada kõiki serveri haldamise ja sellega seotud käsklusi.\
   See on vaikimisi rakendatav õiguste grupp konsoolile ja administraatoritele.

***

## Määrake õigused <a href="#id-2" id="id-2"></a>

***

## Kogu õigus <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Vaikimisi**: `Puudub`

Lubab mängijal kummarduda ja suhelda üksustega, et neile peale istuda.

Üksust peale istudes saate kasutada `liikumisklahve` selle liigutamiseks ja hüppamiseks või lendamiseks `hüppeklahviga`.

`(Namespaced Key)` tähistab üksuse [Namespaced ID](#user-content-fn-2)[^2].

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Vaikimisi**: `Puudub`

Lubab mängijal kasutada üksuse erilisi võimeid, kui ta sõidab üksusel.

Kõikide üksuste erivõimed ei pruugi olla saadaval. Vaadake kõikide saadaolevate erivõimete kohta allpool.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Avaldage oma ideed [Plazma Discordis](https://plazmamc.org/discord) või [GitHubi aruteludes](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Vaadake praegu saadaolevaid erivõimeid</summary>

- **`creeper`**\
  Vajutades `hüppeklahvi` plahvatab.\
  Kui mängijal on lubatud `allow.powered.creeper` õigus, saab ta plahvatuse laadimiseks hoida `hüppeklahvi` all.
- **`delfiin`**\
  Vajutades `hüppeklahvi` teeb hüppe edasi.
- **`phantom`**\
  Vajutades `hüppeklahvi` tulistab tulekahju.
- **`wither`**\
  `Suhtlemisel` tulistab wither pea.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/compass` käsku](commands.md#compass).

#### `bukkit.command.credits`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/credits (Mängija)` käsku](commands.md#credits).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.demo`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/demo (Mängija)` käsku](commands.md#demo).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.ping`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/ping (Mängija)` käsku](commands.md#ping).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.ram`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/ram` käsku](commands.md#ram).

#### `bukkit.command.rambar`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/rambar (Mängija)` käsku](commands.md#rambar).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.restart`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/restart` käsku](commands.md#restart).

#### `bukkit.command.tps`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/tps` käsku](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/tpsbar (Mängija)` käsku](commands.md#tpsbar).

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `bukkit.command.timings`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/timings` käsku](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Vaadake sarnaseid käsklusi [Sparki](https://spark.lucko.me/docs/Command-Usage) lehelt.
{% endhint %}

#### `bukkit.command.uptime`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/uptime` käsku](commands.md#uptime).

#### `minecraft.command.gamemode.(Mängurežiim)`

- **Vaikimisi**: `Maailma administraator`

Lubab kasutada [`/gamemode (Mängurežiim) (Mängija)` käsku.

Lisades õigusele nimele `.other`, võimaldab see seda kasutada teistel mängijatel.

#### `paper.antixray.bypass`

- **Vaikimisi**: `Puudub`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

See võimaldab mõlemal poolel paremat jõudlust kogeda.

> X-Ray seadistamiseks vaadake allpool olevat lehekülge.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Vaikimisi**: `Puudub`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Vaikimisi**: `Puudub`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Vaikimisi**: `Puudub`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Vaikimisi**: `Puudub`

Võimaldab kasutada sepikutel [MiniMessage sildid](https://docs.advntr.dev/minimessage/format.html).

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Vaikimisi**: `Puudub`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Vaikimisi**: `Puudub`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Vaikimisi**: `Puudub`

Võimaldab mängijal jääda passiivse väljaviskamise sihtrühmast välja.

#### `purpur.debug.f3n`

- **Vaikimisi**: `Maailma administraator`

Võimaldab mängijal kasutada mängurežiimi muutmiseks klahvikombinatsiooni `F3 + N`.

See ei tööta, kui puudub vastav mängurežiimi õigus.

#### `purpur.drop.spawners`

- **Vaikimisi**: `Puudub`

Kui kaevate konfigureeritud esemega spawneriploki, siis see kukub maha.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Vaikimisi**: `Puudub`

Muudab Enderi kirstu suurust.

`(NumberString)` võib olla `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Vaikimisi**: `Puudub`

Võimaldab toimida surematu käsna inventaris.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse ignoreerida ühenduse piirangut.

#### `purpur.mending_shift_click`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse eseme remontimise võimaldamiseks `kummargil olles koostööd teha`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse paigaldada spawnereid.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Vaikimisi**: `Puudub`

Mängijale lubatakse kohe pärast Netheri portaali kasutamist kohe teleporteeruda.

#### `purpur.sign.color`

- **Vaikimisi**: `Puudub`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Vaikimisi**: `Puudub`

Luba kasutada märkide kodeerimist `(&o)` märkidele.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Vaikimisi**: `Puudub`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Vaikimisi**: `Puudub`

Luba mängijal takistada TNT plahvatust `vastastikuse tegevusega` kääride abil.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Antud õigus tuleb.

#### `plazma.bypass.ncr-require`

- **Vaikimisi**: `Puudub`

Luba mängijal ühenduda isegi kui pole paigaldatud [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) moodulit.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operaator.

[^2]: Näide: `ender_dragon`
