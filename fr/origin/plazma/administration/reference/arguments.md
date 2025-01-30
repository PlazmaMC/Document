---
description: Découvrez les arguments de démarrage et les propriétés du système.
---

# 🎛️ Arguments de démarrage et propriétés

Le début de l'acquisition et les propriétés du système sont des valeurs ajoutées à la commande utilisée pour l'exécution de Plazma, qui ont un impact global sur le fonctionnement de Plazma.

Selon la **argument de démarrage** et les **propriétés système** ajoutés à l'emplacement de la commande[^2], ils seront divisés.

***

## Propriétés du système <a href="#id-1" id="id-1"></a>

Les propriétés du système sont des valeurs traitées par la JVM avant l'initialisation de Plazma et placées avant `-jar`.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Mode d'emploi <a href="#id-1.1" id="id-1.1"></a>

Les propriétés du système sont ajoutées en tant qu'arguments de commande Java entre `java` et `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indique que cet argument n'est pas intégré à la JVM mais est un argument personnalisé pour Plazma,

Si aucune valeur n'est saisie pour les propriétés, la valeur sera fixée à [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Liste complète des propriétés du système <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Met à jour le format des panneaux obsolètes utilisés.

#### `debug.entities`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Active les journaux de débogage des informations sur les entités.

#### `debug.rewriteForIDE`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive la révision NMS pour permettre une récupération correcte des informations de débogage dans l'IDE et remappe automatiquement les informations de version interne.

#### `disable.watchdog`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive le système d'alerte Watchdog de Spigot.

#### `letMeReload`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive le message de confirmation de la commande `/reload`.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Si vous êtes un développeur de plugin et devez mettre à jour un plugin, utilisez le hotswap au lieu de la commande `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive les plugins utilisant le système d'entrée/sortie standard.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Affiche un avertissement en cas de détection de formatage obsolète dans les composants de chat.

#### `Paper.bypassHostCheck`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive la vérification de motif du serveur lorsqu'un joueur se connecte.

#### `Paper.debugDynamicMissingKeys`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Active les journaux de débogage pour les clés manquantes dans les objets NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Active les journaux de débogage pour les profils de crâne incorrects.

Cela enregistre tous les blocs de crâne incorrects dans le monde avec leur position.

#### `Paper.disableChannelLimit`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive le système de priorisation des classes de plugin.

Utile en cas de problème avec les ombres des plugins.

#### `Paper.disableFlushConsolidate`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive le système de consolidation des envois Netty.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Valeur par défaut**: `750`

Divise les entités en paquets multiples pour l'envoi si elles dépassent cette valeur.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Valeur par défaut**: `8192`

Définit la taille maximale des paquets que le serveur peut recevoir à la fois.

#### `Paper.ignoreJavaVersion`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Désactive la vérification de version de Java.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Cela peut entraîner des dommages permanents aux fichiers du monde et causer des dysfonctionnements dans le jeu.

Tout problème résultant de cette action est de la responsabilité de l'utilisateur, Plamza ne fournissant aucun support à cet égard.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Valeur par défaut**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Valeur par défaut**: `80`

Définit la longueur maximale des lignes des panneaux.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Valeur par défaut**: `(version du monde) + 1`

Définit la version des informations de mise à jour du monde à initialiser en premier.

Utile pour les mises à jour massives de chunks mais rarement utilisé autrement.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Valeur par défaut**: `True`

Active le traitement des commentaires YAML.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Valeur par défaut**: `30`

Expulse un joueur s'il n'a reçu aucune donnée pendant le temps spécifié (en secondes).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Ignore les commentaires des propriétés du serveur.

#### `Paper.debug-sync-loads`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Active les journaux de débogage de la création synchrone des chunks.

#### `Paper.enable-sync-chunk-writes`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Active le système de création synchrone des chunks de base de Minecraft.

Cela entraîne un ralentissement considérable car chaque chunk est sauvegardé séquentiellement.

#### `Paper.explicit-flush`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Active le vidage explicite des canaux réseau.

#### `Paper.strict-thread-checks`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Journalise toujours les erreurs qui ne se produisent pas sur le thread principal.

#### `Paper.tickList-warn-on-excessive-delay`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Affiche un avertissement en cas de délai excessif des tâches planifiées.

#### `Paperclip.patchOnly`

- **Type**: `Boolean`
- **Valeur par défaut**: `False`

Applique uniquement les correctifs sans démarrer le serveur lorsque vous utilisez le fichier exécutable par défaut.

#### `Plazma.aggressiveOptimize`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`
- **Collision**: `Plazma.disableConfigOptimization`

Optimisez la configuration initiale de manière plus forte.

L'activation rendra le serveur plus rapide et plus sécurisé, mais peut avoir un impact majeur sur le gameplay.

#### `Plazma.disableConfigOptimization`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`
- **Collision**: `Plazma.aggressiveOptimize`

Ne pas optimiser la configuration initiale.

Cela utilisera la configuration de base de Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`

Désactivez le branding Plazma et utilisez la favicon de serveur par défaut en mode basic.

#### `Plazma.useVanillaConfiguration`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`
- **Collision**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Cela peut avoir un impact significatif sur la sécurité et les performances du serveur.

