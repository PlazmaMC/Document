---
description: Tìm hiểu cách tạo máy chủ bằng Plazma.
---

# 👟 Bắt đầu

Để sử dụng Plazma một cách ổn định, hệ thống cần đáp ứng các yêu cầu sau.

|                    | Tối thiểu | Đề nghị |
| :----------------: | --------- | ------- |
|      Kiến trúc     | x64       | -       |
|         RAM        | 8GB       | 16GB    |
| Dung lượng lưu trữ | 1GB       | 8GB     |
|         JDK        | 17        | 21      |

Để dễ dàng chỉnh sửa tệp cấu hình, cài đặt trình soạn thảo như [Visual Studio Code](https://code.visualstudio.com/download) cũng là một ý tưởng tốt.

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Đầu ra chính xác" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
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

1. Trước tiên, tải JDK 21 từ [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) dưới dạng `.msi`.
2. Chạy trình cài đặt đã tải xuống và nhấn `Next`.
3. **Kích hoạt `Set JAVA_HOME variable` trong menu hiển thị ở giữa bên trái của cửa sổ,** sau đó nhấn `Next`.
4. Nhấn `Install` để hoàn tất quá trình cài đặt JRE.
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

Sau đó, chạy lệnh sau trong Terminal để cài đặt JRE.

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

## 2. Tải xuống Plazma

Plazma cung cấp nhiều loại tệp thực thi khác nhau.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Tìm hiểu thêm</summary>

Tên tệp thực thi được xác định là `plazma-(quản lý phiên bản)-1.20.4-R0.1-SNAPSHOT-(kiểu ánh xạ).jar`.

- **Kiểu ánh xạ**\
  Ánh xạ là một loại bản đồ kết nối giữa mã nguồn thực và mã nguồn đã bị làm rối.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Bạn có thể tải kịch bản khởi động thông qua nút tải xuống ở góc dưới bên trái.\
**Hãy chắc chắn rằng tệp kịch bản khởi động đã được tải xuống đúng phiên bản của hệ điều hành của bạn.**

***

## 4. Dọn dẹp tệp tin

Di chuyển kịch bản khởi động và Plazma đã tải xuống vào một thư mục mới.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Chạy kịch bản khởi động bây giờ. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Đồng ý với EULA

Sau khi chạy kịch bản khởi động một lần, tệp `eula.txt` sẽ được tạo ra trong thư mục.

EULA[^9] là hợp đồng cấp phép mà bạn phải đồng ý khi sử dụng dịch vụ của [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Để đồng ý với EULA, chỉnh sửa `eula=false` trong tệp `eula.txt` thành `eula=true` và lưu lại.

***

## 6. Cho phép kết nối từ bên ngoài (Windows)

Hệ điều hành hiện đại mặc định chặn kết nối từ bên ngoài để ngăn chặn truy cập nguy hiểm thông qua **tường lửa** và **bộ định tuyến**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| Thông báo                         | Ý nghĩa                                                  |
| --------------------------------- | -------------------------------------------------------- |
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

## 7. Phát triển

Sau khi máy chủ khởi động thành công và hoạt động đúng cách, bây giờ là lúc cá nhân hóa máy chủ.

Hãy tìm hiểu cách cá nhân hóa máy chủ thông qua hướng dẫn dưới đây.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
