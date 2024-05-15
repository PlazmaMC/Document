---
description: Sužinokite apie pradinį argumentą ir sistemos savybes.
---

# 🎛️ Argumentas ir savybės

Pradžios argumentai ir sistemos savybės yra reikšmės, pridedamos prie Plazma vykdymo [naudojamų komandų](#user-content-fn-1)[^1], kurios turi įtakos Plazmos veikimui iš esmės.

\[Pagal **pradinius parametrus** ir **sistemos savybes** bus suskirstyta pagal [komandos papildymo vietą](#user-content-fn-2)[^2].

***

## Sistemos savybės <a href="#id-1" id="id-1"></a>

Sistemos savybės yra reikšmės, įvestos prieš Plazmos inicijavimą prieš JVM, kuris jas apdoroja.

{% hint style="įspėjimas" %}

**Keičiant sistemos savybes, Plazmos ir JVM veikimas gali pasikeisti, tai gali labai paveikti žaidimą!**

Jei nežinote, kokia yra kiekvienos sistemos savybės funkcija, **nenaudokite jos!**

{% endhint %}

### Naudojimo instrukcija <a href="#id-1.1" id="id-1.1"></a>

Sistemos savybės įvedamos kaip Java komandos argumentas tarp `java` ir `-jar`.

Pavyzdžiui, norint pritaikyti `Plazma.dummyProperty` sistemos savybę, įvesdami šį kodą, įvykdžius šią savybę įvedama `37`, o Plazma inicijuojama.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` nurodo, kad ši reikšmė yra specialus argumentas, pridėtas prie Plazmos, o

Jei į savybes neįvedate jokios vertės, vertė bus nustatyta kaip [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Paperweight serijos serverių platforma, norėdama atskirti kiekvienos platformos sistemos savybes, į savybės pavadinimą įtraukia `.`**

Kai kuriose terminalo programose, pvz., Windows PowerShell, šie parametrai gali būti neleidžiami, todėl parametrų galuose reikia pridėti `"` [prieš](#user-content-fn-4)[^4].

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

**`/reload` komanda yra labai nestabili, todėl visi serverio po `/reload` naudojimo atsiradę problemos yra naudotojo atsakomybėje.**

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

Išjungia 128 įskaitomųjų įskiepių [kanalų](#user-content-fn-5)[^5] skaičiaus apribojimą vienam žaidėjui.

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

- **Formatas**: `Sveikas skaičius`
- **Numatytasis**: `750`

Jei entitetas yra didesnis nei nustatyta vertė, jis siunčiamas skaidruose paketuose.

#### `Paper.filterThreshold`

- **Formatas**: `Sveikas skaičius`
- **Numatytasis**: `8192`

Nustato didžiausią paketo dydį, kurį serveris gali priimti vienu metu.

#### `Paper.ignoreJavaVersion`

- **Formatas**: `Logiškas`
- **Numatytasis**: `Neteisinga`

Išjungia Java versijos patikrinimą.

{% hint style="danger" %}

**Taip galite pabandyti pasiekti JVM neegzistuojantį kodą!**

Tai gali pakenkti failams ir visam žaidimo mechanizmui, nes jie gali būti negrįžtamai sugadinti.

Visos su tuo susijusios problemos yra jūsų atsakomybė, o Plamza nepateiks jokios pagalbos šiuo atveju.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Formatas**: `Sveikas skaičius`
- **Numatytasis**: `64`

Nustato ribą plugin kanalo pavadinimui.

#### `Paper.maxSignLength`

- **Formatas**: `Sveikas skaičius`
- **Numatytasis**: `80`

Nustato didžiausią simbolių skaičių, kurį galima įvesti į vieną piktogramą.

#### `Paper.minPrecachedDatafixVersion`

- **Formatas**: `Sveikas skaičius`
- **Numatytasis**: `(pasaulio versija) + 1`

Nustato pradinės pasaulio atnaujinimo informacijos versiją.

Tai naudinga tik tais atvejais, kai reikia atnaujinti didžiulius kiekvieno ruožo duomenis, tačiau kitais atvejais nebenaudojama.

#### `Paper.parseYamlCommentsByDefault`

- **Formatas**: `Logiškas`
- **Numatytasis**: `True`

Įjungia YAML failų komentarų apdorojimą.

#### `Paper.playerConnection.keepAlive`

- **Formatas**: `Sveikas skaičius`
- **Numatytasis**: `30`

Jei žaidėjas neperduoda jokių duomenų per nustatytą laiką (sekundėmis), jis bus išmestas iš žaidimo.

Įprastai, [žaidimas](#user-content-fn-7)[^7] nuolat siunčia [širdies plakimo signalus](#user-content-fn-8)[^8] į serverį, todėl, jei žaidimas neatsako, jis laikomas susidūrusiu ir toliau nebeapdoroja žaidėjų serverio pusėje, bet juos išmeta.

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
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`

Slopina pranešimą, kuris rodomas, kai Plazma inicijuojama [įspėjimas](#user-content-fn-11)[^11].

#### `Plazma.useVanillaFavicon`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Formatas**: `Logiškas`
- **Numatytasis**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

{% hint style="danger" %}

**해당 속성은 패치된 모든 취약점을 되돌립니다!**

이는 서버 안전 및 성능에 크게 영향을 줄 수 있습니다.

해당 속성을 사용하여 발생하는 모든 문제는 서버 관리자에게 있습니다.

{% endhint %}

초기 구성을 Mojang에서 제공하는 기본값으로 제공합니다.

이는 Paper에서 적용한 모든 취약점 패치를 비활성화 합니다.

취약점 패치는 Paper 구성 또는 Plazma 구성에서 다시 활성화 할 수 있습니다.

#### `Plazma.vanillaize`

- **Formatas**: `Logiškas`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

Nurodo [Bukkit konfigūracijos failo](../reference/configurations/bukkit.md) pavadinimą ir vietą.

#### `command-settings`

- **Pseudonimas**: `c`
- **Numatytoji reikšmė**: `commands.yml`

Nurodo [Bukkit komandų konfigūracijos failo](../reference/configurations/bukkit.md) pavadinimą ir vietą.

#### `config`

- **Pseudonimas**: `c`
- **Numatytoji reikšmė**: `server.properties`

Nurodo [serverio savybių](../reference/configurations/property.md) failo pavadinimą ir vietą.

#### `demo`

Paleidžia serverį su demonstraciniu pasauliu.

#### `eraseCache`

Ištrina likusius talpyklos failus po pasaulio atnaujinimo.

#### `forceUpgrade`

Nesvarbu kokios versijos, priverčia pasaulį [atnaujinti](#user-content-fn-12)[^12].

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

Nustato maksimalų leidžiamą [žaidėjų](#user-content-fn-14)[^14] skaičių.

#### `nogui`

Išjungia grafinį sąsajos skydelį.

#### `nojline`

Išjungia JLine ir naudoja standartinę konsolę.

#### `online-mode`

- **Pseudonimas**: `o`
- **Numatytoji reikšmė**: `(serverio savybė)`

Pasirenka, ar patikrinti žaidėją su Mojang autentifikavimo serveriu.

**Naudoti [EULA](../getting-started/README.md#id-5) pažeidimas, jei naudojamas ne Velocity ar kitas įgaliojimų serveris.**

#### `paper-settings`

- **Pseudonimas**: `paper`
- **Numatytoji reikšmė**: `paper.yml`

{% hint style="įspėjimas" %}

**Šis argumentas buvo nutrauktas nuo 1.19.4 versijos**

{% endhint %}

Nustato naudoto PaperSpigot konfigūracijos failo vietą.

Tai naudojama perkelti seną konfigūraciją į naują failą, po to ji nebeveikia.

#### `paper-settings-directory`

- **Pseudonimas**: `paper-dir`
- **Numatytoji reikšmė**: `config`

Nustato [Paper konfigūracijos failo](../reference/configurations/paper/README.md) aplankalo pavadinimą ir vietą.

#### `plazma-settings-directory`

- **Pseudonimas**: `plazma-dir`

Nustato [Plazma konfigūracijos failo](../reference/configurations/plazma/README.md) aplankalo pavadinimą ir vietą.

#### `plugins`

- **Pseudonimas**: `p`
- **Numatytoji reikšmė**: `plugins`

Nustato papildomų įskiepių aplankalo vietą.

#### `pufferfish-settings`

- **Pseudonimas**: `pufferfish`
- **Numatytoji reikšmė**: `pufferfish.yml`

Nustato [Pufferfish konfigūracijos failo](../reference/configurations/pufferfish.md) pavadinimą ir vietą.

#### `purpur-settings`

- **Pseudonimas**: `purpur`
- **Numatytoji reikšmė**: `purpur.yml`

Nustato [Purpur konfigūracijos failo](../reference/configurations/purpur/README.md) pavadinimą ir vietą.

#### `safeMode`

Paleidžia serverį saugiuoju režimu, kaip visiškai standartinį.

#### `server-ip`

- **Pseudonimas**: `h`, `host`
- **Numatytoji reikšmė**: `(serverio savybė)`

Nustato serverio prievado pavadinimą arba [internetinio protokolo](#user-content-fn-13)[^13] adresą.

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

Nurodo [Spigot konfigūracijos failo](../reference/configurations/spigot.md) pavadinimą ir vietą.

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

[^13]: Interneto protokolas, IP.

[^14]: `Lygio 2` arba aukštesnis administratorius yra išskiriamas.
