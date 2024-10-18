---
description: Descubra sobre as permissões do Plazma.
---

# 🛡️ Permissões

Permissões são ferramentas simples de segurança que definem o alcance no qual os jogadores podem interagir no servidor.

Para utilizar e modificar permissões adequadamente, você deve usar plugins como [LuckPerms](https://luckperms.net).

***

## Entendendo o sistema de permissões básicas <a href="#id-1" id="id-1"></a>

No Minecraft, grupos de permissões de gerenciamento básicos são fornecidos.

Você pode definir permissões para **Operadores** e blocos de comando, e pode modificá-las em [Configurações do servidor](configurations/property.md).

0. **Jogador**\
   Grupo de permissões geralmente atribuído a todos os jogadores.
1. **Moderador**\
   Pode ignorar proteções de spawn.
2. **Administrador de Mundo**\
   Pode usar todos os comandos e blocos de comando relacionados à gestão do mundo.\
   Grupo de permissões aplicado por padrão a data packs e blocos de comando.
3. **Administrador**\
   Pode usar todos os comandos relacionados à gestão de jogadores.
4. **Superadministrador**\
   Pode usar todos os comandos, incluindo os de gestão do servidor.\
   Grupo de permissões aplicado por padrão ao console e operadores.

***

## Definindo permissões <a href="#id-2" id="id-2"></a>

***

## Permissões gerais <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Chave com Namespace)`

- **Padrão**: `None`

Permite que os jogadores montem em entidades ao se agachar e interagir com elas.

Ao montar em uma entidade, você pode controlar seu movimento com as teclas de movimento e pular ou voar com a tecla de salto.

A `(Chave com Namespace)` é o [ID com Namespace](#user-content-fn-2)[^2] da entidade.

{% dica estilo="info" %}

**Funciona apenas se `(Entidade) > montável` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Chave com Namespace)`

- **Padrão**: `None`

Permite que os jogadores usem habilidades especiais das entidades enquanto as montam.

Nem todas as entidades possuem habilidades especiais disponíveis. Consulte a lista completa de habilidades especiais disponíveis abaixo.

{% dica estilo="info" %}

Tem ideias para habilidades especiais?

Compartilhe suas ideias no [Plazma Discord](https://plazmamc.org/discord) ou no [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Ver habilidades especiais disponíveis atualmente</summary>

- **`crepper`**\
  Explode ao pressionar a tecla de salto.\
  Se o jogador possuir a permissão `allow.powered.creeper`, pode segurar a tecla de salto para carregar a explosão.
- **`dolphin`**\
  Carrega ao pressionar a tecla de salto.
- **`phantom`**\
  Dispara chamas ao pressionar a tecla de salto.
- **`wither`**\
  Dispara cabeças de Wither ao interagir.

</details>

{% dica estilo="info" %}

**Funciona apenas se `(Entidade) > montável` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `bukkit.command.compass`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/credits (Jogador)`](commands.md#credits).

Adicionando `.other` após o nome da permissão permite que outros jogadores a usem.

#### `bukkit.command.demo`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/demo (Jogador)`](commands.md#demo).

Adicionando `.other` após o nome da permissão permite que outros jogadores a usem.

#### `bukkit.command.ping`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/ping (Jogador)`](commands.md#ping).

Adicionando `.other` após o nome da permissão permite que outros jogadores a usem.

#### `bukkit.command.ram`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/rambar (Jogador)`](commands.md#rambar).

Adicionando `.other` após o nome da permissão permite que outros jogadores a usem.

#### `bukkit.command.restart`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/tpsbar (Jogador)`](commands.md#tpsbar).

Adicionando `.other` após o nome da permissão permite que outros jogadores a usem.

#### `bukkit.command.timings`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Este comando foi descontinuado.**

Para comandos similares, consulte o [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(Modo de Jogo)`

- **Padrão**: `Administrador de Mundo`

Permite o uso do comando [`/gamemode (Modo de Jogo) (Jogador)`](commands.md#gamemode).

Adicionando `.other` após o nome da permissão permite que outros jogadores a usem.

#### `paper.antixray.bypass`

- **Padrão**: `None`

Quando o bloqueio X-Ray está ativado,
os jogadores com permissão não terão seus blocos X-Ray ofuscados.

Isso melhora o desempenho de ambos os lados.

> Para saber mais sobre as configurações X-Ray, consulte a página abaixo.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Padrão**: `None`

{% hint style="warning" %}

Esta permissão será renomeada para `plazma.bypass.watchdog` na versão 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **Padrão**: `None`

Permite o uso de códigos de [cor](https://minecraft.wiki/w/Formatting_codes#Color_codes) em bigornas.

{% dica estilo="info" %}

**Funciona apenas se `anvil > allow-colors` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **Padrão**: `None`

Permite o uso de códigos de [estilo](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) em bigornas.

{% dica estilo="info" %}

**Funciona apenas se `anvil > allow-colors` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Padrão**: `None`

Permite o uso de [tags MiniMessage](https://docs.advntr.dev/minimessage/format.html) em bigornas.

{% dica estilo="info" %}

**Funciona apenas se `anvil > allow-minimessages` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Padrão**: `None`

Permite desativar o `itálico` nos textos das bigornas usando o código de estilo `&r`.

{% dica estilo="info" %}

**Funciona apenas se `anvil > allow-colors` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **Padrão**: `None`

Aplica códigos de [cor](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) quando um jogador assina um livro.

#### `purpur.bypassIdleKick`

- **Padrão**: `None`

Exclui jogadores do kick por inatividade.

#### `purpur.debug.f3n`

- **Padrão**: `Administrador de Mundo`

Permite que os jogadores alternem o modo de jogo pressionando `F3 + N`.

Isso só funciona se o jogador tiver permissão para esse modo de jogo.

#### `purpur.drop.spawners`

- **Padrão**: `None`

Quando minerar um bloco de spawner com o item configurado, ele será derrubado.

{% dica estilo="info" %}

**Funciona apenas se `gameplay-mechanics > silk-touch` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NúmeroTexto)`

- **Padrão**: `None`

Altera o tamanho do baú de ender.

Você pode usar `one`, `two`, `three`, `four`, `five`, `six` como valores para `(NúmeroTexto)`.

{% dica estilo="info" %}

**Funciona apenas se `ender_chest > six-rows` e `ender_chest > use-permissions-for-rows` estiverem ativados nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **Padrão**: `None`

Permite que o totem da indomabilidade funcione mesmo se estiver no inventário.

{% dica estilo="info" %}

**Funciona apenas se `totem-of-undying-works-in-inventory` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **Padrão**: `None`

Permite que o jogador ignore o limite de número de jogadores conectados.

#### `purpur.mending_shift_click`

- **Padrão**: `None`

Permite que o jogador repare o item que está segurando ao `agachar e interagir`.

{% dica estilo="info" %}

**Para que funcione, ative `[Purpur Configurações do Mundo](configurations/purpur/world.md) shift-right-click-repairs-mending-points`.**

{% endhint %}

#### `purpur.place.spawners`

- **Padrão**: `None`

Permite que o jogador instale spawners.

{% dica estilo="info" %}

**Funciona apenas se `gameplay-mechanics > silk-touch` estiver ativado nas [Configurações do mundo Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **Padrão**: `None`

Permite que o jogador seja teleportado instantaneamente ao usar o portal do Nether.

#### `purpur.sign.color`

- **Padrão**: `None`

Permite o uso de [códigos de cores](https://minecraft.wiki/w/Formatting_codes#Color_codes) em placas.

{% dica estilo="info" %}

**Para que funcione, ative `sign > allow-colors` nas **[configurações do mundo Purpur](configurations/purpur/world.md)**.**

{% endhint %}

#### `purpur.sign.magic`

- **Padrão**: `None`

Permite o uso do código de encriptação de analfabetismo `(&o)` nas placas.

{% dica estilo="info" %}

**Para que funcione, ative `sign > allow-colors` nas **[configurações do mundo Purpur](configurations/purpur/world.md)**.**

{% endhint %}

#### `purpur.sign.style`

- **Padrão**: `None`

Permite o uso de [código de formatação `(&o excluso)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) nas placas.

{% dica estilo="info" %}

**Para que funcione, ative `sign > allow-colors` nas **[configurações do mundo Purpur](configurations/purpur/world.md)**.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Padrão**: `None`

Permite que os jogadores evitem a explosão do TNT interagindo com ele usando tesouras.

{% dica estilo="info" %}

**Em [Configurações do Mundo Purpur](configurations/purpur/world.md), `defuse-tnt-change` deve ser igual ou superior a `0.0` para funcionar.**

{% endhint %}

### Permissões previstas

#### `plazma.bypass.ncr-require`

- **Padrão**: `None`

Permite que os jogadores entrem mesmo sem ter o mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) instalado.

{% dica estilo="info" %}

**Em [Configurações do Mundo Plazma](configurations/plazma/world.md), ative `no-chat-reports > require-install` para que funcione.**

{% endhint %}

***

[^1]: Operador.

[^2]: Exemplo: `ender_dragon`
