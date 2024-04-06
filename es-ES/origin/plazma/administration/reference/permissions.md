---
description: Descubre los permisos de Plazma.
---

# 🛡️ Permiso

Los permisos son herramientas de seguridad simples que establecen el alcance en el que los jugadores pueden interactuar en el servidor.

Para aprovechar y modificar los permisos fácilmente, se debe utilizar un plugin como [LuckPerms](https://luckperms.net).

***

## Comprender el sistema de permisos básico <a href="#id-1" id="id-1"></a>

Minecraft proporciona grupos de permisos de administración básicos.

Se pueden configurar los permisos de los [operadores](#user-content-fn-1)[^1] y bloques de comandos, y se pueden modificar en las [propiedades del servidor](configurations/property.md).

0. **Jugador**\
   Es el grupo de permisos que se otorga a todos los jugadores de forma predeterminada.
1. **Moderador**\
   Puede ignorar la protección de spawn.
2. **Administrador de mundo**\
   Puede utilizar todos los comandos y bloques de comandos relacionados con la gestión del mundo.\
   Es el grupo de permisos por defecto aplicado a los datapacks y bloques de comandos.
3. **Administrador**\
   Puede utilizar todos los comandos relacionados con la gestión de jugadores.
4. **Superadministrador**\
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

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md) de [Purpur](configurations/purpur/world.md), solo funciona cuando se activa `(Entidad) > montable`.**

{% endhint %}

#### `allow.special.(Clave con espacio de nombres)`

- **Por defecto**: `Ninguno`

Permite al jugador usar las habilidades especiales de la entidad mientras está montado en ella.

No todas las entidades tienen habilidades especiales disponibles. Consulte a continuación todas las habilidades especiales disponibles.

{% hint style="info" %}

**¿Tienes alguna buena idea para una habilidad especial?**

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

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md) de [Purpur](configurations/purpur/world.md), solo funciona cuando se activa `(Entidad) > montable`.**

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

**Este comando ha sido descontinuado.**

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

Cuando está activado el [Bloqueo de X-Ray](../expert/xray.md), los jugadores con el permiso registrado no serán sometidos a la ofuscación de bloques anti X-Ray.

Esto beneficia el rendimiento de ambas partes.

> Consulte la página a continuación para obtener información sobre cómo configurar el X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Por defecto**: `Ninguno`

{% hint style="warning" %}

Este permiso cambiará a `plazma.bypass.watchdog` en la versión 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Por defecto**: `Ninguno`

Permite el uso de códigos de [color](https://minecraft.wiki/w/Formatting_codes#Color_codes) en los yunques.

{% hint style="info" %}

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md), debe activar `yunque > permitir-colores` para que funcione.**

{% endhint %}

#### `purpur.anvil.format`

- **Por defecto**: `Ninguno`

Permite el uso de códigos de [estilo](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) en los yunques.

{% hint style="info" %}

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md), debe activar `yunque > permitir-colores` para que funcione.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Por defecto**: `Ninguno`

Permite el uso de etiquetas [MiniMessage](https://docs.advntr.dev/minimessage/format.html) en los yunques.

{% hint style="info" %}

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md), debe activar `yunque > permitir-minimessages` para que funcione.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Por defecto**: `Ninguno`

Permite desactivar la `cursiva` con el código de estilo [`&r`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) en los yunques.

{% hint style="info" %}

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md), debe activar `yunque > permitir-colores` para que funcione.**

{% endhint %}

#### `purpur.book.color.sign`

- **Por defecto**: `Ninguno`

Aplica códigos de [estilo](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) al firmar un libro.

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

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md), debe activar `mecánicas-de-juego > silk-touch` para que funcione.**

{% endhint %}

#### `purpur.enderchest.rows.(NúmeroTexto)`

- **Por defecto**: `Ninguno`

Cambia el tamaño del cofre de ender.

Puedes ingresar `one`, `two`, `three`, `four`, `five`, `six` en `(NúmeroTexto)`.

{% hint style="info" %}

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md), debe activar `ender_chest > six-rows` y `ender_chest > use-permissions-for-rows` para que funcione.**

{% endhint %}

#### `purpur.inventory_totem`

- **Por defecto**: `Ninguno`

Permite que el tótem de inmortalidad funcione aunque esté en el inventario.

{% hint style="info" %}

**En [Configuraciones del mundo de Purpur](configurations/purpur/world.md), debes activar `totem-of-undying-works-in-inventory` para que funcione correctamente.**

{% endhint %}

#### `purpur.joinFullServer`

- **Por defecto**: `Ninguno`

Permite a los jugadores ignorar el límite de jugadores conectados.

#### `purpur.mending_shift_click`

- **Por defecto**: `Ninguno`

Permite a los jugadores reparar los objetos que llevan al hacer `clic derecho mientras están agachados`.

{% hint style="info" %}

**En [Configuraciones del mundo de Purpur](configurations/purpur/world.md), debes activar `shift-right-click-repairs-mending-points` para que funcione correctamente.**

{% endhint %}

#### `purpur.place.spawners`

- **Por defecto**: `Ninguno`

Permite a los jugadores colocar spawners.

{% hint style="info" %}

**En [configuraciones/purpur/mundo.md](configurations/purpur/world.md), debe activar `mecánicas-de-juego > silk-touch` para que funcione.**

{% endhint %}

#### `purpur.portal.instant`

- **Por defecto**: `Ninguno`

Permite a los jugadores teletransportarse instantáneamente al usar un portal del Nether.

#### `purpur.sign.color`

- **Por defecto**: `Ninguno`

Permite utilizar códigos de color en los letreros [códigos de color](https://minecraft.wiki/w/Formatting_codes#Color_codes).

{% hint style="info" %}

**En [Configuraciones del mundo de Purpur](configurations/purpur/world.md), debes activar `sign > allow-colors` para que funcione correctamente.**

{% endhint %}

#### `purpur.sign.magic`

- **Por defecto**: `Ninguno`

Permite utilizar el código de obfuscación `(&o)` en los letreros.

{% hint style="info" %}

**En [Configuraciones del mundo de Purpur](configurations/purpur/world.md), debes activar `sign > allow-colors` para que funcione correctamente.**

{% endhint %}

#### `purpur.sign.style`

- **Por defecto**: `Ninguno`

Permite utilizar códigos de estilo en los letreros [`(&o excepto)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**En [Configuraciones del mundo de Purpur](configurations/purpur/world.md), debes activar `sign > allow-colors` para que funcione correctamente.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Por defecto**: `Ninguno`

Permite a los jugadores desactivar la explosión de TNT al interactuar con unas tijeras.

{% hint style="info" %}

**En [Configuraciones del mundo de Purpur](configurations/purpur/world.md), `defuse-tnt-change` debe ser mayor o igual a `0.0` para que funcione correctamente.**

{% endhint %}

### Permiso previsto

#### `plazma.bypass.ncr-require`

- **Por defecto**: `Ninguno`

Permite a los jugadores conectarse aunque no tengan instalado el mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**En [Configuraciones del mundo de Plazma](configurations/plazma/world.md), debes activar `no-chat-reports > require-install` para que funcione correctamente.**

{% endhint %}

***

[^1]: Operador.

[^2]: Ejemplo: `ender_dragon`
