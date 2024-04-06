---
description: Ketahui mengenai kebenaran Plazma.
---

# 🛡️ Kebenaran

Kebenaran adalah alat keselamatan sederhana yang menetapkan lingkungan di mana pemain di dalam server dapat berinteraksi.

Untuk menggunakan dan mengubah kebenaran dengan baik, anda harus menggunakan plugin seperti [LuckPerms](https://luckperms.net).

***

## Memahami Sistem Kebenaran Asas <a href="#id-1" id="id-1"></a>

Minecraft menyediakan kumpulan kebenaran pengurusan asas.

Anda boleh menetapkan kebenaran untuk [pentadbir](#user-content-fn-1)[^1] dan blok perintah, dan boleh diubah dalam [konfigurasi pelayan](configurations/property.md).

0. **Pemain**\
   Kumpulan kebenaran yang diberikan kepada semua pemain secara umum.
1. **Arbitrator**\
   Boleh mengabaikan perlindungan spawn.
2. **Pengurus Dunia**\
   Boleh menggunakan semua perintah dan blok perintah yang berkaitan dengan pengurusan dunia.\
   Kumpulan kebenaran yang dikenakan secara asas pada paket data dan blok perintah.
3. **Pentadbir**\
   Boleh menggunakan semua perintah yang berkaitan dengan pengurusan pemain.
4. **Pentadbir Utama**\
   Boleh menggunakan semua perintah termasuk pengurusan pelayan.\
   Kumpulan kebenaran yang dikenakan secara asas pada konsol dan pentadbir.

***

## Menetapkan Kebenaran <a href="#id-2" id="id-2"></a>

***

## Kebenaran Penuh <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Asal**: `Tiada`

Membenarkan pemain untuk 'melipat' dan berinteraksi dengan entiti untuk menungganginya.

Apabila menunggang entiti, pemain boleh mengawal pergerakan entiti dengan 'keutamaan pergerakan' dan melompat atau terbang dengan 'keutamaan melompat'.

`(Namespaced Key)` merujuk kepada [ID Namespaced](#user-content-fn-2)[^2] entiti.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `(Entity) > ridable` diaktifkan.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Asal**: `Tiada`

Membenarkan pemain menggunakan kemahiran khas entiti semasa menunggangnya.

Tidak semua kemahiran khas entiti boleh digunakan. Rujuk di bawah untuk senarai kemahiran khas yang boleh digunakan.

{% hint style="info" %}

**Ada idea bagus untuk kemahiran khas?**

Silakan kongsi idea anda di [Plazma Discord](https://plazmamc.org/discord) atau [Perbincangan GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Lihat Kemahiran Khas yang Kini Tersedia</summary>

- **`crepper`**\
  Apabila menekan 'keutamaan melompat', akan meletup.\
  Jika pemain mempunyai kebenaran `allow.powered.creeper`, boleh menekan lama 'keutamaan melompat' untuk mengecas.
- **`dolphin`**\
  Apabila menekan 'keutamaan melompat', akan berenang laju.
- **`phantom`**\
  Apabila menekan 'keutamaan melompat', akan menembak nyala.
- **`wither`**\
  Apabila 'berinteraksi', akan menembak kepala wither.

</details>

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `(Entity) > ridable` diaktifkan.**

{% endhint %}

#### `bukkit.command.compass`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/credits (Pemain)`](commands.md#credits).

Menyertakan `.lain` selepas nama kebenaran membenarkan penggunaan oleh pemain lain.

#### `bukkit.command.demo`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/demo (Pemain)`](commands.md#demo).

Menyertakan `.lain` selepas nama kebenaran membenarkan penggunaan oleh pemain lain.

#### `bukkit.command.ping`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/ping (Pemain)`](commands.md#ping).

Menyertakan `.lain` selepas nama kebenaran membenarkan penggunaan oleh pemain lain.

#### `bukkit.command.ram`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/rambar (Pemain)`](commands.md#rambar).

Menyertakan `.lain` selepas nama kebenaran membenarkan penggunaan oleh pemain lain.

#### `bukkit.command.restart`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/tpsbar (Pemain)`](commands.md#tpsbar).

Menyertakan `.lain` selepas nama kebenaran membenarkan penggunaan oleh pemain lain.

#### `bukkit.command.timings`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/timings`](commands.md#timings).

{% hint style="warning" %}

**Perintah ini telah dihentikan.**

Untuk maklumat mengenai perintah yang serupa, sila rujuk [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Asal**: `Pengurus Dunia`

Membenarkan penggunaan [perintah `/gamemode (GameMode) (Pemain)`].

Menyertakan `.lain` selepas nama kebenaran membenarkan penggunaan oleh pemain lain.

#### `paper.antixray.bypass`

- **Asal**: `Tiada`

Apabila [Penghalang X-Ray](../expert/xray.md) diaktifkan, pemain yang mempunyai kebenaran tidak akan mengaburi blok untuk melindungi daripada X-Ray.

Ini akan meningkatkan prestasi untuk kedua-dua pihak.

> Untuk maklumat lanjut mengenai tetapan X-Ray, sila rujuk halaman berikut.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Asal**: `Tiada`

{% hint style="warning" %}

Kebenaran ini akan ditukar kepada `plazma.bypass.watchdog` dalam versi 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Asal**: `Tiada`

Membenarkan penggunaan [kod warna](https://minecraft.wiki/w/Formatting_codes#Color_codes) pada landasan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-colors` diaktifkan.**

{% endhint %}

#### `purpur.anvil.format`

- **Asal**: `Tiada`

Membenarkan penggunaan [kod gaya](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) pada landasan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-colors` diaktifkan.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Asal**: `Tiada`

Membenarkan penggunaan [tag MiniMessage](https://docs.advntr.dev/minimessage/format.html) pada landasan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-minimessages` diaktifkan.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Asal**: `Tiada`

Membenarkan untuk menonaktifkan `teks miring` dengan menggunakan kod gaya `&r` pada landasan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-colors` diaktifkan.**

{% endhint %}

#### `purpur.book.color.sign`

- **Asal**: `Tiada`

Apabila pemain menandatangani buku, kod gaya akan digunakan.

#### `purpur.bypassIdleKick`

- **Asal**: `Tiada`

Mengecualikan pemain dari pilihan tendang ketika tidak aktif.

#### `purpur.debug.f3n`

- **Asal**: `Pengurus Dunia`

Membenarkan pemain untuk menukar mod permainan dengan kekunci `F3 + N`.

Ia tidak akan berfungsi jika tiada kebenaran untuk mod permainan tersebut.

#### `purpur.drop.spawners`

- **Asal**: `Tiada`

Apabila menggali blok spawner dengan item yang ditetapkan dalam konfigurasi, ia akan menjatuhkan blok spawner.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `gameplay-mechanics > silk-touch` diaktifkan.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Asal**: `Tiada`

Menukar saiz peti End.

`(NumberString)` boleh menjadi `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `ender_chest > six-rows` dan `ender_chest > use-permissions-for-rows` diaktifkan.**

{% endhint %}

#### `purpur.inventory_totem`

- **Asal**: `Tiada`

Membenarkan totem abadi berfungsi walaupun berada dalam inventori.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `totem-of-undying-works-in-inventory` diaktifkan.**

{% endhint %}

#### `purpur.joinFullServer`

- **Asal**: `Tiada`

Membenarkan pemain untuk mengabaikan had jumlah pemain yang menyambung.

#### `purpur.mending_shift_click`

- **Asal**: `Tiada`

Membenarkan pemain untuk membaiki item yang dipegang apabila `berjongkok dan berinteraksi`.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) perlu mengaktifkan `shift-right-click-repairs-mending-points` agar berfungsi.**

{% endhint %}

#### `purpur.place.spawners`

- **Asal**: `Tiada`

Membenarkan pemain untuk memasang pemberi spawn.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `gameplay-mechanics > silk-touch` diaktifkan.**

{% endhint %}

#### `purpur.portal.instant`

- **Asal**: `Tiada`

Membenarkan pemain untuk terus bergerak ke destinasi setelah menggunakan portal Nether.

#### `purpur.sign.color`

- **Asal**: `Tiada`

Membenarkan penggunaan [kod warna](https://minecraft.wiki/w/Formatting_codes#Color_codes) pada papan tanda.

{% hint style="info" %}

**Untuk berfungsi, aktifkan `sign > allow-colors` dalam **[Konfigurasi Dunia Purpur](configurations/purpur/world.md)**.**

{% endhint %}

#### `tanda.sihir.purpur`

- **Asal**: `Tiada`

Membenarkan penggunaan kod pengaburan pada papan tanda `(&o)`.

{% hint style="info" %}

**Untuk berfungsi, aktifkan `sign > allow-colors` dalam **[Konfigurasi Dunia Purpur](configurations/purpur/world.md)**.**

{% endhint %}

#### `gaya.tanda.purpur`

- **Asal**: `Tiada`

Membenarkan penggunaan [kod pemformatan `(&o terkecuali)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) pada papan tanda.

{% hint style="info" %}

**Untuk berfungsi, aktifkan `sign > allow-colors` dalam **[Konfigurasi Dunia Purpur](configurations/purpur/world.md)**.**

{% endhint %}

#### `pelepasan.tnt.purpur`

- **Asal**: `Tiada`

Membenarkan pemain untuk mencegah letupan TNT dengan `interaksi saling` menggunakan gunting.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) harus memiliki `defuse-tnt-change` setidaknya `0.0` untuk berfungsi.**

{% endhint %}

### Peranan yang dijadualkan

#### `plazma.lalu-lalang.bypass-ncr`

- **Asal**: `Tiada`

Membenarkan pemain untuk menyertai walaupun mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) tidak dipasang.

{% hint style="info" %}

**[Konfigurasi Dunia Plazma](configurations/plazma/world.md) harus mengaktifkan `no-chat-reports > require-install` untuk berfungsi.**

{% endhint %}

***

[^1]: Operator.

[^2]: Contoh: `ender_dragon`
