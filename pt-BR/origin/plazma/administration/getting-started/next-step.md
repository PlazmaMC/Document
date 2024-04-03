---
description: Descubra como personalizar o servidor.
---

# 📶 Fase de desenvolvimento

A razão pela qual se utiliza uma plataforma de servidor modificada como Plazma, em vez da plataforma oficial fornecida pela Mojang Studios, é a capacidade de **personalização** poderosa.

Aqui estão várias maneiras de personalizar e usar o Plazma.

## Modificação de Configuração <a href="#id-1" id="id-1"></a>

A maneira mais básica de personalizar o Plazma é modificando a configuração.

O Plazma oferece configurações poderosas, desde os mecanismos do jogo até as propriedades dos mobs.

Consulte a página abaixo para obter informações sobre a configuração do Plazma.

{% content-ref url="../reference/configurations/" %}
[configurações](../reference/configurations/)
{% endcontent-ref %}

***

## Uso de Plugins <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma suporta todos os plugins baseados em Paper normalmente.**

Para plugins do Spigot, devido às mudanças de mapeamento a partir do Paper 1.20.5, alguns podem não funcionar, mas a maioria dos plugins baseados em Paper, Pufferfish e Purpur funcionam normalmente no Plazma. Se não funcionarem corretamente, é um erro do Plazma, portanto, [reporte imediatamente.](../diagnosis/plugins.md)

{% endhint %}

Esta é a principal razão para usar o Plazma e a forma mais poderosa de personalizá-lo.
O ecossistema de plugins poderoso do Plazma permite personalizar o servidor facilmente.

Existem várias maneiras de encontrar e baixar plugins. Alguns plugins são enviados para serviços de repositórios públicos, enquanto outros são enviados para o GitHub ou sites próprios.

{% hint style="caution" %}

**Os plugins podem ter acesso direto ao sistema!**

Sempre verifique se os plugins são seguros antes de aplicá-los, usando serviços como o VirusTotal, ou baixe os plugins de serviços confiáveis.

{% endhint %}

Existem vários serviços para baixar plugins. Dentre eles, serviços como [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) revisam os plugins antes de serem disponibilizados, garantindo a segurança.

### Aplicando Plugins <a href="#id-2.1" id="id-2.1"></a>

Após baixar os plugins, é hora de aplicá-los.

1. Os plugins são arquivos `.jar` ou `Java Executable File`. Alguns podem estar compactados, nesse caso, descompacte e use o arquivo com `bukkit`, `spigot` ou `paper` no nome, ou se houver um arquivo com `fat`, use este.
2. Coloque o arquivo baixado na pasta 'plugins' do servidor e reinicie o servidor.
3. Ao iniciar o Plazma, novas informações serão exibidas no console.
   Isso indica que o Plazma carregou os plugins corretamente.
4. Mesmo que o Plazma tenha carregado os plugins corretamente, pode haver problemas ao iniciá-los.
   Use o comando `/plugins` para ver os plugins carregados no servidor.
   Se o nome do plugin não estiver em <mark style="background-color:red;">vermelho</mark>, mas sim em <mark style="background-color:green;">verde</mark>, significa que o plugin foi carregado corretamente.

Se o plugin não foi carregado corretamente, você pode encontrar soluções na página abaixo.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Uso de Datapacks <a href="#id-3" id="id-3"></a>

Datapacks são uma forma de personalização fornecida pelo Minecraft, semelhante a pacotes de recursos.

Com datapacks, é possível adicionar novas entidades e desafios ao jogo, modificando partes internas do jogo.

{% hint style="caution" %}

**Datapacks podem danificar o mundo!**

Datapacks defeituosos podem danificar o mundo de forma irreversível.

Portanto, é recomendável fazer backup do mundo antes de aplicar datapacks.

{% endhint %}

Datapacks podem ser baixados de diversos serviços, como [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs).

Após baixar o datapack, coloque-o na pasta 'datapacks' do mundo do servidor para aplicá-lo.
Se a pasta não existir, crie-a antes de adicionar o datapack.

