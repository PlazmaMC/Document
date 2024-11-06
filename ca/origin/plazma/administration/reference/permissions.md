---
description: Consulta els permisos de Plazma.
---

# 🛡️ Permisos

Els permisos són eines de seguretat senzilles que defineixen l'àmbit en què els jugadors del servidor poden interactuar entre ells.

Per utilitzar i modificar els permisos de manera eficaç, cal utilitzar complements com [LuckPerms](https://luckperms.net).

***

## Entenent el sistema de permisos per defecte <a href="#id-1" id="id-1"></a>

A Minecraft es proporcionen grups de permisos de gestió bàsics.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Jugador**\
   És el grup de permisos que es dóna normalment a tots els jugadors.
2. **Àrbitre**\
   Pot ignorar la protecció de spawn.
3. **Administrador del món**\
   Pot utilitzar totes les ordres i blocs de comandes relacionats amb la gestió del món.\
   És el grup de permisos per defecte aplicat als datapacks i blocs de comandes.
4. **Administrador**\
   Pot utilitzar totes les ordres relacionades amb la gestió dels jugadors.
5. **Superadministrador**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Clau amb espai de noms)`

- **Per defecte**: `Cap`

Permet al jugador utilitzar les habilitats especials de l'entitat en què està muntat.

No totes les entitats tenen habilitats especials disponibles. Consulteu les habilitats especials disponibles a continuació.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Això millora el rendiment per a tots dos.

> Per obtenir informació sobre com configurar X-Ray, consulteu la següent pàgina.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Per defecte**: `Cap`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Per defecte**: `Cap`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Per defecte**: `Cap`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Per defecte**: `Cap`

Permet l'ús de etiquetes MiniMessage a l'enclusa. Consulteu [MiniMessage Tags](https://docs.advntr.dev/minimessage/format.html).

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Per defecte**: `Cap`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Per defecte**: `Cap`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(Número de fila)`

- **Per defecte**: `Cap`

Canvia la mida de l'endrinyera.

Es pot introduir `one`, `two`, `three`, `four`, `five`, `six` a `(Número de fila)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Per defecte**: `Cap`

Permet que el totem d'immortalitat funcioni quan es troba a l'inventari.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Per defecte**: `Cap`

Permet al jugador ignorar el límit de jugadors connectats.

#### `purpur.mending_shift_click`

- **Per defecte**: `Cap`

Permet al jugador reparar l'objecte que té a les mans quan fa `agatxat i interactua`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Per defecte**: `Cap`

Permet al jugador instal·lar spawners.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Per defecte**: `Cap`

Permet al jugador teleportar-se immediatament quan utilitza un portal al Nether.

#### `purpur.sign.color`

- **Per defecte**: `Cap`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Per defecte**: `Cap`

Permet utilitzar el codi d'encriptació `(&o)` als rètols.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Per defecte**: `Cap`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Per defecte**: `Cap`

Permet al jugador evitar l'explosió de TNT interaccionant amb ella amb les tisores.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Permisos previstos

#### `plazma.bypass.ncr-require`

- **Per defecte**: `Cap`

Permet al jugador connectar-se sense tenir instal·lat el mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operador.

[^2]: Per exemple: `ender_dragon`
