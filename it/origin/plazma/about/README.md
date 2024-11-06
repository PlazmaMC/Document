---
description: Scopri di più su cosa sia Plazma come piattaforma server.
---

# ❓ Cosa è Plazma?

- **Plazma** è una piattaforma server basata su [Paper](https://github.com/PaperMC/Paper) che porta solo i vantaggi di [Andromeda](https://github.com/EarendelArchived/Andromeda) e [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Ci sforziamo di offrire sempre elevata stabilità, potente performance, aggiornamenti rapidi e una vasta gamma di funzionalità.

## 📋 Obiettivo di Plazma <a href="#id-1" id="id-1"></a>

- Ci sforziamo di diventare una piattaforma server con aggiornamenti rapidi e alta stabilità.
- Ci sforziamo di offrire una vasta gamma di funzionalità e potenti performance paragonabili alle piattaforme mod.
- Ci sforziamo di creare una piattaforma libera che consenta la personalizzazione dei patch di Vanilla.

## ⚙️ Caratteristiche principali <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Aggiornamenti più veloci**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) mantiene costantemente aggiornati i patch inclusi in Plazma, offrendo gli aggiornamenti più rapidi tra le piattaforme server basate su Paper.
6. **Ottimizzazione dei file di configurazione predefiniti**\
   I file di configurazione predefiniti sono ottimizzati, evitando la necessità di ottimizzarli manualmente.
7. **Funzionamento multithread sistematico**\
   Asincronizzando i meccanismi di sistema non correlati al gioco, si riduce il [tempo di latenza](#user-content-fn-4)[^4] ottimizzando il server.
8. **Blocco dell'uso di spazio non necessario**\
   Unendo i dati con valori simili in un unico dato, si riduce l'utilizzo della memoria.

## ✨ Esempi di utilizzo <a href="#id-3" id="id-3"></a>

- **Piattaforma che gestisce anche plugin complessi in modo corretto**\
  Il server dello sviluppatore [IPECTER](https://github.com/IPECTER) utilizza Plazma.\
  Con plugin proprietari che funzionano con NMS e riflessioni, e una vasta quantità di pacchetti dati complessi applicati,\
  é in grado di gestire più di 100 giocatori senza alcuna riduzione delle prestazioni.
- **Piattaforma che mantiene prestazioni elevate anche sui server RPG**\
  Ha mantenuto stabilmente 100 giocatori su un singolo cluster senza riduzione del TPS,\
  e ha permesso a un totale di 250 giocatori su 4 cluster di giocare senza problemi.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Piattaforma scelta da molti streamer**\
  È stata scelta come un secchiello per la partecipazione degli spettatori di molti streamer.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Scarica

Puoi scaricare Plazma dalla pagina sottostante.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Vuoi informazioni dettagliate sul supporto alle versioni?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Plugin di Bukkit, CraftBukkit, Spigot e plugin di Paper, Pufferfish, Purpur.

[^2]: Microsoft Corporation.

[^3]: Disattivando il sistema di segnalazione chat, la chat viene gestita solo sul server impedendo il tracciamento della chat da parte di Mojang.

[^4]: Tempo in cui il gioco si ferma per far funzionare i meccanismi di sistema.
