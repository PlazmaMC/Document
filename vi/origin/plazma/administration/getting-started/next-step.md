---
description: Tìm hiểu cách tùy chỉnh máy chủ.
---

# 📶 Các bước phát triển

Lý do sử dụng nền tảng máy chủ được sửa đổi như Plazma thay vì sử dụng nền tảng chính thức do Mojang Studios cung cấp là khả năng **tùy chỉnh** mạnh mẽ nhất.

Dưới đây là một số cách để tùy chỉnh và sử dụng Plazma.

## Sửa đổi cấu hình <a href="#id-1" id="id-1"></a>

Cách đơn giản nhất để tùy chỉnh Plazma là chỉnh sửa cấu hình.

Plazma cung cấp cấu hình mạnh mẽ từ cơ chế trò chơi đến thuộc tính của quái vật.

Vui lòng xem chi tiết về cấu hình của Plazma tại trang dưới đây.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**[Một số gói dữ liệu](#user-content-fn-2)[^2] có thể không được áp dụng đúng cách khi áp dụng lần đầu.**

Trong trường hợp này, khuyến nghị khởi động máy chủ **2 lần**.

{% endhint %}

Data Pack có thể dễ bị hỏng mỗi khi Minecraft được cập nhật.

Đặc biệt, nếu Data Pack bị hỏng hoàn toàn, máy chủ có thể bị sự cố,
cho nên việc thử nghiệm kỹ lưỡng trước khi cập nhật máy chủ là rất quan trọng.

{% hint style="info" %}

**Sau lệnh khởi động máy chủ, nhập `safeMode` để tắt tất cả Data Pack và khởi động máy chủ.**

[Vui lòng tham khảo `Tài liệu tham khảo > Đối số và Thuộc tính`](../reference/arguments.md#safeMode) để biết thêm chi tiết.

{% endhint %}

Data Pack đã áp dụng có thể được kiểm tra thông qua lệnh `/datapack list`.

***

## Tối ưu hóa <a href="#id-4" id="id-4"></a>

Plazma đã áp dụng nhiều bản vá tối ưu hóa. Ngoài ra, khi Plazma khởi đầu lần đầu, tự động tối ưu hóa cấu hình nên không cần thực hiện thêm bất kỳ công việc tối ưu hóa nào nếu tuân theo hướng dẫn [Bắt đầu](./README.md).

Tuy nhiên, khi có nhiều người chơi kết nối hoặc kích thước thế giới lớn, bạn có thể thực hiện công việc tối ưu hóa bổ sung theo hướng dẫn dưới đây.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxy kết nối các máy chủ với nhau và cho phép người chơi di chuyển giữa các máy chủ hoặc giao tiếp với máy chủ khác mà không cần thêm bất kỳ công việc nào.

Vui lòng tham khảo thông tin về cấu hình proxy an toàn và chính xác tại trang dưới đây.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## An toàn <a href="#id-5" id="id-5"></a>

Với sự phát triển của các mod, Minecraft có thể dễ dàng bị tấn công bởi [engine xâm nhập](#user-content-fn-3)[^3] trên mạng.

Mặc dù hầu hết các lỗ hổng có thể thực thi trong trò chơi đã bị [chặn mặc định](#user-content-fn-4)[^4], việc tấn công lỗ hổng thông qua bộ nạp bên thứ ba vẫn không bị chặn.

Do đó, nếu máy chủ được công khai, nên cài đặt các plugin chống gian lận, cấu hình proxy và khởi động tự động, sao lưu để có thể khôi phục máy chủ nhanh chóng khi gặp sự cố.

### Thiết lập quyền <a href="#id-5.1" id="id-5.1"></a>

Một số lệnh quản trị của các plugin có thể tồn tại lỗ hổng nếu quyền không được cấu hình đúng.

Nên sử dụng các plugin quản lý quyền như [LuckPerms](https://luckperms.net/) để hạn chế quyền của người dùng thông thường.

### Chặn X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray là một trong những lỗ hổng dễ dàng sử dụng trên các client tối ưu hóa cơ bản.

Plazma cung cấp cấu hình để chặn X-Ray mặc định.

Vui lòng tham khảo cách chặn X-Ray và mô tả tại trang dưới đây.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Danh sách trắng <a href="#id-5.3" id="id-5.3"></a>

Trong trường hợp chỉ một số người dùng được phép kết nối vào máy chủ, nên sử dụng [Ngrok](./README.md#id-6.2) để sử dụng [địa chỉ máy chủ đã được mã hóa](#user-content-fn-5)[^5] hoặc thiết lập danh sách trắng để ngăn người chơi khác kết nối vào máy chủ.

Trong cửa sổ console máy chủ, sử dụng `/whitelist add <player>` để cho phép người chơi kết nối hoặc `/whitelist remove <player>` để cấm người chơi kết nối lại.

Để xem danh sách người chơi được phép kết nối, sử dụng `/whitelist query`.

***

[^1]: Hoặc Add-on cho Minecraft: Bedrock Edition.

[^2]: Bao gồm việc thêm nhóm sinh vật vào trò chơi.

[^3]: Thường được gọi là "hack".

[^4]: Trong trường hợp cấu hình chưa được tối ưu hóa, Plazma lỗi thời hoặc có lỗ hổng mới, có thể không chặn được.

[^5]: Khi người chơi kết nối vào máy chủ, thông qua máy chủ proxy Ngrok, địa chỉ Ngrok được cấp phát mỗi lần khởi động sẽ khác nhau.
