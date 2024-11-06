---
description: Sužinokite apie Plazma teises.
---

# 🛡️ Teisės

Leidimai yra paprastas saugumo įrankis, nustatantis serverio žaidėjų sąveikos galimybės.

Norint tinkamai naudoti leidimus ir lengvai juos keisti, reikia naudoti įskiepius, pvz., [LuckPerms](https://luckperms.net).

***

## Suprasti pagrindinę leidimų sistemą <a href="#id-1" id="id-1"></a>

Minecraft teikia pagrindinius valdymo leidimų grupes.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Žaidėjas**\
   Paprastai tai yra priskiriamas visiems žaidėjams leidimų grupė.
2. **Tarpininkas**\
   Gali ignoruoti spawno apsaugą.
3. **Pasaulio valdytojas**\
   Gali naudoti visas komandas ir komandų blokus, susijusius su pasaulio valdymu.\
   Tai yra numatytasis leidimų grupė, taikomas duomenų paketams ir komandų blokams.
4. **Administratorius**\
   Gali naudoti visas komandas, susijusias su žaidėjų valdymu.
5. **Visagalis**\
   Gali naudoti visas komandas, įskaitant serverio valdymą.\
   Tai yra numatytasis leidimų grupė, taikomas konsolėje ir administratoriams.

***

## Leidimų nustatymas <a href="#id-2" id="id-2"></a>

***

## Visiški leidimai <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Numatytasis**: `None`

Leidžia žaidėjams šliaužti prie entiteto ir jį apeiti.

Kai sėdite ant entiteto, galite valdyti jo judėjimą naudodami `judėjimo klavišus` ir šokinėti arba skristi naudodami `šuolio klavišą`.

Į `(Namespaced Key)` įveskite entiteto [Namespaced ID](#user-content-fn-2)[^2].

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Numatytasis**: `None`

Leidžia žaidėjams naudoti entiteto specialias funkcijas, kai jie sėdi ant jo.

Ne visiems entitetams yra leidžiama naudoti specialias funkcijas. Pilną specialių funkcijų sąrašą rasite žemiau.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Paskelbkite savo idėjas [Plazma Discord](https://plazmamc.org/discord) arba [GitHub diskusijose](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Žiūrėti dabartines specialias funkcijas</summary>

- **`crepper`**\
  Paspaudus `šuolio klavišą`, jis sprogs.\
  Jei žaidėjas turi `allow.powered.creeper` leidimą, jis gali ilgai laikyti `šuolio klavišą`, kad įkrautų.
- **`dolphin`**\
  Paspaudus `šuolio klavišą`, jis puola.
- **`phantom`**\
  Paspaudus `šuolio klavišą`, jis išspjaudys ugnį.
- **`wither`**\
  Jei su juo sąveikaujate, jis iššaudys wither galvą.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/compass` komandą](commands.md#compass).

#### `bukkit.command.credits`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/credits (Žaidėjas)` komandą](commands.md#credits).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.demo`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/demo (Žaidėjas)` komandą](commands.md#demo).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.ping`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/ping (Žaidėjas)` komandą](commands.md#ping).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.ram`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/ram` komandą](commands.md#ram).

#### `bukkit.command.rambar`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/rambar (Žaidėjas)` komandą](commands.md#rambar).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.restart`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/restart` komandą](commands.md#restart).

#### `bukkit.command.tps`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/tps` komandą](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/tpsbar (Žaidėjas)` komandą](commands.md#tpsbar).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `bukkit.command.timings`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/timings` komandą](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Norėdami sužinoti apie panašias funkcijas, apsilankykite [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/uptime` komandą](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia naudoti [`/gamemode (GameMode) (Žaidėjas)` komandą](commands.md#gamemode).

Įrašius leidimo pavadinimą pabaigoje `.other`, leidžia kitiems žaidėjams naudoti.

#### `paper.antixray.bypass`

- **Numatytasis**: `None`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Tai leidžia abiem pusėms patirti našumo pagerėjimą.

> Norėdami sužinoti daugiau apie X-Ray nustatymus, apsilankykite žemiau pateiktame puslapyje.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Numatytasis**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Numatytasis**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Numatytasis**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Numatytasis**: `None`

Leidžia naudoti [MiniMessage žymes](https://docs.advntr.dev/minimessage/format.html) kalvėje.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Numatytasis**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Numatytasis**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Numatytasis**: `None`

Išskiria žaidėją iš neaktyvių išmetimo sąrašo.

#### `purpur.debug.f3n`

- **Numatytasis**: `Pasaulio valdytojas`

Leidžia žaidėjui naudoti `F3 + N` klavišus keisti žaidimo režimą.

Veiks tik turint atitinkamą žaidimo režimo leidimą.

#### `purpur.drop.spawners`

- **Numatytasis**: `None`

Iškasant bloką, nustatytą konfigūracijoje, sukuria spawnerį.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Numatytasis**: `None`

Keičia enderlado dydį.

Į `(NumberString)` galima įvesti `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Numatytasis**: `None`

Leidžia totemui veikti, net jei jis yra inventoriuje.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Numatytasis**: `None`

Leidžia žaidėjui ignoruoti prisijungusių vartotojų limitą.

#### `purpur.mending_shift_click`

- **Numatytasis**: `None`

Leidžia žaidėjui remontuoti laikomą daiktą, kai jis `pasilenkia ir sąveikauja`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Numatytasis**: `None`

Leidžia žaidėjui įdiegti spawnerius.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Numatytasis**: `None`

Leidžia žaidėjui iškart teleportuotis, kai jis naudoja Nether portalą.

#### `purpur.sign.color`

- **Numatytasis**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Numatytasis**: `None`

Leidžiama naudoti kodavimo simbolį `(&o)` ant ženklelio.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Numatytasis**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Numatytasis**: `None`

Leidžiama žaidėjui su švyturėliu `sąveikauti` ir išvengti TNT sprogimo.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Suteikiamos numatomosios teisės

#### `plazma.bypass.ncr-require`

- **Numatytasis**: `None`

Leidžiama žaidėjui prisijungti neturint įdiegto [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) modifikacijos.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operatorius.

[^2]: Pavyzdys: `ender_dragon`
