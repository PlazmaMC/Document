---
description: Ketahui cara membuat server dengan Plazma.
---

# 👟 Mula

Untuk menggunakan Plazma secara stabil, sistem perlu memenuhi keperluan berikut:

|                  | Minimum | Disyorkan |
| :--------------: | ------: | --------: |
|     Seni bina    |     x64 |         - |
|        RAM       |     8GB |      16GB |
| Ruangan simpanan |     1GB |       8GB |
|        JRE       |      17 |        21 |

Untuk mengedit fail konfigurasi dengan lancar, disarankan untuk memasang editor seperti [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Pemasangan JRE

Seperti yang dinyatakan dalam namanya, Minecraft: **"Java"** Edition dibangunkan dengan Java, dan untuk menjalankannya, JRE[^1] diperlukan.

Plazma adalah platform server rasmi Mojang Studios yang [berasaskan](#user-content-fn-2)[^2], oleh itu JRE juga perlu dipasang untuk menggunakan Plazma.

### 1.1 Pemeriksaan Kewujudan JRE

Untuk memeriksa sama ada JRE dipasang dalam sistem, masukkan [`cmd /k java --version`](#user-content-fn-4)[^4] dalam [tetingkap run](#user-content-fn-3)[^3] dan jalankan.

Jika output adalah seperti berikut, langkau ke [langkah 2](setup.md#id-2).

{% code title="Output yang betul" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Jika output tidak seperti di atas, atau seperti di bawah, bermakna tiada JRE atau terlalu lama; oleh itu, lakukan [langkah 1.2](setup.md#id-1.2).

{% code title="JRE tidak dipasang" lineNumbers="true" %}

```log
'java' bukanlah program perintah internal atau eksternal, program yang dapat dijalankan, atau
file batch.
```

{% endcode %}

{% code title="JRE sudah terlalu lama" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Pemasangan JRE

Dalam panduan ini, kami akan menggunakan Azul Zulu sebagai [satu dari jenis](#user-content-fn-5)[^5] JRE.

Selepas pemasangan, sila jalankan semula [Langkah 1.1](setup.md#id-1.1) untuk memastikan pemasangan telah berjaya.

{% tabs %}

{% tab title="Windows" %}

1. Pertama, muat turun **JDK 21** dari [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) dalam format `.msi`.
2. Jalankan penyelenggaraan muat turun dan klik `Next`.
3. Di tengah kiri tetingkap, aktifkan `Set JAVA_HOME variable` dan kemudian klik `Next`.
4. Tekan `Install` untuk menyelesaikan pemasangan JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) memuat turun **JDK 21** dari wizard pemasangan dalam format `.dmg` dan jalankan untuk memasang JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Pertama, jalankan arahan berikut dalam terminal untuk menambahkan repositori Azul Zulu ke APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Kemudian, jalankan arahan berikut dalam terminal untuk memasang JRE.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Anda boleh memasang JRE dengan menjalankan arahan berikut.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Muat Turun Plazma

Plazma menyediakan pelbagai jenis fail eksekusi.

{% hint style="warning" %}

**Kebanyakan kes menggunakan `Reobf Paperclip`.**

Kandungan di bawah adalah untuk mereka yang ingin mengetahui tentang pembangun atau ciri-ciri setiap jenis.\
Jika anda pengguna biasa, anda boleh terus ke [Langkah 3](setup.md#id-3) tanpa sebarang masalah.

{% endhint %}

<details>

<summary>Ketahui lebih lanjut</summary>

Nama fail eksekusi adalah `plazma-(pengurus versi)-1.20.4-R0.1-SNAPSHOT-(jenis pemetaan).jar` yang telah ditetapkan.

- **Jenis Pemetaan**\
  Pemetaan adalah jenis peta yang menghubungkan kod sebenar Minecraft dengan kod yang telah digarap.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.5부터 사용이 종료될 예정입니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다.
- **Pengurus Versi**\
  Pengurus versi adalah pustaka yang diperlukan untuk menjalankan pelayan dan berfungsi sebagai pelancar pelayan yang memuat turun pustaka dan memohonkan fail pelayan.
  - **Paperclip**\
    Dicipta oleh pasukan PaperMC untuk Paper dan platform terbitan lain, berperanan dalam memuat turun pustaka dan menyelaraskan pelayan.
  - **Bundler**\
    Pengurus versi Minecraft Vanilla.

</details>

***

## 3. Cipta Skrip Mula

Untuk memulakan Plazma dengan mudah dan membolehkan pelayan secara automatik mulakan semula, anda perlu membuat [skrip mula](#user-content-fn-6)[^6].

Anda boleh membuat skrip mula melalui [Flags.sh](https://flags.sh).\
Hanya masukkan [jumlah memori yang hendak digunakan oleh Plazma](#user-content-fn-8)[^8] dan perintah akan dioptimumkan secara automatik.

Anda boleh muat turun skrip mula melalui butang muat turun di bahagian kiri bawah.\
**Pastikan skrip mula yang dimuat turun sepadan dengan sistem operasi anda.**

***

## 4. Penyusunan Fail

Pindahkan skrip mula yang dimuat turun dan Plazma ke folder baru sekarang.

{% hint style="warning" %}

**Nama folder mesti tanpa spasi dan dalam bahasa Inggeris.**

Jika tidak, Plazma atau JRE mungkin tidak berfungsi dengan betul.

{% endhint %}

Kini jalankan skrip mula. Untuk Windows, <mark style="background-color:orange;">Anda perlu memilih **Benarkan** dalam tetingkap pilihan Kebenaran Rangkaian</mark>.

***

## 5. Persetujuan EULA

Apabila anda menjalankan skrip mula, fail `eula.txt` akan dicipta dalam folder.

EULA[^9] adalah perjanjian lesen yang perlu anda setujui untuk menggunakan perkhidmatan [Mojang Studios](#user-content-fn-10)[^10].

Jika anda tidak bersetuju dengan EULA, anda tidak boleh memulakan pelayan dan mungkin akan dikenakan [sanksi jika melanggar EULA.](#user-content-fn-11)[^11]

Untuk bersetuju dengan EULA, ubah `eula=false` kepada `eula=true` dalam fail `eula.txt` dan simpan.

***

## 6. Membenarkan Sambungan Luar (Windows)

Sistem operasi moden secara asasnya menghalang akses luaran melalui **firewall** dan **router** untuk melindungi daripada akses berbahaya.

Untuk Windows, kerana anda telah membenarkan dalam [Langkah 3](setup.md#id-3), anda hanya perlu melakukan penerusan port.

{% hint style="info" %}

**Panduan ini diasaskan pada sistem operasi Windows dan [UPnP](#user-content-fn-12)[^12] serta router yang boleh digunakan.**

Jika router anda tidak menyokong UPnP, anda perlu mencari maklumat mengikut panel router yang berbeza.

Atau anda boleh menggunakan [Ngrok](https://ngrok.com/) untuk mencipta alamat sementara.
{% endhint %}

{% hint style="warning" %}

**Untuk sistem operasi UNIX seperti Linux atau macOS, cara konfigurasi firewall berbeza mengikut perkhidmatan, jadi anda perlu mencari maklumat sendiri.**

{% endhint %}

### 6.1 Semak Keperluan Penerusan Port

Masukkan dan jalankan seperti yang berikut dalam tetingkap eksekusi.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jika output adalah `True`, anda boleh berhenti di sini, tetapi jika `False`, anda perlu tetapkan penerusan port.

### 6.2 Menyambung ke Pelayan

{% tabs %}

{% tab title="Akses dari Luar" %}

Jika anda tidak memerlukan penghantaran port atau telah berjaya mengkonfigurasi penghantaran port, anda kini boleh menyambung ke pelayan.

Alamat yang digunakan untuk menyambung ke pelayan boleh disemak [di sini](https://ip.pe.kr/).

{% endtab %}

{% tab title="Cubaan Penerusan Port dengan UPnP" %}

Di dalam `purpur.yml` folder pelayan, aktifkan `network.upnp-port-forwarding` kepada `true`.

Kemudian, mulakan semula pelayan dan Plazma akan cuba meneruskan port secara automatik.

Kejayaan UPnP bergantung kepada mesej yang dipaparkan dalam konsol, di mana ia akan menunjukkan `[UPnP] (mesej)`.

| Mesej                         | Makna                                        |
| ----------------------------- | -------------------------------------------- |
| `Berjaya membuka port (port)` | Penerusan port berjaya.                      |
| `Port (port) sudah terbuka`   | Port telah digunakan oleh perkhidmatan lain. |
| `Gagal membuka port (port)`   | Penerusan port gagal.                        |
| `Perkhidmatan tidak tersedia` | Router tidak menyokong UPnP.                 |

Apabila pelayan ditutup, Plazma akan menutup port secara automatik.

{% endtab %}

{% tab title="Mencipta Alamat Sementara dengan Ngrok" %}

Penggunaan Ngrok berguna untuk ujian sementara, permainan berpasukan, atau bermain dengan rakan-rakan.

1. Muat turun fail ZIP `Windows (64-bit)` dari [Laman Web Ngrok](https://ngrok.com/download).
2. Letakkan fail Ngrok yang dimuat turun ke dalam folder pelayan.
3. Di [Papan Pemuka Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), cipta [token pengesahan](#user-content-fn-13)[^13].
4. Di dalam folder pelayan, jalankan arahan yang dipaparkan dalam `Command Line`.
5. Tambahkan `start /b ngrok tcp --region jp 25565` di bahagian atas skrip eksekusi, dan `taskkill /f /t /im ngrok.exe` di bahagian bawahnya.
6. Dari mesej yang dipaparkan di bahagian atas konsol `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`, `0.tcp.jp.ngrok.io:12345` adalah alamat pelayan.
7. Sekarang anda boleh mengakses alamat tersebut dari luar.

{% endtab %}

{% tab title="Sambungan Lokal" %}

Jika ingin menyambung ke pelayan dari tempatan, boleh menggunakan `cmd /k ipconfig` dalam tetingkap run untuk menyambung ke `Alamat IPv4` yang dipaparkan.

Contohnya, apabila output seperti berikut dipaparkan selepas menjalankan arahan tersebut,

```log
Konfigurasi IP Windows

Adaptor Ethernet Ethernet:

    Sufiks DNS yang Terhubung. . . . :
    Alamat IPv4. . . . . . . . . : 192.168.3.7
    Masker Subnet . . . . . . . : 255.255.255.0
    Gateway Default. . . . . . : 192.168.3.1

```

Anda boleh menyambung ke pelayan dari komputer tempatan dengan mencuba menyambung ke alamat `192.168.3.7` yang dipaparkan pada IPv4.

Jika pelayan dan permainan dijalankan pada PC yang sama, anda boleh menyambung melalui `localhost`.

{% endtab %}
{% endtabs %}

## 7. Tahap Pembangunan

Setelah berjaya memulakan pelayan dan pelayan berfungsi dengan betul, kini tiba masanya untuk menyesuaikan pelayan.

Ketahui cara untuk menyesuaikan pelayan melalui panduan di bawah.

{% content-ref url="langkah-seterusnya.md" %}
[langkah-seterusnya.md](langkah-seterusnya.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java execution environment.

[^2]: Paper yang berasaskan Plazma dibina di atas Spigot, yang pada gilirannya berasaskan platform pelayan rasmi Spigot.

[^3]: Tombol Windows + R

[^4]: Untuk Linux, jalankan `java --version` di terminal

[^5]: JRE merupakan salah satu projek sumber terbuka yang terdapat pelbagai jenis seperti platform pelayan Minecraft.

[^6]: Biasanya dikenali sebagai **launcher**.

[^7]: Aktifkan "Auto-restart" untuk pelayan akan restart secara automatik. Anda boleh menamatkan dengan memasukkan `Control + C`.

[^8]: Tidak disarankan melebihi separuh kapasiti sistem.

    Sebagai contoh, apabila kapasiti memori keseluruhan sistem adalah 8GB, tidak disyorkan untuk mengaturnya melebihi 4GB.

[^9]: Perjanjian Lesen Pengguna Akhir, Perjanjian Lesen Pengguna Akhir. Sila rujuk [Laman Web Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines) untuk maklumat lanjut.

[^10]: Korporasi Microsoft.

[^11]: Di Korea, mengikut Seksyen 32(1)(9) Undang-Undang Pemajuan Industri Permainan, **Korea Microsoft Corporation** boleh mengambil tindakan undang-undang.

[^12]: Plug & Play Universal. Purpur yang termasuk dalam Plazma secara automatik berkomunikasi dengan router melalui teknologi ini hanya membuka port apabila server sedang berjalan, oleh itu, tidak perlu meneruskan port secara manual.

[^13]: Jika tiada akaun, daftar masuk ke Ngrok menggunakan akaun Google atau GitHub.
