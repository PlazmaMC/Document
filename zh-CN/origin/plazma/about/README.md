---
description: 了解 Plazma 是什么样的服务器平台。
---

# ❓ Plazma是什么？

- **Plazma**是基于[Paper](https://github.com/PaperMC/Paper)的服务器平台，汲取了[Andromeda](https://github.com/EarendelArchived/Andromeda)和[Fusion](https://github.com/RuinedTechnologyUnify/Fusion)的优点。
- 我们致力于提供高度稳定性、强大性能、快速更新和丰富功能。

## 📋 Plazma的目标 <a href="#id-1" id="id-1"></a>

- 我们努力成为一个快速更新、高度稳定的服务器平台。
- 我们努力提供与模组平台不相上下的丰富功能和强大性能。
- 我们努力创建一个可以自由定制甚至调整Vanilla补丁的平台。

## ⚙️ 主要特点 <a href="#id-2" id="id-2"></a>

1. **强大的插件生态系统**\
   基于[Paper](https://github.com/PaperMC/Paper)，可以正常运行大多数可在互联网上下载的[最新插件](#user-content-fn-1)[^1]。
2. **无需配置的优化**\
   包含[Pufferfish](https://github.com/pufferfish-gg/Pufferfish)的所有补丁，并包含了一些内置优化和模式，提供最佳性能。
3. **自定义游戏玩法**\
   包括在Plazma中的[Purpur](https://github.com/PurpurMC/Purpur)，可以修改游戏的整体属性。
4. **安全玩服务器**\
   [无聊天举报](https://github.com/Aizistral-Studios/No-Chat-Reports)包括自1.19起添加的[Mojang](#user-content-fn-2)[^2]的[举报系统](#user-content-fn-3)[^3]可以禁用，完全删除诊断信息收集器，可以在无追踪的安全服务器上进行游戏。
5. **最快的更新**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)确保Plazma的内置补丁始终保持最新，为基于Paper的服务器平台提供最快的更新速度。
6. **优化默认配置文件**\
   默认应用的配置文件已经优化，无需自行优化配置文件。
7. **多线程高效运行**\
   通过异步化与游戏机制无关的系统机制，减少[延迟时间](#user-content-fn-4)[^4]以优化服务器。
8. **阻止不必要的空间使用**\
   将具有相似值的数据合并为一个以减少内存使用。

#### 想了解更多关于Plazma的信息？ <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ 应用案例 <a href="#id-3" id="id-3"></a>

- **处理复杂插件的平台**\
  开发者[IPECTER](https://github.com/IPECTER)在其服务器上使用了Plazma。 即使使用自定义插件和大量数据包，基于NMS和反射运行，可以容纳超过100名玩家而无性能下降。
- **在RPG服务器上保持高性能的平台**\
  在单个集群中稳定地维持100名玩家而无TPS下降，并在4个集群中让总共250名玩家可以愉快地游玩。
- **在区块/实体上显示光芒的平台**\
  通过从Purpur更改到Plazma，成功减少了大部分处理区块和实体时出现的延迟。
- **许多流行主播选择的平台**\
  许多知名主播选择使用Plazma作为其观众互动的桶。

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>实时Plazma用户趋势</p></figcaption>
</figure>

## ⬇️ 下载

您可以在下面的页面上下载Plazma。

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### 想了解版本支持的详细信息？

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit、CraftBukkit、Spigot插件以及Paper、Pufferfish、Purpur插件。

[^2]: 由Microsoft Corporation提供。

[^3]: 禁用聊天举报系统将使聊天完全在服务器上处理，阻止Mojang的聊天跟踪。

[^4]: 系统机制需要暂停游戏以运行。
