---
description: Descobreix com personalitzar el servidor.
---

# 📶 Millorar

La raó per la qual s'utilitza una plataforma de servidor modificada com Plazma en lloc de la plataforma oficial de servidors proporcionada per Mojang Studios és la gran capacitat de **personalització** que ofereix.

A continuació es mostren diverses maneres de personalitzar i utilitzar Plazma.

## Modificació de la configuració <a href="#id-1" id="id-1"></a>

La manera més bàsica de personalitzar Plazma és modificar la configuració.

Plazma ofereix una configuració potent que inclou mecanismes de joc i propietats de mobs.

Consulteu la pàgina següent per obtenir més informació sobre la configuració de Plazma.

{% content-ref url="../reference/configurations/" %}
[configuracions](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**En alguns paquets de dades]\(#user-content-fn-2)[^2] pot ser que no s'apliqui correctament en la primera aplicació.**

Per a aquests casos, es recomana reiniciar el servidor **2 vegades**.

{% endhint %}

Els paquets de dades poden resultar fàcilment danyats amb cada actualització del Minecraft.

Especialment si un paquet de dades es danya totalment, el servidor pot fallar,
per tant, és important fer proves completes abans d'actualitzar el servidor.

{% hint style="info" %}

**Després de l'ordre d'inici del servidor, podeu introduir `safeMode` per desactivar tots els paquets de dades i iniciar el servidor.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safemode)

{% endhint %}

Podeu comprovar els paquets de dades aplicats amb la comanda `/datapack list`.

***

## Optimització <a href="#id-4" id="id-4"></a>

Plazma té moltes correccions d'optimització aplicades. 또한, Plazma가 처음으로 시작되면 자동으로
구성을 최적화 하므로 [시작하기](./README.md) 설명서를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우,
아래 설명서를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

El proxy connecta els servidors entre ells i permet als jugadors moure's entre servidors sense cap tasca addicional,
i comunicar-se amb altres servidors.

Per obtenir informació sobre la configuració segura i correcta del proxy, consulteu la pàgina següent.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Seguretat <a href="#id-5" id="id-5"></a>

Amb el desenvolupament de mods, és fàcil trobar motors d'atac de vulnerabilitats en línia en Minecraft.

La majoria de les vulnerabilitats que es poden explotar en jocs estan bloquejades de manera predeterminada]\(#user-content-fn-4)[^4],
però no es bloqueja l'ús d'atacs de vulnerabilitats a través de carregadors de tercers.

Per tant, si el servidor és públic, és recomanable instal·lar complements anti-trampes per bloquejar l'ús de vulnerabilitats,
i configurar proxies, reinicis automàtics, còpies de seguretat, etc., per poder recuperar ràpidament el servidor si es cau.

### Configuració de permisos <a href="#id-5.1" id="id-5.1"></a>

Alguns comandaments d'administrador de plugins poden tenir vulnerabilitats si els permisos no estan configurats correctament.

S'ha de limitar els permisos dels usuaris normals utilitzant plugins de gestió de permisos com [LuckPerms](https://luckperms.net/).

### Blocatge X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray és una de les vulnerabilitats més fàcils d'utilitzar fins i tot en clients d'optimització bàsica.

Plazma ofereix una configuració per bloquejar X-Ray per defecte.

Consulteu la següent pàgina per obtenir informació i instruccions sobre com bloquejar X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Llista blanca <a href="#id-5.3" id="id-5.3"></a>

Si només voleu que alguns usuaris es connectin al servidor,
podeu utilitzar [Ngrok](./README.md#id-6.2) per utilitzar una adreça de servidor ofuscada]\(#user-content-fn-5)[^5] o,
configurar una llista blanca per evitar que altres jugadors es connectin al servidor.

Des de la consola del servidor, podeu permetre l'accés d'un jugador amb `/whitelist add <jugador>` o,
prohibir l'accés amb `/whitelist remove <jugador>`.

Per veure els jugadors amb accés permès, utilitzeu `/whitelist query`.

***

[^1]: O bé amb els add-ons de Minecraft: Bedrock Edition.

[^2]: Afegir noves entitats, etc.

[^3]: Normalment conegut com a "hacks".

[^4]: Si la configuració no està optimitzada, si Plazma és antic o si hi ha vulnerabilitats noves, pot ser que no estiguin bloquejades.

[^5]: Els jugadors es connecten al servidor a través del servidor de proxy Ngrok i cada vegada que es reinicia, l'adreça de Ngrok assignada canvia.
