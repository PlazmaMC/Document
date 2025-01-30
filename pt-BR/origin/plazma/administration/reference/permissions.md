---
description: Saiba mais sobre as permissões do Plazma.
---

# 🛡️ Permissões

Permissão é uma ferramenta de segurança simples que define o escopo no qual os jogadores no servidor podem interagir entre si.

Para usar e editar permissões corretamente, você deve usar plugins como [LuckPerms](https://luckperms.net).

***

## Entendendo o sistema de permissões básicas <a href="#id-1" id="id-1"></a>

No Minecraft, existem grupos de permissões de gerenciamento básicos fornecidos.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Jogador**\
   É o grupo de permissões concedido a todos os jogadores em geral.
2. **Moderador**\
   Pode ignorar a proteção de spawn.
3. **Administrador de Mundo**\
   Pode usar todos os comandos e blocos de comando relacionados à gestão do mundo. É o grupo de permissões padrão para datapacks e blocos de comando.
4. **Administrador**\
   Pode usar todos os comandos relacionados à gestão de jogadores.
5. **Super Administrador**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Chave de Namespace)`

- **Padrão**: `Nenhum`

Permite que os jogadores usem habilidades especiais das entidades enquanto montadas nelas.

Nem todas as entidades possuem habilidades especiais disponíveis. Consulte abaixo para ver todas as habilidades especiais disponíveis.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Isso melhora o desempenho para ambos os lados.

> Para saber mais sobre as configurações de X-Ray, consulte a página abaixo.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Padrão**: `Nenhum`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Padrão**: `Nenhum`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Padrão**: `Nenhum`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Padrão**: `Nenhum`

Permite o uso de [tags MiniMessage](https://docs.advntr.dev/minimessage/format.html) em bigornas.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Padrão**: `Nenhum`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Padrão**: `Nenhum`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NúmeroString)`

- **Padrão**: `Nenhum`

Altera o tamanho do baú de ender.

Você pode inserir `one`, `two`, `three`, `four`, `five`, `six` em `(NúmeroString)`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Padrão**: `Nenhum`

Permite que o totem da imortalidade funcione mesmo quando está no inventário.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Padrão**: `Nenhum`

Permite que o jogador ignore o limite de jogadores conectados.

#### `purpur.mending_shift_click`

- **Padrão**: `Nenhum`

Permite que o jogador repare o item que está segurando ao `agachar e interagir`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Padrão**: `Nenhum`

Permite que o jogador instale spawners.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Padrão**: `Nenhum`

Permite que o jogador seja teleportado imediatamente ao usar o portal do Nether.

#### `purpur.sign.color`

- **Padrão**: `Nenhum`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Padrão**: `Nenhum`

Permite o uso do código de obfuscação `(&o)` em placas.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Padrão**: `Nenhum`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Padrão**: `Nenhum`

Permite que os jogadores evitem a explosão do TNT interagindo com ele usando uma tesoura.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Permissões previstas

#### `plazma.bypass.ncr-require`

- **Padrão**: `Nenhum`

Permite que os jogadores entrem mesmo sem ter o mod [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) instalado.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operador.

[^2]: Exemplo: `ender_dragon`
