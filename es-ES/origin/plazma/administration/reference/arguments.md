---
description: Aprenda sobre los argumentos de inicio y las propiedades del sistema.
---

# 🎛️ Argumentos y propiedades

Los valores de los argumentos de inicio y las propiedades del sistema son valores adjuntos a los [comandos utilizados](#user-content-fn-1)[^1] en la ejecución de Plazma,\
permitiendo cambiar valores que no pueden ser modificados después de la ejecución de Plazma.

De acuerdo al [lugar donde se adjunta el comando](#user-content-fn-2)[^2], se dividen en **argumentos de inicio** y **propiedades del sistema**.

***

## Propiedades del sistema <a href="#id-1" id="id-1"></a>

Las propiedades del sistema se ingresan antes de `-jar` y son procesadas por JVM antes de la inicialización de Plazma.

{% hint style="warning" %}

**Al modificar las propiedades del sistema, el funcionamiento de Plazma y JVM puede cambiar, ¡lo que puede tener un gran impacto en el juego!**

Si no está seguro de qué papel desempeña cada propiedad del sistema, **¡no la utilice bajo ninguna circunstancia!**

{% endhint %}

### Modo de uso <a href="#id-1.1" id="id-1.1"></a>

Las propiedades del sistema se ingresan como argumentos de Java entre `java` y `-jar`.

Por ejemplo, si desea aplicar la propiedad del sistema `Plazma.dummyProperty`,\
al ingresar de la siguiente manera, el valor `37` se asignará a la siguiente propiedad y Plazma se inicializará.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

El prefijo `-D` indica que el argumento no está integrado en JVM, sino que es un argumento exclusivo de Plazma, y

si no se proporciona ningún valor a la propiedad, el valor se fijará en [`true`.](#user-content-fn-3)[^3]

{% hint style="info" %}

**La plataforma del servidor de la serie Paperweight incluye un punto (`.`) en el nombre de cada propiedad del sistema para distinguir las propiedades entre plataformas.**

En algunos terminales como Windows Powershell, es posible que estos argumentos no sean aceptados, por lo que se debe agregar `"` al principio y al final de los argumentos. [^4]

{% endhint %}

### Propiedades del sistema completas <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Actualiza el formato de los carteles obsoletos.

#### `debug.entities`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Activa los registros de depuración relacionados con la información de las entidades.

#### `debug.rewriteForIDE`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva la revisión de NMS y remapea automáticamente la información de la versión interna para que pueda ser correctamente cargada por el IDE.

#### `disable.watchdog`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva el sistema de advertencia del Watchdog de Spigot.

#### `letMeReload`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva el mensaje de confirmación del comando `/reload`.

{% hint style="danger" %}

**El comando `/reload` es muy inestable, por lo que cualquier problema que surja en el servidor después de usar `/reload` será responsabilidad del usuario.**

Si eres desarrollador de plugins y necesitas actualizar un plugin, utiliza el hotswap en lugar de `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva los plugins que utilizan el sistema de entrada y salida estándar.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Advierte cuando se detecta un formato de legado en los componentes del chat.

#### `Paper.bypassHostCheck`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva la verificación de patrones del servidor al conectarse un jugador.

#### `Paper.debugDynamicMissingKeys`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Activa los registros de depuración para claves faltantes en objetos NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Activa los registros de depuración para perfiles de calaveras incorrectos.

Registra la ubicación de todas las calaveras incorrectas en el mundo.

#### `Paper.disableChannelLimit`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva el límite de 128 canales de plugins por jugador.

#### `Paper.disableClassPrioritization`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva la priorización de clases de plugins.

Útil en caso de problemas con los sombreadores de plugins.

#### `Paper.disableFlushConsolidate`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva la consolidación de envío de Netty.

#### `Paper.excessiveTELimit`

- **Tipo**: `Integer`
- **Valor predeterminado**: `750`

Envía fragmentos de entidades en múltiples paquetes si exceden el valor establecido.

#### `Paper.filterThreshold`

- **Tipo**: `Integer`
- **Valor predeterminado**: `8192`

Establece el tamaño máximo de paquetes que el servidor puede recibir de una sola vez.

#### `Paper.ignoreJavaVersion`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva la verificación de la versión de Java.

{% hint style="danger" %}

**¡Esto podría hacer que JVM intente acceder a código inexistente!**

Esto puede causar daños permanentes en archivos como mundos, y desestabilizar completamente el juego.

Cualquier problema causado por esto es responsabilidad del usuario, y Plamza no brindará soporte al respecto.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tipo**: `Integer`
- **Valor predeterminado**: `64`

Establece el límite de caracteres para los nombres de los canales de plugins.

#### `Paper.maxSignLength`

- **Tipo**: `Integer`
- **Valor predeterminado**: `80`

Establece la longitud máxima de caracteres que se pueden ingresar en una línea de un cartel.

#### `Paper.minPrecachedDatafixVersion`

- **Tipo**: `Integer`
- **Valor predeterminado**: `(versión del mundo) + 1`

Establece la versión de la información de actualización del mundo que se inicializará primero.

Útil cuando se necesitan actualizar grandes cantidades de fragmentos, pero no se usa en otros casos.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `True`

Activa el procesamiento de comentarios en archivos YAML.

#### `Paper.playerConnection.keepAlive`

- **Tipo**: `Integer`
- **Valor predeterminado**: `30`

Expulsa al jugador si no ha recibido ningún dato durante el tiempo especificado (en segundos).

Normalmente, el juego[^7] envía continuamente una [señal de latido](#user-content-fn-8)[^8] al servidor, por lo que no se expulsa al jugador, pero

#### `Paper.skipServerPropertiesComments`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Ignora los comentarios de las propiedades del servidor.

#### `Paper.debug-sync-loads`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Activa los registros de depuración de la carga sincronizada de fragmentos.

#### `Paper.enable-sync-chunk-writes`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Activa el sistema de escritura de fragmentos sincronizado por defecto de Minecraft.

Esto guarda cada fragmento en orden, causando una gran degradación del rendimiento.

#### `Paper.explicit-flush`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Activa el vaciado explícito de los canales de red.

#### `Paper.strict-thread-checks`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Registra siempre los errores que no ocurren en el hilo principal.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Muestra una advertencia si una tarea programada tiene un retraso excesivo.

#### `Paperclip.patchOnly`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Si se utiliza el archivo de ejecución predeterminado, aplica solo el parche sin iniciar el servidor.

#### `Plazma.aggressiveOptimize`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `false`

{% hint style="warning" %}

**Esta propiedad se trasladará a un argumento de inicio después de la versión 1.20.5.**

{% endhint %}

Aplica una optimización de configuración más estricta al inicio inicial.

Al activar, el servidor se vuelve más rápido y seguro, pero puede bloquear algunas mecánicas o tener un gran impacto en el juego.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `false`

Suprime el mensaje de advertencia[^11] que se muestra al inicializarse Plazma.

### Propiedad obsoleta <a href="#id-1.3" id="id-1.3"></a>

Las siguientes propiedades del sistema son obsoletas.

#### `timings.bypassMax`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `false`
- **Obsoleto**: Timings ha sido eliminado de Plazma desde

Determina si se puede exceder el máximo de valores que se pueden enviar a la API de Timings de Aikar.

Incluso si se hace esto, si no se maneja la excepción en la API, se aplicará un límite de velocidad.

***

## Argumento de inicio <a href="#id-2" id="id-2"></a>

El argumento de inicio se ingresa después de `-jar *.jar` para inicializar Plazma y se procesa junto con él.

### Modo de uso <a href="#id-2.1" id="id-2.1"></a>

Las propiedades del sistema se ingresan como argumentos de programa después de `-jar *.jar`.

Por ejemplo, si se intenta aplicar el argumento de inicio `nogui`,\
al ingresar de la siguiente manera, Plazma procesará el argumento `nogui` durante la inicialización.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argumento de inicio completo <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Valor predeterminado**: `bukkit.yml`

Establece el nombre y la ubicación del [archivo de configuración de Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Valor predeterminado**: `commands.yml`

Establece el nombre y la ubicación del [archivo de configuración de comandos de Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Valor predeterminado**: `server.properties`

Establece el nombre y la ubicación del archivo de [propiedades del servidor](../reference/configurations/property.md).

#### `demo`

Inicia el servidor en modo demo.

#### `eraseCache`

Elimina los archivos de caché restantes después de actualizar el mundo.

#### `forceUpgrade`

Actualiza el mundo de forma forzada ignorando la versión[^12].

#### `help`

- **Alias**: `?`

Muestra todos los argumentos de inicio de Plazma y sus descripciones.

#### `initSettings`

Crea solo los archivos de configuración y luego cierra el servidor.

#### `jfrProfile`

Activa el perfilado JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Valor predeterminado**: `(server properties)`

Establece el número máximo permitido de [jugadores](#user-content-fn-14).

#### `nogui`

Desactiva el panel de interfaz gráfica.

#### `nojline`

Deshabilita JLine y utiliza la consola vanilla.

#### `modo-en-línea`

- **Alias**: `o`
- **Valor predeterminado**: `(server properties)`

Selecciona si verificar a los jugadores con el servidor de autenticación de Mojang.

**Si no se usa Velocity u otros proxies, puede resultar en una violación del [EULA](../getting-started/README.md#id-5).**

#### `configuración-de-paper`

- **Alias**: `paper`
- **Valor predeterminado**: `paper.yml`

{% hint style="warning" %}

**Este argumento ha sido descontinuado después de la versión 1.19.4**

{% endhint %}

Establece la ubicación de los archivos de configuración de PaperSpigot descontinuados.

Se utiliza para migrar la configuración existente a un nuevo archivo de configuración, y luego ya no se usa.

#### `directorio-de-configuración-de-paper`

- **Alias**: `paper-dir`
- **Valor predeterminado**: `config`

Establece el nombre y la ubicación de la carpeta donde se encuentran los archivos de configuración de Paper.

#### `directorio-de-configuración-de-plazma`

- **Alias**: `plazma-dir`

Establece el nombre y la ubicación de la carpeta donde se encuentran los archivos de configuración de Plazma.

#### `plugins`

- **Alias**: `p`
- **Valor predeterminado**: `plugins`

Establece la ubicación de la carpeta de plugins.

#### `configuración-de-pufferfish`

- **Alias**: `pufferfish`
- **Valor predeterminado**: `pufferfish.yml`

Establece el nombre y la ubicación del archivo de configuración de Pufferfish.

#### `configuración-de-purpur`

- **Alias**: `purpur`
- **Valor predeterminado**: `purpur.yml`

Establece el nombre y la ubicación del archivo de configuración de Purpur.

#### `modo-seguro`

Inicia el servidor en un estado completamente vanilla.

#### `ip-del-servidor`

- **Alias**: `h`, `host`
- **Valor predeterminado**: `(server properties)`

Establece el nombre del host del servidor o la dirección IP [Protocolo de Internet](#user-content-fn-13)[^13].

#### `puerto-del-servidor`

- **Alias**: `p`, `port`
- **Valor predeterminado**: `(server properties)`

Establece el puerto del servidor.

#### `nombre-del-servidor`

- **Valor predeterminado**: `Un Servidor Plazma`

Establece el nombre del servidor.

#### `configuración-de-spigot`

- **Alias**: `S`
- **Valor predeterminado**: `spigot.yml`

Establece el nombre y la ubicación del archivo de configuración de Spigot.

#### `versión`

- **Alias**: `v`

Muestra la versión de Plazma.

#### `directorio-del-mundo`

- **Alias**: `W`, `universo`, `contenedor-de-mundo`
- **Valor predeterminado**: `(carpeta del servidor)`

Establece la ubicación donde se guardan los archivos del mundo.

#### `nombre-del-mundo`

- **Alias**: `w`, `mundo`
- **Valor predeterminado**: `(server properties)`

Establece el nombre del archivo del mundo.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: El manejo de argumentos cambia dependiendo de su ubicación adicional.

[^3]: Por ejemplo, si desea establecer `Plazma.iKnowWhatIAmDoing` en `true`, solo ingresar `-DPlazma.iKnowWhatIAmDoing` es suficiente en lugar de `-DPlazma.iKnowWhatIAmDoing=true`.

[^4]: Por ejemplo, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detector de eventos.

[^6]: Detector de eventos.

[^7]: Cliente.

[^8]: Señal que indica que el servidor está conectado correctamente, como un latido del corazón.

[^9]: Con la función de expulsión AFK de Purpur, también se puede expulsar a los jugadores ausentes.

[^10]: Sistema de escritura de fragmentos sincronizados, Sync Chunk Write System.

[^11]: `¡ADVERTENCIA! Plazma puede causar problemas inesperados, así que asegúrate de probarlo a fondo antes de usarlo en un servidor público.`

[^12]: La `optimización del mundo` en el juego también funciona de la misma manera.

[^13]: Protocolo de Internet, IP.

[^14]: Se excluyen los administradores de nivel 2 o superior.
