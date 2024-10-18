---
description: Μάθετε σχετικά με τα δικαιώματα του Plazma.
---

# 🛡️ Δικαιώματα

Τα δικαιώματα είναι ένα απλό εργαλείο ασφαλείας που ορίζει το εύρος στο οποίο μπορούν να αλληλεπιδρούν οι παίκτες στον εξυπηρετητή.

Για να χρησιμοποιήσετε σωστά και να τροποποιήσετε εύκολα τα δικαιώματα, πρέπει να χρησιμοποιήσετε πρόσθετα όπως το [LuckPerms](https://luckperms.net).

***

## Κατανόηση του βασικού συστήματος δικαιωμάτων <a href="#id-1" id="id-1"></a>

Στο Minecraft, υπάρχουν προεπιλεγμένες ομάδες διαχείρισης δικαιωμάτων.

Μπορείτε να ορίσετε δικαιώματα για τον [διαχειριστή](#user-content-fn-1)[^1] και τα μπλοκ εντολών, τα οποία μπορούν να τροποποιηθούν στις [ιδιότητες του εξυπηρετητή](configurations/property.md).

0. **Παίκτης**\
   Είναι η ομάδα δικαιωμάτων που δίνεται συνήθως σε όλους τους παίκτες.
1. **Διαιτητής**\
   Μπορεί να αγνοήσει την προστασία της εκκίνησης.
2. **Διαχειριστής κόσμου**\
   Μπορεί να χρησιμοποιήσει όλες τις εντολές και τα μπλοκ εντολών που σχετίζονται με τη διαχείριση του κόσμου.\
   Είναι η προεπιλεγμένη ομάδα δικαιωμάτων που εφαρμόζονται στα δεδομένα πακέτα και στα μπλοκ εντολών.
3. **Διαχειριστής**\
   Μπορεί να χρησιμοποιήσει όλες τις εντολές που σχετίζονται με τη διαχείριση των παικτών.
4. **Γενικός Διαχειριστής**\
   Μπορεί να χρησιμοποιήσει όλες τις εντολές που σχετίζονται με τη διαχείριση του εξυπηρετητή.\
   Είναι η προεπιλεγμένη ομάδα δικαιωμάτων που εφαρμόζεται στην κονσόλα και στους διαχειριστές.

***

## Ορισμός δικαιωμάτων <a href="#id-2" id="id-2"></a>

***

## Όλα τα δικαιώματα <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να `καθίσει και να αλληλεπιδράσει` με τον οντότητα για να τον καβαλήσει.

Όταν καβαλάει την οντότητα, μπορεί να χειρίζεται τη μετακίνηση της οντότητας με το `πλήκτρο κίνησης` και να πηδάει ή να πετάει με το `πλήκτρο άλματος`.

Στο `(Namespaced Key)` εισάγεται το [Namespaced ID](#user-content-fn-2)[^2] της οντότητας.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `(Entity) > ridable` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να χρησιμοποιήσει τις ειδικές λειτουργίες του entity όταν τον καβαλάει.

Δεν είναι διαθέσιμες όλες οι ειδικές λειτουργίες για όλα τα entities. Δείτε παρακάτω τις διαθέσιμες ειδικές λειτουργίες.

{% hint style="info" %}

**Έχετε κάποια καλή ιδέα για ειδικές λειτουργίες;**

Δημοσιεύστε την ιδέα σας στο [Plazma Discord](https://plazmamc.org/discord) ή [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Δείτε τις διαθέσιμες ειδικές λειτουργίες</summary>

- **`crepper`**\
  Θα εκραγεί με το πάτημα του `πλήκτρου άλματος`.\
  Αν ο παίκτης έχει την άδεια `allow.powered.creeper`, μπορεί να κρατήσει πατημένο το `πλήκτρο άλματος` για να φορτώσει.
- **`dolphin`**\
  Θα τρέξει με το πάτημα του `πλήκτρου άλματος`.
- **`phantom`**\
  Θα εκτοξεύσει φλόγες με το πάτημα του `πλήκτρου άλματος`.
- **`wither`**\
  Θα εκτοξεύσει το κεφάλι του wither με το `διπλό κλικ`.

</details>

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `(Entity) > ridable` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/credits (Παίκτης)`](commands.md#credits).

Επιτρέπει τη χρήση σε άλλους παίκτες πληκτρολογώντας `.other` μετά το όνομα της άδειας.

#### `bukkit.command.demo`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/demo (Παίκτης)`](commands.md#demo).

Επιτρέπει τη χρήση σε άλλους παίκτες πληκτρολογώντας `.other` μετά το όνομα της άδειας.

#### `bukkit.command.ping`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/ping (Παίκτης)`](commands.md#ping).

Επιτρέπει τη χρήση σε άλλους παίκτες πληκτρολογώντας `.other` μετά το όνομα της άδειας.

#### `bukkit.command.ram`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/rambar (Παίκτης)`](commands.md#rambar).

Επιτρέπει τη χρήση σε άλλους παίκτες πληκτρολογώντας `.other` μετά το όνομα της άδειας.

#### `bukkit.command.restart`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/tpsbar (Παίκτης)`](commands.md#tpsbar).

Επιτρέπει τη χρήση σε άλλους παίκτες πληκτρολογώντας `.other` μετά το όνομα της άδειας.

#### `bukkit.command.timings`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Αυτή η εντολή έχει διακοπεί.**

Για παρόμοιες λειτουργίες, ελέγξτε το [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει τη χρήση της εντολής `/gamemode (GameMode) (Παίκτης)`.

Επιτρέπει τη χρήση σε άλλους παίκτες πληκτρολογώντας `.other` μετά το όνομα της άδειας.

#### `paper.antixray.bypass`

- **Προεπιλογή**: `Κανένα`

Όταν είναι ενεργοποιημένο το [Αποκλεισμός X-Ray](../expert/xray.md),
δεν εφαρμόζει την απόκρυψη των blocks για τους παίκτες με την άδεια.

Με αυτόν τον τρόπο και οι δύο πλευρές μπορούν να βελτιώσουν την απόδοσή τους.

> Για περισσότερες πληροφορίες σχετικά με τη ρύθμιση του X-Ray, δείτε τη σελίδα παρακάτω.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Προεπιλογή**: `Κανένα`

{% hint style="warning" %}

Αυτή η άδεια θα μετονομαστεί σε `plazma.bypass.watchdog` στην έκδοση 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση των [κωδικών χρώματος](https://minecraft.wiki/w/Formatting_codes#Color_codes) στον μοχλό.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `anvil > allow-colors` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση των [κωδικών μορφοποίησης](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) στον μοχλό.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `anvil > allow-colors` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση των [ετικετών MiniMessage](https://docs.advntr.dev/minimessage/format.html) στον μοχλό.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `anvil > allow-minimessages` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει την απενεργοποίηση της `κλίσης γραφής` με τον κωδικό μορφοποίησης `&r` στον μοχλό.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `anvil > allow-colors` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Προεπιλογή**: `Κανένα`

Εφαρμόζει τους [κωδικούς μορφοποίησης](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) όταν ο παίκτης υπογράφει ένα βιβλίο.

#### `purpur.bypassIdleKick`

- **Προεπιλογή**: `Κανένα`

Αποκλείει τον παίκτη από τη λίστα αποβολής λόγω αδράνειας.

#### `purpur.debug.f3n`

- **Προεπιλογή**: `Διαχειριστής Κόσμου`

Επιτρέπει στον παίκτη να αλλάξει το game mode με το πλήκτρο `F3 + N`.

Δεν λειτουργεί χωρίς την κατάλληλη άδεια για το game mode.

#### `purpur.drop.spawners`

- **Προεπιλογή**: `Κανένα`

Όταν σπάσετε ένα spawner block με το συγκεκριμένο αντικείμενο, θα πέσει το spawner block.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `gameplay-mechanics > silk-touch` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Προεπιλογή**: `Κανένα`

Αλλάζει το μέγεθος του ender chest.

Μπορείτε να εισάγετε `one`, `two`, `three`, `four`, `five`, `six` στο `(NumberString)`.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `ender_chest > six-rows` και `ender_chest > use-permissions-for-rows` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη λειτουργία του τότεμ της αθανασίας ακόμα και αν βρίσκεται στο inventory.

{% hint style="info" %}

**Πρέπει να ενεργοποιήσετε το `totem-of-undying-works-in-inventory` στο **[Αρχείο διαμόρφωσης Purpur κόσμου](configurations/purpur/world.md)** για να λειτουργήσει.**

{% endhint %}

#### `purpur.joinFullServer`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να αγνοήσει το όριο συνδέσεων.

#### `purpur.mending_shift_click`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να επισκευάσει το αντικείμενο που κρατάει όταν `κάνει κλικ δεξιά και ταυτόχρονα κάνει κρυφή κίνηση`.

{% hint style="info" %}

**Πρέπει να ενεργοποιήσετε το `shift-right-click-repairs-mending-points` στο **[Αρχείο διαμόρφωσης Purpur κόσμου](configurations/purpur/world.md)** για να λειτουργήσει.**

{% endhint %}

#### `purpur.place.spawners`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να τοποθετήσει spawners.

{% hint style="info" %}

**Λειτουργεί μόνο εάν ενεργοποιηθεί το `gameplay-mechanics > silk-touch` στο [Purpur Σύνολο Κόσμου](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να μετακινηθεί αμέσως όταν χρησιμοποιεί την πύλη του Nether.

#### `purpur.sign.color`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση [κωδικών χρώματος](https://minecraft.wiki/w/Formatting_codes#Color_codes) στις πινακίδες.

{% hint style="info" %}

**Πρέπει να ενεργοποιήσετε το `sign > allow-colors` στο **[Αρχείο διαμόρφωσης Purpur κόσμου](configurations/purpur/world.md)** για να λειτουργήσει.**

{% endhint %}

#### `purpur.sign.magic`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση του κωδικού μαγείας `(&o)` στις πινακίδες.

{% hint style="info" %}

**Πρέπει να ενεργοποιήσετε το `sign > allow-colors` στο **[Αρχείο διαμόρφωσης Purpur κόσμου](configurations/purpur/world.md)** για να λειτουργήσει.**

{% endhint %}

#### `purpur.sign.style`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση [κωδικών μορφοποίησης `(&o εξαιρουμένου)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) στις πινακίδες.

{% hint style="info" %}

**Πρέπει να ενεργοποιήσετε το `sign > allow-colors` στο **[Αρχείο διαμόρφωσης Purpur κόσμου](configurations/purpur/world.md)** για να λειτουργήσει.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να αποτρέψει την έκρηξη TNT κάνοντας `κλικ αριστερά και κρυφή κίνηση`.

{% hint style="info" %}

**Πρέπει το `defuse-tnt-change` να είναι `0.0` ή περισσότερο στο **[Αρχείο διαμόρφωσης Purpur κόσμου](configurations/purpur/world.md)** για να λειτουργήσει.**

{% endhint %}

### Δικαιώματα που πρόκειται να δοθούν

#### `plazma.bypass.ncr-require`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να συνδεθεί ακόμα κι αν δεν έχει εγκαταστήσει το [NoChatReports](https://modrinth.com/mod/no-chat-reports) mod.

{% hint style="info" %}

**Πρέπει να ενεργοποιήσετε το `no-chat-reports > require-install` στο **[Αρχείο διαμόρφωσης Plazma κόσμου](configurations/plazma/world.md)** για να λειτουργήσει.**

{% endhint %}

***

[^1]: Διαχειριστής.

[^2]: Παράδειγμα: `ender_dragon`
