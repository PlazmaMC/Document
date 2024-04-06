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

1. **Starke Plugin-Ökologie**\
   Dank der Basis von [Paper](https://github.com/PaperMC/Paper) funktionieren die meisten im Internet verfügbaren [aktuellen Plugins](#user-content-fn-1)[^1] einwandfrei.
2. **Optimierte Konfiguration ohne Setup**\
   Alle Patches von [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sind enthalten und bieten optimale Leistung durch interne Optimierungen und integrierte Mods.
3. **Anpassbares Spiel nach Ihren Wünschen**\
   [Purpur](https://github.com/PurpurMC/Purpur) in Plazma ermöglicht die Änderung der allgemeinen Spielattribute.
4. **Sicherer Spielserver**\
   [Keine Chat-Berichte](https://github.com/Aizistral-Studios/No-Chat-Reports) sind enthalten, sodass ab 1.19 das hinzugefügte [Mojang](#user-content-fn-2)[^2] [Chat-Meldesystem](#user-content-fn-3)[^3] deaktiviert werden kann und der Diagnose-Informationssammler vollständig entfernt wird, um auf einem sicheren Server ohne Verfolgung spielen zu können.
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
  Plazma wird auf dem Server des Entwicklers [IPECTER](https://github.com/IPECTER) verwendet. Mit eigenen Plugins, die mit NMS und Reflexion arbeiten, und einer Vielzahl komplexer Datapacks kann die Plattform problemlos mehr als 100 Spieler ohne Leistungsabfall bewältigen.
- **Plattform mit schneller Leistung auch in RPG-Servern**\
  In einem einzigen Cluster konnten 100 Spieler ohne TPS-Verlust stabil gehalten werden, und auf 4 Clustern konnten insgesamt 250 Spieler angenehm spielen.
- **Plattform, die im Chunk/Entity-Bereich leuchtet**\
  Durch den Wechsel von Purpur zu Plazma auf einem Survival-Server, bei dem es zu Verzögerungen bei der Verarbeitung von Chunks und Entities kam, konnten die meisten Verzögerungen reduziert werden.
- **Von vielen Streamern gewählte Plattform**\
  Die Plattform wird von vielen bekannten Streamern als Bucket für ihre Zuschauer verwendet.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Realtime Plasma User Trend</p></figcaption>
</figure>

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
