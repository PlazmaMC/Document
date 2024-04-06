---
description: Erfahren Sie mehr über die Berechtigungen von Plazma.
---

# 🛡️ Berechtigungen

Berechtigungen sind ein einfaches Sicherheitstool, das den Bereich festlegt, in dem sich Server-Player interagieren können.

Um Berechtigungen ordnungsgemäß zu nutzen und einfach zu bearbeiten, müssen Sie Plugins wie [LuckPerms](https://luckperms.net) verwenden.

***

## Verständnis des Standardberechtigungssystems <a href="#id-1" id="id-1"></a>

In Minecraft gibt es grundlegende Verwaltungsrechtegruppen.

Sie können Berechtigungen für [Operator](#user-content-fn-1)[^1] und Befehlsblöcke festlegen und in den [Servereigenschaften](configurations/property.md) ändern.

0. **Spieler**\
   Normalerweise die Standardberechtigungsgruppe für alle Spieler.
1. **Vermittler**\
   Kann den Spawnschutz ignorieren.
2. **Welt-Administrator**\
   Kann alle Befehle und Befehlsblöcke im Zusammenhang mit der Weltverwaltung verwenden.\
   Standardberechtigungsgruppe für Datapacks und Befehlsblöcke.
3. **Administrator**\
   Kann alle Befehle im Zusammenhang mit der Spielerverwaltung verwenden.
4. **Hauptadministrator**\
   Kann alle Befehle einschließlich Serververwaltung verwenden.\
   Standardberechtigungsgruppe für Konsole und Operatoren.

***

## Berechtigungen einstellen <a href="#id-2" id="id-2"></a>

***

## Alle Berechtigungen <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, sich zu ducken und mit Entitäten zu interagieren, um auf sie zu steigen.

Wenn Sie auf eine Entität steigen, können Sie ihre Bewegung mit den `Bewegungstasten` steuern und mit der `Sprungtaste` springen oder fliegen.

Der `(Namespaced Key)` ist die [Namespaced ID](#user-content-fn-2)[^2] der Entität.

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `(Entity) > reitbar` aktiviert ist.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, die auf einem Entity reiten, die Spezialfähigkeiten des Entity zu nutzen.

Nicht alle Spezialfähigkeiten aller Entities sind verfügbar. Für eine Liste aller verfügbaren Spezialfähigkeiten siehe unten.

{% Hinweis-Stil="info" %}

**Haben Sie Ideen für Spezialfähigkeiten?**

Veröffentlichen Sie Ihre Ideen auf [Plazma Discord](https://plazmamc.org/discord) oder [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Verfügbare Spezialfähigkeiten anzeigen</summary>

- **`crepper`**\
  Drücken Sie die `Sprungtaste`, um zu explodieren.\
  Wenn ein Spieler die Berechtigung `allow.powered.creeper` hat, kann er die `Sprungtaste` gedrückt halten, um aufzuladen.
- **`dolphin`**\
  Drücken Sie die `Sprungtaste`, um zu sprinten.
- **`phantom`**\
  Drücken Sie die `Sprungtaste`, um Feuerbälle zu schießen.
- **`wither`**\
  Durch `Interaktion` wird der Wither-Schädel abgefeuert.

</details>

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `(Entity) > reitbar` aktiviert ist.**

{% endhint %}

#### `bukkit.command.compass`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/credits (Spieler)`](commands.md#credits).

Durch Eingabe von `.other` hinter dem Berechtigungsnamen wird die Verwendung für andere Spieler ermöglicht.

#### `bukkit.command.demo`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/demo (Spieler)`](commands.md#demo).

Durch Eingabe von `.other` hinter dem Berechtigungsnamen wird die Verwendung für andere Spieler ermöglicht.

#### `bukkit.command.ping`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/ping (Spieler)`](commands.md#ping).

Durch Eingabe von `.other` hinter dem Berechtigungsnamen wird die Verwendung für andere Spieler ermöglicht.

#### `bukkit.command.ram`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/rambar (Spieler)`](commands.md#rambar).

Durch Eingabe von `.other` hinter dem Berechtigungsnamen wird die Verwendung für andere Spieler ermöglicht.

#### `bukkit.command.restart`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/tpsbar (Spieler)`](commands.md#tpsbar).

Durch Eingabe von `.other` hinter dem Berechtigungsnamen wird die Verwendung für andere Spieler ermöglicht.

#### `bukkit.command.timings`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/timings`](commands.md#timings).

{% Hinweis Stil="Warnung" %}

**Dieser Befehl wurde eingestellt.**

Für ähnliche Funktionen siehe [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- Standardmäßig: `Welt-Manager`

Erlaubt die Verwendung des Befehls `/gamemode (GameMode) (Spieler)`.

Durch Eingabe von `.other` hinter dem Berechtigungsnamen wird die Verwendung für andere Spieler ermöglicht.

#### `paper.antixray.bypass`

- **Standardmäßig**: `Nichts`

Wenn X-Ray Blockierung aktiviert ist, wird die Blockverwirrung für berechtigte Spieler nicht durchgeführt.

Dadurch können beide Seiten Leistungsverbesserungen erfahren.

> Für Informationen zur X-Ray-Einstellung siehe die folgende Seite.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standardmäßig**: `Nichts`

{% Hinweis Stil="Warnung" %}

Diese Berechtigung wird in Version 1.20.5 in `plazma.bypass.watchdog` geändert.

{% endhint %}

#### `purpur.anvil.color`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung von [Farbcodes](https://minecraft.wiki/w/Formatting_codes#Color_codes) auf dem Amboss.

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `anvil > allow-colors` aktiviert ist.**

{% endhint %}

#### `purpur.anvil.format`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung von [Styling-Codes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) auf dem Amboss.

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `anvil > allow-colors` aktiviert ist.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung von [MiniMessage-Tags](https://docs.advntr.dev/minimessage/format.html) auf dem Amboss.

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `anvil > allow-minimessages` aktiviert ist.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standardmäßig**: `Nichts`

Ermöglicht das Deaktivieren der `kursiv`-Eigenschaft auf dem Amboss durch den [`&r` Styling-Code](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `anvil > allow-colors` aktiviert ist.**

{% endhint %}

#### `purpur.book.color.sign`

- **Standardmäßig**: `Nichts`

Stellt sicher, dass beim Unterzeichnen von Büchern [Styling-Codes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) angewendet werden.

#### `purpur.bypassIdleKick`

- **Standardmäßig**: `Nichts`

Schließt den Spieler von der Ausweisung im Leerlauf aus.

#### `purpur.debug.f3n`

- Standardmäßig: `Welt-Manager`

Erlaubt es Spielern, den Spielmodus mit `F3 + N` zu ändern.

Funktioniert nicht, wenn die Berechtigung für diesen Spielmodus fehlt.

#### `purpur.drop.spawners`

- **Standardmäßig**: `Nichts`

Wenn Sie mit dem im Setup festgelegten Gegenstand einen Spawner abbauen, fällt der Spawner heraus.

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `gameplay-mechanics > silk-touch` aktiviert ist.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standardmäßig**: `Nichts`

Ändert die Größe der Endertruhe.

Für `(NumberString)` können `one`, `two`, `three`, `four`, `five`, `six` eingegeben werden.

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `ender_chest > six-rows` und `ender_chest > use-permissions-for-rows` aktiviert sind.**

{% endhint %}

#### `purpur.inventory_totem`

- **Standardmäßig**: `Nichts`

Erlaubt es, dass der Totem der Unsterblichkeit auch funktioniert, wenn er sich im Inventar befindet.

{% Hinweis-Stil="info" %}

**In der [Purpur-Weltkonfiguration](configurations/purpur/world.md) muss `totem-of-undying-works-in-inventory` aktiviert sein, damit es funktioniert.**

{% endhint %}

#### `purpur.joinFullServer`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, die Verbindung zu einem vollen Server herzustellen, ohne die Spielerbeschränkung zu beachten.

#### `purpur.mending_shift_click`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, ein gehaltenes Element zu reparieren, wenn sie `sneak + right-click` ausführen.

{% Hinweis-Stil="info" %}

**In der [Purpur-Weltkonfiguration](configurations/purpur/world.md) muss `shift-right-click-repairs-mending-points` aktiviert sein, damit es funktioniert.**

{% endhint %}

#### `purpur.place.spawners`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, Spawner zu platzieren.

{% Hinweis-Stil="info" %}

**In [Purpur World Configurations](configurations/purpur/world.md) funktioniert dies nur, wenn `gameplay-mechanics > silk-touch` aktiviert ist.**

{% endhint %}

#### `purpur.portal.instant`

- **Standardmäßig**: `Nichts`

Bewirkt, dass Spieler sofort teleportiert werden, wenn sie das Nether-Portal benutzen.

#### `purpur.sign.color`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung von [Farbcodes](https://minecraft.wiki/w/Formatting_codes#Color_codes) auf Schildern.

{% Hinweis-Stil="info" %}

**In der [Purpur-Weltkonfiguration](configurations/purpur/world.md) muss `sign > allow-colors` aktiviert sein, damit es funktioniert.**

{% endhint %}

#### `purpur.sign.magic`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung des Verwirrungscode `(&o)` auf Schildern.

{% Hinweis-Stil="info" %}

**In der [Purpur-Weltkonfiguration](configurations/purpur/world.md) muss `sign > allow-colors` aktiviert sein, damit es funktioniert.**

{% endhint %}

#### `purpur.sign.style`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung von [Formatierungscodes `(&o ausgenommen)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) auf Schildern.

{% Hinweis-Stil="info" %}

**In der [Purpur-Weltkonfiguration](configurations/purpur/world.md) muss `sign > allow-colors` aktiviert sein, damit es funktioniert.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, durch `Interaktion mit einer Schere` eine TNT-Explosion zu verhindern.

{% Hinweis-Stil="info" %}

**In der [Purpur-Weltkonfiguration](configurations/purpur/world.md) muss `defuse-tnt-change` größer oder gleich `0.0` sein, damit es funktioniert.**

{% endhint %}

### Geplante Berechtigung

#### `plazma.bypass.ncr-require`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, sich auch ohne installierten [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) Modus zu verbinden.

{% Hinweis-Stil="info" %}

**In der [Plazma-Weltkonfiguration](configurations/plazma/world.md) muss `no-chat-reports > require-install` aktiviert sein, damit es funktioniert.**

{% endhint %}

***

[^1]: Operator.

[^2]: Zum Beispiel: `ender_dragon`
