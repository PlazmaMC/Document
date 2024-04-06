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

1. **Potężny ekosystem wtyczek**\
   [Paper](https://github.com/PaperMC/Paper) bazuje na nim,
   Większość [najnowszych wtyczek](#user-content-fn-1)[^1] dostępnych do pobrania z internetu działa poprawnie.
2. **Optymalizacja bez potrzeby konfiguracji**\
   Wszystkie łaty [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) są zawarte,
   Zawiera pewne optymalizacje i moduły wewnętrzne, zapewniając najlepszą wydajność.
3. **Gra dostosowana do Twoich potrzeb**\
   [Purpur](https://github.com/PurpurMC/Purpur) zawarty w Plazma pozwala na
   modyfikację ogólnych właściwości gry.
4. **Bezpieczne serwery do gry**\
   Zawiera [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) dodane od wersji 1.19
   [Mojang](#user-content-fn-2)[^2] [system zgłaszania czatu](#user-content-fn-3)[^3] można dezaktywować,\
   Diagnostyczny zbieracz danych został całkowicie usunięty, umożliwiając grę na bezpiecznych serwerach bez śledzenia.
5. **Najszybsze aktualizacje**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) zapewnia, że łaty w Plazmie zawsze pozostają aktualne, oferując najbardziej dynamiczne aktualizacje wśród platform serwerowych opartych na Paper.
6. **Optymalizacja podstawowych plików konfiguracyjnych**\
   Domyślne pliki konfiguracyjne są zoptymalizowane, co pozwala uniknąć konieczności ręcznej optymalizacji.
7. **Systematyczna wielowątkowość**\
   Asynchronizacja mechanizmów systemowych niezwiązanych z mechaniką gry pomaga zmniejszyć opóźnienia i zoptymalizować serwer.
8. **Blokuje niepotrzebne użycie pamięci**\
   Łączy dane o podobnej wartości w jedną, zmniejszając zużycie pamięci.

#### Chcesz dowiedzieć się więcej o Plazmie? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Przykłady użycia <a href="#id-3" id="id-3"></a>

- **Platforma obsługująca nawet skomplikowane wtyczki**\
  Plazma jest używana na serwerze dewelopera [IPECTER](https://github.com/IPECTER).\
  Działa bez problemu nawet z własnymi wtyczkami opartymi na NMS i refleksji, mimo zastosowania skomplikowanych i obszernych pakietów danych,
  bez obniżania wydajności przy przyjęciu ponad 100 graczy.
- **Platforma zapewniająca szybką wydajność nawet na serwerach RPG**\
  Stabilnie utrzymała 100 graczy na jednym klastrze bez spadku TPS,
  Na 4 klastrach łącznie 250 graczy mogło komfortowo grać.
- **Platforma oświetlająca chunki/entitety**\
  Zmiana platformy z Purpur na Plazma dla serwera survival, gdzie występowały opóźnienia w przetwarzaniu chunków i entitetów,
  pozwoliła na znaczną redukcję opóźnień.
- **Platforma wybierana przez wielu streamerów**\
  Jest wybierana przez wielu widzów streamerów jako ich preferowana platforma.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Real-time Trend of Plazma Users</p></figcaption>
</figure>

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
