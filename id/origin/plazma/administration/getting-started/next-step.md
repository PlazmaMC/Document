---
description: Pelajari cara menyesuaikan server.
---

# 📶 Tahap Pengembangan

Alasan menggunakan platform server yang dimodifikasi seperti Plazma tanpa menggunakan platform resmi yang disediakan oleh Mojang Studios adalah kemampuan **penyesuaian pengguna** yang kuat.

Berikut adalah beberapa cara untuk menyesuaikan dan menggunakan Plazma.

## Modifikasi Konfigurasi <a href="#id-1" id="id-1"></a>

Cara paling dasar untuk menyesuaikan Plazma adalah dengan memodifikasi konfigurasi.

Plazma menyediakan pengaturan konfigurasi yang kuat mulai dari mekanisme permainan hingga atribut monster.

Silakan lihat penjelasan mengenai konfigurasi Plazma pada halaman berikut.

{% content-ref url="../reference/configurations/" %}
[konfigurasi](../reference/configurations/)
{% endcontent-ref %}

***

## Penggunaan Plugin <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma mendukung semua plugin berbasis kertas dengan baik.**

Untuk plugin Spigot, mungkin ada beberapa yang tidak berfungsi karena perubahan pemetaan Paper sejak 1.20.5, tetapi sebagian besar plugin yang berbasis Paper seperti Paper, Pufferfish, dan Purpur akan berfungsi dengan baik di Plazma. Jika ada masalah dengan fungsi plugin, segera [laporkan kesalahan ini](../diagnosis/plugins.md) kepada Plazma.

{% endhint %}

Ini adalah alasan utama penggunaan Plazma dan cara terkuat untuk menyesuaikan Plazma.
Ekosistem plugin yang kuat dari Plazma memungkinkan server untuk disesuaikan dengan mudah.

Ada beberapa cara untuk mencari dan mengunduh plugin. Beberapa plugin diunggah ke layanan repositori publik, sementara yang lain diunggah ke GitHub atau situs web mereka sendiri.

{% hint style="caution" %}

**Plugin dapat mengakses sistem secara langsung!**

Selalu periksa keamanan plugin sebelum menerapkannya dengan menggunakan layanan seperti VirusTotal, atau unduh plugin dari layanan tepercaya.

{% endhint %}

Ada berbagai layanan yang digunakan untuk mengunduh plugin. Di antaranya, [Forum SpigotMC](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) melakukan peninjauan sebelum plugin diunggah, sehingga hanya plugin yang aman yang disebarkan.

### Menerapkan Plugin <a href="#id-2.1" id="id-2.1"></a>

Setelah mengunduh plugin, saatnya menerapkannya.

1. Plugin berbentuk `.jar` atau `Java Executable File`. Beberapa plugin dikompresi dalam file zip, dalam kasus tersebut, ekstrak file yang mengandung 'bukkit', 'spigot', atau 'paper', jika ada file 'fat' bersamaan, gunakan file 'fat' tersebut.
2. Letakkan file yang diunduh ke dalam folder `plugins` di folder server, lalu (re)start server.
3. Saat Plazma dimulai, akan ada output baru di konsol.
   Ini menandakan bahwa Plazma telah berhasil memuat plugin dengan baik.
4. Meskipun Plazma telah berhasil memuat plugin, mungkin plugin tidak berjalan dengan baik.
   Dengan menggunakan perintah `/plugins`, Anda dapat melihat plugin yang saat ini dimuat di server.
   Jika nama plugin yang diinstal tidak ditandai dengan <mark style="background-color:red;">merah</mark>, tetapi <mark style="background-color:green;">hijau</mark>, itu berarti plugin telah dimuat dengan baik.

Jika plugin tidak dimuat dengan baik, Anda dapat menemukan solusi di halaman berikut.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Menggunakan Data Pack <a href="#id-3" id="id-3"></a>

