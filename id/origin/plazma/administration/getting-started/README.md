---
description: Pelajari cara membuat server dengan Plazma.
---

# 👟 Mulai

Untuk menggunakan Plazma secara stabil, sistem harus memenuhi persyaratan berikut:

|                   | Minimum | Disarankan |
| :---------------: | ------- | ---------- |
|     Arsitektur    | x64     | -          |
|        RAM        | 8GB     | 16GB       |
| Ruang Penyimpanan | 1GB     | 8GB        |
|        JDK        | 17      | 21         |

Untuk pengeditan file konfigurasi yang lancar, disarankan untuk menginstal editor seperti [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Output yang Benar" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' bukanlah perintah internal atau eksternal, program yang dapat dijalankan, atau
file batch.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Pertama, unduh **JDK 21** dari [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) dalam format `.msi`.
2. Jalankan wizard instalasi yang telah diunduh dan klik `Next`.
3. **Aktifkan `Set JAVA_HOME variable` di menu sebelah kiri tengah jendela** dan klik `Next`.
4. Klik `Install` untuk menyelesaikan instalasi JRE.
   {% endtab %}

{% tab title="macOS" %}
[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

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
다음 명령어를 입력하여 JDK를 설치할 수 있습니다.

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
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Pelajari lebih lanjut</summary>

Nama file eksekusi adalah `plazma-(manajer versi)-1.20.4-R0.1-SNAPSHOT-(jenis pemetaan).jar`.

- **Jenis Pemetaan**\
  Pemetaan adalah peta yang menghubungkan kode sebenarnya Minecraft dengan kode yang telah diacak.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Pemetaan Mojang, adalah pemetaan Minecraft vanilla. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Anda dapat mengunduh skrip mulai melalui tombol unduh di pojok kiri bawah.\
**Pastikan skrip mulai yang diunduh sesuai dengan sistem operasi Anda.**

***

## 4. Penyusunan File

Pindahkan skrip mulai yang telah diunduh dan Plazma ke folder baru sekarang.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Jalankan skrip mulai sekarang. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Persetujuan EULA

Setelah menjalankan skrip mulai sekali, file `eula.txt` akan dibuat di folder tersebut.

EULA[^9] adalah perjanjian lisensi yang harus disetujui dengan menggunakan layanan [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Untuk menyetujui EULA, ubah `eula=false` menjadi `eula=true` dalam file `eula.txt` dan simpan perubahan.

***

## 6. Izin Akses Eksternal (Windows)

Sistem operasi modern secara default memblokir akses eksternal untuk melindungi dari akses berbahaya dari luar dengan menggunakan **firewall** dan **router**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Jika router tidak mendukung UPnP, Anda perlu mencari informasi spesifik berdasarkan router masing-masing.

Atau Anda dapat menggunakan [Ngrok](https://ngrok.com/) untuk membuat alamat sementara.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Memeriksa Kebutuhan Port Forwarding

Masukkan dan jalankan perintah berikut di jendela eksekusi.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jika output adalah `True`, Anda tidak perlu melakukan apa pun, tetapi jika `False`, Anda perlu mengatur port forwarding.

### 6.2 Mengakses Server

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

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

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
