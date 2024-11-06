---
description: Erfahren Sie mehr über Startargumente und Systemeigenschaften.
---

# 🎛️ Argumente und Eigenschaften

Die Startargumente und Systemeigenschaften sind Werte, die an den Befehl angehängt werden, der zur Ausführung von Plazma verwendet wird[^1], und beeinflussen insgesamt die Funktionsweise von Plazma.

[Anweisungsposition](#user-content-fn-2)[^2] wird in **Startargumente** und **Systemeigenschaften** unterteilt.

***

## Systemeigenschaft <a href="#id-1" id="id-1"></a>

Systemeigenschaften werden vor dem Start von Plazma vor der Initialisierung in der JVM eingegeben.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Verwendung <a href="#id-1.1" id="id-1.1"></a>

Systemeigenschaften werden als Java-Befehlsargumente zwischen `java` und `-jar` eingegeben.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` zeigt an, dass das Argument nicht in die JVM integriert ist, sondern ein eigenes Argument für Plazma ist und

Wenn keine Werte für Eigenschaften eingegeben werden, wird der Wert auf [`true` festgelegt](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Standardwert**: `750`

Teilt Entitäten in mehrere Pakete auf, wenn sie den angegebenen Wert überschreiten.

#### `Paper.filterThreshold`

- **형태**: `Integer`
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

- **형태**: `Integer`
- **Standardwert**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Standardwert**: `80`

Legt die maximale Länge eines Textes auf einem Schild fest.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Standardwert**: `(Weltversion) + 1`

Legt die Version der zuerst zu initialisierenden Welt-Update-Informationen fest.

Nützlich, wenn eine große Anzahl von Chunks aktualisiert werden muss, aber in anderen Fällen nicht verwendet wird.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Standardwert**: `True`

Aktiviert die Verarbeitung von Kommentaren in YAML-Dateien standardmäßig.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Standardwert**: `30`

Wenn ein Spieler für die angegebene Zeit (in Sekunden) keine Daten sendet, wird der Spieler gekickt.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Konflikt**: `Plazma.disableConfigOptimization`

Stärkere Optimierung der anfänglichen Konfiguration.

Wenn aktiviert, wird der Server schneller und sicherer, kann jedoch das Gameplay stark beeinflussen.

#### `Plazma.disableConfigOptimization`

- **Typ**: `Boolean`
- **Standardwert**: `false`
- **Konflikt**: `Plazma.aggressiveOptimize`

Keine Optimierung der anfänglichen Konfiguration.

Führt zur Verwendung der Standardkonfiguration von Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Standardwert**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Typ**: `Boolean`
- **Standardwert**: `false`

Deaktiviert das Plazma-Branding und verwendet das standardmäßige Server-Favicon von Vanille.

#### `Plazma.useVanillaConfiguration`

- **Typ**: `Boolean`
- **Standardwert**: `false`
- **Konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Dies kann die Server-Sicherheit und Leistung erheblich beeinträchtigen.

Alle Probleme, die durch diese Eigenschaft entstehen, liegen in der Verantwortung des Serveradministrators.
{% endhint %}

Bietet die anfängliche Konfiguration mit den Standardwerten von Mojang an.

Hebt alle von Paper durchgeführten Sicherheitslückenpatches auf.

Sicherheitslückenpatches können in der Paper- oder Plazma-Konfiguration wieder aktiviert werden.

#### `Plazma.vanillaize`

- **Typ**: `Boolean`
- **Standardwert**: `true`
- **Konflikt**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Stellt die anfängliche Konfiguration näher an Vanille an.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Standardwert**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Standardwert**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Startet den Server mit der Demo-Welt.

#### `eraseCache`

Entfernt übrig gebliebene Cache-Dateien nach dem Welt-Upgrade.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Deaktiviert das grafische Benutzeroberflächenpanel.

#### `nojline`

Deaktivieren Sie JLine und verwenden Sie die Vanille-Konsole.

#### `online-mode`

- **Alias**: `o`
- **Standardwert**: `(Servereigenschaft)`

Wählen Sie aus, ob Spieler über den Mojang-Authentifizierungsserver überprüft werden sollen.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Standardwert**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Legt den Speicherort der deaktivierten PaperSpigot-Konfigurationsdatei fest.

Dies wird verwendet, um vorhandene Konfigurationen in eine neue Konfigurationsdatei zu migrieren und wird danach nicht mehr verwendet.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Standardwert**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Standardwert**: `plugins`

Legt den Speicherort des Plugin-Ordners fest.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Standardwert**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Standardwert**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Startet den Server im sicheren Modus, um einen vollständig Vanille-Status zu gewährleisten.

#### `server-ip`

- **Alias**: `h`, `host`
- **Standardwert**: `(Servereigenschaft)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: `Level 2` und höher sind ausgenommen.

[^14]: Internetprotokoll, IP.