Tous les problèmes découlant de l'utilisation de cette propriété relèvent de la responsabilité de l'administrateur du serveur.
{% endhint %}

Fournit la configuration initiale avec les valeurs par défaut fournies par Mojang.

Cela désactive tous les correctifs de vulnérabilité appliqués par Paper.

Les correctifs de vulnérabilité peuvent être réactivés dans la configuration Paper ou Plazma.

#### `Plazma.vanillaize`

- **Type**: `Boolean`
- **Valeur par défaut**: `true`
- **Collision**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Configure la configuration initiale pour être plus proche du mode basic.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Propriété obsolète <a href="#id-1.3" id="id-1.3"></a>

Les propriétés système ci-dessous sont obsolètes.

#### `timings.bypassMax`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`
- **Obsolète**: Depuis la suppression complète de Timings de Plazma

Détermine si une valeur peut dépasser la limite maximale pouvant être envoyée à l'API Timings d'Aikar.

Même si cela est fait, si aucune exception n'est gérée dans l'API, une limitation de débit s'applique.

***

## Argument de démarrage <a href="#id-2" id="id-2"></a>

L'argument de démarrage est saisi après `-jar *.jar` pour initialiser Plazma et est traité conjointement.

### Mode d'emploi <a href="#id-2.1" id="id-2.1"></a>

Les propriétés système sont saisies en tant qu'arguments de commande de programme après `-jar *.jar`.

Par exemple, si vous souhaitez appliquer l'argument de démarrage `nogui`,\
entrez comme suit pour que Plazma traite l'argument `nogui` pendant l'initialisation.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argument de démarrage complet <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Valeur par défaut**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Valeur par défaut**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Valeur par défaut**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Démarre le serveur en mode démo.

#### `eraseCache`

Supprime les fichiers de cache restants après la mise à niveau du monde.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Affiche tous les arguments de démarrage de Plazma et leur description.

#### `initSettings`

Crée uniquement les fichiers de configuration et arrête le serveur.

#### `jfrProfile`

Active le profilage JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Valeur par défaut**: `(propriété du serveur)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Désactive le panneau d'interface graphique.

#### `nojline`

Désactive JLine et utilise la console de base.

#### `mode en ligne`

- **Alias**: `o`
- **Valeur par défaut**: `(propriété du serveur)`

Choisit si les joueurs doivent être vérifiés par le serveur d'authentification Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paramètres-paper`

- **Alias**: `papier`
- **Valeur par défaut**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Définit l'emplacement des fichiers de configuration PaperSpigot désactivés.

Il est utilisé pour migrer les anciennes configurations vers de nouveaux fichiers de configuration, mais n'est plus utilisé par la suite.

#### `répertoire-paramètres-paper`

- **Alias**: `papier-dir`
- **Valeur par défaut**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `répertoire-paramètres-plazma`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Valeur par défaut**: `plugins`

Définit l'emplacement du dossier des plugins.

#### `paramètres-pufferfish`

- **Alias**: `pufferfish`
- **Valeur par défaut**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `paramètres-purpur`

- **Alias**: `purpur`
- **Valeur par défaut**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `mode sécurisé`

Démarre le serveur en mode totalement vanilla.

#### `ip-serveur`

- **Alias**: `h`, `hôte`
- **Valeur par défaut**: `(propriété du serveur)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `port-serveur`

- **Alias**: `p`, `port`
- **Valeur par défaut**: `(propriété du serveur)`

Définit le port du serveur.

#### `nom-serveur`

- **Valeur par défaut**: `Un serveur Plazma`

Définit le nom du serveur.

#### `paramètres-spigot`

- **Alias**: `S`
- **Valeur par défaut**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Affiche la version de Plazma.

#### `répertoire-monde`

- **Alias**: `W`, `univers`, `conteneur-monde`
- **Valeur par défaut**: `(dossier du serveur)`

Définit l'emplacement où les fichiers de monde sont stockés.

#### `nom-monde`

- **Alias**: `w`, `monde`
- **Valeur par défaut**: `(propriété du serveur)`

Définit le nom du fichier de monde.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Le traitement des arguments varie en fonction de l'emplacement auquel ils sont ajoutés.

[^3]: Par exemple, pour activer `Plazma.iKnowWhatIAmDoing` à `true`, il suffit de saisir `-DPlazma.iKnowWhatIAmDoing` au lieu de `-DPlazma.iKnowWhatIAmDoing=true`, cela fonctionnera de la même manière.

[^4]: Par exemple, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Détecteur d'événements.

[^6]: Détecteur d'événements.

[^7]: Client.

[^8]: Signal indiquant une connexion réussie au serveur, similaire aux battements de cœur.

[^9]: Avec la fonction d'expulsion AFK de Purpur, même les joueurs absents peuvent être expulsés.

[^10]: Système d'écriture de chunk synchronisé, Sync Chunk Write System.

[^11]: `ATTENTION! Plazma peut causer des problèmes inattendus, assurez-vous de bien le tester avant de l'utiliser sur un serveur public.`

[^12]: La `optimisation du monde` fonctionne sur le même principe en jeu.

[^13]: Les administrateurs de `niveau 2` ou supérieur sont exclus.

[^14]: Protocole Internet, IP.
