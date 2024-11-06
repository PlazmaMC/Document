---
description: Tutustu käynnistysparametreihin ja järjestelmäominaisuuksiin.
---

# 🎛️ Parametrit ja ominaisuudet

Aloitusparametrit ja järjestelmäominaisuudet ovat Plazman suorituksessa käytettäviä komentoja täydentäviä arvoja, jotka vaikuttavat Plazman toimintaan kokonaisuutena.

[Käynnistysparametrit](#user-content-fn-2)[^2] ja **järjestelmäominaisuudet** jaetaan **käynnistysparametreihin** ja **järjestelmäominaisuuksiin**.

***

## Järjestelmäominaisuus <a href="#id-1" id="id-1"></a>

Järjestelmäominaisuus syötetään `-jar`-parametrin eteen ja sitä käsitellään JVM:ssä ennen Plazman alustamista.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Käyttöohje <a href="#id-1.1" id="id-1.1"></a>

Järjestelmäominaisuudet syötetään Java-käskyparametreina `java` ja `-jar` välissä.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` ilmaisee, että kyseinen parametri ei ole JVM:ssä sisäänrakennettu vaan lisätty Plazmalle erityinen parametri,

Jos arvoa ei anneta, arvoksi asetetaan [`true`](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Kaikki järjestelmäominaisuudet <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Päivittää käytöstä poistettuja kylttejä.

#### `debug.entities`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Aktivoi entiteettitietoihin liittyvät vianmäärityslokit.

#### `debug.rewriteForIDE`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Deaktivoi NMS-revision oikeanlaisen latauksen IDE:stä ja automaattisesti uudelleenkartoittaa sisäiset versiot.

#### `disable.watchdog`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä Spigotin vartijan varoitusjärjestelmän.

#### `letMeReload`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä `/reload`-komentoon liittyvän varmistusviestin.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

Jos olet lisäosakehittäjä ja sinun on päivitettävä lisäosaa, käytä `hotswap`-toimintoa `/reload`-käytön sijaan.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä lisäosan, joka käyttää standardia tulo-lähtöjärjestelmää.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Varoittaa, kun vanhentunut muotoilu havaitaan keskustelukomponentissa.

#### `Paper.bypassHostCheck`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä palvelimeen liittyvä kuviovalidointi, kun pelaaja yrittää liittyä palvelimeen.

#### `Paper.debugDynamicMissingKeys`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Aktivoi vianmäärityslokit puuttuvista avaimista NBT-objekteissa.

#### `Paper.debugInvalidSkullProfiles`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Aktivoi vianmäärityslokit päättömien päälohkojen virheellisistä profiileista.

Tämä kirjaa kaikki virheelliset päälohkot sijainteineen maailmassa.

#### `Paper.disableChannelLimit`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä lisäosien luokan priorisointijärjestelmän.

Hyödyllinen ongelmatilanteissa, joissa lisäosan varjostus aiheuttaa ongelmia.

#### `Paper.disableFlushConsolidate`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä Netty-tiedonsiirron tiivistyksen.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Oletusarvo**: `750`

Jos entiteettejä on enemmän kuin asetettu arvo, ne lähetetään useampina paketteina.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Oletusarvo**: `8192`

Asettaa maksimikokoisen paketin, jonka palvelin voi vastaanottaa kerralla.

#### `Paper.ignoreJavaVersion`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä Java-version tarkistuksen.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Tämä voi aiheuttaa pysyvää vahinkoa maailmoille ja yleisille tiedostoille, ja pelin koko mekaniikka voi hajota.

Kaikki tämän käytön aiheuttamat ongelmat ovat käyttäjän vastuulla, eikä Plazma tarjoa tukea tähän.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Oletusarvo**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Oletusarvo**: `80`

Asettaa kyltin yhdellä rivillä näytettävien merkkien enimmäismäärän.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Oletusarvo**: `(maailman versio) + 1`

Asettaa alustettavien maailman päivitystietojen version ensin.

Hyödyllinen massiivisten alueiden päivityksissä, mutta muissa tapauksissa tarpeeton.

#### `Paper.parseYamlCommentsByDefault`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `True`

Aktivoi YAML-tiedostojen kommenttien käsittelyn.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Oletusarvo**: `30`

Kun pelaaja ei ole lähettänyt mitään tietoa annetun ajan (sekunteina), pelaaja poistetaan palvelimelta.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Ohittaa palvelimen ominaisuuksien kommentit.

#### `Paper.debug-sync-loads`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Aktivoi synkronisen alueen luonnin vianmäärityslokit.

#### `Paper.enable-sync-chunk-writes`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Aktivoi Minecraftin [oletus alueen kirjoitusjärjestelmän](#user-content-fn-10)[^10].

Tämä tallentaa jokaisen alueen peräkkäin, mikä aiheuttaa merkittävää suorituskyvyn laskua.

#### `Paper.explicit-flush`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Aktivoi verkon kanavan suoran tyhjennyksen.

#### `Paper.strict-thread-checks`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Kirjaa aina pääsäikeessä tapahtuvat virheet.

#### `Paper.tickList-warn-on-excessive-delay`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Varoittaa, jos aikataulutettu tehtävä kestää liian kauan.

#### `Paperclip.patchOnly`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Käytettäessä oletustiedostoa, sovellus käynnistetään vain patchia levittämällä ilman palvelimen käynnistämistä.

#### `Plazma.aggressiveOptimize`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `false`
- **Yhteentörmäys**: `Plazma.disableConfigOptimization`

Vahvistaa alkuperäisen kokoonpanon optimointia.

Sen ollessa käytössä palvelin nopeutuu ja turvallisuus lisääntyy, mutta se voi vaikuttaa merkittävästi pelikokemukseen.

#### `Plazma.disableConfigOptimization`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `false`
- **Yhteentörmäys**: `Plazma.aggressiveOptimize`

Ei optimoi alkuperäistä kokoonpanoa.

Tämä asettaa käyttöön Paperin oletuskokoonpanon.

#### `Plazma.iKnowWhatIAmDoing`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `false`

Poistaa Plazman brändäyksen käytöstä ja asettaa käytettäväksi vanillan peruspalvelimen faviconin.

#### `Plazma.useVanillaConfiguration`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `false`
- **Yhteentörmäys**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Tällä voi olla merkittävä vaikutus palvelimen turvallisuuteen ja suorituskykyyn.

Kaikki tämän ominaisuuden aiheuttamat ongelmat ovat palvelimen ylläpitäjän vastuulla.
{% endhint %}

Tuottaa alkuperäisen kokoonpanon Mojangin tarjoamilla oletusarvoilla.

Tämä poistaa käytöstä kaikki Paperissa sovelletut haavoittuvuuden korjaukset.

Haavoittuvuuden korjaukset voidaan aktivoida uudelleen Paperin tai Plazman asetuksissa.

#### `Plazma.vanillaize`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `true`
- **Yhteentörmäys**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Asettaa alkuperäisen kokoonpanon lähemmäksi vaniljaa.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Käytöstä poistettu ominaisuus <a href="#id-1.3" id="id-1.3"></a>

Seuraavat järjestelmän ominaisuudet ovat käytöstä poistettuja ominaisuuksia.

#### `timings.bypassMax`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `false`
- **Käytöstä poistettu**: Timings on poistettu käytöstä Plazmasta eteenpäin

Päätetäänkö arvojen lähettäminen Aikarin Timings API:in ylittääkö maksimin.

Vaikka näin tehtäisiin, jos API:ssa ei käsitellä poikkeusta, rajoitus asetetaan voimaan.

***

## Aloitusparametri <a href="#id-2" id="id-2"></a>

Aloitusparametri syötetään `-jar *.jar` jälkeen, kun Plazma on alustettu ja sitä käsitellään samanaikaisesti.

### Käyttöohje <a href="#id-2.1" id="id-2.1"></a>

Järjestelmän ominaisuudet syötetään ohjelman komentoparametreina `-jar *.jar` jälkeen.

Esimerkiksi, jos haluat käyttää `nogui` aloitusparametria,\
seuraavasti syöttämällä Plazma käsittelee `nogui` parametria alustuksen aikana.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Koko aloitusparametri <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Oletusarvo**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Oletusarvo**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Oletusarvo**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Käynnistää palvelimen demomaailmassa.

#### `eraseCache`

Poistaa jäljellä olevat välimuistitiedostot maailman päivityksen jälkeen.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Tulostaa Plazman koko aloitusparametrit ja niiden kuvaukset.

#### `initSettings`

Luo vain asetustiedoston ja sulkee palvelimen.

#### `jfrProfile`

Aktivoi JFR-profiloinnin.

#### `max-players`

- **Alias**: `s`, `size`
- **Oletusarvo**: `(palvelimen ominaisuus)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Poistaa graafisen käyttöliittymäpaneelin käytöstä.

#### `nojline`

Poistaa JLinen käytöstä ja käyttää vaniljan konsolia.

#### `online-mode`

- **Alias**: `o`
- **Oletusarvo**: `(palvelimen ominaisuus)`

Valitsee, tarkistetaanko pelaajat Mojangin todennuspalvelimella.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Oletusarvo**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Asettaa käytöstä poistetun PaperSpigotin konfiguraatiotiedoston sijainnin.

Tätä käytetään siirtämään vanhaa konfiguraatiota uuteen konfiguraatiotiedostoon, eikä sitä käytetä sen jälkeen.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Oletusarvo**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Oletusarvo**: `plugins`

Asettaa liitännäisten kansion sijainnin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Oletusarvo**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Oletusarvo**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Käynnistää palvelimen täyteen vaniljatilaan.

#### `server-ip`

- **Alias**: `h`, `host`
- **Oletusarvo**: `(palvelimen ominaisuus)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Oletusarvo**: `(palvelimen ominaisuus)`

Asettaa palvelimen portin.

#### `server-name`

- **Oletusarvo**: `A Plazma Server`

Asettaa palvelimen nimen.

#### `spigot-settings`

- **Alias**: `S`
- **Oletusarvo**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Tulostaa Plazman version.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Oletusarvo**: `(palvelimen kansio)`

Asettaa maailmatiedostojen sijainnin.

#### `world-name`

- **Alias**: `w`, `world`
- **Oletusarvo**: `(palvelimen ominaisuus)`

Asettaa maailmatiedoston nimen.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Riippuen lisätyistä sijainneista, sijainti, joka käsittelee parametrit, muuttuu.

[^3]: Esimerkiksi asettaessa `Plazma.iKnowWhatIAmDoing` arvoon `true` (aktivoituna), voit käyttää `-DPlazma.iKnowWhatIAmDoing` sijaan pelkkää `-DPlazma.iKnowWhatIAmDoing`, ja se toimii samalla tavalla.

[^4]: Esimerkiksi `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Tapahtumien havaitseminen.

[^6]: Tapahtumien havaitseminen.

[^7]: Asiakas.

[^8]: Signaali, joka ilmoittaa, että palvelin on yhteydessä normaalisti, kuten sydämen syke.

[^9]: Käyttämällä Purpurin AFK-karkotustoimintoa voit karkottaa myös poissaolevat pelaajat.

[^10]: Synkronoitu palan luontijärjestelmä, Sync Chunk Write System.

[^11]: `VAROITUS! Plazma saattaa aiheuttaa odottamattomia ongelmia, joten varmista, että testaat sen perusteellisesti ennen käyttöä julkisella palvelimella.`

[^12]: Pelissä `maailman optimointi` toimii samalla periaatteella.

[^13]: `Tason 2` ylläpitäjät on suljettu pois.

[^14]: Internet-protokolla, IP.
