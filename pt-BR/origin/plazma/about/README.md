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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Atualizações mais rápidas**\
   O [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) garante que os patches incluídos no Plazma estejam sempre atualizados, oferecendo as atualizações mais rápidas entre as plataformas de servidor baseadas no Paper.
6. **Otimização dos arquivos de configuração padrão**\
   Os arquivos de configuração padrão são otimizados, não sendo necessário otimizá-los manualmente.
7. **Funcionamento multi-thread de forma sistemática**\
   As mecânicas do jogo são assíncronas em relação às mecânicas do sistema não relacionadas ao jogo, reduzindo o [tempo de latência](#user-content-fn-4)[^4] para otimizar o servidor.
8. **Bloqueio do uso de espaço desnecessário**\
   Dados com valores semelhantes são combinados para reduzir o uso de memória.

## ✨ Casos de Uso <a href="#id-3" id="id-3"></a>

- **Plataforma que lida corretamente com plugins complexos**\
  O Plazma é usado nos servidores do desenvolvedor [IPECTER](https://github.com/IPECTER).\
  Mesmo com plugins próprios que funcionam com NMS e reflexão, e uma grande quantidade de datapacks complexos e extensos,\
  consegue lidar com mais de 100 jogadores sem queda de desempenho.
- **Plataforma que mantém um desempenho rápido em servidores de RPG**\
  Manteve 100 jogadores em um único cluster de forma estável sem queda de TPS, e permitiu que 250 jogadores jogassem confortavelmente em 4 clusters.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Plataforma escolhida por muitos streamers**\
  É escolhida como um balde de participação dos espectadores por muitos streamers.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
