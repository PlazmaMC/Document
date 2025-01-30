---
description: Learn how to customize the server.
---

# 🎨 Customization

The reason for using a modified server platform like Plazma instead of the official server platform provided by Mojang Studios is that it allows for powerful **customization**.

Below are various ways to customize and utilize Plazma.

## Configuration Modification <a href="#id-1" id="id-1"></a>

The most basic way to customize Plazma is to modify the configuration.

Plazma provides powerful configuration settings ranging from game mechanics to mob properties.

Refer to the following page for explanations on Plazma's configurations.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## Plugin Usage <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma supports all Paper-based plugins.**

For Spigot plugins, some may not work due to mapping changes from Paper 1.20.5,
but most plugins based on Paper such as Paper, Pufferfish, and Purpur work on Plazma.
If they do not work properly, it is a Plazma error, so please [report it immediately.](../diagnosis/plugins.md)

{% endhint %}

This is the main reason for using Plazma and the most powerful way to customize Plazma.
Plazma's powerful plugin ecosystem makes it easy to customize servers.

There are several ways to find and download plugins. Some plugins are uploaded to public repository services, while others are uploaded to GitHub or their own sites.

{% hint style="caution" %}

**Plugins can directly access the system!**

Always check if plugins are safe using services like VirusTotal before applying them,
or download plugins from trusted services.

{% endhint %}

There are various services for downloading plugins. Among them, services like [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) review plugins before uploading, ensuring only safe plugins are distributed.

### Applying Plugins <a href="#id-2.1" id="id-2.1"></a>

Once you have downloaded the plugins, it's time to apply them.

1. Plugins are in `.jar` or `Java Executable File` format.\
   Some plugins may be compressed, in which case,
   extract the compressed file. If the name contains `bukkit`, `spigot`, or `paper`,
   use the file that includes `fat`.
2. Put the downloaded files in the server folder's `plugins` folder and (re)start the server.
3. When Plazma starts, new content will be displayed on the console.
   This means Plazma has successfully loaded the plugins.
4. Even if Plazma has successfully loaded the plugins, they may not start.
   Use the `/plugins` command to load the currently installed plugins on the server.
   If the installed plugin names are not <mark style="background-color:red;">red</mark> but <mark style="background-color:green;">green</mark>, the plugins have loaded correctly.

If the plugins have not loaded correctly, you can find solutions on the following page.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Using Data Packs <a href="#id-3" id="id-3"></a>

Data packs are a way to customize Minecraft similar to resource packs.

With data packs, you can modify parts of the game like adding new creatures and challenges.

{% hint style="caution" %}

**Data packs can damage worlds!**

Some faulty data packs can damage worlds irreversibly.

Therefore, it is recommended to back up your world before applying data packs.

{% endhint %}

Data packs can be downloaded from various services like [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs).

Once downloaded, you can apply data packs by placing them in the `datapacks` folder in the server's world folder.
If the folder does not exist, create it before adding data packs.

{% hint style="warning" %}

**Some data packs may not apply correctly initially.**

In such cases, it is recommended to restart the server **twice**.

{% endhint %}

Data packs can easily get corrupted with each Minecraft update.

Especially if a data pack is completely corrupted, it can crash the server,
so thorough testing before updating the server is crucial.

{% hint style="info" %}

**You can start the server with all data packs disabled by adding `safeMode` after the server start command.**

[Refer to `References > Arguments` for more details.](../reference/arguments.md)

{% endhint %}

You can check the applied data packs with the `/datapack list` command.

***

[^1]: Or with Minecraft: Bedrock Edition's add-ons.

[^2]: Adding new creatures and more.
