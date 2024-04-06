---
description: Dowiedz się o początkowych argumentach i właściwościach systemowych.
---

# 🎛️ Argumenty i właściwości

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

Zgodnie z **parametrem lokalizacji** dodanym do [polecenia](#user-content-fn-2)[^2], zostanie podzielony na **argumenty początkowe** i **właściwości systemowe**.

***

## Właściwości systemowe <a href="#id-1" id="id-1"></a>

Właściwości systemowe są wartościami wprowadzanymi przed `-jar`, które są przetwarzane przez JVM przed inicjalizacją Plazmy.

{% hint style="warning" %}

**Modyfikacja właściwości systemu może zmienić sposób działania Plazmy oraz JVM i może mieć poważny wpływ na grę!**

Jeśli nie jesteś pewien, jaką rolę pełnią poszczególne właściwości systemu, **nie używaj ich w żadnym wypadku!**

{% endhint %}

### Instrukcje <a href="#id-1.1" id="id-1.1"></a>

Właściwości systemowe są wprowadzane jako argumenty Java między `java` a `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` oznacza, że ten argument jest dodatkowym argumentem dedykowanym Plazmie, a

Jeśli nie podasz żadnej wartości dla właściwości, zostanie ona ustawiona na [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Platformy serwerowe z rodziny Paperweight używają kropki w nazwach właściwości do odróżnienia właściwości dla każdej platformy.**

W niektórych terminalach, takich jak Windows Powershell, może nie być dozwolone używanie tych argumentów, dlatego na końcach argumentów należy dodać `"` [^4].

{% endhint %}

### Wszystkie właściwości systemowe <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Aktualizuje formaty znaków zastanych.

#### `debug.entities`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Włącza dzienniki debugowania informacji dotyczących jednostek.

#### `debug.rewriteForIDE`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza rewizję NMS, umożliwiając IDE poprawne ładowanie informacji debugowania oraz automatyczne mapowanie wersji wewnętrznych.

#### `disable.watchdog`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza system ostrzeżeń Watchdog w Spigocie.

#### `letMeReload`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza potwierdzenie komendy `/reload`.

{% hint style="danger" %}

**Komenda `/reload` jest bardzo niestabilna, dlatego wszelkie problemy po jej użyciu są związane z użytkownikiem.**

Jeśli jesteś deweloperem pluginów i musisz zaktualizować plugin, użyj hotswapu zamiast komendy `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza pluginy korzystające z systemu standardowego wejścia-wyjścia.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyświetla ostrzeżenie, gdy wykryto przestarzałe formatowanie w komponentach czatu.

#### `Paper.bypassHostCheck`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza weryfikację zgodności wzorca serwera podczas łączenia się z serwerem.

#### `Paper.debugDynamicMissingKeys`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Włącza dzienniki debugowania brakujących kluczy w obiektach NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Włącza dzienniki debugowania błędnych profili czaszek.

Loguje wszystkie błędne bloki czaszek w świecie wraz z ich lokalizacją.

#### `Paper.disableChannelLimit`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza limit 128 kanałów wtyczek [dla każdego](#user-content-fn-5)[^5] gracza.

#### `Paper.disableClassPrioritization`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza priorytetowanie klas pluginów.

Przydatne w przypadku problemów z cieniowaniem pluginów.

#### `Paper.disableFlushConsolidate`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza konsolidację spłukiwania Netty.

#### `Paper.excessiveTELimit`

- **Typ**: `Integer`
- **Domyślnie**: `750`

Jeśli istnieje więcej jednostek niż ustawiona wartość, dzielone są na wiele pakietów do przesłania.

#### `Paper.filterThreshold`

- **Typ**: `Integer`
- **Domyślnie**: `8192`

Ustawia maksymalny rozmiar pakietu, który serwer może przyjąć naraz.

#### `Paper.ignoreJavaVersion`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyłącza sprawdzanie wersji Javy.

{% hint style="danger" %}

**Może to spowodować próbę dostępu do nieistniejącego kodu przez JVM!**

Może to spowodować trwałe uszkodzenie plików na poziomie świata i całkowite zniszczenie mechaniki gry.

Wszelkie problemy wynikające z tego są twoją odpowiedzialnością, a Plazma nie udziela wsparcia w tej kwestii.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Typ**: `Integer`
- **Domyślnie**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Typ**: `Integer`
- **Domyślnie**: `80`

Ustawia maksymalną długość linii na znakach tablicy.

#### `Paper.minPrecachedDatafixVersion`

- **Typ**: `Integer`
- **Domyślnie**: `(wersja świata) + 1`

Ustawia wersję informacji o aktualizacji świata, która zostanie zainicjowana jako pierwsza.

Przydatne przy dużej liczbie chunków do aktualizacji, ale w innych przypadkach nie jest używane.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Domyślnie**: `True`

Włącza obsługę komentarzy w plikach YAML.

#### `Paper.playerConnection.keepAlive`

- **Typ**: `Integer`
- **Domyślnie**: `30`

Po określonym czasie (w sekundach) bez otrzymania danych od gracza, gracz zostanie wyrzucony.

Zazwyczaj [gra](#user-content-fn-7)[^7] regularnie wysyła [sygnał bicia serca](#user-content-fn-8)[^8] do serwera, więc [nie zostaniesz wyrzucony,](#user-content-fn-9)[^9] ale jeśli gra nie odpowiada, zostanie uznana za zderzoną i serwer przestanie obsługiwać gracza, a następnie go wyrzuci.

#### `Paper.skipServerPropertiesComments`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Ignoruje komentarze właściwości serwera.

#### `Paper.debug-sync-loads`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Włącza dzienniki debugowania synchronizacji chunków.

#### `Paper.enable-sync-chunk-writes`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Włącza domyślny system zapisu chunków w Minecraft.

To spowoduje, że każdy chunk będzie zapisywany sekwencyjnie, co znacząco obniży wydajność.

#### `Paper.explicit-flush`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Włącza wyraźne opróżnianie kanałów sieciowych.

#### `Paper.strict-thread-checks`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Zawsze rejestruje błędy, które nie występują w głównym wątku.

#### `Paper.tickList-warn-on-excessive-delay`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Wyświetla ostrzeżenie, gdy zaplanowane zadanie ma zbyt duże opóźnienie.

#### `Paperclip.patchOnly`

- **Typ**: `Boolean`
- **Domyślnie**: `False`

Jeśli używasz domyślnego pliku wykonywalnego, aplikuje tylko łatkę bez uruchamiania serwera.

#### `Plazma.aggressiveOptimize`

- **Typ**: `Boolean`
- **Domyślnie**: `false`

{% hint style="warning" %}

**Ta właściwość będzie przeniesiona jako argument początkowy po wersji 1.20.5.**

{% endhint %}

Zwiększa restrykcje konfiguracji stosowane podczas pierwszego uruchomienia.

Aktywacja sprawia, że serwer staje się szybszy i bezpieczniejszy, ale może blokować niektóre mechanizmy lub znacząco wpłynąć na rozgrywkę.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Domyślnie**: `false`

Zapobiega wyświetlaniu [ostrzeżeń](#user-content-fn-11)[^11] podczas inicjowania Plazmy.

### Używane atrybuty <a href="#id-1.3" id="id-1.3"></a> zostały zakończone

Poniższe atrybuty systemowe są atrybutami, które zostały zakończone.

#### `timings.bypassMax`

- **Typ**: `Boolean`
- **Domyślnie**: `false`
- **Zakończone**: Timings zostały usunięte z Plazmy

Decyduje, czy wartość przekazywana do interfejsu API Timingsa Aikara może przekroczyć maksymalną wartość.

Nawet jeśli to jest zrobione, jeśli nie jest obsługiwane przez API, zostanie nałożone ograniczenie prędkości.

***

## Argument początkowy <a href="#id-2" id="id-2"></a>

Argument początkowy jest przekazywany po `-jar *.jar`, aby zainicjować Plazmę i jest przetwarzany razem z nią.

### Sposób użycia <a href="#id-2.1" id="id-2.1"></a>

Atrybuty systemowe są przekazywane jako argumenty programu po `-jar *.jar`.

Na przykład, jeśli chcesz zastosować argument początkowy `nogui`,\
to wprowadź go w ten sposób, a Plazma przetworzy ten argument podczas inicjalizacji.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Całkowity argument początkowy <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Domyślnie**: `bukkit.yml`

Ustawia nazwę i lokalizację [pliku konfiguracyjnego Bukkita](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Domyślnie**: `commands.yml`

Ustawia nazwę i lokalizację [pliku konfiguracyjnego komend Bukkita](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Domyślnie**: `server.properties`

Ustawia nazwę i lokalizację [pliku właściwości serwera](../reference/configurations/property.md).

#### `demo`

Rozpoczyna serwer w trybie demonstracyjnym.

#### `eraseCache`

Usuwa pozostałe pliki pamięci podręcznej po aktualizacji świata.

#### `forceUpgrade`

Niezależnie od wersji, wymusza [aktualizację](#user-content-fn-12)[^12] świata.

#### `help`

- **Alias**: `?`

Wyświetla pełny argument początkowy i opis Plazmy.

#### `initSettings`

Tworzy tylko plik konfiguracyjny i zamyka serwer.

#### `jfrProfile`

Aktywuje profilowanie JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Domyślnie**: `(serwerowe właściwości)`

Ustawia maksymalną liczbę [graczy](#user-content-fn-14)[^14] dozwoloną.

#### `nogui`

Wyłącza panel interfejsu graficznego.

#### `nojline`

Wyłącz JLine i używaj konsoli Vanilla.

#### `online-mode`

- **Alias**: `o`
- **Domyślnie**: `(serwerowe właściwości)`

Wybierz, czy zweryfikować graczy przez serwery uwierzytelniające Mojang.

**Jeśli nie używasz Velocity lub innych proxy, możesz zostać ukarany za naruszenie [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Alias**: `paper`
- **Domyślny**: `paper.yml`

{% hint style="warning" %}

**Ten argument został wycofany z użycia po wersji 1.19.4**

{% endhint %}

Ustawia lokalizację pliku konfiguracyjnego PaperSpigot, który został wycofany z użycia.

Służy do przenoszenia istniejącej konfiguracji do nowego pliku konfiguracyjnego, który nie jest już używany.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Domyślny**: `config`

Ustawia nazwę i lokalizację folderu, w którym znajdują się [pliki konfiguracyjne Paper](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Ustawia nazwę i lokalizację folderu, w którym znajdują się [pliki konfiguracyjne Plazma](../reference/configurations/plazma/README.md).

#### `plugins`

- **Alias**: `p`
- **Domyślny**: `plugins`

Ustawia lokalizację folderu wtyczek.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Domyślny**: `pufferfish.yml`

Ustawia nazwę i lokalizację [pliku konfiguracyjnego Pufferfish](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Domyślny**: `purpur.yml`

Ustawia nazwę i lokalizację [pliku konfiguracyjnego Purpur](../reference/configurations/purpur/README.md).

#### `safeMode`

Uruchamia serwer w trybie pełnej Vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Domyślnie**: `(serwerowe właściwości)`

Ustawia nazwę hosta serwera lub adres [protokołu internetowego](#user-content-fn-13)[^13].

#### `server-port`

- **Alias**: `p`, `port`
- **Domyślnie**: `(serwerowe właściwości)`

Ustawia port serwera.

#### `server-name`

- **Domyślny**: `A Plazma Server`

Ustawia nazwę serwera.

#### `spigot-settings`

- **Alias**: `S`
- **Domyślny**: `spigot.yml`

Ustawia nazwę i lokalizację [pliku konfiguracyjnego Spigot](../reference/configurations/spigot.md).

#### `version`

- **Alias**: `v`

Wyświetla wersję Plazmy.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Domyślny**: `(folder serwera)`

Ustawia lokalizację, w której są przechowywane pliki świata.

#### `world-name`

- **Alias**: `w`, `world`
- **Domyślnie**: `(serwerowe właściwości)`

Ustawia nazwę pliku świata.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Zmienia sposób obsługi argumentów w zależności od dodatkowego miejsca.

[^3]: Na przykład, jeśli chcesz ustawić `Plazma.iKnowWhatIAmDoing` na `true`, zamiast wpisywać `-DPlazma.iKnowWhatIAmDoing=true`, wystarczy wpisać `-DPlazma.iKnowWhatIAmDoing` i będzie działać tak samo.

[^4]: Na przykład, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detektor zdarzeń.

[^6]: Detektor zdarzeń.

[^7]: Klient.

[^8]: Sygnał informujący o poprawnym połączeniu z serwerem, podobnie jak bicie serca.

[^9]: Dzięki funkcji wyrzucania AFK w Purpur, można wyrzucić graczy, którzy są nieaktywni.

[^10]: Synchroniczny system tworzenia chunków, Sync Chunk Write System.

[^11]: `OSTRZEŻENIE! Plazma może powodować niespodziewane problemy, dlatego koniecznie przetestuj go dokładnie przed użyciem na serwerze publicznym.`

[^12]: `Optymalizacja świata` w grach działa na tej samej zasadzie.

[^13]: Protokół internetowy, IP.

[^14]: Administratorzy poziomu 2 i wyższego są wyłączeni.
