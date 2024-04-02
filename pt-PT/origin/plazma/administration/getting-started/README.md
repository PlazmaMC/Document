---
description: Saiba como criar um servidor com Plazma.
---

# 👟 Começar

Para usar o Plazma de forma estável, o sistema deve atender aos seguintes requisitos.

|                         | Mínimo | Recomendado |
| :---------------------: | -----: | ----------: |
|       Arquitetura       |    x64 |           - |
|           RAM           |    8GB |        16GB |
| Espaço de armazenamento |    1GB |         8GB |
|           JRE           |     17 |          21 |

Para facilitar a edição de arquivos de configuração, é recomendável instalar um editor como o [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalação do JRE

Como o nome sugere, o Minecraft: **"Java"** Edition é desenvolvido em Java e requer o JRE[^1] para ser executado.

Como o Plazma é baseado na plataforma oficial de servidores da Mojang Studios, também é necessário instalar o JRE para usar o Plazma.

### 1.1 Verificação do JRE

Para verificar se o JRE está instalado no sistema, digite [`cmd /k java --version`](#user-content-fn-4)[^4] na janela de execução e execute.

Se for exibido como abaixo, prossiga para o [passo 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Se não for exibido como acima, ou se for exibido como abaixo, significa que o JRE não está instalado ou está desatualizado, então você precisa seguir o [passo 1.2](setup.md#id-1.2).

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

### 1.2 Instalação do JRE

Neste guia, usaremos o Azul Zulu como uma das [opções de JRE](#user-content-fn-5)[^5].

Após a instalação, verifique novamente o [passo 1.1](setup.md#id-1.1) para garantir que a instalação foi concluída corretamente.

{% tabs %}

{% tab title="Windows" %}

1. Primeiro, faça o download do **JDK 21** em formato `.msi` do [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Execute o assistente de instalação baixado e clique em `Next`.
3. Ative `Set JAVA_HOME variable` no menu exibido no centro esquerdo da janela e clique em `Next`.
4. Clique em `Install` para concluir a instalação do JRE.

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

Em seguida, execute o seguinte comando no terminal para instalar o JRE.

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

## 2. Download do Plazma

O Plazma oferece vários tipos de arquivos de execução.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

As informações a seguir são para desenvolvedores ou aqueles interessados nas características de cada tipo.\
Se você é um usuário comum, não há problema em pular para o [passo 3](setup.md#id-3).

{% endhint %}

<details>

<summary>Saiba mais</summary>

O nome do arquivo de execução é `plazma-(gerenciador de versão)-1.20.4-R0.1-SNAPSHOT-(tipo de mapeamento).jar`.

- **Tipo de mapeamento**\
  O mapeamento é uma espécie de mapa que conecta o código real do Minecraft ao código ofuscado.
  - **Reobf**\
    Reobfuscation, também conhecido como mapeamento Spigot, é amplamente utilizado em plugins NMS.\
    A partir da versão 1.20.5, seu uso será descontinuado.
  - **Mojmap**\
    Mapeamento da Mojang, é o mapeamento do Minecraft Vanilla.
- **Gerenciador de versão**\
  O gerenciador de versão pode ser considerado o lançador do servidor, que é responsável por fornecer as bibliotecas necessárias para a execução do servidor e aplicar patches nos arquivos do servidor.
  - **Paperclip**\
    Desenvolvido pela equipe PaperMC para Paper e outras plataformas derivadas, é responsável por baixar bibliotecas e aplicar patches no servidor.
  - **Bundler**\
    Gerenciador de versão do Minecraft Vanilla.

</details>

***

## 3. Criação de script de inicialização

Para iniciar o Plazma facilmente e reiniciar o servidor automaticamente, você precisa criar um [script de inicialização](#user-content-fn-6)[^6].

Você pode gerar o script de inicialização através do [Flags.sh](https://flags.sh).\
Basta inserir a quantidade de memória a ser usada pelo Plazma e o comando será otimizado automaticamente.

Você pode baixar o script de inicialização clicando no botão de download na parte inferior esquerda.\
**Certifique-se de que o script de inicialização baixado corresponda ao seu sistema operacional.**

***

## 4. Organização de arquivos

Agora, mova o script de inicialização baixado e o Plazma para uma nova pasta.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Caso contrário, o Plazma ou o JRE podem não funcionar corretamente.

{% endhint %}

Agora, execute o script de inicialização. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. Aceitação do EULA

Após executar o script de inicialização, um arquivo `eula.txt` será criado na pasta.

O EULA[^9] é um contrato de licença que deve ser aceito ao utilizar os serviços da [Mojang Studios](#user-content-fn-10)[^10].

Se você não aceitar o EULA, não poderá iniciar o servidor e poderá sofrer punições, como a suspensão da conta, por violar o EULA.

Para aceitar o EULA, edite o arquivo `eula.txt` alterando `eula=false` para `eula=true` e salve.

***

## 6. Permitir acesso externo (Windows)

Os sistemas operacionais modernos bloqueiam o acesso externo por padrão para evitar acessos não autorizados através do **firewall** e **roteador**.

No caso do Windows, como foi permitido no [passo 3](setup.md#id-3), basta configurar o redirecionamento de portas.

{% dica estilo="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Se o roteador não suportar UPnP, será necessário pesquisar a configuração específica para cada modelo de roteador.

Também é possível usar o [Ngrok](https://ngrok.com/) para gerar um endereço temporário.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Verificação da necessidade de redirecionamento de porta

Digite o seguinte na janela de execução e execute.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Se a saída for `True`, você pode parar por aqui, mas se for `False`, é necessário configurar o redirecionamento de porta.

### 6.2 Acesso ao servidor

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

O endereço usado para acessar o servidor pode ser verificado [aqui](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Em seguida, ao reiniciar o servidor, o Plazma tentará encaminhar automaticamente a porta.

Abaixo está o resultado do sucesso do UPnP de acordo com a mensagem exibida no console, que será mostrada como `[UPnP] (mensagem)`.

| mensagem                           | significado                         |
| ---------------------------------- | ----------------------------------- |
| `Porta aberta com sucesso (porta)` | Sucesso no encaminhamento de porta. |
| `Porta (porta) já está aberta`     | Outro serviço está usando a porta.  |
| `Falha ao abrir a porta (porta)`   | Falha no encaminhamento de porta.   |
| `Serviço indisponível`             | O roteador não suporta UPnP.        |

Quando o servidor é desligado, o Plazma fecha automaticamente a porta.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Baixe o arquivo ZIP do `Windows (64-bit)` no [site do Ngrok](https://ngrok.com/download).
2. Coloque o Ngrok baixado na pasta do servidor.
3. No [painel do Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), gere um [token de autenticação](#user-content-fn-13)[^13].
4. Execute o comando exibido na linha de comando na pasta do servidor.
5. Adicione `start /b ngrok tcp --region jp 25565` no topo do script de execução e `taskkill /f /t /im ngrok.exe` na parte inferior.
6. A partir do `Encaminhamento tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` exibido no topo do console, `0.tcp.jp.ngrok.io:12345` será o endereço do servidor.
7. Agora é possível acessar o servidor externamente através desse endereço.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Por exemplo, ao obter a seguinte saída após a execução do comando,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Tentando se conectar com o endereço IPv4 indicado `192.168.3.7` permitirá o acesso ao servidor localmente.

Se o servidor e o jogo estiverem sendo executados no mesmo PC, é possível se conectar usando `localhost`.

{% endtab %}
{% endtabs %}

## 7. Fase de evolução

Após iniciar o servidor com sucesso e ele estar funcionando corretamente, é hora de personalizá-lo.

Descubra como personalizar o servidor seguindo o guia abaixo.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
{% endcontent-ref %}

***

[^1]: Ambiente de execução Java, ambiente de execução Java.

[^2]: O Paper, base do Plazma, é baseado no Spigot, que por sua vez é baseado na plataforma oficial de servidores Spigot.

[^3]: Tecla Windows + R

[^4]: No caso do Linux, execute `java --version` no terminal.

[^5]: O JRE é um projeto de código aberto, assim como a plataforma de servidores Minecraft, e possui várias variantes.

[^6]: Comumente conhecido como **launcher**.

[^7]: Ao ativar o "Auto-restart", o servidor reiniciará automaticamente. É possível encerrar digitando `Control + C`.

[^8]: Não é recomendado alocar mais da metade da memória do sistema.

    Por exemplo, se a capacidade total de memória do sistema for de 8GB, não é recomendado alocar mais de 4GB.

[^9]: Contrato de Licença do Usuário Final, EULA. Para mais detalhes, consulte o [site do Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: De acordo com o Artigo 32, Parágrafo 1, Item 9 da Lei de Promoção da Indústria de Jogos da Coreia, é possível processar legalmente a **Microsoft Korea Corporation**.

[^12]: Universal Plug & Play. O Purpur incluído no Plazma se comunica automaticamente com o roteador através dessa tecnologia para abrir a porta apenas quando o servidor está em execução, eliminando a necessidade de encaminhamento de porta direto.

[^13]: Se não tiver uma conta, inscreva-se no Ngrok através de uma conta Google ou GitHub.
