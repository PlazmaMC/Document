---
description: Descubra como criar um servidor com Plazma.
---

# 👟 Começando

Para usar o Plazma de forma estável, o sistema deve atender aos seguintes requisitos.

|                         | Mínimo | Recomendado |
| :---------------------: | :----- | :---------- |
|       Arquitetura       | x64    | -           |
|           RAM           | 8GB    | 16GB        |
| Espaço de armazenamento | 1GB    | 8GB         |
|           JRE           | 17     | 21          |

Para facilitar a edição dos arquivos de configuração, é recomendável instalar um editor como o [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalação do JRE

Como o nome sugere, o Minecraft: **"Java"** Edition é desenvolvido em Java e requer o JRE[^1] para ser executado.

Como o Plazma é baseado na plataforma oficial de servidores da Mojang Studios[^2], também é necessário instalar o JRE para usar o Plazma.

### 1.1 Verificação da existência do JRE

Para verificar se o JRE está instalado no sistema, digite [`cmd /k java --version`](#user-content-fn-4)[^4] na janela de execução.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Saída Correta" lineNumbers="true" %}

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

1. Primeiramente, faça o download do **JDK 21** em formato `.msi` do [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Execute o assistente de instalação baixado e clique em `Next`.
3. Ative a opção `Set JAVA_HOME variable` no menu exibido no centro esquerdo da janela e clique em `Next`.
4. Clique em `Install` para concluir a instalação do JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) instala o **JDK 21** baixando e executando o assistente de instalação em formato `.dmg` para instalar o JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Adicione o repositório Azul Zulu ao APT executando o seguinte comando no terminal.

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

Você pode instalar o JRE executando o seguinte comando.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Download do Plazma

O Plazma oferece diversos tipos de arquivos executáveis.

{% hint style="warning" %}

**Na maioria dos casos, use `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Saiba mais</summary>

O nome do arquivo executável é `plazma-(gerenciador de versão)-1.20.4-R0.1-SNAPSHOT-(tipo de mapeamento).jar`.

- **Tipo de mapeamento**\
  O mapeamento é uma espécie de mapa que liga o código real do Minecraft ao código ofuscado.
  - **Reobf**\
    Reobfuscated (reofuscado), também conhecido como mapeamento Spigot, é amplamente utilizado na maioria dos plugins NMS.\
    Está previsto que será descontinuado a partir da versão 1.20.5.
  - **Mojmap**\
    Mapeado pela Mojang, é o mapeamento do Minecraft vanilla.
- **Gerenciador de versão**\
  O gerenciador de versão é uma espécie de lançador do servidor que é necessário para executar o servidor e aplicar patches nos arquivos do servidor.
  - **Paperclip**\
    Desenvolvido pela equipe do PaperMC para Paper e outras plataformas derivadas, é responsável por baixar bibliotecas e aplicar patches no servidor.
  - **Bundler**\
    Gerenciador de versão do Minecraft Vanilla.

</details>

***

## 3. Criação do script de inicialização

Para iniciar o Plazma facilmente e reiniciar o servidor automaticamente, é necessário criar um [script de inicialização](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh) permite a criação de scripts de inicialização através do [generate](#user-content-fn-7)[^7]. Ao inserir apenas a [quantidade de memória a ser usada](#user-content-fn-8)[^8] no Plazma, o comando é otimizado automaticamente.

Você pode baixar o script de inicialização clicando no botão de download na parte inferior esquerda.\
**Certifique-se de que o script de inicialização baixado corresponde ao seu sistema operacional.**

***

## 4. Organização dos arquivos

Agora, mova o script de inicialização e o Plazma para uma nova pasta.

{% hint style="warning" %}

**O nome da pasta deve ser sem espaços e em inglês.**

Caso contrário, o Plazma ou o JRE podem não funcionar corretamente.

{% endhint %}

Agora, execute o script de inicialização. No caso do Windows, <mark style="background-color:orange;">Na janela de seleção de permissão do firewall, selecione **Permitir** obrigatoriamente</mark>.

***

## 5. Aceitação do EULA

Após executar o script de inicialização, um arquivo `eula.txt` será criado na pasta.

O EULA[^9] é um contrato de licença que você deve concordar ao usar os serviços da [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

Se não concordar, não será possível iniciar o servidor e poderá receber [sanções](#user-content-fn-11)[^11] como suspensão da conta por violação do EULA.

{% endhint %}

Para concordar com o EULA, edite o arquivo `eula.txt` de `eula=false` para `eula=true` e salve.

***

## 6. Permitindo acesso externo (Windows)

Os sistemas operacionais modernos bloqueiam o acesso externo por padrão com o uso de **firewalls** e **roteadores** para impedir acessos não autorizados.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Se o roteador não suportar UPnP, você precisará pesquisar as configurações específicas de cada modelo.

Você também pode usar o [Ngrok](https://ngrok.com/) para gerar um endereço temporário.
{% endhint %}

{% hint style="warning" %}

**Para sistemas operacionais baseados em UNIX, como Linux ou macOS, os métodos de configuração do firewall variam para cada serviço, portanto, você deve pesquisar por conta própria.**

{% endhint %}

### 6.1 Verificação da necessidade de encaminhamento de porta

Digite o seguinte comando na janela de execução e execute.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Se a saída for `True`, não é necessário fazer mais nada. Se for `False`, é necessário configurar o encaminhamento de porta.

### 6.2 Acessar o servidor

{% tabs %}

{% tab title="Acesso Externo" %}

Se não for necessário encaminhamento de porta ou se já tiver configurado o encaminhamento de porta com sucesso, agora você pode se conectar ao servidor.

O endereço usado para acessar o servidor pode ser verificado [aqui](https://ip.pe.kr/).

{% endtab %}

{% tab title="Tentativa de Encaminhamento de Porta com UPnP" %}

No arquivo `purpur.yml` da pasta do servidor, ative `network.upnp-port-forwarding` para `true`.

Em seguida, ao reiniciar o servidor, o Plazma tentará automaticamente encaminhar a porta.

Abaixo está o resultado do sucesso do UPnP com base na mensagem exibida no console, que será exibida como `[UPnP] (mensagem)` no console.

| mensagem                           | significado                                         |
| ---------------------------------- | --------------------------------------------------- |
| `Porta aberta com sucesso (porta)` | Sucesso no encaminhamento de porta. |
| `Porta (porta) já está aberta`     | Outro serviço está usando a porta.  |
| `Falha ao abrir porta (porta)`     | Falha no encaminhamento de porta.   |
| `Serviço indisponível`             | O roteador não suporta UPnP.        |

Quando o servidor é encerrado, o Plazma automaticamente fecha a porta.

{% endtab %}

{% tab title="Criação de Endereço Temporário com Ngrok" %}

O uso do Ngrok é útil para testes temporários, jogar com amigos ou para jogos colaborativos.

1. Baixe o arquivo ZIP `Windows (64-bit)` do [site do Ngrok](https://ngrok.com/download).
2. Coloque o Ngrok baixado na pasta do servidor.
3. No [painel do Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), gere um [token de autenticação](#user-content-fn-13)[^13].
4. Execute o comando exibido na linha de comando na pasta do servidor.
5. Adicione `start /b ngrok tcp --region jp 25565` no início do script de execução e `taskkill /f /t /im ngrok.exe` no final.
6. A partir da mensagem exibida no topo do console `Encaminhando tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`, `0.tcp.jp.ngrok.io:12345` será o endereço do servidor.
7. Agora você pode acessar o servidor externamente através desse endereço.

{% endtab %}

{% tab title="Acesso Local" %}

Se estiver tentando acessar o servidor localmente, você pode se conectar usando o `Endereço IPv4` mostrado ao executar `cmd /k ipconfig` na janela de comando.

Por exemplo, se após a execução do comando você vir:

```log
Configuração de IP do Windows

Adaptador Ethernet Ethernet:

    Sufixo DNS específico de conexão. . . . :
    Endereço IPv4. . . . . . . . . : 192.168.3.7
    Máscara de sub-rede. . . . . . . : 255.255.255.0
    Gateway Padrão. . . . . . . : 192.168.3.1

```

Você pode acessar o servidor localmente usando o `192.168.3.7` mostrado como o Endereço IPv4.

Se o servidor e o jogo estiverem sendo executados no mesmo PC, você pode acessar usando `localhost`.

{% endtab %}
{% endtabs %}

## 7. Crescer

Se o servidor foi iniciado com sucesso e está funcionando corretamente, agora é hora de personalizar o servidor.

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Ambiente de Execução Java.

[^2]: O Paper, base do Plazma, é baseado no Spigot, que por sua vez é baseado na plataforma oficial do servidor Spigot.

[^3]: Tecla Windows + R

[^4]: Para Linux, execute `java --version` no terminal.

[^5]: O JRE é um dos projetos de código aberto e existem várias variantes, assim como no caso da plataforma de servidores Minecraft.

[^6]: Comumente conhecido como **launcher**.

[^7]: Ativar o "Auto-restart" fará com que o servidor reinicie automaticamente. Você pode encerrar digitando `Control + C`.

[^8]: Não é recomendado ultrapassar metade da capacidade do sistema.

    Por exemplo, se a capacidade total de memória do sistema for de 8GB, não é recomendado configurar mais de 4GB.

[^9]: Contrato de Licença do Usuário Final, EULA. Consulte o [site do Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines) para mais informações.

[^10]: Microsoft Corporation.

[^11]: De acordo com o Artigo 32, Parágrafo 1, Item 9 da Lei de Promoção da Indústria de Jogos da Coreia, a **Microsoft Korea Co., Ltd.** pode ser processada legalmente.

[^12]: Universal Plug & Play. O Purpur incluído no Plazma se comunica automaticamente com o roteador através dessa tecnologia para abrir a porta somente quando o servidor está em execução, eliminando a necessidade de encaminhamento de porta direto.

[^13]: Se você não tem uma conta, registre-se no Ngrok usando uma conta do Google ou GitHub.
