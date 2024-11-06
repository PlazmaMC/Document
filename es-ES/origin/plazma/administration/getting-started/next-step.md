---
description: Descubre cómo personalizar el servidor.
---

# 🎨 발전하기

Mojang Studios에서 제공하는 공식 서버 플랫폼을 사용하지 않고 Plazma와 같이 수정된 서버 플랫폼을 사용하는 이유는 강력한 **사용자화**가 가능하다는 점이 가장 클 것입니다.

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

{% hint style="success" %}
**Plazma는 Paper 기반의 모든 플러그인을 정상 지원합니다.**

Spigot 플러그인의 경우 1.20.5부터 Paper의 매핑 변화로 일부 동작하지 않을 수 있지만, Paper, Pufferfish 및 Purpur 등 Paper를 기반으로 하는 대부분의 플러그인은 Plazma에서도 모두 작동하며, 만약 정상적으로 작동하지 않을 경우 Plazma의 오류이므로 즉시 [신고해주시기 바랍니다.](../diagnosis/plugins.md)
{% endhint %}

Esta es la razón principal para usar Plazma y la forma más poderosa de personalizarlo. El sólido ecosistema de complementos de Plazma permite personalizar fácilmente el servidor.

Hay varias formas de encontrar y descargar complementos. 어떤 플러그인은 공개 저장소 서비스에 플러그인을 업로드 하고, 어떤 플러그인은 GitHub 또는 자체 사이트에 업로드하기도 합니다.

{% hint style="info" %}
**플러그인은 시스템에 직접적으로 접근할 수 있습니다!**

VirusTotal 등의 서비스를 이용하여 플러그인을 적용하기 전 항상 안전한지 확인하거나, 신뢰 가능한 서비스에서 플러그인을 다운로드 하세요.
{% endhint %}

Hay varios servicios para descargar complementos. Entre ellos, servicios como [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) revisan los complementos antes de ser cargados para garantizar que solo se distribuyan complementos seguros.

### Aplicación de complementos <a href="#id-2.1" id="id-2.1"></a>

Una vez descargados los complementos, es hora de aplicarlos.

1. 플러그인은 `.jar` 또는 `Java Executable File` 로 되어 있습니다.\
   일부 플러그인은 압축 파일로 압축되어 있는 경우도 있는데, 그런 경우 압축을 풀어 이름에 `bukkit`, `spigot` 또는 `paper` 가 포함되어 있고, `fat`이 포함된 파일이 함께 있는 경우 `fat` 파일을 사용하면 됩니다.
2. Coloque los archivos descargados en la carpeta 'plugins' del servidor y reinicie el servidor.
3. Cuando Plazma se inicie, verá nueva información en la consola. Esto indica que Plazma ha cargado los complementos correctamente.
4. A pesar de que Plazma haya cargado los complementos correctamente, es posible que no se inicien. Puede usar el comando `/plugins` para ver los complementos cargados en el servidor. 설치한 플러그인의 이름이 <mark style="background-color:red;">적색</mark>이 아닌 <mark style="background-color:green;">녹색</mark>이라면 플러그인이 정상적으로 로드된 것입니다.

Si un complemento no se ha cargado correctamente, puede encontrar soluciones en la siguiente página.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Uso de paquetes de datos <a href="#id-3" id="id-3"></a>

데이터팩은 Minecraft가 기본적으로 제공하는 사용자화 방법으로써, 리소스팩[^1]과 유사합니다.

Con los paquetes de datos, puede agregar nuevas entidades y desafíos al juego, entre otras modificaciones internas.

{% hint style="info" %}
**데이터팩은 월드를 손상시킬 수 있습니다!**

Algunos paquetes de datos defectuosos pueden dañar el mundo de forma irreversible.

Por lo tanto, se recomienda hacer una copia de seguridad del mundo antes de aplicar paquetes de datos.
{% endhint %}

