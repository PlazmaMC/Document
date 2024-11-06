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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Cập nhật nhanh nhất**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) giữ cho các bản vá trong Plazma luôn cập nhật, cung cấp cập nhật nhanh nhất trong các nền tảng máy chủ dựa trên Paper.
6. **Tối ưu hóa tệp cấu hình mặc định**\
   Tệp cấu hình mặc định đã được tối ưu hóa, không cần phải tối ưu hóa tệp cấu hình một cách riêng lẻ.
7. **Hoạt động đa luồng hệ thống có tổ chức**\
   Bất kỳ cơ chế hệ thống không liên quan đến cơ chế trò chơi nào được bất đồng bộ hóa, giảm [thời gian trễ](#user-content-fn-4)[^4] để tối ưu hóa máy chủ.
8. **Chặn việc sử dụng không cần thiết của không gian**\
   Hợp nhất dữ liệu có giá trị tương tự lại với nhau để giảm bộ nhớ sử dụng.

## ✨ Ứng dụng thực tế <a href="#id-3" id="id-3"></a>

- **Nền tảng xử lý plugin phức tạp một cách chính xác**\
  Plazma được sử dụng trên máy chủ của nhà phát triển [IPECTER](https://github.com/IPECTER).\
  Với các plugin tự phát triển hoạt động bằng NMS và Reflection, cùng với số lượng lớn dữ liệu pack phức tạp,
  máy chủ vẫn có thể chứa hơn 100 người chơi mà không giảm hiệu suất.
- **Nền tảng duy trì hiệu suất nhanh chóng trên máy chủ RPG**\
  Duy trì 100 người chơi trên một cụm mà không giảm TPS,\
  và cho phép tổng cộng 250 người chơi chơi một cách mượt mà trên 4 cụm.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Nhiều nền tảng được nhiều streamer lựa chọn**\
  Được sử dụng như một phần của thùng chứa khán giả của nhiều streamer.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
