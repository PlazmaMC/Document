---
description: Pelajari tentang izin Plazma.
---

# 🛡️ Izin

Izin adalah alat keamanan sederhana yang mengatur jangkauan interaksi antar pemain di dalam server.

Untuk memanfaatkan izin dengan baik dan mudah diubah, Anda harus menggunakan plugin seperti [LuckPerms](https://luckperms.net).

***

## Memahami Sistem Izin Dasar <a href="#id-1" id="id-1"></a>

Minecraft menyediakan grup izin administrasi dasar.

Anda dapat mengatur izin [Administrator](#user-content-fn-1)[^1] dan blok perintah, serta dapat mengubahnya di [konfigurasi server](configurations/property.md).

0. **Pemain**\
   Grup izin yang diberikan kepada semua pemain secara umum.
1. **Mediator**\
   Dapat mengabaikan perlindungan spawn.
2. **Pengelola Dunia**\
   Dapat menggunakan semua perintah dan blok perintah terkait pengelolaan dunia.\
   Grup izin yang secara default diterapkan pada data paket dan blok perintah.
3. **Administrator**\
   Dapat menggunakan semua perintah terkait manajemen pemain.
4. **Super Administrator**\
   Dapat menggunakan semua perintah termasuk manajemen server.\
   Grup izin yang diterapkan secara default pada konsol dan administrator.

***

## Mengatur Izin <a href="#id-2" id="id-2"></a>

***

## Izin Penuh <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Bawaan**: `None`

Memungkinkan pemain untuk merangkak dan berinteraksi dengan entitas untuk menaiki entitas.

Ketika menaiki entitas, pemain dapat mengendalikan gerakan entitas dengan tombol gerak, dan melompat atau terbang dengan tombol lompat.

`(Namespaced Key)` adalah ID Namespaced entitas yang dimasukkan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `(Entity) > ridable` diaktifkan.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Bawaan**: `None`

Memungkinkan pemain menggunakan keterampilan khusus entitas saat menaiki entitas.

Tidak semua keterampilan khusus entitas dapat digunakan. Lihat di bawah untuk daftar lengkap keterampilan khusus yang tersedia.

{% hint style="info" %}

**Punya ide bagus untuk keterampilan khusus?**

Silakan posting ide Anda di [Plazma Discord](https://plazmamc.org/discord) atau [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Lihat Keterampilan Khusus yang Tersedia Saat Ini</summary>

- **`crepper`**\
  Meledak saat tombol lompat ditekan.\
  Jika pemain memiliki izin `allow.powered.creeper`, mereka dapat menekan tombol lompat untuk mengisi daya.
- **`dolphin`**\
  Meledak saat tombol lompat ditekan.
- **`phantom`**\
  Menembakkan api saat tombol lompat ditekan.
- **`wither`**\
  Menembakkan kepala wither saat berinteraksi.

</details>

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `(Entity) > ridable` diaktifkan.**

{% endhint %}

#### `bukkit.command.compass`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/credits (Pemain)`](commands.md#credits).

Menambahkan `.other` setelah nama izin memungkinkan penggunaan oleh pemain lain.

#### `bukkit.command.demo`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/demo (Pemain)`](commands.md#demo).

Menambahkan `.other` setelah nama izin memungkinkan penggunaan oleh pemain lain.

#### `bukkit.command.ping`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/ping (Pemain)`](commands.md#ping).

Menambahkan `.other` setelah nama izin memungkinkan penggunaan oleh pemain lain.

#### `bukkit.command.ram`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/rambar (Pemain)`](commands.md#rambar).

Menambahkan `.other` setelah nama izin memungkinkan penggunaan oleh pemain lain.

#### `bukkit.command.restart`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/tpsbar (Pemain)`](commands.md#tpsbar).

Menambahkan `.other` setelah nama izin memungkinkan penggunaan oleh pemain lain.

#### `bukkit.command.timings`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Perintah ini telah dihentikan.**

Untuk informasi tentang perintah serupa, lihat [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan penggunaan perintah [`/gamemode (GameMode) (Pemain)`].

Menambahkan `.other` setelah nama izin memungkinkan penggunaan oleh pemain lain.

#### `paper.antixray.bypass`

- **Bawaan**: `None`

Ketika [Pemblokiran X-Ray](../expert/xray.md) diaktifkan,
pemain yang memiliki izin tidak akan mengaburkan blok untuk melindungi dari X-Ray.

Ini akan meningkatkan kinerja untuk kedua belah pihak.

> Untuk informasi tentang pengaturan X-Ray, lihat halaman berikut.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Bawaan**: `None`

{% hint style="warning" %}

Izin ini akan diubah menjadi `plazma.bypass.watchdog` pada 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Bawaan**: `None`

Memungkinkan penggunaan [kode warna](https://minecraft.wiki/w/Formatting_codes#Color_codes) pada landasan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-colors` diaktifkan.**

{% endhint %}

#### `purpur.anvil.format`

- **Bawaan**: `None`

Memungkinkan penggunaan [kode gaya](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) pada landasan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-colors` diaktifkan.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Bawaan**: `None`

Memungkinkan penggunaan tag [MiniMessage](https://docs.advntr.dev/minimessage/format.html) pada landasan.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-minimessages` diaktifkan.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Bawaan**: `None`

Memungkinkan nonaktifkan `teks miring` pada landasan menggunakan kode gaya `&r`.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `anvil > allow-colors` diaktifkan.**

{% endhint %}

#### `purpur.book.color.sign`

- **Bawaan**: `None`

Memungkinkan penerapan [kode gaya](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) saat pemain menandatangani buku.

#### `purpur.bypassIdleKick`

- **Bawaan**: `None`

Mengecualikan pemain dari pemain yang akan dikeluarkan karena tidak aktif.

#### `purpur.debug.f3n`

- **Bawaan**: `Pengelola Dunia`

Memungkinkan pemain untuk mengubah mode permainan dengan tombol `F3 + N`.

Akan tidak berfungsi tanpa izin untuk mode permainan tersebut.

#### `purpur.drop.spawners`

- **Bawaan**: `None`

Jika menambang blok spawner dengan item yang dikonfigurasi, blok spawner akan jatuh.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `gameplay-mechanics > silk-touch` diaktifkan.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Bawaan**: `None`

Mengubah ukuran ender chest.

Anda dapat memasukkan `one`, `two`, `three`, `four`, `five`, `six` ke dalam `(NumberString)`.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `ender_chest > six-rows` dan `ender_chest > use-permissions-for-rows` diaktifkan.**

{% endhint %}

#### `purpur.inventory_totem`

- **Bawaan**: `None`

Memungkinkan totem abadi berfungsi meskipun berada di inventaris.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `totem-of-undying-works-in-inventory` diaktifkan.**

{% endhint %}

#### `purpur.joinFullServer`

- **Bawaan**: `None`

Memungkinkan pemain untuk mengabaikan batasan jumlah pengguna yang terhubung.

#### `purpur.mending_shift_click`

- **Bawaan**: `None`

Memungkinkan pemain untuk memperbaiki item yang dipegang saat `menunduk dan berinteraksi`.

{% hint style="info" %}

**Anda harus mengaktifkan `shift-right-click-repairs-mending-points` di **[Konfigurasi Dunia Purpur](configurations/purpur/world.md)** agar ini berfungsi.**

{% endhint %}

#### `purpur.place.spawners`

- **Bawaan**: `None`

Memungkinkan pemain untuk memasang pembuat spawner.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](configurations/purpur/world.md) hanya berfungsi jika `gameplay-mechanics > silk-touch` diaktifkan.**

{% endhint %}

#### `purpur.portal.instant`

- **Bawaan**: `None`

Memungkinkan pemain untuk langsung teleportasi saat menggunakan portal Nether.

#### `purpur.sign.color`

- **Bawaan**: `None`

Memungkinkan penggunaan [kode warna](https://minecraft.wiki/w/Formatting_codes#Color_codes) pada tanda.

{% hint style="info" %}

\*\*Untuk berfungsi, aktifkan `sign > allow-colors` di **[Konfigurasi Dunia Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.magic`

- **Bawaan**: `None`

Memungkinkan penggunaan kode enkripsi pada papan nama`(&o)`.

{% hint style="info" %}

\*\*Untuk berfungsi, aktifkan `sign > allow-colors` di **[Konfigurasi Dunia Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.style`

- **Bawaan**: `None`

Memungkinkan penggunaan [kode pemformatan `(&o excluded)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) pada papan nama.

{% hint style="info" %}

\*\*Untuk berfungsi, aktifkan `sign > allow-colors` di **[Konfigurasi Dunia Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.tnt.defuse`

- **Bawaan**: `None`

Memungkinkan pemain untuk mencegah ledakan TNT dengan `interaksi saling` menggunakan gunting.

{% hint style="info" %}

**[Konfigurasi Dunia Purpur](konfigurasi/purpur/dunia.md) harus memiliki `defuse-tnt-change` setidaknya `0.0` agar berfungsi.**

{% endhint %}

### Hak akses yang akan datang

#### `plazma.bypass.ncr-require`

- **Bawaan**: `None`

Memungkinkan pemain untuk bergabung tanpa harus menginstal mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**[Konfigurasi Dunia Plazma](konfigurasi/plazma/dunia.md) harus mengaktifkan `no-chat-reports > require-install` agar berfungsi.**

{% endhint %}

***

[^1]: Operator.

[^2]: Contoh: `ender_dragon`
