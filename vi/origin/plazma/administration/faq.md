---
description: Tìm hiểu về các câu hỏi thường gặp.
---

# ⁉️ Câu hỏi thường gặp

{% hint style="info" %}

**Không tìm thấy câu trả lời bạn muốn?**

[Máy chủ Discord chính thức](https://discord.gg/MmfC52K8A8) hoặc [Vấn đề GitHub](https://github.com/PlazmaMC/PlazmaBukkit/issues) để đặt câu hỏi trong cộng đồng!

{% endhint %}

### Không thể thực thi với thông báo xuất hiện

Nếu bạn thấy thông báo `no main manifest attribute, in plazma-(version).jar` trên cửa sổ console,\
file bạn đã tải xuống là file API dành cho phát triển, bạn cần phải tải **Reobf Paperweight** từ trang GitHub.

Để biết thêm chi tiết, vui lòng tham khảo trang sau.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Cảnh báo xuất hiện mỗi khi máy chủ khởi động

Plazma chứa một số bản vá không ổn định và luôn có khả năng gây sự cố, vì vậy máy chủ sẽ hiển thị thông báo sau mỗi lần khởi động.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Bạn có thể vô hiệu hóa thông báo này bằng cách sử dụng thuộc tính hệ thống [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Để biết thêm chi tiết, vui lòng tham khảo trang sau.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Có sẵn từ phiên bản 1.20.1 trở lên
