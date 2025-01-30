---
description: Pelajari tentang izin Plazma.
---

# 🛡️ Izin

Izin adalah alat keamanan sederhana yang mengatur jangkauan interaksi antar pemain di dalam server.

Untuk memanfaatkan izin dengan baik dan mudah diubah, Anda harus menggunakan plugin seperti [LuckPerms](https://luckperms.net).

***

## Memahami Sistem Izin Dasar <a href="#id-1" id="id-1"></a>

Minecraft menyediakan grup izin administrasi dasar.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Pemain**\
   Grup izin yang diberikan kepada semua pemain secara umum.
2. **Mediator**\
   Dapat mengabaikan perlindungan spawn.
3. **Pengelola Dunia**\
   Dapat menggunakan semua perintah dan blok perintah terkait pengelolaan dunia.\
   Grup izin yang secara default diterapkan pada data paket dan blok perintah.
4. **Administrator**\
   Dapat menggunakan semua perintah terkait manajemen pemain.
5. **Super Administrator**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Bawaan**: `None`

Memungkinkan pemain menggunakan keterampilan khusus entitas saat menaiki entitas.

Tidak semua keterampilan khusus entitas dapat digunakan. Lihat di bawah untuk daftar lengkap keterampilan khusus yang tersedia.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Ini akan meningkatkan kinerja untuk kedua belah pihak.

> Untuk informasi tentang pengaturan X-Ray, lihat halaman berikut.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Bawaan**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Bawaan**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Bawaan**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Bawaan**: `None`

Memungkinkan penggunaan tag [MiniMessage](https://docs.advntr.dev/minimessage/format.html) pada landasan.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Bawaan**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Bawaan**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Bawaan**: `None`

Mengubah ukuran ender chest.

Anda dapat memasukkan `one`, `two`, `three`, `four`, `five`, `six` ke dalam `(NumberString)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Bawaan**: `None`

Memungkinkan totem abadi berfungsi meskipun berada di inventaris.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Bawaan**: `None`

Memungkinkan pemain untuk mengabaikan batasan jumlah pengguna yang terhubung.

#### `purpur.mending_shift_click`

- **Bawaan**: `None`

Memungkinkan pemain untuk memperbaiki item yang dipegang saat `menunduk dan berinteraksi`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Bawaan**: `None`

Memungkinkan pemain untuk memasang pembuat spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Bawaan**: `None`

Memungkinkan pemain untuk langsung teleportasi saat menggunakan portal Nether.

#### `purpur.sign.color`

- **Bawaan**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Bawaan**: `None`

Memungkinkan penggunaan kode enkripsi pada papan nama`(&o)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Bawaan**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Bawaan**: `None`

Memungkinkan pemain untuk mencegah ledakan TNT dengan `interaksi saling` menggunakan gunting.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Hak akses yang akan datang

#### `plazma.bypass.ncr-require`

- **Bawaan**: `None`

Memungkinkan pemain untuk bergabung tanpa harus menginstal mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Contoh: `ender_dragon`
