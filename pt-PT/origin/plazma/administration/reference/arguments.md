---
description: Descubra sobre os argumentos de inicialização e as propriedades do sistema.
---

# 🎛️ Argumentos e Propriedades

Os argumentos de inicialização e as propriedades do sistema são valores adicionados aos comandos [usados ​​na execução do Plazma](#user-content-fn-1)[^1], que permitem alterar valores que não podem ser alterados após a execução do Plazma.

Dependendo da [posição em que são adicionados ao comando](#user-content-fn-2)[^2], eles são divididos em **Argumentos de Inicialização** e **Propriedades do Sistema**.

***

## Propriedades do Sistema <a href="#id-1" id="id-1"></a>

As propriedades do sistema são valores inseridos antes de `-jar`, processados pelo JVM antes da inicialização do Plazma.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### Modo de Uso <a href="#id-1.1" id="id-1.1"></a>

As propriedades do sistema são inseridas como argumentos de comando Java entre `java` e `-jar`.

Por exemplo, se você deseja aplicar a propriedade do sistema `Plazma.dummyProperty`, ao inserir da seguinte forma, o valor `37` será inserido na próxima propriedade para inicializar o Plazma.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indica que o argumento não está embutido no JVM, mas é um argumento exclusivo adicionado ao Plazma,

Se nenhum valor for inserido na propriedade, o valor será fixado como [`true`.](#user-content-fn-3)[^3]

{% dica estilo="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

{% endhint %}

### Todas as Propriedades do Sistema <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Atualiza o formato de placas desativadas.

#### `debug.entities`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ativa logs de depuração relacionados às informações de entidades.

#### `debug.rewriteForIDE`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa a revisão NMS para permitir que as informações de depuração sejam carregadas corretamente no IDE e remapeia automaticamente as informações de versão interna.

#### `disable.watchdog`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa o sistema de alerta de Watchdog do Spigot.

#### `letMeReload`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa a mensagem de confirmação do comando `/reload`.

{% hint style="danger" %}

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Se você é um desenvolvedor de plugins e precisa atualizar um plugin, use o hotswap em vez do `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa plugins que usam o sistema de entrada/saída padrão.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Avisa quando um formato descontinuado é detectado em componentes de chat.

#### `Paper.bypassHostCheck`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa a verificação de padrão do servidor quando um jogador se conecta.

#### `Paper.debugDynamicMissingKeys`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ativa logs de depuração para chaves ausentes em objetos NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ativa logs de depuração para blocos de cabeça com perfis inválidos.

Isso registra todos os blocos de cabeça inválidos no mundo, juntamente com suas localizações.

#### `Paper.disableChannelLimit`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa o limite de 128 canais de plugin por jogador.

#### `Paper.disableClassPrioritization`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa o sistema de priorização de classes de plugins.

Útil em casos de problemas com sombreamento de plugins.

#### `Paper.disableFlushConsolidate`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa a consolidação de descarga do Netty.

#### `Paper.excessiveTELimit`

- **Tipo**: `Integer`
- **Valor Padrão**: `750`

Divide em múltiplos pacotes para transmissão se houver mais entidades do que o valor definido.

#### `Paper.filterThreshold`

- **Tipo**: `Integer`
- **Valor Padrão**: `8192`

Define o tamanho máximo de pacotes que o servidor pode receber de uma só vez.

#### `Paper.ignoreJavaVersion`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Desativa a verificação da versão do Java.

{% hint style="danger" %}

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Isso pode resultar em danos permanentes nos arquivos do mundo e causar falhas em todo o mecanismo do jogo.

Qualquer problema causado pelo uso disso é de responsabilidade do usuário e o Plamza não oferece suporte para isso.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tipo**: `Integer`
- **Valor Padrão**: `64`

Define o limite de caracteres no nome do canal do plugin.

#### `Paper.maxSignLength`

- **Tipo**: `Integer`
- **Valor Padrão**: `80`

Define o comprimento máximo de caracteres em uma linha de placa.

#### `Paper.minPrecachedDatafixVersion`

- **Tipo**: `Integer`
- **Valor Padrão**: `(versão do mundo) + 1`

Define a versão das informações de atualização do mundo a serem inicializadas primeiro.

Útil ao atualizar um grande número de chunks, mas raramente usado em outras situações.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Verdadeiro`

Ativa o processamento de comentários em arquivos YAML.

#### `Paper.playerConnection.keepAlive`

- **Tipo**: `Integer`
- **Valor Padrão**: `30`

Expulsa o jogador se não receber dados por um determinado período de tempo (em segundos).

Normalmente, o jogo[^7] envia continuamente um [sinal de pulsação](#user-content-fn-8)[^8] para o servidor, evitando a expulsão, mas se o jogo não responder, o servidor considera que houve uma falha e expulsa o jogador.

#### `Paper.skipServerPropertiesComments`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ignora os comentários das propriedades do servidor.

#### `Paper.debug-sync-loads`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ativa logs de depuração para a criação síncrona de chunks.

#### `Paper.enable-sync-chunk-writes`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ativa o sistema de escrita de chunks síncrono padrão do Minecraft.

Isso salva cada chunk em ordem, causando uma grande degradação de desempenho.

#### `Paper.explicit-flush`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ativa o Flush Explícito do canal de rede.

#### `Paper.strict-thread-checks`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Registra sempre erros que não ocorreram no thread principal.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Exibe um aviso se uma tarefa agendada tiver um atraso excessivo.

#### `Paperclip.patchOnly`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Falso`

Ao usar o arquivo de execução padrão, aplica apenas o patch sem iniciar o servidor.

#### `Plazma.aggressiveOptimize`

- **Tipo**: `Boolean`
- **Valor Padrão**: `falso`

{% hint style="warning" %}

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Aplica otimizações de configuração mais rigorosas no início.

Ao ativar, o servidor ficará mais rápido e seguro, mas pode bloquear algumas mecânicas ou ter um grande impacto no jogo.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valor Padrão**: `falso`

Suprime o aviso[^11] exibido quando o Plazma é inicializado.

### Atributo <a href="#id-1.3" id="id-1.3"></a> obsoleto

Os atributos de sistema abaixo são obsoletos.

#### `timings.bypassMax`

- **Tipo**: `Boolean`
- **Valor Padrão**: `falso`
- **Obsoleto**: Desde a remoção do Timings do Plazma

Decide se pode exceder o máximo de valores enviados para a API de Timings de Aikar.

Se não for tratado pela API, será aplicado um limite de taxa.

***

## Argumento de início <a href="#id-2" id="id-2"></a>

O argumento de início é inserido após `-jar *.jar` para inicializar o Plazma e é processado em conjunto.

### Modo de uso <a href="#id-2.1" id="id-2.1"></a>

Os atributos de sistema são inseridos como argumentos de programa após `-jar *.jar`.

Por exemplo, se você deseja aplicar o argumento de início `nogui`,\
insira da seguinte forma para que o Plazma processe o argumento `nogui` durante a inicialização.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argumento de início completo <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Valor padrão**: `bukkit.yml`

Configura o nome e localização do [arquivo de configuração do Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Valor padrão**: `commands.yml`

Configura o nome e localização do [arquivo de configuração de comandos do Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Valor padrão**: `server.properties`

Configura o nome e localização do arquivo de [propriedades do servidor](../reference/configurations/property.md).

#### `demo`

Inicia o servidor no mundo de demonstração.

#### `eraseCache`

Remove os arquivos de cache restantes após a atualização do mundo.

#### `forceUpgrade`

Força a [atualização](#user-content-fn-12)[^12] do mundo, ignorando a versão.

#### `help`

- **Alias**: `?`

Exibe todos os argumentos de início do Plazma e suas descrições.

#### `initSettings`

Cria apenas o arquivo de configuração e encerra o servidor.

#### `jfrProfile`

Ativa o perfil JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Valor padrão**: `(propriedades do servidor)`

Configura o número máximo de [jogadores](#user-content-fn-14)[^14] permitidos.

#### `nogui`

Desativa o painel de interface gráfica.

#### `nojline`

Desativar o JLine e usar o console de baunilha.

#### `online-mode`

- **Alias**: `o`
- **Valor padrão**: `(propriedades do servidor)`

Escolha se autenticar os jogadores no servidor de autenticação da Mojang.

**Se não estiver usando Velocity ou outro proxy, você pode ser sancionado por violar o [EULA](../getting-started/README.md#id-5)**

#### `paper-settings`

- **Alias**: `paper`
- **Valor padrão**: `paper.yml`

{% hint style="warning" %}

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

{% endhint %}

Configura a localização do arquivo de configuração do PaperSpigot descontinuado.

Usado para migrar as configurações do PaperSpigot descontinuado para um novo arquivo de configuração, não é mais utilizado posteriormente.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Valor padrão**: `config`

Configura o nome e a localização da pasta onde os arquivos de configuração do Paper estão localizados.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Configura o nome e a localização da pasta onde os arquivos de configuração do Plazma estão localizados.

#### `plugins`

- **Alias**: `p`
- **Valor padrão**: `plugins`

Configura a localização da pasta de plugins.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Valor padrão**: `pufferfish.yml`

Configura o nome e a localização do arquivo de configuração do Pufferfish.

#### `purpur-settings`

- **Alias**: `purpur`
- **Valor padrão**: `purpur.yml`

Configura o nome e a localização do arquivo de configuração do Purpur.

#### `safeMode`

Inicia o servidor em um estado completamente de baunilha (modo seguro).

#### `server-ip`

- **Alias**: `h`, `host`
- **Valor padrão**: `(propriedades do servidor)`

Configura o nome do host do servidor ou o endereço IP do [Protocolo de Internet](#user-content-fn-13)[^13].

#### `server-port`

- **Alias**: `p`, `port`
- **Valor padrão**: `(propriedades do servidor)`

Configura a porta do servidor.

#### `server-name`

- **Valor padrão**: `A Plazma Server`

Configura o nome do servidor.

#### `spigot-settings`

- **Alias**: `S`
- **Valor padrão**: `spigot.yml`

Configura o nome e a localização do arquivo de configuração do Spigot.

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

[^2]: A forma como os argumentos são tratados muda dependendo da posição em que são adicionados.

[^3]: Por exemplo, se você deseja definir (ativar) `Plazma.iKnowWhatIAmDoing` como `true`, em vez de inserir `-DPlazma.iKnowWhatIAmDoing=true`, você pode simplesmente inserir `-DPlazma.iKnowWhatIAmDoing` e ele funcionará da mesma maneira.

[^4]: Por exemplo, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detector de eventos.

[^6]: Detector de eventos.

[^7]: Cliente.

[^8]: Um sinal que indica que o cliente está conectado ao servidor de forma adequada, como os batimentos cardíacos.

[^9]: Com a função de expulsão AFK do Purpur, é possível expulsar jogadores ausentes.

[^10]: Sistema de escrita de chunks síncrono, Sync Chunk Write System.

[^11]: `AVISO! Plazma pode causar problemas inesperados, portanto, certifique-se de testá-lo completamente antes de usá-lo em um servidor público.`

[^12]: `World Optimization` no jogo também funciona com o mesmo princípio.

[^13]: Protocolo de Internet, IP.

[^14]: Administradores de `nível 2` ou superior estão excluídos.
