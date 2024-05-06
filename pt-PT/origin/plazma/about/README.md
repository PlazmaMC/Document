---
description: Descubra o que é o Plazma como plataforma de servidor.
---

# ❓ O que é o Plazma?

- **Plazma** é uma plataforma de servidor baseada no [Paper](https://github.com/PaperMC/Paper) que traz apenas as vantagens do [Andromeda](https://github.com/EarendelArchived/Andromeda) e [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Estamos empenhados em fornecer sempre alta estabilidade, desempenho poderoso, atualizações rápidas e uma ampla gama de recursos.

## 📋 Objetivos do Plazma <a href="#id-1" id="id-1"></a>

- Estamos empenhados em ser uma plataforma de servidor com atualizações rápidas e alta estabilidade.
- Estamos empenhados em fornecer uma ampla gama de recursos e desempenho poderoso, não menos do que uma plataforma de modos.
- Estamos empenhados em criar uma plataforma livre que permita a personalização dos patches do Vanilla.

## ⚙️ Principais características <a href="#id-2" id="id-2"></a>

1. **Ecossistema de plugins poderoso**\
   Com base no [Paper](https://github.com/PaperMC/Paper),
   a maioria dos [plugins mais recentes](#user-content-fn-1)[^1] disponíveis para download na internet funcionam corretamente.
2. **Otimização sem necessidade de configuração**\
   Com todos os patches do [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) incluídos,
   oferece desempenho máximo com algumas otimizações internas e modos embutidos.
3. **Jogo personalizável como desejar**\
   O [Purpur](https://github.com/PurpurMC/Purpur) incluído no Plazma permite modificar
   as propriedades gerais do jogo conforme desejado.
4. **Servidor seguro para jogar**\
   Com [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) incluído, a partir da versão 1.19,
   é possível desativar o [sistema de denúncia de chat](#user-content-fn-3)[^3] da [Mojang](#user-content-fn-2)[^2] e\
   remover completamente o coletor de informações de diagnóstico para jogar em um servidor seguro sem rastreamento.
5. **Atualizações mais rápidas**\
   O [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) garante que os patches incluídos no Plazma sejam sempre mantidos atualizados, oferecendo as atualizações mais rápidas entre as plataformas de servidor baseadas em Paper.
6. **Otimização dos arquivos de configuração padrão**\
   Os arquivos de configuração padrão são otimizados, não sendo necessário otimizá-los manualmente.
7. **Operação multithread de forma sistemática**\
   As mecânicas do jogo e os sistemas mecânicos não relacionados ao jogo são assíncronos, reduzindo [o tempo de latência](#user-content-fn-4)[^4] para otimizar o servidor.
8. **Bloqueio do uso de espaço desnecessário**\
   Os dados com valores semelhantes são combinados para reduzir o uso de memória.

#### Quer saber mais sobre o Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Casos de uso <a href="#id-3" id="id-3"></a>

- **Plataforma que lida corretamente com plugins complexos**\
  Plazma é usado nos servidores do desenvolvedor [IPECTER](https://github.com/IPECTER).\
  Mesmo com plugins personalizados que funcionam com NMS e reflexão, e com uma grande quantidade de datapacks complexos aplicados,\
  é capaz de lidar com mais de 100 jogadores sem queda de desempenho.
- **Plataforma mantendo desempenho rápido em servidores de RPG**\
  Manteve 100 jogadores em um único cluster sem queda de TPS de forma estável, e\
  250 jogadores no total em 4 clusters puderam jogar confortavelmente.
- **Plataforma que ilumina em chunks/entidades**\
  Ao trocar do Purpur para o Plazma, foi possível reduzir a maioria dos atrasos em servidores de sobrevivência onde ocorriam atrasos no processamento de chunks e entidades.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Real-time Plazma tendência de usuários">
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

[^2]: Microsoft Corporation.

[^3]: Ao desativar o sistema de relatório de chat, o chat é processado apenas no servidor, impedindo o rastreamento de chat da Mojang.

[^4]: Tempo em que o jogo fica parado para que o sistema mecânico funcione.
