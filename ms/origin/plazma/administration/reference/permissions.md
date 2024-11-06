---
description: Ketahui mengenai kebenaran Plazma.
---

# 🛡️ Kebenaran

Kebenaran adalah alat keselamatan sederhana yang menetapkan lingkungan di mana pemain di dalam server dapat berinteraksi.

Untuk menggunakan dan mengubah kebenaran dengan baik, anda harus menggunakan plugin seperti [LuckPerms](https://luckperms.net).

***

## Memahami Sistem Kebenaran Asas <a href="#id-1" id="id-1"></a>

Minecraft menyediakan kumpulan kebenaran pengurusan asas.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Pemain**\
   Kumpulan kebenaran yang diberikan kepada semua pemain secara umum.
2. **Arbitrator**\
   Boleh mengabaikan perlindungan spawn.
3. **Pengurus Dunia**\
   Boleh menggunakan semua perintah dan blok perintah yang berkaitan dengan pengurusan dunia.\
   Kumpulan kebenaran yang dikenakan secara asas pada paket data dan blok perintah.
4. **Pentadbir**\
   Boleh menggunakan semua perintah yang berkaitan dengan pengurusan pemain.
5. **Pentadbir Utama**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Asal**: `Tiada`

Membenarkan pemain menggunakan kemahiran khas entiti semasa menunggangnya.

Tidak semua kemahiran khas entiti boleh digunakan. Rujuk di bawah untuk senarai kemahiran khas yang boleh digunakan.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Ini akan meningkatkan prestasi untuk kedua-dua pihak.

> Untuk maklumat lanjut mengenai tetapan X-Ray, sila rujuk halaman berikut.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Asal**: `Tiada`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Asal**: `Tiada`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Asal**: `Tiada`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Asal**: `Tiada`

Membenarkan penggunaan [tag MiniMessage](https://docs.advntr.dev/minimessage/format.html) pada landasan.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Asal**: `Tiada`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Asal**: `Tiada`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Asal**: `Tiada`

Menukar saiz peti End.

`(NumberString)` boleh menjadi `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Asal**: `Tiada`

Membenarkan totem abadi berfungsi walaupun berada dalam inventori.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Asal**: `Tiada`

Membenarkan pemain untuk mengabaikan had jumlah pemain yang menyambung.

#### `purpur.mending_shift_click`

- **Asal**: `Tiada`

Membenarkan pemain untuk membaiki item yang dipegang apabila `berjongkok dan berinteraksi`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Asal**: `Tiada`

Membenarkan pemain untuk memasang pemberi spawn.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Asal**: `Tiada`

Membenarkan pemain untuk terus bergerak ke destinasi setelah menggunakan portal Nether.

#### `purpur.sign.color`

- **Asal**: `Tiada`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `tanda.sihir.purpur`

- **Asal**: `Tiada`

Membenarkan penggunaan kod pengaburan pada papan tanda `(&o)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `gaya.tanda.purpur`

- **Asal**: `Tiada`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `pelepasan.tnt.purpur`

- **Asal**: `Tiada`

Membenarkan pemain untuk mencegah letupan TNT dengan `interaksi saling` menggunakan gunting.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Peranan yang dijadualkan

#### `plazma.lalu-lalang.bypass-ncr`

- **Asal**: `Tiada`

Membenarkan pemain untuk menyertai walaupun mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) tidak dipasang.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Contoh: `ender_dragon`