Data Pack adalah cara kustomisasi yang disediakan Minecraft, mirip dengan [Resource Pack](#user-content-fn-1).

Dengan menggunakan Data Pack, Anda dapat menambahkan spesies baru dan tantangan dalam permainan, serta melakukan modifikasi pada bagian tertentu di dalam permainan.

{% hint style="caution" %}

**Data Pack dapat merusak dunia!**

Beberapa Data Pack yang rusak dapat merusak dunia dan tidak dapat dikembalikan.

Sebaiknya, cadangkan dunia sebelum menerapkan Data Pack.

{% endhint %}

Data Pack juga dapat diunduh dari berbagai layanan seperti [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs), dan layanan lainnya.

Setelah mengunduh Data Pack, letakkan di folder `datapacks` di folder dunia server.
Jika folder tidak ada, buat folder tersebut sebelum menambahkan Data Pack.

{% hint style="warning" %}

**[Beberapa paket data](#user-content-fn-2)[^2] mungkin tidak diterapkan dengan benar saat pertama kali diterapkan.**

Untuk mengantisipasi hal ini, disarankan untuk me-restart server **2 kali** setelah menerapkan Data Pack.

{% endhint %}

Data Pack dapat dengan mudah rusak setiap kali Minecraft diperbarui.

Khususnya, jika Data Pack rusak, server dapat mengalami crash, oleh karena itu, penting untuk melakukan pengujian yang memadai sebelum memperbarui server.

{% hint style="info" %}

**Setelah perintah memulai server, masukkan `safeMode` untuk menonaktifkan semua Data Pack dan kemudian mulai server.**

[Untuk informasi lebih lanjut, lihat `Referensi > Argumen dan Properti`](../reference/arguments.md#safeMode)

{% endhint %}

Data Pack yang telah diterapkan dapat dikonfirmasi melalui perintah `/datapack list`.

***

## Optimasi <a href="#id-4" id="id-4"></a>

Plazma telah menerapkan banyak patch optimasi. Selain itu, ketika Plazma pertama kali dimulai, konfigurasinya akan dioptimalkan secara otomatis sehingga jika mengikuti panduan [Mulai](./README.md), tidak perlu melakukan tindakan optimasi tambahan.

Namun, jika banyak pemain yang masuk atau ukuran dunia sangat besar, Anda dapat melakukan tindakan optimasi tambahan melalui panduan di bawah ini.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proksi <a href="#id-5" id="id-5"></a>

Proksi menghubungkan server satu sama lain dan memungkinkan pemain berpindah server atau berkomunikasi dengan server lain tanpa tindakan tambahan.

Lihat informasi tentang pengaturan proksi yang aman dan benar di halaman berikut.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Keamanan <a href="#id-5" id="id-5"></a>

Minecraft telah berkembang sehingga mudah untuk mendapatkan [mesin serangan kerentanan](#user-content-fn-3)[^3] secara online.

Meskipun sebagian besar kerentanan yang dapat dieksploitasi dalam permainan umumnya [diblokir secara default](#user-content-fn-4)[^4],
menggunakan pemuat pihak ketiga untuk mengeksploitasi kerentanan tidak diblokir.

Oleh karena itu, jika server terbuka, disarankan untuk menginstal plugin anti-cheat untuk mencegah penggunaan kerentanan, serta mengkonfigurasi proksi, restart otomatis, dan pencadangan agar server dapat pulih dengan cepat jika terjadi kegagalan.

### Pengaturan Izin <a href="#id-5.1" id="id-5.1"></a>

Beberapa perintah administrator plugin mungkin memiliki kerentanan jika izinnya tidak diatur dengan benar.

Disarankan untuk menggunakan plugin manajemen izin seperti [LuckPerms](https://luckperms.net/) untuk membatasi hak akses pengguna reguler.

### Pemblokiran X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray adalah salah satu kerentanan yang mudah digunakan bahkan dalam klien optimasi dasar.

Plazma menyediakan konfigurasi untuk secara default memblokir X-Ray.

Lihat cara dan penjelasan pemblokiran X-Ray di halaman berikut.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

Jika hanya beberapa pengguna yang diizinkan masuk ke server, disarankan untuk menggunakan [Ngrok](./README.md#id-6.2) untuk menggunakan [alamat server yang dienkripsi](#user-content-fn-5)[^5] atau mengatur whitelist untuk mencegah pemain lain masuk ke server.

Anda dapat mengizinkan atau melarang pemain masuk melalui perintah `/whitelist add <player>` atau `/whitelist remove <player>` di konsol server.

Gunakan `/whitelist query` untuk melihat pemain yang diizinkan masuk.

***

[^1]: Atau Add-on Minecraft: Bedrock Edition.

[^2]: Menambahkan spesies baru dan lainnya.

[^3]: Biasanya disebut sebagai "cheat".

[^4]: Jika konfigurasi tidak dioptimalkan, Plazma sudah usang, atau terdapat kerentanan baru, pemblokiran mungkin tidak efektif.

[^5]: Pemain terhubung ke server melalui server proksi Ngrok, dan alamat Ngrok yang dikeluarkan setiap kali restart akan berbeda.
