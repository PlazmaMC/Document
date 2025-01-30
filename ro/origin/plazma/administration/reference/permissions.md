---
description: Aflați mai multe despre permisiunile Plazma.
---

# 🛡️ Permisiuni

Permisiunea este o unealtă simplă de securitate care stabilește domeniul în care jucătorii de pe server pot interacționa între ei.

Pentru a utiliza și modifica permisiunile în mod eficient, trebuie să folosiți plugin-uri precum [LuckPerms](https://luckperms.net).

***

## Înțelegerea sistemului de permisiuni de bază <a href="#id-1" id="id-1"></a>

În Minecraft, sunt furnizate grupuri de permisiuni de administrare de bază.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Jucător**\
   Este grupul de permisiuni acordat de obicei tuturor jucătorilor.
2. **Mediator**\
   Poate ignora protecția de spawn.
3. **Administrator de lume**\
   Poate folosi toate comenzile și blocurile de comandă legate de administrarea lumii.\
   Este grupul de permisiuni implicit pentru datapack-uri și blocuri de comandă.
4. **Administrator**\
   Poate folosi toate comenzile legate de administrarea jucătorilor.
5. **Superadministrator**\
   Poate folosi toate comenzile, inclusiv cele de administrare a serverului.\
   Este grupul de permisiuni implicit pentru consolă și operatori.

***

## Setarea permisiunilor <a href="#id-2" id="id-2"></a>

***

## Permisiuni complete <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Cheia în spațiul de nume)`

- **Implicit**: `None`

Permite jucătorilor să se așeze și să interacționeze cu entitățile pentru a le călări.

Când călărește o entitate, jucătorul poate controla mișcarea entității cu tastele de deplasare și poate sări sau zbura cu tasta de sărit.

În `(Cheia în spațiul de nume)` se introduce [ID-ul în spațiul de nume](#user-content-fn-2)[^2] al entității.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Cheie spațiată)`

- **Implicit**: `None`

Permite jucătorului să folosească abilitățile speciale ale entității când este călare pe aceasta.

Nu toate entitățile au abilități speciale disponibile. Consultați lista completă a abilităților speciale disponibile mai jos.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Vă rugăm să postați ideile pe [Plazma Discord](https://plazmamc.org/discord) sau [Discuțiile GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Vizualizați abilitățile speciale disponibile</summary>

- **`crepper`**\
  Dacă apăsați tasta `săritură`, va exploda.\
  Dacă jucătorul are permisiunea `allow.powered.creeper`, poate încărca apăsând tasta `săritură`.
- **`dolphin`**\
  Dacă apăsați tasta `săritură`, va înota rapid.
- **`phantom`**\
  Dacă apăsați tasta `săritură`, va trage cu flăcări.
- **`wither`**\
  Interacționând, va trage cu capul de wither.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/credits (Jucător)`](commands.md#credits).

Introducând `.other` după numele permisiunii, permite utilizarea pentru alți jucători.

#### `bukkit.command.demo`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/demo (Jucător)`](commands.md#demo).

Introducând `.other` după numele permisiunii, permite utilizarea pentru alți jucători.

#### `bukkit.command.ping`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/ping (Jucător)`](commands.md#ping).

Introducând `.other` după numele permisiunii, permite utilizarea pentru alți jucători.

#### `bukkit.command.ram`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/rambar (Jucător)`](commands.md#rambar).

Introducând `.other` după numele permisiunii, permite utilizarea pentru alți jucători.

#### `bukkit.command.restart`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/tpsbar (Jucător)`](commands.md#tpsbar).

Introducând `.other` după numele permisiunii, permite utilizarea pentru alți jucători.

#### `bukkit.command.timings`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/timings`](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Pentru a afla despre comenzile similare, consultați [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Încorporat**: `Administrator de lume`

Permite utilizarea comenzii `/gamemode (GameMode) (Jucător)`.

Introducând `.other` după numele permisiunii, permite utilizarea pentru alți jucători.

#### `paper.antixray.bypass`

- **Implicit**: `None`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Aceasta va îmbunătăți performanța pentru ambele părți.

> Pentru informații despre setarea X-Ray, consultați pagina de mai jos.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Implicit**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Implicit**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Implicit**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Implicit**: `None`

Permite utilizarea tagurilor [MiniMessage](https://docs.advntr.dev/minimessage/format.html) pe nicovală.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Implicit**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Implicit**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Implicit**: `None`

Exclude jucătorul de la a fi eliminat din cauza inactivității.

#### `purpur.debug.f3n`

- **Încorporat**: `Administrator de lume`

Permite jucătorului să schimbe modul de joc folosind tasta `F3 + N`.

Funcționează doar dacă nu are permisiunea pentru acel mod de joc.

#### `purpur.drop.spawners`

- **Implicit**: `None`

Dacă săpați un bloc de generator cu un element configurat, va elibera blocul generator.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Implicit**: `None`

Schimbă dimensiunea cufărului ender.

În `(NumberString)` puteți introduce `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Implicit**: `None`

Permite funcționarea totemului de nemurire chiar dacă este în inventar.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Implicit**: `None`

Permite jucătorilor să ignore limita de conectare.

#### `purpur.mending_shift_click`

- **Implicit**: `None`

Permite jucătorilor să-și repare obiectele ținând `apăsat Shift` și făcând clic.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Implicit**: `None`

Permite jucătorilor să instaleze spawnere.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Implicit**: `None`

Permite jucătorilor să se teleporteze instantaneu când folosesc portalul Nether.

#### `purpur.sign.color`

- **Implicit**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Implicit**: `None`

Permite utilizarea codului de iluzie `(&o)` pe panouri.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Implicit**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Implicit**: `None`

Permite jucătorilor să prevină explozia TNT-ului interacționând cu ea cu foarfeca.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Permisiuni planificate

#### `plazma.bypass.ncr-require`

- **Implicit**: `None`

Permite jucătorilor să se conecteze fără a avea modul [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) instalat.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Exemplu: `ender_dragon`
