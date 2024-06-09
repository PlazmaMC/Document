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

1. **Starke Plugin-Ökosystem**\
   [Basiert auf Paper](https://github.com/PaperMC/Paper),
   sodass die meisten [aktuellen Plugins](#user-content-fn-1)[^1] aus dem Internet ordnungsgemäß funktionieren.
2. **Keine Konfiguration erforderlich**\
   [Alle Pufferfish-Patches](https://github.com/pufferfish-gg/Pufferfish) sind enthalten,
   mit einigen internen Optimierungen und Modifikationen für beste Leistung.
3. **Spiel nach Belieben anpassen**\
   [Purpur in Plazma enthalten](https://github.com/PurpurMC/Purpur), ermöglicht die Anpassung
   der allgemeinen Eigenschaften des Spiels.
4. **Sicherer Spielserver**\
   [Keine Chat-Berichte](https://github.com/Aizistral-Studios/No-Chat-Reports) sind ab Version 1.19 enthalten, um das [Chat-Meldesystem](#user-content-fn-3)[^3] von [Mojang](#user-content-fn-2)[^2] zu deaktivieren,\
   damit der Diagnoseinformationscollector vollständig entfernt wird und Sie auf einem sicheren Server ohne Verfolgung spielen können.
5. **Schnellste Updates**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) sorgt dafür, dass die enthaltenen Patches von Plazma immer auf dem neuesten Stand gehalten werden und somit die schnellsten Updates unter den auf Paper basierenden Serverplattformen bietet.
6. **Optimierte Standardkonfigurationsdateien**\
   Die standardmäßig angewendeten Konfigurationsdateien sind optimiert, sodass Sie keine eigenen Konfigurationsdateien optimieren müssen.
7. **Systematisches Multithreading**\
   Durch die Asynchronisierung von Systemmechanismen, die nichts mit dem Spielmechanismus zu tun haben, wird die Latenz reduziert und der Server optimiert.
8. **Blockieren der Verwendung unnötiger Speicherbereiche**\
   Durch Zusammenführen von Daten mit ähnlichen Werten wird der Speicherverbrauch reduziert.

#### Möchten Sie mehr über Plazma erfahren? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Anwendungsfälle <a href="#id-3" id="id-3"></a>

- **Plattform, die auch komplexe Plugins richtig verarbeitet**\
  Wird auf dem Server des Entwicklers [IPECTER](https://github.com/IPECTER) verwendet.\
  Eigenes Plugin, das mit NMS und Reflexion funktioniert, mit umfangreichen und komplexen Datapacks,\
  um mehr als 100 Spieler ohne Leistungsabfall zu bewältigen.
- **Plattform, die auch auf RPG-Servern eine schnelle Leistung beibehält**\
  Es konnte die Stabilität von 100 Spielern in einem einzelnen Cluster ohne TPS-Abfall aufrechterhalten werden,\
  und insgesamt 250 Spieler konnten auf 4 Clustern angenehm spielen.
- **Plattform, die Licht in Chunk/Entity zeigt**\
  Durch den Wechsel von Purpur zu Plazma für den Server eines Survival-Servers, der zuvor Verzögerungen beim Verarbeiten von Chunks und Entities hatte, konnten die meisten Verzögerungen reduziert werden.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Echtzeit-Plazma-Benutzerentwicklung">
</a>

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
