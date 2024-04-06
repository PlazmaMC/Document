---
description: Descubre qué es Plazma como plataforma de servidor.
---

# ❓ ¿Qué es Plazma?

- **Plazma** es una plataforma de servidor basada en [Paper](https://github.com/PaperMC/Paper), que solo toma las ventajas de [Andromeda](https://github.com/EarendelArchived/Andromeda) y [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Siempre estamos esforzándonos por ofrecer alta estabilidad, rendimiento potente, actualizaciones rápidas y una amplia gama de funciones.

## 📋 Objetivos de Plazma <a href="#id-1" id="id-1"></a>

- Estamos trabajando para convertirnos en una plataforma de servidor con actualizaciones rápidas y alta estabilidad.
- Estamos trabajando para ofrecer una amplia gama de funciones y un rendimiento potente, no menos que una plataforma de modding.
- Estamos trabajando para crear una plataforma libre donde se pueda personalizar incluso los parches de Vanilla.

## ⚙️ Características principales <a href="#id-2" id="id-2"></a>

1. **Un ecosistema de complementos potente**\
   Basado en [Paper](https://github.com/PaperMC/Paper),
   la mayoría de los [complementos más recientes](#user-content-fn-1)[^1] disponibles para descargar en Internet funcionan correctamente.
2. **Optimización sin necesidad de configuración**\
   Incluye todos los parches de [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) y
   ofrece un rendimiento óptimo con algunas optimizaciones internas y modos integrados.
3. **Personalización del juego a tu gusto**\
   [Purpur](https://github.com/PurpurMC/Purpur) incluido en Plazma
   permite modificar las propiedades generales del juego a tu gusto.
4. **Servidor que juega de forma segura**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) incluido desde la versión 1.19
   de [Mojang](#user-content-fn-2)[^2] que permite deshabilitar el [sistema de informes de chat](#user-content-fn-3)[^3],\
   permitiendo jugar en un servidor seguro sin seguimiento al eliminar por completo el recolector de información de diagnóstico.
5. **Actualizaciones más rápidas**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) mantiene los parches incluidos en Plazma siempre actualizados, ofreciendo las actualizaciones más rápidas entre las plataformas de servidor basadas en Paper.
6. **Optimización de archivos de configuración predeterminados**\
   Los archivos de configuración aplicados por defecto están optimizados, por lo que no es necesario optimizarlos manualmente.
7. **Funcionamiento sistemático de múltiples hilos**\
   Asincroniza los mecanismos del sistema que no están relacionados con los mecanismos del juego para optimizar el servidor reduciendo el [tiempo de latencia](#user-content-fn-4)[^4].
8. **Bloqueo del uso de espacio innecesario**\
   Combina todos los datos con valores similares en uno solo para reducir el uso de memoria.

#### ¿Quieres saber más sobre Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Casos de uso <a href="#id-3" id="id-3"></a>

- **Plataforma que maneja incluso los complejos complementos correctamente**\
  Utilizado en el servidor del desarrollador [IPECTER](https://github.com/IPECTER) con Plazma.\
  A pesar de la gran cantidad de paquetes de datos complejos y extensos plugins propios que funcionan con NMS y reflexión,\
  puede admitir más de 100 jugadores sin caídas de rendimiento.
- **Plataforma que mantiene un rendimiento rápido incluso en servidores de RPG**\
  Ha mantenido de forma estable a 100 jugadores en un único clúster sin caídas de TPS,\
  y hasta 250 jugadores en 4 clústeres pudieron jugar sin problemas.
- **Plataforma que muestra luz en los chunks/entidades**\
  Al cambiar de Purpur a Plazma en el servidor de supervivencia donde se producían retrasos en el procesamiento de chunks y entidades,\
  se pudo reducir la mayoría de los retrasos.
- **Plataforma elegida por muchos streamers**\
  Utilizado como el servidor preferido por muchos espectadores de streamers.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Tendencia de usuarios de Plazma en tiempo real</p></figcaption>
</figure>

## ⬇️ Descargar

Puedes descargar Plazma desde la página a continuación.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### ¿Quieres más información sobre el soporte de versiones?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Plugins de Bukkit, CraftBukkit, Spigot y los plugins de Paper, Pufferfish, Purpur.

[^2]: Propiedad de Microsoft Corporation.

[^3]: Al desactivar el sistema de reporte de chat, el chat se manejará únicamente en el servidor, evitando el rastreo de chat de Mojang.

[^4]: Tiempo en el que el juego se detiene momentáneamente para que funcione el mecanismo del sistema.
