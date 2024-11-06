---
description: Dowiedz się o początkowych argumentach i właściwościach systemowych.
---

# 🎛️ Argumenty i właściwości

Zmienne początkowe i właściwości systemowe są wartościami dodawanymi do [polecenia używanego do uruchomienia Plazmy](#user-content-fn-1)[^1], które mają ogólny wpływ na działanie Plazmy.

Zgodnie z **parametrem lokalizacji** dodanym do [polecenia](#user-content-fn-2)[^2], zostanie podzielony na **argumenty początkowe** i **właściwości systemowe**.

***

## Właściwości systemowe <a href="#id-1" id="id-1"></a>

Właściwości systemowe są wartościami wprowadzanymi przed `-jar`, które są przetwarzane przez JVM przed inicjalizacją Plazmy.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Instrukcje <a href="#id-1.1" id="id-1.1"></a>

Właściwości systemowe są wprowadzane jako argumenty Java między `java` a `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` oznacza, że ten argument jest dodatkowym argumentem dedykowanym Plazmie, a

Jeśli nie podasz żadnej wartości dla właściwości, zostanie ona ustawiona na [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Domyślnie**: `750`

Jeśli istnieje więcej jednostek niż ustawiona wartość, dzielone są na wiele pakietów do przesłania.

#### `Paper.filterThreshold`

- **형태**: `Integer`
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

- **형태**: `Integer`
- **Domyślnie**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Domyślnie**: `80`

Ustawia maksymalną długość linii na znakach tablicy.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Domyślnie**: `(wersja świata) + 1`

Ustawia wersję informacji o aktualizacji świata, która zostanie zainicjowana jako pierwsza.

Przydatne przy dużej liczbie chunków do aktualizacji, ale w innych przypadkach nie jest używane.

#### `Paper.parseYamlCommentsByDefault`

- **Typ**: `Boolean`
- **Domyślnie**: `True`

Włącza obsługę komentarzy w plikach YAML.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Domyślnie**: `30`

Po określonym czasie (w sekundach) bez otrzymania danych od gracza, gracz zostanie wyrzucony.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Kolizja**: `Plazma.disableConfigOptimization`

Wprowadza bardziej agresywne optymalizacje początkowej konfiguracji.

Ze włączeniem tego opcji serwer staje się szybszy i bezpieczniejszy, ale może wpłynąć znacząco na rozgrywkę.

#### `Plazma.disableConfigOptimization`

- **Typ**: `Boolean`
- **Domyślnie**: `false`
- **Kolizja**: `Plazma.aggressiveOptimize`

Nie optymalizuje początkowej konfiguracji.

Ustawia domyślną konfigurację Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Typ**: `Boolean`
- **Domyślnie**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Typ**: `Boolean`
- **Domyślnie**: `false`

Wyłącza markę Plazma i używa domyślnego serwerowego faviconu w stylu Vanilla.

#### `Plazma.useVanillaConfiguration`

- **Typ**: `Boolean`
- **Domyślnie**: `false`
- **Kolizja**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Może to znacząco wpłynąć na bezpieczeństwo i wydajność serwera.

Wszelkie problemy związane z tym parametrem są odpowiedzialnością administratora serwera.
{% endhint %}

Ustawia początkową konfigurację na domyślne wartości dostarczane przez Mojang.

Wyłącza wszystkie załatane wady zastosowane przez Paper.

Wady mogą zostać ponownie włączone w konfiguracji Paper lub Plazma.

#### `Plazma.vanillaize`

- **Typ**: `Boolean`
- **Wartość domyślna**: `true`
- **Kolizja**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Ustawia początkową konfigurację bliżej stylu Vanilla.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Domyślnie**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Domyślnie**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Rozpoczyna serwer w trybie demonstracyjnym.

#### `eraseCache`

Usuwa pozostałe pliki pamięci podręcznej po aktualizacji świata.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Wyłącza panel interfejsu graficznego.

#### `nojline`

Wyłącz JLine i używaj konsoli Vanilla.

#### `online-mode`

- **Alias**: `o`
- **Domyślnie**: `(serwerowe właściwości)`

Wybierz, czy zweryfikować graczy przez serwery uwierzytelniające Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

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

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Domyślny**: `plugins`

Ustawia lokalizację folderu wtyczek.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Domyślny**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Domyślny**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Uruchamia serwer w trybie pełnej Vanilla.

#### `server-ip`

- **Alias**: `h`, `host`
- **Domyślnie**: `(serwerowe właściwości)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: Administratorzy poziomu 2 i wyższego są wyłączeni.

[^14]: Protokół internetowy, IP.
