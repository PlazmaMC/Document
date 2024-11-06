---
description: Ketahui cara membuat server dengan Plazma.
---

# 👟 Mula

Untuk menggunakan Plazma secara stabil, sistem perlu memenuhi keperluan berikut:

|                  | Minimum | Disyorkan |
| :--------------: | ------- | --------- |
|     Seni bina    | x64     | -         |
|        RAM       | 8GB     | 16GB      |
| Ruangan simpanan | 1GB     | 8GB       |
|        JDK       | 17      | 21        |

Untuk mengedit fail konfigurasi dengan lancar, disarankan untuk memasang editor seperti [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Output yang betul" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' bukanlah program perintah internal atau eksternal, program yang dapat dijalankan, atau
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

1. Pertama, muat turun **JDK 21** dari [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) dalam format `.msi`.
2. Jalankan penyelenggaraan muat turun dan klik `Next`.
3. Di tengah kiri tetingkap, aktifkan `Set JAVA_HOME variable` dan kemudian klik `Next`.
4. Tekan `Install` untuk menyelesaikan pemasangan JRE.
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

Kemudian, jalankan arahan berikut dalam terminal untuk memasang JRE.

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

## 2. Muat Turun Plazma

Plazma menyediakan pelbagai jenis fail eksekusi.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Ketahui lebih lanjut</summary>

Nama fail eksekusi adalah `plazma-(pengurus versi)-1.20.4-R0.1-SNAPSHOT-(jenis pemetaan).jar` yang telah ditetapkan.

- **Jenis Pemetaan**\
  Pemetaan adalah jenis peta yang menghubungkan kod sebenar Minecraft dengan kod yang telah digarap.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Anda boleh muat turun skrip mula melalui butang muat turun di bahagian kiri bawah.\
**Pastikan skrip mula yang dimuat turun sepadan dengan sistem operasi anda.**

***

## 4. Penyusunan Fail

Pindahkan skrip mula yang dimuat turun dan Plazma ke folder baru sekarang.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Kini jalankan skrip mula. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Persetujuan EULA

Apabila anda menjalankan skrip mula, fail `eula.txt` akan dicipta dalam folder.

EULA[^9] adalah perjanjian lesen yang perlu anda setujui untuk menggunakan perkhidmatan [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Untuk bersetuju dengan EULA, ubah `eula=false` kepada `eula=true` dalam fail `eula.txt` dan simpan.

***

## 6. Membenarkan Sambungan Luar (Windows)

Sistem operasi moden secara asasnya menghalang akses luaran melalui **firewall** dan **router** untuk melindungi daripada akses berbahaya.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Jika router anda tidak menyokong UPnP, anda perlu mencari maklumat mengikut panel router yang berbeza.

Atau anda boleh menggunakan [Ngrok](https://ngrok.com/) untuk mencipta alamat sementara.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Semak Keperluan Penerusan Port

Masukkan dan jalankan seperti yang berikut dalam tetingkap eksekusi.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jika output adalah `True`, anda boleh berhenti di sini, tetapi jika `False`, anda perlu tetapkan penerusan port.

### 6.2 Menyambung ke Pelayan

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Alamat yang digunakan untuk menyambung ke pelayan boleh disemak [di sini](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Kemudian, mulakan semula pelayan dan Plazma akan cuba meneruskan port secara automatik.

Kejayaan UPnP bergantung kepada mesej yang dipaparkan dalam konsol, di mana ia akan menunjukkan `[UPnP] (mesej)`.

| Mesej                         | Makna                                                        |
| ----------------------------- | ------------------------------------------------------------ |
| `Berjaya membuka port (port)` | Penerusan port berjaya.                      |
| `Port (port) sudah terbuka`   | Port telah digunakan oleh perkhidmatan lain. |
| `Gagal membuka port (port)`   | Penerusan port gagal.                        |
| `Perkhidmatan tidak tersedia` | Router tidak menyokong UPnP.                 |

Apabila pelayan ditutup, Plazma akan menutup port secara automatik.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Muat turun fail ZIP `Windows (64-bit)` dari [Laman Web Ngrok](https://ngrok.com/download).
2. Letakkan fail Ngrok yang dimuat turun ke dalam folder pelayan.
3. Di [Papan Pemuka Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), cipta [token pengesahan](#user-content-fn-13)[^13].
4. Di dalam folder pelayan, jalankan arahan yang dipaparkan dalam `Command Line`.
5. Tambahkan `start /b ngrok tcp --region jp 25565` di bahagian atas skrip eksekusi, dan `taskkill /f /t /im ngrok.exe` di bahagian bawahnya.
6. Dari mesej yang dipaparkan di bahagian atas konsol `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`, `0.tcp.jp.ngrok.io:12345` adalah alamat pelayan.
7. Sekarang anda boleh mengakses alamat tersebut dari luar.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

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

## 7. Maju

Setelah berjaya memulakan pelayan dan pelayan berfungsi dengan betul, kini tiba masanya untuk menyesuaikan pelayan.

Terokai cara untuk menyesuaikan penggunaan pelayan melalui dokumen di bawah.

{% content-ref url="langkah-seterusnya.md" %}
[langkah-seterusnya.md](langkah-seterusnya.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
