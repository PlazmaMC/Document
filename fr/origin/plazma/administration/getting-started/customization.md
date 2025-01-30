---
description: Découvrez comment personnaliser le serveur.
---

# 🎨 Personnalisation

La raison pour laquelle nous utilisons une plateforme de serveur modifiée comme Plazma au lieu de la plateforme officielle fournie par Mojang Studios est la possibilité de personnalisation forte.

Voici plusieurs façons de personnaliser et utiliser Plazma.

## Modification de la configuration <a href="#id-1" id="id-1"></a>

La méthode la plus fondamentale pour personnaliser Plazma est de modifier la configuration.

Plazma offre des paramètres de configuration puissants, allant des mécanismes de jeu aux attributs des monstres.

Consultez la page suivante pour plus d'informations sur la configuration de Plazma.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## Utilisation de plugins <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma prend en charge tous les plugins basés sur Paper.**

Pour les plugins Spigot, certains peuvent ne pas fonctionner en raison des changements de mappage de Paper à partir de 1.20.5, mais la plupart des plugins basés sur Paper tels que Paper, Pufferfish et Purpur fonctionnent tous sur Plazma. Si un plugin ne fonctionne pas correctement, veuillez le signaler immédiatement [ici.](../diagnosis/plugins.md)

{% endhint %}

C'est la principale raison d'utiliser Plazma et le moyen le plus puissant de personnaliser Plazma.
L'écosystème puissant des plugins de Plazma permet de personnaliser facilement le serveur.

Il existe plusieurs façons de trouver et télécharger des plugins. Certains plugins sont téléchargés sur des services de dépôt publics, tandis que d'autres sont téléchargés sur GitHub ou leurs propres sites Web.

{% hint style="caution" %}

**Les plugins peuvent accéder directement au système !**

Avant d'appliquer un plugin, assurez-vous toujours de sa sécurité en utilisant des services tels que VirusTotal, ou téléchargez le plugin à partir de services fiables.

{% endhint %}

Il existe plusieurs services pour télécharger des plugins. Parmi eux, des services tels que [Forum SpigotMC](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hangar](https://hangar.papermc.io/) examinent les plugins avant de les distribuer pour garantir la sécurité.

### Application des plugins <a href="#id-2.1" id="id-2.1"></a>

Une fois le plugin téléchargé, il est temps de l'appliquer.

1. Les plugins sont au format `.jar` ou `Java Executable File`. Certains sont compressés, dans ce cas, extrayez le fichier contenant `bukkit`, `spigot` ou `paper` et utilisez le fichier `fat` s'il est présent.
2. Placez le fichier téléchargé dans le dossier `plugins` du serveur et redémarrez-le.
3. Lorsque Plazma démarre, de nouveaux messages s'afficheront dans la console, indiquant que les plugins ont été chargés correctement.
   Cela signifie que les plugins ont été chargés correctement par Plazma.
4. Même si les plugins ont été chargés correctement par Plazma, ils peuvent ne pas démarrer.
   La commande `/plugins` permet de lister les plugins actuellement chargés sur le serveur.
   Si le nom du plugin est en <mark style="background-color:red;">rouge</mark> et non en <mark style="background-color:green;">vert</mark>, cela signifie que le plugin n'a pas été chargé correctement.

Si un plugin n'a pas été chargé correctement, vous pouvez trouver des solutions sur la page suivante.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Utilisation de datapacks <a href="#id-3" id="id-3"></a>

Les datapacks sont une méthode de personnalisation fournie par Minecraft, similaire aux packs de ressources.

Les datapacks permettent de modifier certains aspects du jeu, comme ajouter de nouvelles entités et défis.

{% hint style="caution" %}

**Les datapacks peuvent endommager le monde !**

Certains datapacks défectueux peuvent endommager le monde de manière irréversible.

Il est donc recommandé de sauvegarder le monde avant d'appliquer un datapack.

{% endhint %}

Les datapacks peuvent être téléchargés depuis plusieurs services tels que [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/).

Une fois le datapack téléchargé, placez-le dans le dossier `datapacks` du monde du serveur.
Créez le dossier s'il n'existe pas.

{% hint style="warning" %}

**Certains [datapacks](#user-content-fn-2) peuvent ne pas s'appliquer correctement lors de la première utilisation.**

Il est recommandé de redémarrer le serveur **2 fois** en cas de problème d'application d'un datapack.

{% endhint %}

Les datapacks peuvent facilement être endommagés à chaque mise à jour de Minecraft.

En cas de corruption totale d'un datapack, il est important de tester suffisamment avant de mettre à jour le serveur pour éviter les crashes.

{% hint style="info" %}

**Après la commande de démarrage du serveur, saisissez `safeMode` pour désactiver tous les datapacks avant de redémarrer le serveur.**

[Consultez `Référence > Arguments` pour plus d'informations détaillées.](../reference/arguments.md)

{% endhint %}

Les datapacks appliqués peuvent être vérifiés en utilisant la commande `/datapack list`.

***

[^1]: Ou des add-ons pour Minecraft: Bedrock Edition.

[^2]: Ajout d'entités et plus encore.
