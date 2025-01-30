---
description: Pelajari tentang argumen awal dan properti sistem.
---

# 🎛️ Argumen dan Properti

Argumen awal dan properti sistem adalah nilai tambahan yang ditambahkan ke [perintah yang digunakan](#user-content-fn-1)[^1] untuk menjalankan Plazma, yang secara keseluruhan memengaruhi operasi Plazma.

[Posisi yang ditambahkan ke perintah](#user-content-fn-2)[^2] akan dibagi menjadi **Argumen Awal** dan **Properti Sistem** sesuai dengan posisi tersebut.

***

## Properti Sistem <a href="#id-1" id="id-1"></a>

Properti sistem dimasukkan sebelum `-jar` dan diproses oleh JVM sebelum Plazma diinisialisasi.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Cara Penggunaan <a href="#id-1.1" id="id-1.1"></a>

Properti sistem dimasukkan sebagai argumen perintah Java antara `java` dan `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` menandakan argumen tersebut adalah argumen tambahan yang ditambahkan ke Plazma, tidak bawaan JVM, dan

Jika tidak ada nilai yang dimasukkan ke dalam properti, nilai akan tetap [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Default**: `750`

Mengirimkan entitas dalam paket terpisah jika melebihi nilai yang ditetapkan.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Default**: `8192`

Menetapkan ukuran maksimal paket yang dapat diterima oleh server sekaligus.

#### `Paper.ignoreJavaVersion`

- **Tipe**: `Boolean`
- **Default**: `False`

Menonaktifkan pengecekan versi Java.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Ini dapat menyebabkan kerusakan permanen pada file-file di dunia dan mempengaruhi mekanisme permainan secara keseluruhan.

Semua masalah yang timbul dari penggunaan ini menjadi tanggung jawab pengguna, dan Plamza tidak memberikan dukungan untuk hal ini.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Default**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Default**: `80`

Menetapkan panjang maksimal karakter yang dapat dimasukkan dalam satu baris tanda.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Default**: `(versi dunia) + 1`

Menetapkan versi informasi pembaruan dunia yang akan diinisialisasi terlebih dahulu.

Berguna saat perlu memperbarui sejumlah besar chunk, tetapi jarang digunakan dalam kasus lain.

#### `Paper.parseYamlCommentsByDefault`

- **Tipe**: `Boolean`
- **Default**: `True`

Mengaktifkan pengolahan komentar dalam file YAML secara default.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Default**: `30`

Mengeluarkan pemain dari server jika tidak menerima data apa pun dari pemain selama jumlah waktu tertentu (dalam detik).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Tabrakan**: `Plazma.disableConfigOptimization`

Mengoptimalkan konfigurasi awal secara lebih kuat.

Mengaktifkan ini akan membuat server lebih cepat dan aman, namun dapat berdampak besar pada gameplay.

#### `Plazma.disableConfigOptimization`

- **Tipe**: `Boolean`
- **Default**: `false`
- **Tabrakan**: `Plazma.aggressiveOptimize`

Tidak mengoptimalkan konfigurasi awal.

Ini menggunakan konfigurasi default dari Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipe**: `Boolean`
- **Default**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tipe**: `Boolean`
- **Default**: `false`

Menonaktifkan branding Plazma dan menggunakan favicon server default vanila.

#### `Plazma.useVanillaConfiguration`

- **Tipe**: `Boolean`
- **Default**: `false`
- **Tabrakan**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Ini dapat memiliki dampak besar pada keamanan dan performa server.

Semua masalah yang timbul dari penggunaan properti ini menjadi tanggung jawab administrator server.
{% endhint %}

Mengatur konfigurasi awal menjadi nilai default yang disediakan oleh Mojang.

Ini menonaktifkan semua patch kerentanan yang diterapkan oleh Paper.

Patch kerentanan dapat diaktifkan kembali dalam konfigurasi Paper atau Plazma.

#### `Plazma.vanillaize`

- **Tipe**: `Boolean`
- **Default**: `true`
- **Tabrakan**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Mengatur konfigurasi awal menjadi lebih mendekati vanila.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Nilai Default**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Nilai Default**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Memulai server ke dalam dunia demo.

#### `eraseCache`

Menghapus file cache yang tersisa setelah upgrade dunia.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Menonaktifkan panel antarmuka grafis.

#### `nojline`

Menonaktifkan JLine dan menggunakan konsol vanilla.

#### `online-mode`

- **Alias**: `o`
- **Nilai Default**: `(Properti Server)`

Memilih untuk memverifikasi pemain melalui server otentikasi Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Nilai Default**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Menetapkan lokasi [File Konfigurasi PaperSpigot](../reference/configurations/paper/README.md) yang telah dihentikan penggunaannya.

Digunakan untuk memindahkan konfigurasi lama ke file konfigurasi baru dan tidak digunakan lagi setelahnya.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Nilai Default**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Nilai Default**: `plugins`

Menetapkan lokasi folder plugin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Nilai Default**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Nilai Default**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Memulai server dalam keadaan vanilla lengkap.

#### `server-ip`

- **Alias**: `h`, `host`
- **Nilai Default**: `(Properti Server)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Administrator `level 2` ke atas dikecualikan.

[^14]: Protokol Internet, IP.
