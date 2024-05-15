---
description: Uurige algust ja süsteemi atribuute.
---

# 🎛️ Algused ja atribuudid

Algusparameetrid ja süsteemi omadused on väärtused, mis lisatakse Plazma käivitamisel kasutatavatele käskudele, mis mõjutavad Plazma üldist toimimist.

[Käivitusparameetrite lisamine](#user-content-fn-2)[^2] jaguneb **algparameetriteks** ja **süsteemi atribuutideks** vastavalt nende lisamise kohale käskudele.

***

## Süsteemi atribuudid <a href="#id-1" id="id-1"></a>

Süsteemi atribuudid sisestatakse `-jar` ette ja töödeldakse JVM poolt enne Plazma alglaadimist.

{% hint style="warning" %}

**Süsteemi omaduste muutmine võib mõjutada Plazma ja JVM-i toimimist ning võib mõjutada oluliselt mängu!**

Kui te ei tea täpselt, millist rolli iga süsteemi atribuut täidab, siis **ärge kasutage seda kunagi!**

{% endhint %}

### Kasutusjuhend <a href="#id-1.1" id="id-1.1"></a>

Süsteemi atribuudid sisestatakse Java käsu argumendina `java` ja `-jar` vahel.

Näiteks kui soovite rakendada süsteemi omadust `Plazma.dummyProperty`, sisestades järgmise, sisestatakse järgmine omadusse `37` ja Plazma alglaaditakse.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` tähistab, et see argument pole JVM-is sisse ehitatud, vaid lisatud eraldi Plazma jaoks,

Kui atribuudile ei sisestata mingit väärtust, siis väärtus fikseeritakse [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}

**Paperweight seeria serveri platvormid eristavad süsteemi omadusi iga platvormi jaoks, sisaldades atribuudi nimes `.`.**

Mõnedes terminalides, nagu Windows Powershell, võib olla nende parameetrite lubamine keelatud, seega tuleb parameetrite mõlemale otsale lisada `"` [lõppu](#user-content-fn-4)[^4].

{% endhint %}

### Kogu süsteemi atribuudid <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Uuendab kasutusel mitte olevaid märgistusi.

#### `debug.entities`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Lülitab sisse seotud entiteedi teabe silumise.

#### `debug.rewriteForIDE`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Võimaldab IDE-l korralikult lugeda silumisinfot, keelates NMS revisiooni ja automaatselt ümberkaardistades sisemise versiooni info.

#### `disable.watchdog`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Lülitab välja Spigoti valvekoera hoiatussüsteemi.

#### `letMeReload`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab `/reload` käsu uuesti laadimise kinnitussõnumi.

{% hint style="danger" %}

**`/reload` käsk on äärmiselt ebastabiilne, seega kõik serveri probleemid pärast `/reload` kasutamist on kasutaja enda vastutusel.**

Kui olete pistikprogrammi arendaja ja peate pistikprogrammi uuendama, siis kasutage `hotswap` asemel `/reload`.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab pistikprogrammi, mis kasutab standardset sisend-väljund süsteemi.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Hoiatab, kui kasutusel on lõpetatud vormingud vestluse komponentides.

#### `Paper.bypassHostCheck`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab serveri mustri sobitamise kontrolli, kui mängija serveriga ühendust loob.

#### `Paper.debugDynamicMissingKeys`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Aktiveerib tõrkeotsingu logi puuduvate NBT võtmete kohta.

#### `Paper.debugInvalidSkullProfiles`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Aktiveerib tõrkeotsingu logi valede koljuprofiilide kohta.

See logib kõik valesti paigutatud koljuprofiilid asukohaga ja maailmas.

#### `Paper.disableChannelLimit`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab 128 plugini [kanali](#user-content-fn-5)[^5] piirangu mängijale.

#### `Paper.disableClassPrioritization`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab pistikprogrammi klassi prioriteedi süsteemi.

Kasulik probleemide korral pistikprogrammi varjundiga.

#### `Paper.disableFlushConsolidate`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab Netty loputamise konsolideerimise süsteemi.

#### `Paper.excessiveTELimit`

- **Tüüp**: `Integer`
- **Vaikimisi väärtus**: `750`

Juhul, kui entiteete on rohkem kui määratud väärtus, jagatakse need mitmeks paketiks edastamiseks.

#### `Paper.filterThreshold`

- **Tüüp**: `Integer`
- **Vaikimisi väärtus**: `8192`

Määrab serveri vastuvõetavate maksimaalsete paketi suuruse.

#### `Paper.ignoreJavaVersion`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab Java versiooni kontrolli.

{% hint style="danger" %}

**See võib põhjustada JVM-i proovimise mitteeksisteerivale koodile juurdepääsu!**

See võib püsivalt kahjustada maailma ja üldiselt faile ning mängu mehaanikat rikkuda.

Kõik sellest tulenevad probleemid on teie enda vastutusel ja Plazma ei paku sellele mingit tuge.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tüüp**: `Integer`
- **Vaikimisi väärtus**: `64`

Piirab pistiku [kanali](#user-content-fn-6)[^6] nime pikkust.

#### `Paper.maxSignLength`

- **Tüüp**: `Integer`
- **Vaikimisi väärtus**: `80`

Määrab märgi maksimaalse pikkuse ühes reas.

#### `Paper.minPrecachedDatafixVersion`

- **Tüüp**: `Integer`
- **Vaikimisi väärtus**: `(maailma versioon) + 1`

Määrab algse maailma uuendusteabe versiooni.

Kasutatakse peamiselt massiliste tükkide värskenduste korral, kuid muul juhul pole vajalik.

#### `Paper.parseYamlCommentsByDefault`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `True`

Lülitab sisse YAML failide kommentaaride töötlemise.

#### `Paper.playerConnection.keepAlive`

- **Tüüp**: `Integer`
- **Vaikimisi väärtus**: `30`

Kui mängijalt pole määratud aja jooksul (sekundites) saadud andmeid, siis mängija välja visatakse.

Tavaliselt saadab [mäng](#user-content-fn-7)[^7] pidevalt [südamepekslemise signaali](#user-content-fn-8)[^8] serverisse, seega kui mäng ei vasta, siis seda ei visata, vaid loetakse mäng kokkupõrkeks ja mängijat ei töödelda serveris edasi ning ta saadetakse minema.

#### `Paper.skipServerPropertiesComments`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Ignoreerib serveri omaduste kommentaare.

#### `Paper.debug-sync-loads`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Lülitab sisse sünkroonse tüki laadimise silumise.

#### `Paper.enable-sync-chunk-writes`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Lülitab sisse Minecrafti [vaikimisi tüki kirjutamise süsteemi](#user-content-fn-10)[^10].

See salvestab iga tüki järjestikku, mis põhjustab märkimisväärset jõudluse langust.

#### `Paper.explicit-flush`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Lülitab võrgukanali selgeks loputamise.

#### `Paper.strict-thread-checks`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Logib alati peamises lõimes esinenud vigu.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Hoiatab, kui planeeritud ülesannetel on liiga suur viivitus.

#### `Paperclip.patchOnly`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Kui kasutatakse vaikimisi käivitusfaili, rakendatakse ainult paigaldus ilma serveri käivitamiseta.

#### `Plazma.aggressiveOptimize`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`

Pärsib Plazma alglaadimisel kuvatava [hoiatuse](#user-content-fn-11)[^11].

#### `Plazma.useVanillaFavicon`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`
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

- **Tüüp**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Kasutatud omadus <a href="#id-1.3" id="id-1.3"></a> on lõpetatud

Allpool olevad süsteemi omadused on lõpetatud

#### `timings.bypassMax`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`
- **Kasutamise lõpetatud**: Timings on Plazmas eemaldatud alates esipaneeli eemaldamisest

Otsustab, kas võib ületada Aikari Timings API-sse saadetavate väärtuste maksimumi

Kui API-s erinditöötlust pole, rakendatakse viivituse piirangut

***

## Algusargumendid <a href="#id-2" id="id-2"></a>

Algusargumendid sisestatakse `-jar *.jar` järel, et Plazma saaks alglaadimise ajal neid töödelda

### Kasutusjuhend <a href="#id-2.1" id="id-2.1"></a>

Süsteemi omadused sisestatakse `-jar *.jar` järel programmi käsureana

Näiteks kui soovite rakendada `nogui` algusargumendina,\
siis järgmiselt sisestades töötleb Plazma alglaadimise ajal `nogui` argumendi

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Kogu algusargumendid <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Lühend**: `b`
- **Vaikimisi väärtus**: `bukkit.yml`

Määrab Bukkiti seadistusfaili nime ja asukoha

#### `command-settings`

- **Lühend**: `c`
- **Vaikimisi väärtus**: `commands.yml`

Määrab Bukkiti käskude seadistusfaili nime ja asukoha

#### `config`

- **Lühend**: `c`
- **Vaikimisi väärtus**: `server.properties`

Määrab serveri omaduste faili nime ja asukoha

#### `demo`

Alustab serverit demomaailmaga

#### `eraseCache`

Eemaldab pärast maailma värskendamist allesjäänud vahemälu failid

#### `forceUpgrade`

Eirab versiooni ja sunnib maailma [värskendama](#user-content-fn-12)[^12]

#### `help`

- **Lühend**: `?`

Väljastab Plazma kõik algusargumendid ja selgitused

#### `initSettings`

Loo ainult konfiguratsioonifail ja sulge server

#### `jfrProfile`

Lülitab sisse JFR-profiliseerimise

#### `max-players`

- **Lühend**: `s`, `size`
- **Vaikimisi väärtus**: `(serveri omadus)`

Määrab lubatud maksimaalse [mängijate](#user-content-fn-14)[^14] arvu

#### `nogui`

Keelab graafilise kasutajaliidese paneeli

#### `nojline`

Keelab JLine'i ja kasutab tavakonsooli

#### `online-mode`

- **Lühend**: `o`
- **Vaikimisi väärtus**: `(serveri omadus)`

Valib, kas autentida mängijad Mojangi autentimisserveris

**Kui ei kasutata Velocity ega muid proksiservereid, võib see viia [EULA](../getting-started/README.md#id-5) rikkumiseni.**

#### `paper-settings`

- **Lühend**: `paper`
- **Vaikimisi väärtus**: `paper.yml`

{% hint style="warning" %}

**See argument on peatatud alates versioonist 1.19.4**

{% endhint %}

Määrab kasutatava PaperSpigoti konfiguratsioonifaili asukoha

Seda kasutatakse varasema seadistuse uude faili migreerimiseks ja seejärel enam ei kasutata

#### `paper-settings-directory`

- **Lühend**: `paper-dir`
- **Vaikimisi väärtus**: `config`

Määrab Paperi konfiguratsioonifailide kausta nime ja asukoha

#### `plazma-settings-directory`

- **Lühend**: `plazma-dir`

Määrab Plazma konfiguratsioonifailide kausta nime ja asukoha

#### `plugins`

- **Lühend**: `p`
- **Vaikimisi väärtus**: `plugins`

Määrab pistikprogrammide kausta asukoha

#### `pufferfish-settings`

- **Lühend**: `pufferfish`
- **Vaikimisi väärtus**: `pufferfish.yml`

Määrab Pufferfishi konfiguratsioonifaili nime ja asukoha

#### `purpur-settings`

- **Lühend**: `purpur`
- **Vaikimisi väärtus**: `purpur.yml`

Määrab Purpuri konfiguratsioonifaili nime ja asukoha

#### `safeMode`

Alustab serverit täielikult tavalises olekus

#### `server-ip`

- **Lühend**: `h`, `host`
- **Vaikimisi väärtus**: `(serveri omadus)`

Määrab serveri hostinime või [Interneti protokolli](#user-content-fn-13)[^13] aadressi

#### `server-port`

- **Lühend**: `p`, `port`
- **Vaikimisi väärtus**: `(serveri omadus)`

Määrab serveri pordi

#### `server-name`

- **Vaikimisi väärtus**: `A Plazma Server`

Määrab serveri nime

#### `spigot-settings`

- **Lühend**: `S`
- **Vaikimisi väärtus**: `spigot.yml`

Määrab Spigoti seadistusfaili nime ja asukoha

#### `version`

- **Lühend**: `v`

Väljastab Plazma versiooni

#### `world-dir`

- **Lühend**: `W`, `universe`, `world-container`
- **Vaikimisi väärtus**: `(serveri kaust)`

Määrab, kuhu salvestatakse maailma failid

#### `world-name`

- **Lühend**: `w`, `world`
- **Vaikimisi väärtus**: `(serveri omadus)`

Määrab maailma faili nime

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Sõltuvalt lisatud asukohast muutub argumendi töötlemise asukoht

[^3]: Näiteks kui soovite seadistada `Plazma.iKnowWhatIAmDoing` väärtuseks `true`, siis töötab sama moodi, kui sisestate ainult `-DPlazma.iKnowWhatIAmDoing` asemel `-DPlazma.iKnowWhatIAmDoing=true`

[^4]: Näiteks, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Sündmuse tuvastaja.

[^6]: Sündmuse tuvastaja.

[^7]: Klient.

[^8]: Signaal, mis teavitab serveri ja kliendi normaalsest ühendusest nagu südamelöök.

[^9]: Purpuri AFK väljaviskamise funktsiooni abil saate välja visata ka mängija, kes on lahkunud.

[^10]: Sync Chunk Write System, süngroonse tüki kirjutamise süsteem.

[^11]: `HOIATUS! Plazma võib põhjustada ootamatuid probleeme, seega veenduge, et testite seda põhjalikult enne selle kasutamist avalikul serveril.`

[^12]: Mängus `maailma optimeerimine` toimib samal põhimõttel.

[^13]: Interneti protokoll, IP.

[^14]: `Tase 2` või kõrgemad administraatorid on välja arvatud.
