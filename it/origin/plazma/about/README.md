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

1. **Ecosistema di plugin potente**\
   Basato su [Paper](https://github.com/PaperMC/Paper),
   la maggior parte dei [plugin più recenti](#user-content-fn-1)[^1] disponibili su Internet funziona correttamente.
2. **Ottimizzazione senza necessità di configurazione**\
   Tutti i patch di [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sono inclusi,
   con alcune ottimizzazioni interne e moduli integrati per offrire le massime prestazioni.
3. **Gioco personalizzabile a piacimento**\
   [Purpur](https://github.com/PurpurMC/Purpur) incluso in Plazma consente di modificare
   le proprietà generali del gioco a tuo piacimento.
4. **Server che gioca in modo sicuro**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) è incluso dall'aggiunta della versione 1.19
   [Mojang](#user-content-fn-2)[^2] ha reso possibile disattivare il [sistema di segnalazione della chat](#user-content-fn-3)[^3],\
   rimuovendo completamente il raccoglitore di informazioni diagnostico, è possibile giocare su un server sicuro e anonimo.
5. **Aggiornamenti più veloci**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) mantiene costantemente aggiornati i patch inclusi in Plazma, offrendo gli aggiornamenti più rapidi tra le piattaforme server basate su Paper.
6. **Ottimizzazione dei file di configurazione predefiniti**\
   I file di configurazione predefiniti sono ottimizzati, evitando la necessità di ottimizzarli manualmente.
7. **Funzionamento multithread sistematico**\
   Asincronizzando i meccanismi di sistema non correlati al gioco, si riduce il [tempo di latenza](#user-content-fn-4)[^4] ottimizzando il server.
8. **Blocco dell'uso di spazio non necessario**\
   Unendo i dati con valori simili in un unico dato, si riduce l'utilizzo della memoria.

#### Vuoi saperne di più su Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Esempi di utilizzo <a href="#id-3" id="id-3"></a>

- **Piattaforma che gestisce anche plugin complessi in modo corretto**\
  Il server dello sviluppatore [IPECTER](https://github.com/IPECTER) utilizza Plazma.\
  Con plugin proprietari che funzionano con NMS e riflessioni, e una vasta quantità di pacchetti dati complessi applicati,\
  é in grado di gestire più di 100 giocatori senza alcuna riduzione delle prestazioni.
- **Piattaforma che mantiene prestazioni elevate anche sui server RPG**\
  Ha mantenuto stabilmente 100 giocatori su un singolo cluster senza riduzione del TPS,\
  e ha permesso a un totale di 250 giocatori su 4 cluster di giocare senza problemi.
- **Piattaforma che mostra luce nei chunk/entità**\
  Cambiando da Purpur a Plazma su un server di sopravvivenza dove c'erano ritardi nel trattare i chunk e le entità,\
  é stato possibile ridurre la maggior parte dei ritardi.
- **Piattaforma scelta da molti streamer**\
  Utilizzata come server Bucket preferito da molti spettatori degli streamer.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Tendenza degli utenti Plazma in tempo reale</p></figcaption>
</figure>

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
