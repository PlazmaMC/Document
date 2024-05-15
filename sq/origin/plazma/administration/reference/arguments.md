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

**Nëse ndryshoni atributet e sistemit, Plazma dhe mënyra se si vepron JVM mund të ndryshojnë, dhe kjo mund të ketë ndikim të madh në lojë!**

Nëse nuk e dini qartë se çfarë rol luajnë atributet e çdo sistemi, **mos i përdorni kurrë ato!**

{% endhint %}

### Mënyra e përdorimit <a href="#id-1.1" id="id-1.1"></a>

Përkatësitë e sistemit vendosen si argumente Java midis `java` dhe `-jar`.

Për shembull, nëse dëshironi të aplikoni atributin e sistemit `Plazma.dummyProperty`, duke futur si më poshtë, vlera `37` do të futet në atributin tjetër dhe Plazma do të inicjalizohet.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` tregon se ky argument nuk është i brendshëm në JVM, por është argument i shtuar ekskluzivisht për Plazma-n.

Nëse nuk jepni asnjë vlerë për tipare, vlera do të mbetet [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Platforma e serverit e serisë Paperweight përfshin një `.` në emrin e atributit për të dalluar atributet e sistemit për çdo platformë individuale.**

Në disa terminalë si Windows Powershell, mund të mos lejohen këto argumente, kështu që duhet të shtoni `"` në fund të argumentit për të [shtuar](#user-content-fn-4)[^4].

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

**Komanda `/reload` është shumë e paqëndrueshme, kështu që çdo problem që ndodh në server pas përdorimit të `/reload` është përgjegjësi e vetë përdoruesit.**

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

Çaktivizon kufirin e numrit të kanaleve të plugin-it, 128 për çdo lojtar.

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

- **Forma**: `Integer`
- **Vlera parazgjedhëse**: `750`

Nëse entiteti është më i madh se vlera e caktuar, ndahet në pako të ndryshme për transmetim.

#### `Paper.filterThreshold`

- **Forma**: `Integer`
- **Vlera parazgjedhëse**: `8192`

Cakton madhësinë maksimale të pako të pranueshme nga serveri.

#### `Paper.ignoreJavaVersion`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `False`

Çaktivizon verifikimin e versionit të Java-së.

{% hint style="danger" %}

**Kjo mund të tentojë qasje në kod që nuk ekziston në JVM!**

Kjo mund të shkaktojë dëmtim të përhershëm të skedarëve të botës dhe shkatërrimin e mekanikës së lojës.

Çdo problem që shkaktohet nga kjo është përgjegjësia e përdoruesit dhe Plamza nuk ofron asnjë mbështetje për këtë.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Forma**: `Integer`
- **Vlera parazgjedhëse**: `64`

