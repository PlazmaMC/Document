---
description: 了解如何定制服务器。
---

# 📶 발전하기

使用修改后的服务器平台，如Plazma，而不是使用Mojang Studios提供的官方服务器平台的原因是可以实现强大的**用户定制**能力。

以下是使用Plazma进行定制和利用的多种方法。

## 配置修改 <a href="#id-1" id="id-1"></a>

对Plazma进行定制的最基本方法就是修改配置。

Plazma提供强大的配置设置，从游戏机制到怪物属性等。

请参考以下页面了解Plazma的配置。

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**[某些数据包](#user-content-fn-2)[^2]在首次应用时可能无法正常应用。**

为此，建议重新启动服务器**2次**。

{% endhint %}

随着Minecraft版本的更新，数据包可能会很容易损坏。

特别是当数据包完全损坏时，服务器可能会崩溃，
因此，在更新服务器之前进行充分测试非常重要。

{% hint style="info" %}

**在启动服务器命令后输入`safeMode`，可以禁用所有数据包并启动服务器。**

[有关详细信息，请参阅`参考 > 参数和属性`](../reference/arguments.md#safeMode)

{% endhint %}

应用的数据包可以通过`/datapack list`命令进行确认。

***

## 优化 <a href="#id-4" id="id-4"></a>

Plazma已应用许多优化补丁。 此外，Plazma在首次启动时会自动优化配置，因此如果遵循[开始](./README.md)指南，则无需进行额外的优化工作。

但是，如果有许多玩家连接，或者世界非常庞大，则可以通过以下指南进行额外的优化工作。

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## 代理 <a href="#id-5" id="id-5"></a>

代理可连接服务器，使玩家无需进行额外操作即可移动到另一个服务器或与其他服务器交流。

有关安全且正确的代理设置信息，请参阅以下页面。

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## 安全 <a href="#id-5" id="id-5"></a>

随着Minecraft模组的发展，可以轻松在线获取[漏洞攻击引擎](#user-content-fn-3)[^3]。

即使在常规游戏中，大多数可执行的漏洞都被[默认阻止](#user-content-fn-4)[^4]，
但通过第三方加载器攻击漏洞是不受阻止的。

因此，如果服务器是公开的，则建议安装反作弊插件等来阻止漏洞使用，并
配置代理、自动重启、备份等，以便在服务器崩溃时快速恢复。

### 权限设置 <a href="#id-5.1" id="id-5.1"></a>

一些插件的管理员命令存在未正确设置权限的漏洞。

建议使用[LuckPerms](https://luckperms.net/)等权限管理插件，
限制普通用户的权限。

### X射线阻挡 <a href="#id-5.2" id="id-5.2"></a>

X射线是基本优化客户端中容易使用的漏洞之一。

Plazma提供了阻止X射线的配置。

有关X射线阻止方法和说明，请参阅以下页面。

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### 白名单 <a href="#id-5.3" id="id-5.3"></a>

如果仅允许某些用户连接到服务器，
则建议使用[Ngrok](./README.md#id-6.2)来使用[混淆的服务器地址](#user-content-fn-5)[^5]，或者
设置白名单以阻止其他玩家连接。

您可以通过服务器控制台中的`/whitelist add <player>`命令允许玩家连接，
或使用`/whitelist remove <player>`来再次禁止玩家连接。

要查看已允许连接的玩家，请使用`/whitelist query`。

***

[^1]: 或者Minecraft: Bedrock Edition的插件。

[^2]: 添加生物群系等。

[^3]: 通常被称为"作弊"。

[^4]: 如果配置不佳，Plazma过时，或者发现了新的漏洞，则可能未阻止玩家使用。

[^5]: 玩家通过Ngrok代理服务器连接到服务器，每次重新启动都会分配一个新的Ngrok地址。
