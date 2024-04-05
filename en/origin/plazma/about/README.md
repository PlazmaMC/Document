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
   Based on [Paper](https://github.com/PaperMC/Paper), most of the latest [plugins](#user-content-fn-1)[^1] available on the internet work seamlessly.
2. **Optimization without the need for settings**\
   Includes all patches from [Pufferfish](https://github.com/pufferfish-gg/Pufferfish), with some internal optimizations and modes for optimal performance.
3. **Customizable gameplay**\
   [Purpur](https://github.com/PurpurMC/Purpur) included in Plazma allows modification of various game attributes.
4. **Secure server gameplay**\
   Includes [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) to disable Mojang's [chat reporting system](#user-content-fn-3)[^3] introduced in 1.19, and completely removes diagnostic information collectors for a traceless, secure server gameplay.
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
  Plazma is being used on the server of developer [IPECTER](https://github.com/IPECTER). Utilizing NMS and reflection-based self-plugins, despite having complex and extensive data packs, it can handle over 100 players without performance degradation.
- **Platform maintaining fast performance on RPG servers**\
  Stably maintaining 100 players on a single cluster without TPS drops and allowing a total of 250 players to play comfortably across 4 clusters.
- **Platform that shines in chunks/entities**\
  By switching from Purpur to Plazma on a survival server where delays occurred in processing chunks and entities, most delays could be reduced.
- **Platform chosen by many streamers**\
  Being used as a bucket for many popular streamers' viewer participation.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Real-time Plazma User Trend</p></figcaption>
</figure>

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
