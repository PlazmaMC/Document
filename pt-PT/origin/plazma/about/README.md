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

1. **Ecossistema de plug-ins poderoso**\
   Com base no [Paper](https://github.com/PaperMC/Paper), a maioria dos [plug-ins mais recentes disponíveis para download na Internet](#user-content-fn-1)[^1] funcionam corretamente.
2. **Otimização sem necessidade de configuração**\
   Com todos os patches do [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) incluídos, e algumas otimizações internas e modos integrados, oferece o melhor desempenho.
3. **Jogo personalizável conforme desejado**\
   O [Purpur](https://github.com/PurpurMC/Purpur) incluído no Plazma permite a modificação de atributos gerais do jogo.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 [Mojang](#user-content-fn-2)[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며, 진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
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

- **Plataforma que lida corretamente com plug-ins complexos**\
  O Plazma está sendo usado nos servidores do desenvolvedor [IPECTER](https://github.com/IPECTER). Mesmo com plug-ins personalizados que funcionam com NMS e reflexão, e uma grande quantidade de data packs complexos aplicados, ele é capaz de lidar com mais de 100 jogadores sem queda de desempenho.
- **Plataforma que mantém um desempenho rápido mesmo em servidores RPG**\
  Foi possível manter 100 jogadores em um único cluster sem queda de TPS, e em 4 clusters, um total de 250 jogadores puderam jogar confortavelmente.
- **Plataforma que brilha em chunks/entidades**\
  Ao mudar de Purpur para Plazma em servidores de sobrevivência onde ocorriam atrasos no processamento de chunks e entidades, foi possível reduzir a maioria dos atrasos.
- **Plataforma escolhida por muitos streamers**\
  É usada como um bucket de visualização para muitos streamers conhecidos.

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

[^2]: Microsoft Corporation.

[^3]: Ao desativar o sistema de relatório de chat, o chat é processado apenas no servidor, impedindo o rastreamento de chat da Mojang.

[^4]: Tempo em que o jogo fica parado para que o sistema mecânico funcione.
