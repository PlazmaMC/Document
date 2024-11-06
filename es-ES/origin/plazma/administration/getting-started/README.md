---
description: Descubra cómo crear un servidor con Plazma.
---

# 👟 Empezar

Para utilizar Plazma de manera estable, el sistema debe cumplir con los siguientes requisitos.

|                           | Mínimo | Recomendado |
| :-----------------------: | ------ | ----------- |
|        Arquitectura       | x64    | -           |
|            RAM            | 8GB    | 16GB        |
| Espacio de almacenamiento | 1GB    | 8GB         |
|            JDK            | 17     | 21          |

Para facilitar la edición de archivos de configuración, también es recomendable instalar un editor como [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Salida correcta" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
Entorno de tiempo de ejecución OpenJDK Zulu21.32+17-CA (compilación 21.0.2+13-LTS)
Servidor VM de 64 bits de OpenJDK Zulu21.32+17-CA (compilación 21.0.2+13-LTS, modo mixto, compartido)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' no es un comando interno o externo, programa ejecutable o archivo por lotes.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Opción no reconocida: --version
Error: No se pudo crear la Máquina Virtual de Java.
Error: Se ha producido una excepción fatal. El programa se cerrará.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. Primero, descargue **JDK 21** de [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) en formato `.msi`.
2. Ejecute el asistente de instalación descargado y haga clic en `Siguiente`.
3. Después de activar `Set JAVA_HOME variable` en el menú mostrado en el centro izquierdo de la ventana, haga clic en `Siguiente`.
4. Presione `Instalar` para completar la instalación de JRE.
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

Luego, ejecute el siguiente comando en la terminal para instalar JRE.

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

## 2. Descarga de Plazma

Plazma ofrece varios archivos ejecutables.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Ver más detalles</summary>

El nombre del archivo ejecutable se establece como `plazma-(administrador de versiones)-1.20.4-R0.1-SNAPSHOT-(formato de mapeo).jar`.

- **Formato de mapeo**\
  El mapeo es una especie de mapa que une el código real de Minecraft con el código ofuscado.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mapeado por Mojang, es el mapeo de Minecraft de vainilla. 1.20.6 이후의 모던 플러그인에서 사용합니다.
- **Administrador de versiones**\
  El administrador de versiones es un lanzador de servidores que proporciona las bibliotecas necesarias para ejecutar el servidor y parchear los archivos del servidor.
  - **Paperclip**\
    Desarrollado por el equipo de PaperMC para Paper y otras plataformas derivadas, se encarga de descargar bibliotecas y aplicar parches al servidor.
  - **Bundler**\
    Administrador de versiones de Minecraft Vanilla.

</details>

***

## 3. Creación de script de inicio

Para iniciar Plazma fácilmente y reiniciar el servidor automáticamente, es necesario crear un [script de inicio](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Puede descargar el script de inicio haciendo clic en el botón de descarga en la esquina inferior izquierda.\
**Asegúrese de que el script descargado sea compatible con su sistema operativo.**

***

## 4. Organización de archivos

Mueva el script de inicio descargado y Plazma a una nueva carpeta.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Ejecute el script de inicio. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Aceptación del EULA

Una vez que ejecute el script de inicio, se creará un archivo `eula.txt` en la carpeta.

El EULA[^9] es un acuerdo de licencia que debe aceptar para utilizar los servicios de [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Para aceptar el EULA, cambie `eula=false` a `eula=true` en el archivo `eula.txt` y guárdelo.

***

## 6. Permitir acceso externo (Windows)

Los sistemas operativos modernos bloquean el acceso externo por defecto con el fin de prevenir accesos no autorizados mediante el **firewall** y el **enrutador**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Si el enrutador no admite UPnP, las instrucciones pueden variar según el modelo del enrutador y se recomienda buscar información específica.

También se puede utilizar [Ngrok](https://ngrok.com/) para generar una dirección temporal.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Verificación de la necesidad de reenvío de puertos

Ingrese y ejecute lo siguiente en la ventana de ejecución.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Si la salida es `True`, no es necesario realizar más acciones. Si es `False`, debe configurar el reenvío de puertos.

### 6.2 Conexión al servidor

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Puede encontrar la dirección utilizada para conectarse al servidor [aquí](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Luego, al reiniciar el servidor, Plazma intentará realizar el reenvío automático de puertos.

A continuación se muestra el resultado del éxito del UPnP según el mensaje mostrado en la consola, que se mostrará como `[UPnP] (mensaje)` en la consola.

| Mensaje                              | Significado                                               |
| ------------------------------------ | --------------------------------------------------------- |
| `Puerto abierto con éxito (puerto)`  | Éxito en el reenvío de puertos.           |
| `El puerto (puerto) ya está abierto` | Otro servicio está utilizando ese puerto. |
| `Error al abrir el puerto (puerto)`  | Fallo en el reenvío de puertos.           |
| `El servicio no está disponible`     | El enrutador no es compatible con UPnP.   |

Cuando el servidor se apaga, Plazma cierra automáticamente el puerto.
{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Descargue el archivo ZIP de `Windows (64-bit)` desde la [página de Ngrok](https://ngrok.com/download).
2. Coloque el Ngrok descargado en la carpeta del servidor.
3. Genere un token de autenticación desde el [tablero de Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Ejecute el comando mostrado en la `Línea de comandos` en la carpeta del servidor.
5. Agregue `start /b ngrok tcp --region jp 25565` en la parte superior del script de ejecución, y `taskkill /f /t /im ngrok.exe` en la parte inferior.
6. En `Reenvío tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` mostrado en la parte superior de la consola, `0.tcp.jp.ngrok.io:12345` será la dirección del servidor.
7. Ahora puede conectarse desde el exterior utilizando esta dirección.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Por ejemplo, si la ejecución del comando muestra una dirección `IPv4` como la siguiente,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Puede intentar conectarse al servidor local utilizando la dirección `192.168.3.7` mostrada en la dirección IPv4.

Si el servidor y el juego se ejecutan en la misma PC, puede conectarse utilizando `localhost`.
{% endtab %}
{% endtabs %}

## 7. 발전하기

Una vez que el servidor se ha iniciado con éxito y está funcionando correctamente, es hora de personalizar el servidor.

Explore a través de este manual cómo personalizar el servidor.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

[^2]: Paper, en el que se basa Plazma, se basa en Spigot, que a su vez se basa en la plataforma oficial del servidor de Spigot.

[^3]: Windows key + R

[^4]: Para Linux, use `java --version` en la terminal.

[^5]: JRE es un proyecto de código abierto con múltiples variantes, al igual que las plataformas de servidores de Minecraft.

[^6]: Comúnmente conocido como **launcher**.

[^7]: Al activar "Auto-reinicio", el servidor se reiniciará automáticamente. Puede detenerlo ingresando `Control + C`.

[^8]: No se recomienda superar la mitad de la capacidad del sistema.

    Por ejemplo, si la capacidad total de memoria del sistema es de 8GB, no se recomienda configurar más de 4GB.

[^9]: Acuerdo de Licencia para el Usuario Final, EULA. Consulte el [sitio web de Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines) para obtener más información.

[^10]: Corporación Microsoft.

[^11]: Según el Artículo 32, Párrafo 1, Punto 9 de la Ley de Promoción de la Industria de Juegos de la República de Corea, **Korea Microsoft Corporation** tiene el derecho de presentar una demanda legal.

[^12]: Universal Plug & Play. Purpur incluido en Plazma se comunica automáticamente con el enrutador a través de esta tecnología para abrir puertos solo cuando el servidor está en funcionamiento, eliminando la necesidad de reenvío de puertos directo.

[^13]: Si no tiene una cuenta, regístrese en Ngrok a través de una cuenta de Google o GitHub.
