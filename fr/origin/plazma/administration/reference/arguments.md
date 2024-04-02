---
description: Découvrez les arguments de démarrage et les propriétés du système.
---

# 🎛️ Arguments de démarrage et propriétés

Les variables de démarrage et les propriétés du système sont des valeurs ajoutées aux [commandes utilisées](#user-content-fn-1)[^1] pour l'exécution de Plazma, permettant de modifier des valeurs qui ne peuvent être modifiées après l'exécution de Plazma.

Selon l'**emplacement des ajouts aux commandes**,[^2] ils sont divisés en **arguments de démarrage** et **propriétés du système**.

***

## Propriétés du système <a href="#id-1" id="id-1"></a>

Les propriétés du système sont des valeurs traitées par la JVM avant l'initialisation de Plazma et placées avant `-jar`.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### Mode d'emploi <a href="#id-1.1" id="id-1.1"></a>

Les propriétés du système sont ajoutées en tant qu'arguments de commande Java entre `java` et `-jar`.

Par exemple, pour appliquer la propriété du système `Plazma.dummyProperty`, saisir comme suit ajoutera la valeur `37` à la propriété suivante pour l'initialisation de Plazma.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indique que cet argument n'est pas intégré à la JVM mais est un argument personnalisé pour Plazma,

et si aucune valeur n'est spécifiée, la valeur est fixée à [`true`.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

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

Désactive la limite de 128 canaux de plugin par joueur[^5].

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

- **Type**: `Integer`
- **Valeur par défaut**: `750`

Divise les entités en paquets multiples pour l'envoi si elles dépassent cette valeur.

#### `Paper.filterThreshold`

- **Type**: `Integer`
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

- **Type**: `Integer`
- **Valeur par défaut**: `64`

Définit la limite de caractères pour les noms de canaux de plugin.

#### `Paper.maxSignLength`

- **Type**: `Integer`
- **Valeur par défaut**: `80`

Définit la longueur maximale des lignes des panneaux.

#### `Paper.minPrecachedDatafixVersion`

- **Type**: `Integer`
- **Valeur par défaut**: `(version du monde) + 1`

Définit la version des informations de mise à jour du monde à initialiser en premier.

Utile pour les mises à jour massives de chunks mais rarement utilisé autrement.

#### `Paper.parseYamlCommentsByDefault`

- **Type**: `Boolean`
- **Valeur par défaut**: `True`

Active le traitement des commentaires YAML.

#### `Paper.playerConnection.keepAlive`

- **Type**: `Integer`
- **Valeur par défaut**: `30`

Expulse un joueur s'il n'a reçu aucune donnée pendant le temps spécifié (en secondes).

Normalement, le jeu[^7] envoie continuellement des [signaux de battement](#user-content-fn-8)[^8] au serveur, donc le joueur n'est pas expulsé, mais s'il ne reçoit aucune réponse du jeu, il est considéré comme planté et est expulsé.

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

{% hint style="warning" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Applique une optimisation de configuration plus stricte au démarrage initial.

L'activation rend le serveur plus rapide et plus sûr, mais peut bloquer certaines fonctionnalités ou avoir un impact majeur sur le jeu.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`

Supprime l'avertissement[^11] affiché lors de l'initialisation de Plazma.

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

Définit le nom et l'emplacement du [fichier de configuration Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Valeur par défaut**: `commands.yml`

Définit le nom et l'emplacement du [fichier de configuration des commandes Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Valeur par défaut**: `server.properties`

Définit le nom et l'emplacement du fichier de [propriétés du serveur](../reference/configurations/property.md).

#### `demo`

Démarre le serveur en mode démo.

#### `eraseCache`

Supprime les fichiers de cache restants après la mise à niveau du monde.

#### `forceUpgrade`

Met à niveau de force le monde en ignorant la version. [^12]

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

Définit le nombre maximum de [joueurs](#user-content-fn-14).

#### `nogui`

Désactive le panneau d'interface graphique.

#### `nojline`

Désactive JLine et utilise la console de base.

#### `mode en ligne`

- **Alias**: `o`
- **Valeur par défaut**: `(propriété du serveur)`

Choisit si les joueurs doivent être vérifiés par le serveur d'authentification Mojang.

**Si vous n'utilisez pas Velocity ou d'autres proxies, vous risquez des sanctions pour violation de l'[EULA](../getting-started/README.md#id-5).**

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

Définit le nom et l'emplacement du dossier contenant les [fichiers de configuration Paper](../reference/configurations/paper/README.md).

#### `répertoire-paramètres-plazma`

- **Alias**: `plazma-dir`

Définit le nom et l'emplacement du dossier contenant les [fichiers de configuration Plazma](../reference/configurations/plazma/README.md).

#### `plugins`

- **Alias**: `p`
- **Valeur par défaut**: `plugins`

Définit l'emplacement du dossier des plugins.

#### `paramètres-pufferfish`

- **Alias**: `pufferfish`
- **Valeur par défaut**: `pufferfish.yml`

Définit le nom et l'emplacement du [fichier de configuration Pufferfish](../reference/configurations/pufferfish.md).

#### `paramètres-purpur`

- **Alias**: `purpur`
- **Valeur par défaut**: `purpur.yml`

Définit le nom et l'emplacement du [fichier de configuration Purpur](../reference/configurations/purpur/README.md).

#### `mode sécurisé`

Démarre le serveur en mode totalement vanilla.

#### `ip-serveur`

- **Alias**: `h`, `hôte`
- **Valeur par défaut**: `(propriété du serveur)`

Définit le nom d'hôte du serveur ou l'adresse [protocole Internet](#user-content-fn-13)[^13].

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

Définit le nom et l'emplacement du [fichier de configuration Spigot](../reference/configurations/spigot.md).

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

[^13]: Protocole Internet, IP.

[^14]: Les administrateurs de `niveau 2` ou supérieur sont exclus.
