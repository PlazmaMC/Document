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

1. **Ecossistema de plug-ins poderoso**\
   Com base no [Paper](https://github.com/PaperMC/Paper), a maioria dos [plug-ins mais recentes](#user-content-fn-1)[^1] disponíveis na internet funcionam corretamente.
2. **Otimização sem necessidade de configuração**\
   Com todos os patches do [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) incluídos, juntamente com otimizações internas e modos embutidos, oferece o máximo desempenho.
3. **Personalização do jogo conforme desejado**\
   O [Purpur](https://github.com/PurpurMC/Purpur) incluído no Plazma permite modificar os atributos gerais do jogo.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 [Mojang](#user-content-fn-2)[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며, 진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
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

- **Plataforma que lida corretamente com plug-ins complexos**\
  O Plazma está sendo usado nos servidores do desenvolvedor [IPECTER](https://github.com/IPECTER). Mesmo com plug-ins personalizados que operam com NMS e reflexão, e uma grande quantidade de data packs complexos, ele é capaz de lidar com mais de 100 jogadores sem queda de desempenho.
- **Plataforma mantendo alto desempenho em servidores de RPG**\
  Manteve 100 jogadores em um único cluster sem queda de TPS e permitiu que 250 jogadores jogassem confortavelmente em 4 clusters.
- **Plataforma que brilha em chunks/entidades**\
  Ao mudar de Purpur para Plazma em servidores de sobrevivência que sofriam atrasos no processamento de chunks e entidades, foi possível reduzir a maioria dos atrasos.
- **Plataforma escolhida por muitos streamers**\
  É utilizada como um balde de visão dos espectadores por muitos streamers de sucesso.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Real-time tendência de uso do Plazma</p></figcaption>
</figure>

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
