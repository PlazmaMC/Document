---
description: Saznajte više o ovlastima Plazme.
---

# 🛡️ Ovlasti

Dozvole su jednostavni sigurnosni alat koji omogućuje igračima na poslužitelju međusobno djelovanje.

Za pravilno korištenje i jednostavno uređivanje dozvola, trebate koristiti dodatke poput [LuckPerms](https://luckperms.net).

***

## Razumijevanje osnovnog sustava dozvola <a href="#id-1" id="id-1"></a>

Minecraft pruža osnovne administratorske skupine dozvola.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Igrač**\
   Ovo je osnovna skupina dozvola koja se dodjeljuje svim igračima.
2. **Posrednik**\
   Može ignorirati zaštitu od spawnanja.
3. **Administrator svijeta**\
   Može koristiti sve naredbe i naredbene blokove povezane s upravljanjem svijetom.\
   Ovo je osnovna skupina dozvola koja se primjenjuje na pakete podataka i naredbene blokove.
4. **Administrator**\
   Može koristiti sve naredbe povezane s upravljanjem igračima.
5. **Glavni administrator**\
   Može koristiti sve naredbe uključujući upravljanje poslužiteljem.\
   Ovo je osnovna skupina dozvola koja se primjenjuje na konzolu i administratore.

***

## Postavljanje dozvola <a href="#id-2" id="id-2"></a>

***

## Sve dozvole <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Osnovno**: `Nijedan`

Dopušta igračima da se sagnu i međudjeluju s entitetom kako bi se mogli voziti na entitetu.

Kada se voze entitetom, mogu upravljati kretanjem entiteta pomoću `tipki za kretanje` i skakati ili letjeti pomoću `tipke za skok`.

U `(Namespaced Key)` upisuje se [Namespaced ID](#user-content-fn-2)[^2] entiteta.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Osnovno**: `Nijedan`

Dopušta igračima da koriste posebne sposobnosti entiteta dok su na njima.

Nisu sve posebne sposobnosti svih entiteta dostupne. Pogledajte sve dostupne posebne sposobnosti u nastavku.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Molimo podijelite svoje ideje na [Plazma Discord](https://plazmamc.org/discord) ili [GitHub raspravama](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Pogledajte trenutno dostupne posebne sposobnosti</summary>

- **`crepper`**\
  Prilikom pritiska `tipke za skok` eksplodira.\
  Ako igrač ima dozvolu `allow.powered.creeper`, može držati `tipku za skok` za punjenje.
- **`dolphin`**\
  Prilikom pritiska `tipke za skok` napada brzinom.
- **`phantom`**\
  Prilikom pritiska `tipke za skok` ispaljuje plamen.
- **`wither`**\
  Kada se `međudjeluje`, ispaljuje glavu Withera.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/compass` naredbe](commands.md#compass).

#### `bukkit.command.credits`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/credits (Igrač)` naredbe](commands.md#credits).

Dodavanjem `.other` iza imena dozvole omogućuje se korištenje drugim igračima.

#### `bukkit.command.demo`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/demo (Igrač)` naredbe](commands.md#demo).

Dodavanjem `.other` iza imena dozvole omogućuje se korištenje drugim igračima.

#### `bukkit.command.ping`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/ping (Igrač)` naredbe](commands.md#ping).

Dodavanjem `.other` iza imena dozvole omogućuje se korištenje drugim igračima.

#### `bukkit.command.ram`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/ram` naredbe](commands.md#ram).

#### `bukkit.command.rambar`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/rambar (Igrač)` naredbe](commands.md#rambar).

Dodavanjem `.other` iza imena dozvole omogućuje se korištenje drugim igračima.

#### `bukkit.command.restart`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/restart` naredbe](commands.md#restart).

#### `bukkit.command.tps`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/tps` naredbe](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/tpsbar (Igrač)` naredbe](commands.md#tpsbar).

Dodavanjem `.other` iza imena dozvole omogućuje se korištenje drugim igračima.

#### `bukkit.command.timings`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/timings` naredbe](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Za slične funkcionalnosti pogledajte [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/uptime` naredbe](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Osnovno**: `Administrator svijeta`

Dopušta korištenje [`/gamemode (GameMode) (Igrač)` naredbe](commands.md#gamemode).

Dodavanjem `.other` iza imena dozvole omogućuje se korištenje drugim igračima.

#### `paper.antixray.bypass`

- **Osnovno**: `Nijedan`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

To omogućuje poboljšanje performansi za obje strane.

> Za upute o postavljanju X-Ray-a pogledajte dolje navedenu stranicu.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Osnovno**: `Nijedan`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Osnovno**: `Nijedan`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Osnovno**: `Nijedan`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Osnovno**: `Nijedan`

Omogućuje korištenje [MiniMessage oznaka](https://docs.advntr.dev/minimessage/format.html) na kovčegu.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Osnovno**: `Nijedan`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Osnovno**: `Nijedan`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Osnovno**: `Nijedan`

Igrači se izuzimaju iz izbacivanja zbog neaktivnosti.

#### `purpur.debug.f3n`

- **Osnovno**: `Administrator svijeta`

Omogućuje igračima promjenu načina igre pomoću tipki `F3 + N`.

Nije moguće raditi ako nemate dozvolu za taj način igre.

#### `purpur.drop.spawners`

- **Osnovno**: `Nijedan`

Kada iskopate spawner blok s postavkama iz konfiguracije, spawner će pasti na tlo.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Osnovno**: `Nijedan`

Mijenja veličinu ender kovčega.

U `(NumberString)` možete unijeti `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Osnovno**: `Nijedan`

Omogućuje funkcioniranje Totema besmrtnosti čak i ako je u inventaru.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Osnovno**: `Nijedan`

Dopustite igraču da ignorira ograničenje broja posjetitelja.

#### `purpur.mending_shift_click`

- **Osnovno**: `Nijedan`

Dopustite igraču da popravi predmet koji drži kada se `poklekne i interagira`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Osnovno**: `Nijedan`

Dopustite igraču da postavi spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Osnovno**: `Nijedan`

Omogućite igraču trenutno teleportiranje kada koristi Nether portal.

#### `purpur.sign.color`

- **Osnovno**: `Nijedan`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Osnovno**: `Nijedan`

Prijenosnici mogu koristiti kod za otežavanje čitanja `(&o)` na znakovima.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Osnovno**: `Nijedan`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Osnovno**: `Nijedan`

Dopušta igračima da `međusobno djeluju` škarama kako bi spriječili TNT eksploziju.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Planirana dozvola

#### `plazma.bypass.ncr-require`

- **Osnovno**: `Nijedan`

Dopušta igračima da se priključe čak i ako nemaju instaliran mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Primjer: `ender_dragon`
