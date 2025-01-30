---
description: Μάθετε σχετικά με τα δικαιώματα του Plazma.
---

# 🛡️ Δικαιώματα

Τα δικαιώματα είναι ένα απλό εργαλείο ασφαλείας που ορίζει το εύρος στο οποίο μπορούν να αλληλεπιδρούν οι παίκτες στον εξυπηρετητή.

Για να χρησιμοποιήσετε σωστά και να τροποποιήσετε εύκολα τα δικαιώματα, πρέπει να χρησιμοποιήσετε πρόσθετα όπως το [LuckPerms](https://luckperms.net).

***

## Κατανόηση του βασικού συστήματος δικαιωμάτων <a href="#id-1" id="id-1"></a>

Στο Minecraft, υπάρχουν προεπιλεγμένες ομάδες διαχείρισης δικαιωμάτων.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Παίκτης**\
   Είναι η ομάδα δικαιωμάτων που δίνεται συνήθως σε όλους τους παίκτες.
2. **Διαιτητής**\
   Μπορεί να αγνοήσει την προστασία της εκκίνησης.
3. **Διαχειριστής κόσμου**\
   Μπορεί να χρησιμοποιήσει όλες τις εντολές και τα μπλοκ εντολών που σχετίζονται με τη διαχείριση του κόσμου.\
   Είναι η προεπιλεγμένη ομάδα δικαιωμάτων που εφαρμόζονται στα δεδομένα πακέτα και στα μπλοκ εντολών.
4. **Διαχειριστής**\
   Μπορεί να χρησιμοποιήσει όλες τις εντολές που σχετίζονται με τη διαχείριση των παικτών.
5. **Γενικός Διαχειριστής**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να χρησιμοποιήσει τις ειδικές λειτουργίες του entity όταν τον καβαλάει.

Δεν είναι διαθέσιμες όλες οι ειδικές λειτουργίες για όλα τα entities. Δείτε παρακάτω τις διαθέσιμες ειδικές λειτουργίες.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Με αυτόν τον τρόπο και οι δύο πλευρές μπορούν να βελτιώσουν την απόδοσή τους.

> Για περισσότερες πληροφορίες σχετικά με τη ρύθμιση του X-Ray, δείτε τη σελίδα παρακάτω.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Προεπιλογή**: `Κανένα`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Προεπιλογή**: `Κανένα`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Προεπιλογή**: `Κανένα`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση των [ετικετών MiniMessage](https://docs.advntr.dev/minimessage/format.html) στον μοχλό.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Προεπιλογή**: `Κανένα`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Προεπιλογή**: `Κανένα`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Προεπιλογή**: `Κανένα`

Αλλάζει το μέγεθος του ender chest.

Μπορείτε να εισάγετε `one`, `two`, `three`, `four`, `five`, `six` στο `(NumberString)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη λειτουργία του τότεμ της αθανασίας ακόμα και αν βρίσκεται στο inventory.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να αγνοήσει το όριο συνδέσεων.

#### `purpur.mending_shift_click`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να επισκευάσει το αντικείμενο που κρατάει όταν `κάνει κλικ δεξιά και ταυτόχρονα κάνει κρυφή κίνηση`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να τοποθετήσει spawners.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να μετακινηθεί αμέσως όταν χρησιμοποιεί την πύλη του Nether.

#### `purpur.sign.color`

- **Προεπιλογή**: `Κανένα`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει τη χρήση του κωδικού μαγείας `(&o)` στις πινακίδες.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Προεπιλογή**: `Κανένα`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να αποτρέψει την έκρηξη TNT κάνοντας `κλικ αριστερά και κρυφή κίνηση`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Δικαιώματα που πρόκειται να δοθούν

#### `plazma.bypass.ncr-require`

- **Προεπιλογή**: `Κανένα`

Επιτρέπει στον παίκτη να συνδεθεί ακόμα κι αν δεν έχει εγκαταστήσει το [NoChatReports](https://modrinth.com/mod/no-chat-reports) mod.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Διαχειριστής.

[^2]: Παράδειγμα: `ender_dragon`
