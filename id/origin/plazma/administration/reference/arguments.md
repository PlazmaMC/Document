---
description: Pelajari tentang argumen awal dan properti sistem.
---

# 🎛️ Argumen dan Properti

Argumen awal dan properti sistem adalah nilai yang ditambahkan ke [perintah yang digunakan](#user-content-fn-1)[^1] dalam eksekusi Plazma,\
memungkinkan untuk mengubah nilai yang tidak dapat diubah setelah Plazma dieksekusi.

[Posisi yang ditambahkan ke perintah](#user-content-fn-2)[^2] akan dibagi menjadi **Argumen Awal** dan **Properti Sistem** sesuai dengan posisi tersebut.

***

## Properti Sistem <a href="#id-1" id="id-1"></a>

Properti sistem dimasukkan sebelum `-jar` dan diproses oleh JVM sebelum Plazma diinisialisasi.

{% hint style="warning" %}

**Jika Anda mengubah properti sistem, cara kerja Plazma dan JVM dapat berubah, dan ini dapat berdampak besar pada permainan!**

Jika Anda tidak yakin apa peran setiap properti sistem, **jangan pernah menggunakannya!**

{% endhint %}

### Cara Penggunaan <a href="#id-1.1" id="id-1.1"></a>

Properti sistem dimasukkan sebagai argumen perintah Java antara `java` dan `-jar`.

Misalnya, jika ingin menerapkan properti sistem `Plazma.dummyProperty`,\
masukkan nilai `37` setelah properti tersebut untuk inisialisasi Plazma.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` menandakan argumen tersebut adalah argumen tambahan yang ditambahkan ke Plazma, tidak bawaan JVM, dan

Jika tidak ada nilai yang dimasukkan ke dalam properti, nilai akan tetap [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Platform server seri Paperweight menggunakan `.` dalam nama properti untuk membedakan properti sistem di setiap platform.**

Di beberapa terminal seperti Windows Powershell, argumen semacam ini mungkin tidak diizinkan, sehingga, `"` harus ditambahkan di kedua ujung argumen\[#user-content-fn-4)[^4].

{% endhint %}

### Seluruh Properti Sistem <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tipe**: `Boolean`
- **Default**: `False`

Memperbarui format tanda yang sudah tidak digunakan.

#### `debug.entities`

- **Tipe**: `Boolean`
- **Default**: `False`

Mengaktifkan log debug terkait informasi entitas.

#### `debug.rewriteForIDE`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan revisi NMS untuk IDE agar dapat memuat informasi debug dengan benar,\
dan secara otomatis meremapping informasi versi internal.

#### `disable.watchdog`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan sistem peringatan Watchdog Spigot.

#### `letMeReload`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan pesan konfirmasi untuk perintah `/reload`.

{% hint style="danger" %}

**`/reload` command sangat tidak stabil, jadi semua masalah yang muncul setelah menggunakan `/reload` menjadi tanggung jawab pengguna sendiri.**

Jika Anda adalah pengembang plugin dan perlu melakukan pembaruan plugin, gunakan hotswap alih-alih `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan plugin yang menggunakan sistem I/O standar.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tipe**: `Boolean`
- **Default**: `False`

Memberikan peringatan ketika format lama terdeteksi pada komponen obrolan.

#### `Paper.bypassHostCheck`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan verifikasi pola server saat pemain terhubung ke server.

#### `Paper.debugDynamicMissingKeys`

- **Tipe**: `Boolean`
- **Default**: `False`

Mengaktifkan log debug untuk kunci yang hilang pada objek NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Tipe**: `Boolean`
- **Default**: `False`

Mengaktifkan log debug untuk blok tengkorak dengan profil yang tidak valid.

Semua blok tengkorak yang tidak valid akan dicatat dengan posisi mereka di dunia.

#### `Paper.disableChannelLimit`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan batasan jumlah 128 plugin [channel](#user-content-fn-5)[^5] yang diterapkan per pemain.

#### `Paper.disableClassPrioritization`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan sistem prioritas kelas plugin.

Berguna jika terjadi masalah dalam shading plugin.

#### `Paper.disableFlushConsolidate`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan sistem konsolidasi flush Netty.

#### `Paper.excessiveTELimit`

- **Tipe**: `Integer`
- **Default**: `750`

Mengirimkan entitas dalam paket terpisah jika melebihi nilai yang ditetapkan.

#### `Paper.filterThreshold`

- **Tipe**: `Integer`
- **Default**: `8192`

Menetapkan ukuran maksimal paket yang dapat diterima oleh server sekaligus.

#### `Paper.ignoreJavaVersion`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan pengecekan versi Java.

{% hint style="danger" %}

**Ini dapat menyebabkan JVM mencoba mengakses kode yang tidak ada!**

Ini dapat menyebabkan kerusakan permanen pada file-file di dunia dan mempengaruhi mekanisme permainan secara keseluruhan.

Semua masalah yang timbul dari penggunaan ini menjadi tanggung jawab pengguna, dan Plamza tidak memberikan dukungan untuk hal ini.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tipe**: `Integer`
- **Default**: `64`

Mengatur batasan nama [channel](#user-content-fn-5)[^5] plugin.

#### `Paper.maxSignLength`

- **Tipe**: `Integer`
- **Default**: `80`

Menetapkan panjang maksimal karakter yang dapat dimasukkan dalam satu baris tanda.

#### `Paper.minPrecachedDatafixVersion`

- **Tipe**: `Integer`
- **Default**: `(versi dunia) + 1`

Menetapkan versi informasi pembaruan dunia yang akan diinisialisasi terlebih dahulu.

Berguna saat perlu memperbarui sejumlah besar chunk, tetapi jarang digunakan dalam kasus lain.

#### `Paper.parseYamlCommentsByDefault`

- **Tipe**: `Boolean`
- **Default**: `True`

Mengaktifkan pengolahan komentar dalam file YAML secara default.

#### `Paper.playerConnection.keepAlive`

- **Tipe**: `Integer`
- **Default**: `30`

Mengeluarkan pemain dari server jika tidak menerima data apa pun dari pemain selama jumlah waktu tertentu (dalam detik).

Secara umum, [game](#user-content-fn-7)[^7] akan terus mengirimkan [sinyal detak](#user-content-fn-8)[^8] ke server, sehingga tidak akan diusir, tetapi jika game tidak merespons, server akan menganggapnya bertabrakan dan tidak akan lagi memproses pemain di server dan mengusirnya.

#### `Paper.skipServerPropertiesComments`

- **Tipe**: `Boolean`
- **Default**: `False`

Mengabaikan komentar properti server.

#### `Paper.debug-sync-loads`

- **Tipe**: `Boolean`
- **Default**: `False`

Mengaktifkan log debug untuk pembuatan chunk secara sinkron.

#### `Paper.enable-sync-chunk-writes`

- **Tipe**: `Boolean`
- **Default**: `False`

Mengaktifkan sistem pembuatan chunk standar Minecraft[^10].

Ini menyebabkan setiap chunk disimpan secara berurutan, menyebabkan penurunan kinerja yang signifikan.

#### `Paper.explicit-flush`

- **Tipe**: `Boolean`
- **Default**: `False`

Mengaktifkan pengeksekusian eksplisit pada saluran jaringan.

#### `Paper.strict-thread-checks`

- **Tipe**: `Boolean`
- **Default**: `False`

Selalu mencatat kesalahan yang terjadi di luar utas utama.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tipe**: `Boolean`
- **Default**: `False`

Memberikan peringatan jika tugas terjadwal mengalami keterlambatan berlebih.

#### `Paperclip.patchOnly`

- **Tipe**: `Boolean`
- **Default**: `False`

Jika menggunakan file eksekusi bawaan, hanya menerapkan patch tanpa memulai server.

#### `Plazma.aggressiveOptimize`

- **Tipe**: `Boolean`
- **Default**: `false`

{% hint style="warning" %}

**Properti ini akan dipindahkan sebagai argumen awal mulai dari versi 1.20.5.**

{% endhint %}

Menerapkan optimalisasi konfigurasi yang lebih ketat saat pertama kali dimulai.

Mengaktifkan akan membuat server lebih cepat dan aman, tetapi dapat memblokir beberapa mekanisme atau berdampak besar pada gameplay.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipe**: `Boolean`
- **Default**: `false`

Menghentikan pesan [peringatan](#user-content-fn-11)[^11] yang muncul saat Plazma diinisialisasi.

### Atribut yang sudah tidak digunakan <a href="#id-1.3" id="id-1.3"></a>

Berikut adalah atribut sistem yang sudah tidak digunakan.

#### `timings.bypassMax`

- **Tipe**: `Boolean`
- **Default**: `false`
- **Dihentikan**: Setelah Timings dihapus dari Plazma

Menentukan apakah nilai yang dapat dikirim ke API Timings Aikar dapat melebihi batas maksimum.

Jika tidak diatasi dalam API, batasan kecepatan akan diterapkan.

***

## Argumen Mulai <a href="#id-2" id="id-2"></a>

Argumen Mulai dimasukkan setelah `-jar *.jar` untuk menginisialisasi Plazma dan merupakan nilai yang diproses bersamaan.

### Cara Penggunaan <a href="#id-2.1" id="id-2.1"></a>

Properti sistem dimasukkan setelah `-jar *.jar` sebagai argumen perintah program.

Misalnya, jika Anda ingin menerapkan argumen mulai `nogui`,\
masukkan seperti ini agar Plazma memproses argumen `nogui` saat inisialisasi.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argumen Mulai Lengkap <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Nilai Default**: `bukkit.yml`

Menetapkan nama dan lokasi [File Konfigurasi Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Nilai Default**: `commands.yml`

Menetapkan nama dan lokasi [File Konfigurasi Perintah Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Nilai Default**: `server.properties`

Menetapkan nama dan lokasi [File Properti Server](../reference/configurations/property.md).

#### `demo`

Memulai server ke dalam dunia demo.

#### `eraseCache`

Menghapus file cache yang tersisa setelah upgrade dunia.

#### `forceUpgrade`

Memaksa [upgrade](#user-content-fn-12)[^12] dunia tanpa memperdulikan versi.

#### `help`

- **Alias**: `?`

Menampilkan argumen mulai lengkap dan penjelasan Plazma.

#### `initSettings`

Membuat file konfigurasi saja dan menutup server.

#### `jfrProfile`

Mengaktifkan profil JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Nilai Default**: `(Properti Server)`

Menetapkan jumlah maksimum [pemain](#user-content-fn-14)[^14] yang diizinkan.

#### `nogui`

Menonaktifkan panel antarmuka grafis.

#### `nojline`

Menonaktifkan JLine dan menggunakan konsol vanilla.

#### `online-mode`

- **Alias**: `o`
- **Nilai Default**: `(Properti Server)`

Memilih untuk memverifikasi pemain melalui server otentikasi Mojang.

**Jika tidak menggunakan Velocity atau proxy lain, bisa mengakibatkan pelanggaran [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Nilai Default**: `paper.yml`

{% hint style="warning" %}

**Argumen ini telah dihentikan penggunaannya setelah versi 1.19.4**

{% endhint %}

Menetapkan lokasi [File Konfigurasi PaperSpigot](../reference/configurations/paper/README.md) yang telah dihentikan penggunaannya.

Digunakan untuk memindahkan konfigurasi lama ke file konfigurasi baru dan tidak digunakan lagi setelahnya.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Nilai Default**: `config`

Menetapkan nama dan lokasi folder tempat [File Konfigurasi Paper](../reference/configurations/paper/README.md) berada.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Menetapkan nama dan lokasi folder tempat [File Konfigurasi Plazma](../reference/configurations/plazma/README.md) berada.

#### `plugins`

- **Alias**: `p`
- **Nilai Default**: `plugins`

Menetapkan lokasi folder plugin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Nilai Default**: `pufferfish.yml`

Menetapkan nama dan lokasi [File Konfigurasi Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Nilai Default**: `purpur.yml`

Menetapkan nama dan lokasi [File Konfigurasi Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Memulai server dalam keadaan vanilla lengkap.

#### `server-ip`

- **Alias**: `h`, `host`
- **Nilai Default**: `(Properti Server)`

Menetapkan nama host server atau alamat [protokol internet](#user-content-fn-13)[^13].

#### `server-port`

- **Alias**: `p`, `port`
- **Nilai Default**: `(Properti Server)`

Menetapkan port server.

#### `server-name`

- **Nilai Default**: `A Plazma Server`

Menetapkan nama server.

#### `spigot-settings`

- **Alias**: `S`
- **Nilai Default**: `spigot.yml`

Menetapkan nama dan lokasi [File Konfigurasi Spigot](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Menampilkan versi Plazma.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Nilai Default**: `(folder server)`

Menetapkan lokasi penyimpanan file dunia.

#### `world-name`

- **Alias**: `w`, `world`
- **Nilai Default**: `(Properti Server)`

Menetapkan nama file dunia.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Posisi argumen yang diproses tergantung pada lokasi tambahan yang ditambahkan.

[^3]: Misalnya, jika ingin mengatur (mengaktifkan) `Plazma.iKnowWhatIAmDoing` menjadi `true`, cukup masukkan `-DPlazma.iKnowWhatIAmDoing` tanpa `=true` dan akan tetap berfungsi.

[^4]: Misalnya, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detektor acara.

[^6]: Detektor acara.

[^7]: Klien.

[^8]: Sinyal yang menunjukkan bahwa klien terhubung dengan server dengan lancar seperti detak jantung.

[^9]: Dengan fitur kick AFK Purpur, Anda dapat mengeluarkan pemain yang meninggalkan tempat.

[^10]: Sistem Penulisan Chunk Sinkron.

[^11]: `PERINGATAN! Plazma mungkin menyebabkan masalah yang tidak terduga, jadi pastikan untuk mengujinya secara menyeluruh sebelum menggunakannya di server publik.`

[^12]: Dalam permainan, `optimisasi dunia` juga beroperasi dengan prinsip yang sama.

[^13]: Protokol Internet, IP.

[^14]: Administrator `level 2` ke atas dikecualikan.
