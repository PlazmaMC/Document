---
description: Erfahren Sie mehr über Plazma als Serverplattform.
---

# ❓ Was ist Plazma?

- **Plazma** ist eine auf [Paper](https://github.com/PaperMC/Paper) basierende Serverplattform, die nur die Vorteile von [Andromeda](https://github.com/EarendelArchived/Andromeda) und [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) vereint.
- Wir bemühen uns stets um hohe Stabilität, starke Leistung, schnelle Updates und ein umfangreiches Funktionsangebot.

## 📋 Ziele von Plazma <a href="#id-1" id="id-1"></a>

- Wir streben danach, eine Serverplattform mit schnellen Updates und hoher Stabilität zu sein.
- Wir bemühen uns, Funktionen und Leistung zu bieten, die denen von Mod-Plattformen in nichts nachstehen.
- Wir streben danach, eine frei anpassbare Plattform zu schaffen, die auch Patches von Vanilla anpassen kann.

## ⚙️ Hauptmerkmale <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Schnellste Updates**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) sorgt dafür, dass die enthaltenen Patches von Plazma immer auf dem neuesten Stand gehalten werden und somit die schnellsten Updates unter den auf Paper basierenden Serverplattformen bietet.
6. **Optimierte Standardkonfigurationsdateien**\
   Die standardmäßig angewendeten Konfigurationsdateien sind optimiert, sodass Sie keine eigenen Konfigurationsdateien optimieren müssen.
7. **Systematisches Multithreading**\
   Durch die Asynchronisierung von Systemmechanismen, die nichts mit dem Spielmechanismus zu tun haben, wird die Latenz reduziert und der Server optimiert.
8. **Blockieren der Verwendung unnötiger Speicherbereiche**\
   Durch Zusammenführen von Daten mit ähnlichen Werten wird der Speicherverbrauch reduziert.

## ✨ Anwendungsfälle <a href="#id-3" id="id-3"></a>

- **Plattform, die auch komplexe Plugins richtig verarbeitet**\
  Wird auf dem Server des Entwicklers [IPECTER](https://github.com/IPECTER) verwendet.\
  Eigenes Plugin, das mit NMS und Reflexion funktioniert, mit umfangreichen und komplexen Datapacks,\
  um mehr als 100 Spieler ohne Leistungsabfall zu bewältigen.
- **Plattform, die auch auf RPG-Servern eine schnelle Leistung beibehält**\
  Es konnte die Stabilität von 100 Spielern in einem einzelnen Cluster ohne TPS-Abfall aufrechterhalten werden,\
  und insgesamt 250 Spieler konnten auf 4 Clustern angenehm spielen.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Download

Auf der folgenden Seite können Sie Plazma herunterladen.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Möchten Sie detaillierte Informationen zur Unterstützung von Versionen erhalten?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot-Plugins und Paper, Pufferfish, Purpur-Plugins.

[^2]: Von Microsoft Corporation.

[^3]: Durch Deaktivieren des Chat-Meldesystems wird der Chat ausschließlich auf dem Server verarbeitet und das Chat-Tracking von Mojang verhindert.

[^4]: Zeit, die das Spiel angehalten wird, um die Systemmechanismen zu aktivieren.
