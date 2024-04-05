---
description: Descubra como personalizar o servidor.
---

# 📶 Fase de desenvolvimento

A razão pela qual se utiliza uma plataforma de servidor modificada como o Plazma em vez da plataforma oficial fornecida pela Mojang Studios é a capacidade de **personalização** intensa.

Aqui estão várias maneiras de personalizar e utilizar o Plazma.

## Modificação de configuração <a href="#id-1" id="id-1"></a>

A forma mais básica de personalizar o Plazma é modificando a configuração.

O Plazma oferece configurações poderosas, desde os mecanismos do jogo até as propriedades dos mobs.

Consulte a página abaixo para obter informações sobre as configurações do Plazma.

{% content-ref url="../reference/configurations/" %}
[configurações](../reference/configurations/)
{% endcontent-ref %}

***

## Utilização de plugins <a href="#id-2" id="id-2"></a>

{% dica style="sucesso" %}

**Plazma suporta todos os plugins baseados em Paper normalmente.**

Para plugins Spigot, devido às mudanças de mapeamento do Paper a partir da 1.20.5, alguns podem não funcionar corretamente, mas a maioria dos plugins baseados em Paper, como Paper, Pufferfish e Purpur, funcionam normalmente no Plazma e, se não funcionarem corretamente, é um erro do Plazma, então por favor [reporte imediatamente.](../diagnosis/plugins.md)

{% endhint %}

Esta é a principal razão para usar o Plazma e a maneira mais poderosa de personalizá-lo.
O ecossistema de plugins robusto do Plazma permite personalizar facilmente o servidor.

Existem várias maneiras de encontrar e baixar plugins. Alguns plugins são enviados para serviços de repositórios públicos e outros são enviados para GitHub ou sites próprios.

{% dica style="atenção" %}

**Os plugins podem acessar diretamente o sistema!**

Sempre verifique se o plugin é seguro antes de aplicá-lo usando serviços como VirusTotal, ou baixe o plugin de serviços confiáveis.

{% endhint %}

Existem vários serviços para baixar plugins. Entre eles, serviços como [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) revisam os plugins antes de serem enviados, garantindo que apenas plugins seguros sejam distribuídos.

### Aplicando plugins <a href="#id-2.1" id="id-2.1"></a>

Depois de baixar os plugins, é hora de aplicá-los.

1. Os plugins estão em arquivos `.jar` ou `Java Executable File`.\
   Alguns são compactados e, nesse caso, extraia, procure por `bukkit`, `spigot` ou `paper` no nome e, se houver um arquivo `fat`, use-o.
2. Coloque o arquivo baixado na pasta `plugins` do servidor e (re)inicie o servidor.
3. Quando o Plazma iniciar, haverá novas mensagens no console.
   Isso significa que o Plazma carregou os plugins corretamente.
4. Mesmo que o Plazma tenha carregado os plugins corretamente, eles podem não iniciar.
   Com o comando `/plugins`, você pode ver os plugins carregados no servidor.
   Se o nome do plugin não estiver em <mark style="background-color:red;">vermelho</mark>, mas sim em <mark style="background-color:green;">verde</mark>, significa que o plugin foi carregado corretamente.

Se os plugins não foram carregados corretamente, você pode encontrar soluções na página abaixo.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Usando pacotes de dados <a href="#id-3" id="id-3"></a>

