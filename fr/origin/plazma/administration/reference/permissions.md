---
description: Découvrez les autorisations de Plazma.
---

# 🛡️ Autorisations

Les autorisations sont des outils de sécurité simples qui définissent la portée d'interaction des joueurs sur le serveur.

Pour bien utiliser et modifier les autorisations, vous devez utiliser des plugins tels que [LuckPerms](https://luckperms.net).

***

## Comprendre le système d'autorisations de base <a href="#id-1" id="id-1"></a>

Minecraft propose des groupes de permissions de gestion de base.

Vous pouvez définir les autorisations des **opérateurs** et des blocs de commandes, et les modifier dans les [propriétés du serveur](configurations/property.md).

0. **Joueur**\
   Groupe de permissions généralement attribué à tous les joueurs.
1. **Médiateur**\
   Peut ignorer la protection du spawn.
2. **Administrateur de monde**\
   Peut utiliser toutes les commandes et blocs de commande liés à la gestion du monde.\
   Groupe de permissions appliqué par défaut aux datapacks et blocs de commande.
3. **Administrateur**\
   Peut utiliser toutes les commandes liées à la gestion des joueurs.
4. **Super administrateur**\
   Peut utiliser toutes les commandes, y compris celles liées à la gestion du serveur.\
   Groupe de permissions appliqué par défaut à la console et aux opérateurs.

***

## Définir des autorisations <a href="#id-2" id="id-2"></a>

***

## Autorisations globales <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Clé namespace)`

- **Par défaut**: `Aucun`

Permet aux joueurs de monter sur une entité en s'accroupissant et en interagissant avec elle.

En montant sur une entité, vous pouvez contrôler son déplacement avec les touches de déplacement et sauter ou voler avec la touche de saut.

La [clé namespace](#user-content-fn-2)[^2] de l'entité est saisie dans `(Clé namespace)`.

{% hint style="info" %}

\*\*Le `(Entity) > montable` ne fonctionne que si activé dans les **[configurations mondiales de Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Clé en espace de noms)`

- **Par défaut**: `Aucun`

Permet au joueur d'utiliser les compétences spéciales de l'entité lorsqu'il est monté sur celle-ci.

Toutes les entités n'ont pas accès aux compétences spéciales. Consultez ci-dessous toutes les compétences spéciales disponibles.

{% hint style="info" %}

**Avez-vous des idées pour des compétences spéciales?**

Veuillez publier vos idées sur [Plazma Discord](https://plazmamc.org/discord) ou [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Voir toutes les compétences spéciales disponibles actuellement</summary>

- **`creeper`**\
  Explose lorsqu'on appuie sur la touche `sauter`.\
  Si le joueur a la permission `allow.powered.creeper`, il peut charger en maintenant la touche `sauter`.
- **`dauphin`**\
  Charge en appuyant sur la touche `sauter`.
- **`phantom`**\
  Tire des flammes en appuyant sur la touche `sauter`.
- **`wither`**\
  Lance la tête de Wither en interagissant.

</details>

{% hint style="info" %}

\*\*Le `(Entity) > montable` ne fonctionne que si activé dans les **[configurations mondiales de Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/credits (Joueur)`](commands.md#credits).

En ajoutant `.autre` après le nom de la permission, permet de l'utiliser pour d'autres joueurs.

#### `bukkit.command.demo`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/demo (Joueur)`](commands.md#demo).

En ajoutant `.autre` après le nom de la permission, permet de l'utiliser pour d'autres joueurs.

#### `bukkit.command.ping`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/ping (Joueur)`](commands.md#ping).

En ajoutant `.autre` après le nom de la permission, permet de l'utiliser pour d'autres joueurs.

#### `bukkit.command.ram`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/rambar (Joueur)`](commands.md#rambar).

En ajoutant `.autre` après le nom de la permission, permet de l'utiliser pour d'autres joueurs.

#### `bukkit.command.restart`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/tpsbar (Joueur)`](commands.md#tpsbar).

En ajoutant `.autre` après le nom de la permission, permet de l'utiliser pour d'autres joueurs.

#### `bukkit.command.timings`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Cette commande est désormais désactivée.**

Consultez [Spark](https://spark.lucko.me/docs/Command-Usage) pour des commandes similaires.

{% endhint %}

#### `bukkit.command.uptime`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(Mode de jeu)`

- **Fourni par défaut**: `Administrateur de monde`

Autorise l'utilisation de la commande `/gamemode (Mode de jeu) (Joueur)`.

En ajoutant `.autre` après le nom de la permission, permet de l'utiliser pour d'autres joueurs.

#### `paper.antixray.bypass`

- **Par défaut**: `Aucun`

Si le blocage X-Ray est activé,
les joueurs avec cette permission ne seront pas soumis à l'obscurcissement des blocs X-Ray.

Cela améliore les performances des deux côtés.

> Consultez la page ci-dessous pour plus d'informations sur la configuration X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Par défaut**: `Aucun`

{% hint style="warning" %}

Cette permission sera renommée en `plazma.bypass.watchdog` dans la version 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Par défaut**: `Aucun`

Permet l'utilisation des [codes couleur](https://minecraft.wiki/w/Formatting_codes#Color_codes) sur l'enclume.

{% hint style="info" %}

**Vous devez activer `anvil > allow-colors` dans les **[configurations mondiales de Purpur](configurations/purpur/world.md)** pour que cela fonctionne.**

{% endhint %}

#### `purpur.anvil.format`

- **Par défaut**: `Aucun`

Permet l'utilisation des [codes de style](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) sur l'enclume.

{% hint style="info" %}

**Vous devez activer `anvil > allow-colors` dans les **[configurations mondiales de Purpur](configurations/purpur/world.md)** pour que cela fonctionne.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Par défaut**: `Aucun`

Permet l'utilisation des [balises MiniMessage](https://docs.advntr.dev/minimessage/format.html) sur l'enclume.

{% hint style="info" %}

**Vous devez activer `anvil > allow-minimessages` dans les **[configurations mondiales de Purpur](configurations/purpur/world.md)** pour que cela fonctionne.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Par défaut**: `Aucun`

Permet de désactiver l'`italique` en utilisant le code de style `&r` sur l'enclume.

{% hint style="info" %}

**Vous devez activer `anvil > allow-colors` dans les **[configurations mondiales de Purpur](configurations/purpur/world.md)** pour que cela fonctionne.**

{% endhint %}

#### `purpur.book.color.sign`

- **Par défaut**: `Aucun`

Applique les [codes de style](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) lorsque le joueur signe un livre.

#### `purpur.bypassIdleKick`

- **Par défaut**: `Aucun`

Exclut le joueur de l'expulsion pour inactivité.

#### `purpur.debug.f3n`

- **Fourni par défaut**: `Administrateur de monde`

Autorise le joueur à changer de mode de jeu en appuyant sur `F3 + N`.

Cela ne fonctionne que si le joueur a la permission pour ce mode de jeu.

#### `purpur.drop.spawners`

- **Par défaut**: `Aucun`

Lorsque vous minez un bloc de spawner avec l'objet configuré, il fait tomber le bloc de spawner.

{% hint style="info" %}

**Vous devez activer `gameplay-mechanics > silk-touch` dans les **[configurations mondiales de Purpur](configurations/purpur/world.md)** pour que cela fonctionne.**

{% endhint %}

#### `purpur.enderchest.rows.(NombreTexte)`

- **Par défaut**: `Aucun`

Modifie la taille du coffre de l'End.

Vous pouvez saisir `one`, `two`, `three`, `four`, `five`, `six` pour `(NombreTexte)`.

{% hint style="info" %}

**Vous devez activer `ender_chest > six-rows` et `ender_chest > use-permissions-for-rows` dans les **[configurations mondiales de Purpur](configurations/purpur/world.md)** pour que cela fonctionne.**

{% endhint %}

#### `purpur.inventory_totem`

- **Par défaut**: `Aucun`

Permet au totem d'immortalité de fonctionner même s'il est dans l'inventaire.

{% hint style="info" %}

**Activez `totem-of-undying-works-in-inventory` dans les **[**configurations de monde Purpur**](configurations/purpur/world.md)** pour qu'il fonctionne.**

{% endhint %}

#### `purpur.joinFullServer`

- **Par défaut**: `Aucun`

Permet au joueur d'ignorer la limite de joueurs connectés.

#### `purpur.mending_shift_click`

- **Par défaut**: `Aucun`

Permet au joueur de réparer un objet en le tenant et en **s'accroupissant et en interagissant**.

{% hint style="info" %}

**Activez `shift-right-click-repairs-mending-points` dans les **[**configurations de monde Purpur**](configurations/purpur/world.md)** pour qu'il fonctionne.**

{% endhint %}

#### `purpur.place.spawners`

- **Par défaut**: `Aucun`

Permet au joueur d'installer des générateurs.

{% hint style="info" %}

**Vous devez activer `gameplay-mechanics > silk-touch` dans les **[configurations mondiales de Purpur](configurations/purpur/world.md)** pour que cela fonctionne.**

{% endhint %}

#### `purpur.portal.instant`

- **Par défaut**: `Aucun`

Permet au joueur de se téléporter immédiatement lorsqu'il utilise un portail de l'End.

#### `purpur.sign.color`

- **Par défaut**: `Aucun`

Permet d'utiliser des codes de couleur sur les panneaux [codes de couleur](https://minecraft.wiki/w/Formatting_codes#Color_codes).

{% hint style="info" %}

**Activez `sign > allow-colors` dans les **[**configurations de monde Purpur**](configurations/purpur/world.md)** pour qu'il fonctionne.**

{% endhint %}

#### `purpur.sign.magic`

- **Par défaut**: `Aucun`

Permet d'utiliser le code d'illusion `(&o)` sur les panneaux.

{% hint style="info" %}

**Activez `sign > allow-colors` dans les **[**configurations de monde Purpur**](configurations/purpur/world.md)** pour qu'il fonctionne.**

{% endhint %}

#### `purpur.sign.style`

- **Par défaut**: `Aucun`

Permet d'utiliser les codes de style sur les panneaux [à l'exception de `(&o)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% hint style="info" %}

**Activez `sign > allow-colors` dans les **[**configurations de monde Purpur**](configurations/purpur/world.md)** pour qu'il fonctionne.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Par défaut**: `Aucun`

Permet au joueur d'empêcher l'explosion du TNT en interagissant avec des ciseaux.

{% hint style="info" %}

**`defuse-tnt-change` doit être supérieur ou égal à `0.0` dans les **[**configurations de monde Purpur**](configurations/purpur/world.md)** pour qu'il fonctionne.**

{% endhint %}

### Permission prévue

#### `plazma.bypass.ncr-require`

- **Par défaut**: `Aucun`

Permet au joueur de se connecter même sans avoir installé le mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**Activez `no-chat-reports > require-install` dans les **[**configurations de monde Plazma**](configurations/plazma/world.md)** pour qu'il fonctionne.**

{% endhint %}

***

[^1]: Opérateur.

[^2]: Par exemple : `ender_dragon`
