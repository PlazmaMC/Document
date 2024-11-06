---
description: Selvitä Plazma-sovelluksen oikeudet.
---

# 🛡️ Oikeudet

Oikeudet ovat yksinkertainen turvallisuustyökalu, joka määrittää, millä tavalla palvelimen pelaajat voivat vuorovaikuttaa keskenään.

Oikeuksien asianmukaiseen käyttöön ja helpottamiseen tarvitaan lisäosia, kuten [LuckPerms](https://luckperms.net).

***

## Ymmärtääksesi perusoikeusjärjestelmää, katso <a href="#id-1" id="id-1"></a>

Minecraft tarjoaa perus hallintaoikeusryhmiä.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Pelaaja**\
   Yleinen oikeusryhmä, joka annetaan kaikille pelaajille.
2. **Välittäjä**\
   Voi ohittaa spawn-suojauksen.
3. **Maailmanhallitsija**\
   Voi käyttää kaikkia maailmanhallintaan liittyviä komentoja ja komentolohkoja.\
   Oletusarvoinen oikeusryhmä datapaketeille ja komentolohkoille.
4. **Hallinnoija**\
   Voi käyttää kaikkia pelaajien hallintaan liittyviä komentoja.
5. **Ylimmäinen hallinnoija**\
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

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Oletus**: `None`

Sallii pelaajan käyttää entiteetin erikoistaitoja, kun pelaaja ratsastaa entiteetillä.

Kaikki entiteetit eivät välttämättä voi käyttää erikoistaitoja. Kaikki käytettävissä olevat erikoistaidot löytyvät alla olevasta linkistä.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Tämä mahdollistaa suorituskyvyn parantamisen molemmilla osapuolilla.

> Katso X-Rayn asetukset alla olevasta linkistä.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Oletus**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Oletus**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Oletus**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Oletus**: `None`

Mahdollistaa MiniMessage-tunnisteiden käytön alasimissa [MiniMessage-tageilla](https://docs.advntr.dev/minimessage/format.html).

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Oletus**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Oletus**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Oletus**: `None`

Muuttaa enderarkun koon.

`(NumberString)` voi olla `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Oletus**: `None`

Sallii kuolemattomuuden toimivan, vaikka totemi olisi inventaariossa.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Oletus**: `None`

Sallii pelaajan ohittaa liittymisrajoituksen.

#### `purpur.mending_shift_click`

- **Oletus**: `None`

Sallii pelaajan korjata esineitä pitämällä niitä ja kyykistymällä.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Oletus**: `None`

Sallii pelaajan asentaa kohderyhmät.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Oletus**: `None`

Sallii pelaajan siirtyä heti Nether-portaalista.

#### `purpur.sign.color`

- **Oletus**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Oletus**: `None`

Sallii kylteissä käsittämättömän koodin `(&o)` käytön.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Oletus**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Oletus**: `None`

Sallii pelaajan estää TNT:n räjähdyksen vuorovaikutteisesti saksilla.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Suunnitellut oikeudet

#### `plazma.bypass.ncr-require`

- **Oletus**: `None`

Sallii pelaajan liittyä, vaikka [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) -moduulia ei olisi asennettu.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operaattori.

[^2]: Esimerkiksi: `ender_dragon`
