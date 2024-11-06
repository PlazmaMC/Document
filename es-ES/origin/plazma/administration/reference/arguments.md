---
description: Aprenda sobre los argumentos de inicio y las propiedades del sistema.
---

# 🎛️ Argumentos y propiedades

El inicio de la adquisición y las propiedades del sistema son valores adicionales adjuntos a los comandos utilizados en la ejecución de Plazma[^1], los cuales tienen un impacto general en el funcionamiento de Plazma.

De acuerdo con la ubicación a la que se adjunta el comando, se divide en **argumentos de inicio** y **atributos del sistema**.

***

## Propiedades del sistema <a href="#id-1" id="id-1"></a>

Las propiedades del sistema se ingresan antes de `-jar` y son procesadas por JVM antes de la inicialización de Plazma.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Modo de uso <a href="#id-1.1" id="id-1.1"></a>

Las propiedades del sistema se ingresan como argumentos de Java entre `java` y `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

El prefijo `-D` indica que el argumento no está integrado en JVM, sino que es un argumento exclusivo de Plazma, y

Si no se ingresa ningún valor en los atributos, el valor se fija en [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Valor predeterminado**: `750`

Envía fragmentos de entidades en múltiples paquetes si exceden el valor establecido.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Valor predeterminado**: `8192`

Establece el tamaño máximo de paquetes que el servidor puede recibir de una sola vez.

#### `Paper.ignoreJavaVersion`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `False`

Desactiva la verificación de la versión de Java.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Esto puede causar daños permanentes en archivos como mundos, y desestabilizar completamente el juego.

Cualquier problema causado por esto es responsabilidad del usuario, y Plamza no brindará soporte al respecto.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Valor predeterminado**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Valor predeterminado**: `80`

Establece la longitud máxima de caracteres que se pueden ingresar en una línea de un cartel.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Valor predeterminado**: `(versión del mundo) + 1`

Establece la versión de la información de actualización del mundo que se inicializará primero.

Útil cuando se necesitan actualizar grandes cantidades de fragmentos, pero no se usa en otros casos.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `True`

Activa el procesamiento de comentarios en archivos YAML.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Valor predeterminado**: `30`

Expulsa al jugador si no ha recibido ningún dato durante el tiempo especificado (en segundos).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Conflicto**: `Plazma.disableConfigOptimization`

Optimiza la configuración inicial más agresivamente.

Al activarlo, el servidor se vuelve más rápido y seguro, pero puede tener un gran impacto en el juego.

#### `Plazma.disableConfigOptimization`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `false`
- **Conflicto**: `Plazma.aggressiveOptimize`

No optimiza la configuración inicial.

Esto establece el uso de la configuración básica de Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `false`

Desactiva el branding de Plazma y usa el favicon predeterminado de vanilla del servidor.

#### `Plazma.useVanillaConfiguration`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `false`
- **Conflicto**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Esto puede tener un gran impacto en la seguridad y rendimiento del servidor.

Cualquier problema derivado del uso de esta propiedad recae en el administrador del servidor.
{% endhint %}

Establece la configuración inicial en los valores predeterminados proporcionados por Mojang.

Esto desactiva todos los parches de vulnerabilidades aplicados por Paper.

Los parches de vulnerabilidades se pueden volver a activar en la configuración de Paper o Plazma.

#### `Plazma.vanillaize`

- **Tipo**: `Boolean`
- **Valor predeterminado**: `true`
- **Conflicto**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Establece la configuración inicial de forma más cercana a la de vanilla.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Valor predeterminado**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Valor predeterminado**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Inicia el servidor en modo demo.

#### `eraseCache`

Elimina los archivos de caché restantes después de actualizar el mundo.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Desactiva el panel de interfaz gráfica.

#### `nojline`

Deshabilita JLine y utiliza la consola vanilla.

#### `modo-en-línea`

- **Alias**: `o`
- **Valor predeterminado**: `(server properties)`

Selecciona si verificar a los jugadores con el servidor de autenticación de Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `configuración-de-paper`

- **Alias**: `paper`
- **Valor predeterminado**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Establece la ubicación de los archivos de configuración de PaperSpigot descontinuados.

Se utiliza para migrar la configuración existente a un nuevo archivo de configuración, y luego ya no se usa.

#### `directorio-de-configuración-de-paper`

- **Alias**: `paper-dir`
- **Valor predeterminado**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `directorio-de-configuración-de-plazma`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Valor predeterminado**: `plugins`

Establece la ubicación de la carpeta de plugins.

#### `configuración-de-pufferfish`

- **Alias**: `pufferfish`
- **Valor predeterminado**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `configuración-de-purpur`

- **Alias**: `purpur`
- **Valor predeterminado**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `modo-seguro`

Inicia el servidor en un estado completamente vanilla.

#### `ip-del-servidor`

- **Alias**: `h`, `host`
- **Valor predeterminado**: `(server properties)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Se excluyen los administradores de nivel 2 o superior.

[^14]: Protocolo de Internet, IP.
