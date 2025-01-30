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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Cele mai rapide actualizări**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) asigură că patch-urile incluse în Plazma sunt întotdeauna actualizate, oferind cele mai rapide actualizări printre platformele de server bazate pe Paper.
6. **Optimizarea fișierelor de configurare implicite**\
   Fișierele de configurare aplicate implicit sunt optimizate, astfel încât nu este necesară optimizarea acestora manual.
7. **Funcționare sistematică pe mai multe fire de execuție**\
   Asincronizează mecanismele de sistem care nu sunt legate de mecanismele jocului pentru a reduce [timpul de întârziere](#user-content-fn-4) și a optimiza serverul.
8. **Blocarea utilizării spațiilor inutile**\
   Combinați datele cu valori similare într-una singură pentru a reduce consumul de memorie.

## ✨ Studii de caz <a href="#id-3" id="id-3"></a>

- **Platforma care gestionează corect și plugin-urile complexe**\
  Plazma este utilizat pe serverul dezvoltatorului [IPECTER](https://github.com/IPECTER).\
  Cu propriul său plugin care funcționează cu NMS și reflecție, și cu o cantitate mare și complexă de pachete de date aplicate, serverul poate susține peste 100 de jucători fără scădere de performanță.
- **Platforma care menține performanța rapidă și pe serverele RPG**\
  A reușit să mențină 100 de jucători pe un singur cluster fără scădere a TPS-ului și să permită 250 de jucători să joace confortabil pe 4 clustere.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Platforma aleasă de mulți streameri**\
  Este aleasă ca un recipient pentru implicarea spectatorilor multor streameri.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
