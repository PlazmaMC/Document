---
description: Découvrez comment créer un serveur avec Plazma.
---

# 👟 Commencer

Pour utiliser Plazma de manière stable, le système doit répondre aux exigences suivantes.

|                    | Minimum | Recommandé |
| :----------------: | ------: | ---------: |
|    Architecture    |     x64 |          - |
|         RAM        |    8 Go |      16 Go |
| Espace de stockage |    1 Go |       8 Go |
|         JRE        |      17 |         21 |

Pour une modification de fichier fluide, il est recommandé d'installer un éditeur tel que [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Installation de JRE

Comme son nom l'indique, Minecraft: **"Java"** Edition est développé en Java et nécessite JRE[^1] pour s'exécuter.

Plazma étant basé sur la plateforme officielle de serveurs de Mojang Studios, l'installation de JRE est également nécessaire pour utiliser Plazma.

### 1.1 Vérification de la présence de JRE

Pour vérifier si JRE est installé sur le système, saisissez [`cmd /k java --version`](#user-content-fn-4)[^4] dans la fenêtre d'exécution et exécutez.

Si vous obtenez la sortie suivante, passez à l'étape 2.

{% code title="Sortie correcte" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Si la sortie est différente ou ressemble à ce qui suit, cela signifie que JRE est absent ou trop ancien, vous devez alors effectuer l'étape 1.2.

{% code title="JRE non installé" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE trop ancien" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Installation de JRE

Dans ce guide, nous utilisons Azul Zulu comme l'une des versions de JRE[^5].

Une fois l'installation terminée, refaites l'étape 1.1 pour vérifier que l'installation s'est correctement déroulée.

{% tabs %}

{% tab title="Windows" %}

1. Téléchargez d'abord **JDK 21** en format `.msi` depuis [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Exécutez l'assistant d'installation téléchargé et cliquez sur `Suivant`.
3. **Activez `Set JAVA_HOME variable` dans le menu affiché au centre gauche de la fenêtre**, puis cliquez sur `Suivant`.
4. Cliquez sur `Installer` pour terminer l'installation de JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) téléchargez et exécutez l'assistant d'installation en forme de fichier `.dmg` pour installer JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Ajoutez d'abord le référentiel Azul Zulu à APT en exécutant la commande suivante dans le terminal.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Ensuite, installez JRE en exécutant la commande suivante dans le terminal.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Vous pouvez installer JRE en entrant la commande suivante.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Téléchargement de Plazma

Plazma propose différents types de fichiers exécutables.

{% hint style="warning" %}

**Dans la plupart des cas, utilisez `Reobf Paperclip`.**

Les informations ci-dessous sont destinées aux développeurs ou à ceux qui s'intéressent aux caractéristiques de chaque type.\
Si vous êtes un utilisateur standard, vous pouvez passer directement à l'étape 3 sans problème.

{% endhint %}

<details>

<summary>En savoir plus</summary>

Le nom du fichier exécutable est défini comme suit : `plazma-(version du gestionnaire)-1.20.4-R0.1-SNAPSHOT-(type de mappage).jar`.

- **Type de mappage**\
  Le mappage est une sorte de carte reliant le code réel de Minecraft au code obfusqué.
  - **Reobf**\
    Reobfuscation, également appelé mappage Spigot, est largement utilisé dans la plupart des plugins NMS.\
    Son utilisation sera interrompue à partir de la version 1.20.5.
  - **Mojmap**\
    Mappage de Mojang, c'est le mappage de Minecraft vanilla.
- **Version du gestionnaire**\
  Le gestionnaire de version est essentiel pour le fonctionnement du serveur, car il fournit les bibliothèques nécessaires et patche les fichiers du serveur.
  - **Paperclip**\
    Développé par l'équipe PaperMC pour Paper et d'autres plates-formes dérivées, il télécharge les bibliothèques et applique les correctifs au serveur.
  - **Bundler**\
    Le gestionnaire de version de Minecraft vanilla.

</details>

***

## 3. Création du script de démarrage

Pour démarrer Plazma facilement et redémarrer automatiquement le serveur, vous devez créer un [script de démarrage](#user-content-fn-6)[^6].

Vous pouvez créer le script de démarrage via [Flags.sh](https://flags.sh). En entrant simplement la [mémoire à utiliser](#user-content-fn-8)[^8] pour Plazma, la commande sera automatiquement optimisée.

Vous pouvez télécharger le script de démarrage en bas à gauche.\
**Assurez-vous que le script téléchargé correspond à votre système d'exploitation.**

***

## 4. Nettoyage des fichiers

Déplacez maintenant le script de démarrage téléchargé et Plazma dans un nouveau dossier.

{% hint style="warning" %}

**Le nom du dossier doit être sans espace et en anglais.**

Sinon, Plazma ou JRE risquent de ne pas fonctionner correctement.

{% endhint %}

Exécutez maintenant le script de démarrage. Pour Windows, <mark style="background-color:orange;">Dans la fenêtre de sélection d'autorisation de pare-feu, assurez-vous de sélectionner **Autoriser**</mark>.

***

## 5. Acceptation de l'EULA

Après avoir exécuté le script de démarrage une fois, un fichier `eula.txt` sera créé dans le dossier.

L'EULA[^9] est un contrat de licence que vous devez accepter en utilisant les services de [Mojang Studios](#user-content-fn-10)[^10].

Si vous refusez l'EULA, vous ne pourrez pas démarrer le serveur et pourrez être sanctionné en cas de violation, comme la suspension de votre compte, etc. [Voir les sanctions](#user-content-fn-11)[^11].

Pour accepter l'EULA, modifiez `eula=false` en `eula=true` dans le fichier `eula.txt` et enregistrez les modifications.

***

## 6. Autorisation d'accès externe (Windows)

Les systèmes d'exploitation modernes bloquent généralement l'accès externe par défaut à des fins de sécurité à l'aide du **pare-feu** et du **routeur**.

Pour Windows, puisque vous avez autorisé le pare-feu à l'étape 3, il vous suffit de configurer le transfert de port.

{% hint style="info" %}

**Ce guide suppose que vous utilisez le système d'exploitation Windows et un routeur compatible avec [UPnP](#user-content-fn-12)[^12].**

Si votre routeur ne prend pas en charge l'UPnP, vous devrez rechercher comment configurer le transfert de port spécifiquement pour votre routeur.

Vous pouvez également utiliser [Ngrok](https://ngrok.com/) pour générer une adresse temporaire.
{% endhint %}

{% hint style="warning" %}

**Pour les systèmes d'exploitation de type UNIX (Linux ou macOS, etc.), les méthodes de configuration du pare-feu varient selon les services, il est donc nécessaire de rechercher les informations directement.**

{% endhint %}

### 6.1 Vérification de la nécessité du transfert de port

Saisissez la commande suivante dans la fenêtre d'exécution et exécutez-la.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Si la sortie est `True`, vous avez terminé ici, sinon vous devrez configurer le transfert de port.

### 6.2 Connexion au serveur

{% tabs %}

{% tab title="Connexion externe" %}

Si le renvoi de port n'est pas nécessaire ou si vous l'avez déjà configuré avec succès, vous pouvez maintenant vous connecter au serveur.

L'adresse utilisée pour se connecter au serveur peut être vérifiée [ici](https://ip.pe.kr/)

{% endtab %}

{% tab title="Tentative de renvoi de port avec UPnP" %}

Dans le fichier `purpur.yml` du serveur, activez `network.upnp-port-forwarding` sur `true`.

Ensuite, après avoir redémarré le serveur, Plazma tentera automatiquement de rediriger les ports.

Le succès du UPnP est déterminé par le message affiché dans la console, qui sera affiché comme `[UPnP] (message)`.

| Message                               | Signification                           |
| ------------------------------------- | --------------------------------------- |
| `Port (port) ouvert avec succès`      | Redirection de port réussie.            |
| `Le port (port) est déjà ouvert`      | Un autre service utilise déjà ce port.  |
| `Échec de l'ouverture du port (port)` | Échec de la redirection de port.        |
| `Le service est indisponible`         | Le routeur ne prend pas en charge UPnP. |

Lorsque le serveur est arrêté, Plazma ferme automatiquement le port.

{% endtab %}

{% tab title="Création d'une adresse temporaire avec Ngrok" %}

L'utilisation de Ngrok est utile pour des tests temporaires, des sessions de jeu en groupe ou jouer avec des amis.

1. Téléchargez le fichier ZIP `Windows (64-bit)` depuis le site [Ngrok](https://ngrok.com/download).
2. Placez le Ngrok téléchargé dans le dossier du serveur.
3. Sur le [tableau de bord Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), créez un [jeton d'authentification](#user-content-fn-13)[^13].
4. Exécutez la commande affichée dans la `Ligne de commande` du dossier du serveur.
5. Ajoutez `start /b ngrok tcp --region jp 25565` en haut du script d'exécution, et `taskkill /f /t /im ngrok.exe` en bas.
6. Dans la console, l'adresse `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` devient l'adresse du serveur `0.tcp.jp.ngrok.io:12345`.
7. Vous pouvez maintenant vous connecter depuis l'extérieur via cette adresse.

{% endtab %}

{% tab title="Connexion locale" %}

Si vous souhaitez vous connecter au serveur en local, vous pouvez utiliser l'adresse `IPv4` affichée en exécutant `cmd /k ipconfig` dans la fenêtre d'exécution.

Par exemple, lorsque vous obtenez la sortie suivante après l'exécution de la commande,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

En essayant de vous connecter avec l'adresse IPv4 `192.168.3.7` affichée ici, vous pouvez accéder au serveur en local.

Si le serveur et le jeu sont exécutés sur le même PC, vous pouvez vous connecter via `localhost`.

{% endtab %}
{% endtabs %}

## 7. Phase de développement

Après avoir démarré avec succès le serveur et qu'il fonctionne correctement, il est temps de le personnaliser.

Découvrez comment personnaliser le serveur en suivant le guide ci-dessous.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Environnement d'exécution Java, environnement d'exécution Java.

[^2]: Paper, la base de Plazma, est basé sur Spigot, qui est la plateforme officielle du serveur.

[^3]: Touches Windows + R

[^4]: Pour Linux, utilisez `java --version` dans le terminal.

[^5]: JRE est un projet open source avec plusieurs variantes comme les plateformes de serveurs Minecraft.

[^6]: Il est généralement appelé **launcher**.

[^7]: Activer l'option "Redémarrage automatique" permet au serveur de redémarrer automatiquement. Vous pouvez arrêter en entrant `Control + C`.

[^8]: Il n'est pas recommandé de dépasser la moitié de la capacité du système.

    Par exemple, si la capacité totale de mémoire du système est de 8 Go, il n'est pas recommandé de dépasser 4 Go.

[^9]: Contrat de licence utilisateur final, contrat de licence utilisateur final. Consultez le site [Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines) pour plus d'informations.

[^10]: Microsoft Corporation.

[^11]: En vertu de l'article 32, paragraphe 1, point 9 de la loi sur la promotion de l'industrie du jeu en Corée, **Korea Microsoft Corporation** peut intenter une action en justice.

[^12]: Universal Plug & Play. Le Purpur inclus dans Plazma communique automatiquement avec le routeur via cette technologie, ouvrant les ports uniquement lorsque le serveur est en cours d'exécution, donc il n'est pas nécessaire de configurer le transfert de port manuellement.

[^13]: Si vous n'avez pas de compte, inscrivez-vous sur Ngrok via un compte Google ou GitHub.
