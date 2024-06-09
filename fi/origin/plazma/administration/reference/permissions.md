---
description: Selvitä Plazma-sovelluksen oikeudet.
---

# 🛡️ Oikeudet

Oikeudet ovat yksinkertainen turvallisuustyökalu, joka määrittää, millä tavalla palvelimen pelaajat voivat vuorovaikuttaa keskenään.

Oikeuksien asianmukaiseen käyttöön ja helpottamiseen tarvitaan lisäosia, kuten [LuckPerms](https://luckperms.net).

***

## Ymmärtääksesi perusoikeusjärjestelmää, katso <a href="#id-1" id="id-1"></a>

Minecraft tarjoaa perus hallintaoikeusryhmiä.

[Ylläpitäjä](#user-content-fn-1)[^1] voi asettaa oikeudet ja komennot lohkot voidaan muokata [palvelimen ominaisuuksissa](configurations/property.md).

0. **Pelaaja**\
   Yleinen oikeusryhmä, joka annetaan kaikille pelaajille.
1. **Välittäjä**\
   Voi ohittaa spawn-suojauksen.
2. **Maailmanhallitsija**\
   Voi käyttää kaikkia maailmanhallintaan liittyviä komentoja ja komentolohkoja.\
   Oletusarvoinen oikeusryhmä datapaketeille ja komentolohkoille.
3. **Hallinnoija**\
   Voi käyttää kaikkia pelaajien hallintaan liittyviä komentoja.
4. **Ylimmäinen hallinnoija**\
   Voi käyttää kaikkia palvelimen hallintaan liittyviä komentoja.\
   Oletusarvoinen oikeusryhmä konsolille ja ylläpitäjille.

***

## Oikeuksien määrittäminen <a href="#id-2" id="id-2"></a>

***

## Kaikki oikeudet <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Oletus**: `None`

Sallii pelaajan kyytiin nousemisen ja vuorovaikutuksen entiteetin kanssa.

Kun pelaaja nousee kyytiin, hän voi ohjata entiteetin liikettä liikkumisnäppäimillä ja hypätä tai lentää hyppynäppäimellä.

`(Namespaced Key)` tarkoittaa entiteetin [Namespaced ID](#user-content-fn-2)[^2].

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `(Entity) > ridable` aktivoituna toimiakseen.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Oletus**: `None`

Sallii pelaajan käyttää entiteetin erikoistaitoja, kun pelaaja ratsastaa entiteetillä.

Kaikki entiteetit eivät välttämättä voi käyttää erikoistaitoja. Kaikki käytettävissä olevat erikoistaidot löytyvät alla olevasta linkistä.

{% vinkki tyyli="info" %}

**Onko sinulla hyviä ideoita erikoistaitoja varten?**

Jaa ideoitasi [Plazma Discordissa](https://plazmamc.org/discord) tai [GitHubin keskusteluissa](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Näytä käytettävissä olevat erikoistaidot</summary>

- **`crepper`**\
  Räjähtää painamalla `hyppy-näppäintä`.\
  Jos pelaajalla on oikeus `allow.powered.creeper`, hän voi ladata räjäytyksen pitämällä `hyppy-näppäintä` pohjassa.
- **`dolphin`**\
  Ryntää painamalla `hyppy-näppäintä`.
- **`phantom`**\
  Ampuu liekkejä painamalla `hyppy-näppäintä`.
- **`wither`**\
  Ampuu wither-päätä painamalla `vuorovaikutus-näppäintä`.

</details>

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `(Entity) > ridable` aktivoituna toimiakseen.**

{% endhint %}

#### `bukkit.command.compass`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/compass`-komentojen](commands.md#compass) käytön.

#### `bukkit.command.credits`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/credits (Pelaaja)`-komentojen](commands.md#credits) käytön.

Lisää `.other` käyttäjänimen perään antaa oikeuden käyttää komentoa muille pelaajille.

#### `bukkit.command.demo`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/demo (Pelaaja)`-komentojen](commands.md#demo) käytön.

Lisää `.other` käyttäjänimen perään antaa oikeuden käyttää komentoa muille pelaajille.

#### `bukkit.command.ping`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/ping (Pelaaja)`-komentojen](commands.md#ping) käytön.

Lisää `.other` käyttäjänimen perään antaa oikeuden käyttää komentoa muille pelaajille.

#### `bukkit.command.ram`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/ram`-komentojen](commands.md#ram) käytön.

#### `bukkit.command.rambar`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/rambar (Pelaaja)`-komentojen](commands.md#rambar) käytön.

Lisää `.other` käyttäjänimen perään antaa oikeuden käyttää komentoa muille pelaajille.

#### `bukkit.command.restart`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/restart`-komentojen](commands.md#restart) käytön.

#### `bukkit.command.tps`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/tps`-komentojen](commands.md#tps) käytön.

#### `bukkit.command.tpsbar`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/tpsbar (Pelaaja)`-komentojen](commands.md#tpsbar) käytön.

Lisää `.other` käyttäjänimen perään antaa oikeuden käyttää komentoa muille pelaajille.

#### `bukkit.command.timings`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/timings`-komentojen](commands.md#timings) käytön.

{% hint style="warning" %}

**Tämä komento on poistettu käytöstä.**

Katso vastaava komento [Sparkista](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/uptime`-komentojen](commands.md#uptime) käytön.

#### `minecraft.command.gamemode.(GameMode)`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii [`/gamemode (GameMode) (Pelaaja)`-komentojen](commands.md#gamemode) käytön.

Lisää `.other` käyttäjänimen perään antaa oikeuden käyttää komentoa muille pelaajille.

#### `paper.antixray.bypass`

- **Oletus**: `None`

Kun [X-Ray estäminen](../expert/xray.md) on aktivoitu,
oikeutetuille pelaajille ei suoriteta X-Ray estämiseen liittyvää lohkojen hämäystä.

Tämä mahdollistaa suorituskyvyn parantamisen molemmilla osapuolilla.

> Katso X-Rayn asetukset alla olevasta linkistä.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Oletus**: `None`

{% hint style="warning" %}

Tämä oikeus muutetaan versiossa 1.20.5 muotoon `plazma.bypass.watchdog`.

{% endhint %}

#### `purpur.anvil.color`

- **Oletus**: `None`

Mahdollistaa värillisten koodien käytön alasimissa [värikoodien](https://minecraft.wiki/w/Formatting_codes#Color_codes) avulla.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `anvil > allow-colors` aktivoituna toimiakseen.**

{% endhint %}

#### `purpur.anvil.format`

- **Oletus**: `None`

Mahdollistaa muotoilukoodien käytön alasimissa [muotoilukoodien](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) avulla.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `anvil > allow-colors` aktivoituna toimiakseen.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Oletus**: `None`

Mahdollistaa MiniMessage-tunnisteiden käytön alasimissa [MiniMessage-tageilla](https://docs.advntr.dev/minimessage/format.html).

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `anvil > allow-minimessages` aktivoituna toimiakseen.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Oletus**: `None`

Mahdollistaa `kursiivin` poistamisen alasimissa käyttämällä [`&r` muotoilukoodia](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `anvil > allow-colors` aktivoituna toimiakseen.**

{% endhint %}

#### `purpur.book.color.sign`

- **Oletus**: `None`

Kun pelaaja allekirjoittaa kirjan, sovelletaan [muotoilukoodit](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- **Oletus**: `None`

Poistaa pelaajan lepotilasta johtuvan poiston uhasta.

#### `purpur.debug.f3n`

- **Sisäänrakennettu**: `maailmanhallintaaja`

Sallii pelaajan vaihtaa pelitilaa painamalla `F3 + N` näppäimiä.

Toimii vain, jos pelaajalla on kyseiseen pelitilaan oikeus.

#### `purpur.drop.spawners`

- **Oletus**: `None`

Kaivettaessa spawner-lohkolla käytetään asetettuja esineitä, spawner-lohko pudotetaan.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `gameplay-mechanics > silk-touch` aktivoituna toimiakseen.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Oletus**: `None`

Muuttaa enderarkun koon.

`(NumberString)` voi olla `one`, `two`, `three`, `four`, `five`, `six`.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `ender_chest > six-rows` ja `ender_chest > use-permissions-for-rows` aktivoituna toimiakseen.**

{% endhint %}

#### `purpur.inventory_totem`

- **Oletus**: `None`

Sallii kuolemattomuuden toimivan, vaikka totemi olisi inventaariossa.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md): aktivoi `totem-of-undying-works-in-inventory` sen toimimiseksi.**

{% endhint %}

#### `purpur.joinFullServer`

- **Oletus**: `None`

Sallii pelaajan ohittaa liittymisrajoituksen.

#### `purpur.mending_shift_click`

- **Oletus**: `None`

Sallii pelaajan korjata esineitä pitämällä niitä ja kyykistymällä.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md): aktivoi `shift-right-click-repairs-mending-points` sen toimimiseksi.**

{% endhint %}

#### `purpur.place.spawners`

- **Oletus**: `None`

Sallii pelaajan asentaa kohderyhmät.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md) vaativat `gameplay-mechanics > silk-touch` aktivoituna toimiakseen.**

{% endhint %}

#### `purpur.portal.instant`

- **Oletus**: `None`

Sallii pelaajan siirtyä heti Nether-portaalista.

#### `purpur.sign.color`

- **Oletus**: `None`

Sallii värillisten koodien käytön kylteissä [värikoodien](https://minecraft.wiki/w/Formatting_codes#Color_codes) avulla.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md): aktivoi `sign > allow-colors` sen toimimiseksi.**

{% endhint %}

#### `purpur.sign.magic`

- **Oletus**: `None`

Sallii kylteissä käsittämättömän koodin `(&o)` käytön.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md): aktivoi `sign > allow-colors` sen toimimiseksi.**

{% endhint %}

#### `purpur.sign.style`

- **Oletus**: `None`

Sallii kylteissä [tyylittelykoodit `(&o pois)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) käytön.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md): aktivoi `sign > allow-colors` sen toimimiseksi.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Oletus**: `None`

Sallii pelaajan estää TNT:n räjähdyksen vuorovaikutteisesti saksilla.

{% vinkki tyyli="info" %}

**[Purpur maailman asetukset](configurations/purpur/world.md): `defuse-tnt-change` on oltava vähintään `0.0` sen toimimiseksi.**

{% endhint %}

### Suunnitellut oikeudet

#### `plazma.bypass.ncr-require`

- **Oletus**: `None`

Sallii pelaajan liittyä, vaikka [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) -moduulia ei olisi asennettu.

{% vinkki tyyli="info" %}

**[Plazma maailman asetukset](configurations/plazma/world.md): aktivoi `no-chat-reports > require-install` sen toimimiseksi.**

{% endhint %}

***

[^1]: Operaattori.

[^2]: Esimerkiksi: `ender_dragon`
