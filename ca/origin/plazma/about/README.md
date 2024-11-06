---
description: Descobreix què és Plazma com a plataforma de servidor.
---

# ❓ Què és Plazma?

- **Plazma** és una plataforma de servidor basada en [Paper](https://github.com/PaperMC/Paper) que recull només els avantatges de [Andròmeda](https://github.com/EarendelArchived/Andromeda) i [Fusió](https://github.com/RuinedTechnologyUnify/Fusion).
- Estem treballant per proporcionar sempre una alta estabilitat, un rendiment potent, actualitzacions ràpides i una gran quantitat de funcions.

## 📋 Objectius de Plazma <a href="#id-1" id="id-1"></a>

- Estem treballant per convertir-nos en una plataforma de servidor amb actualitzacions ràpides i alta estabilitat.
- Estem treballant per oferir una gran quantitat de funcions i un rendiment potent, igual que una plataforma de mod.
- Estem treballant per crear una plataforma lliure on es pugui personalitzar fins i tot els parches de la vanília.

## ⚙️ Característiques principals <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Actualitzacions més ràpides**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) manté sempre actualitzades les correccions incloses a Plazma, oferint les actualitzacions més ràpides entre les plataformes de servidor basades en Paper.
6. **Optimització dels fitxers de configuració bàsics**\
   Els fitxers de configuració per defecte estan optimitzats, evitant la necessitat d'optimitzar-los manualment.
7. **Funcionament sistemàtic de múltiples fils**\
   Asincronitza els mecanismes del sistema que no estan relacionats amb els mecanismes del joc per optimitzar el servidor i reduir els temps de retard[^4].
8. **Bloqueig de l'ús d'espai innecessari**\
   Combina les dades amb valors similars en un de sol per reduir l'ús de memòria.

## ✨ Casos d'ús <a href="#id-3" id="id-3"></a>

- **Plataforma que gestiona fins i tot els plugins més complexos de manera adequada**\
  El servidor de l'IPECTER utilitza Plazma.\
  Amb plugins propis que funcionen amb NMS i reflexió, i una gran quantitat de paquets de dades complexos aplicats,\
  és capaç de suportar més de 100 jugadors sense cap descens de rendiment.
- **Plataforma que manté un rendiment ràpid fins i tot en servidors RPG**\
  Ha mantingut 100 jugadors en un sol clúster sense cap descens de TPS de manera estable,\
  i ha permès a 250 jugadors jugar còmodament en 4 clústers.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Plataforma escollida per molts streamers**\
  És utilitzada com a cub per a la participació dels espectadors de molts streamers.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Descarregar

Pots descarregar Plazma des de la següent pàgina.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Vols més informació sobre les versions compatibles?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Plugins de Bukkit, CraftBukkit, Spigot i plugins de Paper, Pufferfish, Purpur.

[^2]: Propietat de Microsoft Corporation.

[^3]: En desactivar el sistema de denúncies de xat, el xat es processa únicament al servidor, evitant el seguiment del xat de Mojang.

[^4]: Temps en què el joc es deté temporalment perquè funcioni el mecanisme del sistema.
