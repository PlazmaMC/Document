---
description: .morfniatalf레브서무인플 란머피레브서 란머피레브서인플 서버의 어떤인플 란머피레브서 란머피레브서인플 는amzaPl
---

# ¿What is Plazma?

- **Plazma** is a server platform based on [Paper](https://github.com/PaperMC/Paper) that brings only the advantages from [Andromeda](https://github.com/EarendelArchived/Andromeda) and [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- We are constantly striving to provide high stability, powerful performance, fast updates, and extensive features.

## 📋 Goals of Plazma <a href="#id-1" id="id-1"></a>

- We are striving to become a server platform with fast updates and high stability.
- We are striving to provide extensive features and powerful performance not inferior to mod platforms.
- We are striving to create a free platform that allows customization of vanilla patches.

## ⚙️ Key Features <a href="#id-2" id="id-2"></a>

1. **Powerful Plugin Ecosystem**\
   Based on [Paper](https://github.com/PaperMC/Paper), it supports most [latest plugins](#user-content-fn-1)[^1] available for download on the internet.
2. **Optimization without the need for settings**\
   Includes all patches from [Pufferfish](https://github.com/pufferfish-gg/Pufferfish), with some internal optimizations and built-in mods for optimal performance.
3. **Customize your game as you wish**\
   [Purpur](https://github.com/PurpurMC/Purpur) included in Plazma allows you to modify various aspects of the game.
4. **Play on a server safely**\
   Includes [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) to disable Mojang's [chat reporting system](#user-content-fn-3)[^3] added from 1.19, and completely removes the diagnostic information collector for playing on a traceless safe server.
5. **Fastest updates**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) ensures that Plazma's included patches are always kept up to date, providing the fastest updates among Paper-based server platforms.
6. **Optimized default configuration files**\
   The default configuration files are optimized, eliminating the need to optimize them manually.
7. **Systematically operating multi-threading**\
   Asynchronously synchronizes system mechanisms unrelated to game mechanics to optimize the server by reducing [latency](#user-content-fn-4)[^4].
8. **Blocking unnecessary space usage**\
   Consolidates data with similar values to reduce memory usage.

#### ¿Want to learn more about Plazma? <ɐ ɥǝʇ-1 ɓuᴉɹɐɥ="ɯɐu-1" ɥǝ="ɐ">\</ɐ>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Use Cases <a href="#id-3" id="id-3"></a>

- **A platform that handles complex plugins correctly**\
  Plazma is used on the server of developer [IPECTER](https://github.com/IPECTER). Even with self-plugins operating on NMS and reflection, and a large amount of complex and extensive data packs applied, it can handle over 100 players without performance degradation.
- **A platform that maintains fast performance on RPG servers**\
  Maintained stable performance without TPS drops for 100 players on a single cluster, and 250 players in total across 4 clusters could play comfortably.
- **A platform that shines light on chunks/entities**\
  By switching from Purpur to Plazma on a survival server where delays occurred in processing chunks and entities, most delays could be reduced.
- **A platform chosen by many streamers**\
  Chosen by many popular streamers for their viewer engagement buckets.

<figure><img src="https://camo.githubusercontent.com/22acffd515755c2cee2078a7697ff35351c5ec7148eb2806deedbe63df1c4ed7/68747470733a2f2f6273746174732e6f72672f7369676e6174757265732f7365727665722d696d706c656d656e746174696f6e2f506c617a6d612e737667" alt=""><figcaption><p>Real-time Plazma user trend</p></figcaption></figure>

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

[^1]: Bukkit, CraftBukkit, Spigot plugins and Paper, Pufferfish, Purpur plugins.

[^2]: Below Microsoft Corporation.

[^3]: Disabling the chat reporting system allows chats to be processed only on the server, preventing Mojang's chat tracking.

[^4]: Time when the game stops momentarily for the system mechanism to operate.