Vendos kufizimin e emrit të [kanalit](#user-content-fn-6)[^6] të shtojcës.

#### `Paper.maxSignLength`

- **Forma**: `Integer`
- **Vlera parazgjedhëse**: `80`

Cakton gjatësinë maksimale të shenjave në një rresht.

#### `Paper.minPrecachedDatafixVersion`

- **Forma**: `Integer`
- **Vlera parazgjedhëse**: `(versioni i botës) + 1`

Cakton versionin e informacionit të përditësimit fillestar për botën që do të inicializohet së pari.

Është e dobishme kur ka nevojë për të azhurnuar një numër të madh të blloqeve, por nuk përdoret në raste të tjera.

#### `Paper.parseYamlCommentsByDefault`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `True`

Aktivizon trajtimin e komenteve YAML-së.

#### `Paper.playerConnection.keepAlive`

- **Forma**: `Integer`
- **Vlera parazgjedhëse**: `30`

Kur nuk pranohet asnjë të dhënë nga një lojtar për një periudhë të caktuar (sekonda), lojtari do të dërgohet larg.

Në rastet normale, [loja](#user-content-fn-7)[^7] vazhdon të dërgojë [sinjalet e zemrës](#user-content-fn-8)[^8] në server, kështu që nuk do të jetë i [dëbuar,](#user-content-fn-9)[^9] por nëse loja nuk përgjigjet, konsiderohet se ka ndodhur një konflikt dhe nuk do të trajtojë më lojtarët në server dhe do t'i dëbojë ata.

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
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iDijaCfarePoBej`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`

Parandalon [sinjalin e paralajmërimit](#user-content-fn-11)[^11] që shfaqet kur Plazma inicializohet.

#### `Plazma.useVanillaFavicon`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Forma**: `Boolean`
- **Vlera parazgjedhëse**: `false`
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

- **Forma**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

Cakton emrin dhe vendndodhjen e [skedarit konfigurues të Bukkit-it](../reference/configurations/bukkit.md).

#### `command-settings`

- **Alias**: `c`
- **Vlera parazgjedhur**: `commands.yml`

Cakton emrin dhe vendndodhjen e [skedarit konfigurues të komandave të Bukkit-it](../reference/configurations/bukkit.md).

#### `config`

- **Alias**: `c`
- **Vlera parazgjedhur**: `server.properties`

Cakton emrin dhe vendndodhjen e [skedarit të pronave të serverit](../reference/configurations/property.md).

#### `demo`

Fillon serverin në botën demo.

#### `eraseCache`

Fshin skedarët e mbetur të kešit pas përmirësimit të botës.

#### `forceUpgrade`

Forcon një [përmirësim](#user-content-fn-12)[^12] të botës pa marrë parasysh versionin.

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

Vendos numrin maksimal të [lojtarëve](#user-content-fn-14)[^14] të lejuar.

#### `nogui`

Çaktivizon panelin e ndërfaqes grafike.

#### `nojline`

Çaktivizon JLine dhe përdor konzolën vanilje.

#### `online-mode`

- **Alias**: `o`
- **Vlera parazgjedhur**: `(pronat e serverit)`

Zgjedh nëse do të verifikohen lojtarët me serverin e autentifikimit të Mojang-ut.

**Nëse nuk përdoret një [EULA](../getting-started/README.md#id-5) për shfrytëzim të proxy-së si Velocity, mund të ndëshkohet për shkelje.**

#### `paper-settings`

- **Alias**: `paper`
- **Vlera parazgjedhur**: `paper.yml`

{% hint style="warning" %}

**Ky argument është ndaluar për përdorim pas versionit 1.19.4**

{% endhint %}

Cakton vendndodhjen e [skedarit konfigurues të PaperSpigot-it të ndaluar në përdorim](../reference/configurations/paper/README.md).

Përdoret për të transferuar konfigurimin ekzistues në një skedar të ri, dhe më pas nuk do të përdoret më.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Vlera parazgjedhur**: `config`

Cakton emrin dhe vendndodhjen e dosjes ku gjenden [skedarët konfigurues të Paper-it](../reference/configurations/paper/README.md).

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Cakton emrin dhe vendndodhjen e dosjes ku gjenden [skedarët konfigurues të Plazma-së](../reference/configurations/plazma/README.md).

#### `plugins`

- **Alias**: `p`
- **Vlera parazgjedhur**: `plugins`

Cakton vendndodhjen e dosjes së shtojcave.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Vlera parazgjedhur**: `pufferfish.yml`

Cakton emrin dhe vendndodhjen e [skedarit konfigurues të Pufferfish-it](../reference/configurations/pufferfish.md).

#### `purpur-settings`

- **Alias**: `purpur`
- **Vlera parazgjedhur**: `purpur.yml`

Cakton emrin dhe vendndodhjen e [skedarit konfigurues të Purpur-it](../reference/configurations/purpur/README.md).

#### `safeMode`

Fillon serverin në një gjendje të plotë vanilje.

#### `server-ip`

- **Alias**: `h`, `host`
- **Vlera parazgjedhur**: `(pronat e serverit)`

Cakton emrin e hostit të serverit ose adresën [IP të internetit](#user-content-fn-13)[^13].

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

Cakton emrin dhe vendndodhjen e [skedarit konfigurues të Spigot-it](../reference/configurations/spigot.md).

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

[^13]: Protokolli i Internetit, IP.

[^14]: Administratorët me `nivel 2` ose më të lartë janë përjashtuar.
