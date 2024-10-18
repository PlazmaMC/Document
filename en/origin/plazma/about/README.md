---
description: Learn about what Plazma is as a server platform.
---

# ❓ What is Plazma?

- **Plazma** is a server platform based on [Paper](https://github.com/PaperMC/Paper) that takes only the advantages of [Andromeda](https://github.com/EarendelArchived/Andromeda) and [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- We are always striving to provide high stability, powerful performance, fast updates, and extensive features.

## 📋 Goals of Plazma <a href="#id-1" id="id-1"></a>

- We are working hard to become a server platform with fast updates and high stability.
- We are striving to provide extensive features and powerful performance comparable to mod platforms.
- We are working towards creating a free platform that allows customization of vanilla patches.

## ⚙️ Key Features <a href="#id-2" id="id-2"></a>

1. **Powerful Plugin Ecosystem**\
   Based on [Paper](https://github.com/PaperMC/Paper),
   most of the [latest plugins](#user-content-fn-1)[^1] available for download on the internet work properly.
2. **Optimization without the need for settings**\
   Containing all patches from [Pufferfish](https://github.com/pufferfish-gg/Pufferfish),
   with some built-in optimizations and modes, it provides the best performance.
3. **Customizable game to your liking**\
   [Purpur](https://github.com/PurpurMC/Purpur) included in Plazma allows you to
   modify the overall attributes of the game.
4. **Play on a server safely**\
   Includes [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) to disable
   [Mojang](#user-content-fn-2)[^2]'s [chat reporting system](#user-content-fn-3)[^3] added from 1.19,
   allowing you to play on a server without tracking with the complete removal of diagnostic data collectors.
5. **Fastest updates**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) ensures that Plazma's included patches are always kept up to date, providing the fastest updates among Paper-based server platforms.
6. **Optimized default configuration files**\
   The default configuration files are optimized, eliminating the need for manual optimization.
7. **Systematically functioning multithreading**\
   Asynchronously synchronizing system mechanisms unrelated to game mechanics to reduce [latency](#user-content-fn-4)[^4] and optimize the server.
8. **Blocking unnecessary space usage**\
   Consolidating data with similar values reduces memory usage.

#### Want to learn more about Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Use Cases <a href="#id-3" id="id-3"></a>

- **Platform that handles complex plugins correctly**\
  Plazma is used on the server of developer [IPECTER](https://github.com/IPECTER).
  With self-plugins that operate with NMS and reflection, and a large number of complex and massive data packs applied,
  it can handle over 100 players without performance degradation.
- **Platform that maintains fast performance on RPG servers**\
  Maintained 100 players on a single cluster without TPS drop, and
  250 players in total were able to play comfortably on 4 clusters.
- **Platform that shines light on chunks/entities**\
  By switching from Purpur to Plazma, the platform for survival servers that previously experienced delays in processing chunks and entities,
  was able to reduce most of the delays.
- **Platform chosen by many streamers**\
  It is being chosen as a bucket for viewer participation by many streamers.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Real-time Plazma user trend">
</a>

## ⬇️ Download

You can download Plazma from the page below.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Want detailed information on supported versions?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot plugins, and Paper, Pufferfish, Purpur plugins.

[^2]: Below Microsoft Corporation.

[^3]: Disabling the chat reporting system ensures that chat is processed only on the server, preventing Mojang's chat tracking.

[^4]: The system mechanism temporarily pauses the game to operate.
