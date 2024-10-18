---
description: Tìm hiểu về quyền của Plazma.
---

# 🛡️ Quyền

Quyền là một công cụ bảo mật đơn giản để thiết lập phạm vi mà người chơi trên máy chủ có thể tương tác với nhau.

Để sử dụng quyền một cách hiệu quả và dễ dàng chỉnh sửa, bạn cần sử dụng các plugin như [LuckPerms](https://luckperms.net).

***

## Hiểu về hệ thống quyền mặc định <a href="#id-1" id="id-1"></a>

Trong Minecraft, có các nhóm quyền quản lý cơ bản được cung cấp.

Bạn có thể thiết lập quyền cho [quản trị viên](#user-content-fn-1)[^1] và khối lệnh, và có thể chỉnh sửa trong [cấu hình máy chủ](configurations/property.md).

0. **Người chơi**\
   Thường là nhóm quyền mà tất cả người chơi được cấp.
1. **Trung gian**\
   Có thể bỏ qua bảo vệ spawn.
2. **Quản trị viên thế giới**\
   Có thể sử dụng tất cả các lệnh và khối lệnh liên quan đến quản lý thế giới.\
   Là nhóm quyền mặc định cho dữ liệu và khối lệnh.
3. **Quản trị viên**\
   Có thể sử dụng tất cả các lệnh liên quan đến quản lý người chơi.
4. **Chủ quản trị**\
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

**Chỉ hoạt động khi đã kích hoạt `(Entity) > ridable` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Mặc định**: `Không`

Cho phép người chơi sử dụng kỹ năng đặc biệt của thực thể khi đang lên thực thể.

Không phải tất cả các kỹ năng đặc biệt của thực thể đều có sẵn. Xem danh sách toàn bộ kỹ năng đặc biệt có sẵn dưới đây.

{% hint style="info" %}

**Có ý tưởng tốt cho kỹ năng đặc biệt?**

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

**Chỉ hoạt động khi đã kích hoạt `(Entity) > ridable` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

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

**Lệnh này đã bị ngừng sử dụng.**

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

Khi [Chống X-Ray](../expert/xray.md) được kích hoạt,
những người chơi có quyền sẽ không bị mã hóa các khối chống X-Ray.

Điều này giúp cả hai bên trải nghiệm cải thiện hiệu suất.

> Để biết cách cấu hình chống X-Ray, hãy tham khảo trang dưới đây.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Mặc định**: `Không`

{% hint style="warning" %}

Quyền này sẽ được thay đổi thành `plazma.bypass.watchdog` trong 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Mặc định**: `Không`

Cho phép sử dụng [mã màu](https://minecraft.wiki/w/Formatting_codes#Color_codes) trên mỏ.

{% hint style="info" %}

**Chỉ hoạt động khi đã kích hoạt `anvil > allow-colors` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Mặc định**: `Không`

Cho phép sử dụng [mã định dạng](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) trên mỏ.

{% hint style="info" %}

**Chỉ hoạt động khi đã kích hoạt `anvil > allow-colors` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Mặc định**: `Không`

Cho phép sử dụng [Thẻ MiniMessage](https://docs.advntr.dev/minimessage/format.html) trên mỏ.

{% hint style="info" %}

**Chỉ hoạt động khi đã kích hoạt `anvil > allow-minimessages` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Mặc định**: `Không`

Cho phép vô hiệu hóa `nghiêng chữ` bằng mã định dạng `&r` trên mỏ.

{% hint style="info" %}

**Chỉ hoạt động khi đã kích hoạt `anvil > allow-colors` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Mặc định**: `Không`

Khi người chơi ký vào sách, áp dụng [mã định dạng](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

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

**Chỉ hoạt động khi đã kích hoạt `gameplay-mechanics > silk-touch` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Mặc định**: `Không`

Thay đổi kích thước của hòm kỹ lưu.

Có thể nhập `one`, `two`, `three`, `four`, `five`, `six` vào `(NumberString)`.

{% hint style="info" %}

**Chỉ hoạt động khi đã kích hoạt `ender_chest > six-rows` và `ender_chest > use-permissions-for-rows` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Mặc định**: `Không`

Cho phép bảo vệ bất tử hoạt động khi còn trong hòm đồ.

{% hint style="info" %}

**Chỉ hoạt động khi đã kích hoạt `totem-of-undying-works-in-inventory` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Mặc định**: `Không`

Cho phép người chơi bỏ qua giới hạn số người truy cập.

#### `purpur.mending_shift_click`

- **Mặc định**: `Không`

Cho phép người chơi sửa chữa vật phẩm đang cầm khi họ `ngồi xuống và tương tác`.

{% hint style="info" %}

**[Cấu hình theo từng thế giới Purpur](configurations/purpur/world.md) cần kích hoạt `shift-right-click-repairs-mending-points` để hoạt động.**

{% endhint %}

#### `purpur.place.spawners`

- **Mặc định**: `Không`

Cho phép người chơi cài đặt trứng sinh vật.

{% hint style="info" %}

**Chỉ hoạt động khi đã kích hoạt `gameplay-mechanics > silk-touch` trong [Cấu hình thế giới Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Mặc định**: `Không`

Cho phép người chơi di chuyển ngay lập tức khi họ sử dụng cổng Nether.

#### `purpur.sign.color`

- **Mặc định**: `Không`

표지판에 [mã màu](https://minecraft.wiki/w/Formatting_codes#Color_codes) được phép sử dụng.

{% hint style="info" %}

**Phải kích hoạt `sign > allow-colors` trong **[cấu hình thế giới Purpur](configurations/purpur/world.md)** để hoạt động.**

{% endhint %}

#### `purpur.sign.magic`

- **Mặc định**: `Không`

Cho phép sử dụng mã hóa độc đáo `(&o)` trên biển chỉ dẫn.

{% hint style="info" %}

**Phải kích hoạt `sign > allow-colors` trong **[cấu hình thế giới Purpur](configurations/purpur/world.md)** để hoạt động.**

{% endhint %}

#### `purpur.sign.style`

- **Mặc định**: `Không`

Cho phép sử dụng [mã định dạng `(&o không bao gồm)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) trên biển chỉ dẫn.

{% hint style="info" %}

**Phải kích hoạt `sign > allow-colors` trong **[cấu hình thế giới Purpur](configurations/purpur/world.md)** để hoạt động.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Mặc định**: `Không`

Cho phép người chơi ngăn chặn vụ nổ TNT bằng cách `tương tác` với nó bằng kéo.

{% hint style="info" %}

**[Cấu hình thế giới Purpur](configurations/purpur/world.md) cần có `defuse-tnt-change` lớn hơn hoặc bằng `0.0` để hoạt động.**

{% endhint %}

### Quyền sắp được cung cấp

#### `plazma.bypass.ncr-require`

- **Mặc định**: `Không`

Cho phép người chơi kết nối mà không cần cài đặt mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**[Cấu hình thế giới Plazma](configurations/plazma/world.md) cần kích hoạt `no-chat-reports > require-install` để hoạt động.**

{% endhint %}

***

[^1]: Người điều hành.

[^2]: Ví dụ: `ender_dragon`
