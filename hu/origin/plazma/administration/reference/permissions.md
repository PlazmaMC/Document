---
description: Ismerje meg a Plazma engedélyeit.
---

# 🛡️ Engedély

Jogosultság egy egyszerű biztonsági eszköz, amely beállítja a szerveren belüli játékosok közötti interakció lehetőségeit.

A jogosultságok megfelelő kihasználásához és könnyű módosításához használni kell a [LuckPerms](https://luckperms.net) vagy hasonló bővítményeket.

***

## Alap jogosultság rendszer megértése <a href="#id-1" id="id-1"></a>

A Minecraft alapvető adminisztrációs jogosultság csoportokat biztosít.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Játékos**\
   Általában minden játékosnak rendelkezésére álló jogosultság csoport.
2. **Mediátor**\
   Figyelmen kívül hagyhatja a spawn védelmet.
3. **Világkezelő**\
   Minden világkezeléshez kapcsolódó parancsokat és parancsblokkokat használhat.\
   Ez az alapértelmezett jogosultság csoport a datapackokhoz és parancsblokkokhoz.
4. **Adminisztrátor**\
   Minden játékossal kapcsolatos parancsokat használhat.
5. **Főadminisztrátor**\
   Minden szerverkezeléshez kapcsolódó parancsot használhat.\
   Ez az alapértelmezett jogosultság csoport a konzolhoz és az adminisztrátorokhoz.

***

## Jogosultságok beállítása <a href="#id-2" id="id-2"></a>

***

## Összes jogosultság <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Alapértelmezett**: `None`

Engedélyezi a játékosoknak, hogy lehajolva és interakcióval felszálljanak az entitásra.

Ha felszáll az entitásra, akkor a `mozgás billentyűkkel` irányíthatja az entitás mozgását, és a `ugrás billentyűvel` ugorhat vagy repülhet.

A `(Namespaced Key)` helyére az entitás [Namespaced ID](#user-content-fn-2)[^2] kerül.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Alapértelmezett**: `None`

Engedélyezi a játékosoknak, hogy az entitáson ülve használhassák az entitás speciális képességeit.

Nem minden entitás speciális képessége használható. Az összes elérhető speciális képességet az alábbiakban találja.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Kérjük, ossza meg az ötleteit a [Plazma Discord](https://plazmamc.org/discord) vagy a [GitHub Beszélgetések](https://github.com/PlazmaMC/PlazmaBukkit/discussions) oldalon!
{% endhint %}

<details>

<összefoglalás>Elérhető speciális képességek megtekintése</összefoglalás>

- **`crepper`**\
  Ha megnyomja az `ugrás gombot`, akkor felrobban.\
  Ha a játékos rendelkezik az `allow.powered.creeper` jogosultsággal, akkor tartsa lenyomva az `ugrás gombot` a töltéshez.
- **`dolphin`**\
  Ha megnyomja az `ugrás gombot`, akkor úszik.
- **`phantom`**\
  Ha megnyomja az `ugrás gombot`, akkor tüzet lövöldöz.
- **`wither`**\
  Ha `kölcsönhatásba lép`, akkor wither fejet lő ki.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/compass` parancs](commands.md#compass) használatát.

#### `bukkit.command.credits`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/credits (Játékos)` parancs](commands.md#credits) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.demo`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/demo (Játékos)` parancs](commands.md#demo) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.ping`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/ping (Játékos)` parancs](commands.md#ping) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.ram`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/ram` parancs](commands.md#ram) használatát.

#### `bukkit.command.rambar`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/rambar (Játékos)` parancs](commands.md#rambar) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.restart`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/restart` parancs](commands.md#restart) használatát.

#### `bukkit.command.tps`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/tps` parancs](commands.md#tps) használatát.

#### `bukkit.command.tpsbar`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/tpsbar (Játékos)` parancs](commands.md#tpsbar) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `bukkit.command.timings`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/timings` parancs](commands.md#timings) használatát.

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

További hasonló parancsokért látogasson el a [Spark](https://spark.lucko.me/docs/Command-Usage) oldalra.
{% endhint %}

#### `bukkit.command.uptime`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/uptime` parancs](commands.md#uptime) használatát.

#### `minecraft.command.gamemode.(GameMode)`

- **Alapértelmezett**: `Világkezelő`

Engedélyezi a [`/gamemode (GameMode) (Játékos)` parancs](commands.md#gamemode) használatát.

Ha a jogosultság után `.other`-t ír, akkor más játékosok számára is engedélyezi a használatát.

#### `paper.antixray.bypass`

- **Alapértelmezett**: `None`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Ezzel mindkét fél javulást tapasztalhat.

> Az X-Ray beállításokról további információért látogasson el az alábbi oldalra.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Alapértelmezett**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Alapértelmezett**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Alapértelmezett**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Alapértelmezett**: `None`

Lehetővé teszi a kovácsoló asztalon a [MiniMessage címkék](https://docs.advntr.dev/minimessage/format.html) használatát.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Alapértelmezett**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Alapértelmezett**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Alapértelmezett**: `None`

Kizárja a játékost az inaktív állapotból történő kirúgásból.

#### `purpur.debug.f3n`

- **Alapértelmezett**: `Világkezelő`

Lehetővé teszi a játékos számára, hogy az `F3 + N` billentyűkombinációval változtassa a játék módot.

Csak akkor működik, ha nincs jogosultsága a megfelelő játékmódhoz.

#### `purpur.drop.spawners`

- **Alapértelmezett**: `None`

Ha az előre beállított tárggyal bányászik spawner blokkot, akkor a spawner blokkot elejti.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Alapértelmezett**: `None`

Megváltoztatja az ender láda méretét.

A `(NumberString)` helyére `one`, `two`, `three`, `four`, `five`, `six` írható.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Alapértelmezett**: `None`

Lehetővé teszi a visszatérő totem működését az inventáriumban.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Alapértelmezett**: `None`

A játékosnak engedélyezve van, hogy figyelmen kívül hagyja a csatlakozók számának korlátozását.

#### `purpur.mending_shift_click`

- **Alapértelmezett**: `None`

A játékosnak lehetősége van az `együttműködés lehajlására`, hogy megjavítsa a kezében lévő tárgyat.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Alapértelmezett**: `None`

A játékosnak engedélyezve van a mobgenerálók telepítése.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Alapértelmezett**: `None`

A játékosnak lehetősége van azonnal átugrani, amikor használja a Nether portált.

#### `purpur.sign.color`

- **Alapértelmezett**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Alapértelmezett**: `None`

표지판에 난독화 kód`(&o)` használatát engedélyezi.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.jel.stílus`

- **Alapértelmezett**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.hatástalanít`

- **Alapértelmezett**: `None`

A játékosok `kölcsönhatás` használatával megakadályozhatják a TNT robbanását.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Biztosított jog

#### `plazma.mellőzés.ncr-szükség`

- **Alapértelmezett**: `None`

A játékosoknak lehetőségük van a [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) módot telepítetlenül is csatlakozni.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operátor.

[^2]: Például: `ender_dragon`
