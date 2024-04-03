---
description: Erfahren Sie, wie Sie den Server anpassen können.
---

# 🎨 Anpassung für Benutzer

Der Grund, warum Plazma und nicht die offizielle Serverplattform von Mojang Studios verwendet wird, ist die Möglichkeit einer starken **Benutzeranpassung**.

Hier sind verschiedene Möglichkeiten, wie Plazma angepasst und genutzt werden kann.

## Konfigurationsänderung <a href="#id-1" id="id-1"></a>

Die grundlegendste Methode zur Anpassung von Plazma besteht darin, die Konfiguration zu ändern.

Plazma bietet leistungsstarke Konfigurationseinstellungen von Spielmechaniken bis hin zu Eigenschaften von Mobs.

Weitere Informationen zur Konfiguration von Plazma finden Sie auf der folgenden Seite.

{% content-ref url="../reference/configurations/" %}
[Konfigurationen](../reference/configurations/)
{% endcontent-ref %}

## Verwendung von Plugins <a href="#id-2" id="id-2"></a>

{% Hinweis-Stil="Erfolg" %}

**Plazma unterstützt alle auf Papier basierenden Plugins ordnungsgemäß.**

Für Spigot-Plugins kann es aufgrund der Mapping-Änderungen von Paper ab Version 1.20.5 zu einigen Fehlfunktionen kommen, jedoch funktionieren die meisten Plugins, die auf Paper basieren, wie Paper, Pufferfish und Purpur, auch in Plazma einwandfrei. Sollte ein Plugin nicht ordnungsgemäß funktionieren, handelt es sich um einen Fehler in Plazma, daher melden Sie dies bitte sofort [hier](../diagnosis/plugins.md).

{% endhint %}

Dies ist der Hauptgrund für die Verwendung von Plazma und gleichzeitig die leistungsstärkste Methode zur Anpassung von Plazma.
Das starke Plugin-Ökosystem von Plazma ermöglicht es Ihnen, den Server einfach anzupassen.

Es gibt verschiedene Möglichkeiten, Plugins zu finden und herunterzuladen. Einige Plugins werden in öffentlichen Repository-Diensten hochgeladen, während andere auf GitHub oder eigenen Websites hochgeladen werden.

{% Hinweis-Stil="Vorsicht" %}

**Plugins können direkt auf das System zugreifen!**

Verwenden Sie Dienste wie VirusTotal, um die Sicherheit von Plugins vor der Anwendung zu überprüfen, oder laden Sie Plugins von vertrauenswürdigen Diensten herunter.

{% endhint %}

Es gibt verschiedene Dienste zum Herunterladen von Plugins. Davon durchlaufen Services wie [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hangar](https://hangar.papermc.io/) eine Prüfung, bevor Plugins hochgeladen werden, um sicherzustellen, dass nur sichere Plugins verbreitet werden.

### Plugin-Anwendung <a href="#id-2.1" id="id-2.1"></a>

Wenn Sie ein Plugin heruntergeladen haben, ist es nun an der Zeit, das Plugin anzuwenden.

1. Plugins sind als `.jar` oder `Java-Ausführbare Datei` verfügbar.\
   Einige Plugins sind möglicherweise als komprimierte Dateien verpackt. In diesem Fall entpacken Sie die Datei und verwenden Sie die Datei, die `bukkit`, `spigot` oder `paper` im Namen enthält, sowie die Datei mit `fat`.
2. Legen Sie die heruntergeladene Datei in den Ordner `plugins` im Serververzeichnis und starten Sie den Server (neu).
3. Wenn Plazma gestartet wird, werden neue Inhalte in der Konsole ausgegeben.
   Dies bedeutet, dass Plazma das Plugin ordnungsgemäß geladen hat.
4. Auch wenn Plazma das Plugin ordnungsgemäß geladen hat, könnte es sein, dass das Plugin nicht gestartet wurde.
   Mit dem Befehl `/plugins` können Sie die aktuell geladenen Plugins auf dem Server abrufen.
   Wenn der Name des installierten Plugins nicht <mark style="background-color:red;">rot</mark>, sondern <mark style="background-color:green;">grün</mark> ist, wurde das Plugin ordnungsgemäß geladen.

Wenn ein Plugin nicht ordnungsgemäß geladen wurde, finden Sie auf der folgenden Seite Lösungen für das Problem.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Datapack verwenden <a href="#id-3" id="id-3"></a>

Datapacks sind eine Möglichkeit der Anpassung, die Minecraft standardmäßig bietet und ähnlich wie [Resource Packs](#user-content-fn-1)[^1] funktionieren.

Mit Datapacks können Sie neue Kreaturen und Herausforderungen im Spiel hinzufügen.

{% Hinweis-Stil="Vorsicht" %}

**Datapacks können die Welt beschädigen!**

Einige defekte Datapacks können die Welt beschädigen, was nicht rückgängig gemacht werden kann.

Daher wird empfohlen, die Welt vor dem Anwenden von Datapacks zu sichern.

{% endhint %}

Datapacks können auch von verschiedenen Diensten wie [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) heruntergeladen werden.

Nachdem Sie Datapacks heruntergeladen haben, können Sie sie im Ordner `datapacks` im Weltverzeichnis des Servers platzieren, um sie anzuwenden.
Erstellen Sie den Ordner, falls er nicht vorhanden ist, und fügen Sie die Datapacks hinzu.

{% Hinweis Stil="Warnung" %}

**Einige [Datapacks](#user-content-fn-2)[^2] funktionieren möglicherweise nicht ordnungsgemäß, wenn sie zum ersten Mal angewendet werden.**

In diesem Fall wird empfohlen, den Server **zweimal** neu zu starten.

{% endhint %}

Datapacks können bei jeder Aktualisierung von Minecraft leicht beschädigt werden.

Insbesondere wenn Datapacks vollständig beschädigt sind, kann der Server abstürzen. Daher ist es wichtig, vor dem Aktualisieren des Servers ausreichende Tests durchzuführen.

{% Hinweis-Stil="info" %}

**Geben Sie nach dem Startbefehl des Servers `safeMode` ein, um alle Datapacks zu deaktivieren, bevor Sie den Server starten.**

Weitere Informationen finden Sie unter `Referenz > Argumente und Eigenschaften`.](../reference/arguments.md)

{% endhint %}

Die angewendeten Datapacks können mit dem Befehl `/datapack list` überprüft werden.

***

[^1]: Oder Minecraft: Bedrock Edition Add-ons.

[^2]: Hinzufügen von Kreaturen usw.
