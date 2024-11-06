---
description: Mësoni për argumentet fillestare dhe përkatësitë e sistemit.
---

# 🎛️ Argumentet dhe përkatësitë

Fillimi i blerjes dhe atributet e sistemit janë vlera shtesë për ekzekutimin e Plazma-s [komandave të përdorura](#user-content-fn-1)[^1], që kanë një ndikim të gjerë në funksionimin e Plazma-s.

[Pozicioni i shtimit të komandës](#user-content-fn-2)[^2] ndahet në **argumentin fillestar** dhe **tiparet e sistemit** sipas pozicionit të shtimit të komandës.

***

## Përkatësitë e sistemit <a href="#id-1" id="id-1"></a>

Përkatësitë e sistemit vendosen para `-jar` përpara se Plazma të inicializohet në JVM.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Mënyra e përdorimit <a href="#id-1.1" id="id-1.1"></a>

Përkatësitë e sistemit vendosen si argumente Java midis `java` dhe `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` tregon se ky argument nuk është i brendshëm në JVM, por është argument i shtuar ekskluzivisht për Plazma-n.

Nëse nuk jepni asnjë vlerë për tipare, vlera do të mbetet [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Përkatësitë e tërësisë së sistemit <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Përditëson formatin e shenjave të ndaluar për përdorim.

#### `debug.entities`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Aktivizon regjistrimet e debugimit të informacioneve të entitetit.

#### `debug.rewriteForIDE`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon revisionin NMS për IDE për të marrë informacionin e brendshëm në mënyrë korrekte dhe për të rimapeuar automatikisht informacionin e versionit të brendshëm.

#### `disable.watchdog`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon sistemin e sinjalizimit të Watchdog të Spigot-it.

#### `letMeReload`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon mesazhin e rikonfirmimit të komandës `/reload`.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Nëse jeni zhvillues shtojcësh dhe duhet të përditësoni shtojcën, përdorni hotswap në vend të `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon shtojcët që përdorin sistemin standard të hyrjeve-daljeve.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Njofton kur zbulohet formatimi i vjetruar në komponentët e bisedës.

#### `Paper.bypassHostCheck`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon verifikimin e përputhshmërisë së modelit të serverit kur një lojtar lidhet me serverin.

#### `Paper.debugDynamicMissingKeys`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Aktivizon regjistrimet e debugimit për çelësat që mungojnë në objektet NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Aktivizon regjistrimet e debugimit për profilet e kokrave të pavlefshme.

Ky veprim regjistron të gjitha kokrat e pavlefshme në botë me pozicionin e tyre.

#### `Paper.disableChannelLimit`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon sistemin e prioritetit të klasave shtojcës.

Është e dobishme në rast se ka probleme me shënjuesit e klasave shtojcës.

#### `Paper.disableFlushConsolidate`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon sistemin e konsolidimit të shkarkimit të Netty.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Vlera parazgjedhëse**: `750`

Nëse entiteti është më i madh se vlera e caktuar, ndahet në pako të ndryshme për transmetim.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Vlera parazgjedhëse**: `8192`

Cakton madhësinë maksimale të pako të pranueshme nga serveri.

#### `Paper.ignoreJavaVersion`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon verifikimin e versionit të Java-së.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Kjo mund të shkaktojë dëmtim të përhershëm të skedarëve të botës dhe shkatërrimin e mekanikës së lojës.

Çdo problem që shkaktohet nga kjo është përgjegjësia e përdoruesit dhe Plamza nuk ofron asnjë mbështetje për këtë.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Vlera parazgjedhëse**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Vlera parazgjedhëse**: `80`

Cakton gjatësinë maksimale të shenjave në një rresht.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Vlera parazgjedhëse**: `(versioni i botës) + 1`

Cakton versionin e informacionit të përditësimit fillestar për botën që do të inicializohet së pari.

Është e dobishme kur ka nevojë për të azhurnuar një numër të madh të blloqeve, por nuk përdoret në raste të tjera.

#### `Paper.parseYamlCommentsByDefault`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `True`

Aktivizon trajtimin e komenteve YAML-së.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Vlera parazgjedhëse**: `30`

Kur nuk pranohet asnjë të dhënë nga një lojtar për një periudhë të caktuar (sekonda), lojtari do të dërgohet larg.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Ignoron komentet e pronave të serverit.

#### `Paper.debug-sync-loads`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Aktivizon regjistrimet e debugimit të ngarkesave sinkrone të blloqeve.

#### `Paper.enable-sync-chunk-writes`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Aktivizon sistemin e shkrimit të blloqeve të sinkronizuara të Minecraft-it.

Ky veprim shkruan secilin bllok në një rend të caktuar, duke shkaktuar një ulje të madhe të performancës.

#### `Paper.explicit-flush`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Aktivizon shprazjen e qartë të rrjetit të kanaleve.

#### `Paper.strict-thread-checks`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Regjistron gjithmonë gabimet që ndodhin jashtë thread-it kryesor.

#### `Paper.tickList-warn-on-excessive-delay`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Nëse një detyrë e rezervuar ka një vonesë të tepërt, shfaq një sinjalizim.

#### `Paperclip.patchOnly`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Kur përdoret ekzekutuesi i ofruar, aplikon vetëm ndryshime pa filluar serverin.

#### `Plazma.aggressiveOptimize`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`
- **konflikt**: `Plazma.disableConfigOptimization`

Optimizonin e konfigurimit fillimor në mënyrë më të fortë.

Aktivizimi bën serverin më të shpejtë dhe më të sigurt, por mund të ketë ndikim të madh në lojë.

#### `Plazma.disableConfigOptimization`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`
- **konflikt**: `Plazma.aggressiveOptimize`

Nuk optimizon konfigurimin fillestar.

Kjo e përdor konfigurimin bazë të Paper.

#### `Plazma.iDijaCfarePoBej`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`

Çaktivizon markën Plazma dhe përdor favicon bazë të serverit vanilë.

#### `Plazma.useVanillaConfiguration`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`
- **konflikt**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Kjo mund të ketë ndikim të madh në sigurinë dhe performancën e serverit.

Çdo problem që shkaktohet duke përdorur këtë atribut është në dore të administratorit të serverit.
{% endhint %}

Optimizon konfigurimin fillestar me vlerat bazë të ofruara nga Mojang.

Kjo çaktivizon të gjitha patch-et e realizuara në dobësitë nga Paper.

Patch-et e dobësive mund të aktivizohen përsëri në konfigurimin e Paper ose Plazma.

#### `Plazma.vanillaize`

- **Forma**: `Boolean`
- **Default**: `true`
- **konflikt**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Optimizon konfigurimin fillestar në një mënyrë të ngjashme me vanilën.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Atribute i ndaluar në përdorim <a href="#id-1.3" id="id-1.3"></a>

Atributet e sistemit nën janë të ndaluara për përdorim.

#### `timings.bypassMax`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`
- **Ndalur në përdorim**: Timings pas heqjes së plotë në Plazma

Vendos nëse mund të kalohet maksimumi i vlerave që mund të dërgohen në API-në e Timings së Aikarit.

Edhe nëse kjo ndodh, do të aplikohet një kufizim i shpejtësisë nëse nuk është trajtuar në mënyrë të veçantë nga API-ja.

***

## Argumenti fillimor <a href="#id-2" id="id-2"></a>

Argumenti fillimor vendoset pas `-jar *.jar` dhe inicializon Plazma-në dhe trajtohet së bashku me vlerat e tjera.

### Mënyra e përdorimit <a href="#id-2.1" id="id-2.1"></a>

Pas `-jar *.jar`, cilësitë e sistemit vendosen si argumente komandë për programin.

Për shembull, nëse dëshironi të përdorni argumentin fillimor `nogui`,\
duke e vendosur si më poshtë, Plazma do ta trajtojë argumentin `nogui` gjatë inicializimit.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argumenti i plotë fillimor <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Vlera parazgjedhur**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Vlera parazgjedhur**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Vlera parazgjedhur**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Fillon serverin në botën demo.

#### `eraseCache`

Fshin skedarët e mbetur të kešit pas përmirësimit të botës.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Shfaq argumentet dhe shpjegimin e plotë të fillimit të Plazma-së.

#### `initSettings`

Krijon vetëm skedarët e konfigurimit dhe mbyll serverin.

#### `jfrProfile`

Aktivizon profilimin JFR.

#### `max-players`

- **Alias**: `s`, `size`
- **Vlera parazgjedhur**: `(pronat e serverit)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Çaktivizon panelin e ndërfaqes grafike.

#### `nojline`

Çaktivizon JLine dhe përdor konzolën vanilje.

#### `online-mode`

- **Alias**: `o`
- **Vlera parazgjedhur**: `(pronat e serverit)`

Zgjedh nëse do të verifikohen lojtarët me serverin e autentifikimit të Mojang-ut.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Vlera parazgjedhur**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Cakton vendndodhjen e [skedarit konfigurues të PaperSpigot-it të ndaluar në përdorim](../reference/configurations/paper/README.md).

Përdoret për të transferuar konfigurimin ekzistues në një skedar të ri, dhe më pas nuk do të përdoret më.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Vlera parazgjedhur**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Vlera parazgjedhur**: `plugins`

Cakton vendndodhjen e dosjes së shtojcave.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Vlera parazgjedhur**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Vlera parazgjedhur**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Fillon serverin në një gjendje të plotë vanilje.

#### `server-ip`

- **Alias**: `h`, `host`
- **Vlera parazgjedhur**: `(pronat e serverit)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Vlera parazgjedhur**: `(pronat e serverit)`

Cakton portin e serverit.

#### `server-name`

- **Vlera parazgjedhur**: `Një Server Plazma`

Cakton emrin e serverit.

#### `spigot-settings`

- **Alias**: `S`
- **Vlera parazgjedhur**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Shfaq versionin e Plazma-së.

#### `world-dir`

- **Alias**: `W`, `universi`, `kontenieri i botës`
- **Vlera parazgjedhur**: `(dosja e serverit)`

Cakton vendndodhjen ku ruhen skedarët e botës.

#### `world-name`

- **Alias**: `w`, `botë`
- **Vlera parazgjedhur**: `(pronat e serverit)`

Cakton emrin e skedarit të botës.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Vendndodhja e argumenteve ndryshon në varësi të vendndodhjes së shtesave.

[^3]: Për shembull, nëse dëshironi të aktivizoni `Plazma.iKnowWhatIAmDoing` në `true`, mund ta bëni këtë duke vendosur `-DPlazma.iKnowWhatIAmDoing=true` ose vetëm `-DPlazma.iKnowWhatIAmDoing`.

[^4]: Për shembull, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detektori i eventit.

[^6]: Detektori i eventit.

[^7]: Klienti.

[^8]: Sinjali që tregon se serveri është lidhur normalisht si zemërpuls.

[^9]: Duke përdorur funksionin e largimit të AFK të Purpur, mund të dërgoni larg edhe lojtarët që janë larguar nga vendi.

[^10]: Sistemi i shkrimit të blloqeve të sinkronizuar, Sync Chunk Write System.

[^11]: `KUJDES! Plazma mund të shkaktojë probleme të papritura, kështu që sigurohuni të testoni plotësisht para se ta përdorni në një server publik.`

[^12]: Në lojë, `optimizimi i botës` vepron në këtë mënyrë.

[^13]: Administratorët me `nivel 2` ose më të lartë janë përjashtuar.

[^14]: Protokolli i Internetit, IP.
