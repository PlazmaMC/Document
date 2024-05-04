---
description: Ketahui tentang argumen permulaan dan sifat sistem.
---

# 🎛️ Argumen dan Sifat

Argumen permulaan dan sifat sistem adalah nilai yang ditambahkan ke [perintah yang digunakan](#user-content-fn-1)[^1] dalam pelaksanaan Plazma,\
membolehkan nilai yang tidak boleh diubah selepas Plazma dilaksanakan untuk diubah.

Berdasarkan [lokasi nilai yang ditambahkan ke perintah](#user-content-fn-2)[^2], ia dibahagikan kepada **argumen permulaan** dan **sifat sistem**.

***

## Sifat sistem <a href="#id-1" id="id-1"></a>

Sifat sistem dimasukkan sebelum `-jar` dan diproses oleh JVM sebelum Plazma diinisialisasi.

{% hint style="warning" %}

### Mengubah sifat sistem boleh mengubah cara Plazma dan JVM berfungsi dan boleh memberi kesan besar kepada permainan!

Jika anda tidak pasti peranan setiap sifat sistem, **jangan gunakannya sama sekali!**
{% endhint %}

### Cara Penggunaan <a href="#id-1.1" id="id-1.1"></a>

Sifat sistem dimasukkan sebagai argumen perintah Java antara `java` dan `-jar`.

Contohnya, jika anda ingin menggunakan sifat sistem `Plazma.dummyProperty`,\
masukkan nilai seterusnya sebagai `37` untuk inisialisasi Plazma.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` menandakan argumen tersebut adalah tambahan khas untuk Plazma dan tidak disertakan dalam JVM,

Jika tidak ada nilai yang dimasukkan, nilai akan tetap [`true`.](#user-content-fn-3)[^3]

{% hint style="info" %}

### Platform Pemendatang Berat membezakan sifat sistem untuk setiap platform dengan menyertakan `.` dalam nama sifat.

Beberapa terminal seperti Windows Powershell mungkin tidak menerima argumen ini, jadi, tambahkan `"` pada kedua hujung argumen. [sebagai langkah berjaga-jaga.](#user-content-fn-4)[^4]
{% endhint %}

### Sifat Sistem Penuh <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Mengemaskini format tanda yang telah digunakan.

#### `debug.entities`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Aktifkan log debug berkaitan maklumat entiti.

#### `debug.rewriteForIDE`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan semula revisi NMS untuk IDE,\
memetakan semula maklumat versi dalaman secara automatik.

#### `disable.watchdog`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan sistem amaran Watchdog Spigot.

#### `letMeReload`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan mesej pengesahan semula perintah `/reload`.

{% hint style="danger" %}

### Perintah `/reload` sangat tidak stabil, oleh itu, semua masalah yang berlaku selepas menggunakan `/reload` adalah tanggungjawab pengguna sendiri.

Untuk pembangun plugin yang perlu mengemaskini plugin, gunakan hotswap sebagai gantinya.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan plugin yang menggunakan sistem input/output standard.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Amaran jika format lama dikesan dalam komponen chat.

#### `Paper.bypassHostCheck`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan pengesahan pola hos semasa pemain menyambung ke pelayan.

#### `Paper.debugDynamicMissingKeys`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Aktifkan log debug untuk kunci yang hilang dalam objek NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Aktifkan log debug untuk profil kepala yang tidak sah.

Log ini mencatat semua blok kepala yang salah dalam dunia bersama dengan lokasinya.

#### `Paper.disableChannelLimit`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan had jumlah saluran plugin (128 saluran setiap pemain) yang dikenakan kepada setiap pemain.

#### `Paper.disableClassPrioritization`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan sistem keutamaan kelas plugin.

Berguna jika ada masalah dalam shading plugin.

#### `Paper.disableFlushConsolidate`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan sistem konsolidasi flush Netty.

#### `Paper.excessiveTELimit`

- **Jenis**: `Integer`
- **Nilai Lalai**: `750`

Jika entiti melebihi nilai yang ditetapkan, ia akan dihantar melalui paket berganda.

#### `Paper.filterThreshold`

- **Jenis**: `Integer`
- **Nilai Lalai**: `8192`

Tetapkan saiz maksimum paket yang boleh diterima oleh pelayan pada satu masa.

#### `Paper.ignoreJavaVersion`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan pengesahan versi Java.

{% hint style="danger" %}

### Ini boleh menyebabkan JVM cuba mengakses kod yang tidak wujud!

Ini boleh merosakkan fail dan dunia secara kekal, menyebabkan kegagalan mekanisme permainan.

Semua masalah yang timbul daripada penggunaan ini adalah tanggungjawab pengguna dan Plamza tidak akan memberikan sebarang sokongan untuk itu.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **Jenis**: `Integer`
- **Nilai Lalai**: `64`

Tetapkan had nama saluran plugin.

#### `Paper.maxSignLength`

- **Jenis**: `Integer`
- **Nilai Lalai**: `80`

Tetapkan panjang maksimum teks pada satu baris tanda.

#### `Paper.minPrecachedDatafixVersion`

- **Jenis**: `Integer`
- **Nilai Lalai**: `(versi dunia) + 1`

Tetapkan versi maklumat pembetulan data yang perlu diinisialisasi terlebih dahulu.

Berguna jika perlu mengemaskini banyak chunk, tetapi jarang digunakan dalam keadaan biasa.

#### `Paper.parseYamlCommentsByDefault`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `True`

Aktifkan pemprosesan komen YAML secara lalai.

#### `Paper.playerConnection.keepAlive`

- **Jenis**: `Integer`
- **Nilai Lalai**: `30`

Pemain akan dikeluarkan jika tiada data diterima daripada mereka selama tempoh yang ditetapkan (dalam saat).

Biasanya, permainan[^7] akan terus menghantar [isyarat jantung](#user-content-fn-8)[^8] ke pelayan, [mengelakkan pembanjiran,](#user-content-fn-9)[^9] tetapi jika permainan tidak memberi respons, pelayan menganggap permainan telah mengalami kegagalan dan mengeluarkan pemain tanpa lebih lanjut memproses mereka.

#### `Paper.skipServerPropertiesComments`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Abaikan komen sifat pelayan.

#### `Paper.debug-sync-loads`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Aktifkan log debug penulisan chunk secara selari.

#### `Paper.enable-sync-chunk-writes`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Aktifkan [sistem penulisan chunk asas Minecraft](#user-content-fn-10)[^10].

Ini akan menyebabkan setiap chunk disimpan secara berurutan, menyebabkan penurunan prestasi yang ketara.

#### `Paper.explicit-flush`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Aktifkan Pengepaman Eksplisit saluran rangkaian.

#### `Paper.strict-thread-checks`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Log ralat yang berlaku di luar utama sentiasa.

#### `Paper.tickList-warn-on-excessive-delay`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Paparkan amaran jika tugas yang dirancang mempunyai kelewatan yang terlalu lama.

#### `Paperclip.patchOnly`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Jika menggunakan fail eksekusi yang disediakan secara lalai, hanya lakukan pengepaman tanpa memulakan pelayan.

#### `Plazma.aggressiveOptimize`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `false`

{% hint style="warning" %}

### Sifat ini akan dipindahkan sebagai argumen permulaan selepas 1.20.5.

{% endhint %}

Optimumkan konfigurasi yang digunakan pada permulaan dengan lebih ketat.

Apabila diaktifkan, server akan menjadi lebih cepat dan selamat, tetapi boleh menghalang beberapa mekanisme atau memberi kesan besar kepada permainan.

#### `Plazma.iKnowWhatIAmDoing`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `false`

Menekan mesej amaran[^11] yang dipaparkan semasa Plazma diinisialisasi.

### Harta tanah yang telah dihentikan penggunaannya <a href="#id-1.3" id="id-1.3"></a>

Ciri-ciri sistem di bawah ini adalah ciri-ciri yang telah dihentikan penggunaannya.

#### `timings.bypassMax`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `false`
- **Dihentikan**: Selepas Plazma mengeluarkan Timings secara keseluruhan dari penggunaan

Menentukan sama ada nilai yang melebihi had yang boleh dihantar ke API Timings Aikar.

Walaupun begitu, sekiranya tidak diuruskan dalam API, had kadar akan dikenakan.

***

## Argumen Permulaan <a href="#id-2" id="id-2"></a>

Argumen Permulaan dimasukkan selepas `-jar *.jar` untuk inisialisasi Plazma dan nilainya diproses bersama.

### Cara Penggunaan <a href="#id-2.1" id="id-2.1"></a>

Ciri sistem dimasukkan sebagai argumen arahan program selepas `-jar *.jar`.

Contohnya, jika ingin menggunakan argumen permulaan `nogui`,\
masukkan seperti berikut untuk membolehkan Plazma memproses argumen `nogui` semasa inisialisasi.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argumen Permulaan Penuh <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Nilai Asas**: `bukkit.yml`

Menetapkan nama dan lokasi [Fail Konfigurasi Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Nilai Asas**: `commands.yml`

Menetapkan nama dan lokasi [Fail Konfigurasi Perintah Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Nilai Asas**: `server.properties`

Menetapkan nama dan lokasi [Fail Sifat Pelayan](../reference/configurations/property.md).

#### `demo`

Memulakan pelayan dengan dunia demo.

#### `eraseCache`

Menghapus fail cache yang tinggal selepas menaik taraf dunia.

#### `forceUpgrade`

Memaksa [menaik taraf](#user-content-fn-12)[^12] dunia tanpa mengira versi.

#### `help`

- **Alias**: `?`

Mencetak argumen permulaan dan penerangan penuh Plazma.

#### `initSettings`

Mencipta fail konfigurasi sahaja dan menamatkan pelayan.

#### `jfrProfile`

Aktifkan profil JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Nilai Asas**: `(Sifat Pelayan)`

Menetapkan jumlah maksimum [pemain](#user-content-fn-14)[^14] yang dibenarkan.

#### `nogui`

Matikan panel antara muka grafik.

#### `nojline`

Matikan JLine dan gunakan konsol biasa.

#### `online-mode`

- **Alias**: `o`
- **Nilai Asas**: `(Sifat Pelayan)`

Pilih untuk mengesahkan pemain dengan pelayan pengesahan Mojang.

**Jika tidak menggunakan Velocity atau proksi, boleh dikenakan tindakan disiplin mengikut [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Nilai Asas**: `paper.yml`

{% hint style="warning" %}

### Argumen ini tidak lagi digunakan selepas versi 1.19.4

{% endhint %}

Menetapkan lokasi [Fail Konfigurasi PaperSpigot](../reference/configurations/paper/README.md) yang tidak lagi digunakan.

Digunakan untuk memindahkan konfigurasi sedia ada ke fail konfigurasi baru dan tidak digunakan selepas itu.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Nilai Asas**: `config`

Menetapkan nama dan lokasi folder yang mengandungi [Fail Konfigurasi Paper](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Menetapkan nama dan lokasi folder yang mengandungi [Fail Konfigurasi Plazma](../reference/configurations/plazma/README.md).

#### `plugins`

- **Alias**: `p`
- **Nilai Asas**: `plugins`

Menetapkan lokasi folder plugin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Nilai Asas**: `pufferfish.yml`

Menetapkan nama dan lokasi [Fail Konfigurasi Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Nilai Asas**: `purpur.yml`

Menetapkan nama dan lokasi [Fail Konfigurasi Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Memulakan pelayan dalam keadaan vanilla penuh.

#### `server-ip`

- **Alias**: `h`, `host`
- **Nilai Asas**: `(Sifat Pelayan)`

Menetapkan nama hos pelayan atau alamat [protokol internet](#user-content-fn-13)[^13].

#### `server-port`

- **Alias**: `p`, `port`
- **Nilai Asas**: `(Sifat Pelayan)`

Menetapkan port pelayan.

#### `server-name`

- **Nilai Asas**: `A Pelayan Plazma`

Menetapkan nama pelayan.

#### `spigot-settings`

- **Alias**: `S`
- **Nilai Asas**: `spigot.yml`

Menetapkan nama dan lokasi [Fail Konfigurasi Spigot](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Mencetak versi Plazma.

#### `world-dir`

- **Alias**: `W`, `alam semesta`, `bekas alam semesta`
- **Nilai Asas**: `(Folder Pelayan)`

Menetapkan lokasi di mana fail dunia disimpan.

#### `world-name`

- **Alias**: `w`, `dunia`
- **Nilai Asas**: `(Sifat Pelayan)`

Menetapkan nama fail dunia.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Lokasi tambahan yang menentukan bagaimana argumen diproses berubah.

[^3]: Sebagai contoh, jika ingin menetapkan `Plazma.iKnowWhatIAmDoing` kepada `true`, menggantikan `-DPlazma.iKnowWhatIAmDoing=true` dengan `-DPlazma.iKnowWhatIAmDoing` akan berfungsi sama.

[^4]: Sebagai contoh, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Pendeteksi acara.

[^6]: Pendeteksi acara.

[^7]: Pelayan.

[^8]: Isyarat yang mengesahkan bahawa pelayan berhubung dengan betul seperti denyutan jantung.

[^9]: Dengan menggunakan ciri pembersihan AFK Purpur, anda boleh mengeluarkan pemain yang tidak hadir.

[^10]: Sistem Penulisan Cebisan Serentak, Sync Chunk Write System.

[^11]: `AMARAN! Plazma mungkin menyebabkan masalah yang tidak dijangka, jadi pastikan untuk mengujinya dengan teliti sebelum menggunakannya di server awam.`

[^12]: Dalam permainan, `pengoptimuman dunia` beroperasi dengan prinsip yang sama.

[^13]: Protokol Internet, IP.

[^14]: Pentadbir `Tahap 2` atau yang lebih tinggi dikecualikan.