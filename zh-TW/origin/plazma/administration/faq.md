---
description: 瞭解常見問題。
---

# ⁉️ 常見問題

{% hint style="info" %}

**找不到您想要的答案嗎？**

[官方 Discord 伺服器](https://discord.gg/MmfC52K8A8) 或 [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) 向社區提問！

{% endhint %}

### 執行時顯示訊息但未執行

如果在控制台上輸出`no main manifest attribute, in plazma-(version).jar`，\
下載的文件是開發API文件，應該從GitHub頁面下載**Reobf Paperweight**。

請參考以下頁面以獲得詳細資訊。

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### 每次啟動伺服器時都會顯示警告

Plazma包含一些不穩定的修補程式，因此可能會總是在伺服器啟動時輸出以下警告訊息。

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

可以使用[`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1]系統屬性來停用此警告訊息。

請參考以下頁面以獲得詳細資訊。

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: 從1.20.1版本開始可用
