---
description: Descubra como criar um servidor com Plazma.
---

# 👟 Começando

Para usar o Plazma de forma estável, o sistema deve atender aos seguintes requisitos.

|                         | Mínimo | Recomendado |
| :---------------------: | -----: | ----------: |
|       Arquitetura       |    x64 |           - |
|           RAM           |    8GB |        16GB |
| Espaço de armazenamento |    1GB |         8GB |
|           JRE           |     17 |          21 |

Para facilitar a edição dos arquivos de configuração, é recomendável instalar um editor como o [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalação do JRE

Como o nome sugere, o Minecraft: **"Java"** Edition é desenvolvido em Java e requer o JRE[^1] para ser executado.

Como o Plazma é baseado na plataforma oficial de servidores da Mojang Studios[^2], também é necessário instalar o JRE para usar o Plazma.

### 1.1 Verificação da existência do JRE

Para verificar se o JRE está instalado no sistema, digite [`cmd /k java --version`](#user-content-fn-4)[^4] na janela de execução.

Se a saída for como abaixo, pule para o [passo 2](setup.md#id-2).

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Se a saída for diferente ou se for como abaixo, o JRE não está instalado ou está desatualizado, então você precisa executar o [passo 1.2](setup.md#id-1.2).

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

Neste guia, utilizaremos o Azul Zulu como [uma das opções](#user-content-fn-5)[^5] de JRE.

Após a instalação, verifique se a instalação foi concluída corretamente executando novamente o [passo 1.1](setup.md#id-1.1).

{% tabs %}

{% tab title="Windows" %}

1. Primeiramente, faça o download do **JDK 21** em formato `.msi` do [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu).
2. Execute o assistente de instalação baixado e clique em `Next`.
3. Ative a opção `Set JAVA_HOME variable` no menu exibido no centro esquerdo da janela e clique em `Next`.
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

O Plazma oferece diversos tipos de arquivos executáveis.

{% hint style="warning" %}

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

As informações a seguir são para desenvolvedores ou curiosos sobre as características de cada tipo.\
Se você é um usuário comum, não há problema em pular para o [passo 3](setup.md#id-3).

{% endhint %}

<details>

<summary>Saiba mais</summary>

O nome do arquivo executável é `plazma-(gerenciador de versão)-1.20.4-R0.1-SNAPSHOT-(tipo de mapeamento).jar`.

- **Tipo de mapeamento**\
  O mapeamento é uma espécie de mapa que liga o código real do Minecraft ao código ofuscado.
  - **Reobf**\
    Reobfuscation, também conhecido como mapeamento Spigot, é amplamente utilizado em plugins NMS.\
    A partir da versão 1.20.5, seu uso será descontinuado.
  - **Mojmap**\
    Mapeamento da Mojang, é o mapeamento do Minecraft Vanilla.
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

Você pode criar o script de inicialização através do [Flags.sh](https://flags.sh). Basta inserir a [memória a ser usada pelo Plazma](#user-content-fn-8)[^8] e o comando será otimizado automaticamente.

Você pode baixar o script de inicialização clicando no botão de download na parte inferior esquerda.\
**Certifique-se de que o script de inicialização baixado corresponde ao seu sistema operacional.**

***

## 4. Organização dos arquivos

Agora, mova o script de inicialização e o Plazma para uma nova pasta.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Caso contrário, o Plazma ou o JRE podem não funcionar corretamente.

{% endhint %}

Agora, execute o script de inicialização. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. Aceitação do EULA

Após executar o script de inicialização, um arquivo `eula.txt` será criado na pasta.

O EULA[^9] é um contrato de licença que você deve concordar ao usar os serviços da [Mojang Studios](#user-content-fn-10)[^10].

Se você não concordar com o EULA, não poderá iniciar o servidor e poderá receber penalidades, como a suspensão da conta, por violar o EULA.

Para concordar com o EULA, edite o arquivo `eula.txt` de `eula=false` para `eula=true` e salve.

***

## 6. Permitindo acesso externo (Windows)

Os sistemas operacionais modernos bloqueiam o acesso externo por padrão com o uso de **firewalls** e **roteadores** para impedir acessos não autorizados.

No Windows, como você já permitiu no [passo 3](setup.md#id-3), basta encaminhar as portas.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Se o roteador não suportar UPnP, você precisará pesquisar as configurações específicas de cada modelo.

Você também pode usar o [Ngrok](https://ngrok.com/) para gerar um endereço temporário.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Verificação da necessidade de encaminhamento de porta

Digite o seguinte comando na janela de execução e execute.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Se a saída for `True`, não é necessário fazer mais nada. Se for `False`, é necessário configurar o encaminhamento de porta.

### 6.2 Acessar o servidor

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

O endereço usado para acessar o servidor pode ser verificado [aqui](https://ip.pe.kr/).

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Em seguida, ao reiniciar o servidor, o Plazma tentará automaticamente encaminhar a porta.

Abaixo está o resultado do sucesso do UPnP com base na mensagem exibida no console, que será exibida como `[UPnP] (mensagem)` no console.

| mensagem                           | significado                         |
| ---------------------------------- | ----------------------------------- |
| `Porta aberta com sucesso (porta)` | Sucesso no encaminhamento de porta. |
| `Porta (porta) já está aberta`     | Outro serviço está usando a porta.  |
| `Falha ao abrir porta (porta)`     | Falha no encaminhamento de porta.   |
| `Serviço indisponível`             | O roteador não suporta UPnP.        |

Quando o servidor é encerrado, o Plazma automaticamente fecha a porta.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Baixe o arquivo ZIP `Windows (64-bit)` do [site do Ngrok](https://ngrok.com/download).
2. Coloque o Ngrok baixado na pasta do servidor.
3. No [painel do Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken), gere um [token de autenticação](#user-content-fn-13)[^13].
4. Execute o comando exibido na linha de comando na pasta do servidor.
5. Adicione `start /b ngrok tcp --region jp 25565` no início do script de execução e `taskkill /f /t /im ngrok.exe` no final.
6. A partir da mensagem exibida no topo do console `Encaminhando tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565`, `0.tcp.jp.ngrok.io:12345` será o endereço do servidor.
7. Agora você pode acessar o servidor externamente através desse endereço.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Por exemplo, se após a execução do comando você vir:

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Você pode acessar o servidor localmente usando o `192.168.3.7` mostrado como o Endereço IPv4.

Se o servidor e o jogo estiverem sendo executados no mesmo PC, você pode acessar usando `localhost`.

{% endtab %}
{% endtabs %}

## 7. Fase de desenvolvimento

Se o servidor foi iniciado com sucesso e está funcionando corretamente, agora é hora de personalizar o servidor.

Saiba como personalizar o servidor seguindo o guia abaixo.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
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
