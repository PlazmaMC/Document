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
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Kasutusjuhend <a href="#id-1.1" id="id-1.1"></a>

Süsteemi atribuudid sisestatakse Java käsu argumendina `java` ja `-jar` vahel.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` tähistab, et see argument pole JVM-is sisse ehitatud, vaid lisatud eraldi Plazma jaoks,

Kui atribuudile ei sisestata mingit väärtust, siis väärtus fikseeritakse [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Vaikimisi väärtus**: `750`

Juhul, kui entiteete on rohkem kui määratud väärtus, jagatakse need mitmeks paketiks edastamiseks.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Vaikimisi väärtus**: `8192`

Määrab serveri vastuvõetavate maksimaalsete paketi suuruse.

#### `Paper.ignoreJavaVersion`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `False`

Keelab Java versiooni kontrolli.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

See võib püsivalt kahjustada maailma ja üldiselt faile ning mängu mehaanikat rikkuda.

Kõik sellest tulenevad probleemid on teie enda vastutusel ja Plazma ei paku sellele mingit tuge.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Vaikimisi väärtus**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Vaikimisi väärtus**: `80`

Määrab märgi maksimaalse pikkuse ühes reas.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Vaikimisi väärtus**: `(maailma versioon) + 1`

Määrab algse maailma uuendusteabe versiooni.

Kasutatakse peamiselt massiliste tükkide värskenduste korral, kuid muul juhul pole vajalik.

#### `Paper.parseYamlCommentsByDefault`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `True`

Lülitab sisse YAML failide kommentaaride töötlemise.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Vaikimisi väärtus**: `30`

Kui mängijalt pole määratud aja jooksul (sekundites) saadud andmeid, siis mängija välja visatakse.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Kokkupõrge**: `Plazma.disableConfigOptimization`

Optimeerib algseadistust tugevamini.

Aktiveerimisel muutub server kiiremaks ja turvalisemaks, kuid võib mõjutada tugevalt mängimiskogemust.

#### `Plazma.disableConfigOptimization`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`
- **Kokkupõrge**: `Plazma.aggressiveOptimize`

Ei optimeeri algseadistust agressiivselt.

See kasutab Paberi vaikimisi seadistust.

#### `Plazma.iKnowWhatIAmDoing`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`

Keelab Plazma brändi ja kasutab vaikimisi serveri veebilogi.

#### `Plazma.useVanillaConfiguration`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `false`
- **Kokkupõrge**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

See võib oluliselt mõjutada serveri turvalisust ja jõudlust.

Kõik selle omadusest tulenevad probleemid on serveri administraatori vastutusel.
{% endhint %}

Optimeerib algseadistust Mojangi poolt pakutud vaikeseadistusega.

See deaktiveerib kõik paberist rakendatud haavatavuste parandused.

Haavatavuste parandusi saab uuesti lubada Paberi või Plazma seadistustes.

#### `Plazma.vanillaize`

- **Tüüp**: `Boolean`
- **Vaikimisi väärtus**: `true`
- **Kokkupõrge**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Optimeerib algseadistust lähemale vanillale.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Lühend**: `c`
- **Vaikimisi väärtus**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Lühend**: `c`
- **Vaikimisi väärtus**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Alustab serverit demomaailmaga

#### `eraseCache`

Eemaldab pärast maailma värskendamist allesjäänud vahemälu failid

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Keelab graafilise kasutajaliidese paneeli

#### `nojline`

Keelab JLine'i ja kasutab tavakonsooli

#### `online-mode`

- **Lühend**: `o`
- **Vaikimisi väärtus**: `(serveri omadus)`

Valib, kas autentida mängijad Mojangi autentimisserveris

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Lühend**: `paper`
- **Vaikimisi väärtus**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Määrab kasutatava PaperSpigoti konfiguratsioonifaili asukoha

Seda kasutatakse varasema seadistuse uude faili migreerimiseks ja seejärel enam ei kasutata

#### `paper-settings-directory`

- **Lühend**: `paper-dir`
- **Vaikimisi väärtus**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Lühend**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Lühend**: `p`
- **Vaikimisi väärtus**: `plugins`

Määrab pistikprogrammide kausta asukoha

#### `pufferfish-settings`

- **Lühend**: `pufferfish`
- **Vaikimisi väärtus**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Lühend**: `purpur`
- **Vaikimisi väärtus**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Alustab serverit täielikult tavalises olekus

#### `server-ip`

- **Lühend**: `h`, `host`
- **Vaikimisi väärtus**: `(serveri omadus)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: `Tase 2` või kõrgemad administraatorid on välja arvatud.

[^14]: Interneti protokoll, IP.
