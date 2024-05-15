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

**Ao modificar as propriedades do sistema, o funcionamento do Plazma e do JVM pode ser alterado, o que pode ter um grande impacto no jogo!**

Se você não tem certeza sobre qual papel cada propriedade do sistema desempenha, **não as utilize de forma alguma!**

{% endhint %}

### Modo de Uso <a href="#id-1.1" id="id-1.1"></a>

As propriedades do sistema são inseridas como argumentos Java entre `java` e `-jar`.

Por exemplo, ao aplicar a propriedade do sistema `Plazma.dummyProperty`, ao inserir da seguinte forma, o valor `37` será inserido na próxima propriedade e o Plazma será inicializado.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indica que o argumento não é integrado ao JVM, sendo um argumento exclusivo do Plazma,

Se nenhum valor for inserido nas propriedades, o valor será fixado como [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**A plataforma do tipo Paperweight diferencia as propriedades do sistema em cada plataforma incluindo um `.` no nome da propriedade.**

Em alguns terminais como Windows Powershell, pode não ser permitido esses argumentos, portanto, é necessário adicionar `"` ao redor dos argumentos [como medida de precaução](#user-content-fn-4)[^4].

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

**O comando `/reload` é extremamente instável, portanto, quaisquer problemas que ocorram no servidor após o uso do `/reload` são de responsabilidade do próprio usuário.**

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

Desativa o limite de 128 canais de plugin aplicados por jogador.

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

- **Tipo**: `Integer`
- **Valor Padrão**: `750`

Divide em múltiplos pacotes para transmissão se a entidade exceder o valor definido.

#### `Paper.filterThreshold`

- **Tipo**: `Integer`
- **Valor Padrão**: `8192`

Define o tamanho máximo dos pacotes que o servidor pode receber de uma vez.

#### `Paper.ignoreJavaVersion`

- **Tipo**: `Boolean`
- **Valor Padrão**: `False`

Desativa a verificação da versão do Java.

{% hint style="danger" %}

**Isso pode permitir que o JVM tente acessar código inexistente!**

Pode resultar em danos permanentes nos arquivos do mundo e na quebra de todo o mecanismo do jogo.

Quaisquer problemas resultantes do uso dessa configuração são de responsabilidade do usuário, e o Plamza não oferece suporte para isso.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tipo**: `Integer`
- **Valor Padrão**: `64`

Define a restrição do nome do canal do plugin.

#### `Paper.maxSignLength`

- **Tipo**: `Integer`
- **Valor Padrão**: `80`

Define o comprimento máximo de caracteres por linha em placas.

#### `Paper.minPrecachedDatafixVersion`

- **Tipo**: `Integer`
- **Valor Padrão**: `(versão do mundo) + 1`

Define a versão das informações de atualização do mundo a ser inicializada primeiro.

Útil ao atualizar grandes quantidades de chunks, mas raramente usado em outras situações.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valor Padrão**: `True`

Ativa o processamento de comentários em arquivos YAML.

#### `Paper.playerConnection.keepAlive`

- **Tipo**: `Integer`
- **Valor Padrão**: `30`

Expulsa um jogador se não receber dados por um determinado tempo em segundos.

Normalmente, o [jogo](#user-content-fn-7)[^7] continua enviando [sinais de batimento cardíaco](#user-content-fn-8)[^8] para o servidor, portanto, não será expulso; no entanto, se o jogo não responder, será considerado em conflito e, consequentemente, não processará mais o jogador no servidor e o expulsará.

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
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`

Suprime a exibição do [aviso](#user-content-fn-11)[^11] exibido durante a inicialização do Plazma.

#### `Plazma.useVanillaFavicon`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Tipo**: `Boolean`
- **Valor Padrão**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

{% hint style="danger" %}

**해당 속성은 패치된 모든 취약점을 되돌립니다!**

이는 서버 안전 및 성능에 크게 영향을 줄 수 있습니다.

해당 속성을 사용하여 발생하는 모든 문제는 서버 관리자에게 있습니다.

{% endhint %}

초기 구성을 Mojang에서 제공하는 기본값으로 제공합니다.

이는 Paper에서 적용한 모든 취약점 패치를 비활성화 합니다.

취약점 패치는 Paper 구성 또는 Plazma 구성에서 다시 활성화 할 수 있습니다.

#### `Plazma.vanillaize`

- **Tipo**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

Configura o nome e a localização do [arquivo de configurações do Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Valor padrão**: `commands.yml`

Configura o nome e a localização do [arquivo de configurações de comandos do Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Valor padrão**: `server.properties`

Configura o nome e a localização do [arquivo de propriedades do servidor](../reference/configurations/property.md).

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

Cria apenas os arquivos de configuração e encerra o servidor.

#### `jfrProfile`

Ativa o perfil JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Valor padrão**: `(propriedades do servidor)`

Define o número máximo de [jogadores](#user-content-fn-14)[^14] permitidos.

#### `nogui`

Desativa o painel de interface gráfica.

#### `nojline`

Desativa o JLine e usa o console padrão.

#### `online-mode`

- **Alias**: `o`
- **Valor padrão**: `(propriedades do servidor)`

Escolhe se deve validar os jogadores no servidor de autenticação da Mojang.

**Caso não esteja usando Velocity ou outro proxy, pode resultar em violação do [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Valor padrão**: `paper.yml`

{% hint style="warning" %}

**Este argumento foi descontinuado após a versão 1.19.4**

{% endhint %}

Configura a localização do arquivo de configuração descontinuado do PaperSpigot.

Usado para migrar a configuração existente para um novo arquivo de configuração e não será mais usado posteriormente.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Valor padrão**: `config`

Configura o nome e a localização da pasta onde o [arquivo de configuração do Paper](../reference/configurations/paper/README.md) está localizado.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Configura o nome e a localização da pasta onde o [arquivo de configuração do Plazma](../reference/configurations/plazma/README.md) está localizado.

#### `plugins`

- **Alias**: `p`
- **Valor padrão**: `plugins`

Configura a localização da pasta de plugins.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Valor padrão**: `pufferfish.yml`

Configura o nome e a localização do [arquivo de configuração do Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Valor padrão**: `purpur.yml`

Configura o nome e a localização do [arquivo de configuração do Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Inicia o servidor em um estado completamente padrão.

#### `server-ip`

- **Alias**: `h`, `host`
- **Valor padrão**: `(propriedades do servidor)`

Configura o nome do host do servidor ou o endereço de [Protocolo de Internet](#user-content-fn-13)[^13].

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

Configura o nome e a localização do [arquivo de configurações do Spigot](../reference/configurations/spigot.md).

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

[^13]: Protocolo de Internet, IP.

[^14]: Administradores de `nível 2` ou superior são excluídos.
