---
description: 瞭解如何自訂伺服器。
---

# 📶 발전하기

Mojang Studios提供的官方伺服器平台，與Plazma等修改過的伺服器平台不同，最主要的原因是可以進行強大的**使用者自訂**。

以下是使用Plazma進行自訂和利用的多種方法。

## 配置修改 <a href="#id-1" id="id-1"></a>

對Plazma進行自訂的最基本方法就是修改配置。

Plazma提供了從遊戲機制到怪物屬性等強大的配置設定。

有關Plazma配置的說明，請參考下面的頁面。

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**[部分資料包](#user-content-fn-2)[^2]在初次應用時可能無法正常應用。**

为此，建议重新启动服务器**2次**。

{% endhint %}

数据包在Minecraft更新时很容易损坏。

特别是当数据包完全损坏时，服务器会崩溃，
因此，在更新服务器之前进行充分测试非常重要。

{% hint style="info" %}

**在服务器启动命令后输入`safeMode`，可以禁用所有数据包后启动服务器。**

[詳細內容請參考 `參考 > 引數與屬性`](../reference/arguments.md#safeMode)

{% endhint %}

应用的数据包可以通过`/datapack list`命令进行确认。

***

## 最佳化 <a href="#id-4" id="id-4"></a>

Plazma已經應用了許多最佳化補丁。 此外，當Plazma首次啟動時，會自動優化配置，因此如果遵循[入門指南](./README.md)，則無需進行額外的最佳化工作。

但是，如果有許多玩家連線，或者世界很大，
您可以通過以下指南進行額外的最佳化工作。

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## 代理 <a href="#id-5" id="id-5"></a>

代理可將服務器連接在一起，使玩家無需進行額外操作即可移動到其他服務器，
與其他服務器進行通信。

有關安全且正確的代理設置的信息，請參閱以下頁面。

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## 安全 <a href="#id-5" id="id-5"></a>

由於Minecraft的模組化發展，甚至在線上也很容易獲得[弱點攻擊引擎](#user-content-fn-3)[^3]。

即使在普通遊戲中，大多數可執行的弱點都是[基本上被阻擋的](#user-content-fn-4)[^4]，
但通過第三方加載器攻擊弱點是不被阻擋的。

因此，如果服務器是公開的，建議安裝反作弊插件等來阻止弱點使用，
並配置代理、自動重啟、備份等，以便即使服務器宕機也能快速恢復。

### 權限設定 <a href="#id-5.1" id="id-5.1"></a>

一些插件的管理員命令存在未正確設置權限的弱點。

建議使用[LuckPerms](https://luckperms.net/)等權限管理插件，
限制普通用戶的權限。

### X射線阻擋 <a href="#id-5.2" id="id-5.2"></a>

X射線是一種基本最佳化客戶端中很容易使用的弱點之一。

Plazma提供了可以基本阻擋X射線的配置。

有關X射線阻擋方法和說明，請參考以下頁面。

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### 白名單 <a href="#id-5.3" id="id-5.3"></a>

如果只允許部分用戶訪問服務器，
請使用[Ngrok](./README.md#id-6.2)來使用[混淆的服務器地址](#user-content-fn-5)[^5]，或者
設置白名單以防止其他玩家訪問服務器。

您可以在服務器控制台上使用 `/whitelist add <player>` 允許玩家訪問，或者
使用 `/whitelist remove <player>` 來再次禁止玩家訪問。

要查看已允許訪問的玩家，請使用 `/whitelist query`。

***

[^1]: 或者Minecraft: Bedrock Edition的插件。

[^2]: 添加新生物群系等。

[^3]: 通常被稱為"作弊"。

[^4]: 如果配置未最佳化，Plazma過時，或者發現了新的弱點，則可能未阻擋。

[^5]: 玩家通過Ngrok代理服務器訪問，每次重新啟動時發放的Ngrok地址都會有所不同。
