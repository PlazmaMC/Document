---
description: Erfahren Sie, wie Sie den Server anpassen können.
---

# 📶 Fortschritt machen

Der Grund, warum Plazma und nicht die offizielle Serverplattform von Mojang Studios verwendet wird, ist die Möglichkeit einer starken **Benutzeranpassung**.

Hier sind verschiedene Möglichkeiten, wie Plazma angepasst und genutzt werden kann.

## Konfigurationsänderung <a href="#id-1" id="id-1"></a>

Die grundlegendste Methode zur Anpassung von Plazma besteht darin, die Konfiguration zu ändern.

Plazma bietet leistungsstarke Konfigurationseinstellungen von Spielmechaniken bis hin zu Eigenschaften von Mobs.

Weitere Informationen zur Konfiguration von Plazma finden Sie auf der folgenden Seite.

{% content-ref url="../reference/configurations/" %}
[Konfigurationen](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**In einigen Datenpaketen]\(#user-content-fn-2)[^2] kann es beim ersten Anwenden vorkommen, dass es nicht ordnungsgemäß angewendet wird.**

In diesem Fall wird empfohlen, den Server **zweimal** neu zu starten.

{% endhint %}

Datapacks können bei jeder Aktualisierung von Minecraft leicht beschädigt werden.

Insbesondere wenn Datapacks vollständig beschädigt sind, kann der Server abstürzen. Daher ist es wichtig, vor dem Aktualisieren des Servers ausreichende Tests durchzuführen.

{% Hinweis-Stil="info" %}

**Geben Sie nach dem Startbefehl des Servers `safeMode` ein, um alle Datapacks zu deaktivieren, bevor Sie den Server starten.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safemode)

{% endhint %}

Die angewendeten Datapacks können mit dem Befehl `/datapack list` überprüft werden.

***

## Optimierung <a href="#id-4" id="id-4"></a>

Es wurden viele Optimierungspatches auf Plazma angewendet. 또한, Plazma가 처음으로 시작되면 자동으로
구성을 최적화 하므로 [시작하기](./README.md) 설명서를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우,
아래 설명서를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxies verbinden Server miteinander und ermöglichen es Spielern, Server ohne zusätzliche Arbeit zu wechseln oder
mit anderen Servern zu kommunizieren.

Weitere Informationen zur sicheren und korrekten Proxy-Konfiguration finden Sie auf der folgenden Seite.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Sicherheit <a href="#id-5" id="id-5"></a>

Minecraft hat sich zu einem Mod entwickelt, der es einfach macht, [Schwachstellenangriffsmaschinen](#user-content-fn-3)[^3] auch online zu bekommen.

Obwohl die meisten Schwachstellen, die in normalen Spielen ausgeführt werden können, [standardmäßig blockiert sind](#user-content-fn-4)[^4],
ist es möglich, Schwachstellen durch Drittanbieter-Loader anzugreifen.

Daher wird empfohlen, wenn der Server öffentlich zugänglich ist, Anti-Cheat-Plugins zu installieren, um die Nutzung von Schwachstellen zu blockieren,
und Proxies, automatische Neustarts, Backups usw. zu konfigurieren, damit der Server schnell wiederhergestellt werden kann, wenn er abstürzt.

### Berechtigungseinstellung <a href="#id-5.1" id="id-5.1"></a>

Einige Admin-Befehle von Plugins können Schwachstellen aufweisen, wenn die Berechtigungen nicht ordnungsgemäß festgelegt sind.

Es wird empfohlen, Berechtigungsverwaltungs-Plugins wie
[LuckPerms](https://luckperms.net/) zu verwenden, um die Rechte von normalen Benutzern einzuschränken.

### X-Ray-Blockierung <a href="#id-5.2" id="id-5.2"></a>

X-Ray ist eine der Schwachstellen, die selbst von grundlegenden Optimierungsclients leicht genutzt werden können.

Plazma bietet eine Konfiguration, um X-Ray standardmäßig zu blockieren.

Weitere Informationen zur X-Ray-Blockierungsmethode finden Sie auf der folgenden Seite.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

Wenn nur bestimmte Benutzer auf den Server zugreifen können sollen, ist es empfehlenswert, [Ngrok](./README.md#id-6.2) zu verwenden, um eine [verschleierte Serveradresse zu verwenden](#user-content-fn-5)[^5] oder
eine Whitelist festzulegen, um zu verhindern, dass andere Spieler auf den Server zugreifen können.

In der Serverkonsole können Sie mit `/whitelist add <Spieler>` den Zugriff des Spielers erlauben oder
mit `/whitelist remove <Spieler>` den Zugriff des Spielers erneut verweigern.

Verwenden Sie `/whitelist query`, um die autorisierten Spieler anzuzeigen.

***

[^1]: Oder Minecraft: Bedrock Edition Add-ons.

[^2]: Hinzufügen von Kreaturen usw.

[^3]: Im Allgemeinen als "Hacks" bezeichnet.

[^4]: In Fällen von nicht optimierten Konfigurationen, veralteten Plazma-Versionen oder neu entdeckten Schwachstellen kann es sein, dass sie nicht blockiert sind.

[^5]: Spieler stellen über den Ngrok-Proxyserver eine Verbindung zum Server her, und die bei jedem Neustart ausgegebene Ngrok-Adresse ändert sich.
