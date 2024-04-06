---
description: Descubre cómo personalizar el servidor.
---

# 📶 Desarrollarse

La razón por la que se utiliza una plataforma de servidor modificada como Plazma en lugar de utilizar la plataforma oficial de servidores proporcionada por Mojang Studios es la capacidad de realizar una **personalización** poderosa.

A continuación se presentan varias formas de personalizar y utilizar Plazma.

## Modificación de la configuración <a href="#id-1" id="id-1"></a>

La forma más básica de personalizar Plazma es modificar la configuración.

Plazma proporciona ajustes de configuración poderosos que van desde los mecanismos del juego hasta las propiedades de los mobs.

Consulte la página siguiente para obtener información sobre la configuración de Plazma.

{% content-ref url="../reference/configurations/" %}
[configuraciones](../reference/configurations/)
{% endcontent-ref %}

***

## Uso de complementos <a href="#id-2" id="id-2"></a>

{% hint style="éxito" %}

**Plazma soporta correctamente todos los complementos basados en Paper.**

En el caso de los complementos de Spigot, debido a los cambios de mapeo de Paper a partir de la versión 1.20.5, algunos pueden no funcionar correctamente, pero la mayoría de los complementos basados en Paper, como Paper, Pufferfish y Purpur, funcionarán correctamente en Plazma. Si un complemento no funciona correctamente, se debe informar inmediatamente [aquí.](../diagnosis/plugins.md)

{% endhint %}

Esta es la razón principal para usar Plazma y la forma más poderosa de personalizarlo.
El sólido ecosistema de complementos de Plazma permite personalizar fácilmente el servidor.

Hay varias formas de encontrar y descargar complementos. Algunos complementos se cargan en servicios de repositorios públicos, mientras que otros se pueden cargar en GitHub o en su propio sitio web.

{% hint style="precaución" %}

**¡Los complementos pueden acceder directamente al sistema!**

Antes de aplicar un complemento, siempre asegúrese de que sea seguro utilizando servicios como VirusTotal, o descargando los complementos de servicios confiables.

{% endhint %}

Hay varios servicios para descargar complementos. Entre ellos, servicios como [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) revisan los complementos antes de ser cargados para garantizar que solo se distribuyan complementos seguros.

### Aplicación de complementos <a href="#id-2.1" id="id-2.1"></a>

Una vez descargados los complementos, es hora de aplicarlos.

1. Los complementos están en formato `.jar` o archivo ejecutable de Java. Algunos pueden estar comprimidos, en cuyo caso, si contienen `bukkit`, `spigot` o `paper` en el nombre y un archivo `fat`, se debe usar el archivo `fat`.
2. Coloque los archivos descargados en la carpeta 'plugins' del servidor y reinicie el servidor.
3. Cuando Plazma se inicie, verá nueva información en la consola.
   Esto indica que Plazma ha cargado los complementos correctamente.
4. A pesar de que Plazma haya cargado los complementos correctamente, es posible que no se inicien.
   Puede usar el comando `/plugins` para ver los complementos cargados en el servidor.
   Si el nombre de un complemento instalado es <mark style="background-color:red;">rojo</mark> en lugar de <mark style="background-color:green;">verde</mark>, significa que el complemento se ha cargado correctamente.

Si un complemento no se ha cargado correctamente, puede encontrar soluciones en la siguiente página.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Uso de paquetes de datos <a href="#id-3" id="id-3"></a>

