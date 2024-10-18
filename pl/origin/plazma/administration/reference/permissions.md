---
description: Sprawdź uprawnienia Plazmy.
---

# 🛡️ Uprawnienia

Uprawnienia to proste narzędzie bezpieczeństwa, które określa zakres interakcji graczy na serwerze.

Aby skutecznie korzystać z uprawnień i łatwo je modyfikować, należy użyć wtyczek takich jak [LuckPerms](https://luckperms.net).

***

## Zrozumienie podstawowego systemu uprawnień <a href="#id-1" id="id-1"></a>

W Minecraft dostępne są podstawowe grupy uprawnień administracyjnych.

Można ustawić uprawnienia dla [Administratorów](#user-content-fn-1)[^1] oraz bloków poleceń, a także je modyfikować w [konfiguracji serwera](configurations/property.md).

0. **Gracz**\
   To standardowa grupa uprawnień, przypisywana zazwyczaj wszystkim graczom.
1. **Mediator**\
   Może ignorować ochronę spawnu.
2. **Administrator świata**\
   Może używać wszystkich poleceń i bloków poleceń związanych z zarządzaniem światem.\
   To podstawowa grupa uprawnień stosowana do pakietów danych i bloków poleceń.
3. **Administrator**\
   Może używać wszystkich poleceń związanych z zarządzaniem graczami.
4. **Superadministrator**\
   Może używać wszystkich poleceń związanych z zarządzaniem serwerem.\
   To podstawowa grupa uprawnień stosowana do konsoli i administratorów.

***

## Ustawianie uprawnień <a href="#id-2" id="id-2"></a>

***

## Pełne uprawnienia <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Nazwany klucz)`

- **Domyślnie**: `Brak`

Pozwala graczom na wchodzenie na jednostki poprzez `kucnięcie i interakcję` z nimi.

Gdy gracz wsiądzie na jednostkę, może sterować jej ruchem za pomocą `klawiszy ruchu` oraz skakać lub latać za pomocą `klawisza skoku`.

W miejscu `(Nazwany klucz)` wprowadzany jest [Identyfikator przestrzeni nazw](#user-content-fn-2)[^2] jednostki.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `ridable` dla `(Jednostka)`.**

{% endhint %}

#### `allow.special.(Nazwany klucz)`

- **Domyślnie**: `Brak`

Pozwala graczom na korzystanie z specjalnych umiejętności jednostki, gdy ją prowadzą.

Nie wszystkie jednostki posiadają specjalne umiejętności. Sprawdź dostępne specjalne umiejętności poniżej.

{% hint style="info" %}

Masz pomysł na specjalną umiejętność?

Podziel się swoim pomysłem na [Discordzie Plazmy](https://plazmamc.org/discord) lub [Dyskusjach na GitHubie](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Zobacz dostępne obecnie specjalne umiejętności</summary>

- **`crepper`**\
  Po naciśnięciu `klawisza skoku` następuje wybuch.\
  Jeśli gracz ma uprawnienie `allow.powered.creeper`, może naładować wybuch, przytrzymując `klawisz skoku`.
- **`dolphin`**\
  Po naciśnięciu `klawisza skoku` następuje pędzenie.
- **`phantom`**\
  Po naciśnięciu `klawisza skoku` następuje wystrzelenie płomieni.
- **`wither`**\
  Po `interakcji` wystrzeliwuje głowę Wither'a.

</details>

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `ridable` dla `(Jednostka)`.**

{% endhint %}

#### `bukkit.command.compass`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/credits (Gracz)`](commands.md#credits).

Dodanie `.other` po nazwie uprawnienia pozwala na udzielenie innym graczom możliwości korzystania z niej.

#### `bukkit.command.demo`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/demo (Gracz)`](commands.md#demo).

Dodanie `.other` po nazwie uprawnienia pozwala na udzielenie innym graczom możliwości korzystania z niej.

#### `bukkit.command.ping`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/ping (Gracz)`](commands.md#ping).

Dodanie `.other` po nazwie uprawnienia pozwala na udzielenie innym graczom możliwości korzystania z niej.

#### `bukkit.command.ram`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/rambar (Gracz)`](commands.md#rambar).

Dodanie `.other` po nazwie uprawnienia pozwala na udzielenie innym graczom możliwości korzystania z niej.

#### `bukkit.command.restart`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/tpsbar (Gracz)`](commands.md#tpsbar).

Dodanie `.other` po nazwie uprawnienia pozwala na udzielenie innym graczom możliwości korzystania z niej.

#### `bukkit.command.timings`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Ta komenda została wycofana.**

Aby uzyskać informacje o podobnych komendach, odwiedź stronę [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(TrybGry)`

- **Domyślnie**: `Administrator świata`

Pozwala na użycie komendy [`/gamemode (TrybGry) (Gracz)`](commands.md#gamemode).

Dodanie `.other` po nazwie uprawnienia pozwala na udzielenie innym graczom możliwości korzystania z niej.

#### `paper.antixray.bypass`

- **Domyślnie**: `Brak`

Jeśli blokada X-Ray jest aktywna,
uprawnieni gracze nie będą poddawani zakłóceniom bloków X-Ray.

Dzięki temu obie strony mogą cieszyć się poprawioną wydajnością.

> Aby dowiedzieć się więcej na temat konfiguracji X-Ray, sprawdź poniższą stronę.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Domyślnie**: `Brak`

{% hint style="warning" %}

To uprawnienie zostanie zmienione na `plazma.bypass.watchdog` w wersji 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Domyślnie**: `Brak`

Pozwala na korzystanie z [kodów kolorów](https://minecraft.wiki/w/Formatting_codes#Color_codes) na kowadle.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `allow-colors` dla `kowadła`.**

{% endhint %}

#### `purpur.anvil.format`

- **Domyślnie**: `Brak`

Pozwala na korzystanie ze [styli formatowania](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na kowadle.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `allow-colors` dla `kowadła`.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Domyślnie**: `Brak`

Pozwala na korzystanie z tagów [MiniMessage](https://docs.advntr.dev/minimessage/format.html) na kowadle.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `allow-minimessages` dla `kowadła`.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Domyślnie**: `Brak`

Pozwala na wyłączenie `pochylenia tekstu` za pomocą kodu stylowania `&r` na kowadle.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `allow-colors` dla `kowadła`.**

{% endhint %}

#### `purpur.book.color.sign`

- **Domyślnie**: `Brak`

Po podpisaniu książki przez gracza, zastosowane zostaną [kody formatowania](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Domyślnie**: `Brak`

Wyłącza wydalanie gracza z powodu bezczynności.

#### `purpur.debug.f3n`

- **Domyślnie**: `Administrator świata`

Pozwala graczom na zmianę trybu gry za pomocą klawiszy `F3 + N`.

Funkcja ta nie działa, jeśli gracz nie ma odpowiednich uprawnień.

#### `purpur.drop.spawners`

- **Domyślnie**: `Brak`

Kopanie spawnerów za pomocą odpowiedniego przedmiotu powoduje ich upuszczenie.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `silk-touch` dla mechanik rozgrywki.**

{% endhint %}

#### `purpur.enderchest.rows.(LiczbaCiągZnaków)`

- **Domyślnie**: `Brak`

Zmienia rozmiar skrzyni Endera.

W miejscu `(LiczbaCiągZnaków)` można wprowadzić `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `six-rows` oraz `use-permissions-for-rows` dla `skrzyni enderowej`.**

{% endhint %}

#### `purpur.inventory_totem`

- **Domyślnie**: `Brak`

Pozwala na działanie totemów nieśmiertelności, gdy znajdują się w ekwipunku.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `totem-of-undying-works-in-inventory`.**

{% endhint %}

#### `purpur.joinFullServer`

- **Domyślnie**: `Brak`

Zezwala graczowi na zignorowanie limitu liczby graczy podłączonych.

#### `purpur.mending_shift_click`

- **Domyślnie**: `Brak`

Zezwala graczowi na naprawę trzymanego przedmiotu poprzez `przytrzymanie i interakcję`.

{% hint style="info" %}

\*\*Aby działało, należy włączyć `shift-right-click-repairs-mending-points` w **[Konfiguracjach świata Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.place.spawners`

- **Domyślnie**: `Brak`

Zezwala graczowi na instalację spawnów.

{% hint style="info" %}

**Działa tylko wtedy, gdy w [konfiguracji Purpur](configurations/purpur/world.md) jest włączone `silk-touch` dla mechanik rozgrywki.**

{% endhint %}

#### `purpur.portal.instant`

- **Domyślnie**: `Brak`

Pozwala graczowi natychmiastowo teleportować się po wejściu do Netheru.

#### `purpur.sign.color`

- **Domyślnie**: `Brak`

Zezwalaj na korzystanie z [kodów kolorów](https://minecraft.wiki/w/Formatting_codes#Color_codes) na tablicach informacyjnych.

{% hint style="info" %}

**Aby działało poprawnie, włącz `sign > allow-colors` w [konfiguracjach świata Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.magic`

- **Domyślnie**: `Brak`

Zezwól na użycie kodu zaciemnienia `(&o)` na tablicach informacyjnych.

{% hint style="info" %}

**Aby działało poprawnie, włącz `sign > allow-colors` w [konfiguracjach świata Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.style`

- **Domyślnie**: `Brak`

Zezwól na użycie [kodu stylizacji `(&o wyłączając)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) na tablicach informacyjnych.

{% hint style="info" %}

**Aby działało poprawnie, włącz `sign > allow-colors` w [konfiguracjach świata Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.tnt.defuse`

- **Domyślnie**: `Brak`

Zezwól graczom na zatrzymanie wybuchu TNT poprzez `interakcję wzajemną` z nożyczkami.

{% hint style="info" %}

**Aby działało, `defuse-tnt-change` w [Konfiguracjach Świata Purpur](configurations/purpur/world.md) musi wynosić co najmniej `0.0`.**

{% endhint %}

### Przyznane uprawnienia

#### `plazma.bypass.ncr-require`

- **Domyślnie**: `Brak`

Zezwól graczom na dołączenie nawet bez zainstalowanego moda [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**Aby działało, należy włączyć `no-chat-reports > require-install` w [Konfiguracjach Świata Plazma](configurations/plazma/world.md).**

{% endhint %}

***

[^1]: Operator.

[^2]: Przykład: `ender_dragon`
