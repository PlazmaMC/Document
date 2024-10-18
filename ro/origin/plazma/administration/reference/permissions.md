---
description: Aflați mai multe despre permisiunile Plazma.
---

# 🛡️ Permisiuni

Permisiunea este o unealtă simplă de securitate care stabilește domeniul în care jucătorii de pe server pot interacționa între ei.

Pentru a utiliza și modifica permisiunile în mod eficient, trebuie să folosiți plugin-uri precum [LuckPerms](https://luckperms.net).

***

## Înțelegerea sistemului de permisiuni de bază <a href="#id-1" id="id-1"></a>

În Minecraft, sunt furnizate grupuri de permisiuni de administrare de bază.

Puteți seta permisiunile pentru [operatori](#user-content-fn-1)[^1] și blocuri de comandă, acestea putând fi modificate în [configurările serverului](configurations/property.md).

0. **Jucător**\
   Este grupul de permisiuni acordat de obicei tuturor jucătorilor.
1. **Mediator**\
   Poate ignora protecția de spawn.
2. **Administrator de lume**\
   Poate folosi toate comenzile și blocurile de comandă legate de administrarea lumii.\
   Este grupul de permisiuni implicit pentru datapack-uri și blocuri de comandă.
3. **Administrator**\
   Poate folosi toate comenzile legate de administrarea jucătorilor.
4. **Superadministrator**\
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

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `(Entity) > ridable` este activat.**

{% endhint %}

#### `allow.special.(Cheie spațiată)`

- **Implicit**: `None`

Permite jucătorului să folosească abilitățile speciale ale entității când este călare pe aceasta.

Nu toate entitățile au abilități speciale disponibile. Consultați lista completă a abilităților speciale disponibile mai jos.

{% hint style="info" %}

**Aveți idei bune pentru abilități speciale?**

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

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `(Entity) > ridable` este activat.**

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

**Această comandă a fost întreruptă.**

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

Dacă este activată [Blocarea X-Ray](../expert/xray.md), nu se va cripta blocurile X-Ray pentru jucătorii cu permisiunea înregistrată.

Aceasta va îmbunătăți performanța pentru ambele părți.

> Pentru informații despre setarea X-Ray, consultați pagina de mai jos.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Implicit**: `None`

{% hint style="warning" %}

Această permisiune va fi schimbată în `plazma.bypass.watchdog` în versiunea 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Implicit**: `None`

Permite utilizarea codurilor de [culoare](https://minecraft.wiki/w/Formatting_codes#Color_codes) pe nicovală.

{% hint style="info" %}

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `anvil > allow-colors` este activat.**

{% endhint %}

#### `purpur.anvil.format`

- **Implicit**: `None`

Permite utilizarea codurilor de [stil](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) pe nicovală.

{% hint style="info" %}

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `anvil > allow-colors` este activat.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Implicit**: `None`

Permite utilizarea tagurilor [MiniMessage](https://docs.advntr.dev/minimessage/format.html) pe nicovală.

{% hint style="info" %}

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `anvil > allow-minimessages` este activat.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Implicit**: `None`

Permite dezactivarea `înclinării textului` pe nicovală folosind codul de stilare `&r`.

{% hint style="info" %}

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `anvil > allow-colors` este activat.**

{% endhint %}

#### `purpur.book.color.sign`

- **Implicit**: `None`

Când un jucător semnează o carte, se aplică [codurile de stil](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

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

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `gameplay-mechanics > silk-touch` este activat.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Implicit**: `None`

Schimbă dimensiunea cufărului ender.

În `(NumberString)` puteți introduce `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `ender_chest > six-rows` și `ender_chest > use-permissions-for-rows` sunt activate.**

{% endhint %}

#### `purpur.inventory_totem`

- **Implicit**: `None`

Permite funcționarea totemului de nemurire chiar dacă este în inventar.

{% hint style="info" %}

**În [Configurările lumii Purpur](configurations/purpur/world.md) trebuie să activați `totem-of-undying-works-in-inventory` pentru a funcționa.**

{% endhint %}

#### `purpur.joinFullServer`

- **Implicit**: `None`

Permite jucătorilor să ignore limita de conectare.

#### `purpur.mending_shift_click`

- **Implicit**: `None`

Permite jucătorilor să-și repare obiectele ținând `apăsat Shift` și făcând clic.

{% hint style="info" %}

**În [Configurările lumii Purpur](configurations/purpur/world.md) trebuie să activați `shift-right-click-repairs-mending-points` pentru a funcționa.**

{% endhint %}

#### `purpur.place.spawners`

- **Implicit**: `None`

Permite jucătorilor să instaleze spawnere.

{% hint style="info" %}

**În [configurațiile lume Purpur](configurations/purpur/world.md), funcționează doar dacă `gameplay-mechanics > silk-touch` este activat.**

{% endhint %}

#### `purpur.portal.instant`

- **Implicit**: `None`

Permite jucătorilor să se teleporteze instantaneu când folosesc portalul Nether.

#### `purpur.sign.color`

- **Implicit**: `None`

Permite utilizarea [codurilor de culoare](https://minecraft.wiki/w/Formatting_codes#Color_codes) pe panouri.

{% hint style="info" %}

**În [Configurările lumii Purpur](configurations/purpur/world.md) trebuie să activați `sign > allow-colors` pentru a funcționa.**

{% endhint %}

#### `purpur.sign.magic`

- **Implicit**: `None`

Permite utilizarea codului de iluzie `(&o)` pe panouri.

{% hint style="info" %}

**În [Configurările lumii Purpur](configurations/purpur/world.md) trebuie să activați `sign > allow-colors` pentru a funcționa.**

{% endhint %}

#### `purpur.sign.style`

- **Implicit**: `None`

Permite utilizarea [codurilor de stil `(&o exclus)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) pe panouri.

{% hint style="info" %}

**În [Configurările lumii Purpur](configurations/purpur/world.md) trebuie să activați `sign > allow-colors` pentru a funcționa.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Implicit**: `None`

Permite jucătorilor să prevină explozia TNT-ului interacționând cu ea cu foarfeca.

{% hint style="info" %}

**În [Configurările lumii Purpur](configurations/purpur/world.md) `defuse-tnt-change` trebuie să fie mai mare sau egal cu `0.0` pentru a funcționa.**

{% endhint %}

### Permisiuni planificate

#### `plazma.bypass.ncr-require`

- **Implicit**: `None`

Permite jucătorilor să se conecteze fără a avea modul [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) instalat.

{% hint style="info" %}

**În [Configurările lumii Plazma](configurations/plazma/world.md) trebuie să activați `no-chat-reports > require-install` pentru a funcționa.**

{% endhint %}

***

[^1]: Operator.

[^2]: Exemplu: `ender_dragon`