{% hint style="warning" %}

**Em alguns casos, a aplicação inicial de parte dos pacotes de dados[^2] pode não ser aplicada corretamente na primeira vez.**

Para esses casos, é recomendável reiniciar o servidor **2 vezes**.

{% endhint %}

Datapacks podem ser facilmente corrompidos a cada atualização do Minecraft.

Principalmente se um datapack estiver completamente corrompido, pode causar falhas no servidor. Portanto, é importante testar bem antes de atualizar o servidor.

{% hint style="info" %}

**Após o comando de inicialização do servidor, digite `safeMode` para desativar todos os datapacks antes de iniciar o servidor.**

Para mais informações, consulte `Referência > Argumentos e Propriedades`.(../reference/arguments.md#safeMode)

{% endhint %}

Você pode verificar os datapacks aplicados com o comando `/datapack list`.

***

## Otimização <a href="#id-4" id="id-4"></a>

Plazma possui muitos patches de otimização aplicados. Além disso, quando o Plazma é iniciado pela primeira vez, ele otimiza automaticamente a configuração, portanto, se você seguir o guia [Getting Started](./README.md), não será necessário realizar trabalhos adicionais de otimização.

No entanto, se muitos jogadores se conectarem ou se o mundo for extenso, você pode realizar trabalhos adicionais de otimização seguindo o guia abaixo.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxies conectam servidores e permitem que os jogadores se movam entre servidores ou se comuniquem com outros servidores sem trabalho adicional.

Consulte a página abaixo para informações sobre configurações de proxy seguras e corretas.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Segurança <a href="#id-5" id="id-5"></a>

Com o desenvolvimento de mods, é fácil encontrar [motores de ataque de vulnerabilidades](#user-content-fn-3)[^3] online.

Embora a maioria das vulnerabilidades executáveis em jogos normais sejam [bloqueadas por padrão](#user-content-fn-4)[^4], atacar vulnerabilidades através de carregadores de terceiros não é bloqueado.

Portanto, se o servidor estiver público, é recomendável instalar plugins anti-cheat e configurar proxies, reinicializações automáticas, backups, etc., para impedir o uso de vulnerabilidades e garantir uma rápida recuperação em caso de falha do servidor.

### Configuração de permissões <a href="#id-5.1" id="id-5.1"></a>

Alguns comandos de administrador de plugins podem ter vulnerabilidades se as permissões não forem configuradas corretamente.

É recomendável limitar as permissões de usuários com plugins de gerenciamento de permissões como [LuckPerms](https://luckperms.net/).

### Bloqueio de X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray é uma das vulnerabilidades facilmente exploráveis mesmo em clientes de otimização básica.

Plazma oferece uma configuração para bloquear X-Ray por padrão.

Consulte a página abaixo para obter informações e instruções sobre como bloquear X-Ray.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Lista branca <a href="#id-5.3" id="id-5.3"></a>

Se deseja permitir apenas alguns usuários a acessarem o servidor, é recomendável usar [Ngrok](./README.md#id-6.2) para usar um endereço de servidor ofuscado[^5] ou configurar uma lista branca para impedir que outros jogadores acessem o servidor.

Na console do servidor, você pode permitir a entrada de jogadores com `/whitelist add <player>` ou proibir a entrada com `/whitelist remove <player>`.

Para ver os jogadores com permissão de entrada, use `/whitelist query`.

***

[^1]: Ou através de addons do Minecraft: Bedrock Edition.

[^2]: Adição de novas entidades, etc.

[^3]: Comumente conhecidos como "hacks".

[^4]: Se a configuração não estiver otimizada, se o Plazma estiver desatualizado ou se houver novas vulnerabilidades descobertas, elas podem não estar bloqueadas.

[^5]: Os jogadores acessam o servidor através do servidor proxy Ngrok e o endereço do Ngrok gerado a cada reinicialização é diferente.
