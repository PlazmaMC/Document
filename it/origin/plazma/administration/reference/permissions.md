---
description: Scopri i permessi di Plazma.
---

# 🛡️ Permessi

I permessi sono uno strumento di sicurezza semplice che definisce l'ambito in cui i giocatori del server possono interagire tra loro.

Per utilizzare e modificare correttamente i permessi, è necessario utilizzare plugin come [LuckPerms](https://luckperms.net).

***

## Comprendere il sistema di permessi predefinito <a href="#id-1" id="id-1"></a>

Minecraft fornisce gruppi di permessi di amministrazione di base.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Giocatore**\
   Solitamente è il gruppo di permessi assegnato a tutti i giocatori.
2. **Mediatore**\
   Può ignorare le protezioni dello spawn.
3. **Amministratore del mondo**\
   Può utilizzare tutti i comandi e i blocchi di comando relativi alla gestione del mondo.\
   È il gruppo di permessi predefinito per i datapack e i blocchi di comando.
4. **Amministratore**\
   Può utilizzare tutti i comandi relativi alla gestione dei giocatori.
5. **Super amministratore**\
   Può utilizzare tutti i comandi, inclusi quelli per la gestione del server.\
   È il gruppo di permessi predefinito per la console e gli amministratori.

***

## Impostazione dei permessi <a href="#id-2" id="id-2"></a>

***

## Permessi completi <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Chiave con spazio dei nomi)`

- **Predefinito**: `Nessuno`

Permette ai giocatori di interagire con un'entità mentre si accovacciano per salire sull'entità.

Salendo sull'entità, i giocatori possono controllarne il movimento con i tasti di movimento e saltare o volare con il tasto di salto.

La `(Chiave con spazio dei nomi)` corrisponde all'ID con spazio dei nomi dell'entità.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Chiave con spazio dei nomi)`

- **Predefinito**: `Nessuno`

Permette ai giocatori di utilizzare le abilità speciali dell'entità su cui si trovano.

Non tutte le entità dispongono di abilità speciali utilizzabili. Consultare di seguito l'elenco completo delle abilità speciali disponibili.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Pubblica le tue idee su [Plazma Discord](https://plazmamc.org/discord) o [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Visualizza le abilità speciali attualmente disponibili</summary>

- **`crepper`**\
  Premendo il tasto di salto, esploderà.\
  Se un giocatore ha il permesso `allow.powered.creeper`, può caricare l'esplosione premendo a lungo il tasto di salto.
- **`dolphin`**\
  Premendo il tasto di salto, si caricherà in avanti.
- **`phantom`**\
  Premendo il tasto di salto, spareraà fiamme.
- **`wither`**\
  Interagendo, spareraà teste di Wither.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/credits (Giocatore)`](commands.md#credits).

Aggiungendo `.other` alla fine del nome del permesso, consente ad altri giocatori di utilizzarlo.

#### `bukkit.command.demo`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/demo (Giocatore)`](commands.md#demo).

Aggiungendo `.other` alla fine del nome del permesso, consente ad altri giocatori di utilizzarlo.

#### `bukkit.command.ping`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/ping (Giocatore)`](commands.md#ping).

Aggiungendo `.other` alla fine del nome del permesso, consente ad altri giocatori di utilizzarlo.

#### `bukkit.command.ram`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/rambar (Giocatore)`](commands.md#rambar).

Aggiungendo `.other` alla fine del nome del permesso, consente ad altri giocatori di utilizzarlo.

#### `bukkit.command.restart`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/tpsbar (Giocatore)`](commands.md#tpsbar).

Aggiungendo `.other` alla fine del nome del permesso, consente ad altri giocatori di utilizzarlo.

#### `bukkit.command.timings`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/timings`](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Per scoprire comandi simili, consulta [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(Modalità di gioco)`

- **Predefinito**: `Amministratore del mondo`

Permette l'uso del comando [`/gamemode (Modalità di gioco) (Giocatore)`](commands.md#gamemode).

Aggiungendo `.other` alla fine del nome del permesso, consente ad altri giocatori di utilizzarlo.

#### `paper.antixray.bypass`

- **Predefinito**: `Nessuno`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Ciò migliora le prestazioni per entrambi gli utenti.

> Per informazioni su come configurare l'X-Ray, consulta la pagina seguente.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Predefinito**: `Nessuno`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Predefinito**: `Nessuno`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Predefinito**: `Nessuno`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Predefinito**: `Nessuno`

Permette l'uso dei [tag MiniMessage](https://docs.advntr.dev/minimessage/format.html) sull'incudine.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Predefinito**: `Nessuno`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Predefinito**: `Nessuno`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Predefinito**: `Nessuno`

Esclude i giocatori dall'essere espulsi per inattività.

#### `purpur.debug.f3n`

- **Predefinito**: `Amministratore del mondo`

Permette ai giocatori di cambiare modalità di gioco premendo `F3 + N`.

Funziona solo se il giocatore ha il permesso per quella modalità di gioco.

#### `purpur.drop.spawners`

- **Predefinito**: `Nessuno`

Rilascia un blocco spawner quando viene distrutto con l'oggetto specificato nella configurazione.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(StringaNumerica)`

- **Predefinito**: `Nessuno`

Modifica le dimensioni dell'ender chest.

La `(StringaNumerica)` può essere `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Predefinito**: `Nessuno`

Consente al totem dell'immortalità di funzionare anche se è nell'inventario.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Predefinito**: `Nessuno`

Consente al giocatore di ignorare il limite di utenti connessi.

#### `purpur.mending_shift_click`

- **Predefinito**: `Nessuno`

Consente al giocatore di riparare l'oggetto che tiene in mano quando si `accovaccia e interagisce`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Predefinito**: `Nessuno`

Consente al giocatore di posizionare gli spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Predefinito**: `Nessuno`

Permette al giocatore di teletrasportarsi immediatamente quando utilizza il portale dell'End.

#### `purpur.sign.color`

- **Predefinito**: `Nessuno`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Predefinito**: `Nessuno`

Consenti l'uso del codice di oscuramento sul cartello `(&o)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Predefinito**: `Nessuno`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Predefinito**: `Nessuno`

Consenti ai giocatori di prevenire l'esplosione del TNT interagendo con le forbici.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Permesso previsto

#### `plazma.bypass.ncr-require`

- **Predefinito**: `Nessuno`

Consenti ai giocatori di accedere anche senza l'installazione della mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operatore.

[^2]: Esempio: `ender_dragon`
