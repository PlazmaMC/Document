---
description: Learn how to userize the server.
---

# 🎨 Userization

Using a modified server platform like Plazma instead of the official server platform provided by Mojang Studios
is because the most significant reason is the ability for **customization**.

Below are various ways to customize and utilize Plazma.

## Configuration Modification <a href="#id-1" id="id-1"></a>

The most basic way to customize Plazma is to modify the configuration.

Plazma provides powerful configuration settings from game mechanics to mob attributes.

Refer to the following page for explanations about Plazma's configurations.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## Plugin Usage <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma be supportin' all plugins based on Paper.**

For Spigot plugins, there may be some issues due to mappin' changes from Paper 1.20.5 onwards,
but most plugins based on Paper like Paper, Pufferfish, and Purpur be workin' on Plazma as well,
and if they don't be workin' properly, it be an error of Plazma, so please [report it immediately.](../diagnosis/plugins.md)

{% endhint %}

Bein' a major reason for usin' Plazma and the most powerful way to customize Plazma.
Plazma's powerful plugin ecosystem makes it easy to customize servers.

There be various ways to find and download plugins. Some plugins be uploaded to public repository services, while others be uploaded to GitHub or their own
sites.

{% hint style="caution" %}

**Plugins can directly access the system!**

Always make sure to check if a plugin be safe by usin' services like VirusTotal before applyin' it,
or download plugins from trusted services.

{% endhint %}

There be several services used to download plugins. Among them, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) be services that go through a review process before plugins be uploaded, makin' sure only safe plugins be distributed.

### Applyin' Plugins <a href="#id-2.1" id="id-2.1"></a>

Once ye have downloaded a plugin, it be time to apply it.

1. Plugins be in `.jar` or `Java Executable File` format.\
   Some plugins may be compressed, in which case
   ye should unzip them and if there be files with `bukkit`, `spigot`, or `paper` in their names,
   use the `fat` file if there be one.
2. Put the downloaded file in the `plugins` folder of the server directory and restart the server.
3. When Plazma starts, new content will be output to the console.
   This means that Plazma has properly loaded the plugins.
4. Even if Plazma has loaded the plugins properly, they may not have started.
   Ye can use the `/plugins` command to load the currently installed plugins on the server.
   If the plugin names be not in <mark style="background-color:red;">red</mark>
   but in <mark style="background-color:green;">green</mark>, then the plugins have been loaded properly.

If the plugins haven't loaded properly, ye can find solutions on the followin' page.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Usin' Data Packs <a href="#id-3" id="id-3"></a>

Data Packs be a way to customize Minecraft similar to
[Resource Packs](#user-content-fn-1)[^1].

With Data Packs, ye can modify parts of the game like addin' new creatures and challenges.

{% hint style="caution" %}

**Data Packs can damage worlds!**

Some faulty Data Packs can damage worlds irreversibly.

Therefore, it be recommended to backup the world before applyin' Data Packs.

{% endhint %}

Data Packs can be downloaded from various services like [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) and others.

Once ye have downloaded a Data Pack, ye can apply it by puttin' it in the `datapacks` folder of the server's world directory.
If the folder doesn't exist, ye can create it and add the Data Pack.

{% hint style="warning" %}

**Some [Data Packs](#user-content-fn-2)[^2] may not apply properly on the first try.**

In such cases, it be recommended to restart the server **2 times**.

{% endhint %}

Data Packs can easily get damaged with each Minecraft update.

Especially when Data Packs be completely damaged, the server may crash,
so it be important to thoroughly test before updatin' the server.

{% hint style="info" %}

**After the server startin' command, ye can enter `safeMode` to disable all Data Packs before startin' the server.**

[Refer to 'Arguments' in the `Reference` for more details.](../reference/arguments.md)

{% endhint %}

Ye can check the applied Data Packs with the `/datapack list` command.

***

[^1]: Or in Minecraft: Bedrock Edition's add-ons.

[^2]: Such as addin' new creatures.
