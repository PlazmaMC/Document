---
description: Tìm hiểu về quyền của Plazma.
---

# 🛡️ Quyền

Quyền là một công cụ bảo mật đơn giản để thiết lập phạm vi mà người chơi trên máy chủ có thể tương tác với nhau.

Để sử dụng quyền một cách hiệu quả và dễ dàng chỉnh sửa, bạn cần sử dụng các plugin như [LuckPerms](https://luckperms.net).

***

## Hiểu về hệ thống quyền mặc định <a href="#id-1" id="id-1"></a>

Trong Minecraft, có các nhóm quyền quản lý cơ bản được cung cấp.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Người chơi**\
   Thường là nhóm quyền mà tất cả người chơi được cấp.
2. **Trung gian**\
   Có thể bỏ qua bảo vệ spawn.
3. **Quản trị viên thế giới**\
   Có thể sử dụng tất cả các lệnh và khối lệnh liên quan đến quản lý thế giới.\
   Là nhóm quyền mặc định cho dữ liệu và khối lệnh.
4. **Quản trị viên**\
   Có thể sử dụng tất cả các lệnh liên quan đến quản lý người chơi.
5. **Chủ quản trị**\
   Có thể sử dụng tất cả các lệnh liên quan đến quản lý máy chủ.\
   Là nhóm quyền mặc định cho bảng điều khiển và quản trị viên.

***

## Thiết lập quyền <a href="#id-2" id="id-2"></a>

***

## Toàn bộ quyền <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Mặc định**: `Không`

Cho phép người chơi `ngồi và tương tác` với thực thể để lên thực thể.

Khi lên thực thể, bạn có thể điều khiển di chuyển của thực thể bằng `phím di chuyển` và có thể nhảy hoặc bay bằng `phím nhảy`.

Trong `(Namespaced Key)` sẽ là [ID Namespaced của thực thể](#user-content-fn-2)[^2].

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Mặc định**: `Không`

Cho phép người chơi sử dụng kỹ năng đặc biệt của thực thể khi đang lên thực thể.

Không phải tất cả các kỹ năng đặc biệt của thực thể đều có sẵn. Xem danh sách toàn bộ kỹ năng đặc biệt có sẵn dưới đây.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Hãy chia sẻ ý tưởng của bạn tại [Plazma Discord](https://plazmamc.org/discord) hoặc [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Xem danh sách kỹ năng đặc biệt có sẵn hiện tại</summary>

- **`crepper`**\
  Khi nhấn `phím nhảy`, sẽ phát nổ.\
  Nếu người chơi có quyền `allow.powered.creeper`, họ có thể giữ `phím nhảy` để nạp năng lượng.
- **`dolphin`**\
  Khi nhấn `phím nhảy`, sẽ lao về phía trước.
- **`phantom`**\
  Khi nhấn `phím nhảy`, sẽ phun lửa.
- **`wither`**\
  Khi `tương tác`, sẽ phóng đầu wither.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/credits (Người chơi)`](commands.md#credits).

Thêm `.other` sau tên quyền để cho phép người chơi khác sử dụng.

#### `bukkit.command.demo`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/demo (Người chơi)`](commands.md#demo).

Thêm `.other` sau tên quyền để cho phép người chơi khác sử dụng.

#### `bukkit.command.ping`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/ping (Người chơi)`](commands.md#ping).

Thêm `.other` sau tên quyền để cho phép người chơi khác sử dụng.

#### `bukkit.command.ram`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/rambar (Người chơi)`](commands.md#rambar).

Thêm `.other` sau tên quyền để cho phép người chơi khác sử dụng.

#### `bukkit.command.restart`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/tpsbar (Người chơi)`](commands.md#tpsbar).

Thêm `.other` sau tên quyền để cho phép người chơi khác sử dụng.

#### `bukkit.command.timings`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/timings`](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Để biết thêm về các lệnh tương tự, hãy xem trang [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép sử dụng lệnh `/gamemode (GameMode) (Người chơi)`.

Thêm `.other` sau tên quyền để cho phép người chơi khác sử dụng.

#### `paper.antixray.bypass`

- **Mặc định**: `Không`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Điều này giúp cả hai bên trải nghiệm cải thiện hiệu suất.

> Để biết cách cấu hình chống X-Ray, hãy tham khảo trang dưới đây.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Mặc định**: `Không`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Mặc định**: `Không`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Mặc định**: `Không`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Mặc định**: `Không`

Cho phép sử dụng [Thẻ MiniMessage](https://docs.advntr.dev/minimessage/format.html) trên mỏ.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Mặc định**: `Không`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Mặc định**: `Không`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **Mặc định**: `Không`

Loại bỏ người chơi khỏi danh sách đuổi vì không hoạt động.

#### `purpur.debug.f3n`

- **Mặc định**: `Quản trị viên thế giới`

Cho phép người chơi thay đổi chế độ game bằng phím `F3 + N`.

Không hoạt động nếu không có quyền cho chế độ game đó.

#### `purpur.drop.spawners`

- **Mặc định**: `Không`

Khi đào mỏ với vật phẩm được cấu hình, sẽ rơi ra khối spawner.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Mặc định**: `Không`

Thay đổi kích thước của hòm kỹ lưu.

Có thể nhập `one`, `two`, `three`, `four`, `five`, `six` vào `(NumberString)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Mặc định**: `Không`

Cho phép bảo vệ bất tử hoạt động khi còn trong hòm đồ.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Mặc định**: `Không`

Cho phép người chơi bỏ qua giới hạn số người truy cập.

#### `purpur.mending_shift_click`

- **Mặc định**: `Không`

Cho phép người chơi sửa chữa vật phẩm đang cầm khi họ `ngồi xuống và tương tác`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Mặc định**: `Không`

Cho phép người chơi cài đặt trứng sinh vật.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Mặc định**: `Không`

Cho phép người chơi di chuyển ngay lập tức khi họ sử dụng cổng Nether.

#### `purpur.sign.color`

- **Mặc định**: `Không`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Mặc định**: `Không`

Cho phép sử dụng mã hóa độc đáo `(&o)` trên biển chỉ dẫn.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Mặc định**: `Không`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Mặc định**: `Không`

Cho phép người chơi ngăn chặn vụ nổ TNT bằng cách `tương tác` với nó bằng kéo.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Quyền sắp được cung cấp

#### `plazma.bypass.ncr-require`

- **Mặc định**: `Không`

Cho phép người chơi kết nối mà không cần cài đặt mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Người điều hành.

[^2]: Ví dụ: `ender_dragon`
