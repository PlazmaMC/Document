---
description: Dowiedz się, czym jest Plazma jako platforma serwerowa.
---

# ❓ Czym jest Plazma?

- **Plazma** to platforma serwerowa oparta na [Paper](https://github.com/PaperMC/Paper), która czerpie tylko zalety z [Andromeda](https://github.com/EarendelArchived/Andromeda) i [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Staramy się zapewnić zawsze wysoką stabilność, potężne osiągi, szybkie aktualizacje i bogate funkcje.

## 📋 Cele Plazmy <a href="#id-1" id="id-1"></a>

- Dążymy do stworzenia platformy serwerowej charakteryzującej się szybkimi aktualizacjami i wysoką stabilnością.
- Staramy się zapewnić bogate funkcje i potężne osiągi, nie ustępując platformie modów.
- Dążymy do stworzenia platformy, która pozwala na swobodne dostosowanie łatki Vanilla.

## ⚙️ Główne cechy <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Najszybsze aktualizacje**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) zapewnia, że łaty w Plazmie zawsze pozostają aktualne, oferując najbardziej dynamiczne aktualizacje wśród platform serwerowych opartych na Paper.
6. **Optymalizacja podstawowych plików konfiguracyjnych**\
   Domyślne pliki konfiguracyjne są zoptymalizowane, co pozwala uniknąć konieczności ręcznej optymalizacji.
7. **Systematyczna wielowątkowość**\
   Asynchronizacja mechanizmów systemowych niezwiązanych z mechaniką gry pomaga zmniejszyć opóźnienia i zoptymalizować serwer.
8. **Blokuje niepotrzebne użycie pamięci**\
   Łączy dane o podobnej wartości w jedną, zmniejszając zużycie pamięci.

## ✨ Przykłady użycia <a href="#id-3" id="id-3"></a>

- **Platforma obsługująca nawet skomplikowane wtyczki**\
  Plazma jest używana na serwerze dewelopera [IPECTER](https://github.com/IPECTER).\
  Działa bez problemu nawet z własnymi wtyczkami opartymi na NMS i refleksji, mimo zastosowania skomplikowanych i obszernych pakietów danych,
  bez obniżania wydajności przy przyjęciu ponad 100 graczy.
- **Platforma zapewniająca szybką wydajność nawet na serwerach RPG**\
  Stabilnie utrzymała 100 graczy na jednym klastrze bez spadku TPS,
  Na 4 klastrach łącznie 250 graczy mogło komfortowo grać.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Platforma wybrana przez wielu streamerów**\
  Jest używana jako wiadro dla uczestnictwa widzów wielu streamerów.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Pobierz

Możesz pobrać Plazmę ze strony poniżej.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Chcesz dowiedzieć się więcej o obsługiwanych wersjach?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Wtyczki Bukkit, CraftBukkit, Spigot oraz wtyczki Paper, Pufferfish, Purpur.

[^2]: Przedsiębiorstwo Microsoft Corporation.

[^3]: Wyłączając system zgłaszania czatu, komunikacja w czacie jest przetwarzana tylko na serwerze, co pozwala uniknąć śledzenia czatu przez Mojang.

[^4]: Czas, w którym gra jest wstrzymywana, aby działał mechanizm systemowy.
