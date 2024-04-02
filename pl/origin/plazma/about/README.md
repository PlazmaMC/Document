---
description: Plazma는 어떤 서버 플랫폼인지 알아보세요.
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
   Dzięki oparciu o [Paper](https://github.com/PaperMC/Paper), większość [najnowszych wtyczek](#user-content-fn-1)[^1] dostępnych w Internecie działa poprawnie.
2. **Optymalizacja bez konieczności konfiguracji**\
   Zawiera wszystkie łaty [Pufferfish](https://github.com/pufferfish-gg/Pufferfish), a także niektóre własne optymalizacje i moduły, zapewniając najlepszą wydajność.
3. **Gra dostosowana do Twoich potrzeb**\
   [Purpur](https://github.com/PurpurMC/Purpur) zawarty w Plazmie pozwala na modyfikację ogólnych właściwości gry.
4. **Bezpieczne serwery do gry**\
   Zawiera [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports), który pozwala wyłączyć wprowadzony przez Mojang[^2] system zgłaszania czatu od wersji 1.19, a także całkowicie usuwa zbieranie informacji diagnostycznych, umożliwiając grę na bezpiecznym serwerze bez śledzenia.
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
  Plazma jest używana na serwerze programisty [IPECTER](https://github.com/IPECTER). Mimo zastosowania własnych wtyczek działających na NMS i refleksji, oraz dużej ilości skomplikowanych pakietów danych, serwer obsługuje ponad 100 graczy bez spadku wydajności.
- **Platforma utrzymująca szybkość na serwerach RPG**\
  Na pojedynczym klastrze utrzymywano 100 graczy bez spadków TPS, a na 4 klastrach łącznie 250 graczy mogło komfortowo grać.
- **Platforma świetnie radząca sobie z chunkami/encjami**\
  Zamiana Purpura na Plazmę na serwerze survival, gdzie występowały opóźnienia związane z obsługą chunków i encji, pozwoliła na znaczną redukcję opóźnień.
- **Platforma wybierana przez wielu streamerów**\
  Jest używana jako bukiet przez wielu popularnych streamerów.

<figure><img src="https://camo.githubusercontent.com/22acffd515755c2cee2078a7697ff35351c5ec7148eb2806deedbe63df1c4ed7/68747470733a2f2f6273746174732e6f72672f7369676e6174757265732f7365727665722d696d706c656d656e746174696f6e2f506c617a6d612e737667" alt=""><figcaption><p>Wykres użytkowników Plazmy na żywo</p></figcaption></figure>

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
