---
description: 了解常见问题。
---

# ⁉️ 常见问题

{% hint style="info" %}

**找不到想要的答案吗？**

[官方 Discord 服务器](https://discord.gg/MmfC52K8A8)或者[GitHub 问题](https://github.com/PlazmaMC/PlazmaBukkit/issues)向社区提问！

{% endhint %}

### 打印消息后无法执行

如果控制台显示 `no main manifest attribute, in plazma-(version).jar`，
则下载的文件是开发 API 文件，应从 GitHub 页面下载 **Reobf Paperweight**。

请参考以下页面以获取更多信息。

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### 每次启动服务器时都会显示警告

Plazma 包含一些不稳定的补丁，因此可能会出现故障。因此，在服务器启动时始终显示以下警告消息。

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

使用 [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] 系统属性可以禁用此警告消息。

请参考以下页面以获取更多信息。

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: 从1.20.1版本开始提供
