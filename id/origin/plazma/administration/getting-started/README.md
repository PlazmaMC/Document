---
description: Pelajari cara membuat server dengan Plazma.
---

# 👟 Mulai

Untuk menggunakan Plazma secara stabil, sistem harus memenuhi persyaratan berikut:

|                   | Minimum | Disarankan |
| :---------------: | :------ | :--------- |
|     Arsitektur    | x64     | -          |
|        RAM        | 8GB     | 16GB       |
| Ruang Penyimpanan | 1GB     | 8GB        |
|        JRE        | 17      | 21         |

Untuk pengeditan file konfigurasi yang lancar, disarankan untuk menginstal editor seperti [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalasi JRE

Seperti namanya, Minecraft: **"Java"** Edition dikembangkan dengan Java, sehingga memerlukan JRE[^1] untuk dijalankan.

Karena Plazma didasarkan pada platform server resmi Mojang Studios[^2], untuk menggunakan Plazma juga diperlukan instalasi JRE.

### 1.1 Memeriksa Ketersediaan JRE

Untuk memeriksa apakah JRE telah terinstal di sistem, masukkan [`cmd /k java --version`](#user-content-fn-4)[^4] di jendela jalankan dan jalankan perintah tersebut.

Jika outputnya sama seperti di atas, lanjutkan ke [Langkah 2](setup.md#id-2).

{% code title="Output yang Benar" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Jika output tidak sama seperti di atas atau jika outputnya menunjukkan bahwa JRE tidak ada atau terlalu lama, maka Anda perlu melakukan [Langkah 1.2](setup.md#id-1.2).

{% code title="JRE Tidak Terinstal" lineNumbers="true" %}

```log
'java' bukanlah perintah internal atau eksternal, program yang dapat dijalankan, atau
file batch.
```

{% endcode %}

{% code title="JRE Terlalu Lama" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Instalasi JRE

Dalam panduan ini, kami akan menggunakan Azul Zulu sebagai [salah satu jenis](#user-content-fn-5)[^5] dari JRE.

Setelah instalasi selesai, lakukan kembali langkah [1.1](setup.md#id-1.1) untuk memastikan instalasi telah selesai dengan benar.

{% tabs %}

{% tab title="Windows" %}

1. Pertama, unduh **JDK 21** dari [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) dalam format `.msi`.
2. Jalankan wizard instalasi yang telah diunduh dan klik `Next`.
3. **Aktifkan `Set JAVA_HOME variable` di menu sebelah kiri tengah jendela** dan klik `Next`.
4. Klik `Install` untuk menyelesaikan instalasi JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) memasang **JDK 21** dari Wizard Instalasi dalam format `.dmg` setelah diunduh, lalu menjalankan untuk menginstal JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Pertama, jalankan perintah berikut di terminal untuk menambahkan repositori Azul Zulu ke APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Selanjutnya, instal JRE dengan menjalankan perintah berikut di terminal.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Anda dapat menginstal JRE dengan menjalankan perintah berikut.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Unduh Plazma

Plazma menyediakan berbagai jenis file eksekusi.

{% hint style="warning" %}

**Sebagian besar kasus menggunakan `Reobf Paperclip`.**

Informasi di bawah ini ditujukan untuk pengembang atau mereka yang ingin mengetahui lebih lanjut tentang masing-masing jenis.\
Jika Anda pengguna umum, tidak masalah untuk melompat ke [langkah 3](setup.md#id-3).

{% endhint %}

<details>

<summary>Pelajari lebih lanjut</summary>

Nama file eksekusi adalah `plazma-(manajer versi)-1.20.4-R0.1-SNAPSHOT-(jenis pemetaan).jar`.

- **Jenis Pemetaan**\
  Pemetaan adalah peta yang menghubungkan kode sebenarnya Minecraft dengan kode yang telah diacak.
  - **Reobf**\
    Reobfuscated (재난독화), juga dikenal sebagai pemetaan Spigot, digunakan dalam sebagian besar plugin NMS.\
    Akan dihentikan penggunaannya mulai dari versi 1.20.5.
  - **Mojmap**\
    Pemetaan Mojang, adalah pemetaan Minecraft vanilla.
- **Manajer Versi**\
  Manajer versi adalah perangkat peluncur yang diperlukan untuk menjalankan server dan menerapkan patch pada file server.
  - **Paperclip**\
    Dikembangkan oleh tim PaperMC untuk Paper dan platform turunannya, berperan dalam mengunduh pustaka dan menerapkan patch pada server.
  - **Bundler**\
    Manajer versi Minecraft Vanilla.

</details>

***

## 3. Buat Skrip Mulai

Untuk memulai Plazma dengan mudah dan merestart server secara otomatis, Anda perlu membuat [skrip mulai](#user-content-fn-6)[^6].

Anda dapat membuat skrip awal melalui [Flags.sh](https://flags.sh) untuk [membuat](#user-content-fn-7)[^7].\
Hanya dengan memasukkan jumlah memori yang ingin Anda gunakan di Plazma, perintah akan dioptimalkan secara otomatis.

Anda dapat mengunduh skrip mulai melalui tombol unduh di pojok kiri bawah.\
**Pastikan skrip mulai yang diunduh sesuai dengan sistem operasi Anda.**

***

## 4. Penyusunan File

Pindahkan skrip mulai yang telah diunduh dan Plazma ke folder baru sekarang.

{% hint style="warning" %}

**Nama folder harus tanpa spasi dan dalam bahasa Inggris.**

Jika tidak, Plazma atau JRE mungkin tidak berfungsi dengan benar.

{% endhint %}

Jalankan skrip mulai sekarang. Untuk Windows, <mark style="background-color:orange;">Pilih **Allow** di jendela pemilihan izin firewall</mark>.

***

## 5. Persetujuan EULA

Setelah menjalankan skrip mulai sekali, file `eula.txt` akan dibuat di folder tersebut.

EULA[^9] adalah perjanjian lisensi yang harus disetujui dengan menggunakan layanan [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

Jika Anda tidak menyetujui, Anda tidak dapat memulai server dan dapat dikenakan [sanksi](#user-content-fn-11)[^11], seperti suspensi akun karena melanggar EULA.

{% endhint %}

Untuk menyetujui EULA, ubah `eula=false` menjadi `eula=true` dalam file `eula.txt` dan simpan perubahan.

***

## 6. Izin Akses Eksternal (Windows)

Sistem operasi modern secara default memblokir akses eksternal untuk melindungi dari akses berbahaya dari luar dengan menggunakan **firewall** dan **router**.

Untuk Windows, karena sudah mengizinkan pada [langkah 3](setup.md#id-3), Anda hanya perlu melakukan port forwarding.

{% hint style="info" %}

**Panduan ini diasumsikan untuk sistem operasi Windows dan router yang mendukung [UPnP](#user-content-fn-12)[^12].**

Jika router tidak mendukung UPnP, Anda perlu mencari informasi spesifik berdasarkan router masing-masing.

Atau Anda dapat menggunakan [Ngrok](https://ngrok.com/) untuk membuat alamat sementara.
{% endhint %}

{% hint style="warning" %}

**Untuk sistem operasi UNIX (semi) seperti Linux atau macOS, pengaturan firewall berbeda untuk setiap layanan, jadi Anda harus mencari informasi sendiri.**

{% endhint %}

### 6.1 Memeriksa Kebutuhan Port Forwarding

Masukkan dan jalankan perintah berikut di jendela eksekusi.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jika output adalah `True`, Anda tidak perlu melakukan apa pun, tetapi jika `False`, Anda perlu mengatur port forwarding.

### 6.2 Mengakses Server

{% tabs %}

{% tab title="Akses dari Luar" %}

Jika tidak perlu port forwarding, atau jika Anda sudah berhasil melakukan port forwarding, Anda sekarang dapat terhubung ke server.

Alamat yang digunakan untuk mengakses server dapat ditemukan [di sini](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Kemudian, restart server, Plazma akan mencoba port forwarding secara otomatis.

Keberhasilan UPnP akan tergantung pada pesan yang muncul di konsol, yang akan ditampilkan sebagai `[UPnP] (pesan)`.

| Pesan                          | Arti                                                     |
| ------------------------------ | -------------------------------------------------------- |
| `Berhasil membuka port (port)` | Port forwarding berhasil.                |
| `Port (port) sudah terbuka`    | Port sedang digunakan oleh layanan lain. |
| `Gagal membuka port (port)`    | Port forwarding gagal.                   |
| `Layanan tidak tersedia`       | Router tidak mendukung UPnP.             |

Ketika server dimatikan, Plazma akan menutup port secara otomatis.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Unduh file ZIP `Windows (64-bit)` dari [situs Ngrok](https://ngrok.com/download).
2. Letakkan file Ngrok yang diunduh ke dalam folder server.
3. Buat [token otentikasi](#user-content-fn-13) dari [Dashboard Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Jalankan perintah yang ditampilkan di `Command Line` dari folder server.
5. Tambahkan `start /b ngrok tcp --region jp 25565` di bagian atas skrip eksekusi dan `taskkill /f /t /im ngrok.exe` di bagian bawahnya.
6. Pada pesan `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` di bagian atas konsol, `0.tcp.jp.ngrok.io:12345` adalah alamat server.
7. Sekarang Anda dapat mengakses melalui alamat tersebut dari luar.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Misalnya, setelah menjalankan perintah,

```log
Windows Konfigurasi IP

Ethernet Adapter Ethernet:

    Suffix DNS terhubung. . . . :
    Alamat IPv4. . . . . . . . . : 192.168.3.7
    Subnet Mask . . . . . . . : 255.255.255.0
    Gateway Default . . . . . . : 192.168.3.1

```

Jika Anda mencoba terhubung ke server dari lokal, coba hubungkan ke `192.168.3.7` yang ditunjukkan sebagai Alamat IPv4.

Jika server dan game dijalankan pada PC yang sama, Anda dapat terhubung melalui `localhost`.

{% endtab %}
{% endtabs %}

## 7. Growing

Setelah berhasil memulai server dan server berfungsi dengan baik, saatnya untuk menyesuaikan server.

Pelajari cara menyesuaikan server melalui panduan di bawah ini.

{% content-ref url="langkah-selanjutnya.md" %}
[langkah-selanjutnya.md](langkah-selanjutnya.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Lingkungan Eksekusi Java.

[^2]: Berdasarkan Paper yang merupakan dasar dari Plazma, yang juga didasarkan pada Spigot, yang merupakan platform server resmi.

[^3]: Tombol Windows + R

[^4]: Untuk Linux, di terminal ketik `java --version`

[^5]: JRE adalah salah satu proyek sumber terbuka, seperti platform server Minecraft yang memiliki berbagai jenis.

[^6]: Biasanya dikenal sebagai **launcher**.

[^7]: Aktifkan "Auto-restart" untuk menjadwalkan restart otomatis server. Anda dapat menutup dengan menekan `Control + C`.

[^8]: Tidak disarankan melebihi setengah dari kapasitas sistem.

    Misalnya, ketika kapasitas memori sistem secara keseluruhan adalah 8GB, disarankan untuk tidak mengatur lebih dari 4GB.

[^9]: Perjanjian Lisensi Pengguna Akhir, Perjanjian Lisensi Pengguna Akhir. Silakan lihat [Situs web Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines) untuk informasi lebih lanjut.

[^10]: Perusahaan Microsoft.

[^11]: Dalam hal Korea Selatan, berdasarkan Pasal 32 Ayat 1 Nomor 9 dari Undang-Undang Promosi Industri Permainan, **Korea Microsoft Corporation** dapat mengajukan tuntutan hukum.

[^12]: Universal Plug & Play. Purpur yang terdapat dalam Plazma berkomunikasi secara otomatis dengan router melalui teknologi ini, sehingga tidak perlu melakukan port forwarding secara langsung ketika server sedang berjalan.

[^13]: Jika tidak memiliki akun, daftarlah ke Ngrok melalui akun Google atau GitHub.