Os pacotes de dados são uma forma de personalização fornecida pelo Minecraft, semelhante a [pacotes de recursos](#user-content-fn-1)[^1].

Com pacotes de dados, você pode adicionar novas entidades e desafios ao jogo, entre outras modificações internas.

{% dica style="atenção" %}

**Os pacotes de dados podem danificar o mundo!**

Alguns pacotes de dados defeituosos podem danificar o mundo de forma irreversível.

Portanto, é recomendável fazer backup do mundo antes de aplicar pacotes de dados.

{% endhint %}

Os pacotes de dados podem ser baixados de vários serviços, como [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/), entre outros.

Depois de baixar os pacotes de dados, você pode aplicá-los colocando-os na pasta `datapacks` do mundo do servidor.
Se a pasta não existir, crie-a para adicionar os pacotes de dados.

{% hint style="warning" %}

**[Alguns pacotes de dados](#user-content-fn-2)[^2] podem não ser aplicados corretamente na primeira aplicação.**

Para isso, é recomendável reiniciar o servidor **2 vezes**.

{% endhint %}

Os pacotes de dados podem ser facilmente corrompidos a cada atualização do Minecraft.

Especialmente se os pacotes de dados estiverem completamente corrompidos, é importante testar bem antes de atualizar o servidor para evitar conflitos.

{% dica estilo="info" %}

**Depois de inserir `safeMode` após o comando de inicialização do servidor, você pode desativar todos os pacotes de dados e iniciar o servidor.**

Para mais informações, consulte `Referência > Argumentos e Propriedades`.](../reference/arguments.md#safeMode)

{% endhint %}

Você pode verificar os pacotes de dados aplicados com o comando `/datapack list`.

***

## Otimização <a href="#id-4" id="id-4"></a>

Plazma tem muitos patches de otimização aplicados. Além disso, quando o Plazma é iniciado pela primeira vez, otimiza automaticamente
a configuração, então se você seguir o guia [Começando](./README.md), não há necessidade de mais trabalho de otimização.

No entanto, se muitos jogadores se conectarem ou se o mundo for extenso,
você pode realizar trabalhos adicionais de otimização seguindo o guia abaixo.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

O proxy conecta servidores e permite que os jogadores se movam entre servidores
ou se comuniquem com outros servidores sem trabalho adicional.

Para informações sobre configurações de proxy seguras e corretas, consulte a página abaixo.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Segurança <a href="#id-5" id="id-5"></a>

Com o avanço dos mods, é fácil encontrar um [motor de ataque de vulnerabilidades](#user-content-fn-3)[^3] online.

Embora a maioria das vulnerabilidades executáveis em jogos normais sejam [bloqueadas por padrão](#user-content-fn-4)[^4],
a exploração de vulnerabilidades através de carregadores de terceiros não é bloqueada.

Portanto, se o servidor estiver público, é recomendável instalar plugins anti-cheat para bloquear a exploração de vulnerabilidades,
e configurar proxies, reinicializações automáticas, backups, etc., para que o servidor possa ser rapidamente recuperado em caso de queda.

### Configuração de permissões <a href="#id-5.1" id="id-5.1"></a>

Alguns comandos de administrador de plugins podem ter vulnerabilidades se as permissões não forem configuradas corretamente.

É recomendável usar plugins de gerenciamento de permissões como
LuckPerms](https://luckperms.net/) para restringir as permissões de usuários comuns.

### Bloqueio de X-Ray <a href="#id-5.2" id="id-5.2"></a>

O X-Ray é uma das vulnerabilidades facilmente exploráveis mesmo em clientes de otimização básica.

Plazma oferece uma configuração para bloquear o uso do X-Ray por padrão.

Consulte a página abaixo para obter informações e instruções sobre o bloqueio do X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Lista branca <a href="#id-5.3" id="id-5.3"></a>

Se deseja permitir apenas alguns usuários a acessarem o servidor,
utilize [Ngrok](./README.md#id-6.2) para usar [um endereço de servidor ofuscado](#user-content-fn-5)[^5] ou
configure uma lista branca para impedir que outros jogadores acessem o servidor.

No console do servidor, use `/whitelist add <player>` para permitir a entrada de um jogador ou
`/whitelist remove <player>` para proibir a entrada de um jogador novamente.

Use `/whitelist query` para ver os jogadores permitidos a entrar.

***

[^1]: Ou no Minecraft: Bedrock Edition, os add-ons.

[^2]: Adição de novas entidades, entre outras coisas.

[^3]: Normalmente chamado de "hacks".

[^4]: Se a configuração não estiver otimizada, se o Plazma estiver desatualizado ou se novas vulnerabilidades forem descobertas, elas podem não ser bloqueadas.

[^5]: Os jogadores se conectam ao servidor através do servidor de proxy Ngrok e um novo endereço Ngrok é emitido a cada reinicialização.