데이터팩 또한 여러 서비스에서 다운로드 할 수 있으며, [CurseForge](https://www.curseforge.com/minecraft/search?page=1\\&pageSize=50\\&sortBy=relevancy\\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) 등 여러 서비스에서 찾을 수 있습니다.

Una vez descargados los paquetes de datos, se pueden aplicar colocándolos en la carpeta 'datapacks' del mundo del servidor. Si la carpeta no existe, simplemente créela y añada los paquetes de datos.

{% hint style="warning" %}
[**일부 데이터팩**](#user-content-fn-2)[^2]**의 경우 처음 적용시 정상적으로 적용되지 않을 수 있습니다.**

En caso de esto, se recomienda reiniciar el servidor **2 veces**.
{% endhint %}

Los paquetes de datos pueden dañarse fácilmente con cada actualización de Minecraft.

특히, 데이터팩이 완전히 손상된 경우, 서버가 충돌하기 때문에, 서버를 업데이트하기 전 충분한 테스트를 거치는 것이 중요합니다.

{% hint style="info" %}
**서버 시작 명령어 뒤에 `safeMode`를 입력하여 데이터팩을 모두 비활성화 한 뒤 서버를 시작할 수 있습니다.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safemode)
{% endhint %}

Puede verificar los paquetes de datos aplicados con el comando `/datapack list`.

***

## Optimización <a href="#id-4" id="id-4"></a>

Plazma tiene muchas correcciones de optimización aplicadas. 또한, Plazma가 처음으로 시작되면 자동으로 구성을 최적화 하므로 [시작하기](./) 설명서를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우, 아래 설명서를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

프록시는 서버를 서로 연결하고 플레이어가 추가적인 작업 없이 서버를 이동하거나, 다른 서버와 소통할 수 있게 합니다.

Consulte la siguiente página para obtener información sobre la configuración segura y correcta del proxy.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Seguridad <a href="#id-5" id="id-5"></a>

Con el desarrollo de mods, en Minecraft es posible encontrar fácilmente un [motor de ataque de vulnerabilidades](#user-content-fn-3).

일반 게임에서도 실행 가능한 대부분의 취약점은 [기본적으로 차단되어 있지만](#user-content-fn-4)[^4], 서드파티 로더를 통해 취약점을 공격하는것은 차단되어 있지 않습니다.

따라서, 서버가 공개되어 있는 경우, 안티 치트 플러그인 등을 설치하여 취약점 사용을 차단하고, 프록시 및 자동 재시작, 백업 등을 구성하여 서버가 다운되어도 빠르게 복구할 수 있도록 하는 것이 권장됩니다.

### Configuración de permisos <a href="#id-5.1" id="id-5.1"></a>

Algunos comandos de administrador de complementos pueden tener vulnerabilidades si los permisos no están configurados correctamente.

[LuckPerms](https://luckperms.net/) 등의 권한 관리 플러그인을 사용하여 일반 사용자의 권한을 제한하는 조치를 하는것이 권장됩니다.

### Bloqueo de X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray es una de las vulnerabilidades que se pueden utilizar fácilmente incluso en clientes de optimización básica.

Plazma proporciona una configuración para bloquear X-Ray de forma predeterminada.

Consulte la siguiente página para obtener información sobre cómo bloquear X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Lista blanca <a href="#id-5.3" id="id-5.3"></a>

일부 사용자만 서버에 접속할 수 있도록 하는 경우, [Ngrok](./#id-6.2)을 사용하여 [난독화된 서버 주소를 사용](#user-content-fn-5)[^5] 하거나, 화이트리스트를 설정하여 다른 플레이어가 서버에 접속하지 못하도록 하는 것도 권장됩니다.

서버 콘솔에서 `/whitelist add <player>` 를 통해 플레이어의 접속을 허용하거나, `/whitelist remove <player>` 로 플레이어의 접속을 다시 금지할 수 있습니다.

Para ver los jugadores permitidos, use `/whitelist query`.

***

[^1]: O también en Minecraft: Bedrock Edition con complementos como la adición de entidades.

[^2]: Añadir entidades al juego, entre otras cosas.

[^3]: Comúnmente conocido como "hackeo".

[^4]: Es posible que las configuraciones no estén optimizadas, que Plazma sea antiguo o que no bloquee vulnerabilidades recién descubiertas.

[^5]: Los jugadores se conectan al servidor a través del servidor proxy Ngrok, y la dirección de Ngrok emitida en cada reinicio será diferente.
