---
description: Tìm hiểu về đối số khởi đầu và thuộc tính hệ thống.
---

# 🎛️ Đối số và thuộc tính

Đối số khởi đầu và thuộc tính hệ thống là các giá trị được thêm vào các [lệnh được sử dụng](#user-content-fn-1)[^1] trong quá trình chạy Plazma,\
cho phép thay đổi giá trị không thể thay đổi sau khi Plazma đã chạy.

[위치에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 매개변수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## Thuộc tính hệ thống <a href="#id-1" id="id-1"></a>

Thuộc tính hệ thống được nhập trước `-jar` và được xử lý trong JVM trước khi Plazma khởi tạo.

{% hint style="warning" %}

**Khi chỉnh sửa thuộc tính hệ thống, cách hoạt động của Plazma và JVM có thể thay đổi, ảnh hưởng lớn đến trò chơi!**

Nếu không chắc chắn về vai trò của mỗi thuộc tính hệ thống, **đừng bao giờ sử dụng!**

{% endhint %}

### Cách sử dụng <a href="#id-1.1" id="id-1.1"></a>

Thuộc tính hệ thống được nhập như một đối số lệnh Java giữa `java` và `-jar`.

Ví dụ, nếu muốn áp dụng thuộc tính hệ thống `Plazma.dummyProperty`,\
bằng cách nhập như sau, giá trị `37` sẽ được nhập vào thuộc tính tiếp theo và Plazma sẽ khởi tạo.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` chỉ ra rằng đối số này không được tích hợp trong JVM mà là đối số riêng của Plazma,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정](#user-content-fn-3)[^3]됩니다.

{% hint style="info" %}

**Nền tảng máy chủ dòng Paperweight sử dụng dấu `.` trong tên thuộc tính để phân biệt từng nền tảng.**

Windows Powershell 등 일부 터미널에서는 이러한 매개변수를 허용하지 않을 수 있으므로, 매개변수 양 끝에 `"`를 [추가해야](#user-content-fn-4)[^4] 합니다.

{% endhint %}

### Toàn bộ thuộc tính hệ thống <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Cập nhật định dạng biển báo đã ngưng sử dụng.

#### `debug.entities`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Kích hoạt nhật ký gỡ lỗi liên quan đến thông tin thực thể.

#### `debug.rewriteForIDE`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa NMS revision để IDE có thể đọc thông tin gỡ lỗi một cách chính xác và tự động làm lại thông tin phiên bản nội bộ.

#### `disable.watchdog`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa hệ thống cảnh báo Watchdog của Spigot.

#### `letMeReload`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa thông báo xác nhận lệnh `/reload`.

{% hint style="danger" %}

**Lệnh `/reload` rất không ổn định, vì vậy, mọi vấn đề xảy ra sau khi sử dụng `/reload` là trách nhiệm của người dùng.**

Nếu bạn là nhà phát triển plugin và cần phải cập nhật plugin, hãy sử dụng hotswap thay vì `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa plugin sử dụng hệ thống nhập/xuất tiêu chuẩn.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Cảnh báo khi phát hiện định dạng cũ trong thành phần chat.

#### `Paper.bypassHostCheck`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa kiểm tra khớp mẫu máy chủ khi người chơi kết nối đến máy chủ.

#### `Paper.debugDynamicMissingKeys`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Kích hoạt nhật ký gỡ lỗi cho các khóa bị thiếu trong đối tượng NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Kích hoạt nhật ký gỡ lỗi cho các hồ sơ đầu mạc không hợp lệ.

Nhật ký này sẽ ghi lại tất cả các hồ sơ đầu mạc không hợp lệ trong thế giới cùng với vị trí của chúng.

#### `Paper.disableChannelLimit`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

플레이어당 적용되는 128개의 플러그인 [채널](#user-content-fn-5)[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa hệ thống ưu tiên lớp plugin.

Hữu ích khi gặp vấn đề trong plugin shade.

#### `Paper.disableFlushConsolidate`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa hệ thống gộp nén flush của Netty.

#### `Paper.excessiveTELimit`

- **Loại**: `Integer`
- **Giá trị mặc định**: `750`

Nếu số thực thể vượt quá giá trị được đặt, chúng sẽ được chia thành các gói tin đa phần và gửi đi.

#### `Paper.filterThreshold`

- **Loại**: `Integer`
- **Giá trị mặc định**: `8192`

Thiết lập kích thước tối đa của gói tin mà máy chủ có thể nhận được trong một lần.

#### `Paper.ignoreJavaVersion`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Vô hiệu hóa kiểm tra phiên bản Java.

{% hint style="danger" %}

**Như vậy, JVM có thể cố gắng truy cập vào mã không tồn tại!**

Có thể dẫn đến hỏng toàn bộ tệp trong thế giới và làm hỏng cơ chế trò chơi.

Mọi vấn đề phát sinh từ việc này là trách nhiệm của bạn và Plamza sẽ không hỗ trợ bất kỳ vấn đề nào liên quan.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Loại**: `Integer`
- **Giá trị mặc định**: `64`

플러그인 [채널](#user-content-fn-5)[^5] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Loại**: `Integer`
- **Giá trị mặc định**: `80`

Thiết lập độ dài tối đa của mỗi dòng trên biển báo.

#### `Paper.minPrecachedDatafixVersion`

- **Loại**: `Integer`
- **Giá trị mặc định**: `(phiên bản thế giới) + 1`

Thiết lập phiên bản thông tin cập nhật thế giới cần khởi tạo trước hết.

Hữu ích khi cần cập nhật lượng lớn chunk, nhưng không cần thiết trong các trường hợp khác.

#### `Paper.parseYamlCommentsByDefault`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `True`

Kích hoạt xử lý chú thích trong tệp YAML mặc định.

#### `Paper.playerConnection.keepAlive`

- **Loại**: `Integer`
- **Giá trị mặc định**: `30`

Khi không nhận được bất kỳ dữ liệu nào từ người chơi trong thời gian được chỉ định (giây), máy chủ sẽ đuổi người chơi.

일반적인 경우, [게임](#user-content-fn-7)[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Bỏ qua các chú thích trong tệp cấu hình máy chủ.

#### `Paper.debug-sync-loads`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Kích hoạt nhật ký gỡ lỗi việc tải đồng bộ chunk.

#### `Paper.enable-sync-chunk-writes`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Kích hoạt hệ thống ghi chunk theo trình tự mặc định của Minecraft.

Điều này làm cho việc lưu trữ mỗi chunk theo thứ tự, gây ra sự giảm hiệu suất lớn.

#### `Paper.explicit-flush`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Kích hoạt việc xả của mạng chanel một cách rõ ràng.

#### `Paper.strict-thread-checks`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Luôn ghi log lỗi không xảy ra trên luồng chính.

#### `Paper.tickList-warn-on-excessive-delay`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Xuất cảnh báo nếu công việc đặt trước có thời gian chờ quá lâu.

#### `Paperclip.patchOnly`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `False`

Khi sử dụng tệp thực thi mặc định, chỉ áp dụng bản vá mà không khởi động máy chủ.

#### `Plazma.aggressiveOptimize`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `false`

{% hint style="warning" %}

**Thuộc tính này sẽ được chuyển sang đối số khởi đầu từ phiên bản 1.20.5 trở đi.**

{% endhint %}

Áp dụng tối ưu hóa cấu hình ban đầu một cách nghiêm ngặt hơn khi khởi đầu lần đầu.

Khi kích hoạt, máy chủ sẽ trở nhanh hơn và an toàn hơn, nhưng có thể chặn một số lỗi hoặc ảnh hưởng lớn đến trò chơi.

#### `Plazma.iKnowWhatIAmDoing`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `false`

Plazma가 초기화될 때 출력되는 [경고문](#user-content-fn-11)[^11]을 억제합니다.

### Thuộc tính đã bị ngưng sử dụng <a href="#id-1.3" id="id-1.3"></a>

Dưới đây là các thuộc tính hệ thống đã bị ngưng sử dụng.

#### `timings.bypassMax`

- **Loại**: `Boolean`
- **Giá trị mặc định**: `false`
- **ĐÃ NGƯNG SỬ DỤNG**: Timings đã bị loại bỏ hoàn toàn khỏi Plazma từ sau

Quyết định xem có thể vượt quá giá trị tối đa có thể gửi đến API Timings của Aikar.

Ngay cả khi điều này xảy ra, nếu không được xử lý bởi API, giới hạn tần suất sẽ được áp dụng.

***

## Tham số bắt đầu <a href="#id-2" id="id-2"></a>

Tham số bắt đầu được nhập sau `-jar *.jar` để khởi tạo Plazma và xử lý cùng với nhau.

### Cách sử dụng <a href="#id-2.1" id="id-2.1"></a>

Thuộc tính hệ thống được nhập như tham số lệnh chương trình sau `-jar *.jar`.

Ví dụ, nếu bạn muốn áp dụng tham số bắt đầu `nogui`,\
hãy nhập như sau để Plazma xử lý tham số `nogui` trong quá trình khởi tạo.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Toàn bộ tham số bắt đầu <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Bí danh**: `b`
- **Giá trị mặc định**: `bukkit.yml`

Đặt tên và vị trí của [Tệp cấu hình Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Bí danh**: `c`
- **Giá trị mặc định**: `commands.yml`

Đặt tên và vị trí của [Tệp cấu hình lệnh Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Bí danh**: `c`
- **Giá trị mặc định**: `server.properties`

Đặt tên và vị trí của tệp [Thuộc tính máy chủ](../reference/configurations/property.md).

#### `demo`

Khởi động máy chủ vào thế giới demo.

#### `eraseCache`

Xóa tệp cache còn lại sau nâng cấp thế giới.

#### `forceUpgrade`

Bỏ qua phiên bản và bắt buộc nâng cấp thế giới [^12].

#### `help`

- **Bí danh**: `?`

Xuất toàn bộ tham số khởi đầu và mô tả của Plazma.

#### `initSettings`

Chỉ tạo tệp cấu hình và kết thúc máy chủ.

#### `jfrProfile`

Kích hoạt hồ sơ JFR.

#### `max-players`

- **Bí danh**: `s`, `size`
- **Giá trị mặc định**: `(Thuộc tính máy chủ)`

Thiết lập số lượng [người chơi](#user-content-fn-14)[^14] tối đa được phép.

#### `nogui`

Vô hiệu hóa bảng điều khiển giao diện đồ họa.

#### `nojline`

비활성화된 JLine을 사용하고 바닐라 콘솔을 사용합니다.

#### `온라인 모드`

- **별칭**: `o`
- **Giá trị mặc định**: `(Thuộc tính máy chủ)`

Mojang 인증 서버에서 플레이어를 인증할지 선택합니다.

**Velocity 또는 기타 프록시를 사용하지 않는 경우 [EULA](../getting-started/README.md#id-5) 위반으로 처벌될 수 있습니다.**

#### `paper-settings`

- **별칭**: `paper`
- **기본값**: `paper.yml`

{% hint style="warning" %}

**Đối số này đã bị ngưng sử dụng từ phiên bản 1.19.4 trở đi**

{% endhint %}

사용 중지된 PaperSpigot 구성 파일의 위치를 설정합니다.

기존 구성을 새 구성 파일로 이전하기 위해 사용되며, 그 이후에는 사용되지 않습니다.

#### `paper-settings-directory`

- **별칭**: `paper-dir`
- **기본값**: `config`

[Paper 구성 파일](../reference/configurations/paper/README.md)이 위치하는 폴더의 이름과 위치를 설정합니다.

#### `plazma-settings-directory`

- **별칭**: `plazma-dir`

[Plazma 구성 파일](../reference/configurations/plazma/README.md)이 위치하는 폴더의 이름과 위치를 설정합니다.

#### `plugins`

- **별칭**: `p`
- **기본값**: `plugins`

플러그인 폴더의 위치를 설정합니다.

#### `pufferfish-settings`

- **별칭**: `pufferfish`
- **기본값**: `pufferfish.yml`

[Pufferfish 구성 파일](../reference/configurations/pufferfish.md)의 이름과 위치를 설정합니다.

#### `purpur-settings`

- **별칭**: `purpur`
- **기본값**: `purpur.yml`

[Purpur 구성 파일](../reference/configurations/purpur/README.md)의 이름과 위치를 설정합니다.

#### `safeMode`

(안전 모드) 서버를 완전한 바닐라 상태로 시작합니다.

#### `server-ip`

- **별칭**: `h`, `host`
- **Giá trị mặc định**: `(Thuộc tính máy chủ)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-13)[^13] 주소를 설정합니다.

#### `server-port`

- **별칭**: `p`, `port`
- **Giá trị mặc định**: `(Thuộc tính máy chủ)`

서버의 포트를 설정합니다.

#### `server-name`

- **기본값**: `A Plazma Server`

서버의 이름을 설정합니다.

#### `spigot-settings`

- **별칭**: `S`
- **기본값**: `spigot.yml`

[Spigot 구성 파일](../reference/configurations/spigot.md)의 이름과 위치를 설정합니다.

#### `version`

- **별칭**: `v`

Plazma 버전을 표시합니다.

#### `world-dir`

- **별칭**: `W`, `universe`, `world-container`
- **기본값**: `(서버 폴더)`

월드 파일이 저장되는 위치를 설정합니다.

#### `world-name`

- **별칭**: `w`, `world`
- **Giá trị mặc định**: `(Thuộc tính máy chủ)`

월드 파일의 이름을 설정합니다.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: 위치에 따라 처리되는 인수가 변경됩니다.

[^3]: 예를 들어, `Plazma.iKnowWhatIAmDoing`을 `true`로 설정하려는 경우, `-DPlazma.iKnowWhatIAmDoing=true` 대신 `-DPlazma.iKnowWhatIAmDoing`만 입력해도 작동합니다.

[^4]: 예를 들어, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: 이벤트 감지기.

[^6]: 이벤트 감지기.

[^7]: 클라이언트.

[^8]: 서버와의 정상적인 연결을 나타내는 신호.

[^9]: Purpur의 AFK 추방 기능을 사용하면 자리를 비운 플레이어도 추방할 수 있습니다.

[^10]: 동기 청크 작성 시스템, Sync Chunk Write System.

[^11]: `주의! Plazma는 예기치 않은 문제를 일으킬 수 있으므로 공개 서버에 사용하기 전에 충분히 테스트하십시오.`

[^12]: 게임에서 `월드 최적화`도 이와 같은 원리로 작동합니다.

[^13]: 인터넷 프로토콜, IP.

[^14]: `레벨 2` 이상의 관리자는 제외합니다.