Los paquetes de datos son una forma de personalizar Minecraft similar a los [paquetes de recursos](#user-content-fn-1).

Con los paquetes de datos, puede agregar nuevas entidades y desafíos al juego, entre otras modificaciones internas.

{% hint style="precaución" %}

**¡Los paquetes de datos pueden dañar el mundo!**

Algunos paquetes de datos defectuosos pueden dañar el mundo de forma irreversible.

Por lo tanto, se recomienda hacer una copia de seguridad del mundo antes de aplicar paquetes de datos.

{% endhint %}

Los paquetes de datos se pueden descargar de varios servicios, como [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs).

Una vez descargados los paquetes de datos, se pueden aplicar colocándolos en la carpeta 'datapacks' del mundo del servidor.
Si la carpeta no existe, simplemente créela y añada los paquetes de datos.

{% hint style="warning" %}

**En algunos paquetes de datos[^2], es posible que la aplicación inicial no se aplique correctamente la primera vez.**

En caso de esto, se recomienda reiniciar el servidor **2 veces**.

{% endhint %}

Los paquetes de datos pueden dañarse fácilmente con cada actualización de Minecraft.

Especialmente si un paquete de datos se daña por completo, es importante realizar pruebas exhaustivas antes de actualizar el servidor para evitar conflictos.

{% hint style="info" %}

**Después de ingresar `safeMode` detrás del comando de inicio del servidor, puede desactivar todos los paquetes de datos y reiniciar el servidor.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safemode)

{% endhint %}

Puede verificar los paquetes de datos aplicados con el comando `/datapack list`.

***

## Optimización <a href="#id-4" id="id-4"></a>

Plazma tiene muchas correcciones de optimización aplicadas. 또한, Plazma가 처음으로 시작되면 자동으로
구성을 최적화 하므로 [시작하기](./README.md) 설명서를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우,
아래 설명서를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

El proxy conecta servidores entre sí y permite a los jugadores moverse entre servidores o comunicarse con otros sin realizar tareas adicionales.

Consulte la siguiente página para obtener información sobre la configuración segura y correcta del proxy.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Seguridad <a href="#id-5" id="id-5"></a>

Con el desarrollo de mods, en Minecraft es posible encontrar fácilmente un [motor de ataque de vulnerabilidades](#user-content-fn-3).

Aunque la mayoría de las vulnerabilidades que son ejecutables en juegos normales están [bloqueadas de forma predeterminada](#user-content-fn-4),
atacar vulnerabilidades a través de cargadores de terceros no está bloqueado.

Por lo tanto, si el servidor está expuesto al público, se recomienda instalar complementos anti-trampas para bloquear el uso de vulnerabilidades y configurar proxies, reinicios automáticos, copias de seguridad, etc., para que el servidor pueda recuperarse rápidamente en caso de caída.

### Configuración de permisos <a href="#id-5.1" id="id-5.1"></a>

Algunos comandos de administrador de complementos pueden tener vulnerabilidades si los permisos no están configurados correctamente.

Se recomienda limitar los permisos de usuarios normales utilizando plugins de administración de permisos como [LuckPerms](https://luckperms.net/).

### Bloqueo de X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray es una de las vulnerabilidades que se pueden utilizar fácilmente incluso en clientes de optimización básica.

Plazma proporciona una configuración para bloquear X-Ray de forma predeterminada.

Consulte la siguiente página para obtener información sobre cómo bloquear X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Lista blanca <a href="#id-5.3" id="id-5.3"></a>

Si solo desea que algunos usuarios se conecten al servidor, se recomienda utilizar [Ngrok](./README.md#id-6.2) para usar una dirección de servidor ofuscada o configurar una lista blanca para evitar que otros jugadores se conecten.

Puede permitir o prohibir la conexión de un jugador en la consola del servidor con `/whitelist add <jugador>` o `/whitelist remove <jugador>`.

Para ver los jugadores permitidos, use `/whitelist query`.

***

[^1]: O también en Minecraft: Bedrock Edition con complementos como la adición de entidades.

[^2]: Añadir entidades al juego, entre otras cosas.

[^3]: Comúnmente conocido como "hackeo".

[^4]: Es posible que las configuraciones no estén optimizadas, que Plazma sea antiguo o que no bloquee vulnerabilidades recién descubiertas.

[^5]: Los jugadores se conectan al servidor a través del servidor proxy Ngrok, y la dirección de Ngrok emitida en cada reinicio será diferente.
