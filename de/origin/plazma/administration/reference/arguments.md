---
description: Erfahren Sie mehr über Startargumente und Systemeigenschaften.
---

# 🎛️ Argumente und Eigenschaften

Die Startargumente und Systemeigenschaften sind Werte, die an den Befehl angehängt werden, der zur Ausführung von Plazma verwendet wird[^1], und beeinflussen insgesamt die Funktionsweise von Plazma.

[Anweisungsposition](#user-content-fn-2)[^2] wird in **Startargumente** und **Systemeigenschaften** unterteilt.

***

## Systemeigenschaft <a href="#id-1" id="id-1"></a>

Systemeigenschaften werden vor dem Start von Plazma vor der Initialisierung in der JVM eingegeben.

{% Hinweis Stil="Warnung" %}

**Wenn Sie Systemeigenschaften ändern, kann sich das Verhalten von Plazma und JVM ändern und sich erheblich auf das Spiel auswirken!**

Wenn Sie nicht sicher sind, welche Rolle jede Systemeigenschaft spielt, **verwenden Sie sie auf keinen Fall!**

{% endhint %}

### Verwendung <a href="#id-1.1" id="id-1.1"></a>

Systemeigenschaften werden als Java-Befehlsargumente zwischen `java` und `-jar` eingegeben.

Wenn Sie z.B. die Systemspezialeigenschaft `Plazma.dummyProperty` anwenden möchten, wird der Wert `37` für die nächste Eigenschaft eingegeben und Plazma initialisiert.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` zeigt an, dass das Argument nicht in die JVM integriert ist, sondern ein eigenes Argument für Plazma ist und

Wenn keine Werte für Eigenschaften eingegeben werden, wird der Wert auf [`true` festgelegt](#user-content-fn-3)[^3].

{% Hinweis-Stil="info" %}

**Die Paperweight-Serverserie verwendet Punkte in den Attributnamen, um die Systemeigenschaften für jede Plattform zu unterscheiden.**

In einigen Terminals wie Windows Powershell können diese Argumente möglicherweise nicht akzeptiert werden, daher müssen Sie `"` am Anfang und Ende der Argumente [hinzufügen](#user-content-fn-4)[^4].

{% endhint %}

### Alle Systemeigenschaften <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Aktualisiert das verwendete veraltete Schildformat.

#### `debug.entities`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Aktiviert Debug-Logs für Entitätsinformationen.

#### `debug.rewriteForIDE`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert die NMS-Revision, um Debug-Informationen in der IDE korrekt zu laden und aktualisiert automatisch die interne Versionsinformation.

#### `disable.watchdog`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert das Watchdog-Warnsystem von Spigot.

#### `letMeReload`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert die Bestätigungsnachricht des `/reload`-Befehls.

{% hint style="danger" %}

**Der Befehl `/reload` ist äußerst instabil, daher liegt die Verantwortung für alle Probleme im Server nach der Verwendung von `/reload` beim Benutzer selbst.**

Wenn Sie ein Plugin-Entwickler sind und Ihr Plugin aktualisieren müssen, verwenden Sie anstelle von `/reload` das Hotswap.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert Plugins, die das Standard-Ein-/Ausgabesystem verwenden.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Typ**: `Boolean`
- **Standardwert**: `False`

Warnt, wenn veraltete Formatierungen in Chat-Komponenten erkannt werden.

#### `Paper.bypassHostCheck`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert die Überprüfung der Musterübereinstimmung des Servers, wenn ein Spieler eine Verbindung herstellt.

#### `Paper.debugDynamicMissingKeys`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Aktiviert Debug-Logs für fehlende Schlüssel in NBT-Objekten.

#### `Paper.debugInvalidSkullProfiles`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Aktiviert Debug-Logs für ungültige Schädelprofile.

Dies protokolliert alle fehlerhaften Schädelblöcke in der Welt mit ihren Positionen.

#### `Paper.disableChannelLimit`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert die Begrenzung der Anzahl von 128 Plug-in [Kanälen](#user-content-fn-5)[^5] pro Spieler.

#### `Paper.disableClassPrioritization`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert das Klassenpriorisierungssystem für Plugins.

Nützlich, wenn Probleme mit Plugin-Schatten auftreten.

#### `Paper.disableFlushConsolidate`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert das Netty Flush-Konsolidierungssystem.

#### `Paper.excessiveTELimit`

- **Typ**: `Integer`
- **Standardwert**: `750`

Teilt Entitäten in mehrere Pakete auf, wenn sie den angegebenen Wert überschreiten.

#### `Paper.filterThreshold`

- **Typ**: `Integer`
- **Standardwert**: `8192`

Legt die maximale Paketgröße fest, die der Server auf einmal empfangen kann.

#### `Paper.ignoreJavaVersion`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Deaktiviert die Java-Versionüberprüfung.

{% hint style="danger" %}

**Auf diese Weise kann JVM versuchen, auf nicht vorhandenen Code zuzugreifen!**

Dies kann zu dauerhaften Schäden an Dateien wie der Welt und zu einem Zusammenbruch des gesamten Spielmechanismus führen.

Alle Probleme, die durch diese Maßnahme entstehen, liegen in Ihrer Verantwortung, und Plamza leistet keine Unterstützung dafür.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Typ**: `Integer`
- **Standardwert**: `64`

Legt die Beschränkung des Plugin-Kanalnamens fest.

#### `Paper.maxSignLength`

- **Typ**: `Integer`
- **Standardwert**: `80`

Legt die maximale Länge eines Textes auf einem Schild fest.

#### `Paper.minPrecachedDatafixVersion`

- **Typ**: `Integer`
- **Standardwert**: `(Weltversion) + 1`

Legt die Version der zuerst zu initialisierenden Welt-Update-Informationen fest.

Nützlich, wenn eine große Anzahl von Chunks aktualisiert werden muss, aber in anderen Fällen nicht verwendet wird.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Standardwert**: `True`

Aktiviert die Verarbeitung von Kommentaren in YAML-Dateien standardmäßig.

#### `Paper.playerConnection.keepAlive`

- **Typ**: `Integer`
- **Standardwert**: `30`

Wenn ein Spieler für die angegebene Zeit (in Sekunden) keine Daten sendet, wird der Spieler gekickt.

In der Regel sendet das [Spiel](#user-content-fn-7)[^7] kontinuierlich [Heartbeat-Signale](#user-content-fn-8)[^8] an den Server, daher wird ein Spieler nicht ausgeschlossen, aber wenn das Spiel nicht antwortet, wird angenommen, dass das Spiel abgestürzt ist und der Server den Spieler nicht mehr behandelt und ihn ausschließt.

#### `Paper.skipServerPropertiesComments`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Ignoriert Kommentare in den Servereigenschaften.

#### `Paper.debug-sync-loads`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Aktiviert Debug-Logs für synchronisierte Chunk-Loads.

#### `Paper.enable-sync-chunk-writes`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Aktiviert das Standard-Chunk-Schreibsystem von Minecraft.

Dies führt dazu, dass jeder Chunk nacheinander gespeichert wird, was zu erheblicher Leistungseinbuße führt.

#### `Paper.explicit-flush`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Aktiviert das explizite Flushen des Netzwerkkanals.

#### `Paper.strict-thread-checks`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Protokolliert immer Fehler, die nicht im Hauptthread auftreten.

#### `Paper.tickList-warn-on-excessive-delay`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Gibt eine Warnung aus, wenn geplante Aufgaben eine übermäßige Verzögerung aufweisen.

#### `Paperclip.patchOnly`

- **Typ**: `Boolean`
- **Standardwert**: `False`

Wendet nur Patches an, ohne den Server zu starten, wenn das Standardausführungsprogramm verwendet wird.

#### `Plazma.aggressiveOptimize`

- **Typ**: `Boolean`
- **Standardwert**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Typ**: `Boolean`
- **Standardwert**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Standardwert**: `false`

Unterdrückt die Warnung, die beim Initialisieren von Plazma angezeigt wird, [aus](#user-content-fn-11)[^11].

#### `Plazma.useVanillaFavicon`

- **Typ**: `Boolean`
- **Standardwert**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Typ**: `Boolean`
- **Standardwert**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

{% Hinweis-Stil="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

{% hint style="danger" %}

**해당 속성은 패치된 모든 취약점을 되돌립니다!**

이는 서버 안전 및 성능에 크게 영향을 줄 수 있습니다.

해당 속성을 사용하여 발생하는 모든 문제는 서버 관리자에게 있습니다.

{% endhint %}

초기 구성을 Mojang에서 제공하는 기본값으로 제공합니다.

이는 Paper에서 적용한 모든 취약점 패치를 비활성화 합니다.

취약점 패치는 Paper 구성 또는 Plazma 구성에서 다시 활성화 할 수 있습니다.

#### `Plazma.vanillaize`

- **Typ**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% Hinweis-Stil="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Das <a href="#id-1.3" id="id-1.3"></a> Eigenschaft wurde eingestellt

Die folgenden Systemeigenschaften sind eingestellt

#### `timings.bypassMax`

- **Typ**: `Boolean`
- **Standardwert**: `false`
- **Eingestellt**: Timings wurden seit der Entfernung aus Plazma

Entscheidet, ob der Wert, der an Aikars Timings API gesendet werden kann, überschritten werden kann.

Wenn dies trotzdem nicht von der API behandelt wird, wird eine Ratenbegrenzung angewendet.

***

## Startargument <a href="#id-2" id="id-2"></a>

Das Startargument wird nach `-jar *.jar` eingegeben und wird von Plazma initialisiert und gemeinsam verarbeitet.

### Verwendung <a href="#id-2.1" id="id-2.1"></a>

Systemeigenschaften werden als Programmargumente nach `-jar *.jar` eingegeben.

Wenn beispielsweise das Startargument `nogui` angewendet werden soll,\
geben Sie wie folgt ein, damit Plazma das Argument `nogui` während der Initialisierung verarbeitet.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Gesamtes Startargument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Standardwert**: `bukkit.yml`

Legt Namen und Position der [Bukkit-Konfigurationsdatei](../reference/configurations/bukkit.md) fest.

#### `command-settings`

- **Alias**: `c`
- **Standardwert**: `commands.yml`

Legt Namen und Position der [Bukkit-Befehlskonfigurationsdatei](../reference/configurations/bukkit.md) fest.

#### `config`

- **Alias**: `c`
- **Standardwert**: `server.properties`

Legt Namen und Position der [Servereigenschaften](../reference/configurations/property.md) fest.

#### `demo`

Startet den Server mit der Demo-Welt.

#### `eraseCache`

Entfernt übrig gebliebene Cache-Dateien nach dem Welt-Upgrade.

#### `forceUpgrade`

Ignoriert die Version und führt ein [erzwungenes Upgrade](#user-content-fn-12)[^12] der Welt durch.

#### `help`

- **Alias**: `?`

Gibt alle Startargumente und Erklärungen von Plazma aus.

#### `initSettings`

Erstellt nur die Konfigurationsdatei und beendet den Server.

#### `jfrProfile`

Aktiviert die JFR-Profilerstellung.

#### `max-players`

- **Alias**: `s`, `size`
- **Standardwert**: `(Servereigenschaft)`

Legt die maximale Anzahl von [Spielern](#user-content-fn-14)[^14] fest, die erlaubt sind.

#### `nogui`

Deaktiviert das grafische Benutzeroberflächenpanel.

#### `nojline`

Deaktivieren Sie JLine und verwenden Sie die Vanille-Konsole.

#### `online-mode`

- **Alias**: `o`
- **Standardwert**: `(Servereigenschaft)`

Wählen Sie aus, ob Spieler über den Mojang-Authentifizierungsserver überprüft werden sollen.

**Bei Verwendung von Velocity oder anderen Proxys können Sanktionen gegen die [EULA](../getting-started/README.md#id-5) verhängt werden.**

#### `paper-settings`

- **Alias**: `paper`
- **Standardwert**: `paper.yml`

{% Hinweis Stil="Warnung" %}

**Dieses Argument wurde nach Version 1.19.4 eingestellt.**

{% endhint %}

Legt den Speicherort der deaktivierten PaperSpigot-Konfigurationsdatei fest.

Dies wird verwendet, um vorhandene Konfigurationen in eine neue Konfigurationsdatei zu migrieren und wird danach nicht mehr verwendet.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standardwert**: `config`

Legt den Namen und Speicherort des Ordners fest, in dem die [Paper-Konfigurationsdatei](../reference/configurations/paper/README.md) gespeichert ist.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Legt den Namen und Speicherort des Ordners fest, in dem die [Plazma-Konfigurationsdatei](../reference/configurations/plazma/README.md) gespeichert ist.

#### `plugins`

- **Alias**: `p`
- **Standardwert**: `plugins`

Legt den Speicherort des Plugin-Ordners fest.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardwert**: `pufferfish.yml`

Legt Namen und Speicherort der [Pufferfish-Konfigurationsdatei](../reference/configurations/pufferfish.md) fest.

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardwert**: `purpur.yml`

Legt Namen und Speicherort der [Purpur-Konfigurationsdatei](../reference/configurations/purpur/README.md) fest.

#### `safeMode`

Startet den Server im sicheren Modus, um einen vollständig Vanille-Status zu gewährleisten.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standardwert**: `(Servereigenschaft)`

Legt den Hostnamen des Servers oder die [Internetprotokoll](#user-content-fn-13)[^13]-Adresse fest.

#### `server-port`

- **Alias**: `p`, `port`
- **Standardwert**: `(Servereigenschaft)`

Legt den Port des Servers fest.

#### `server-name`

- **Standardwert**: `Ein Plazma-Server`

Legt den Namen des Servers fest.

#### `spigot-settings`

- **Alias**: `S`
- **Standardwert**: `spigot.yml`

Legt Namen und Speicherort der [Spigot-Konfigurationsdatei](../reference/configurations/spigot.md) fest.

#### `version`

- **Alias**: `v`

Gibt die Plazma-Version aus.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Standardwert**: `(Serverordner)`

Legt den Speicherort der Weltdateien fest.

#### `world-name`

- **Alias**: `w`, `world`
- **Standardwert**: `(Servereigenschaft)`

Legt den Namen der Weltdateien fest.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Die Verarbeitung von Argumenten ändert sich je nach angehängtem Ort.

[^3]: Wenn Sie beispielsweise `Plazma.iKnowWhatIAmDoing` auf `true` setzen möchten, funktioniert dies genauso, wenn Sie nur `-DPlazma.iKnowWhatIAmDoing` anstelle von `-DPlazma.iKnowWhatIAmDoing=true` eingeben.

[^4]: Zum Beispiel, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Event-Detektor.

[^6]: Event-Detektor.

[^7]: Client.

[^8]: Ein Signal, das anzeigt, dass der Server ordnungsgemäß mit dem Herzschlag verbunden ist.

[^9]: Mit der AFK-Kick-Funktion von Purpur können auch abwesende Spieler gekickt werden.

[^10]: Synchrones Chunk-Schreibsystem, Sync Chunk Write System.

[^11]: `WARNUNG! Plazma kann unerwartete Probleme verursachen, daher sollten Sie es vor der Verwendung auf einem öffentlichen Server gründlich testen.`

[^12]: Das `Welt-Optimieren` im Spiel funktioniert nach dem gleichen Prinzip.

[^13]: Internetprotokoll, IP.

[^14]: `Level 2` und höher sind ausgenommen.
