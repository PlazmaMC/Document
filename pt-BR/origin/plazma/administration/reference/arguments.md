---
description: Descubra sobre os argumentos iniciais e as propriedades do sistema.
---

# 🎛️ Argumentos e Propriedades

O início da aquisição e as propriedades do sistema são valores adicionados ao comando usado na execução do Plazma, que têm um impacto geral na operação do Plazma.

[Posição anexada ao comando](#user-content-fn-2)[^2] irá dividir-se em **Argumento Inicial** e **Propriedades do Sistema**.

***

## Propriedades do Sistema <a href="#id-1" id="id-1"></a>

As propriedades do sistema são valores processados pelo JVM antes da inicialização do Plazma, inseridos antes do `-jar`.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Modo de Uso <a href="#id-1.1" id="id-1.1"></a>

As propriedades do sistema são inseridas como argumentos Java entre `java` e `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indica que o argumento não é integrado ao JVM, sendo um argumento exclusivo do Plazma,

Se nenhum valor for inserido nas propriedades, o valor será fixado como [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Todas as Propriedades do Sistema <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Atualiza o formato de placas desativadas.

#### `debug.entities`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Ativa os logs de depuração das informações das entidades.

#### `debug.rewriteForIDE`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa a revisão de NMS para permitir que as informações sejam corretamente carregadas no IDE e remapeia automaticamente as informações de versão interna.

#### `disable.watchdog`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa o sistema de alerta do Watchdog do Spigot.

#### `letMeReload`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa a mensagem de confirmação do comando `/reload`.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Se você é um desenvolvedor de plugins e precisa atualizá-los, utilize o hotswap ao invés do `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa plugins que usam o sistema de entrada e saída padrão.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Adverte quando um formato desativado é detectado nos componentes de chat.

#### `Paper.bypassHostCheck`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa a verificação de padrão do servidor quando um jogador se conecta.

#### `Paper.debugDynamicMissingKeys`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Ativa logs de depuração para chaves ausentes em objetos NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Ativa logs de depuração para blocos de cabeça com perfis inválidos.

Isso registra todas as cabeças com perfis inválidos no mundo, juntamente com suas posições.

#### `Paper.disableChannelLimit`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa a priorização de classes de plugins.

Útil em situações de problemas com sombreamento de plugins.

#### `Paper.disableFlushConsolidate`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa a consolidação de limpeza do Netty.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Valor Padrão**: `750`

Divide em múltiplos pacotes para transmissão se a entidade exceder o valor definido.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Valor Padrão**: `8192`

Define o tamanho máximo dos pacotes que o servidor pode receber de uma vez.

#### `Paper.ignoreJavaVersion`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa a verificação da versão do Java.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Pode resultar em danos permanentes nos arquivos do mundo e na quebra de todo o mecanismo do jogo.

Quaisquer problemas resultantes do uso dessa configuração são de responsabilidade do usuário, e o Plamza não oferece suporte para isso.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Valor Padrão**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Valor Padrão**: `80`

Define o comprimento máximo de caracteres por linha em placas.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Valor Padrão**: `(versão do mundo) + 1`

Define a versão das informações de atualização do mundo a ser inicializada primeiro.

Útil ao atualizar grandes quantidades de chunks, mas raramente usado em outras situações.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valor Padrão**: `True`

Ativa o processamento de comentários em arquivos YAML.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Valor Padrão**: `30`

Expulsa um jogador se não receber dados por um determinado tempo em segundos.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Ignora os comentários das propriedades do servidor.

#### `Paper.debug-sync-loads`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Ativa logs de depuração para a criação sincronizada de chunks.

#### `Paper.enable-sync-chunk-writes`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Ativa o sistema de criação de chunks padrão do Minecraft.

Isso salva cada chunk sequencialmente, resultando em uma grande perda de desempenho.

#### `Paper.explicit-flush`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Ativa o Flush Explicito do canal de rede.

#### `Paper.strict-thread-checks`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Registra sempre erros que não ocorrem na thread principal.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Exibe um aviso se uma tarefa agendada tiver um atraso excessivo.

#### `Paperclip.patchOnly`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Se estiver usando o arquivo de execução fornecido por padrão, aplica apenas o patch sem iniciar o servidor.

#### `Plazma.aggressiveOptimize`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`
- **Conflito**: `Plazma.disableConfigOptimization`

Fortalece ainda mais a otimização inicial.

Ativar isso fará com que o servidor fique mais rápido e seguro, mas pode ter um grande impacto no gameplay.

#### `Plazma.disableConfigOptimization`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`
- **Conflito**: `Plazma.aggressiveOptimize`

Não otimiza a configuração inicial.

Isso faz uso da configuração padrão do Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`

Desativa a marca Plazma e utiliza o ícone de servidor padrão do Vanilla.

#### `Plazma.useVanillaConfiguration`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`
- **Conflito**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Isso pode ter um grande impacto na segurança e desempenho do servidor.

Quaisquer problemas decorrentes do uso deste atributo são de responsabilidade do administrador do servidor.
{% endhint %}

Fornece a configuração inicial com os valores padrão fornecidos pela Mojang.

Isso desativa todas as correções de vulnerabilidades aplicadas pelo Paper.

As correções de vulnerabilidades podem ser reativadas na configuração do Paper ou da Plazma.

#### `Plazma.vanillaize`

- **Tipo**: `Boolean`
- **Padrão**: `true`
- **Conflito**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Configura a otimização inicial para se aproximar do Vanilla.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Propriedade descontinuada <a href="#id-1.3" id="id-1.3"></a>

As seguintes propriedades do sistema são descontinuadas.

#### `timings.bypassMax`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`
- **Descontinuado**: Desde a remoção do Timings do Plazma

Determina se pode exceder o valor máximo que pode ser enviado para a API de Timings de Aikar.

Mesmo que isso seja feito, se não for tratado pela API, um limite de taxa será aplicado.

***

## Argumento de início <a href="#id-2" id="id-2"></a>

O argumento de início é inserido após `-jar *.jar` para inicializar o Plazma e é processado em conjunto.

### Como usar <a href="#id-2.1" id="id-2.1"></a>

As propriedades do sistema são inseridas como argumentos de comando após `-jar *.jar`.

Por exemplo, se você quiser aplicar o argumento de início `nogui`,\
insira da seguinte forma para que o Plazma processe o argumento `nogui` durante a inicialização.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argumento de início completo <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Valor padrão**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Valor padrão**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Valor padrão**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Inicia o servidor no mundo de demonstração.

#### `eraseCache`

Remove os arquivos de cache restantes após a atualização do mundo.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Exibe todos os argumentos de início do Plazma e suas descrições.

#### `initSettings`

Cria apenas os arquivos de configuração e encerra o servidor.

#### `jfrProfile`

Ativa o perfil JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Valor padrão**: `(propriedades do servidor)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Desativa o painel de interface gráfica.

#### `nojline`

Desativa o JLine e usa o console padrão.

#### `online-mode`

- **Alias**: `o`
- **Valor padrão**: `(propriedades do servidor)`

Escolhe se deve validar os jogadores no servidor de autenticação da Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Valor padrão**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Configura a localização do arquivo de configuração descontinuado do PaperSpigot.

Usado para migrar a configuração existente para um novo arquivo de configuração e não será mais usado posteriormente.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Valor padrão**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Valor padrão**: `plugins`

Configura a localização da pasta de plugins.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Valor padrão**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Valor padrão**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Inicia o servidor em um estado completamente padrão.

#### `server-ip`

- **Alias**: `h`, `host`
- **Valor padrão**: `(propriedades do servidor)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Valor padrão**: `(propriedades do servidor)`

Configura a porta do servidor.

#### `server-name`

- **Valor padrão**: `Um Servidor Plazma`

Configura o nome do servidor.

#### `spigot-settings`

- **Alias**: `S`
- **Valor padrão**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Exibe a versão do Plazma.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Valor padrão**: `(pasta do servidor)`

Configura a localização onde os arquivos do mundo são salvos.

#### `world-name`

- **Alias**: `w`, `world`
- **Valor padrão**: `(propriedades do servidor)`

Configura o nome do arquivo do mundo.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: A posição de processamento dos argumentos muda dependendo da posição em que são anexados.

[^3]: Por exemplo, ao tentar definir `Plazma.iKnowWhatIAmDoing` como `true` (ativado), você pode usar apenas `-DPlazma.iKnowWhatIAmDoing` em vez de `-DPlazma.iKnowWhatIAmDoing=true` e ainda funcionará da mesma forma.

[^4]: Por exemplo, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detector de eventos.

[^6]: Detector de eventos.

[^7]: Cliente.

[^8]: Um sinal que indica que está conectado corretamente ao servidor, como batimentos cardíacos.

[^9]: Com a função de expulsão AFK do Purpur, é possível expulsar jogadores ausentes.

[^10]: Sistema de escrita de chunk síncrono, Sync Chunk Write System.

[^11]: \`ATENÇÃO!" Plazma pode causar problemas inesperados, portanto, certifique-se de testá-lo completamente antes de usá-lo em um servidor público.

[^12]: No jogo, a `otimização de mundo` também funciona com o mesmo princípio.

[^13]: Administradores de `nível 2` ou superior são excluídos.

[^14]: Protocolo de Internet, IP.
