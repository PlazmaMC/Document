---
description: Learn how to customize the server.
---

# 📶 발전하기

The reason for using a modified server platform like Plazma instead of the official server platform provided by Mojang Studios is that it allows for powerful **customization**.

Below are various ways to customize and utilize Plazma.

## Configuration Modification <a href="#id-1" id="id-1"></a>

The most basic way to customize Plazma is to modify the configuration.

Plazma provides powerful configuration settings ranging from game mechanics to mob properties.

Refer to the following page for explanations on Plazma's configurations.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**For some data packs, it may not be applied correctly when first applied.**

In such cases, it is recommended to restart the server **twice**.

{% endhint %}

Data packs can easily get corrupted with each Minecraft update.

Especially if a data pack is completely corrupted, it can crash the server,
so thorough testing before updating the server is crucial.

{% hint style="info" %}

**You can start the server with all data packs disabled by adding `safeMode` after the server start command.**

Refer to `Reference > Arguments and Properties` for more information.

{% endhint %}

You can check the applied data packs with the `/datapack list` command.

***

## Optimization <a href="#id-4" id="id-4"></a>

Plazma has many optimization patches applied. Additionally, when Plazma starts for the first time, it automatically optimizes the configuration, so if you follow the [Getting Started](./README.md) guide, there is no need for additional optimization work.

However, if many players connect or if the size of the world is vast, you can perform additional optimization work following the guide below.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxies connect servers together, allowing players to move between servers or communicate with other servers without additional effort.

For information on safe and proper proxy settings, refer to the page below.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Safety <a href="#id-5" id="id-5"></a>

As Minecraft mods advance, vulnerabilities can easily be exploited online.

Most vulnerabilities that are executable in regular games are [blocked by default](#user-content-fn-4), but attacking vulnerabilities through third-party loaders is not blocked.

Therefore, if the server is public, it is recommended to install anti-cheat plugins to block vulnerability exploits, configure proxies, automatic restarts, backups, etc., to quickly recover the server if it goes down.

### Permission Settings <a href="#id-5.1" id="id-5.1"></a>

Some plugin admin commands may have vulnerabilities if permissions are not properly set.

Using permission management plugins like [LuckPerms](https://luckperms.net/) to restrict regular user permissions is recommended.

### X-Ray Blocking <a href="#id-5.2" id="id-5.2"></a>

X-Ray is one of the vulnerabilities easily accessible even in basic optimization clients.

Plazma provides configurations to block X-Ray by default.

Refer to the page below for X-Ray blocking methods and explanations.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

If only certain users can access the server, it is recommended to use [Ngrok](./README.md#id-6.2) to use an obfuscated server address or set up a whitelist to prevent other players from accessing the server.

Allow player access through `/whitelist add <player>` in the server console, or prohibit player access again with `/whitelist remove <player>`.

Use `/whitelist query` to see players allowed access.

***

[^1]: Or with Minecraft: Bedrock Edition's add-ons.

[^2]: Adding new creatures and more.

[^3]: Commonly referred to as 'hacks'.

[^4]: If the configuration is not optimized, if Plazma is outdated, or if newly discovered vulnerabilities are present, they may not be blocked.

[^5]: Players connect to the server through the Ngrok proxy server, and the Ngrok address issued with each restart will change.
