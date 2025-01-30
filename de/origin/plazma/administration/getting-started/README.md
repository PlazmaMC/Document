---
description: Erfahren Sie, wie Sie einen Server mit Plazma erstellen.
---

# 👟 Los geht's

Um Plazma stabil zu nutzen, muss das System die folgenden Anforderungen erfüllen.

|               | Minimum | Empfohlen |
| :-----------: | ------- | --------- |
|  Architektur  | x64     | -         |
|      RAM      | 8GB     | 16GB      |
| Speicherplatz | 1GB     | 8GB       |
|      JDK      | 17      | 21        |

Für eine reibungslose Konfigurationsdateibearbeitung ist es auch ratsam, einen Editor wie [Visual Studio Code](https://code.visualstudio.com/download) zu installieren.

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Richtige Ausgabe" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Laufzeitumgebung Zulu21.32+17-CA (Build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (Build 21.0.2+13-LTS, gemischter Modus, gemeinsame Nutzung)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' ist keine interne oder externe Befehl, ein ausführbares Programm oder
eine Stapeldatei.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Unbekannte Option: --version
Fehler: Java Virtual Machine konnte nicht erstellt werden.
Fehler: Es ist ein schwerwiegender Ausnahmefehler aufgetreten. Das Programm wird beendet.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Laden Sie zuerst [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) herunter und installieren Sie **JDK 21** im `.msi`-Format.
2. Führen Sie den heruntergeladenen Installationsassistenten aus und klicken Sie auf `Next`.
3. Aktivieren Sie im mittleren linken Bereich des Fensters `Set JAVA_HOME variable` und klicken Sie dann auf `Next`.
4. Klicken Sie auf `Install`, um die JRE-Installation abzuschließen.
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

Führen Sie dann den folgenden Befehl im Terminal aus, um JRE zu installieren.

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

## 2. Plazma herunterladen

Plazma bietet verschiedene Arten von ausführbaren Dateien an.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Weitere Informationen</summary>

Der Name der ausführbaren Datei ist `plazma-(Version Manager)-1.20.4-R0.1-SNAPSHOT-(Mapping Typ).jar`.

- **Mapping Typ**\
  Mapping ist eine Art Karte, die den echten Code von Minecraft mit dem obfuszierten Code verbindet.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, ist das Mapping für das Vanilla Minecraft. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Sie können das Startskript über den Download-Button unten links herunterladen.\
**Stellen Sie sicher, dass das heruntergeladene Startskript mit Ihrem Betriebssystem übereinstimmt.**

***

## 4. Dateien ordnen

Verschieben Sie das heruntergeladene Startskript und Plazma in einen neuen Ordner.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Führen Sie nun das Startskript aus. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA-Zustimmung

Nach dem Ausführen des Startskripts wird eine `eula.txt`-Datei im Ordner erstellt.

Die EULA[^9] ist ein Endbenutzer-Lizenzvertrag, dem Sie zustimmen müssen, um die Dienste von [Mojang Studios](#user-content-fn-10)[^10] zu nutzen.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Um der EULA zuzustimmen, ändern Sie `eula=false` in der `eula.txt`-Datei in `eula=true` und speichern Sie die Änderungen.

***

## 6. Externe Verbindungen zulassen (Windows)

Moderne Betriebssysteme blockieren standardmäßig externe Zugriffe, um vor Gefahren zu schützen, indem sie die Firewall und den Router verwenden.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Wenn Ihr Router UPnP nicht unterstützt, müssen Sie je nach Routermodell Informationen suchen.

Alternativ können Sie auch [Ngrok](https://ngrok.com/) verwenden, um eine temporäre Adresse zu generieren.
{% endhint %}

{% hint style="warning" %}
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

| Nachricht                                | Bedeutung                                                      |
| ---------------------------------------- | -------------------------------------------------------------- |
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

Erfahren Sie, wie Sie den Server anpassen können, indem Sie das folgende Handbuch lesen.

{% content-ref url="naechster-schritt.md" %}
[naechster-schritt.md](naechster-schritt.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
