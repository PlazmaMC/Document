---
description: Tìm hiểu cách tạo máy chủ bằng Plazma.
---

# 👟 Bắt đầu

Để sử dụng Plazma một cách ổn định, hệ thống cần đáp ứng các yêu cầu sau.

|                    | Tối thiểu | Đề nghị |
| :----------------: | --------: | ------: |
|      Kiến trúc     |       x64 |       - |
|         RAM        |       8GB |    16GB |
| Dung lượng lưu trữ |       1GB |     8GB |
|         JRE        |        17 |      21 |

Để dễ dàng chỉnh sửa tệp cấu hình, cài đặt trình soạn thảo như [Visual Studio Code](https://code.visualstudio.com/download) cũng là một ý tưởng tốt.

***

## 1. Cài đặt JRE

Như tên gọi, Minecraft: **"Java"** Edition được phát triển bằng Java, vì vậy để chạy, cần cài đặt JRE[^1].

Plazma là nền tảng máy chủ chính thức của Mojang Studios [dựa trên](#user-content-fn-2)[^2], vì vậy để sử dụng Plazma cũng cần cài đặt JRE.

### 1.1 Kiểm tra sự tồn tại của JRE

Để kiểm tra xem JRE đã được cài đặt trên hệ thống hay chưa, hãy nhập [`cmd /k java --version`](#user-content-fn-4)[^4] vào cửa sổ chạy và chạy nó.

Nếu xuất hiện như sau, bỏ qua [Bước 2](setup.md#id-2).

{% code title="Đầu ra chính xác" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Nếu không xuất hiện như trên hoặc xuất hiện như sau, có nghĩa là không có JRE hoặc quá cũ, vì vậy cần thực hiện [Bước 1.2](setup.md#id-1.2).

{% code title="JRE chưa được cài đặt" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE quá cũ" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Cài đặt JRE

Trong hướng dẫn này, chúng ta sẽ sử dụng Azul Zulu là [một trong những loại](#user-content-fn-5)[^5] của JRE.

Sau khi cài đặt xong, hãy thực hiện lại [Bước 1.1](setup.md#id-1.1) để kiểm tra xem quá trình cài đặt đã hoàn tất đúng cách hay chưa.

{% tabs %}

{% tab title="Windows" %}

1. Trước tiên, tải JDK 21 từ [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) dưới dạng `.msi`.
2. Chạy trình cài đặt đã tải xuống và nhấn `Next`.
3. **Kích hoạt `Set JAVA_HOME variable` trong menu hiển thị ở giữa bên trái của cửa sổ,** sau đó nhấn `Next`.
4. Nhấn `Install` để hoàn tất quá trình cài đặt JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) từ **JDK 21** bằng cách tải xuống và chạy trình cài đặt dạng `.dmg` sau đó cài đặt JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Bắt đầu bằng cách chạy lệnh sau trong terminal để thêm kho lưu trữ Azul Zulu vào APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Sau đó, chạy lệnh sau trong Terminal để cài đặt JRE.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Bạn có thể cài đặt JRE bằng cách nhập lệnh sau.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Tải xuống Plazma

Plazma cung cấp nhiều loại tệp thực thi khác nhau.

{% hint style="warning" %}

**Thường thì sử dụng `Reobf Paperclip`.**

Nội dung dưới đây dành cho những người muốn tìm hiểu về các nhà phát triển hoặc đặc điểm của từng loại.\
Nếu bạn là người dùng thông thường, có thể bỏ qua [Bước 3](setup.md#id-3) mà không gặp vấn đề.

{% endhint %}

<details>

<summary>Tìm hiểu thêm</summary>

Tên tệp thực thi được xác định là `plazma-(quản lý phiên bản)-1.20.4-R0.1-SNAPSHOT-(kiểu ánh xạ).jar`.

- **Kiểu ánh xạ**\
  Ánh xạ là một loại bản đồ kết nối giữa mã nguồn thực và mã nguồn đã bị làm rối.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.5부터 사용이 종료될 예정입니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다.
- **Quản lý phiên bản**\
  Quản lý phiên bản là một loại trình khởi chạy máy chủ cung cấp thư viện cần thiết cho việc chạy máy chủ và áp dụng bản vá cho máy chủ.
  - **Paperclip**\
    Là một trình quản lý phát triển bởi nhóm PaperMC để tải về thư viện và áp dụng bản vá cho Paper và các nền tảng phát sinh khác.
  - **Bundler**\
    Là trình quản lý phiên bản Minecraft vanilla.

</details>

***

## 3. Tạo kịch bản khởi động

Để bắt đầu Plazma một cách dễ dàng và tự động khởi động lại máy chủ, bạn cần tạo [kịch bản khởi động](#user-content-fn-6)[^6].

Bạn có thể tạo kịch bản khởi động thông qua [Flags.sh](https://flags.sh).\
Chỉ cần nhập [số lượng bộ nhớ sẽ sử dụng cho Plazma](#user-content-fn-8)[^8], lệnh sẽ tự động tối ưu hóa.

Bạn có thể tải kịch bản khởi động thông qua nút tải xuống ở góc dưới bên trái.\
**Hãy chắc chắn rằng tệp kịch bản khởi động đã được tải xuống đúng phiên bản của hệ điều hành của bạn.**

***

## 4. Dọn dẹp tệp tin

Di chuyển kịch bản khởi động và Plazma đã tải xuống vào một thư mục mới.

{% hint style="warning" %}

**Tên thư mục phải không có khoảng trắng và phải được thiết lập bằng tiếng Anh.**

Nếu không, Plazma hoặc JRE có thể không hoạt động đúng cách.

{% endhint %}

Chạy kịch bản khởi động bây giờ. Đối với Windows, <mark style="background-color:orange;">Trong hộp thoại chọn cho phép tường lửa, hãy chắc chắn chọn **Cho phép**</mark>.

***

## 5. Đồng ý với EULA

Sau khi chạy kịch bản khởi động một lần, tệp `eula.txt` sẽ được tạo ra trong thư mục.

EULA[^9] là hợp đồng cấp phép mà bạn phải đồng ý khi sử dụng dịch vụ của [Mojang Studios](#user-content-fn-10)[^10].

Nếu không đồng ý với EULA, bạn sẽ không thể khởi động máy chủ và có thể bị xử phạt nếu vi phạm EULA, chẳng hạn như bị đình chỉ tài khoản.

Để đồng ý với EULA, chỉnh sửa `eula=false` trong tệp `eula.txt` thành `eula=true` và lưu lại.

***

## 6. Cho phép kết nối từ bên ngoài (Windows)

Hệ điều hành hiện đại mặc định chặn kết nối từ bên ngoài để ngăn chặn truy cập nguy hiểm thông qua **tường lửa** và **bộ định tuyến**.

Trong trường hợp của Windows, sau khi đã cho phép ở [Bước 3](setup.md#id-3), chỉ cần cấu hình chuyển tiếp cổng.

{% hint style="info" %}

**Hướng dẫn này giả định rằng bạn đang sử dụng hệ điều hành Windows và [UPnP](#user-content-fn-12)[^12] trên router có sẵn.**

Nếu bộ định tuyến không hỗ trợ UPnP, từng bộ định tuyến có cấu hình khác nhau, vì vậy bạn cần tìm kiếm thông tin trực tiếp.

Hoặc bạn có thể sử dụng [Ngrok](https://ngrok.com/) để tạo địa chỉ tạm thời.
{% endhint %}

{% hint style="warning" %}

**Trong trường hợp hệ điều hành (gần) UNIX như Linux hoặc macOS, cách thiết lập tường lửa sẽ khác nhau cho từng dịch vụ, bạn cần tìm kiếm thông tin trực tiếp.**

{% endhint %}

### 6.1 Kiểm tra cần thiết về chuyển tiếp cổng

Nhập và chạy như sau trong cửa sổ chạy.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Nếu kết quả là `True`, bạn có thể dừng ở đây, nhưng nếu là `False`, bạn cần cấu hình chuyển tiếp cổng.

### 6.2 Kết nối đến máy chủ

{% tabs %}

{% tab title="Truy cập từ bên ngoài" %}

Nếu không cần chuyển tiếp cổng hoặc đã thành công trong việc chuyển tiếp cổng, bạn có thể truy cập vào máy chủ ngay bây giờ.

Địa chỉ được sử dụng để kết nối đến máy chủ có thể được xác nhận [tại đây](https://ip.pe.kr/).

{% endtab %}

{% tab title="Thử Port Forwarding qua UPnP" %}

Trong `purpur.yml` của thư mục máy chủ, kích hoạt `network.upnp-port-forwarding` thành `true`.

Sau đó, khởi động lại máy chủ, Plazma sẽ tự động thử chuyển tiếp cổng.

Dưới đây là kết quả thành công của UPnP dựa trên thông báo xuất hiện trên cửa sổ console, trên console sẽ hiển thị `[UPnP] (thông báo)`.

| Thông báo                         | Ý nghĩa                                  |
| --------------------------------- | ---------------------------------------- |
| `Successfully opened port (cổng)` | Chuyển tiếp cổng thành công.             |
| `Port (cổng) is already open`     | Cổng đang được sử dụng bởi dịch vụ khác. |
| `Failed to open port (cổng)`      | Chuyển tiếp cổng thất bại.               |
| `Service is unavailable`          | Bộ định tuyến không hỗ trợ UPnP.         |

Khi máy chủ tắt, Plazma sẽ tự động đóng cổng.

{% endtab %}

{% tab title="Tạo địa chỉ tạm thời bằng Ngrok" %}

Phương pháp sử dụng Ngrok hữu ích cho các bài kiểm tra ngắn hạn, tham gia hoặc chơi cùng bạn bè.

1. Tải xuống tệp ZIP `Windows (64-bit)` từ [trang chủ Ngrok](https://ngrok.com/download).
2. Đặt tệp Ngrok đã tải xuống vào thư mục máy chủ.
3. Tạo [token xác thực](#user-content-fn-13) từ [bảng điều khiển Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) trong thư mục máy chủ.
4. Chạy lệnh được hiển thị trong `Command Line` trong thư mục máy chủ.
5. Thêm `start /b ngrok tcp --region jp 25565` vào đầu tập lệnh chạy và `taskkill /f /t /im ngrok.exe` vào cuối tập lệnh chạy.
6. Từ thông báo `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` ở đầu console, `0.tcp.jp.ngrok.io:12345` sẽ là địa chỉ của máy chủ.
7. Bây giờ bạn có thể kết nối từ bên ngoài thông qua địa chỉ đó.

{% endtab %}

{% tab title="Kết nối từ máy cục bộ" %}

Nếu bạn muốn kết nối đến máy chủ từ máy cục bộ, bạn có thể sử dụng `cmd /k ipconfig` trong cửa sổ thực thi để kết nối với `Địa chỉ IPv4` được hiển thị.

Ví dụ, sau khi thực thi lệnh,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Khi thử kết nối đến máy chủ, sử dụng địa chỉ IPv4 được hiển thị là `192.168.3.7`.

Nếu máy chủ và trò chơi chạy trên cùng một PC, bạn có thể kết nối bằng `localhost`.

{% endtab %}
{% endtabs %}

## 7. Bước Phát triển

Sau khi máy chủ khởi động thành công và hoạt động đúng cách, bây giờ là lúc cá nhân hóa máy chủ.

Tìm hiểu cách cá nhân hóa máy chủ thông qua hướng dẫn dưới đây.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Môi trường thực thi Java.

[^2]: Paper, nền tảng của Plazma, dựa trên Spigot và Spigot dựa trên nền tảng máy chủ chính thức.

[^3]: Phím Windows + R

[^4]: Trong Linux, chạy `java --version` trong terminal

[^5]: JRE là một trong những dự án mã nguồn mở, tương tự như nền tảng máy chủ Minecraft với nhiều loại khác nhau.

[^6]: Thường được biết đến là **trình chạy**.

[^7]: Kích hoạt "Tự động khởi động lại" sẽ tự động khởi động lại máy chủ. Nhấn `Control + C` để dừng.

[^8]: Không khuyến khích vượt quá nửa dung lượng hệ thống.

    Ví dụ, nếu dung lượng bộ nhớ hệ thống là 8GB, không nên thiết lập trên 4GB.

[^9]: End-User License Agreement, Thỏa thuận Sử dụng cuối cùng. Vui lòng kiểm tra chi tiết tại [trang chủ Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Tập đoàn Microsoft.

[^11]: Theo Điều 32, Khoản 1, Mục 9 của Luật Phát triển Ngành công nghiệp Game của Hàn Quốc, **Công ty TNHH Microsoft Hàn Quốc** có thể bị truy tố hợp pháp.

[^12]: Universal Plug & Play. Purpur đi kèm trong Plazma sử dụng công nghệ này để tự động giao tiếp với bộ định tuyến và mở cổng chỉ khi máy chủ đang chạy, không cần phải chuyển tiếp cổng trực tiếp.

[^13]: Nếu không có tài khoản, đăng ký Ngrok thông qua tài khoản Google hoặc GitHub.
