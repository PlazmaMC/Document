---
description: Saznajte o početnim argumentima i svojstvima sustava.
---

# 🎛️ Argumenti i svojstva

Početna vrijednost i svojstva sustava su vrijednosti koje se dodaju [naredbi koja se koristi](#user-content-fn-1)[^1] za izvođenje Plazma, što ima opći utjecaj na rad Plazme.

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## Svojstva sustava <a href="#id-1" id="id-1"></a>

Svojstva sustava su vrijednosti koje se unose ispred `-jar` i obrađuju se od strane JVM-a prije inicijalizacije Plazme.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Način korištenja <a href="#id-1.1" id="id-1.1"></a>

Svojstva sustava se unose kao Java argumenti između `java` i `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` označava da taj argument nije ugrađen u JVM već je dodan Plazmi kao poseban argument,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정](#user-content-fn-3)[^3]됩니다.

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Sva svojstva sustava <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Ažurira oblikovanje znakova koje više nije podržano.

#### `debug.entities`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Omogućuje aktiviranje debug logova vezanih uz informacije o entitetima.

#### `debug.rewriteForIDE`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje NMS reviziju za ispravno učitavanje debug informacija u IDE-u i automatski remapira interne verzije.

#### `disable.watchdog`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje Watchdog upozorbeni sustav u Spigotu.

#### `letMeReload`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje potvrdu `/reload` naredbe.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Ako ste razvojni programer i trebate ažurirati dodatak, koristite hotswap umjesto `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje pluginove koji koriste standardni unos/izlaz.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Upozorava kada se otkrije zastarjelo oblikovanje u chat komponentama.

#### `Paper.bypassHostCheck`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje provjeru podudarnosti uzorka poslužitelja prilikom povezivanja igrača.

#### `Paper.debugDynamicMissingKeys`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Omogućuje debug logove za ključeve koji nedostaju u NBT objektima.

#### `Paper.debugInvalidSkullProfiles`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Omogućuje debug logove za nevaljane profile glava blokova.

Ovo logira sve nevaljane glave blokova u svijetu zajedno s njihovim položajem.

#### `Paper.disableChannelLimit`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje prioritetizaciju klasa pluginova.

Koristan je u slučaju problema s pluginovima u sjeni.

#### `Paper.disableFlushConsolidate`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje Netty sustav za spajanje podataka.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Zadano**: `750`

Ako entiteta ima više od postavljene vrijednosti, dijeli se u više paketa za prijenos.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Zadano**: `8192`

Postavlja maksimalnu veličinu paketa koje poslužitelj može primiti odjednom.

#### `Paper.ignoreJavaVersion`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje provjeru verzije Java-e.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

To može trajno oštetiti datoteke poput svijeta i uzrokovati potpuni kvar igre.

Svi problemi koji proizlaze iz toga isključivo su vaša odgovornost, a Plazma ne pruža nikakvu podršku za to.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Zadano**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Zadano**: `80`

Postavlja maksimalnu duljinu teksta na jednom redu ploče.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Zadano**: `(verzija svijeta) + 1`

Postavlja verziju inicijalizacije podataka koje treba predmemorirati.

Koristan je kad treba ažurirati veliki broj blokova, ali inače se rijetko koristi.

#### `Paper.parseYamlCommentsByDefault`

- **Vrsta**: `Boolean`
- **Zadano**: `True`

Omogućuje obradu komentara u YAML datotekama.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Zadano**: `30`

Igrač će biti izbačen ako ne primi nikakve podatke od igrača u određenom vremenskom razdoblju (u sekundama).

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Ignorira komentare u postavkama poslužitelja.

#### `Paper.debug-sync-loads`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Omogućuje debug logove za sinkronizirano stvaranje dijelova.

#### `Paper.enable-sync-chunk-writes`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Omogućuje Minecraftov [zadani sustav stvaranja dijelova](#user-content-fn-10)[^10].

Ovo uzrokuje da se svaki dio pohranjuje redoslijedom, što dovodi do značajnog smanjenja performansi.

#### `Paper.explicit-flush`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Omogućuje eksplicitno ispiranje mrežnih kanala.

#### `Paper.strict-thread-checks`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Uvijek zapisuje pogreške koje nisu nastale na glavnom dretvu.

#### `Paper.tickList-warn-on-excessive-delay`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Upozorava ako rezervirani zadaci imaju preveliko kašnjenje.

#### `Paperclip.patchOnly`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Ako koristite zadani izvršni datoteku, primjenjuje se samo zakrpa, a poslužitelj se ne pokreće.

#### `Plazma.aggressiveOptimize`

- **Vrsta**: `Boolean`
- **Zadano**: `false`
- **Sukob**: `Plazma.disableConfigOptimization`

Pojačava pocetnu konfiguraciju.

Aktivacija će ubrzati i učiniti server sigurnijim, ali može imati veliki utjecaj na igru.

#### `Plazma.disableConfigOptimization`

- **Vrsta**: `Boolean`
- **Zadano**: `false`
- **Sukob**: `Plazma.aggressiveOptimize`

Neće optimizirati pocetnu konfiguraciju.

Ovo koristi osnovnu konfiguraciju Paper-a.

#### `Plazma.iKnowWhatIAmDoing`

- **Vrsta**: `Boolean`
- **Zadano**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Vrsta**: `Boolean`
- **Zadano**: `false`

Isključuje Plazmin brendiranje i koristi vanilski osnovni favicon servera.

#### `Plazma.useVanillaConfiguration`

- **Vrsta**: `Boolean`
- **Zadano**: `false`
- **Sukob**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

To može značajno utjecati na sigurnost i performanse servera.

Sve probleme uzrokovane ovom osobinom rješava server administrator.
{% endhint %}

Postavlja pocetnu konfiguraciju na zadane vrijednosti koje pruža Mojang.

To isključuje sve patch-e za ranjivosti koje primjenjuje Paper.

Patch-ovi za ranjivosti se mogu ponovno aktivirati u postavkama Paper-a ili Plazme.

#### `Plazma.vanillaize`

- **Vrsta**: `Boolean`
- **Default**: `true`
- **Sukob**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Postavlja pocetnu konfiguraciju bliže vanili.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### 사용 중단된 svojstvo <a href="#id-1.3" id="id-1.3"></a>

Ispod sustav svojstvo su onemogućeni svojstvo.

#### `timings.bypassMax`

- **Vrsta**: `Boolean`
- **Zadano**: `false`
- **ZASTARJELO**: Nakon uklanjanja Timingsa iz Plazme

Odlučuje može li se premašiti maksimalna vrijednost koja se može poslati Aikarovom Timings API-ju.

Čak i ako se to dogodi, primjenjuje se ograničenje brzine ako se iznimka ne obradi u API-ju.

***

## Početni argument <a href="#id-2" id="id-2"></a>

Početni argument se unosi nakon `-jar *.jar` kako bi se Plazma inicijalizirala i obrađivala zajedno s njim.

### Upute za korištenje <a href="#id-2.1" id="id-2.1"></a>

Svojstva sustava unose se kao programski argument iza `-jar *.jar`.

Na primjer, ako želite primijeniti početni argument `nogui`,\
unosom kako slijedi, Plazma će tijekom inicijalizacije obraditi argument `nogui`.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Cjelokupni početni argument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Nadimak**: `b`
- **Zadana vrijednost**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Nadimak**: `c`
- **Zadana vrijednost**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Nadimak**: `c`
- **Zadana vrijednost**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Pokreće server u demo svijetu.

#### `eraseCache`

Briše preostale keš datoteke nakon nadogradnje svijeta.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Nadimak**: `?`

Ispisuje sve početne argumente i opise Plazme.

#### `initSettings`

Samo stvara konfiguracijsku datoteku i gasi server.

#### `jfrProfile`

Omogućuje JFR profiliranje.

#### `max-players`

- **Nadimak**: `s`, `size`
- **Zadana vrijednost**: `(svojstvo servera)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Onemogućuje grafički sučelje Plazme.

#### `nojline`

Onemogućuje JLine i koristi običnu konzolu.

#### `online-mode`

- **Nadimak**: `o`
- **Zadana vrijednost**: `(svojstvo servera)`

Odabire hoće li se igrači provjeravati preko Mojangovih autentikacijskih poslužitelja.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Nadimak**: `paper`
- **Zadana vrijednost**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Postavlja lokaciju [PaperSpigot konfiguracijske datoteke](../reference/configurations/paper/README.md) koja je ukinuta.

Ovo se koristi za prebacivanje postojeće konfiguracije u novu datoteku i više se ne koristi nakon toga.

#### `paper-settings-directory`

- **Nadimak**: `paper-dir`
- **Zadana vrijednost**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Nadimak**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Nadimak**: `p`
- **Zadana vrijednost**: `plugins`

Postavlja lokaciju mape dodatka.

#### `pufferfish-settings`

- **Nadimak**: `pufferfish`
- **Zadana vrijednost**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Nadimak**: `purpur`
- **Zadana vrijednost**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Pokreće server u potpunoj vanilla stanju.

#### `server-ip`

- **Nadimak**: `h`, `host`
- **Zadana vrijednost**: `(svojstvo servera)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Nadimak**: `p`, `port`
- **Zadana vrijednost**: `(svojstvo servera)`

Postavlja port servera.

#### `server-name`

- **Zadana vrijednost**: `A Plazma Server`

Postavlja ime servera.

#### `spigot-settings`

- **Nadimak**: `S`
- **Zadana vrijednost**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Nadimak**: `v`

Ispisuje verziju Plazme.

#### `world-dir`

- **Nadimak**: `W`, `universe`, `world-container`
- **Zadana vrijednost**: `(mapa servera)`

Postavlja lokaciju gdje se sprema datoteka svijeta.

#### `world-name`

- **Nadimak**: `w`, `world`
- **Zadana vrijednost**: `(svojstvo servera)`

Postavlja ime datoteke svijeta.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Mjesto na kojem se argumenti obrađuju ovisi o dodatku na kraju.

[^3]: Na primjer, ako želite postaviti `Plazma.iKnowWhatIAmDoing` na `true`, umjesto `-DPlazma.iKnowWhatIAmDoing=true`, dovoljno je unijeti `-DPlazma.iKnowWhatIAmDoing`.

[^4]: Na primjer, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detektor događaja.

[^6]: Detektor događaja.

[^7]: Klijent.

[^8]: Signal koji signalizira da je server uspješno povezan poput otkucaja srca.

[^9]: Korištenjem Purpur AFK izbacivanja, možete izbaciti igrače koji su odsutni.

[^10]: Sustav pisanja sinkroniziranog chunka, Sync Chunk Write System.

[^11]: `UPOZORENJE! Plazma može uzrokovati neočekivane probleme, stoga budite sigurni da je temeljito testirate prije nego je koristite na javnom poslužitelju.`

[^12]: U igri `svjetska optimizacija` također radi prema tom principu.

[^13]: `Administratori razina 2` ili više su isključeni.

[^14]: Internet protokol, IP.
