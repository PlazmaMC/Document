---
description: Saiba mais sobre as permissões do Plazma.
---

# 🛡️ Permissões

Permissão é uma ferramenta de segurança simples que define o escopo no qual os jogadores no servidor podem interagir entre si.

Para usar e editar permissões corretamente, você deve usar plugins como [LuckPerms](https://luckperms.net).

***

## Entendendo o sistema de permissões básicas <a href="#id-1" id="id-1"></a>

No Minecraft, existem grupos de permissões de gerenciamento básicos fornecidos.

Você pode definir permissões para operadores e blocos de comando, e podem ser modificadas em [configurações do servidor](configurations/property.md).

0. **Jogador**\
   É o grupo de permissões concedido a todos os jogadores em geral.
1. **Moderador**\
   Pode ignorar a proteção de spawn.
2. **Administrador de Mundo**\
   Pode usar todos os comandos e blocos de comando relacionados à gestão do mundo. É o grupo de permissões padrão para datapacks e blocos de comando.
3. **Administrador**\
   Pode usar todos os comandos relacionados à gestão de jogadores.
4. **Super Administrador**\
   Pode usar todos os comandos, incluindo os de gestão do servidor. É o grupo de permissões padrão para o console e operadores.

***

## Configurando Permissões <a href="#id-2" id="id-2"></a>

***

## Permissões Totais <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Chave de Namespace)`

- **Padrão**: `Nenhum`

Permite que os jogadores montem em entidades ao se agacharem e interagirem com elas.

Ao montar em uma entidade, os jogadores podem controlar o movimento da entidade com as teclas de movimento e pular ou voar com a tecla de pulo.

A `(Chave de Namespace)` é o [ID de Namespace](#user-content-fn-2) da entidade.

{% hint style="info" %}

**Somente funciona se `(Entidade) > montável` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Chave de Namespace)`

- **Padrão**: `Nenhum`

Permite que os jogadores usem habilidades especiais das entidades enquanto montadas nelas.

Nem todas as entidades possuem habilidades especiais disponíveis. Consulte abaixo para ver todas as habilidades especiais disponíveis.

{% hint style="info" %}

Tem uma ideia para uma habilidade especial?

Compartilhe suas ideias no [Plazma Discord](https://plazmamc.org/discord) ou [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Ver Habilidades Especiais Disponíveis Atualmente</summary>

- **`creeper`**\
  Explode ao pressionar a tecla de pulo. Se o jogador tiver a permissão `allow.powered.creeper`, pode segurar a tecla de pulo para carregar a explosão.
- **`dolphin`**\
  Avança ao pressionar a tecla de pulo.
- **`phantom`**\
  Dispara chamas ao pressionar a tecla de pulo.
- **`wither`**\
  Dispara cabeças de Wither ao interagir.

</details>

{% hint style="info" %}

**Somente funciona se `(Entidade) > montável` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/credits (Jogador)`](commands.md#credits).

Adiciona a extensão `.other` ao nome da permissão para permitir que outros jogadores a usem.

#### `bukkit.command.demo`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/demo (Jogador)`](commands.md#demo).

Adiciona a extensão `.other` ao nome da permissão para permitir que outros jogadores a usem.

#### `bukkit.command.ping`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/ping (Jogador)`](commands.md#ping).

Adiciona a extensão `.other` ao nome da permissão para permitir que outros jogadores a usem.

#### `bukkit.command.ram`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/rambar (Jogador)`](commands.md#rambar).

Adiciona a extensão `.other` ao nome da permissão para permitir que outros jogadores a usem.

#### `bukkit.command.restart`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/tpsbar (Jogador)`](commands.md#tpsbar).

Adiciona a extensão `.other` ao nome da permissão para permitir que outros jogadores a usem.

#### `bukkit.command.timings`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Este comando foi descontinuado.**

Para funcionalidades similares, consulte [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(Modo de Jogo)`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/gamemode (Modo de Jogo) (Jogador)`](commands.md#gamemode).

Adiciona a extensão `.other` ao nome da permissão para permitir que outros jogadores a usem.

#### `paper.antixray.bypass`

- **Padrão**: `Nenhum`

Quando a [Prevenção de X-Ray](../expert/xray.md) está ativada,
os jogadores com essa permissão não terão os blocos protegidos pelo embaralhamento de blocos X-Ray.

Isso melhora o desempenho para ambos os lados.

> Para saber mais sobre as configurações de X-Ray, consulte a página abaixo.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Padrão**: `Nenhum`

{% hint style="warning" %}

Essa permissão será alterada para `plazma.bypass.watchdog` na versão 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Padrão**: `Nenhum`

Permite o uso de [códigos de cores](https://minecraft.wiki/w/Formatting_codes#Color_codes) em bigornas.

{% hint style="info" %}

**Funciona apenas se `(Bigorna) > permitir-cores` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Padrão**: `Nenhum`

Permite o uso de [códigos de estilo](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) em bigornas.

{% hint style="info" %}

**Funciona apenas se `(Bigorna) > permitir-cores` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Padrão**: `Nenhum`

Permite o uso de [tags MiniMessage](https://docs.advntr.dev/minimessage/format.html) em bigornas.

{% hint style="info" %}

**Funciona apenas se `(Bigorna) > permitir-minimessages` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Padrão**: `Nenhum`

Permite desativar a `inclinacão do texto` com o código de estilo `&r` em bigornas.

{% hint style="info" %}

**Funciona apenas se `(Bigorna) > permitir-cores` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Padrão**: `Nenhum`

Aplica [códigos de estilo](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) quando um jogador assina um livro.

#### `purpur.bypassIdleKick`

- **Padrão**: `Nenhum`

Exclui jogadores da lista de expulsão por inatividade.

#### `purpur.debug.f3n`

- **Padrão**: `Administrador de Mundo`

Permite que os jogadores alterem o modo de jogo pressionando `F3 + N`.

Isso só funciona se o jogador tiver permissão para esse modo de jogo.

#### `purpur.drop.spawners`

- **Padrão**: `Nenhum`

Ao minerar um bloco de spawner com o item configurado, o bloco de spawner será derrubado.

{% hint style="info" %}

**Funciona apenas se `(mecânicas de jogabilidade) > toque-seda` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NúmeroString)`

- **Padrão**: `Nenhum`

Altera o tamanho do baú de ender.

Você pode inserir `one`, `two`, `three`, `four`, `five`, `six` em `(NúmeroString)`.

{% hint style="info" %}

**Funciona apenas se `ender_chest > six-rows` e `ender_chest > use-permissions-for-rows` estiverem ativados na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Padrão**: `Nenhum`

Permite que o totem da imortalidade funcione mesmo quando está no inventário.

{% hint style="info" %}

**Funciona apenas se `totem-of-undying-works-in-inventory` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Padrão**: `Nenhum`

Permite que o jogador ignore o limite de jogadores conectados.

#### `purpur.mending_shift_click`

- **Padrão**: `Nenhum`

Permite que o jogador repare o item que está segurando ao `agachar e interagir`.

{% hint style="info" %}

\*\*Para que funcione, ative `shift-right-click-repairs-mending-points` nas \*\*[configurações do mundo Purpur](configurations/purpur/world.md).

{% endhint %}

#### `purpur.place.spawners`

- **Padrão**: `Nenhum`

Permite que o jogador instale spawners.

{% hint style="info" %}

**Funciona apenas se `(mecânicas de jogabilidade) > toque-seda` estiver ativado na [configuração do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Padrão**: `Nenhum`

Permite que o jogador seja teleportado imediatamente ao usar o portal do Nether.

#### `purpur.sign.color`

- **Padrão**: `Nenhum`

Permite o uso de [códigos de cores](https://minecraft.wiki/w/Formatting_codes#Color_codes) em placas.

{% hint style="info" %}

**Para que funcione, ative `sign > allow-colors` nas [configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.magic`

- **Padrão**: `Nenhum`

Permite o uso do código de obfuscação `(&o)` em placas.

{% hint style="info" %}

**Para que funcione, ative `sign > allow-colors` nas [configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.style`

- **Padrão**: `Nenhum`

Permite o uso de [códigos de formatação `(&o excluso)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) em placas.

{% hint style="info" %}

**Para que funcione, ative `sign > allow-colors` nas [configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.tnt.defuse`

- **Padrão**: `Nenhum`

Permite que os jogadores evitem a explosão do TNT interagindo com ele usando uma tesoura.

{% hint style="info" %}

**Em [Configurações do Mundo Purpur](configurations/purpur/world.md), `defuse-tnt-change` deve ser igual ou superior a `0.0` para funcionar.**

{% endhint %}

### Permissões previstas

#### `plazma.bypass.ncr-require`

- **Padrão**: `Nenhum`

Permite que os jogadores entrem mesmo sem ter o mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) instalado.

{% hint style="info" %}

**Em [Configurações do Mundo Plazma](configurations/plazma/world.md), é necessário ativar `no-chat-reports > require-install` para funcionar.**

{% endhint %}

***

[^1]: Operador.

[^2]: Exemplo: `ender_dragon`
