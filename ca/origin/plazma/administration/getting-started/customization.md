---
description: Descobreix com personalitzar el servidor.
---

# 🎨 Personalització

La raó per la qual s'utilitza una plataforma de servidor modificada com Plazma en lloc de la plataforma oficial de servidors proporcionada per Mojang Studios és la gran capacitat de **personalització** que ofereix.

A continuació es mostren diverses maneres de personalitzar i utilitzar Plazma.

## Modificació de la configuració <a href="#id-1" id="id-1"></a>

La manera més bàsica de personalitzar Plazma és modificar la configuració.

Plazma ofereix una configuració potent que inclou mecanismes de joc i propietats de mobs.

Consulteu la pàgina següent per obtenir més informació sobre la configuració de Plazma.

{% content-ref url="../reference/configurations/" %}
[configuracions](../reference/configurations/)
{% endcontent-ref %}

## Ús de plugins <a href="#id-2" id="id-2"></a>

{% hint style="èxit" %}

**Plazma dóna suport a tots els connectors basats en Paper de manera normal.**

En el cas dels connectors Spigot, a partir de la versió 1.20.5, a causa dels canvis de mapeig de Paper, alguns poden no funcionar correctament,
però la majoria dels connectors basats en Paper com Paper, Pufferfish i Purpur funcionen a Plazma sense problemes,
i si algun d'ells no funciona correctament, és un error de Plazma, si us plau, [informeu-nos immediatament.](../diagnosis/plugins.md)

{% endhint %}

És la raó principal per utilitzar Plazma i la forma més potent de personalitzar-lo.
L'ecosistema de connectors potent de Plazma permet personalitzar els servidors fàcilment.

Hi ha diverses maneres de trobar i descarregar connectors. Alguns connectors es pugen a serveis de magatzematge públics i altres es pugen a GitHub o a llocs web propis.

{% hint style="advertència" %}

**Els connectors poden accedir directament al sistema!**

Utilitzeu serveis com VirusTotal per assegurar-vos sempre que els connectors són segurs abans d'aplicar-los,
i descarregueu els connectors de serveis fiables.

{% endhint %}

Hi ha diversos serveis per descarregar connectors. D'entre ells, serveis com [Fòrum de SpigotMC](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) revisen els connectors abans de ser pujats i eliminen els que no són segurs, assegurant la distribució només de connectors segurs.

### Aplicació de connectors <a href="#id-2.1" id="id-2.1"></a>

Un cop descarregats els connectors, ara és el moment d'aplicar-los.

1. Els connectors són fitxers `.jar` o fitxers executables de Java.\
   Alguns connectors poden estar comprimits, en aquest cas,
   descomprimeix-los i si el nom conté `bukkit`, `spigot` o `paper`,
   utilitza el fitxer que conté `fat`.
2. Poseu els fitxers descarregats a la carpeta `plugins` del servidor i reinicieu-lo (o inicieu-lo de nou).
3. Quan s'inicia Plazma, es mostrarà informació nova a la consola.
   Això significa que Plazma ha carregat els connectors correctament.
4. Tot i que Plazma hagi carregat els connectors correctament, poden no iniciar-se.
   Amb la comanda `/plugins` podeu veure els connectors carregats al servidor.
   Si el nom del connector no és
   vermell <mark style="background-color:red;">sino verd</mark>, vol dir que s'ha carregat correctament.

Si els connectors no s'han carregat correctament, podeu trobar solucions a la següent pàgina.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Ús de paquets de dades <a href="#id-3" id="id-3"></a>

Els paquets de dades són una forma de personalitzar el Minecraft similar als [paquets de recursos](#user-content-fn-1)[^1].

Amb els paquets de dades podeu afegir noves entitats i reptes al joc i modificar parts del joc.

{% hint style="advertència" %}

**Els paquets de dades poden danyar el món!**

Alguns paquets de dades defectuosos poden danyar el món i això no es pot desfer.

Per tant, és recomanable fer una còpia de seguretat del món abans d'aplicar paquets de dades.

{% endhint %}

Els paquets de dades es poden descarregar de diversos serveis com [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) i altres.

Un cop descarregats els paquets de dades, els podeu aplicar posant-los a la carpeta `datapacks` del món del servidor.
Si la carpeta no existeix, podeu crear-la i afegir-hi els paquets de dades.

{% hint style="warning" %}

**Alguns [paquets de dades](#user-content-fn-2)[^2] poden no aplicar-se correctament la primera vegada.**

Per a aquests casos, es recomana reiniciar el servidor **2 vegades**.

{% endhint %}

Els paquets de dades poden resultar fàcilment danyats amb cada actualització del Minecraft.

Especialment si un paquet de dades es danya totalment, el servidor pot fallar,
per tant, és important fer proves completes abans d'actualitzar el servidor.

{% hint style="info" %}

**Després de l'ordre d'inici del servidor, podeu introduir `safeMode` per desactivar tots els paquets de dades i iniciar el servidor.**

[Consulteu `Referència > Arguments` per obtenir més informació.](../reference/arguments.md)

{% endhint %}

Podeu comprovar els paquets de dades aplicats amb la comanda `/datapack list`.

***

[^1]: O bé amb els add-ons de Minecraft: Bedrock Edition.

[^2]: Afegir noves entitats, etc.
