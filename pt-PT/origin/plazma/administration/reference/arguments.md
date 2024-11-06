---
description: Descubra sobre os argumentos de inicialização e as propriedades do sistema.
---

# 🎛️ Argumentos e Propriedades

Os argumentos de entrada e as propriedades do sistema são valores adicionais anexados ao comando usado na execução do Plazma, que afetam globalmente o funcionamento do Plazma.

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## Propriedades do Sistema <a href="#id-1" id="id-1"></a>

As propriedades do sistema são valores inseridos antes de `-jar`, processados pelo JVM antes da inicialização do Plazma.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Modo de Uso <a href="#id-1.1" id="id-1.1"></a>

As propriedades do sistema são inseridas como argumentos de comando Java entre `java` e `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indica que o argumento não está embutido no JVM, mas é um argumento exclusivo adicionado ao Plazma,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정](#user-content-fn-3)[^3]됩니다.

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Valor Padrão**: `750`

Divide em múltiplos pacotes para transmissão se houver mais entidades do que o valor definido.

#### `Paper.filterThreshold`

- **형태**: `Integer`
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

- **형태**: `Integer`
- **Valor Padrão**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Valor Padrão**: `80`

Define o comprimento máximo de caracteres em uma linha de placa.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Valor Padrão**: `(versão do mundo) + 1`

Define a versão das informações de atualização do mundo a serem inicializadas primeiro.

Útil ao atualizar um grande número de chunks, mas raramente usado em outras situações.

#### `Paper.parseYamlCommentsByDefault`

- **Tipo**: `Boolean`
- **Valor Padrão**: `Verdadeiro`

Ativa o processamento de comentários em arquivos YAML.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Valor Padrão**: `30`

Expulsa o jogador se não receber dados por um determinado período de tempo (em segundos).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 servidor ficará mais rápido e seguro, mas pode afetar significativamente o jogo.

#### `Plazma.disableConfigOptimization`

- **Tipo**: `Boolean`
- **Valor Padrão**: `falso`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

Isso faz com que utilize a configuração padrão do Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Tipo**: `Boolean`
- **Valor Padrão**: `falso`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tipo**: `Boolean`
- **Valor Padrão**: `falso`

Desativa a marca Plazma e utiliza o ícone de servidor padrão do tipo baunilha.

#### `Plazma.useVanillaConfiguration`

- **Tipo**: `Boolean`
- **Valor Padrão**: `falso`
- **충돌**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Isso pode ter um impacto significativo na segurança e desempenho do servidor.

Quaisquer problemas decorrentes do uso deste atributo são de responsabilidade do administrador do servidor.
{% endhint %}

Fornece a configuração inicial com os valores padrão fornecidos pela Mojang.

Isso desativa todas as correções de falhas aplicadas pelo Paper.

As correções de falhas podem ser reativadas na configuração do Paper ou na configuração do Plazma.

#### `Plazma.vanillaize`

- **Tipo**: `Boolean`
- **Padrão**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Configura a inicialização para ser mais semelhante ao tipo baunilha.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

Cria apenas o arquivo de configuração e encerra o servidor.

#### `jfrProfile`

Ativa o perfil JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Valor padrão**: `(propriedades do servidor)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Desativa o painel de interface gráfica.

#### `nojline`

Desativar o JLine e usar o console de baunilha.

#### `online-mode`

- **Alias**: `o`
- **Valor padrão**: `(propriedades do servidor)`

Escolha se autenticar os jogadores no servidor de autenticação da Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

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

Inicia o servidor em um estado completamente de baunilha (modo seguro).

#### `server-ip`

- **Alias**: `h`, `host`
- **Valor padrão**: `(propriedades do servidor)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[^13]: Administradores de `nível 2` ou superior estão excluídos.

[^14]: Protocolo de Internet, IP.
