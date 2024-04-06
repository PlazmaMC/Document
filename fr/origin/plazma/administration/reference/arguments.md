---
description: Découvrez les arguments de démarrage et les propriétés du système.
---

# 🎛️ Arguments de démarrage et propriétés

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

Selon la **argument de démarrage** et les **propriétés système** ajoutés à l'emplacement de la commande[^2], ils seront divisés.

***

## Propriétés du système <a href="#id-1" id="id-1"></a>

Les propriétés du système sont des valeurs traitées par la JVM avant l'initialisation de Plazma et placées avant `-jar`.

{% hint style="warning" %}

**La modification des propriétés du système peut modifier le fonctionnement de Plazma et de JVM, ce qui peut avoir un impact majeur sur le jeu !**

Si vous ne savez pas exactement quel rôle chaque propriété du système joue, **ne l'utilisez jamais !**

{% endhint %}

### Mode d'emploi <a href="#id-1.1" id="id-1.1"></a>

Les propriétés du système sont ajoutées en tant qu'arguments de commande Java entre `java` et `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indique que cet argument n'est pas intégré à la JVM mais est un argument personnalisé pour Plazma,

Si aucune valeur n'est saisie pour les propriétés, la valeur sera fixée à [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**La plateforme serveur de la série Paperweight utilise un point (`.`) dans le nom des propriétés pour distinguer les propriétés de chaque plateforme.**

Dans certains terminaux tels que Windows Powershell, ces arguments peuvent ne pas être autorisés, il est donc nécessaire d'ajouter `"` aux extrémités des arguments[^4].

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

**La commande `/reload` est très instable, donc tous les problèmes survenant après l'utilisation de `/reload` sont de la responsabilité de l'utilisateur.**

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

Désactive la limite de 128 canaux de plugin appliqués par joueur[^5].

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

**Cela peut permettre à JVM d'essayer d'accéder à un code inexistant !**

Cela peut entraîner des dommages permanents aux fichiers du monde et causer des dysfonctionnements dans le jeu.

Tout problème résultant de cette action est de la responsabilité de l'utilisateur, Plamza ne fournissant aucun support à cet égard.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Type**: `Integer`
- **Valeur par défaut**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

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

En général, le [jeu](#user-content-fn-7)[^7] continue d'envoyer un [signal de battement de cœur](#user-content-fn-8)[^8] au serveur, donc en cas de non-réponse du jeu, il est considéré comme en conflit et le joueur est expulsé sans être banni, mais le serveur cesse de traiter le joueur.

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

**Cette propriété sera déplacée vers les arguments de démarrage après la version 1.20.5.**

{% endhint %}

Applique une optimisation de configuration plus stricte au démarrage initial.

L'activation rend le serveur plus rapide et plus sûr, mais peut bloquer certaines fonctionnalités ou avoir un impact majeur sur le jeu.

#### `Plazma.iKnowWhatIAmDoing`

- **Type**: `Boolean`
- **Valeur par défaut**: `false`

Supprime le [message d'avertissement](#user-content-fn-11)[^11] affiché lors de l'initialisation de Plazma.

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

**Cet argument a été abandonné après la version 1.19.4.**

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
