---
description: Découvrez comment créer un serveur avec Plazma.
---

# 👟 Commencer

Pour utiliser Plazma de manière stable, le système doit répondre aux exigences suivantes.

|                    | Minimum | Recommandé |
| :----------------: | ------- | ---------- |
|    Architecture    | x64     | -          |
|         RAM        | 8 Go    | 16 Go      |
| Espace de stockage | 1 Go    | 8 Go       |
|         JDK        | 17      | 21         |

Pour une modification de fichier fluide, il est recommandé d'installer un éditeur tel que [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Sortie correcte" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Environnement d'exécution Zulu21.32+17-CA (version 21.0.2+13-LTS)
OpenJDK 64 bits Server VM Zulu21.32+17-CA (version 21.0.2+13-LTS, mode mixte, partage)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' n'est pas reconnu en tant que commande interne ou externe, programme exécutable ou fichier de commandes.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Option non reconnue : --version
Erreur : Impossible de créer la machine virtuelle Java.
Erreur : Une exception fatale s'est produite. Le programme va se fermer.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Téléchargez d'abord **JDK 21** en format `.msi` depuis [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Exécutez l'assistant d'installation téléchargé et cliquez sur `Suivant`.
3. **Activez `Set JAVA_HOME variable` dans le menu affiché au centre gauche de la fenêtre**, puis cliquez sur `Suivant`.
4. Cliquez sur `Installer` pour terminer l'installation de JRE.
   {% endtab %}

{% tab title="macOS" %}
[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.
{% endtab %}

{% tab title="Debian/Ubuntu" %}
먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

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
다음 명령어를 입력하여 JDK를 설치할 수 있습니다.

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
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>En savoir plus</summary>

Le nom du fichier exécutable est défini comme suit : `plazma-(version du gestionnaire)-1.20.4-R0.1-SNAPSHOT-(type de mappage).jar`.

- **Type de mappage**\
  Le mappage est une sorte de carte reliant le code réel de Minecraft au code obfusqué.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Vous pouvez télécharger le script de démarrage en bas à gauche.\
**Assurez-vous que le script téléchargé correspond à votre système d'exploitation.**

***

## 4. Nettoyage des fichiers

Déplacez maintenant le script de démarrage téléchargé et Plazma dans un nouveau dossier.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Exécutez maintenant le script de démarrage. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Acceptation de l'EULA

Après avoir exécuté le script de démarrage une fois, un fichier `eula.txt` sera créé dans le dossier.

L'EULA[^9] est un contrat de licence que vous devez accepter en utilisant les services de [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Pour accepter l'EULA, modifiez `eula=false` en `eula=true` dans le fichier `eula.txt` et enregistrez les modifications.

***

## 6. Autorisation d'accès externe (Windows)

Les systèmes d'exploitation modernes bloquent généralement l'accès externe par défaut à des fins de sécurité à l'aide du **pare-feu** et du **routeur**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Si votre routeur ne prend pas en charge l'UPnP, vous devrez rechercher comment configurer le transfert de port spécifiquement pour votre routeur.

Vous pouvez également utiliser [Ngrok](https://ngrok.com/) pour générer une adresse temporaire.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Vérification de la nécessité du transfert de port

Saisissez la commande suivante dans la fenêtre d'exécution et exécutez-la.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Si la sortie est `True`, vous avez terminé ici, sinon vous devrez configurer le transfert de port.

### 6.2 Connexion au serveur

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

L'adresse utilisée pour se connecter au serveur peut être vérifiée [ici](https://ip.pe.kr/)
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Ensuite, après avoir redémarré le serveur, Plazma tentera automatiquement de rediriger les ports.

Le succès du UPnP est déterminé par le message affiché dans la console, qui sera affiché comme `[UPnP] (message)`.

| Message                               | Signification                                           |
| ------------------------------------- | ------------------------------------------------------- |
| `Port (port) ouvert avec succès`      | Redirection de port réussie.            |
| `Le port (port) est déjà ouvert`      | Un autre service utilise déjà ce port.  |
| `Échec de l'ouverture du port (port)` | Échec de la redirection de port.        |
| `Le service est indisponible`         | Le routeur ne prend pas en charge UPnP. |

Lorsque le serveur est arrêté, Plazma ferme automatiquement le port.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Téléchargez le fichier ZIP `Windows (64-bit)` depuis le site [Ngrok](https://ngrok.com/download).
2. Placez le Ngrok téléchargé dans le dossier du serveur.
3. Sur le [tableau de bord Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), créez un [jeton d'authentification](#user-content-fn-13)[^13].
4. Exécutez la commande affichée dans la `Ligne de commande` du dossier du serveur.
5. Ajoutez `start /b ngrok tcp --region jp 25565` en haut du script d'exécution, et `taskkill /f /t /im ngrok.exe` en bas.
6. Dans la console, l'adresse `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` devient l'adresse du serveur `0.tcp.jp.ngrok.io:12345`.
7. Vous pouvez maintenant vous connecter depuis l'extérieur via cette adresse.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

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

## 7. Évoluer

Après avoir démarré avec succès le serveur et qu'il fonctionne correctement, il est temps de le personnaliser.

Découvrez comment personnaliser le serveur à travers le guide ci-dessous.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
