---
description: Înțelegeți argumentele de pornire și proprietățile sistemului.
---

# 🎛️ Argumente și proprietăți

Începutul achiziției și proprietățile sistemului sunt valori adăugate la [comenzile utilizate](#user-content-fn-1)[^1] pentru a rula Plazma, având un impact general asupra funcționării Plazmei.

[Locația adăugată comenzii](#user-content-fn-2)[^2] va fi împărțită în **Argumentul de pornire** și **Proprietățile sistemului** conform.

***

## Proprietățile sistemului <a href="#id-1" id="id-1"></a>

Proprietățile sistemului sunt valorile procesate de JVM înainte de inițializarea Plazma, fiind introduse înainte de `-jar`.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Mod de utilizare <a href="#id-1.1" id="id-1.1"></a>

Proprietățile sistemului sunt introduse ca argumente Java între `java` și `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indică faptul că argumentul respectiv nu este încorporat în JVM, ci este un argument dedicat adăugat la Plazma,

Dacă nu se introduce nici o valoare pentru proprietate, valoarea va fi fixată la [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Toate proprietățile sistemului <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Actualizează formatul panourilor de semnalizare dezactivate.

#### `debug.entities`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Activează jurnalele de depanare legate de informațiile entității.

#### `debug.rewriteForIDE`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează revizia NMS pentru a permite IDE-ului să citească corect informațiile de depanare și remapează automat informațiile de versiune interne.

#### `disable.watchdog`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează sistemul de avertizare Watchdog al Spigot.

#### `letMeReload`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează mesajul de confirmare al comenzii `/reload`.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Dacă sunteți dezvoltator de plugin-uri și trebuie să faceți actualizări, folosiți hotswap în loc de comanda `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează pluginurile care folosesc sistemul standard de intrare/ieșire.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Avertizează când se detectează un format vechi în componentele de chat.

#### `Paper.bypassHostCheck`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează verificarea potrivirii modelului serverului atunci când un jucător se conectează la server.

#### `Paper.debugDynamicMissingKeys`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Activează jurnalele de depanare pentru cheile lipsă din obiectele NBT.

#### `Paper.debugInvalidSkullProfiles`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Activează jurnalele de depanare pentru profilurile incorecte ale capului.

Aceasta va înregistra toate blocurile de cap incorecte din lume, împreună cu locațiile acestora.

#### `Paper.disableChannelLimit`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează sistemul de prioritizare a claselor de pluginuri.

Util în cazul în care apar probleme în umbrirea pluginurilor.

#### `Paper.disableFlushConsolidate`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează consolidarea de flux Netty.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Valoare implicită**: `750`

Dacă entitățile depășesc valoarea setată, sunt trimise în pachete multiple.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Valoare implicită**: `8192`

Setează dimensiunea maximă a pachetului pe care serverul îl poate primi odată.

#### `Paper.ignoreJavaVersion`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează verificarea versiunii Java.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Acest lucru poate duce la deteriorarea permanentă a fișierelor precum lumea și la defectarea mecanismului de joc.

Orice problemă cauzată de acest lucru este responsabilitatea dumneavoastră, Plazma nu oferă nicio asistență în acest sens.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Valoare implicită**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Valoare implicită**: `80`

Setează lungimea maximă a textului pe o linie a unui panou de semnalizare.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Valoare implicită**: `(versiunea lumii) + 1`

Setează versiunea inițială a informațiilor de actualizare a lumii care trebuie inițializate.

Util în cazul în care este necesară actualizarea în masă a chunk-urilor, dar în celelalte situații nu este folosit.

#### `Paper.parseYamlCommentsByDefault`

- **Tip**: `Boolean`
- **Valoare implicită**: `True`

Activează procesarea comentariilor YAML din fișiere.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Valoare implicită**: `30`

Dacă un jucător nu trimite nicio dată pentru o perioadă specificată (în secunde), este deconectat.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Ignoră comentariile din proprietățile serverului.

#### `Paper.debug-sync-loads`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Activează jurnalele de depanare pentru încărcările sincronizate de chunk-uri.

#### `Paper.enable-sync-chunk-writes`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Activează sistemul de scriere a chunk-urilor sincronizat implicit din Minecraft.

Acest lucru duce la o performanță foarte scăzută deoarece fiecare chunk este salvat în ordine.

#### `Paper.explicit-flush`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Activează descărcarea explicită a canalului de rețea.

#### `Paper.strict-thread-checks`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Înregistrează întotdeauna erorile care nu apar pe thread-ul principal.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Afișează avertismente când o sarcină programată are o întârziere excesivă.

#### `Paperclip.patchOnly`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dacă se folosește fișierul de executare implicit, aplică doar patch-ul fără a porni serverul.

#### `Plazma.aggressiveOptimize`

- **Tip**: `Boolean`
- **Valoare implicită**: `false`
- **Conflict**: `Plazma.disableConfigOptimization`

Optimize the initial configuration more strongly.

Activating this will make the server faster and safer, but can have a major impact on gameplay.

#### `Plazma.disableConfigOptimization`

- **Tip**: `Boolean`
- **Valoare implicită**: `false`
- **Conflict**: `Plazma.aggressiveOptimize`

Do not optimize the initial configuration.

This forces the use of the default configuration of Paper.

#### `Plazma.iKnowWhatIAmDoing`

- **Tip**: `Boolean`
- **Valoare implicită**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tip**: `Boolean`
- **Valoare implicită**: `false`

Disables Plazma branding and uses the vanilla default server favicon.

#### `Plazma.useVanillaConfiguration`

- **Tip**: `Boolean`
- **Valoare implicită**: `false`
- **Conflict**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

This can significantly impact server security and performance.

Any issues arising from using this property are the responsibility of the server administrator.
{% endhint %}

Provides the initial configuration with the default values provided by Mojang.

This disables all vulnerability patches applied in Paper.

Vulnerability patches can be re-enabled in Paper configuration or Plazma configuration.

#### `Plazma.vanillaize`

- **Tip**: `Boolean`
- **Default**: `true`
- **Conflict**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Sets the initial configuration closer to vanilla.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Proprietatea întreruptă <a href="#id-1.3" id="id-1.3"></a>

Următoarele proprietăți de sistem sunt proprietăți întrerupte.

#### `timings.bypassMax`

- **Tip**: `Boolean`
- **Valoare implicită**: `false`
- **Întrerupt**: Timings a fost eliminat din Plazma

Hotărăște dacă valoarea trimisă către API-ul Timings al lui Aikar poate depăși maximul permis.

Chiar și atunci când se face acest lucru, limita de rată se aplică dacă nu este gestionată excepțional de API.

***

## Argumentul de pornire <a href="#id-2" id="id-2"></a>

Argumentul de pornire este introdus după `-jar *.jar` pentru a inițializa Plazma și este tratat împreună cu acesta.

### Mod de utilizare <a href="#id-2.1" id="id-2.1"></a>

Proprietățile de sistem sunt introduse ca argumente de comandă după `-jar *.jar`.

De exemplu, dacă doriți să aplicați argumentul de pornire `nogui`,\
introduceți astfel pentru ca Plazma să-l proceseze în timpul inițializării.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Argumentul de pornire complet <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Poreclă**: `b`
- **Valoare implicită**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Poreclă**: `c`
- **Valoare implicită**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Poreclă**: `c`
- **Valoare implicită**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Pornește serverul în lumea demonstrativă.

#### `eraseCache`

Șterge fișierele de cache rămase după actualizarea lumii.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Poreclă**: `?`

Afișează toate argumentele și descrierile de pornire ale Plazma.

#### `initSettings`

Generează doar fișierele de configurare și închide serverul.

#### `jfrProfile`

Activează profilarea JFR.

#### `max-players`

- **Poreclă**: `s`, `size`
- **Valoare implicită**: `(proprietatea serverului)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Dezactivează panoul interfeței grafice.

#### `nojline`

Dezactivează JLine și folosește consola vanilla.

#### `mod-online`

- **Poreclă**: `o`
- **Valoare implicită**: `(proprietatea serverului)`

Selectează dacă să verifice jucătorii prin serverul de autentificare Mojang.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `setări-hârtie`

- **Poreclă**: `hârtie`
- **Valoare implicită**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Stabilește locația fișierului de configurare PaperSpigot dezactivat.

Acesta este utilizat pentru a muta configurația existentă într-un nou fișier de configurare și nu va fi utilizat ulterior.

#### `director-setări-hârtie`

- **Poreclă**: `dir-hârtie`
- **Valoare implicită**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `director-setări-plazma`

- **Poreclă**: `dir-plazma`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `module`

- **Poreclă**: `m`
- **Valoare implicită**: `module`

Stabilește locația folderului pentru module.

#### `setări-pufferfish`

- **Poreclă**: `pufferfish`
- **Valoare implicită**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `setări-purpur`

- **Poreclă**: `purpur`
- **Valoare implicită**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `mod-sigur`

(Mod sigur) Pornește serverul într-o stare complet vanilată.

#### `ip-server`

- **Poreclă**: `h`, `gazdă`
- **Valoare implicită**: `(proprietatea serverului)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `port-server`

- **Poreclă**: `p`, `port`
- **Valoare implicită**: `(proprietatea serverului)`

Stabilește portul serverului.

#### `nume-server`

- **Valoare implicită**: `Un server Plazma`

Stabilește numele serverului.

#### `setări-spigot`

- **Poreclă**: `S`
- **Valoare implicită**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `versiune`

- **Poreclă**: `v`

Afișează versiunea Plazma.

#### `director-lume`

- **Poreclă**: `W`, `univers`, `container-lume`
- **Valoare implicită**: `(folder-ul serverului)`

Stabilește locația în care sunt salvate fișierele lumii.

#### `nume-lume`

- **Poreclă**: `w`, `lume`
- **Valoare implicită**: `(proprietatea serverului)`

Stabilește numele fișierului lumii.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Poziția de procesare a argumentelor se schimbă în funcție de locația adăugată.

[^3]: De exemplu, dacă doriți să setați (activați) `Plazma.iKnowWhatIAmDoing` la `true`, în loc să introduceți `-DPlazma.iKnowWhatIAmDoing=true`, puteți introduce doar `-DPlazma.iKnowWhatIAmDoing` și va funcționa la fel de bine.

[^4]: De exemplu, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Detector de evenimente.

[^6]: Detector de evenimente.

[^7]: Client.

[^8]: Semnal care confirmă o conexiune corectă cu serverul, similar cu bătăile inimii.

[^9]: Cu funcția de eliminare AFK a lui Purpur, jucătorii care stau inactivi pot fi eliminați.

[^10]: Sistem de scriere sincronizată a chunk-urilor, Sync Chunk Write System.

[^11]: `ATENȚIE! Plazma poate cauza probleme neașteptate, așa că asigurați-vă că o testați în detaliu înainte de a o utiliza pe un server public.`

[^12]: Optimizarea lumii în joc funcționează pe același principiu.

[^13]: Administratorii de nivel 2 și peste sunt excluși.

[^14]: Protocolul Internet, IP.
