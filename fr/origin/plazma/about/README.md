---
description: Découvrez ce qu'est Plazma en tant que plateforme de serveur.
---

# ❓ Qu'est-ce que Plazma?

- **Plazma** est une plateforme de serveur basée sur [Paper](https://github.com/PaperMC/Paper) qui ne prend que les avantages d'[Andromeda](https://github.com/EarendelArchived/Andromeda) et de [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Nous nous efforçons de fournir une stabilité élevée, des performances puissantes, des mises à jour rapides et une multitude de fonctionnalités.

## 📋 Objectifs de Plazma <a href="#id-1" id="id-1"></a>

- Nous nous efforçons de devenir une plateforme de serveur avec des mises à jour rapides et une grande stabilité.
- Nous nous efforçons de fournir une multitude de fonctionnalités et des performances puissantes, tout comme une plateforme de mod.
- Nous nous efforçons de créer une plateforme libre permettant de personnaliser même les correctifs de Vanilla.

## ⚙️ Caractéristiques principales <a href="#id-2" id="id-2"></a>

1. **Un écosystème de plugins puissant**\
   Basé sur [Paper](https://github.com/PaperMC/Paper),
   la plupart des [derniers plugins](#user-content-fn-1)[^1] disponibles sur Internet fonctionnent correctement.
2. **Optimisation sans configuration requise**\
   Tous les correctifs de [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sont inclus,
   offrant des performances optimales grâce à des optimisations internes et des mods intégrés.
3. **Personnalisation du jeu selon vos préférences**\
   [Purpur](https://github.com/PurpurMC/Purpur) inclus dans Plazma permet de modifier
   les propriétés globales du jeu à votre guise.
4. **Un serveur jouant en toute sécurité**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) est inclus depuis la version 1.19 pour désactiver le
   système de signalement de chat de [Mojang](#user-content-fn-2)[^2] et supprimer complètement le collecteur de diagnostics, permettant de jouer sur un serveur sécurisé sans suivi.
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

- **Une plateforme traitant également les plugins complexes correctement**\
  Utilisé sur le serveur du développeur [IPECTER](https://github.com/IPECTER), Plazma fonctionne avec NMS et la réflexion. Malgré l'application de nombreux plugins complexes et de vastes datapacks, il peut accueillir plus de 100 joueurs sans perte de performances.
- **Une plateforme maintenant des performances rapides même sur des serveurs RPG**\
  Il a maintenu 100 joueurs sur un seul cluster sans baisse de TPS, et jusqu'à 250 joueurs sur 4 clusters peuvent jouer confortablement sans problème.
- **Une plateforme qui brille dans les chunks/entités**\
  En remplaçant Purpur par Plazma sur un serveur de survie où des retards se produisaient lors du traitement des chunks et des entités, la plupart des retards ont été réduits.
- **Une plateforme choisie par de nombreux streamers**\
  Utilisé comme serveur de visionnage par de nombreux spectateurs de streamers populaires.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Évolution en temps réel de l'utilisation de Plazma</p></figcaption>
</figure>

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
