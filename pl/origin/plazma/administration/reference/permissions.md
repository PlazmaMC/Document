---
description: Sprawdź uprawnienia Plazmy.
---

# 🛡️ Uprawnienia

Uprawnienia to proste narzędzie bezpieczeństwa, które określa zakres interakcji graczy na serwerze.

Aby skutecznie korzystać z uprawnień i łatwo je modyfikować, należy użyć wtyczek takich jak [LuckPerms](https://luckperms.net).

***

## Zrozumienie podstawowego systemu uprawnień <a href="#id-1" id="id-1"></a>

W Minecraft dostępne są podstawowe grupy uprawnień administracyjnych.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Gracz**\
   To standardowa grupa uprawnień, przypisywana zazwyczaj wszystkim graczom.
2. **Mediator**\
   Może ignorować ochronę spawnu.
3. **Administrator świata**\
   Może używać wszystkich poleceń i bloków poleceń związanych z zarządzaniem światem.\
   To podstawowa grupa uprawnień stosowana do pakietów danych i bloków poleceń.
4. **Administrator**\
   Może używać wszystkich poleceń związanych z zarządzaniem graczami.
5. **Superadministrator**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Nazwany klucz)`

- **Domyślnie**: `Brak`

Pozwala graczom na korzystanie z specjalnych umiejętności jednostki, gdy ją prowadzą.

Nie wszystkie jednostki posiadają specjalne umiejętności. Sprawdź dostępne specjalne umiejętności poniżej.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Dzięki temu obie strony mogą cieszyć się poprawioną wydajnością.

> Aby dowiedzieć się więcej na temat konfiguracji X-Ray, sprawdź poniższą stronę.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Domyślnie**: `Brak`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Domyślnie**: `Brak`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Domyślnie**: `Brak`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Domyślnie**: `Brak`

Pozwala na korzystanie z tagów [MiniMessage](https://docs.advntr.dev/minimessage/format.html) na kowadle.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Domyślnie**: `Brak`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Domyślnie**: `Brak`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(LiczbaCiągZnaków)`

- **Domyślnie**: `Brak`

Zmienia rozmiar skrzyni Endera.

W miejscu `(LiczbaCiągZnaków)` można wprowadzić `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Domyślnie**: `Brak`

Pozwala na działanie totemów nieśmiertelności, gdy znajdują się w ekwipunku.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Domyślnie**: `Brak`

Zezwala graczowi na zignorowanie limitu liczby graczy podłączonych.

#### `purpur.mending_shift_click`

- **Domyślnie**: `Brak`

Zezwala graczowi na naprawę trzymanego przedmiotu poprzez `przytrzymanie i interakcję`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Domyślnie**: `Brak`

Zezwala graczowi na instalację spawnów.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Domyślnie**: `Brak`

Pozwala graczowi natychmiastowo teleportować się po wejściu do Netheru.

#### `purpur.sign.color`

- **Domyślnie**: `Brak`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Domyślnie**: `Brak`

Zezwól na użycie kodu zaciemnienia `(&o)` na tablicach informacyjnych.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Domyślnie**: `Brak`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Domyślnie**: `Brak`

Zezwól graczom na zatrzymanie wybuchu TNT poprzez `interakcję wzajemną` z nożyczkami.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Przyznane uprawnienia

#### `plazma.bypass.ncr-require`

- **Domyślnie**: `Brak`

Zezwól graczom na dołączenie nawet bez zainstalowanego moda [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Przykład: `ender_dragon`
