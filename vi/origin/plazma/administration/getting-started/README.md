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

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Nếu không xuất hiện như trên hoặc xuất hiện như sau, có nghĩa là không có JRE hoặc quá cũ, vì vậy cần thực hiện [Bước 1.2](setup.md#id-1.2).

{% code title="JRE가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE가 너무 오래됨" lineNumbers="true" %}

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

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

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

다음 명령어를 입력하여 JRE를 설치할 수 있습니다.

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

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Nội dung dưới đây dành cho những người muốn tìm hiểu về các nhà phát triển hoặc đặc điểm của từng loại.\
Nếu bạn là người dùng thông thường, có thể bỏ qua [Bước 3](setup.md#id-3) mà không gặp vấn đề.

{% endhint %}

<details>

<summary>Tìm hiểu thêm</summary>

Tên tệp thực thi được xác định là `plazma-(quản lý phiên bản)-1.20.4-R0.1-SNAPSHOT-(kiểu ánh xạ).jar`.

- **Kiểu ánh xạ**\
  Ánh xạ là một loại bản đồ kết nối giữa mã nguồn thực và mã nguồn đã bị làm rối.
  - **Reobf**\
    Reobfuscation, còn được gọi là Spigot mapping và được sử dụng trong hầu hết các plugin NMS.\
    Sẽ ngừng sử dụng từ phiên bản 1.20.5 trở đi.
  - **Mojmap**\
    Mojang mapping, là ánh xạ Minecraft vanilla.
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

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Nếu không, Plazma hoặc JRE có thể không hoạt động đúng cách.

{% endhint %}

Chạy kịch bản khởi động bây giờ. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

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

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Nếu bộ định tuyến không hỗ trợ UPnP, từng bộ định tuyến có cấu hình khác nhau, vì vậy bạn cần tìm kiếm thông tin trực tiếp.

Hoặc bạn có thể sử dụng [Ngrok](https://ngrok.com/) để tạo địa chỉ tạm thời.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Kiểm tra cần thiết về chuyển tiếp cổng

Nhập và chạy như sau trong cửa sổ chạy.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Nếu kết quả là `True`, bạn có thể dừng ở đây, nhưng nếu là `False`, bạn cần cấu hình chuyển tiếp cổng.

### 6.2 Kết nối đến máy chủ

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Địa chỉ được sử dụng để kết nối đến máy chủ có thể được xác nhận [tại đây](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

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

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Tải xuống tệp ZIP `Windows (64-bit)` từ [trang chủ Ngrok](https://ngrok.com/download).
2. Đặt tệp Ngrok đã tải xuống vào thư mục máy chủ.
3. Tạo [token xác thực](#user-content-fn-13) từ [bảng điều khiển Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) trong thư mục máy chủ.
4. Chạy lệnh được hiển thị trong `Command Line` trong thư mục máy chủ.
5. Thêm `start /b ngrok tcp --region jp 25565` vào đầu tập lệnh chạy và `taskkill /f /t /im ngrok.exe` vào cuối tập lệnh chạy.
6. Từ thông báo `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` ở đầu console, `0.tcp.jp.ngrok.io:12345` sẽ là địa chỉ của máy chủ.
7. Bây giờ bạn có thể kết nối từ bên ngoài thông qua địa chỉ đó.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

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

{% content-ref url="customization.md" %}
[customization.md](customization.md)
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
