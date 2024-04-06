---
description: Erfahren Sie, wie Sie einen Server mit Plazma erstellen.
---

# 👟 Los geht's

Um Plazma stabil zu nutzen, muss das System die folgenden Anforderungen erfüllen.

|               | Minimum | Empfohlen |
| :-----------: | :------ | :-------- |
|  Architektur  | x64     | -         |
|      RAM      | 8GB     | 16GB      |
| Speicherplatz | 1GB     | 8GB       |
|      JRE      | 17      | 21        |

Für eine reibungslose Konfigurationsdateibearbeitung ist es auch ratsam, einen Editor wie [Visual Studio Code](https://code.visualstudio.com/download) zu installieren.

***

## 1. JRE Installation

Wie der Name schon sagt, wird Minecraft: **"Java"** Edition in Java entwickelt und erfordert daher JRE[^1] zur Ausführung.

Da Plazma auf der offiziellen Serverplattform von Mojang Studios basiert[^2], muss auch JRE installiert werden, um Plazma zu verwenden.

### 1.1 Überprüfung der JRE-Installation

Um zu überprüfen, ob JRE auf dem System installiert ist, geben Sie [`cmd /k java --version`](#user-content-fn-4)[^4] in das Ausführungsfenster ein und führen Sie es aus.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Richtige Ausgabe" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Laufzeitumgebung Zulu21.32+17-CA (Build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (Build 21.0.2+13-LTS, gemischter Modus, gemeinsame Nutzung)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE nicht installiert" lineNumbers="true" %}

```log
'java' ist keine interne oder externe Befehl, ein ausführbares Programm oder
eine Stapeldatei.
```

{% endcode %}

{% code title="JRE veraltet" lineNumbers="true" %}

```log
Unbekannte Option: --version
Fehler: Java Virtual Machine konnte nicht erstellt werden.
Fehler: Es ist ein schwerwiegender Ausnahmefehler aufgetreten. Das Programm wird beendet.
```

{% endcode %}

### 1.2 JRE-Installation

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. Laden Sie zuerst [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) herunter und installieren Sie **JDK 21** im `.msi`-Format.
2. Führen Sie den heruntergeladenen Installationsassistenten aus und klicken Sie auf `Next`.
3. Aktivieren Sie im mittleren linken Bereich des Fensters `Set JAVA_HOME variable` und klicken Sie dann auf `Next`.
4. Klicken Sie auf `Install`, um die JRE-Installation abzuschließen.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) **JDK 21** als `.dmg` Installationsassistenten von Azul Zulu herunterladen und ausführen, um JRE zu installieren.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Fügen Sie zunächst das Azul Zulu-Repository zu APT hinzu, indem Sie den folgenden Befehl im Terminal ausführen.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Führen Sie dann den folgenden Befehl im Terminal aus, um JRE zu installieren.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Sie können JRE installieren, indem Sie den folgenden Befehl eingeben.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma herunterladen

Plazma bietet verschiedene Arten von ausführbaren Dateien an.

{% Hinweis Stil="Warnung" %}

**In den meisten Fällen wird `Reobf Paperclip` verwendet.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Weitere Informationen</summary>

Der Name der ausführbaren Datei ist `plazma-(Version Manager)-1.20.4-R0.1-SNAPSHOT-(Mapping Typ).jar`.

- **Mapping Typ**\
  Mapping ist eine Art Karte, die den echten Code von Minecraft mit dem obfuszierten Code verbindet.
  - **Reobf**\
    Reobfuscated (재난독화), auch als Spigot-Mapping bekannt, wird hauptsächlich in den meisten NMS-Plugins verwendet.\
    Die Verwendung wird ab Version 1.20.5 eingestellt.
  - **Mojmap**\
    Mojang-mapped, ist das Mapping für das Vanilla Minecraft.
- **Version Manager**\
  Der Version Manager ist eine Art Launcher, der die für den Serverbetrieb erforderlichen Bibliotheken bereitstellt und Serverdateien patcht.
  - **Paperclip**\
    Ein Administrator, den das PaperMC-Team für Paper und andere abgeleitete Plattformen entwickelt hat. Es lädt Bibliotheken herunter und wendet Patches auf den Server an.
  - **Bundler**\
    Der Version Manager für Vanilla Minecraft.

</details>

***

## 3. Startskript erstellen

Um Plazma einfach zu starten und den Server automatisch neu zu starten, müssen Sie ein [Startskript](#user-content-fn-6)[^6] erstellen.

Über [Flags.sh](https://flags.sh) können Sie das Startskript für [Plazma](#user-content-fn-7)[^7] erstellen, indem Sie nur den [zu verwendenden Speicher](#user-content-fn-8)[^8] eingeben, werden die Befehle automatisch optimiert.

Sie können das Startskript über den Download-Button unten links herunterladen.\
**Stellen Sie sicher, dass das heruntergeladene Startskript mit Ihrem Betriebssystem übereinstimmt.**

***

## 4. Dateien ordnen

Verschieben Sie das heruntergeladene Startskript und Plazma in einen neuen Ordner.

{% Hinweis Stil="Warnung" %}

**Der Ordnungsname muss zwingend ohne Leerzeichen und in Englisch sein.**

Andernfalls funktionieren Plazma oder JRE möglicherweise nicht ordnungsgemäß.

{% endhint %}

Führen Sie nun das Startskript aus. Für Windows müssen Sie im <mark style="background-color:orange;">Firewall-Zulassungsauswahlfenster unbedingt **Zulassen** auswählen</mark>.

***

## 5. EULA-Zustimmung

Nach dem Ausführen des Startskripts wird eine `eula.txt`-Datei im Ordner erstellt.

Die EULA[^9] ist ein Endbenutzer-Lizenzvertrag, dem Sie zustimmen müssen, um die Dienste von [Mojang Studios](#user-content-fn-10)[^10] zu nutzen.

{% Hinweis Stil="Warnung" %}

Wenn Sie nicht zustimmen, können Sie den Server nicht starten und bei Verstoß gegen die EULA können [Sanktionen](#user-content-fn-11)[^11] wie die Sperrung des Kontos verhängt werden.

{% endhint %}

Um der EULA zuzustimmen, ändern Sie `eula=false` in der `eula.txt`-Datei in `eula=true` und speichern Sie die Änderungen.

***

## 6. Externe Verbindungen zulassen (Windows)

Moderne Betriebssysteme blockieren standardmäßig externe Zugriffe, um vor Gefahren zu schützen, indem sie die Firewall und den Router verwenden.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% Hinweis-Stil="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Wenn Ihr Router UPnP nicht unterstützt, müssen Sie je nach Routermodell Informationen suchen.

Alternativ können Sie auch [Ngrok](https://ngrok.com/) verwenden, um eine temporäre Adresse zu generieren.
{% endhint %}

{% Hinweis Stil="Warnung" %}

**Für Betriebssysteme wie Linux oder macOS (halb) UNIX, bei denen die Einstellungsmethoden für Firewall-Dienste unterschiedlich sind, müssen Sie die Informationen selbst recherchieren.**

{% endhint %}

### 6.1 Überprüfung der Notwendigkeit von Port-Weiterleitungen

Geben Sie Folgendes in das Ausführungsfenster ein und führen Sie es aus.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Wenn die Ausgabe `True` ist, sind keine weiteren Maßnahmen erforderlich. Wenn die Ausgabe `False` ist, müssen Port-Weiterleitungen festgelegt werden.

### 6.2 Serververbindung

{% tabs %}

{% tab title="Externer Zugriff" %}

Wenn keine Portweiterleitung erforderlich ist oder bereits erfolgreich durchgeführt wurde, können Sie jetzt eine Verbindung zum Server herstellen.

Die Adresse, die zum Verbinden mit dem Server verwendet wird, finden Sie [hier](https://ip.pe.kr/) heraus.

{% endtab %}

{% tab title="UPnP für Portweiterleitung versuchen" %}

In der Datei `purpur.yml` im Serverordner aktivieren Sie `network.upnp-port-forwarding` auf `true`.

Danach, wenn Sie den Server neu starten, versucht Plazma automatisch Portweiterleitung.

Die folgende Meldung auf der Konsole zeigt den Erfolg oder Misserfolg von UPnP an, und in der Konsole wird `[UPnP] (Nachricht)` angezeigt.

| Nachricht                                | Bedeutung                                                      |
| ---------------------------------------- | -------------------------------------------------------------- |
| `Port (포트)` erfolgreich geöffnet         | Portweiterleitung erfolgreich.                 |
| `Port (포트) ist bereits geöffnet`         | Ein anderer Dienst verwendet den Port bereits. |
| `Port (포트) konnte nicht geöffnet werden` | Portweiterleitung fehlgeschlagen.              |
| `Dienst ist nicht verfügbar`             | Der Router unterstützt kein UPnP.              |

Wenn der Server heruntergefahren wird, schließt Plazma die Ports automatisch.

{% endtab %}

{% tab title="Erstellen einer temporären Adresse mit Ngrok" %}

Die Verwendung von Ngrok ist nützlich für kurzfristige Tests, gemeinsame Nutzung oder Spielen mit Freunden.

1. Laden Sie die `Windows (64-bit)` ZIP-Datei von der [Ngrok-Website](https://ngrok.com/download) herunter.
2. Legen Sie das heruntergeladene Ngrok in den Serverordner.
3. Erstellen Sie auf dem [Ngrok-Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) einen [Authentifizierungstoken](#user-content-fn-13).
4. Führen Sie den im Serverordner angezeigten Befehl in der `Command Line` aus.
5. Fügen Sie dem Ausführungsskript `start /b ngrok tcp --region jp 25565` am Anfang und `taskkill /f /t /im ngrok.exe` am Ende hinzu.
6. In der Konsole wird `Weiterleitung tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` angezeigt, wobei `0.tcp.jp.ngrok.io:12345` die Adresse des Servers ist.
7. Jetzt können Sie über diese Adresse von extern auf den Server zugreifen.

{% endtab %}

{% tab title="Verbindung von lokal" %}

Wenn Sie versuchen, sich lokal mit dem Server zu verbinden, können Sie dies über das Ausführen von `cmd /k ipconfig` im Ausführungsfenster und die Verwendung der angezeigten `IPv4-Adresse` tun.

Beispielsweise, wenn nach Ausführung des Befehls Folgendes angezeigt wird:

```log
Windows IP-Konfiguration

Ethernet-Adapter Ethernet:

    Verbundenes DNS-Suffix. . . . :
    IPv4-Adresse. . . . . . . . . : 192.168.3.7
    Subnetzmaske . . . . . . . : 255.255.255.0
    Standardgateway . . . . . . : 192.168.3.1

```

Versuchen Sie, sich mit der im IPv4-Adressfeld angezeigten `192.168.3.7` zu verbinden, um lokal auf den Server zuzugreifen.

Wenn Server und Spiel auf demselben PC ausgeführt werden, können Sie sich mit `localhost` verbinden.

{% endtab %}
{% endtabs %}

## 7. Fortschritt

Wenn der Server erfolgreich gestartet wurde und ordnungsgemäß funktioniert, ist es jetzt an der Zeit, den Server anzupassen.

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="naechster-schritt.md" %}
[naechster-schritt.md](naechster-schritt.md)
{% endcontent-ref %}

***

[^1]: Java-Laufzeitumgebung, Java-Laufzeitumgebung.

[^2]: Die auf Paper basierende Plazma basiert auf Spigot, das wiederum auf der offiziellen Serverplattform von Spigot basiert.

[^3]: Windows-Taste + R

[^4]: Für Linux verwenden Sie `java --version` im Terminal.

[^5]: JRE ist ein Open-Source-Projekt mit verschiedenen Versionen, ähnlich wie die Minecraft-Serverplattform.

[^6]: Es wird im Allgemeinen als **Launcher** bezeichnet.

[^7]: Durch Aktivieren von "Auto-Neustart" wird der Server automatisch neu gestartet. Sie können `Strg + C` eingeben, um es zu beenden.

[^8]: Es wird nicht empfohlen, mehr als die Hälfte des Systems zu verwenden.

    Beispielsweise wird bei einem Gesamtspeicher von 8 GB die Einstellung auf mehr als 4 GB nicht empfohlen.

[^9]: Endbenutzer-Lizenzvereinbarung, Endbenutzer-Lizenzvereinbarung. Weitere Informationen finden Sie auf der [Minecraft-Website](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: Gemäß Artikel 32 Absatz 1 Nummer 9 des Gesetzes über die Förderung der Spieleindustrie in Korea kann **Korea Microsoft Corporation** rechtlich belangt werden.

[^12]: Universal Plug & Play. Durch das in Plazma enthaltene Purpur kommuniziert automatisch mit dem Router über diese Technologie, um die Ports nur zu öffnen, wenn der Server läuft, daher ist kein manuelles Portforwarding erforderlich.

[^13]: Wenn Sie kein Konto haben, können Sie sich über ein Google- oder GitHub-Konto bei Ngrok anmelden.
