---
description: Descobreix com crear un servidor amb Plazma.
---

# 👟 Començar

Per utilitzar Plazma de manera estable, el sistema ha de complir amb els següents requisits.

|                        | Mínim | Recomanat |
| :--------------------: | :---- | :-------- |
|      Arquitectura      | x64   | -         |
|           RAM          | 8GB   | 16GB      |
| Espai d'emmagatzematge | 1GB   | 8GB       |
|           JRE          | 17    | 21        |

Per a una edició de fitxers de configuració més fàcil, també és recomanable instal·lar un editor com [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instal·lar JRE

Com el nom indica, Minecraft: **"Java"** Edition està desenvolupat en Java, per tant, requereix JRE[^1] per funcionar.

Com que Plazma està basat en la plataforma oficial de servidors de Mojang Studios[^2], també cal instal·lar JRE per utilitzar Plazma.

### 1.1 Comprovar si JRE està instal·lat

Per verificar si JRE està instal·lat al sistema, introduïu [`cmd /k java --version`](#user-content-fn-4)[^4] a la finestra d'execució i executeu-la.

Si es mostra el següent, salteu al [pas 2](setup.md#id-2).

{% code title="Sortida correcta" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Entorn d'execució Zulu21.32+17-CA (compilació 21.0.2+13-LTS)
OpenJDK Màquina virtual de servidor de 64 bits Zulu21.32+17-CA (compilació 21.0.2+13-LTS, mode mixt, compartit)
```

{% endcode %}

Si no es mostra així, o es mostra com a continuació, vol dir que JRE no està instal·lat o és massa antic, per tant, heu de seguir el [pas 1.2](setup.md#id-1.2).

{% code title="JRE no està instal·lat" lineNumbers="true" %}

```log
'java' no és un comandament intern o extern, un programa executable o un
fitxer de processament per lots.
```

{% endcode %}

{% code title="JRE està massa antic" lineNumbers="true" %}

```log
Opció no reconeguda: --versió
Error: No s'ha pogut crear la Màquina Virtual Java.
Error: Ha succeït una excepció fatal. El programa sortirà.
```

{% endcode %}

### 1.2 Instal·lar JRE

En aquesta guia, farem servir Azul Zulu com una de les opcions de JRE[^5].

Un cop instal·lat, torneu a fer el [pas 1.1](setup.md#id-1.1) per comprovar que la instal·lació s'ha completat correctament.

{% tabs %}

{% tab title="Windows" %}

1. Primer, des de [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) baixeu **JDK 21** en format `.msi`.
2. Executeu l'assistent d'instal·lació descarregat i feu clic a 'Següent'.
3. Un cop activat 'Set JAVA_HOME variable' al menú central esquerre, feu clic a 'Següent'.
4. Feu clic a 'Instal·la' per completar la instal·lació de JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) després de descarregar el **JDK 21** en format `.dmg` des de l'assistent d'instal·lació i executar-lo per instal·lar JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Primer, executeu la següent comanda al terminal per afegir el repositori Azul Zulu a APT.

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

Podeu instal·lar JRE amb la següent comanda.

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

**En la majoria dels casos, feu servir `Reobf Paperclip`.**

El següent és per a desenvolupadors o aquells interessats en les característiques de cada tipus.\
Si ets un usuari comú, no hi ha cap problema en saltar al [pas 3](setup.md#id-3).

{% endhint %}

<details>

<summary>Més informació</summary>

El nom del fitxer executable és `plazma-(gestor de versions)-1.20.4-R0.1-SNAPSHOT-(format de mapeig).jar`.

- **Format de mapeig**\
  El mapeig és una mena de mapa que connecta el codi real de Minecraft amb el codi ofuscado.
  - **Reobf**\
    Reobfuscat (reobfuscació), també conegut com a Spigot mapeig, s'utilitza principalment en la majoria dels plugins NMS.\
    S'aturarà d'utilitzar-se a partir de la versió 1.20.5.
  - **Mojmap**\
    Mapeig de Mojang, és el mapeig del Minecraft de la vanila.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 [생성](#user-content-fn-7)[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Podeu descarregar l'script d'inici fent clic al botó de descàrrega a la part inferior esquerra.\
**Assegureu-vos que l'script d'inici descarregat és compatible amb el vostre sistema operatiu.**

***

## 4. Neteja de fitxers

Ara, mou l'script d'inici descarregat i Plazma a una nova carpeta.

{% hint style="warning" %}

**El nom de la carpeta ha de ser sense espais i en anglès.**

En cas contrari, Plazma o JRE podrien no funcionar correctament.

{% endhint %}

Ara executeu l'script d'inici. En el cas de Windows, en la finestra de selecció de permisos del firewall, heu de seleccionar **Permetre** obligatòriament.

***

## 5. Acceptar l'EULA

Després d'executar l'script d'inici, es crearà un fitxer `eula.txt` a la carpeta.

L'EULA[^9] és un acord de llicència que has d'acceptar per utilitzar els serveis de [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 [제재](#user-content-fn-11)[^11]를 받을 수 있습니다.

{% endhint %}

Per acceptar l'EULA, canvieu `eula=false` a `eula=true` al fitxer `eula.txt` i deseu-lo.

***

## 6. Permetre connexions externes (Windows)

Els sistemes operatius moderns bloquegen els accessos externs per seguretat mitjançant el **firewall** i el **encaminador**.

En el cas de Windows, com ja heu permès en el [pas 3](setup.md#id-3), només cal fer el reenviament de ports.

{% hint style="info" %}

**Aquesta guia està redactada assumint que feu servir el sistema operatiu Windows i teniu un router que permet [UPnP](#user-content-fn-12)[^12].**

Si l'encaminador no suporta UPnP, heu de cercar informació específica per a cada encaminador, ja que cada panell és diferent.

També podeu generar una adreça temporal amb [Ngrok](https://ngrok.com/).
{% endhint %}

{% hint style="warning" %}

**En sistemes operatius basats en UNIX com Linux o macOS, les instruccions per configurar el firewall varien segons el servei, caldrà buscar informació específica.**

{% endhint %}

### 6.1 Comprovar si cal fer reenviament de ports

Introduïu la següent comanda a l'execució i executeu-la.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Si la sortida és `Verdader`, ja podeu acabar, però si és `Fals`, cal configurar el reenviament de ports.

### 6.2 Connectar-se al servidor

{% tabs %}

{% tab title="Connexió des de l'exterior" %}

Si no cal fer reenviament de ports o ja heu reenviat els ports amb èxit, ja podeu connectar-vos al servidor.

L'adreça utilitzada per connectar-se al servidor es pot trobar [aquí](https://ip.pe.kr/).

{% endtab %}

{% tab title="Intent de reenviament de ports amb UPnP" %}

Al fitxer `purpur.yml` de la carpeta del servidor, activa `network.upnp-port-forwarding` com a `true`.

A continuació, en reiniciar el servidor, Plazma intentarà reenviar automàticament els ports.

A continuació es mostra l'estat de l'èxit del UPnP segons el missatge que es mostra a la consola, que es visualitzarà com a `[UPnP] (missatge)`.

| Missatge                                 | Significat                                               |
| ---------------------------------------- | -------------------------------------------------------- |
| `S'ha obert correctament el port (port)` | Reenviament de ports reeixit.            |
| `El port (port) ja està obert`           | Un altre servei està utilitzant el port. |
| `Error en obrir el port (port)`          | Reenviament de ports fallit.             |
| `El servei no està disponible`           | El router no suporta UPnP.               |

Quan el servidor es tanca, Plazma tanca automàticament el port.

{% endtab %}

{% tab title="Crear una adreça temporal amb Ngrok" %}

L'ús de Ngrok és útil per a proves temporals, jocs col·laboratius o jugar amb amics.

1. Baixeu el fitxer ZIP de `Windows (64-bit)` des de la [pàgina web de Ngrok](https://ngrok.com/download).
2. Col·loqueu l'arxiu Ngrok descarregat a la carpeta del servidor.
3. A la [pàgina web de Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) genereu un token d'autenticació.
4. Executeu la comanda que es mostra a la finestra `Command Line` de la carpeta del servidor.
5. Afegiu `start /b ngrok tcp --region jp 25565` a la part superior de l'script d'inici i `taskkill /f /t /im ngrok.exe` a la part inferior.
6. A la part superior de la consola, l'adreça `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` serà l'adreça del servidor.
7. Ara podeu connectar-vos des de l'extern utilitzant aquesta adreça.

{% endtab %}

{% tab title="Connexió des de local" %}

Si vols connectar-te al servidor des de local, pots utilitzar la finestra d'execució per accedir a la `Direcció IPv4` que es mostra en executar `cmd /k ipconfig`.

Per exemple, si després d'executar la comanda es mostra el següent:

```log
Windows IP configuració

Adaptador d'Ethernet Ethernet:

    Sufix de DNS connectat. . . . :
    Adreça IPv4. . . . . . . . . : 192.168.3.7
    Màscara de subxarxa . . . . . . . : 255.255.255.0
    Passarel·la predeterminada . . . . . . : 192.168.3.1

```

Podeu connectar-vos al servidor des de l'ordinador local utilitzant l'adreça IPv4 indicada com a `192.168.3.7`.

Si el servidor i el joc s'estan executant al mateix PC, podeu connectar-vos utilitzant `localhost`.

{% endtab %}
{% endtabs %}

## 7. 발전하기

Si heu iniciat el servidor amb èxit i aquest funciona correctament, ara és moment de personalitzar-lo.

Consulteu la guia següent per aprendre com personalitzar el servidor.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
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
