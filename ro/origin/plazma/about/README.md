---
description: Aflați mai multe despre platforma de servere Plazma.
---

# ❓ Ce este Plazma?

- **Plazma** este o platformă de server bazată pe [Paper](https://github.com/PaperMC/Paper) care își aduce doar avantajele din [Andromeda](https://github.com/EarendelArchived/Andromeda) și [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Ne străduim să oferim întotdeauna o stabilitate ridicată, performanță puternică, actualizări rapide și o gamă extinsă de funcționalități.

## 📋 Obiectivele Plazma <a href="#id-1" id="id-1"></a>

- Ne străduim să devenim o platformă de server cu actualizări rapide și o stabilitate ridicată.
- Ne străduim să oferim o gamă extinsă de funcționalități și performanță puternică, la fel de bune ca cele ale unei platforme de moduri.
- Ne străduim să creăm o platformă liberă și personalizabilă care să permită și patch-uri pentru Vanilla.

## ⚙️ Caracteristici cheie <a href="#id-2" id="id-2"></a>

1. **Ecosistem puternic de plugin-uri**\
   Bazat pe [Paper](https://github.com/PaperMC/Paper), Plazma suportă majoritatea [plugin-urilor recente](#user-content-fn-1) disponibile pentru descărcare de pe internet.
2. **Optimizare fără nevoi de configurare**\
   Toate patch-urile de la [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sunt incluse, iar unele optimizări interne și moduri sunt integrate pentru a oferi cea mai bună performanță.
3. **Personalizarea jocului după bunul plac**\
   [Purpur](https://github.com/PurpurMC/Purpur) inclus în Plazma permite modificarea atributelor generale ale jocului.
4. **Server care joacă în condiții de siguranță**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) este inclus pentru a dezactiva [Sistemul de raportare a chat-ului](#user-content-fn-3)[^3] adăugat începând cu versiunea 1.19 de la [Mojang](#user-content-fn-2)[^2], iar colectorul de informații de diagnosticare este complet eliminat pentru a juca pe un server sigur fără urmărire.
5. **Cele mai rapide actualizări**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) asigură că patch-urile incluse în Plazma sunt întotdeauna actualizate, oferind cele mai rapide actualizări printre platformele de server bazate pe Paper.
6. **Optimizarea fișierelor de configurare implicite**\
   Fișierele de configurare aplicate implicit sunt optimizate, astfel încât nu este necesară optimizarea acestora manual.
7. **Funcționare sistematică pe mai multe fire de execuție**\
   Asincronizează mecanismele de sistem care nu sunt legate de mecanismele jocului pentru a reduce [timpul de întârziere](#user-content-fn-4) și a optimiza serverul.
8. **Blocarea utilizării spațiilor inutile**\
   Combinați datele cu valori similare într-una singură pentru a reduce consumul de memorie.

#### Doriți să aflați mai multe despre Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Studii de caz <a href="#id-3" id="id-3"></a>

- **Platforma care gestionează corect și plugin-urile complexe**\
  Plazma este utilizată pe serverul dezvoltatorului [IPECTER](https://github.com/IPECTER). Cu plugin-uri personalizate care funcționează cu NMS și reflexie, precum și cu o cantitate mare și complexă de datapack-uri, poate susține peste 100 de jucători fără scăderea performanței.
- **Platforma care menține performanța rapidă și pe serverele RPG**\
  Pentru un singur cluster, a reușit să mențină 100 de jucători fără scăderea TPS-ului și pe 4 clustere, un total de 250 de jucători au putut juca fără probleme.
- **Platforma care face lumina în chunk-uri/entități**\
  Schimbarea de la Purpur la Plazma pentru platforma serverului unui server de supraviețuire care avea întârzieri în procesarea chunk-urilor și entităților a permis reducerea majorității întârzierilor.
- **Platforma aleasă de mulți streameri**\
  Este folosită ca server de vizualizare pentru mulți streameri cunoscuți.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Evolutia utilizatorilor Plazma in timp real</p></figcaption>
</figure>

## ⬇️ Descărcare

Puteți descărca Plazma de pe pagina de mai jos.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Doriți să aflați mai multe despre suportul pentru versiuni?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Plugin-urile Bukkit, CraftBukkit, Spigot și plugin-urile Paper, Pufferfish, Purpur.

[^2]: De la Microsoft Corporation.

[^3]: Dacă dezactivați sistemul de raportare a chat-ului, chat-ul este gestionat exclusiv pe server, prevenind urmărirea chat-ului de către Mojang.

[^4]: Timpul când jocul se oprește pentru ca mecanismele de sistem să funcționeze.
