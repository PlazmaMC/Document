---
description: Erfahren Sie mehr über die Berechtigungen von Plazma.
---

# 🛡️ Berechtigungen

Berechtigungen sind ein einfaches Sicherheitstool, das den Bereich festlegt, in dem sich Server-Player interagieren können.

Um Berechtigungen ordnungsgemäß zu nutzen und einfach zu bearbeiten, müssen Sie Plugins wie [LuckPerms](https://luckperms.net) verwenden.

***

## Verständnis des Standardberechtigungssystems <a href="#id-1" id="id-1"></a>

In Minecraft gibt es grundlegende Verwaltungsrechtegruppen.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Spieler**\
   Normalerweise die Standardberechtigungsgruppe für alle Spieler.
2. **Vermittler**\
   Kann den Spawnschutz ignorieren.
3. **Welt-Administrator**\
   Kann alle Befehle und Befehlsblöcke im Zusammenhang mit der Weltverwaltung verwenden.\
   Standardberechtigungsgruppe für Datapacks und Befehlsblöcke.
4. **Administrator**\
   Kann alle Befehle im Zusammenhang mit der Spielerverwaltung verwenden.
5. **Hauptadministrator**\
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

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, die auf einem Entity reiten, die Spezialfähigkeiten des Entity zu nutzen.

Nicht alle Spezialfähigkeiten aller Entities sind verfügbar. Für eine Liste aller verfügbaren Spezialfähigkeiten siehe unten.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Dadurch können beide Seiten Leistungsverbesserungen erfahren.

> Für Informationen zur X-Ray-Einstellung siehe die folgende Seite.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Standardmäßig**: `Nichts`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Standardmäßig**: `Nichts`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Standardmäßig**: `Nichts`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung von [MiniMessage-Tags](https://docs.advntr.dev/minimessage/format.html) auf dem Amboss.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Standardmäßig**: `Nichts`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Standardmäßig**: `Nichts`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Standardmäßig**: `Nichts`

Ändert die Größe der Endertruhe.

Für `(NumberString)` können `one`, `two`, `three`, `four`, `five`, `six` eingegeben werden.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Standardmäßig**: `Nichts`

Erlaubt es, dass der Totem der Unsterblichkeit auch funktioniert, wenn er sich im Inventar befindet.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, die Verbindung zu einem vollen Server herzustellen, ohne die Spielerbeschränkung zu beachten.

#### `purpur.mending_shift_click`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, ein gehaltenes Element zu reparieren, wenn sie `sneak + right-click` ausführen.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, Spawner zu platzieren.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Standardmäßig**: `Nichts`

Bewirkt, dass Spieler sofort teleportiert werden, wenn sie das Nether-Portal benutzen.

#### `purpur.sign.color`

- **Standardmäßig**: `Nichts`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Standardmäßig**: `Nichts`

Ermöglicht die Verwendung des Verwirrungscode `(&o)` auf Schildern.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Standardmäßig**: `Nichts`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, durch `Interaktion mit einer Schere` eine TNT-Explosion zu verhindern.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Geplante Berechtigung

#### `plazma.bypass.ncr-require`

- **Standardmäßig**: `Nichts`

Ermöglicht es Spielern, sich auch ohne installierten [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) Modus zu verbinden.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Zum Beispiel: `ender_dragon`
