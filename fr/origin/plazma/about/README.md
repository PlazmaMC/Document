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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Mises à jour les plus rapides**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) maintient les correctifs inclus dans Plazma toujours à jour, offrant ainsi les mises à jour les plus rapides parmi les plateformes de serveur basées sur Paper.
6. **Optimisation des fichiers de configuration par défaut**\
   Les fichiers de configuration par défaut sont optimisés, vous n'avez pas besoin de les optimiser vous-même.
7. **Fonctionnement multithread systématique**\
   En asynchronisant les mécanismes système non liés au jeu, nous réduisons les temps de latence pour optimiser le serveur.
8. **Blocage de l'utilisation d'espace inutile**\
   Nous fusionnons toutes les données similaires en une seule pour réduire la consommation de mémoire.

## ✨ Cas d'utilisation <a href="#id-3" id="id-3"></a>

- **Une plateforme traitant également les plugins complexes correctement**\
  Utilisé sur le serveur du développeur [IPECTER](https://github.com/IPECTER), Plazma fonctionne avec NMS et la réflexion. Malgré l'application de nombreux plugins complexes et de vastes datapacks, il peut accueillir plus de 100 joueurs sans perte de performances.
- **Une plateforme maintenant des performances rapides même sur des serveurs RPG**\
  Il a maintenu 100 joueurs sur un seul cluster sans baisse de TPS, et jusqu'à 250 joueurs sur 4 clusters peuvent jouer confortablement sans problème.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **La plateforme choisie par de nombreux streamers**\
  Utilisée comme un seau pour l'engagement des spectateurs de nombreux streamers.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
