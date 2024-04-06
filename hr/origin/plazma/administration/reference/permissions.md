---
description: Saznajte više o ovlastima Plazme.
---

# 🛡️ Ovlasti

Dozvole su jednostavni sigurnosni alat koji omogućuje igračima na poslužitelju međusobno djelovanje.

Za pravilno korištenje i jednostavno uređivanje dozvola, trebate koristiti dodatke poput [LuckPerms](https://luckperms.net).

***

## Razumijevanje osnovnog sustava dozvola <a href="#id-1" id="id-1"></a>

Minecraft pruža osnovne administratorske skupine dozvola.

Možete postaviti dozvole za [administratora](#user-content-fn-1)[^1] i naredbeni blok te ih možete urediti u [konfiguracijama poslužitelja](configurations/property.md).

0. **Igrač**\
   Ovo je osnovna skupina dozvola koja se dodjeljuje svim igračima.
1. **Posrednik**\
   Može ignorirati zaštitu od spawnanja.
2. **Administrator svijeta**\
   Može koristiti sve naredbe i naredbene blokove povezane s upravljanjem svijetom.\
   Ovo je osnovna skupina dozvola koja se primjenjuje na pakete podataka i naredbene blokove.
3. **Administrator**\
   Može koristiti sve naredbe povezane s upravljanjem igračima.
4. **Glavni administrator**\
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

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `(Entity) > ridable` za funkcioniranje.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Osnovno**: `Nijedan`

Dopušta igračima da koriste posebne sposobnosti entiteta dok su na njima.

Nisu sve posebne sposobnosti svih entiteta dostupne. Pogledajte sve dostupne posebne sposobnosti u nastavku.

{% hint style="info" %}

**Imate li dobru ideju za posebne sposobnosti?**

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

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `(Entity) > ridable` za funkcioniranje.**

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

**Ova naredba je obustavljena.**

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

Ako je [X-Ray blokiran](../expert/xray.md), igračima s ovlaštenjem neće biti zamagljivanje blokova zaštite od X-Raya.

To omogućuje poboljšanje performansi za obje strane.

> Za upute o postavljanju X-Ray-a pogledajte dolje navedenu stranicu.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Osnovno**: `Nijedan`

{% hint style="warning" %}

Ovo ovlaštenje bit će promijenjeno u `plazma.bypass.watchdog` u verziji 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Osnovno**: `Nijedan`

Omogućuje korištenje [boja](https://minecraft.wiki/w/Formatting_codes#Color_codes) na kovčegu.

{% hint style="info" %}

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `anvil > allow-colors` za funkcioniranje.**

{% endhint %}

#### `purpur.anvil.format`

- **Osnovno**: `Nijedan`

Omogućuje korištenje [stilova](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na kovčegu.

{% hint style="info" %}

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `anvil > allow-colors` za funkcioniranje.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Osnovno**: `Nijedan`

Omogućuje korištenje [MiniMessage oznaka](https://docs.advntr.dev/minimessage/format.html) na kovčegu.

{% hint style="info" %}

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `anvil > allow-minimessages` za funkcioniranje.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Osnovno**: `Nijedan`

Omogućuje onemogućavanje `kurziva` pomoću stilskog koda `&r` na kovčegu.

{% hint style="info" %}

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `anvil > allow-colors` za funkcioniranje.**

{% endhint %}

#### `purpur.book.color.sign`

- **Osnovno**: `Nijedan`

Kada igrač potpiše knjigu, primjenjuju se [stilski kodovi](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

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

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `gameplay-mechanics > silk-touch` za funkcioniranje.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Osnovno**: `Nijedan`

Mijenja veličinu ender kovčega.

U `(NumberString)` možete unijeti `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `ender_chest > six-rows` i `ender_chest > use-permissions-for-rows` za funkcioniranje.**

{% endhint %}

#### `purpur.inventory_totem`

- **Osnovno**: `Nijedan`

Omogućuje funkcioniranje Totema besmrtnosti čak i ako je u inventaru.

{% hint style="info" %}

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `totem-of-undying-works-in-inventory` za funkcioniranje.**

{% endhint %}

#### `purpur.joinFullServer`

- **Osnovno**: `Nijedan`

Dopustite igraču da ignorira ograničenje broja posjetitelja.

#### `purpur.mending_shift_click`

- **Osnovno**: `Nijedan`

Dopustite igraču da popravi predmet koji drži kada se `poklekne i interagira`.

{% hint style="info" %}

**Morate omogućiti `shift-right-click-repairs-mending-points` u [Purpur konfiguracijama svijeta](configurations/purpur/world.md) da bi to funkcioniralo.**

{% endhint %}

#### `purpur.place.spawners`

- **Osnovno**: `Nijedan`

Dopustite igraču da postavi spawner.

{% hint style="info" %}

**[Purpur konfiguracije svijeta](configurations/purpur/world.md) moraju biti omogućene `gameplay-mechanics > silk-touch` za funkcioniranje.**

{% endhint %}

#### `purpur.portal.instant`

- **Osnovno**: `Nijedan`

Omogućite igraču trenutno teleportiranje kada koristi Nether portal.

#### `purpur.sign.color`

- **Osnovno**: `Nijedan`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting_codes#Color_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}

**[Purpur svijet konfiguracija](configurations/purpur/world.md) treba omogućiti `sign > allow-colors` da bi radilo.**

{% endhint %}

#### `purpur.sign.magic`

- **Osnovno**: `Nijedan`

Prijenosnici mogu koristiti kod za otežavanje čitanja `(&o)` na znakovima.

{% hint style="info" %}

**[Purpur svijet konfiguracija](configurations/purpur/world.md) treba omogućiti `sign > allow-colors` da bi radilo.**

{% endhint %}

#### `purpur.sign.style`

- **Osnovno**: `Nijedan`

Prijenosnici mogu koristiti [stilizacijske kodove `(&o isključeno)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na znakovima.

{% hint style="info" %}

**[Purpur svijet konfiguracija](configurations/purpur/world.md) treba omogućiti `sign > allow-colors` da bi radilo.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Osnovno**: `Nijedan`

Dopušta igračima da `međusobno djeluju` škarama kako bi spriječili TNT eksploziju.

{% hint style="info" %}

**[Konfiguracije Purpur svijeta](configurations/purpur/world.md) moraju imati `defuse-tnt-change` veći od `0.0` da bi radilo.**

{% endhint %}

### Planirana dozvola

#### `plazma.bypass.ncr-require`

- **Osnovno**: `Nijedan`

Dopušta igračima da se priključe čak i ako nemaju instaliran mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**[Konfiguracije Plazma svijeta](configurations/plazma/world.md) moraju imati omogućeno `no-chat-reports > require-install` da bi radilo.**

{% endhint %}

***

[^1]: Operator.

[^2]: Primjer: `ender_dragon`
