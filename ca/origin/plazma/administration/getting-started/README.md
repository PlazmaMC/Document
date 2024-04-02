---
description: Descobreix com crear un servidor amb Plazma.
---

# 👟 Començar

Per utilitzar Plazma de manera estable, el sistema ha de complir amb els següents requisits.

|                        | Mínim | Recomanat |
| :--------------------: | ----: | --------: |
|      Arquitectura      |   x64 |         - |
|           RAM          |   8GB |      16GB |
| Espai d'emmagatzematge |   1GB |       8GB |
|           JRE          |    17 |        21 |

Per a una edició de fitxers de configuració més fàcil, també és recomanable instal·lar un editor com [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instal·lar JRE

Com el nom indica, Minecraft: **"Java"** Edition està desenvolupat en Java, per tant, requereix JRE[^1] per funcionar.

Com que Plazma està basat en la plataforma oficial de servidors de Mojang Studios[^2], també cal instal·lar JRE per utilitzar Plazma.

### 1.1 Comprovar si JRE està instal·lat

Per verificar si JRE està instal·lat al sistema, introduïu [`cmd /k java --version`](#user-content-fn-4)[^4] a la finestra d'execució i executeu-la.

Si es mostra el següent, salteu al [pas 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Si no es mostra així, o es mostra com a continuació, vol dir que JRE no està instal·lat o és massa antic, per tant, heu de seguir el [pas 1.2](setup.md#id-1.2).

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

### 1.2 Instal·lar JRE

En aquesta guia, farem servir Azul Zulu com una de les opcions de JRE[^5].

Un cop instal·lat, torneu a fer el [pas 1.1](setup.md#id-1.1) per comprovar que la instal·lació s'ha completat correctament.

{% tabs %}

{% tab title="Windows" %}

1. Primer, des de [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) baixeu **JDK 21** en format `.msi`.
2. Executeu l'assistent d'instal·lació descarregat i feu clic a 'Següent'.
3. Un cop activat 'Set JAVA_HOME variable' al menú central esquerre, feu clic a 'Següent'.
4. Feu clic a 'Instal·la' per completar la instal·lació de JRE.

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

Després, executeu la següent comanda al terminal per instal·lar JRE.

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

## 2. Descarregar Plazma

Plazma ofereix diversos tipus de fitxers executables.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

El següent és per a desenvolupadors o aquells interessats en les característiques de cada tipus.\
Si ets un usuari comú, no hi ha cap problema en saltar al [pas 3](setup.md#id-3).

{% endhint %}

<details>

<summary>Més informació</summary>

El nom del fitxer executable és `plazma-(gestor de versions)-1.20.4-R0.1-SNAPSHOT-(format de mapeig).jar`.

- **Format de mapeig**\
  El mapeig és una mena de mapa que connecta el codi real de Minecraft amb el codi ofuscado.
  - **Reobf**\
    Reobfuscació, també conegut com a mapeig de Spigot, és utilitzat en la majoria dels plugins NMS.\
    A partir de la versió 1.20.5, deixarà de ser utilitzat.
  - **Mojmap**\
    Mapeig de Mojang, és el mapeig del Minecraft de base.
- **Gestor de versions**\
  El gestor de versions és una mena de llançador que necessita biblioteques per al funcionament del servidor i per aplicar patches als fitxers del servidor.
  - **Paperclip**\
    Desenvolupat pel equip de PaperMC per a Paper i altres plataformes derivades, descarrega biblioteques i aplica patches al servidor.
  - **Bundler**\
    Gestor de versions del Minecraft de base.

</details>

***

## 3. Creació de l'script d'inici

Per iniciar Plazma de manera senzilla i reiniciar el servidor automàticament, heu de crear un [script d'inici](#user-content-fn-6)[^6].

Podeu crear un script d'inici a través de [Flags.sh](https://flags.sh). Només cal introduir la [memòria a utilitzar per Plazma](#user-content-fn-8)[^8] i l'ordre s'optimitzarà automàticament.

Podeu descarregar l'script d'inici fent clic al botó de descàrrega a la part inferior esquerra.\
**Assegureu-vos que l'script d'inici descarregat és compatible amb el vostre sistema operatiu.**

***

## 4. Neteja de fitxers

Ara, mou l'script d'inici descarregat i Plazma a una nova carpeta.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

En cas contrari, Plazma o JRE podrien no funcionar correctament.

{% endhint %}

Ara executeu l'script d'inici. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. Acceptar l'EULA

Després d'executar l'script d'inici, es crearà un fitxer `eula.txt` a la carpeta.

L'EULA[^9] és un acord de llicència que has d'acceptar per utilitzar els serveis de [Mojang Studios](#user-content-fn-10)[^10].

Si no accepteu l'EULA, no podreu iniciar el servidor i, si incompliu l'EULA, podeu rebre sancions com la suspensió del compte, entre altres [mesures disciplinàries](#user-content-fn-11)[^11].

Per acceptar l'EULA, canvieu `eula=false` a `eula=true` al fitxer `eula.txt` i deseu-lo.

***

## 6. Permetre connexions externes (Windows)

Els sistemes operatius moderns bloquegen els accessos externs per seguretat mitjançant el **firewall** i el **encaminador**.

En el cas de Windows, com ja heu permès en el [pas 3](setup.md#id-3), només cal fer el reenviament de ports.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Si l'encaminador no suporta UPnP, heu de cercar informació específica per a cada encaminador, ja que cada panell és diferent.

També podeu generar una adreça temporal amb [Ngrok](https://ngrok.com/).
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Comprovar si cal fer reenviament de ports

Introduïu la següent comanda a l'execució i executeu-la.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Si la sortida és `Verdader`, ja podeu acabar, però si és `Fals`, cal configurar el reenviament de ports.

### 6.2 Connectar-se al servidor

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

L'adreça utilitzada per connectar-se al servidor es pot trobar [aquí](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

A continuació, en reiniciar el servidor, Plazma intentarà reenviar automàticament els ports.

A continuació es mostra l'estat de l'èxit del UPnP segons el missatge que es mostra a la consola, que es visualitzarà com a `[UPnP] (missatge)`.

| Missatge                                 | Significat                               |
| ---------------------------------------- | ---------------------------------------- |
| `S'ha obert correctament el port (port)` | Reenviament de ports reeixit.            |
| `El port (port) ja està obert`           | Un altre servei està utilitzant el port. |
| `Error en obrir el port (port)`          | Reenviament de ports fallit.             |
| `El servei no està disponible`           | El router no suporta UPnP.               |

Quan el servidor es tanca, Plazma tanca automàticament el port.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Baixeu el fitxer ZIP de `Windows (64-bit)` des de la [pàgina web de Ngrok](https://ngrok.com/download).
2. Col·loqueu l'arxiu Ngrok descarregat a la carpeta del servidor.
3. A la [pàgina web de Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) genereu un token d'autenticació.
4. Executeu la comanda que es mostra a la finestra `Command Line` de la carpeta del servidor.
5. Afegiu `start /b ngrok tcp --region jp 25565` a la part superior de l'script d'inici i `taskkill /f /t /im ngrok.exe` a la part inferior.
6. A la part superior de la consola, l'adreça `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` serà l'adreça del servidor.
7. Ara podeu connectar-vos des de l'extern utilitzant aquesta adreça.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Per exemple, si després d'executar la comanda es mostra el següent:

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Podeu connectar-vos al servidor des de l'ordinador local utilitzant l'adreça IPv4 indicada com a `192.168.3.7`.

Si el servidor i el joc s'estan executant al mateix PC, podeu connectar-vos utilitzant `localhost`.

{% endtab %}
{% endtabs %}

## 7. Fase de desenvolupament

Si heu iniciat el servidor amb èxit i aquest funciona correctament, ara és moment de personalitzar-lo.

Consulteu la guia següent per aprendre com personalitzar el servidor.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Entorn d'execució de Java, entorn d'execució de Java.

[^2]: Paper, la base de Plazma, es basa en Spigot, que és la plataforma oficial del servidor basada en Spigot.

[^3]: Tecla Windows + R

[^4]: En el cas de Linux, executeu `java --version` a la terminal.

[^5]: JRE és un dels projectes de codi obert i té diversos tipus com les plataformes de servidor de Minecraft.

[^6]: Generalment conegut com a **llançador**.

[^7]: En activar "Reinici automàtic", el servidor es reiniciarà automàticament. Podeu sortir introduint `Control + C`.

[^8]: No es recomana superar la meitat de la capacitat del sistema.

    Per exemple, si la capacitat total de memòria del sistema és de 8 GB, no es recomana configurar-la per sobre dels 4 GB.

[^9]: Acord de llicència per a l'usuari final, acord de llicència per a l'usuari final. Per obtenir més informació, consulteu el [lloc web de Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Corporació Microsoft.

[^11]: Segons l'article 32.1.9 de la Llei de Promoció de la Indústria dels Jocs de Corea, es pot presentar una denúncia legal contra **Microsoft Korea Co., Ltd.** a Corea.

[^12]: Universal Plug & Play. Purpur, inclosa en Plazma, utilitza aquesta tecnologia per comunicar-se automàticament amb el router només quan el servidor està en marxa, de manera que no cal reenviar els ports manualment.

[^13]: Si no teniu un compte, registreu-vos a Ngrok amb un compte de Google o GitHub.
