---
description: Ketahui tentang argumen permulaan dan sifat sistem.
---

# 🎛️ Argumen dan Sifat

Permulaan dan sifat sistem adalah nilai tambahan kepada [perintah yang digunakan](#user-content-fn-1)[^1] dalam pelaksanaan Plazma, yang memberi kesan keseluruhan kepada operasi Plazma.

[Posisi yang dilampirkan pada arahan](#user-content-fn-2)[^2] akan dibahagikan kepada **Argumen Permulaan** dan **Sifat Sistem**.

***

## Sifat sistem <a href="#id-1" id="id-1"></a>

Sifat sistem dimasukkan sebelum `-jar` dan diproses oleh JVM sebelum Plazma diinisialisasi.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Cara Penggunaan <a href="#id-1.1" id="id-1.1"></a>

Sifat sistem dimasukkan sebagai argumen perintah Java antara `java` dan `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` menandakan argumen tersebut adalah tambahan khas untuk Plazma dan tidak disertakan dalam JVM,

Jika tidak ada nilai yang dimasukkan ke dalam sifat, nilai akan tetap [`benar`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Nilai Lalai**: `750`

Jika entiti melebihi nilai yang ditetapkan, ia akan dihantar melalui paket berganda.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Nilai Lalai**: `8192`

Tetapkan saiz maksimum paket yang boleh diterima oleh pelayan pada satu masa.

#### `Paper.ignoreJavaVersion`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `False`

Matikan pengesahan versi Java.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Ini boleh merosakkan fail dan dunia secara kekal, menyebabkan kegagalan mekanisme permainan.

Semua masalah yang timbul daripada penggunaan ini adalah tanggungjawab pengguna dan Plamza tidak akan memberikan sebarang sokongan untuk itu.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Nilai Lalai**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Nilai Lalai**: `80`

Tetapkan panjang maksimum teks pada satu baris tanda.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Nilai Lalai**: `(versi dunia) + 1`

Tetapkan versi maklumat pembetulan data yang perlu diinisialisasi terlebih dahulu.

Berguna jika perlu mengemaskini banyak chunk, tetapi jarang digunakan dalam keadaan biasa.

#### `Paper.parseYamlCommentsByDefault`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `True`

Aktifkan pemprosesan komen YAML secara lalai.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Nilai Lalai**: `30`

Pemain akan dikeluarkan jika tiada data diterima daripada mereka selama tempoh yang ditetapkan (dalam saat).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Konflik**: `Plazma.disableConfigOptimization`

Optimum konfigurasi awal yang lebih kuat.

Mengaktifkan ini akan membuat server lebih cepat dan lebih selamat, tetapi boleh memberi impak besar kepada permainan.

#### `Plazma.disableConfigOptimization`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `false`
- **Konflik**: `Plazma.aggressiveOptimize`

Tidak mengoptimumkan konfigurasi awal.

Ini akan menggunakan konfigurasi asas Kertas.

#### `Plazma.iKnowWhatIAmDoing`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `false`

Melumpuhkan jenama Plazma dan menggunakan favicon asas vanila untuk server.

#### `Plazma.useVanillaConfiguration`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `false`
- **Konflik**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Ini boleh memberi kesan besar kepada keselamatan dan prestasi server.

Sebarang masalah yang timbul dari penggunaan ciri ini adalah tanggungjawab pentadbir server.
{% endhint %}

Menggunakan nilai asas yang disediakan oleh Mojang untuk konfigurasi awal.

Ini mematikan semua penambalan kelemahan yang digunakan dalam Paper.

Penambalan kelemahan boleh diaktifkan semula dalam konfigurasi Paper atau Plazma.

#### `Plazma.vanillaize`

- **Jenis**: `Boolean`
- **Nilai Lalai**: `true`
- **Konflik**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Menetapkan konfigurasi awal kepada sesuatu yang lebih hampir kepada vanila.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Nilai Asas**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Nilai Asas**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Memulakan pelayan dengan dunia demo.

#### `eraseCache`

Menghapus fail cache yang tinggal selepas menaik taraf dunia.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Matikan panel antara muka grafik.

#### `nojline`

Matikan JLine dan gunakan konsol biasa.

#### `online-mode`

- **Alias**: `o`
- **Nilai Asas**: `(Sifat Pelayan)`

Pilih untuk mengesahkan pemain dengan pelayan pengesahan Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Nilai Asas**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Menetapkan lokasi [Fail Konfigurasi PaperSpigot](../reference/configurations/paper/README.md) yang tidak lagi digunakan.

Digunakan untuk memindahkan konfigurasi sedia ada ke fail konfigurasi baru dan tidak digunakan selepas itu.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Nilai Asas**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Nilai Asas**: `plugins`

Menetapkan lokasi folder plugin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Nilai Asas**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Nilai Asas**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Memulakan pelayan dalam keadaan vanilla penuh.

#### `server-ip`

- **Alias**: `h`, `host`
- **Nilai Asas**: `(Sifat Pelayan)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Pentadbir `Tahap 2` atau yang lebih tinggi dikecualikan.

[^14]: Protokol Internet, IP.
