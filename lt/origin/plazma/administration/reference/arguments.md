---
description: Sužinokite apie pradinį argumentą ir sistemos savybes.
---

# 🎛️ Argumentas ir savybės

Pradžios argumentai ir sistemos savybės yra reikšmės, pridedamos prie Plazma vykdymo [naudojamų komandų](#user-content-fn-1)[^1], kurios turi įtakos Plazmos veikimui iš esmės.

\[Pagal **pradinius parametrus** ir **sistemos savybes** bus suskirstyta pagal [komandos papildymo vietą](#user-content-fn-2)[^2].

***

## Sistemos savybės <a href="#id-1" id="id-1"></a>

Sistemos savybės yra reikšmės, įvestos prieš Plazmos inicijavimą prieš JVM, kuris jas apdoroja.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Naudojimo instrukcija <a href="#id-1.1" id="id-1.1"></a>

Sistemos savybės įvedamos kaip Java komandos argumentas tarp `java` ir `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` nurodo, kad ši reikšmė yra specialus argumentas, pridėtas prie Plazmos, o

Jei į savybes neįvedate jokios vertės, vertė bus nustatyta kaip [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Visos sistemos savybės <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Atnaujina naudojamus išjungtus ženklus.

#### `debug.entities`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Įjungia susijusią entiteto informacijos derinį.

#### `debug.rewriteForIDE`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

IDE teisingai įkelia derinimo informaciją, išjungia NMS reviziją ir automatiškai pertvarko vidinę versijos informaciją.

#### `disable.watchdog`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia Spigot stebėjimo šuns sistemos įspėjimus.

#### `letMeReload`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia patvirtinimo pranešimą dėl `reload` komandos.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Jeigu esate įskiepių kūrėjas ir turite atnaujinti įskiepius, naudokite šilumą vietoj `reload` komandos.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia įprastos įvesties-išvesties sistemos įskiepius.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Įspėja, kai aptinkamas pasenusi formatavimo sistema pokalbių komponente.

#### `Paper.bypassHostCheck`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia serverio šablono patikros patikrinimą, kai žaidėjas prisijungia prie serverio.

#### `Paper.debugDynamicMissingKeys`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Įjungia derinimo įrašus, susijusius su praleistomis NBT raktažodžių dalimis.

#### `Paper.debugInvalidSkullProfiles`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Įjungia derinimo įrašus, susijusius su netinkamais kaukių profiliais.

Tai įrašo visus neteisingus kaukių blokus žemėlapyje kartu su jų vietomis.

#### `Paper.disableChannelLimit`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia įskiepių klasės prioritizavimo sistemą.

Tai naudinga, jei yra problemų su įskiepių šešėliu.

#### `Paper.disableFlushConsolidate`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia Netty nusistovėjusią plūduriavimo konsolidavimo sistemą.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Numatytasis**: `750`

Jei entitetas yra didesnis nei nustatyta vertė, jis siunčiamas skaidruose paketuose.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Numatytasis**: `8192`

Nustato didžiausią paketo dydį, kurį serveris gali priimti vienu metu.

#### `Paper.ignoreJavaVersion`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia Java versijos patikrinimą.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Tai gali pakenkti failams ir visam žaidimo mechanizmui, nes jie gali būti negrįžtamai sugadinti.

Visos su tuo susijusios problemos yra jūsų atsakomybė, o Plamza nepateiks jokios pagalbos šiuo atveju.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Numatytasis**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Numatytasis**: `80`

Nustato didžiausią simbolių skaičių, kurį galima įvesti į vieną piktogramą.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Numatytasis**: `(pasaulio versija) + 1`

Nustato pradinės pasaulio atnaujinimo informacijos versiją.

Tai naudinga tik tais atvejais, kai reikia atnaujinti didžiulius kiekvieno ruožo duomenis, tačiau kitais atvejais nebenaudojama.

#### `Paper.parseYamlCommentsByDefault`

- **Formatas**: `Logiškas`
- **Numatytasis**: `True`

Įjungia YAML failų komentarų apdorojimą.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Numatytasis**: `30`

Jei žaidėjas neperduoda jokių duomenų per nustatytą laiką (sekundėmis), jis bus išmestas iš žaidimo.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Ignoruoja serverio savybių komentarus.

#### `Paper.debug-sync-loads`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Įjungia sinchronizuotų ruožų kūrimo derinimo įrašus.

#### `Paper.enable-sync-chunk-writes`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Įjungia Minecraft [numatytą ruožų kūrimo sistemą](#user-content-fn-10)[^10].

Tai leidžia kiekvieną ruožą išsaugoti eilės tvarka, kuri labai sumažina našumą.

#### `Paper.explicit-flush`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Įjungia tinklo kanalo išsamią nusistovėjimą.

#### `Paper.strict-thread-checks`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Visada žurnališkai užfiksuoja klaidas, kurios neįvyko pagrindiniame gijime.

#### `Paper.tickList-warn-on-excessive-delay`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Jeigu užduotis turi per didelį laukimo laiką, išspausdina įspėjimą.

#### `Paperclip.patchOnly`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Kai naudojamas numatytas vykdomasis failas, tačiau nepradedamas serveris, tik taikomi pataisymai.

#### `Plazma.aggressiveOptimize`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`
- **Konfliktas**: `Plazma.disableConfigOptimization`

Stipriau optimizuoja pradinę konfigūraciją.

Įjungus šį nustatymą serveris tampa greitesnis ir saugesnis, tačiau gali turėti didelį poveikį žaidimo procesui.

#### `Plazma.disableConfigOptimization`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`
- **Konfliktas**: `Plazma.aggressiveOptimize`

Neoptimizuoja pradinės konfigūracijos.

Tai nustato paprastąjį Paper konfigūracijos variantą.

#### `Plazma.iKnowWhatIAmDoing`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`

Išjungia Plazma prekinį ženklą ir naudoja standartinį serverio favicon.

#### `Plazma.useVanillaConfiguration`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`
- **Konfliktas**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Tai gali labai paveikti serverio saugumą ir veikimą.

Visos problemas, kylančios naudojant šį parametrą, yra operatoriaus dėl serverio.
{% endhint %}

Nustato pradinę konfigūraciją pagal Mojang numatytuosius nustatymus.

Tai atšaukia visus ištaisytus pažeidžiamumus, kuriuos taiko Paper.

Ištaisymus galima vėl įjungti naudojant Paper arba Plazma konfigūracijas.

#### `Plazma.vanillaize`

- **Formatas**: `Logiškas`
- **Pagal nutylėjimą**: `true`
- **Konfliktas**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Nustato pradinę konfigūraciją artimą standartiniam variantui.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Nebenaudojamas atributas <a href="#id-1.3" id="id-1.3"></a>

Žemiau pateikti sistemos atributai yra nebenaudojami.

#### `timings.bypassMax`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`
- **Nebenaudojamas**: Timings buvo pašalintas iš Plazma nuo

Nusprendžia, ar galima viršyti maksimalų Timings API siunčiamų reikšmių skaičių.

Jei tai padarysite, tačiau API neapdoros išimčių, bus taikomas greičio apribojimas.

***

## Pradžios argumentas <a href="#id-2" id="id-2"></a>

Pradžios argumentas yra įvestas po `-jar *.jar` ir yra reikšmė, kuri bus apdorota kartu su Plazma inicializavimu.

### Naudojimo instrukcija <a href="#id-2.1" id="id-2.1"></a>

Sistemos savybės yra įvestos po `-jar *.jar` kaip programos komandiniai argumentai.

Pavyzdžiui, norint pritaikyti pradžios argumentą `nogui`,\
įvedus taip, Plazma inicializuojant bus apdorotas argumentas `nogui`.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Visas pradžios argumentas <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Pseudonimas**: `b`
- **Numatytoji reikšmė**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Pseudonimas**: `c`
- **Numatytoji reikšmė**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Pseudonimas**: `c`
- **Numatytoji reikšmė**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Paleidžia serverį su demonstraciniu pasauliu.

#### `eraseCache`

Ištrina likusius talpyklos failus po pasaulio atnaujinimo.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Pseudonimas**: `?`

Atspausdina Plazmos visus pradžios argumentus ir aprašymą.

#### `initSettings`

Sukuria tik konfigūracijos failą ir išjungia serverį.

#### `jfrProfile`

Įjungia JFR profilį.

#### `max-players`

- **Pseudonimas**: `s`, `size`
- **Numatytoji reikšmė**: `(serverio savybė)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Išjungia grafinį sąsajos skydelį.

#### `nojline`

Išjungia JLine ir naudoja standartinę konsolę.

#### `online-mode`

- **Pseudonimas**: `o`
- **Numatytoji reikšmė**: `(serverio savybė)`

Pasirenka, ar patikrinti žaidėją su Mojang autentifikavimo serveriu.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Pseudonimas**: `paper`
- **Numatytoji reikšmė**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Nustato naudoto PaperSpigot konfigūracijos failo vietą.

Tai naudojama perkelti seną konfigūraciją į naują failą, po to ji nebeveikia.

#### `paper-settings-directory`

- **Pseudonimas**: `paper-dir`
- **Numatytoji reikšmė**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Pseudonimas**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Pseudonimas**: `p`
- **Numatytoji reikšmė**: `plugins`

Nustato papildomų įskiepių aplankalo vietą.

#### `pufferfish-settings`

- **Pseudonimas**: `pufferfish`
- **Numatytoji reikšmė**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Pseudonimas**: `purpur`
- **Numatytoji reikšmė**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Paleidžia serverį saugiuoju režimu, kaip visiškai standartinį.

#### `server-ip`

- **Pseudonimas**: `h`, `host`
- **Numatytoji reikšmė**: `(serverio savybė)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Pseudonimas**: `p`, `port`
- **Numatytoji reikšmė**: `(serverio savybė)`

Nustato serverio prievadą.

#### `server-name`

- **Numatytoji reikšmė**: `A Plazma Server`

Nustato serverio pavadinimą.

#### `spigot-settings`

- **Pseudonimas**: `S`
- **Numatytoji reikšmė**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Pseudonimas**: `v`

Atspausdina Plazma versiją.

#### `world-dir`

- **Pseudonimas**: `W`, `universe`, `world-container`
- **Numatytoji reikšmė**: `(serverio aplankas)`

Nustato vietą, kur saugomi pasaulio failai.

#### `world-name`

- **Pseudonimas**: `w`, `world`
- **Numatytoji reikšmė**: `(serverio savybė)`

Nustato pasaulio failo pavadinimą.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Parametrų tvarka priklauso nuo vietos, kurioje yra pridėti argumentai.

[^3]: Pavyzdžiui, norint nustatyti `Plazma.iKnowWhatIAmDoing` į `true`, vietoje `-DPlazma.iKnowWhatIAmDoing=true` galima įvesti tik `-DPlazma.iKnowWhatIAmDoing` ir taip pat veiks.

[^4]: Pavyzdžiui, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Įvykio jutiklis.

[^6]: Įvykio jutiklis.

[^7]: Klientas.

[^8]: Signalas, pranešantis, kad serveris yra sėkmingai prijungtas kaip širdies plakimas.

[^9]: Naudodami Purpur AFK išmesti funkciją, galite išmesti net tuos žaidėjus, kurie paliko vietą.

[^10]: Sinchroninis ruožo rašymo sistema, Sync Chunk Write System.

[^11]: `ĮSPĖJIMAS! Plazma gali sukelti netikėtų problemų, todėl būtinai išsamiai išbandykite jį prieš naudojant jį viešame serveryje.`

[^12]: Žaidimuose `pasaulio optimizavimas` taip pat veikia pagal šį principą.

[^13]: `Lygio 2` arba aukštesnis administratorius yra išskiriamas.

[^14]: Interneto protokolas, IP.
