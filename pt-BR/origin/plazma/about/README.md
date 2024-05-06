---
description: Descubra mais sobre o que é o Plazma como plataforma de servidor.
---

# ❓ O que é o Plazma?

- **Plazma** é uma plataforma de servidor baseada no [Paper](https://github.com/PaperMC/Paper), que traz apenas os pontos fortes do [Andromeda](https://github.com/EarendelArchived/Andromeda) e do [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Estamos empenhados em fornecer sempre alta estabilidade, desempenho poderoso, atualizações rápidas e uma ampla gama de recursos.

## 📋 Objetivos do Plazma <a href="#id-1" id="id-1"></a>

- Estamos trabalhando para ser uma plataforma de servidor com atualizações rápidas e alta estabilidade.
- Estamos empenhados em fornecer uma ampla gama de recursos e desempenho poderoso, não menos do que uma plataforma de modos.
- Estamos trabalhando para criar uma plataforma livre que permita personalizar até mesmo os patches do Vanilla.

## ⚙️ Principais Características <a href="#id-2" id="id-2"></a>

1. **Ecossistema de plugins poderoso**\
   Com base no [Paper](https://github.com/PaperMC/Paper),
   a maioria dos [plugins mais recentes](#user-content-fn-1)[^1] disponíveis na internet funcionam corretamente.
2. **Otimização sem necessidade de configuração**\
   Todos os patches do [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) estão incluídos, e também possui otimizações internas e modos embutidos para oferecer o melhor desempenho.
3. **Personalize o jogo como quiser**\
   O [Purpur](https://github.com/PurpurMC/Purpur) incluído no Plazma permite modificar as propriedades gerais do jogo.
4. **Servidores seguros para jogar**\
   O [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) está incluído para desativar o [sistema de denúncias de chat](#user-content-fn-3)[^3] da [Mojang](#user-content-fn-2)[^2] adicionado a partir da versão 1.19,\
   e o coletor de informações de diagnóstico foi completamente removido para permitir jogar em servidores seguros sem rastreamento.
5. **Atualizações mais rápidas**\
   O [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) garante que os patches incluídos no Plazma estejam sempre atualizados, oferecendo as atualizações mais rápidas entre as plataformas de servidor baseadas no Paper.
6. **Otimização dos arquivos de configuração padrão**\
   Os arquivos de configuração padrão são otimizados, não sendo necessário otimizá-los manualmente.
7. **Funcionamento multi-thread de forma sistemática**\
   As mecânicas do jogo são assíncronas em relação às mecânicas do sistema não relacionadas ao jogo, reduzindo o [tempo de latência](#user-content-fn-4)[^4] para otimizar o servidor.
8. **Bloqueio do uso de espaço desnecessário**\
   Dados com valores semelhantes são combinados para reduzir o uso de memória.

#### Quer saber mais sobre o Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Casos de Uso <a href="#id-3" id="id-3"></a>

- **Plataforma que lida corretamente com plugins complexos**\
  O Plazma é usado nos servidores do desenvolvedor [IPECTER](https://github.com/IPECTER).\
  Mesmo com plugins próprios que funcionam com NMS e reflexão, e uma grande quantidade de datapacks complexos e extensos,\
  consegue lidar com mais de 100 jogadores sem queda de desempenho.
- **Plataforma que mantém um desempenho rápido em servidores de RPG**\
  Manteve 100 jogadores em um único cluster de forma estável sem queda de TPS, e permitiu que 250 jogadores jogassem confortavelmente em 4 clusters.
- **Plataforma que brilha em chunks/entidades**\
  Ao mudar de Purpur para Plazma em servidores de sobrevivência onde ocorriam atrasos no processamento de chunks e entidades, foi possível reduzir a maioria dos atrasos.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Tendência de usuários Plazma em tempo real">
</a>

## ⬇️ Download

Você pode baixar o Plazma na página abaixo.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Quer saber mais sobre o suporte de versões?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Plug-ins Bukkit, CraftBukkit, Spigot e Paper, Pufferfish, Purpur.

[^2]: Propriedade da Microsoft Corporation.

[^3]: Ao desativar o sistema de denúncias de chat, o chat é processado apenas no servidor, evitando o rastreamento de chat da Mojang.

[^4]: Tempo em que o jogo é interrompido para permitir o funcionamento do mecanismo do sistema.
