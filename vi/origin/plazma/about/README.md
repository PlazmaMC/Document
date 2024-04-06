---
description: Tìm hiểu về Plazma là gì.
---

# ❓ Plazma là gì?

- **Plazma** là nền tảng máy chủ dựa trên [Paper](https://github.com/PaperMC/Paper) mang lại những điểm mạnh từ [Andromeda](https://github.com/EarendelArchived/Andromeda) và [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Luôn cố gắng cung cấp sự ổn định cao và hiệu suất mạnh mẽ, cập nhật nhanh chóng và nhiều tính năng phong phú.

## 📋 Mục tiêu của Plazma <a href="#id-1" id="id-1"></a>

- Đang cố gắng trở thành một nền tảng máy chủ với cập nhật nhanh chóng và ổn định cao.
- Đang cố gắng cung cấp nhiều tính năng và hiệu suất mạnh mẽ không kém phần nền tảng mod.
- Đang cố gắng tạo ra một nền tảng tự do có thể tùy chỉnh các bản vá của Vanilla.

## ⚙️ Đặc điểm chính <a href="#id-2" id="id-2"></a>

1. **Hệ sinh thái plugin mạnh mẽ**\
   Dựa trên [Paper](https://github.com/PaperMC/Paper),
   hầu hết [các plugin mới nhất](#user-content-fn-1)[^1] có thể tải xuống trên Internet hoạt động bình thường.
2. **Tối ưu hóa không cần cấu hình**\
   Tất cả các bản vá của [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) đã được bao gồm,
   cung cấp hiệu suất tốt nhất với một số tối ưu hóa và mod tích hợp.
3. **Trò chơi cá nhân hóa theo ý thích**\
   [Purpur](https://github.com/PurpurMC/Purpur) đi kèm với Plazma cho phép chỉnh sửa
   các thuộc tính tổng quát của trò chơi.
4. **Máy chủ chơi an toàn**\
   Có [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) tích hợp từ 1.19 trở đi
   [Mojang](#user-content-fn-2)[^2] đã vô hiệu hóa [hệ thống báo cáo trò chuyện](#user-content-fn-3)[^3],\
   loại bỏ hoàn toàn trình thu thập thông tin chẩn đoán để chơi trên máy chủ an toàn không bị theo dõi.
5. **Cập nhật nhanh nhất**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) giữ cho các bản vá trong Plazma luôn cập nhật, cung cấp cập nhật nhanh nhất trong các nền tảng máy chủ dựa trên Paper.
6. **Tối ưu hóa tệp cấu hình mặc định**\
   Tệp cấu hình mặc định đã được tối ưu hóa, không cần phải tối ưu hóa tệp cấu hình một cách riêng lẻ.
7. **Hoạt động đa luồng hệ thống có tổ chức**\
   Bất kỳ cơ chế hệ thống không liên quan đến cơ chế trò chơi nào được bất đồng bộ hóa, giảm [thời gian trễ](#user-content-fn-4)[^4] để tối ưu hóa máy chủ.
8. **Chặn việc sử dụng không cần thiết của không gian**\
   Hợp nhất dữ liệu có giá trị tương tự lại với nhau để giảm bộ nhớ sử dụng.

#### Muốn tìm hiểu thêm về Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Ứng dụng thực tế <a href="#id-3" id="id-3"></a>

- **Nền tảng xử lý plugin phức tạp một cách chính xác**\
  Plazma được sử dụng trên máy chủ của nhà phát triển [IPECTER](https://github.com/IPECTER).\
  Với các plugin tự phát triển hoạt động bằng NMS và Reflection, cùng với số lượng lớn dữ liệu pack phức tạp,
  máy chủ vẫn có thể chứa hơn 100 người chơi mà không giảm hiệu suất.
- **Nền tảng duy trì hiệu suất nhanh chóng trên máy chủ RPG**\
  Duy trì 100 người chơi trên một cụm mà không giảm TPS,\
  và cho phép tổng cộng 250 người chơi chơi một cách mượt mà trên 4 cụm.
- **Nền tảng hiển thị ánh sáng từ chunk/entity**\
  Thay đổi từ Purpur sang Plazma trên máy chủ sinh tồn trước đây gặp độ trễ khi xử lý chunk và entity,
  giúp giảm đáng kể độ trễ.
- **Nền tảng được nhiều streamer lựa chọn**\
  Được sử dụng như một phần của bucket được lựa chọn bởi nhiều người xem của nhiều streamer.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Trend người dùng Plazma trực tiếp">
</a>

## ⬇️ Tải xuống

Bạn có thể tải Plazma từ trang dưới đây.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Bạn muốn biết thông tin chi tiết về việc hỗ trợ phiên bản?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot plugin và Paper, Pufferfish, Purpur plugin.

[^2]: Được cung cấp bởi Microsoft Corporation.

[^3]: Nếu vô hiệu hóa hệ thống báo cáo trò chuyện, việc trò chuyện chỉ được xử lý trên máy chủ, ngăn chặn việc theo dõi trò chuyện từ Mojang.

[^4]: Thời gian dừng game trong một khoảng thời gian ngắn để hệ thống hoạt động.
