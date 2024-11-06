---
description: Découvrez les autorisations de Plazma.
---

# 🛡️ Autorisations

Les autorisations sont des outils de sécurité simples qui définissent la portée d'interaction des joueurs sur le serveur.

Pour bien utiliser et modifier les autorisations, vous devez utiliser des plugins tels que [LuckPerms](https://luckperms.net).

***

## Comprendre le système d'autorisations de base <a href="#id-1" id="id-1"></a>

Minecraft propose des groupes de permissions de gestion de base.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Joueur**\
   Groupe de permissions généralement attribué à tous les joueurs.
2. **Médiateur**\
   Peut ignorer la protection du spawn.
3. **Administrateur de monde**\
   Peut utiliser toutes les commandes et blocs de commande liés à la gestion du monde.\
   Groupe de permissions appliqué par défaut aux datapacks et blocs de commande.
4. **Administrateur**\
   Peut utiliser toutes les commandes liées à la gestion des joueurs.
5. **Super administrateur**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Clé en espace de noms)`

- **Par défaut**: `Aucun`

Permet au joueur d'utiliser les compétences spéciales de l'entité lorsqu'il est monté sur celle-ci.

Toutes les entités n'ont pas accès aux compétences spéciales. Consultez ci-dessous toutes les compétences spéciales disponibles.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Cela améliore les performances des deux côtés.

> Consultez la page ci-dessous pour plus d'informations sur la configuration X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Par défaut**: `Aucun`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Par défaut**: `Aucun`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Par défaut**: `Aucun`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Par défaut**: `Aucun`

Permet l'utilisation des [balises MiniMessage](https://docs.advntr.dev/minimessage/format.html) sur l'enclume.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Par défaut**: `Aucun`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Par défaut**: `Aucun`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NombreTexte)`

- **Par défaut**: `Aucun`

Modifie la taille du coffre de l'End.

Vous pouvez saisir `one`, `two`, `three`, `four`, `five`, `six` pour `(NombreTexte)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Par défaut**: `Aucun`

Permet au totem d'immortalité de fonctionner même s'il est dans l'inventaire.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Par défaut**: `Aucun`

Permet au joueur d'ignorer la limite de joueurs connectés.

#### `purpur.mending_shift_click`

- **Par défaut**: `Aucun`

Permet au joueur de réparer un objet en le tenant et en **s'accroupissant et en interagissant**.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Par défaut**: `Aucun`

Permet au joueur d'installer des générateurs.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Par défaut**: `Aucun`

Permet au joueur de se téléporter immédiatement lorsqu'il utilise un portail de l'End.

#### `purpur.sign.color`

- **Par défaut**: `Aucun`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Par défaut**: `Aucun`

Permet d'utiliser le code d'illusion `(&o)` sur les panneaux.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Par défaut**: `Aucun`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Par défaut**: `Aucun`

Permet au joueur d'empêcher l'explosion du TNT en interagissant avec des ciseaux.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Permission prévue

#### `plazma.bypass.ncr-require`

- **Par défaut**: `Aucun`

Permet au joueur de se connecter même sans avoir installé le mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Opérateur.

[^2]: Par exemple : `ender_dragon`
