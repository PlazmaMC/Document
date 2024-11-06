---
description: Descubre los permisos de Plazma.
---

# 🛡️ Permiso

Los permisos son herramientas de seguridad simples que establecen el alcance en el que los jugadores pueden interactuar en el servidor.

Para aprovechar y modificar los permisos fácilmente, se debe utilizar un plugin como [LuckPerms](https://luckperms.net).

***

## Comprender el sistema de permisos básico <a href="#id-1" id="id-1"></a>

Minecraft proporciona grupos de permisos de administración básicos.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Jugador**\
   Es el grupo de permisos que se otorga a todos los jugadores de forma predeterminada.
2. **Moderador**\
   Puede ignorar la protección de spawn.
3. **Administrador de mundo**\
   Puede utilizar todos los comandos y bloques de comandos relacionados con la gestión del mundo.\
   Es el grupo de permisos por defecto aplicado a los datapacks y bloques de comandos.
4. **Administrador**\
   Puede utilizar todos los comandos relacionados con la gestión de jugadores.
5. **Superadministrador**\
   Puede utilizar todos los comandos, incluidos los de gestión del servidor.\
   Es el grupo de permisos por defecto aplicado a la consola y a los operadores.

***

## Configuración de permisos <a href="#id-2" id="id-2"></a>

***

## Permisos completos <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Clave con espacio de nombres)`

- **Por defecto**: `Ninguno`

Permite a los jugadores montar en entidades al agacharse e interactuar con ellas.

Al montar en una entidad, se puede controlar su movimiento con las teclas de movimiento y saltar o volar con la tecla de salto.

En `(Clave con espacio de nombres)` se debe introducir el [ID con espacio de nombres](#user-content-fn-2)[^2] de la entidad.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Clave con espacio de nombres)`

- **Por defecto**: `Ninguno`

Permite al jugador usar las habilidades especiales de la entidad mientras está montado en ella.

No todas las entidades tienen habilidades especiales disponibles. Consulte a continuación todas las habilidades especiales disponibles.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

¡Publica tus ideas en [Plazma Discord](https://plazmamc.org/discord) o [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Ver todas las habilidades especiales disponibles actualmente</summary>

- **`crepper`**\
  Al presionar la tecla de salto, explota.\
  Si el jugador tiene el permiso `allow.powered.creeper`, puede cargar manteniendo presionada la tecla de salto.
- **`dolphin`**\
  Al presionar la tecla de salto, embiste.
- **`phantom`**\
  Al presionar la tecla de salto, dispara llamas.
- **`wither`**\
  Al interactuar, dispara la cabeza de wither.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/credits (Jugador)`](commands.md#credits).

Al agregar `.other` después del nombre del permiso, se permite su uso a otros jugadores.

#### `bukkit.command.demo`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/demo (Jugador)`](commands.md#demo).

Al agregar `.other` después del nombre del permiso, se permite su uso a otros jugadores.

#### `bukkit.command.ping`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/ping (Jugador)`](commands.md#ping).

Al agregar `.other` después del nombre del permiso, se permite su uso a otros jugadores.

#### `bukkit.command.ram`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/rambar (Jugador)`](commands.md#rambar).

Al agregar `.other` después del nombre del permiso, se permite su uso a otros jugadores.

#### `bukkit.command.restart`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/tpsbar (Jugador)`](commands.md#tpsbar).

Al agregar `.other` después del nombre del permiso, se permite su uso a otros jugadores.

#### `bukkit.command.timings`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/timings`](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Para obtener información sobre comandos similares, consulte [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(Modo de juego)`

- **Por defecto**: `Administrador del mundo`

Permite el uso del comando `/gamemode (Modo de juego) (Jugador)`.

Al agregar `.other` después del nombre del permiso, se permite su uso a otros jugadores.

#### `paper.antixray.bypass`

- **Por defecto**: `Ninguno`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Esto beneficia el rendimiento de ambas partes.

> Consulte la página a continuación para obtener información sobre cómo configurar el X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Por defecto**: `Ninguno`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Por defecto**: `Ninguno`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Por defecto**: `Ninguno`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Por defecto**: `Ninguno`

Permite el uso de etiquetas [MiniMessage](https://docs.advntr.dev/minimessage/format.html) en los yunques.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Por defecto**: `Ninguno`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Por defecto**: `Ninguno`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Por defecto**: `Ninguno`

Excluye al jugador de ser expulsado por inactividad.

#### `purpur.debug.f3n`

- **Por defecto**: `Administrador del mundo`

Permite al jugador cambiar el modo de juego con la tecla `F3 + N`.

Solo funciona si tiene permiso para ese modo de juego.

#### `purpur.drop.spawners`

- **Por defecto**: `Ninguno`

Al minar bloques de spawner con el objeto configurado, se suelta el bloque de spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NúmeroTexto)`

- **Por defecto**: `Ninguno`

Cambia el tamaño del cofre de ender.

Puedes ingresar `one`, `two`, `three`, `four`, `five`, `six` en `(NúmeroTexto)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Por defecto**: `Ninguno`

Permite que el tótem de inmortalidad funcione aunque esté en el inventario.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Por defecto**: `Ninguno`

Permite a los jugadores ignorar el límite de jugadores conectados.

#### `purpur.mending_shift_click`

- **Por defecto**: `Ninguno`

Permite a los jugadores reparar los objetos que llevan al hacer `clic derecho mientras están agachados`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Por defecto**: `Ninguno`

Permite a los jugadores colocar spawners.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Por defecto**: `Ninguno`

Permite a los jugadores teletransportarse instantáneamente al usar un portal del Nether.

#### `purpur.sign.color`

- **Por defecto**: `Ninguno`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Por defecto**: `Ninguno`

Permite utilizar el código de obfuscación `(&o)` en los letreros.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Por defecto**: `Ninguno`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Por defecto**: `Ninguno`

Permite a los jugadores desactivar la explosión de TNT al interactuar con unas tijeras.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Permiso previsto

#### `plazma.bypass.ncr-require`

- **Por defecto**: `Ninguno`

Permite a los jugadores conectarse aunque no tengan instalado el mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operador.

[^2]: Ejemplo: `ender_dragon`
