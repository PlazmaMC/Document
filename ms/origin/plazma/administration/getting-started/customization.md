---
description: Ketahui cara menggunaan semula pelayan.
---

# 🎨 Penggunaan semula

Alasan mengapa menggunakan platform server yang telah diubah seperti Plazma daripada platform server rasmi yang disediakan oleh Mojang Studios adalah kerana ia membolehkan **penyesuaian pengguna** yang kuat.

Berikut adalah beberapa cara untuk menyesuaikan dan menggunakan Plazma.

## Penyesuaian Konfigurasi <a href="#id-1" id="id-1"></a>

Cara paling asas untuk menyesuaikan Plazma adalah dengan mengubah konfigurasi.

Plazma menyediakan pengaturan konfigurasi yang kuat, mulai dari mekanisme permainan hingga sifat-sifat entiti.

Sila rujuk halaman di bawah untuk penjelasan mengenai konfigurasi Plazma.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## Penggunaan Plugin <a href="#id-2" id="id-2"></a>

{% hint style="kejayaan" %}

**Plazma menyokong semua plugin berasaskan kertas dengan baik.**

Bagi plugin Spigot, mungkin tidak berfungsi sepenuhnya disebabkan oleh perubahan pemetaan Paper sejak 1.20.5, tetapi kebanyakan plugin yang berasaskan Paper seperti Paper, Pufferfish, dan Purpur berfungsi dengan baik di Plazma. Jika tidak berfungsi dengan betul, sila [laporkan segera.](../diagnosis/plugins.md)

{% endhint %}

Ini adalah sebab utama penggunaan Plazma dan cara terkuat untuk mengkustomisasi Plazma.
Ekosistem plugin yang kuat bagi Plazma membolehkan pengguna mengkustomisasi server dengan mudah.

Terdapat pelbagai cara untuk mencari dan memuat turun plugin. Sesetengah plugin dimuat naik ke perkhidmatan repositori awam, manakala yang lain dimuat naik ke GitHub atau laman web sendiri.

{% hint style="amaran" %}

**Plugin boleh mengakses sistem secara langsung!**

Pastikan plugin selamat sebelum menggunakannya dengan menggunakan perkhidmatan seperti VirusTotal atau muat turun plugin dari perkhidmatan yang dipercayai.

{% endhint %}

Terdapat pelbagai perkhidmatan untuk memuat turun plugin. Antara perkhidmatan yang digunakan untuk muat naik plugin termasuk [Forum SpigotMC](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) yang melakukan penilaian sebelum membenarkan plugin tidak selamat disebarkan.

### Memasang Plugin <a href="#id-2.1" id="id-2.1"></a>

Setelah memuat turun plugin, tiba masanya untuk memasangnya.

1. Plugin berbentuk `.jar` atau `Fail Eksekutif Java`.\
   Beberapa plugin mungkin berbentuk fail yang ditekan dan perlu ditekan semula, jika begitu,\
   buka fail yang mengandungi `bukkit`, `spigot`, atau `paper` dan gunakan fail yang mengandungi `fat`.
2. Letakkan fail yang dimuat turun ke dalam folder `plugins` dalam folder pelayan dan mulakan semula pelayan.
3. Apabila Plazma dimulakan, mesej baru akan dipaparkan di konsol.
   Ini bermakna Plazma telah memuatkan plugin dengan betul.
4. Walaupun Plazma telah memuatkan plugin dengan betul, mungkin plugin tidak dapat dimulakan.
   Dengan menggunakan perintah `/plugins`, anda boleh melihat senarai plugin yang dimuatkan pada pelayan.
   Jika nama plugin yang dipasang tidak berwarna <mark style="background-color:red;">merah</mark> tetapi berwarna <mark style="background-color:green;">hijau</mark>, bermakna plugin telah dimuatkan dengan betul.

Jika plugin tidak dimuatkan dengan betul, anda boleh mencari penyelesaian di halaman berikut.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Penggunaan Data Pack <a href="#id-3" id="id-3"></a>

Data Pack adalah cara untuk mengkustomisasi Minecraft yang disediakan secara asas, serupa dengan [Pak Sumber](#user-content-fn-1)[^1].

Dengan menggunakan Data Pack, anda boleh menambahkan kumpulan makhluk baru dan cabaran permainan lain dalam permainan.

{% hint style="amaran" %}

**Data Pack boleh merosakkan dunia!**

Beberapa Data Pack yang rosak boleh merosakkan dunia dan ini tidak dapat dikembalikan.

Oleh itu, disarankan untuk membuat salinan data dunia sebelum menggunakan Data Pack.

{% endhint %}

Data Pack boleh didapati dari pelbagai perkhidmatan seperti [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) dan lain-lain.

Selepas memuat turun Data Pack, letakkan dalam folder `datapacks` dalam folder dunia pelayan untuk menggunakannya.
Jika folder tidak wujud, anda boleh ciptakannya dan masukkan Data Pack di dalamnya.

{% hint style="warning" %}

**Beberapa [Data Pack](#user-content-fn-2)[^2] mungkin tidak berfungsi dengan betul pada permulaan.**

Untuk kes seperti ini, disarankan untuk memulakan semula pelayan **2 kali**.

{% endhint %}

Data Pack mudah rosak setiap kali Minecraft dikemaskini.

Khususnya, jika Data Pack rosak sepenuhnya, menyebabkan pelayan mengalami kegagalan, oleh itu,
ujian yang mencukupi sebelum mengemaskini pelayan adalah penting.

{% hint style="info" %}

**Selepas memulakan pelayan, masukkan `safeMode` selepas arahan permulaan untuk menonaktifkan semua Data Pack sebelum memulakan semula pelayan.**

[Sila rujuk `Rujukan > Argumen dan Sifat` untuk maklumat lanjut.](../reference/arguments.md)

{% endhint %}

Data Pack yang dipasang boleh disahkan dengan menggunakan perintah `/datapack list`.

***

[^1]: Atau tambahan untuk Edisi Minecraft: Bedrock.

[^2]: Menambah kumpulan makhluk dan lain-lain.
