---
description: Dowiedz się o początkowych argumentach i właściwościach systemowych.
---

# 🎛️ Argumenty i właściwości

Początkowe zmienne i właściwości systemowe to wartości dodawane do [polecenia używanego do uruchomienia Plazmy](#user-content-fn-1)[^1], które umożliwiają zmianę wartości, które nie mogą być zmienione po uruchomieniu Plazmy.

W zależności od [miejsca, w którym jest dodawane do polecenia](#user-content-fn-2)[^2], dzielą się na **początkowe argumenty** i **właściwości systemowe**.

***

## Właściwości systemowe <a href="#id-1" id="id-1"></a>

Właściwości systemowe są wartościami wprowadzanymi przed `-jar`, które są przetwarzane przez JVM przed inicjalizacją Plazmy.

{% hint style="warning" %}

**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**

{% endhint %}

### Instrukcje <a href="#id-1.1" id="id-1.1"></a>

Właściwości systemowe są wprowadzane jako argumenty Java między `java` a `-jar`.

Na przykład, jeśli chcesz zastosować właściwość systemową `Plazma.dummyProperty`,\
wprowadzając ją w ten sposób, wartość `37` zostanie przypisana do tej właściwości podczas inicjalizacji Plazmy.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` oznacza, że ten argument jest dodatkowym argumentem dedykowanym Plazmie, a

jeśli nie wprowadzisz żadnej wartości, wartość zostanie [\`ustawiona na wartość „true”.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야 합니다.](#user-content-fn-4)[^4]

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

**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

Wyłącza limit 128 kanałów pluginów na gracza[^5].

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

**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Może to spowodować trwałe uszkodzenie plików na poziomie świata i całkowite zniszczenie mechaniki gry.

Wszelkie problemy wynikające z tego są twoją odpowiedzialnością, a Plazma nie udziela wsparcia w tej kwestii.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Typ**: `Integer`
- **Domyślnie**: `64`

Ustawia limit nazw kanałów pluginów[^6].

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

Zazwyczaj gra[^7] nadal wysyła [sygnał bicza serwera](#user-content-fn-8)[^8], więc nie zostaniesz wyrzucony, ale]\(#user-content-fn-9)[^9] jeśli gra nie odpowiada, serwer uzna to za awarię i przestanie obsługiwać gracza, wyrzucając go.

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

**해당 속성은 1.20.5 이후 시작 인수로 이동 될 예정입니다.**

{% endhint %}

Zwiększa restrykcje konfiguracji stosowane podczas pierwszego uruchomienia.

Aktywacja sprawia, że serwer staje się szybszy i bezpieczniejszy, ale może blokować niektóre mechanizmy lub znacząco wpłynąć na rozgrywkę.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Domyślnie**: `false`

Tłumi komunikat ostrzegawczy[^11], który pojawia się podczas inicjalizacji Plazmy.

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

**이 인수는 1.19.4 이후 사용이 중지되었습니다**

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
