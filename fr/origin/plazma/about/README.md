---
description: Plazma는 어떤 서버 플랫폼인지 알아보세요.
---

# ❓ Qu'est-ce que Plazma?

- **Plazma** est une plateforme de serveur basée sur [Paper](https://github.com/PaperMC/Paper) qui ne prend que les avantages d'[Andromeda](https://github.com/EarendelArchived/Andromeda) et de [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Nous nous efforçons de fournir une stabilité élevée, des performances puissantes, des mises à jour rapides et une multitude de fonctionnalités.

## 📋 Objectifs de Plazma <a href="#id-1" id="id-1"></a>

- Nous nous efforçons de devenir une plateforme de serveur avec des mises à jour rapides et une grande stabilité.
- Nous nous efforçons de fournir une multitude de fonctionnalités et des performances puissantes, tout comme une plateforme de mod.
- Nous nous efforçons de créer une plateforme libre permettant de personnaliser même les correctifs de Vanilla.

## ⚙️ Caractéristiques principales <a href="#id-2" id="id-2"></a>

1. **Écosystème de plugins puissant**\
   Basé sur [Paper](https://github.com/PaperMC/Paper), la plupart des [plugins récents](#user-content-fn-1)[^1] disponibles sur Internet fonctionnent correctement.
2. **Optimisation sans configuration requise**\
   Tous les correctifs de [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sont inclus, avec des optimisations internes et des mods intégrés pour des performances optimales.
3. **Jeu personnalisable à volonté**\
   [Purpur](https://github.com/PurpurMC/Purpur) inclus dans Plazma permet de modifier les propriétés globales du jeu.
4. **Serveur sûr à jouer**\
   Avec [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) inclus, vous pouvez désactiver le nouveau système de signalement de discussion de Mojang[^2] introduit à partir de la version 1.19, et supprimer complètement le collecteur de données de diagnostic pour jouer sur un serveur sécurisé et sans suivi.
5. **Mises à jour les plus rapides**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) maintient les correctifs inclus dans Plazma toujours à jour, offrant ainsi les mises à jour les plus rapides parmi les plateformes de serveur basées sur Paper.
6. **Optimisation des fichiers de configuration par défaut**\
   Les fichiers de configuration par défaut sont optimisés, vous n'avez pas besoin de les optimiser vous-même.
7. **Fonctionnement multithread systématique**\
   En asynchronisant les mécanismes système non liés au jeu, nous réduisons les temps de latence pour optimiser le serveur.
8. **Blocage de l'utilisation d'espace inutile**\
   Nous fusionnons toutes les données similaires en une seule pour réduire la consommation de mémoire.

#### Vous voulez en savoir plus sur Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Cas d'utilisation <a href="#id-3" id="id-3"></a>

- **Plateforme gérant même les plugins complexes correctement**\
  Plazma est utilisé sur les serveurs du développeur [IPECTER](https://github.com/IPECTER). Malgré l'utilisation de plugins personnalisés fonctionnant avec NMS et réflexion, ainsi que de nombreux datapacks complexes et volumineux, il peut accueillir plus de 100 joueurs sans perte de performances.
- **Plateforme maintenant des performances rapides même sur des serveurs RPG**\
  Il a maintenu 100 joueurs sur un seul cluster sans baisse de TPS, et 250 joueurs au total sur 4 clusters ont pu jouer confortablement.
- **Plateforme illuminant les chunks/entités**\
  En passant de Purpur à Plazma sur un serveur de survie où des retards se produisaient lors du traitement des chunks et des entités, la plupart des retards ont pu être réduits.
- **Plateforme choisie par de nombreux streamers**\
  Utilisé comme un seau d'audience par de nombreux streamers populaires.

<figure><img src="https://camo.githubusercontent.com/22acffd515755c2cee2078a7697ff35351c5ec7148eb2806deedbe63df1c4ed7/68747470733a2f2f6273746174732e6f72672f7369676e6174757265732f7365727665722d696d706c656d656e746174696f6e2f506c617a6d612e737667" alt=""><figcaption><p>Tendance en temps réel des utilisateurs de Plazma</p></figcaption></figure>

## ⬇️ Téléchargement

Vous pouvez télécharger Plazma sur la page ci-dessous.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Vous voulez plus d'informations sur la prise en charge des versions?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Plugins Bukkit, CraftBukkit, Spigot et Paper, Pufferfish, Purpur.

[^2]: Propriété de Microsoft Corporation.

[^3]: En désactivant le système de signalement de discussion, le chat est traité uniquement sur le serveur, ce qui empêche le suivi des discussions par Mojang.

[^4]: Temps pendant lequel le jeu se fige pour permettre au mécanisme système de fonctionner.
