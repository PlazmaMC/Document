---
description: Learn how to customize the server.
---

# 📶 Developing

The reason for using a modified server platform like Plazma instead of the official server platform provided by Mojang Studios is that it allows for powerful **customization**.

Below are various ways to customize and utilize Plazma.

## Configuration Modification <a href="#id-1" id="id-1"></a>

The most basic way to customize Plazma is to modify its configuration.

Plazma provides powerful configuration settings ranging from game mechanics to mob properties.

Refer to the following page for an explanation of Plazma's configurations.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

## Plugin Usage <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma supports all Paper-based plugins.**

For Spigot plugins, some may not work due to mapping changes from Paper 1.20.5,
However, most plugins based on Paper such as Paper, Pufferfish, and Purpur
work on Plazma as well. If a plugin does not work properly, it is an error of Plazma, so please [report it immediately.](../diagnosis/plugins.md)

{% endhint %}

This is the main reason for using Plazma and the most powerful way to customize Plazma.
Plazma's powerful plugin ecosystem makes it easy to customize the server.

There are several ways to find and download plugins. Some plugins
upload plugins to public repository services, while others upload to GitHub or their own
websites.

{% hint style="caution" %}

**Plugins can directly access the system!**

Always check if the plugin is safe using services like VirusTotal before applying it,
or download the plugin from a trusted service.

{% endhint %}

There are various services used to download plugins. Among them, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/), etc. review plugins before they are uploaded to ensure that only safe plugins are distributed.

### Applying Plugins <a href="#id-2.1" id="id-2.1"></a>

Once you have downloaded the plugins, it's time to apply them.

1. Plugins are in `.jar` or `Java Executable File` format.\
   Some plugins are compressed, in which case
   unzip the file and if the name includes `bukkit`, `spigot`, or `paper`,
   use the `fat` file if there is a file with `fat`.
2. Place the downloaded file in the `plugins` folder of the server directory and (re)start the server.
3. When Plazma starts, new content will be output on the console.
   This means that Plazma has successfully loaded the plugins.
4. Even if Plazma has successfully loaded the plugins, they may not start.
   You can load the currently loaded plugins on the server using the `/plugins` command.
   If the installed plugin names are not in <mark style="background-color:red;">red</mark> but
   in <mark style="background-color:green;">green</mark>, the plugins have loaded correctly.

If the plugins have not loaded correctly, you can find solutions on the following page.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Using Datapacks <a href="#id-3" id="id-3"></a>

Datapacks are a way to customize Minecraft provided similarly to
[Resource Packs](#user-content-fn-1).

With datapacks, you can modify parts of the game such as adding new creature groups and challenges.

{% hint style="caution" %}

**Datapacks can damage worlds!**

Some faulty datapacks can damage worlds irreversibly.

Therefore, it is recommended to back up the world before applying datapacks.

{% endhint %}

Datapacks can be downloaded from various services such as [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/), etc.

Once downloaded, you can apply datapacks by placing them in the `datapacks` folder of the server's world directory.
If the folder does not exist, create it and add the datapacks.

{% hint style="warning" %}

**In some data packs, initial application may not be applied correctly when first applied.**

In such cases, it is recommended to restart the server **twice**.

{% endhint %}

Datapacks can easily be corrupted when Minecraft updates its version.

Especially when datapacks are completely corrupted, the server may crash,
so it is important to thoroughly test before updating the server.

{% hint style="info" %}

**After the server start command, you can enter `safeMode` to disable all datapacks and start the server.**

[Please refer to `Reference > Arguments and Properties` for more details.](../reference/arguments.md#safemode)

{% endhint %}

You can check the applied datapacks using the `/datapack list` command.

***

## Optimization <a href="#id-4" id="id-4"></a>

Plazma has many optimization patches applied. Also, when Plazma starts for the first time,
it automatically optimizes the configuration, so if you follow the [Getting Started](./README.md) guide, there is no need for additional optimization.

However, if many players connect or if the world is vast,
you can perform additional optimization tasks through the following guide.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxies connect servers to each other and allow players to move servers without additional tasks or communicate with other servers.

Refer to the below page for information on safe and proper proxy settings.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Safety <a href="#id-5" id="id-5"></a>

As Minecraft mods develop, it is easy to find [vulnerability attack engines](#user-content-fn-3) online.

Most vulnerabilities that can be executed in normal games are [basically blocked](#user-content-fn-4), but attacking vulnerabilities through third-party loaders is not blocked.

Therefore, if the server is public, it is recommended to install anti-cheat plugins to block vulnerability usage and configure proxies, automatic restarts, backups, etc., to quickly recover the server if it goes down.

### Permission Settings <a href="#id-5.1" id="id-5.1"></a>

Some plugin administrator commands may have vulnerabilities if permissions are not properly set.

It is recommended to use permission management plugins like [LuckPerms](https://luckperms.net/) to restrict the permissions of regular users.

### X-Ray Blocking <a href="#id-5.2" id="id-5.2"></a>

X-Ray is one of the vulnerabilities that can easily be used even in basic optimization clients.

Plazma provides a configuration that can block X-Ray by default.

Please refer to the below page for X-Ray blocking methods and explanations.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

If only some users can connect to the server, it is recommended to use [Ngrok](./README.md#id-6.2) to use an obfuscated server address or set up a whitelist to prevent other players from connecting.

Allow player access by using `/whitelist add <player>` in the server console or prohibit player access again with `/whitelist remove <player>`.

Use `/whitelist query` to see players who are allowed access.

***

[^1]: Or Minecraft: Bedrock Edition addons.

[^2]: Adding new creature groups, etc.

[^3]: Commonly referred to as "hacks".

[^4]: If the configuration is not optimized, or Plazma is old, or new vulnerabilities are not blocked, players may not be blocked when connecting to the server.

[^5]: When players connect to the server, it is through the Ngrok proxy server, and the Ngrok address issued with each restart will be different.
