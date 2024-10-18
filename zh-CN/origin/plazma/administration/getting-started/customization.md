---
description: 了解如何定制服务器。
---

# 🎨 用户定制

使用修改后的服务器平台，如Plazma，而不是使用Mojang Studios提供的官方服务器平台的原因是可以实现强大的**用户定制**能力。

以下是使用Plazma进行定制和利用的多种方法。

## 配置修改 <a href="#id-1" id="id-1"></a>

对Plazma进行定制的最基本方法就是修改配置。

Plazma提供强大的配置设置，从游戏机制到怪物属性等。

请参考以下页面了解Plazma的配置。

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## 使用插件 <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma支持基于Paper的所有插件。**

对于Spigot插件，由于1.20.5版本后Paper的映射变化，可能会导致部分插件无法正常工作，但是基于Paper的插件，如Paper、Pufferfish和Purpur等，都可以在Plazma上正常运行。如果插件无法正常工作，请立即[报告给Plazma](../diagnosis/plugins.md)。

{% endhint %}

这是使用Plazma的主要原因，也是个性化Plazma的最强大方式。
Plazma强大的插件生态系统使服务器可以轻松个性化。

查找和下载插件有多种方法。 一些插件会将插件上传到公共存储库服务，而另一些插件则会上传到GitHub或自己的网站。

{% hint style="caution" %}

**插件可以直接访问系统！**

使用VirusTotal等服务在应用插件之前始终确保安全，或者从可信赖的服务下载插件。

{% endhint %}

有多种服务可用于下载插件。 其中，[SpigotMC论坛](https://www.spigotmc.org/resources/)、[BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins)、[Modrinth](https://modrinth.com/plugins)、[Hanger](https://hangar.papermc.io/)等服务在上传插件之前经过审核，只允许安全的插件流通。

### 应用插件 <a href="#id-2.1" id="id-2.1"></a>

如果已下载插件，则现在是应用插件的时候了。

1. 插件是以`.jar`或`Java可执行文件`的形式存在。\
   有些插件可能被压缩成压缩文件，在这种情况下，
   解压缩并找到名称中包含`bukkit`、`spigot`或`paper`的文件，
   如果有`fat`文件，则使用`fat`文件。
2. 将下载的文件放入服务器文件夹的`plugins`文件夹中，并重新启动服务器。
3. Plazma启动后，控制台将输出新内容。
   这表示Plazma已成功加载插件。
4. 即使Plazma已成功加载插件，某些插件可能无法启动。
   使用`/plugins`命令可以查看当前加载到服务器的插件。
   如果安装的插件名称不是<mark style="background-color:red;">红色</mark>，而是<mark style="background-color:green;">绿色</mark>，则表示插件已成功加载。

如果插件未能成功加载，请查看下面的页面以找到解决方法。

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## 使用数据包 <a href="#id-3" id="id-3"></a>

数据包是Minecraft提供的一种用户自定义方法，类似于[资源包](#user-content-fn-1)[^1]。

使用数据包可以添加新的生物群系和挑战，修改游戏内的一些部分。

{% hint style="caution" %}

**数据包可能损坏世界！**

一些损坏的数据包可能会损坏世界，这是不可逆转的。

因此，在应用数据包之前建议备份世界。

{% endhint %}

数据包也可以从多个服务中下载，如[CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs)、[Modrinth](https://modrinth.com/datapacks)、[Planet Minecraft](https://www.planetminecraft.com/data-packs)等服务。

下载数据包后，将其放入服务器的世界文件夹中的`datapacks`文件夹中以应用。
如果没有该文件夹，可以创建一个并添加数据包。

{% hint style="warning" %}

**某些[数据包](#user-content-fn-2)[^2]在首次应用时可能无法正常应用。**

为此，建议重新启动服务器**2次**。

{% endhint %}

随着Minecraft版本的更新，数据包可能会很容易损坏。

特别是当数据包完全损坏时，服务器可能会崩溃，
因此，在更新服务器之前进行充分测试非常重要。

{% hint style="info" %}

**在启动服务器命令后输入`safeMode`，可以禁用所有数据包并启动服务器。**

[有关详细信息，请参阅`参考 > 参数和属性`。](../reference/arguments.md)

{% endhint %}

应用的数据包可以通过`/datapack list`命令进行确认。

***

[^1]: 或者Minecraft: Bedrock Edition的插件。

[^2]: 添加生物群系等。
