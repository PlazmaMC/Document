---
description: Saznajte o početnim argumentima i svojstvima sustava.
---

# 🎛️ Argumenti i svojstva

Početni argumenti i svojstva sustava su vrijednosti dodane naredbi koja se koristi za izvođenje Plazme, koje omogućuju promjenu vrijednosti koje se ne mogu promijeniti nakon što se Plazma pokrene.

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]에 따라 **시작 인수**와 **시스템 속성**으로 나뉘게 됩니다.

***

## Svojstva sustava <a href="#id-1" id="id-1"></a>

Svojstva sustava su vrijednosti koje se unose ispred `-jar` i obrađuju se od strane JVM-a prije inicijalizacije Plazme.

{% hint style="warning" %}

**Ako promijenite svojstva sustava, to može promijeniti način rada Plazme i JVM-a te može imati veliki utjecaj na igru!**

Ako niste sigurni kakvu ulogu ima svako svojstvo sustava, **nemojte ih nikada koristiti!**

{% endhint %}

### Način korištenja <a href="#id-1.1" id="id-1.1"></a>

Svojstva sustava se unose kao Java argumenti između `java` i `-jar`.

Na primjer, ako želite primijeniti svojstvo sustava `Plazma.dummyProperty`,
unosom sljedećeg, sljedeće svojstvo će biti postavljeno na `37` pri inicijalizaciji Plazme.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` označava da taj argument nije ugrađen u JVM već je dodan Plazmi kao poseban argument,

속성에 아무런 값도 입력하지 않으면 값이 [`true`로 고정](#user-content-fn-3)[^3]됩니다.

{% hint style="info" %}

**Platforma Paperweight obitelji servera koristi `.` u nazivima svojstava kako bi razlikovala svojstva za svaku platformu.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 [추가해야](#user-content-fn-4)[^4] 합니다.

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

**`/reload` naredba je vrlo nestabilna, stoga svi problemi koji se pojave nakon korištenja `/reload` su odgovornost korisnika.**

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

플레이어당 적용되는 128개의 플러그인 [채널](#user-content-fn-5)[^5]의 개수 제한을 비활성화 합니다.

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

- **Vrsta**: `Integer`
- **Zadano**: `750`

Ako entiteta ima više od postavljene vrijednosti, dijeli se u više paketa za prijenos.

#### `Paper.filterThreshold`

- **Vrsta**: `Integer`
- **Zadano**: `8192`

Postavlja maksimalnu veličinu paketa koje poslužitelj može primiti odjednom.

#### `Paper.ignoreJavaVersion`

- **Vrsta**: `Boolean`
- **Zadano**: `False`

Onemogućuje provjeru verzije Java-e.

{% hint style="danger" %}

**Na ovaj način možete pokušati pristupiti kodu koji ne postoji u JVM-u!**

To može trajno oštetiti datoteke poput svijeta i uzrokovati potpuni kvar igre.

Svi problemi koji proizlaze iz toga isključivo su vaša odgovornost, a Plazma ne pruža nikakvu podršku za to.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Vrsta**: `Integer`
- **Zadano**: `64`

플러그인 [채널](#user-content-fn-5)[^5] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Vrsta**: `Integer`
- **Zadano**: `80`

Postavlja maksimalnu duljinu teksta na jednom redu ploče.

#### `Paper.minPrecachedDatafixVersion`

- **Vrsta**: `Integer`
- **Zadano**: `(verzija svijeta) + 1`

Postavlja verziju inicijalizacije podataka koje treba predmemorirati.

Koristan je kad treba ažurirati veliki broj blokova, ali inače se rijetko koristi.

#### `Paper.parseYamlCommentsByDefault`

- **Vrsta**: `Boolean`
- **Zadano**: `True`

Omogućuje obradu komentara u YAML datotekama.

#### `Paper.playerConnection.keepAlive`

- **Vrsta**: `Integer`
- **Zadano**: `30`

Igrač će biti izbačen ako ne primi nikakve podatke od igrača u određenom vremenskom razdoblju (u sekundama).

일반적인 경우, [게임](#user-content-fn-7)[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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

{% hint style="warning" %}

**Ovo svojstvo će se premjestiti kao početni argument nakon verzije 1.20.5.**

{% endhint %}

Primjenjuje strože optimizacije konfiguracije koje se primjenjuju pri prvom pokretanju.

Aktivacijom će poslužitelj postati brži i sigurniji, ali može blokirati neke mehanizme ili imati veliki utjecaj na igranje igara.

#### `Plazma.iKnowWhatIAmDoing`

- **Vrsta**: `Boolean`
- **Zadano**: `false`

Plazma가 초기화될 때 출력되는 [경고문](#user-content-fn-11)[^11]을 억제합니다.

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

Postavlja ime i lokaciju [Bukkit konfiguracijske datoteke](../reference/configurations/bukkit.md).

#### `command-settings`

- **Nadimak**: `c`
- **Zadana vrijednost**: `commands.yml`

Postavlja ime i lokaciju [Bukkit konfiguracijske datoteke naredbi](../reference/configurations/bukkit.md).

#### `config`

- **Nadimak**: `c`
- **Zadana vrijednost**: `server.properties`

Postavlja ime i lokaciju [datoteke svojstava servera](../reference/configurations/property.md).

#### `demo`

Pokreće server u demo svijetu.

#### `eraseCache`

Briše preostale keš datoteke nakon nadogradnje svijeta.

#### `forceUpgrade`

Nasilno [nadograđuje](#user-content-fn-12)[^12] svijet bez obzira na verziju.

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

Postavlja maksimalni broj [igrača](#user-content-fn-14)[^14] koji su dopušteni.

#### `nogui`

Onemogućuje grafički sučelje Plazme.

#### `nojline`

Onemogućuje JLine i koristi običnu konzolu.

#### `online-mode`

- **Nadimak**: `o`
- **Zadana vrijednost**: `(svojstvo servera)`

Odabire hoće li se igrači provjeravati preko Mojangovih autentikacijskih poslužitelja.

**U slučaju da se ne koristi Velocity ili drugi posrednici, može doći do kršenja [EULA](../getting-started/README.md#id-5).**

#### `paper-settings`

- **Nadimak**: `paper`
- **Zadana vrijednost**: `paper.yml`

{% hint style="warning" %}

**Ovaj argument je prestao biti podržan nakon verzije 1.19.4**

{% endhint %}

Postavlja lokaciju [PaperSpigot konfiguracijske datoteke](../reference/configurations/paper/README.md) koja je ukinuta.

Ovo se koristi za prebacivanje postojeće konfiguracije u novu datoteku i više se ne koristi nakon toga.

#### `paper-settings-directory`

- **Nadimak**: `paper-dir`
- **Zadana vrijednost**: `config`

Postavlja ime i lokaciju mape u kojoj se nalazi [Paper konfiguracijska datoteka](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Nadimak**: `plazma-dir`

Postavlja ime i lokaciju mape u kojoj se nalazi [Plazma konfiguracijska datoteka](../reference/configurations/plazma/README.md).

#### `plugins`

- **Nadimak**: `p`
- **Zadana vrijednost**: `plugins`

Postavlja lokaciju mape dodatka.

#### `pufferfish-settings`

- **Nadimak**: `pufferfish`
- **Zadana vrijednost**: `pufferfish.yml`

Postavlja ime i lokaciju [Pufferfish konfiguracijske datoteke](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Nadimak**: `purpur`
- **Zadana vrijednost**: `purpur.yml`

Postavlja ime i lokaciju [Purpur konfiguracijske datoteke](../reference/configurations/purpur/README.md).

#### `safeMode`

Pokreće server u potpunoj vanilla stanju.

#### `server-ip`

- **Nadimak**: `h`, `host`
- **Zadana vrijednost**: `(svojstvo servera)`

Postavlja ime hosta servera ili [IP adresu](#user-content-fn-13)[^13].

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

Postavlja ime i lokaciju [Spigot konfiguracijske datoteke](../reference/configurations/spigot.md).

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

[^13]: Internet protokol, IP.

[^14]: `Administratori razina 2` ili više su isključeni.
