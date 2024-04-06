---
description: Saiba como criar um servidor com Plazma.
---

# 👟 Começar

Para usar o Plazma de forma estável, o sistema deve atender aos seguintes requisitos.

|                         | Mínimo | Recomendado |
| :---------------------: | :----- | :---------- |
|       Arquitetura       | x64    | -           |
|           RAM           | 8GB    | 16GB        |
| Espaço de armazenamento | 1GB    | 8GB         |
|           JRE           | 17     | 21          |

Para facilitar a edição de arquivos de configuração, é recomendável instalar um editor como o [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalação do JRE

Como o nome sugere, o Minecraft: **"Java"** Edition é desenvolvido em Java e requer o JRE[^1] para ser executado.

Como o Plazma é baseado na plataforma oficial de servidores da Mojang Studios, também é necessário instalar o JRE para usar o Plazma.

### 1.1 Verificação do JRE

Para verificar se o JRE está instalado no sistema, digite [`cmd /k java --version`](#user-content-fn-4)[^4] na janela de execução e execute.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Saída correta" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE não está instalado" lineNumbers="true" %}

```log
'java' não é reconhecido como um comando interno ou externo, um programa operável ou um arquivo em lotes.
```

{% endcode %}

{% code title="JRE está desatualizado" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Instalação do JRE

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. Primeiro, faça o download do **JDK 21** em formato `.msi` do [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Execute o assistente de instalação baixado e clique em `Next`.
3. Ative `Set JAVA_HOME variable` no menu exibido no centro esquerdo da janela e clique em `Next`.
4. Clique em `Install` para concluir a instalação do JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) instale **JDK 21** do Azul Zulu em formato `.dmg` baixando o assistente de instalação e executando para instalar o JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Primeiramente, execute o seguinte comando no terminal para adicionar o repositório Azul Zulu ao APT.

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

Você pode instalar o JRE inserindo o seguinte comando.

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

**Na maioria dos casos, use `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Saiba mais</summary>

O nome do arquivo de execução é `plazma-(gerenciador de versão)-1.20.4-R0.1-SNAPSHOT-(tipo de mapeamento).jar`.

- **Tipo de mapeamento**\
  O mapeamento é uma espécie de mapa que conecta o código real do Minecraft ao código ofuscado.
  - **Reobf**\
    Reobfuscated (재난독화), também conhecido como mapeamento Spigot, é amplamente utilizado na maioria dos plugins NMS.\
    Está previsto que será descontinuado a partir da versão 1.20.5.
  - **Mojmap**\
    Mapeado pela Mojang, é o mapeamento padrão do Minecraft vanilla.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 [생성](#user-content-fn-7)[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Você pode baixar o script de inicialização clicando no botão de download na parte inferior esquerda.\
**Certifique-se de que o script de inicialização baixado corresponda ao seu sistema operacional.**

***

## 4. Organização de arquivos

Agora, mova o script de inicialização baixado e o Plazma para uma nova pasta.

{% hint style="warning" %}

**O nome da pasta não deve conter espaços e deve ser configurado em inglês.**

Caso contrário, o Plazma ou o JRE podem não funcionar corretamente.

{% endhint %}

Agora, execute o script de inicialização. Para o Windows, <mark style="background-color:orange;">na janela de seleção de permissão do firewall, selecione **Permitir** obrigatoriamente</mark>.

***

## 5. Aceitação do EULA

Após executar o script de inicialização, um arquivo `eula.txt` será criado na pasta.

O EULA[^9] é um contrato de licença que deve ser aceito ao utilizar os serviços da [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 [제재](#user-content-fn-11)[^11]를 받을 수 있습니다.

{% endhint %}

Para aceitar o EULA, edite o arquivo `eula.txt` alterando `eula=false` para `eula=true` e salve.

***

## 6. Permitir acesso externo (Windows)

Os sistemas operacionais modernos bloqueiam o acesso externo por padrão para evitar acessos não autorizados através do **firewall** e **roteador**.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% dica estilo="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Se o roteador não suportar UPnP, será necessário pesquisar a configuração específica para cada modelo de roteador.

Também é possível usar o [Ngrok](https://ngrok.com/) para gerar um endereço temporário.
{% endhint %}

{% hint style="warning" %}

**Para sistemas operacionais baseados em UNIX, como Linux ou macOS, os métodos de configuração do firewall variam de acordo com o serviço, portanto, é necessário pesquisar diretamente.**

{% endhint %}

### 6.1 Verificação da necessidade de redirecionamento de porta

Digite o seguinte na janela de execução e execute.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Se a saída for `True`, você pode parar por aqui, mas se for `False`, é necessário configurar o redirecionamento de porta.

### 6.2 Acesso ao servidor

{% tabs %}

{% tab title="Acesso externo" %}

Se não for necessário encaminhamento de porta, ou se o encaminhamento de porta já foi configurado com sucesso, agora você pode se conectar ao servidor.

O endereço usado para acessar o servidor pode ser verificado [aqui](https://ip.pe.kr/).

{% endtab %}

{% tab title="Tentativa de encaminhamento de porta com UPnP" %}

No `purpur.yml` da pasta do servidor, ative `network.upnp-port-forwarding` para `true`.

Em seguida, ao reiniciar o servidor, o Plazma tentará encaminhar automaticamente a porta.

Abaixo está o resultado do sucesso do UPnP de acordo com a mensagem exibida no console, que será mostrada como `[UPnP] (mensagem)`.

| mensagem                           | significado                                         |
| ---------------------------------- | --------------------------------------------------- |
| `Porta aberta com sucesso (porta)` | Sucesso no encaminhamento de porta. |
| `Porta (porta) já está aberta`     | Outro serviço está usando a porta.  |
| `Falha ao abrir a porta (porta)`   | Falha no encaminhamento de porta.   |
| `Serviço indisponível`             | O roteador não suporta UPnP.        |

Quando o servidor é desligado, o Plazma fecha automaticamente a porta.

{% endtab %}

{% tab title="Geração de endereço temporário com Ngrok" %}

O método com Ngrok é útil para testes temporários, jogar com amigos ou em modo multiplayer.

1. Baixe o arquivo ZIP do `Windows (64-bit)` no [site do Ngrok](https://ngrok.com/download).
2. Coloque o Ngrok baixado na pasta do servidor.
3. No [painel do Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), gere um [token de autenticação](#user-content-fn-13)[^13].
4. Execute o comando exibido na linha de comando na pasta do servidor.
5. Adicione `start /b ngrok tcp --region jp 25565` no topo do script de execução e `taskkill /f /t /im ngrok.exe` na parte inferior.
6. A partir do `Encaminhamento tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` exibido no topo do console, `0.tcp.jp.ngrok.io:12345` será o endereço do servidor.
7. Agora é possível acessar o servidor externamente através desse endereço.

{% endtab %}

{% tab title="Conexão local" %}

Se estiver tentando se conectar ao servidor localmente, você pode usar o `endereço IPv4` exibido ao executar `cmd /k ipconfig` na janela de execução.

Por exemplo, ao obter a seguinte saída após a execução do comando,

```log
Configuração de IP do Windows

Adaptador Ethernet Ethernet:

    Sufixo DNS específico de conexão. . . . :
    Endereço IPv4. . . . . . . . . : 192.168.3.7
    Máscara de sub-rede. . . . . . . : 255.255.255.0
    Gateway Padrão. . . . . . . : 192.168.3.1

```

Tentando se conectar com o endereço IPv4 indicado `192.168.3.7` permitirá o acesso ao servidor localmente.

Se o servidor e o jogo estiverem sendo executados no mesmo PC, é possível se conectar usando `localhost`.

{% endtab %}
{% endtabs %}

## 7. 발전하기

Após iniciar o servidor com sucesso e ele estar funcionando corretamente, é hora de personalizá-lo.

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
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
