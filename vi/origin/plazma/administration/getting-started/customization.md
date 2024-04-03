---
description: Tìm hiểu cách tùy chỉnh máy chủ.
---

# 🎨 Tùy chỉnh người dùng

Lý do sử dụng nền tảng máy chủ được sửa đổi như Plazma thay vì sử dụng nền tảng chính thức do Mojang Studios cung cấp là khả năng **tùy chỉnh** mạnh mẽ nhất.

Dưới đây là một số cách để tùy chỉnh và sử dụng Plazma.

## Sửa đổi cấu hình <a href="#id-1" id="id-1"></a>

Cách đơn giản nhất để tùy chỉnh Plazma là chỉnh sửa cấu hình.

Plazma cung cấp cấu hình mạnh mẽ từ cơ chế trò chơi đến thuộc tính của quái vật.

Vui lòng xem chi tiết về cấu hình của Plazma tại trang dưới đây.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## Sử dụng plugin <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma hỗ trợ tất cả các plugin dựa trên Paper một cách bình thường.**

Với các plugin Spigot, có thể có một số plugin không hoạt động do sự thay đổi về ánh xạ của Paper từ phiên bản 1.20.5 trở đi,
nhưng hầu hết các plugin dựa trên Paper như Paper, Pufferfish và Purpur đều hoạt động trên Plazma
và nếu không hoạt động đúng cách, đó là lỗi của Plazma nên bạn vui lòng [báo cáo ngay.](../diagnosis/plugins.md)

{% endhint %}

Đây là lý do chính khiến bạn nên sử dụng Plazma và cũng là cách mạnh mẽ nhất để cá nhân hóa Plazma.
Hệ sinh thái plugin mạnh mẽ của Plazma giúp bạn dễ dàng cá nhân hóa máy chủ.

Có nhiều cách để tìm kiếm và tải plugin. Một số plugin
được tải lên dịch vụ kho lưu trữ công cộng, trong khi một số plugin khác được tải lên GitHub hoặc trang web
của họ.

{% hint style="caution" %}

**Plugin có thể truy cập trực tiếp vào hệ thống của bạn!**

Luôn kiểm tra plugin bằng dịch vụ như VirusTotal trước khi áp dụng,
hoặc tải plugin từ dịch vụ đáng tin cậy.

{% endhint %}

Có nhiều dịch vụ để tải plugin. Trong số đó, các dịch vụ như [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) sẽ kiểm duyệt plugin trước khi được tải lên,
và chỉ phân phối các plugin an toàn.

### Áp dụng Plugin <a href="#id-2.1" id="id-2.1"></a>

Sau khi tải plugin, bạn có thể áp dụng chúng.

1. Plugin có dạng `.jar` hoặc `Java Executable File`.\
   Một số plugin được nén thành tập tin nén, trong trường hợp đó
   bạn cần giải nén và sử dụng tập tin chứa `bukkit`, `spigot` hoặc `paper`,
   nếu có tập tin `fat` đi kèm, sử dụng tập tin `fat`.
2. Đặt tập tin đã tải vào thư mục `plugins` của máy chủ và khởi động (lại) máy chủ.
3. Khi Plazma khởi động, thông tin mới sẽ được hiển thị trên bảng điều khiển.
   Điều này có nghĩa là Plazma đã tải plugin một cách bình thường.
4. Dù Plazma đã tải plugin một cách bình thường, có thể plugin chưa khởi động được.
   Sử dụng lệnh `/plugins` để xem danh sách plugin đang hoạt động trên máy chủ.
   Nếu tên plugin cài đặt không được hiển thị màu <mark style="background-color:red;">đỏ</mark>
   màu <mark style="background-color:green;">xanh lá cây</mark> thì plugin đã được tải đúng cách.

Nếu plugin không được tải đúng cách, bạn có thể tìm thấy cách khắc phục trên trang dưới đây.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Sử dụng Data Pack <a href="#id-3" id="id-3"></a>

Data Pack là cách cá nhân hóa Minecraft mà trò chơi cung cấp sẵn, tương tự như
[Resource Pack](#user-content-fn-1)[^1].

Với Data Pack, bạn có thể thêm nhóm sinh vật mới và thách thức mới vào trò chơi
và chỉnh sửa một số phần của trò chơi.

{% hint style="caution" %}

**Data Pack có thể làm hỏng thế giới của bạn!**

Một số Data Pack bị hỏng có thể làm hỏng thế giới của bạn và điều này không thể khôi phục được.

Do đó, việc sao lưu thế giới trước khi áp dụng Data Pack được khuyến khích.

{% endhint %}

Data Pack cũng có thể tải từ nhiều dịch vụ như [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) và nhiều dịch vụ khác.

Sau khi tải Data Pack, bạn có thể đặt chúng vào thư mục `datapacks` trong thế giới của máy chủ để áp dụng.
Nếu không có thư mục, bạn có thể tạo một thư mục và thêm vào đó.

{% hint style="warning" %}

**Một số Data Pack có thể không áp dụng đúng lần đầu.**

Trong trường hợp này, khuyến nghị khởi động máy chủ **2 lần**.

{% endhint %}

Data Pack có thể dễ bị hỏng mỗi khi Minecraft được cập nhật.

Đặc biệt, nếu Data Pack bị hỏng hoàn toàn, máy chủ có thể bị sự cố,
cho nên việc thử nghiệm kỹ lưỡng trước khi cập nhật máy chủ là rất quan trọng.

{% hint style="info" %}

**Sau lệnh khởi động máy chủ, nhập `safeMode` để tắt tất cả Data Pack và khởi động máy chủ.**

[Xem thêm tại `Reference > Arguments` để biết thông tin chi tiết.](../reference/arguments.md)

{% endhint %}

Data Pack đã áp dụng có thể được kiểm tra thông qua lệnh `/datapack list`.

***

[^1]: Hoặc Add-on cho Minecraft: Bedrock Edition.

[^2]: Bao gồm việc thêm nhóm sinh vật vào trò chơi.
