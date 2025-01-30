---
description: 瞭解如何自訂伺服器。
---

# 🎨 使用者化

Mojang Studios提供的官方伺服器平台，與Plazma等修改過的伺服器平台不同，最主要的原因是可以進行強大的**使用者自訂**。

以下是使用Plazma進行自訂和利用的多種方法。

## 配置修改 <a href="#id-1" id="id-1"></a>

對Plazma進行自訂的最基本方法就是修改配置。

Plazma提供了從遊戲機制到怪物屬性等強大的配置設定。

有關Plazma配置的說明，請參考下面的頁面。

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## 使用插件 <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma支持所有基于Paper的插件。**

对于Spigot插件，由于从1.20.5开始，由于Paper的映射变化，某些插件可能无法正常工作，但是基于Paper的插件，如Paper、Pufferfish和Purpur等，都可以在Plazma上正常运行。如果插件无法正常工作，请立即[报告给Plazma](../diagnosis/plugins.md)。

{% endhint %}

这是使用Plazma的主要原因，也是使Plazma个性化的最强大方法。
Plazma强大的插件生态系统使服务器易于个性化。

有多种方法可以查找并下载插件。 一些插件会将插件上传到公共存储库服务，而另一些插件则会上传到GitHub或自己的网站。

{% hint style="caution" %}

**插件可以直接访问系统！**

使用VirusTotal等服务在应用插件之前始终确保安全性，或者从可信任的服务下载插件。

{% endhint %}

有多种服务可用于下载插件。 其中，[SpigotMC论坛](https://www.spigotmc.org/resources/)、[BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins)、[Modrinth](https://modrinth.com/plugins)、[Hanger](https://hangar.papermc.io/)等服务在上传插件之前经过审核，只有安全的插件才会被分发。

### 应用插件 <a href="#id-2.1" id="id-2.1"></a>

如果已经下载了插件，现在可以应用插件了。

1. 插件是`.jar`或`Java可执行文件`。\
   有些插件可能被压缩成压缩文件，这种情况下
   解压缩并包含`bukkit`、`spigot`或`paper`的名称，
   如果有`fat`文件，则使用`fat`文件。
2. 将下载的文件放入服务器文件夹中的`plugins`文件夹中，然后重新启动服务器。
3. Plazma启动后，控制台将输出新内容。
   这表示Plazma已成功加载插件。
4. 即使Plazma已成功加载插件，某些插件可能无法启动。
   使用`/plugins`命令可以加载当前服务器上加载的插件。
   如果安装的插件名称不是<mark style="background-color:red;">红色</mark>，而是 <mark style="background-color:green;">绿色</mark>，则插件已正常加载。

如果插件未能正常加载，请查看以下页面以找到解决方案。

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## 使用数据包 <a href="#id-3" id="id-3"></a>

数据包是Minecraft默认提供的个性化方式，类似于[资源包](#user-content-fn-1)[^1]。

使用数据包可以添加新生物群系和挑战，修改游戏内的部分内容。

{% hint style="caution" %}

**数据包可能会损坏世界！**

一些损坏的数据包可能会损坏世界，这是无法挽回的。

因此，建议在应用数据包之前备份世界。

{% endhint %}

数据包也可以从多个服务中下载，如[CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs)、[Modrinth](https://modrinth.com/datapacks)、[Planet Minecraft](https://www.planetminecraft.com/data-packs/)等服务。

下载数据包后，将其放入服务器世界文件夹中的`datapacks`文件夹中以应用。
如果文件夹不存在，可以创建文件夹并添加。

{% hint style="warning" %}

**某些[数据包](#user-content-fn-2)[^2]在第一次应用时可能无法正确应用。**

为此，建议重新启动服务器**2次**。

{% endhint %}

数据包在Minecraft更新时很容易损坏。

特别是当数据包完全损坏时，服务器会崩溃，
因此，在更新服务器之前进行充分测试非常重要。

{% hint style="info" %}

**在服务器启动命令后输入`safeMode`，可以禁用所有数据包后启动服务器。**

[有关详细信息，请参阅`参考 > 参数和属性`。](../reference/arguments.md)

{% endhint %}

应用的数据包可以通过`/datapack list`命令进行确认。

***

[^1]: 或者Minecraft: Bedrock Edition的插件。

[^2]: 添加新生物群系等。
