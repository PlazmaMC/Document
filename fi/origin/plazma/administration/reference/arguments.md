---
description: Tutustu käynnistysparametreihin ja järjestelmäominaisuuksiin.
---

# 🎛️ Parametrit ja ominaisuudet

Käynnistysmuuttujat ja järjestelmäominaisuudet ovat arvoja, jotka lisätään [käytettäviin komentoihin](#user-content-fn-1)[^1] Plazman suorituksen aikana,\
ja ne mahdollistavat arvojen lisäämisen, jotka eivät ole muutettavissa Plazman suorituksen jälkeen.

Niiden mukaisesti **käynnistysparametrit** ja **järjestelmäominaisuudet** jaetaan **komentoon liitettävän sijainnin mukaan**.

***

## Järjestelmäominaisuus <a href="#id-1" id="id-1"></a>

Järjestelmäominaisuus syötetään `-jar`-parametrin eteen ja sitä käsitellään JVM:ssä ennen Plazman alustamista.

{% hint style="warning" %}

**Järjestelmäominaisuuksien muuttaminen voi muuttaa Plazman ja JVM:n toimintatapaa ja vaikuttaa suuresti peliin!**

Jos et tiedä tarkalleen, mitä kukin järjestelmäominaisuus tekee, **älä käytä niitä missään tapauksessa!**

{% endhint %}

### Käyttöohje <a href="#id-1.1" id="id-1.1"></a>

Järjestelmäominaisuudet syötetään Java-käskyparametreina `java` ja `-jar` välissä.

Esimerkiksi jos haluat käyttää `Plazma.dummyProperty`-järjestelmäominaisuutta,\
syöttämällä seuraavasti seuraava ominaisuus arvolla `37` lisätään Plazman alustukseen.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` ilmaisee, että kyseinen parametri ei ole JVM:ssä sisäänrakennettu vaan lisätty Plazmalle erityinen parametri,

jos arvoa ei anneta, arvo on [`true` oletusarvoisesti.](#user-content-fn-3)[^3]

{% vinkki tyyli="info" %}

**Paperweight-sarjan palvelualustat sisältävät pisteen ominaisuuden nimen erottamiseksi kullakin alustalla.**

Joissakin terminaaleissa, kuten Windows Powershellissä, nämä parametrit eivät ehkä ole sallittuja, joten parametrien molempiin päihin on [lisättävä `"`.](#user-content-fn-4)[^4]

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

**`/reload`-komento on erittäin epävakaa, joten kaikki ongelmat, jotka ilmenevät sen käytön jälkeen, ovat käyttäjän omalla vastuulla.**

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

Poistaa käytöstä rajoituksen, joka asettaa 128 lisäosakanavaa pelaajaa kohti.[^5]

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

- **Tyyppi**: `Integer`
- **Oletusarvo**: `750`

Jos entiteettejä on enemmän kuin asetettu arvo, ne lähetetään useampina paketteina.

#### `Paper.filterThreshold`

- **Tyyppi**: `Integer`
- **Oletusarvo**: `8192`

Asettaa maksimikokoisen paketin, jonka palvelin voi vastaanottaa kerralla.

#### `Paper.ignoreJavaVersion`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `False`

Poistaa käytöstä Java-version tarkistuksen.

{% hint style="danger" %}

**Tällä tavoin JVM voi yrittää käsitellä olematonta koodia!**

Tämä voi aiheuttaa pysyvää vahinkoa maailmoille ja yleisille tiedostoille, ja pelin koko mekaniikka voi hajota.

Kaikki tämän käytön aiheuttamat ongelmat ovat käyttäjän vastuulla, eikä Plazma tarjoa tukea tähän.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Tyyppi**: `Integer`
- **Oletusarvo**: `64`

Asettaa lisäosakanavan[^6] nimen enimmäisrajan.

#### `Paper.maxSignLength`

- **Tyyppi**: `Integer`
- **Oletusarvo**: `80`

Asettaa kyltin yhdellä rivillä näytettävien merkkien enimmäismäärän.

#### `Paper.minPrecachedDatafixVersion`

- **Tyyppi**: `Integer`
- **Oletusarvo**: `(maailman versio) + 1`

Asettaa alustettavien maailman päivitystietojen version ensin.

Hyödyllinen massiivisten alueiden päivityksissä, mutta muissa tapauksissa tarpeeton.

#### `Paper.parseYamlCommentsByDefault`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `True`

Aktivoi YAML-tiedostojen kommenttien käsittelyn.

#### `Paper.playerConnection.keepAlive`

- **Tyyppi**: `Integer`
- **Oletusarvo**: `30`

Kun pelaaja ei ole lähettänyt mitään tietoa annetun ajan (sekunteina), pelaaja poistetaan palvelimelta.

Yleensä peli[^7] lähettää jatkuvasti [sydämenlyöntisignaalia](#user-content-fn-8)[^8] palvelimelle, [joten pelaajaa ei poisteta,](#user-content-fn-9)[^9] mutta jos peli ei vastaa, se katsotaan kaatuneeksi ja pelaaja poistetaan palvelimelta.

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

{% hint style="warning" %}

**Tämä ominaisuus siirtyy käynnistysparametriin 1.20.5 jälkeen.**

{% endhint %}

Käynnistyksen alussa sovelletaan tiukempaa kokoonpanon optimointia.

Kun aktivoidaan, palvelin nopeutuu ja turvallisuus paranee, mutta se voi estää joitain temppuja tai vaikuttaa merkittävästi pelikokemukseen.

#### `Plazma.iKnowWhatIAmDoing`

- **Tyyppi**: `Boolean`
- **Oletusarvo**: `false`

Estää varoituksen[^11], joka ilmestyy Plazman alustuksen yhteydessä.

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

Asettaa Bukkitin [konfiguraatiotiedoston](../reference/configurations/bukkit.md) nimen ja sijainnin.

#### `command-settings`

- **Alias**: `c`
- **Oletusarvo**: `commands.yml`

Asettaa Bukkittiin [komentokonfiguraatiotiedoston](../reference/configurations/bukkit.md) nimen ja sijainnin.

#### `config`

- **Alias**: `c`
- **Oletusarvo**: `server.properties`

Asettaa [palvelimen ominaisuudet](../reference/configurations/property.md) tiedoston nimen ja sijainnin.

#### `demo`

Käynnistää palvelimen demomaailmassa.

#### `eraseCache`

Poistaa jäljellä olevat välimuistitiedostot maailman päivityksen jälkeen.

#### `forceUpgrade`

Ohittaa version ja pakottaa maailman [päivityksen](#user-content-fn-12)[^12].

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

Asettaa sallitun maksimi [pelaajien](#user-content-fn-14)[^14] määrän.

#### `nogui`

Poistaa graafisen käyttöliittymäpaneelin käytöstä.

#### `nojline`

Poistaa JLinen käytöstä ja käyttää vaniljan konsolia.

#### `online-mode`

- **Alias**: `o`
- **Oletusarvo**: `(palvelimen ominaisuus)`

Valitsee, tarkistetaanko pelaajat Mojangin todennuspalvelimella.

**Jos et käytä Velocityä tai muita etuovia, voit rikkoa [EULA:n](../getting-started/README.md#id-5) ja joutua seuraamuksiin.**

#### `paper-settings`

- **Alias**: `paper`
- **Oletusarvo**: `paper.yml`

{% hint style="warning" %}

**Tämä parametri on poistettu käytöstä 1.19.4 jälkeen**

{% endhint %}

Asettaa käytöstä poistetun PaperSpigotin konfiguraatiotiedoston sijainnin.

Tätä käytetään siirtämään vanhaa konfiguraatiota uuteen konfiguraatiotiedostoon, eikä sitä käytetä sen jälkeen.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Oletusarvo**: `config`

Asettaa [Paperin konfiguraatiotiedoston](../reference/configurations/paper/README.md) sijainnin ja nimen.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Asettaa [Plazman konfiguraatiotiedoston](../reference/configurations/plazma/README.md) sijainnin ja nimen.

#### `plugins`

- **Alias**: `p`
- **Oletusarvo**: `plugins`

Asettaa liitännäisten kansion sijainnin.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Oletusarvo**: `pufferfish.yml`

Asettaa [Pufferfishin konfiguraatiotiedoston](../reference/configurations/pufferfish.md) nimen ja sijainnin.

#### `purpur-settings`

- **Alias**: `purpur`
- **Oletusarvo**: `purpur.yml`

Asettaa [Purpurin konfiguraatiotiedoston](../reference/configurations/purpur/README.md) nimen ja sijainnin.

#### `safeMode`

Käynnistää palvelimen täyteen vaniljatilaan.

#### `server-ip`

- **Alias**: `h`, `host`
- **Oletusarvo**: `(palvelimen ominaisuus)`

Asettaa palvelimen isännän nimen tai [Internet-protokolla](#user-content-fn-13)[^13] osoitteen.

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

Asettaa [Spigotin konfiguraatiotiedoston](../reference/configurations/spigot.md) nimen ja sijainnin.

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

[^13]: Internet-protokolla, IP.

[^14]: `Tason 2` ylläpitäjät on suljettu pois.
