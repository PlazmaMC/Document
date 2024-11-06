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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Actualizaciones más rápidas**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) mantiene los parches incluidos en Plazma siempre actualizados, ofreciendo las actualizaciones más rápidas entre las plataformas de servidor basadas en Paper.
6. **Optimización de archivos de configuración predeterminados**\
   Los archivos de configuración aplicados por defecto están optimizados, por lo que no es necesario optimizarlos manualmente.
7. **Funcionamiento sistemático de múltiples hilos**\
   Asincroniza los mecanismos del sistema que no están relacionados con los mecanismos del juego para optimizar el servidor reduciendo el [tiempo de latencia](#user-content-fn-4)[^4].
8. **Bloqueo del uso de espacio innecesario**\
   Combina todos los datos con valores similares en uno solo para reducir el uso de memoria.

## ✨ Casos de uso <a href="#id-3" id="id-3"></a>

- **Plataforma que maneja incluso los complejos complementos correctamente**\
  Utilizado en el servidor del desarrollador [IPECTER](https://github.com/IPECTER) con Plazma.\
  A pesar de la gran cantidad de paquetes de datos complejos y extensos plugins propios que funcionan con NMS y reflexión,\
  puede admitir más de 100 jugadores sin caídas de rendimiento.
- **Plataforma que mantiene un rendimiento rápido incluso en servidores de RPG**\
  Ha mantenido de forma estable a 100 jugadores en un único clúster sin caídas de TPS,\
  y hasta 250 jugadores en 4 clústeres pudieron jugar sin problemas.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Plataforma elegida por muchos streamers**\
  Ha sido elegida como el cubo de participación de los espectadores de muchos streamers.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
