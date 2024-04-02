---
description: Erfahren Sie, wie Sie einen Server mit Plazma erstellen.
---

# 👟 Los geht's

Um Plazma stabil zu nutzen, muss das System die folgenden Anforderungen erfüllen.

|               | Minimum | Empfohlen |
| :-----------: | ------: | --------: |
|  Architektur  |     x64 |         - |
|      RAM      |     8GB |      16GB |
| Speicherplatz |     1GB |       8GB |
|      JRE      |      17 |        21 |

Für eine reibungslose Konfigurationsdateibearbeitung ist es auch ratsam, einen Editor wie [Visual Studio Code](https://code.visualstudio.com/download) zu installieren.

***

## 1. JRE Installation

Wie der Name schon sagt, wird Minecraft: **"Java"** Edition in Java entwickelt und erfordert daher JRE[^1] zur Ausführung.

Da Plazma auf der offiziellen Serverplattform von Mojang Studios basiert[^2], muss auch JRE installiert werden, um Plazma zu verwenden.

### 1.1 Überprüfung der JRE-Installation

Um zu überprüfen, ob JRE auf dem System installiert ist, geben Sie [`cmd /k java --version`](#user-content-fn-4)[^4] in das Ausführungsfenster ein und führen Sie es aus.

Wenn die Ausgabe wie folgt aussieht, überspringen Sie [Schritt 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Wenn dies nicht der Fall ist oder wenn die Ausgabe wie folgt aussieht, ist JRE nicht vorhanden oder zu alt, und Sie müssen [Schritt 1.2](setup.md#id-1.2) ausführen.

{% code title="JRE가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE-Installation

In diesem Handbuch verwenden wir Azul Zulu als eine der [JRE-Varianten](#user-content-fn-5)[^5].

Überprüfen Sie nach Abschluss der Installation erneut [Schritt 1.1](setup.md#id-1.1), um sicherzustellen, dass die Installation korrekt abgeschlossen wurde.

{% tabs %}

{% tab title="Windows" %}

1. Laden Sie zuerst [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) herunter und installieren Sie **JDK 21** im `.msi`-Format.
2. Führen Sie den heruntergeladenen Installationsassistenten aus und klicken Sie auf `Next`.
3. Aktivieren Sie im mittleren linken Bereich des Fensters `Set JAVA_HOME variable` und klicken Sie dann auf `Next`.
4. Klicken Sie auf `Install`, um die JRE-Installation abzuschließen.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

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

다음 명령어를 입력하여 JRE를 설치할 수 있습니다.

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

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Die folgenden Informationen sind für Entwickler oder diejenigen gedacht, die sich für die Eigenschaften der verschiedenen Arten interessieren.\
Für normale Benutzer ist es nicht erforderlich, [Schritt 3](setup.md#id-3) zu lesen.

{% endhint %}

<details>

<summary>Weitere Informationen</summary>

Der Name der ausführbaren Datei ist `plazma-(Version Manager)-1.20.4-R0.1-SNAPSHOT-(Mapping Typ).jar`.

- **Mapping Typ**\
  Mapping ist eine Art Karte, die den echten Code von Minecraft mit dem obfuszierten Code verbindet.
  - **Reobf**\
    Reobfuscation, auch bekannt als Spigot Mapping, wird hauptsächlich von den meisten NMS-Plugins verwendet.\
    Es wird ab Version 1.20.5 nicht mehr unterstützt.
  - **Mojmap**\
    Mojang Mapping, das Mapping für das Vanilla Minecraft.
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

Sie können das Startskript über [Flags.sh](https://flags.sh) erstellen. Geben Sie einfach die [zu verwendende Speichermenge](#user-content-fn-8)[^8] für Plazma ein, und der Befehl wird automatisch optimiert.

Sie können das Startskript über den Download-Button unten links herunterladen.\
**Stellen Sie sicher, dass das heruntergeladene Startskript mit Ihrem Betriebssystem übereinstimmt.**

***

## 4. Dateien ordnen

Verschieben Sie das heruntergeladene Startskript und Plazma in einen neuen Ordner.

{% Hinweis Stil="Warnung" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Andernfalls funktionieren Plazma oder JRE möglicherweise nicht ordnungsgemäß.

{% endhint %}

Führen Sie nun das Startskript aus. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA-Zustimmung

Nach dem Ausführen des Startskripts wird eine `eula.txt`-Datei im Ordner erstellt.

Die EULA[^9] ist ein Endbenutzer-Lizenzvertrag, dem Sie zustimmen müssen, um die Dienste von [Mojang Studios](#user-content-fn-10)[^10] zu nutzen.

Ohne Zustimmung zur EULA können Sie den Server nicht starten, und bei Verstoß gegen die EULA können Maßnahmen wie Kontosperrung ergriffen werden. [^11]

Um der EULA zuzustimmen, ändern Sie `eula=false` in der `eula.txt`-Datei in `eula=true` und speichern Sie die Änderungen.

***

## 6. Externe Verbindungen zulassen (Windows)

Moderne Betriebssysteme blockieren standardmäßig externe Zugriffe, um vor Gefahren zu schützen, indem sie die Firewall und den Router verwenden.

Da Sie in Schritt 3 die Windows-Firewall bereits zugelassen haben, müssen Sie nur noch Port-Weiterleitungen einrichten.

{% Hinweis-Stil="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Wenn Ihr Router UPnP nicht unterstützt, müssen Sie je nach Routermodell Informationen suchen.

Alternativ können Sie auch [Ngrok](https://ngrok.com/) verwenden, um eine temporäre Adresse zu generieren.
{% endhint %}

{% Hinweis Stil="Warnung" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Überprüfung der Notwendigkeit von Port-Weiterleitungen

Geben Sie Folgendes in das Ausführungsfenster ein und führen Sie es aus.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Wenn die Ausgabe `True` ist, sind keine weiteren Maßnahmen erforderlich. Wenn die Ausgabe `False` ist, müssen Port-Weiterleitungen festgelegt werden.

### 6.2 Serververbindung

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Die Adresse, die zum Verbinden mit dem Server verwendet wird, finden Sie [hier](https://ip.pe.kr/) heraus.

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Danach, wenn Sie den Server neu starten, versucht Plazma automatisch Portweiterleitung.

Die folgende Meldung auf der Konsole zeigt den Erfolg oder Misserfolg von UPnP an, und in der Konsole wird `[UPnP] (Nachricht)` angezeigt.

| Nachricht                                | Bedeutung                                      |
| ---------------------------------------- | ---------------------------------------------- |
| `Port (포트)` erfolgreich geöffnet         | Portweiterleitung erfolgreich.                 |
| `Port (포트) ist bereits geöffnet`         | Ein anderer Dienst verwendet den Port bereits. |
| `Port (포트) konnte nicht geöffnet werden` | Portweiterleitung fehlgeschlagen.              |
| `Dienst ist nicht verfügbar`             | Der Router unterstützt kein UPnP.              |

Wenn der Server heruntergefahren wird, schließt Plazma die Ports automatisch.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Laden Sie die `Windows (64-bit)` ZIP-Datei von der [Ngrok-Website](https://ngrok.com/download) herunter.
2. Legen Sie das heruntergeladene Ngrok in den Serverordner.
3. Erstellen Sie auf dem [Ngrok-Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken) einen [Authentifizierungstoken](#user-content-fn-13).
4. Führen Sie den im Serverordner angezeigten Befehl in der `Command Line` aus.
5. Fügen Sie dem Ausführungsskript `start /b ngrok tcp --region jp 25565` am Anfang und `taskkill /f /t /im ngrok.exe` am Ende hinzu.
6. In der Konsole wird `Weiterleitung tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` angezeigt, wobei `0.tcp.jp.ngrok.io:12345` die Adresse des Servers ist.
7. Jetzt können Sie über diese Adresse von extern auf den Server zugreifen.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Beispielsweise, wenn nach Ausführung des Befehls Folgendes angezeigt wird:

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Versuchen Sie, sich mit der im IPv4-Adressfeld angezeigten `192.168.3.7` zu verbinden, um lokal auf den Server zuzugreifen.

Wenn Server und Spiel auf demselben PC ausgeführt werden, können Sie sich mit `localhost` verbinden.

{% endtab %}
{% endtabs %}

## 7. Entwicklungsphase

Wenn der Server erfolgreich gestartet wurde und ordnungsgemäß funktioniert, ist es jetzt an der Zeit, den Server anzupassen.

Erfahren Sie, wie Sie den Server anpassen können, indem Sie den folgenden Leitfaden lesen.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
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
