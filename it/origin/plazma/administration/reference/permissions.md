---
description: Scopri i permessi di Plazma.
---

# 🛡️ Permessi

I permessi sono uno strumento di sicurezza semplice che definisce l'ambito in cui i giocatori del server possono interagire tra loro.

Per utilizzare e modificare correttamente i permessi, è necessario utilizzare plugin come [LuckPerms](https://luckperms.net).

***

## Comprendere il sistema di permessi predefinito <a href="#id-1" id="id-1"></a>

Minecraft fornisce gruppi di permessi di amministrazione di base.

È possibile impostare i permessi per gli **amministratori** e i blocchi di comando, modificandoli nelle [proprietà del server](configurations/property.md).

0. **Giocatore**\
   Solitamente è il gruppo di permessi assegnato a tutti i giocatori.
1. **Mediatore**\
   Può ignorare le protezioni dello spawn.
2. **Amministratore del mondo**\
   Può utilizzare tutti i comandi e i blocchi di comando relativi alla gestione del mondo.\
   È il gruppo di permessi predefinito per i datapack e i blocchi di comando.
3. **Amministratore**\
   Può utilizzare tutti i comandi relativi alla gestione dei giocatori.
4. **Super amministratore**\
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

**Funziona solo se è attivato `(Entità) > montabile` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Chiave con spazio dei nomi)`

- **Predefinito**: `Nessuno`

Permette ai giocatori di utilizzare le abilità speciali dell'entità su cui si trovano.

Non tutte le entità dispongono di abilità speciali utilizzabili. Consultare di seguito l'elenco completo delle abilità speciali disponibili.

{% hint style="info" %}

Hai idee per abilità speciali?

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

**Funziona solo se è attivato `(Entità) > montabile` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

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

**Questo comando è stato interrotto.**

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

Se l'[Anti X-Ray](../expert/xray.md) è attivo,
non verrà crittografato il blocco anti X-Ray per i giocatori con questo permesso.

Ciò migliora le prestazioni per entrambi gli utenti.

> Per informazioni su come configurare l'X-Ray, consulta la pagina seguente.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Predefinito**: `Nessuno`

{% hint style="warning" %}

Questo permesso sarà rinominato in `plazma.bypass.watchdog` nella versione 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Predefinito**: `Nessuno`

Permette l'uso dei [codici di colore](https://minecraft.wiki/w/Formatting_codes#Color_codes) sull'incudine.

{% hint style="info" %}

**Funziona solo se è attivato `anvil > allow-colors` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Predefinito**: `Nessuno`

Permette l'uso dei [codici di formattazione](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) sull'incudine.

{% hint style="info" %}

**Funziona solo se è attivato `anvil > allow-colors` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Predefinito**: `Nessuno`

Permette l'uso dei [tag MiniMessage](https://docs.advntr.dev/minimessage/format.html) sull'incudine.

{% hint style="info" %}

**Funziona solo se è attivato `anvil > allow-minimessages` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Predefinito**: `Nessuno`

Permette di disattivare il `corsivo` utilizzando il codice di formattazione `&r` sull'incudine.

{% hint style="info" %}

**Funziona solo se è attivato `anvil > allow-colors` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Predefinito**: `Nessuno`

Applica i [codici di formattazione](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) quando un giocatore firma un libro.

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

**Funziona solo se è attivato `gameplay-mechanics > silk-touch` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(StringaNumerica)`

- **Predefinito**: `Nessuno`

Modifica le dimensioni dell'ender chest.

La `(StringaNumerica)` può essere `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Funziona solo se è attivato `ender_chest > six-rows` e `ender_chest > use-permissions-for-rows` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Predefinito**: `Nessuno`

Consente al totem dell'immortalità di funzionare anche se è nell'inventario.

{% hint style="info" %}

**Funziona solo se è attivato `totem-of-undying-works-in-inventory` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Predefinito**: `Nessuno`

Consente al giocatore di ignorare il limite di utenti connessi.

#### `purpur.mending_shift_click`

- **Predefinito**: `Nessuno`

Consente al giocatore di riparare l'oggetto che tiene in mano quando si `accovaccia e interagisce`.

{% hint style="info" %}

**Per attivare questa funzione, è necessario abilitare `shift-right-click-repairs-mending-points` nelle [Configurazioni del Mondo di Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.place.spawners`

- **Predefinito**: `Nessuno`

Consente al giocatore di posizionare gli spawner.

{% hint style="info" %}

**Funziona solo se è attivato `gameplay-mechanics > silk-touch` nelle [configurazioni del mondo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Predefinito**: `Nessuno`

Permette al giocatore di teletrasportarsi immediatamente quando utilizza il portale dell'End.

#### `purpur.sign.color`

- **Predefinito**: `Nessuno`

Consente l'uso dei [codici colore](https://minecraft.wiki/w/Formatting_codes#Color_codes) sui cartelli.

{% hint style="info" %}

**Devi attivare `sign > allow-colors` nelle **[Configurazioni del mondo Purpur](configurations/purpur/world.md)** per farlo funzionare.**

{% endhint %}

#### `purpur.sign.magic`

- **Predefinito**: `Nessuno`

Consenti l'uso del codice di oscuramento sul cartello `(&o)`.

{% hint style="info" %}

**Devi attivare `sign > allow-colors` nelle **[Configurazioni del mondo Purpur](configurations/purpur/world.md)** per farlo funzionare.**

{% endhint %}

#### `purpur.sign.style`

- **Predefinito**: `Nessuno`

Consenti l'uso dei [codici di formattazione `(&o escluso)`](https://minecraft.wiki/w/Formatting_codes) sul cartello.

{% hint style="info" %}

**Devi attivare `sign > allow-colors` nelle **[Configurazioni del mondo Purpur](configurations/purpur/world.md)** per farlo funzionare.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Predefinito**: `Nessuno`

Consenti ai giocatori di prevenire l'esplosione del TNT interagendo con le forbici.

{% hint style="info" %}

**Nelle [configurazioni del mondo di Purpur](configurations/purpur/world.md), `defuse-tnt-change` deve essere superiore a `0.0` per funzionare.**

{% endhint %}

### Permesso previsto

#### `plazma.bypass.ncr-require`

- **Predefinito**: `Nessuno`

Consenti ai giocatori di accedere anche senza l'installazione della mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**Nelle [configurazioni del mondo di Plazma](configurations/plazma/world.md), è necessario attivare `no-chat-reports > require-install` per farlo funzionare.**

{% endhint %}

***

[^1]: Operatore.

[^2]: Esempio: `ender_dragon`
