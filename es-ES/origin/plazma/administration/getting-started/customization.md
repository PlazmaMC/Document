---
description: Descubre cómo personalizar el servidor.
---

# 🎨 Personalización de usuario

La razón por la que se utiliza una plataforma de servidor modificada como Plazma en lugar de utilizar la plataforma oficial de servidores proporcionada por Mojang Studios es la capacidad de realizar una **personalización** poderosa.

A continuación se presentan varias formas de personalizar y utilizar Plazma.

## Modificación de la configuración <a href="#id-1" id="id-1"></a>

La forma más básica de personalizar Plazma es modificar la configuración.

Plazma proporciona ajustes de configuración poderosos que van desde los mecanismos del juego hasta las propiedades de los mobs.

Consulte la página siguiente para obtener información sobre la configuración de Plazma.

{% content-ref url="../reference/configurations/" %}
[configuraciones](../reference/configurations/)
{% endcontent-ref %}

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

**Algunos [paquetes de datos](#user-content-fn-2) pueden no aplicarse correctamente la primera vez.**

En caso de esto, se recomienda reiniciar el servidor **2 veces**.

{% endhint %}

Los paquetes de datos pueden dañarse fácilmente con cada actualización de Minecraft.

Especialmente si un paquete de datos se daña por completo, es importante realizar pruebas exhaustivas antes de actualizar el servidor para evitar conflictos.

{% hint style="info" %}

**Después de ingresar `safeMode` detrás del comando de inicio del servidor, puede desactivar todos los paquetes de datos y reiniciar el servidor.**

[Consulte `Referencia > Argumentos` para obtener más información detallada.](../reference/arguments.md)

{% endhint %}

Puede verificar los paquetes de datos aplicados con el comando `/datapack list`.

***

[^1]: O también en Minecraft: Bedrock Edition con complementos como la adición de entidades.

[^2]: Añadir entidades al juego, entre otras cosas.
