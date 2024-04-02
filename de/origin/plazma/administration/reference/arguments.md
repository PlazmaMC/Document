---
description: Erfahren Sie mehr über Startargumente und Systemeigenschaften.
---

# 🎛️ Argumente und Eigenschaften

Startvariablen und Systemeigenschaften sind Werte, die an [Plazma-Befehle](#user-content-fn-1)[^1] angehängt werden, um Werte hinzuzufügen, die nach dem Start von Plazma nicht mehr geändert werden können.

Je nach [Anhängestelle des Befehls](#user-content-fn-2)[^2] werden sie in **Startargumente** und **Systemeigenschaften** unterteilt.

***

## Systemeigenschaft <a href="#id-1" id="id-1"></a>

Systemeigenschaften werden vor dem Start von Plazma vor der Initialisierung in der JVM eingegeben.

{% Hinweis Stil="Warnung" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### Verwendung <a href="#id-1.1" id="id-1.1"></a>

Systemeigenschaften werden als Java-Befehlsargumente zwischen `java` und `-jar` eingegeben.

Wenn Sie beispielsweise die Systemeigenschaft `Plazma.dummyProperty` anwenden möchten, wird der Wert `37` wie folgt eingegeben, um die nachfolgende Eigenschaft zu initialisieren.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` zeigt an, dass das Argument nicht in die JVM integriert ist, sondern ein eigenes Argument für Plazma ist und

wenn kein Wert angegeben wird, wird der Wert auf [`true` festgelegt.](#user-content-fn-3)[^3]

{% Hinweis-Stil="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

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

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

Deaktiviert die Begrenzung der Anzahl von Plugin-Kanälen pro Spieler auf 128.

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

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Dies kann zu dauerhaften Schäden an Dateien wie der Welt und zu einem Zusammenbruch des gesamten Spielmechanismus führen.

Alle Probleme, die durch diese Maßnahme entstehen, liegen in Ihrer Verantwortung, und Plamza leistet keine Unterstützung dafür.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Typ**: `Integer`
- **Standardwert**: `64`

Legt die Beschränkung für den Namen des Plugin-Kanals fest.

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

Normalerweise sendet das Spiel[^7] weiterhin Herzschläge an den Server, sodass kein Kick erfolgt, wenn das Spiel nicht antwortet, wird angenommen, dass es abgestürzt ist und der Spieler wird gekickt.

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

{% Hinweis Stil="Warnung" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Es werden strengere Konfigurationsoptimierungen angewendet, die beim ersten Start gelten.

Wenn aktiviert, wird der Server schneller und sicherer, aber es kann einige Gimmicks blockieren oder sich stark auf das Spielerlebnis auswirken.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Standardwert**: `false`

Unterdrückt die Warnmeldung[^11], die beim Initialisieren von Plazma angezeigt wird.

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

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

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
