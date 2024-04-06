---
description: Consulta els permisos de Plazma.
---

# 🛡️ Permisos

Els permisos són eines de seguretat senzilles que defineixen l'àmbit en què els jugadors del servidor poden interactuar entre ells.

Per utilitzar i modificar els permisos de manera eficaç, cal utilitzar complements com [LuckPerms](https://luckperms.net).

***

## Entenent el sistema de permisos per defecte <a href="#id-1" id="id-1"></a>

A Minecraft es proporcionen grups de permisos de gestió bàsics.

Es poden establir permisos per a **operadors**[^1] i blocs de comandes, i es poden modificar a les [proprietats del servidor](configurations/property.md).

0. **Jugador**\
   És el grup de permisos que es dóna normalment a tots els jugadors.
1. **Àrbitre**\
   Pot ignorar la protecció de spawn.
2. **Administrador del món**\
   Pot utilitzar totes les ordres i blocs de comandes relacionats amb la gestió del món.\
   És el grup de permisos per defecte aplicat als datapacks i blocs de comandes.
3. **Administrador**\
   Pot utilitzar totes les ordres relacionades amb la gestió dels jugadors.
4. **Superadministrador**\
   Pot utilitzar totes les ordres relacionades amb la gestió del servidor, inclosa la consola.\
   És el grup de permisos per defecte aplicat a la consola i als operadors.

***

## Configuració de permisos <a href="#id-2" id="id-2"></a>

***

## Permisos globals <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Clau amb espai de noms)`

- **Per defecte**: `Cap`

Permet als jugadors agenollar-se i interactuar amb l'entitat per pujar-hi.

En pujar a l'entitat, es pot controlar el seu moviment amb les tecles de **moviment** i saltar o volar amb la tecla de **salt**.

A la **clau amb espai de noms** s'hi introdueix la [ID amb espai de noms](#user-content-fn-2)[^2] de l'entitat.

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si se activa `(Entity) > montable`.**

{% endhint %}

#### `allow.special.(Clau amb espai de noms)`

- **Per defecte**: `Cap`

Permet al jugador utilitzar les habilitats especials de l'entitat en què està muntat.

No totes les entitats tenen habilitats especials disponibles. Consulteu les habilitats especials disponibles a continuació.

{% hint style="info" %}

**Teniu alguna idea per a una habilitat especial?**

Si teniu una idea, feu-la saber al [Discord de Plazma](https://plazmamc.org/discord) o a les [Discussions de GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Veure les habilitats especials disponibles actualment</summary>

- **`crepper`**\
  Al prémer la tecla de salt, explota.\
  Si el jugador té el permís `allow.powered.creeper`, pot carregar la explosió mantenint premuda la tecla de salt.
- **`dolphin`**\
  Al prémer la tecla de salt, carrega.
- **`phantom`**\
  Al prémer la tecla de salt, llança flames.
- **`wither`**\
  En interactuar, llança caps de Wither.

</details>

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si se activa `(Entity) > montable`.**

{% endhint %}

#### `bukkit.command.compass`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/credits (Jugador)`](commands.md#credits).

Introduir `.altre` al final del permís permet que altres jugadors l'utilitzin.

#### `bukkit.command.demo`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/demo (Jugador)`](commands.md#demo).

Introduir `.altre` al final del permís permet que altres jugadors l'utilitzin.

#### `bukkit.command.ping`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/ping (Jugador)`](commands.md#ping).

Introduir `.altre` al final del permís permet que altres jugadors l'utilitzin.

#### `bukkit.command.ram`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/rambar (Jugador)`](commands.md#rambar).

Introduir `.altre` al final del permís permet que altres jugadors l'utilitzin.

#### `bukkit.command.restart`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/tpsbar (Jugador)`](commands.md#tpsbar).

Introduir `.altre` al final del permís permet que altres jugadors l'utilitzin.

#### `bukkit.command.timings`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Aquesta comanda ha estat desactivada.**

Per obtenir informació sobre comandes similars, consulteu [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(Mode de joc)`

- **Per defecte**: `Administrador del món`

Permet l'ús de la comanda `/gamemode (Mode de joc) (Jugador)`.

Introduir `.altre` al final del permís permet que altres jugadors l'utilitzin.

#### `paper.antixray.bypass`

- **Per defecte**: `Cap`

Si està activat el bloqueig de X-Ray, els jugadors amb aquest permís no rebran la protecció de blocs X-Ray.

Això millora el rendiment per a tots dos.

> Per obtenir informació sobre com configurar X-Ray, consulteu la següent pàgina.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Per defecte**: `Cap`

{% hint style="warning" %}

Aquest permís es canviarà a `plazma.bypass.watchdog` a la versió 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Per defecte**: `Cap`

Permet l'ús de codis de color en l'enclusa. Consulteu [codis de color](https://minecraft.wiki/w/Formatting_codes#Color_codes).

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si s'activa `anvil > permet-colors`.**

{% endhint %}

#### `purpur.anvil.format`

- **Per defecte**: `Cap`

Permet l'ús de codis d'estil en l'enclusa. Consulteu [codis d'estil](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si s'activa `anvil > permet-colors`.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Per defecte**: `Cap`

Permet l'ús de etiquetes MiniMessage a l'enclusa. Consulteu [MiniMessage Tags](https://docs.advntr.dev/minimessage/format.html).

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si s'activa `anvil > permet-minimessages`.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Per defecte**: `Cap`

Permet desactivar la `cursiva` en l'enclusa amb el codi d'estil `&r`. Consulteu [codis d'estil](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si s'activa `anvil > permet-colors`.**

{% endhint %}

#### `purpur.book.color.sign`

- **Per defecte**: `Cap`

Aplica codis d'estil quan un jugador signa un llibre. Consulteu [codis d'estil](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Per defecte**: `Cap`

Exclou els jugadors de ser expulsats per inactivitat.

#### `purpur.debug.f3n`

- **Per defecte**: `Administrador del món`

Permet als jugadors canviar el mode de joc amb la tecla `F3 + N`.

Només funciona si tenen el permís per a aquest mode de joc.

#### `purpur.drop.spawners`

- **Per defecte**: `Cap`

Quan es mina un bloc de spawner amb l'objecte configurat, el bloc de spawner cau.

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si s'activa `gameplay-mechanics > silk-touch`.**

{% endhint %}

#### `purpur.enderchest.rows.(Número de fila)`

- **Per defecte**: `Cap`

Canvia la mida de l'endrinyera.

Es pot introduir `one`, `two`, `three`, `four`, `five`, `six` a `(Número de fila)`.

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si s'activa `ender_chest > six-rows` i `ender_chest > use-permissions-for-rows`.**

{% endhint %}

#### `purpur.inventory_totem`

- **Per defecte**: `Cap`

Permet que el totem d'immortalitat funcioni quan es troba a l'inventari.

{% hint style="info" %}

**Cal activar `totem-of-undying-works-in-inventory` a la **[configuracions del món de Purpur](configurations/purpur/world.md)** perquè funcioni.**

{% endhint %}

#### `purpur.joinFullServer`

- **Per defecte**: `Cap`

Permet al jugador ignorar el límit de jugadors connectats.

#### `purpur.mending_shift_click`

- **Per defecte**: `Cap`

Permet al jugador reparar l'objecte que té a les mans quan fa `agatxat i interactua`.

{% hint style="info" %}

**Cal activar `shift-right-click-repairs-mending-points` a la **[configuracions del món de Purpur](configurations/purpur/world.md)** perquè funcioni.**

{% endhint %}

#### `purpur.place.spawners`

- **Per defecte**: `Cap`

Permet al jugador instal·lar spawners.

{% hint style="info" %}

**En el [configuracions del món Purpur](configurations/purpur/world.md), només funciona si s'activa `gameplay-mechanics > silk-touch`.**

{% endhint %}

#### `purpur.portal.instant`

- **Per defecte**: `Cap`

Permet al jugador teleportar-se immediatament quan utilitza un portal al Nether.

#### `purpur.sign.color`

- **Per defecte**: `Cap`

Permet utilitzar codis de **color** en els rètols. (https://minecraft.wiki/w/Formatting_codes#Color_codes)

{% hint style="info" %}

**Cal activar `sign > allow-colors` a la **[configuracions del món de Purpur](configurations/purpur/world.md)** perquè funcioni.**

{% endhint %}

#### `purpur.sign.magic`

- **Per defecte**: `Cap`

Permet utilitzar el codi d'encriptació `(&o)` als rètols.

{% hint style="info" %}

**Cal activar `sign > allow-colors` a la **[configuracions del món de Purpur](configurations/purpur/world.md)** perquè funcioni.**

{% endhint %}

#### `purpur.sign.style`

- **Per defecte**: `Cap`

Permet utilitzar codis d'estil en els rètols, excepte `(&o)`. (https://minecraft.wiki/w/Formatting_codes#Formatting_codes)

{% hint style="info" %}

**Cal activar `sign > allow-colors` a la **[configuracions del món de Purpur](configurations/purpur/world.md)** perquè funcioni.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Per defecte**: `Cap`

Permet al jugador evitar l'explosió de TNT interaccionant amb ella amb les tisores.

{% hint style="info" %}

**Cal que `defuse-tnt-change` a la **[configuracions del món de Purpur](configurations/purpur/world.md)** sigui de `0.0` o superior perquè funcioni.**

{% endhint %}

### Permisos previstos

#### `plazma.bypass.ncr-require`

- **Per defecte**: `Cap`

Permet al jugador connectar-se sense tenir instal·lat el mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**Cal activar `no-chat-reports > require-install` a la **[configuracions del món de Plazma](configurations/plazma/world.md)** perquè funcioni.**

{% endhint %}

***

[^1]: Operador.

[^2]: Per exemple: `ender_dragon`
