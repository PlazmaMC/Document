---
description: Înțelegeți argumentele de pornire și proprietățile sistemului.
---

# 🎛️ Argumente și proprietăți

시작 변수와 시스템 속성은 Plazma 실행에 [사용되는 명령어](#user-content-fn-1)[^1]에 덧붙이는 값으로,
Plazma가 실행된 이후 변경할 수 없는 값을 변경할 수 있게 해줍니다.

[Locația adăugată comenzii](#user-content-fn-2)[^2] va fi împărțită în **Argumentul de pornire** și **Proprietățile sistemului** conform.

***

## Proprietățile sistemului <a href="#id-1" id="id-1"></a>

Proprietățile sistemului sunt valorile procesate de JVM înainte de inițializarea Plazma, fiind introduse înainte de `-jar`.

{% hint style="warning" %}

**Modificarea proprietăților sistemului poate schimba modul de funcționare al Plazma și JVM și poate avea un impact major asupra jocului!**

Dacă nu înțelegeți cu certitudine rolul fiecărei proprietăți de sistem, **nu o utilizați niciodată!**

{% endhint %}

### Mod de utilizare <a href="#id-1.1" id="id-1.1"></a>

Proprietățile sistemului sunt introduse ca argumente Java între `java` și `-jar`.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우,
다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` indică faptul că argumentul respectiv nu este încorporat în JVM, ci este un argument dedicat adăugat la Plazma,

Dacă nu se introduce nici o valoare pentru proprietate, valoarea va fi fixată la [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Platforma serverului din seria Paperweight include un punct (`.`) în numele proprietății pentru a distinge proprietățile sistemului pentru fiecare platformă.**

În unele terminale cum ar fi Windows Powershell, aceste argumente pot să nu fie acceptate, așa că trebuie să adăugați `"` la capetele argumentelor [conform](#user-content-fn-4)[^4].

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

**Comanda `/reload` este foarte instabilă, astfel că toate problemele apărute în server după utilizarea `/reload` sunt responsabilitatea utilizatorului.**

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

Dezactivează limita de 128 de canale de pluginuri [aplicate fiecărui jucător](#user-content-fn-5)[^5].

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

- **Tip**: `Integer`
- **Valoare implicită**: `750`

Dacă entitățile depășesc valoarea setată, sunt trimise în pachete multiple.

#### `Paper.filterThreshold`

- **Tip**: `Integer`
- **Valoare implicită**: `8192`

Setează dimensiunea maximă a pachetului pe care serverul îl poate primi odată.

#### `Paper.ignoreJavaVersion`

- **Tip**: `Boolean`
- **Valoare implicită**: `False`

Dezactivează verificarea versiunii Java.

{% hint style="danger" %}

**Aceasta ar putea permite JVM să încerce să acceseze cod inexistent!**

Acest lucru poate duce la deteriorarea permanentă a fișierelor precum lumea și la defectarea mecanismului de joc.

Orice problemă cauzată de acest lucru este responsabilitatea dumneavoastră, Plazma nu oferă nicio asistență în acest sens.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tip**: `Integer`
- **Valoare implicită**: `64`

플러그인 [채널](#user-content-fn-6)[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **Tip**: `Integer`
- **Valoare implicită**: `80`

Setează lungimea maximă a textului pe o linie a unui panou de semnalizare.

#### `Paper.minPrecachedDatafixVersion`

- **Tip**: `Integer`
- **Valoare implicită**: `(versiunea lumii) + 1`

Setează versiunea inițială a informațiilor de actualizare a lumii care trebuie inițializate.

Util în cazul în care este necesară actualizarea în masă a chunk-urilor, dar în celelalte situații nu este folosit.

#### `Paper.parseYamlCommentsByDefault`

- **Tip**: `Boolean`
- **Valoare implicită**: `True`

Activează procesarea comentariilor YAML din fișiere.

#### `Paper.playerConnection.keepAlive`

- **Tip**: `Integer`
- **Valoare implicită**: `30`

Dacă un jucător nu trimite nicio dată pentru o perioadă specificată (în secunde), este deconectat.

În mod obișnuit, [jocul](#user-content-fn-7)[^7] trimite în continuu semnalul de [bătaie al inimii](#user-content-fn-8)[^8] către server, astfel că nu vei fi [dat afară,](#user-content-fn-9)[^9] dar dacă jocul nu răspunde, se consideră că a intrat în conflict și nu mai procesează jucătorul pe server, ci îl dă afară.

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

{% hint style="warning" %}

**Această proprietate va fi mutată ca argument de pornire după versiunea 1.20.5.**

{% endhint %}

Aplică optimizări mai stricte la configurarea inițială la prima pornire.

Activarea va face serverul să funcționeze mai rapid și mai sigur, dar poate bloca unele mecanisme sau putea afecta în mod semnificativ jocul.

#### `Plazma.iKnowWhatIAmDoing`

- **Tip**: `Boolean`
- **Valoare implicită**: `false`

Suprimă [avertismentul](#user-content-fn-11)[^11] afișat la inițializarea Plazmei.

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

Stabilește numele și locația [fișierului de configurare Bukkit](../reference/configurations/bukkit.md).

#### `command-settings`

- **Poreclă**: `c`
- **Valoare implicită**: `commands.yml`

Stabilește numele și locația [fișierului de configurare a comenzilor Bukkit](../reference/configurations/bukkit.md).

#### `config`

- **Poreclă**: `c`
- **Valoare implicită**: `server.properties`

Stabilește numele și locația [fișierului de proprietăți al serverului](../reference/configurations/property.md).

#### `demo`

Pornește serverul în lumea demonstrativă.

#### `eraseCache`

Șterge fișierele de cache rămase după actualizarea lumii.

#### `forceUpgrade`

Actualizează lumea forțat, ignorând versiunea [de actualizare](#user-content-fn-12)[^12].

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

Stabilește numărul maxim de [jucători](#user-content-fn-14)[^14] permis.

#### `nogui`

Dezactivează panoul interfeței grafice.

#### `nojline`

Dezactivează JLine și folosește consola vanilla.

#### `mod-online`

- **Poreclă**: `o`
- **Valoare implicită**: `(proprietatea serverului)`

Selectează dacă să verifice jucătorii prin serverul de autentificare Mojang.

**În cazul în care nu se utilizează Velocity sau alte proxy-uri, se poate fi sancționat pentru încălcarea [EULA](../getting-started/README.md#id-5).**

#### `setări-hârtie`

- **Poreclă**: `hârtie`
- **Valoare implicită**: `paper.yml`

{% hint style="warning" %}

**Acest argument a fost dezactivat după versiunea 1.19.4**

{% endhint %}

Stabilește locația fișierului de configurare PaperSpigot dezactivat.

Acesta este utilizat pentru a muta configurația existentă într-un nou fișier de configurare și nu va fi utilizat ulterior.

#### `director-setări-hârtie`

- **Poreclă**: `dir-hârtie`
- **Valoare implicită**: `config`

Stabilește numele și locația folderului în care se află [fișierele de configurare Paper](../reference/configurations/paper/README.md).

#### `director-setări-plazma`

- **Poreclă**: `dir-plazma`

Stabilește numele și locația folderului în care se află [fișierele de configurare Plazma](../reference/configurations/plazma/README.md).

#### `module`

- **Poreclă**: `m`
- **Valoare implicită**: `module`

Stabilește locația folderului pentru module.

#### `setări-pufferfish`

- **Poreclă**: `pufferfish`
- **Valoare implicită**: `pufferfish.yml`

Stabilește numele și locația [fișierului de configurare Pufferfish](../reference/configurations/pufferfish.md).

#### `setări-purpur`

- **Poreclă**: `purpur`
- **Valoare implicită**: `purpur.yml`

Stabilește numele și locația [fișierului de configurare Purpur](../reference/configurations/purpur/README.md).

#### `mod-sigur`

(Mod sigur) Pornește serverul într-o stare complet vanilată.

#### `ip-server`

- **Poreclă**: `h`, `gazdă`
- **Valoare implicită**: `(proprietatea serverului)`

Stabilește numele gazdei sau adresa [Protocolului Internet](#user-content-fn-13)[^13] a serverului.

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

Stabilește numele și locația [fișierului de configurare Spigot](../reference/configurations/spigot.md).

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

[^13]: Protocolul Internet, IP.

[^14]: Administratorii de nivel 2 și peste sunt excluși.
