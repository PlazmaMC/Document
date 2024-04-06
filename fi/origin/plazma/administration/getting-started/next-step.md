---
description: Opi muokkaamaan palvelinta käyttäjän tarpeiden mukaan.
---

# 📶 Kehittyä

Käyttäessäsi muokattua palvelin-alustaa kuten Plazmaa, et käytä Mojang Studiosin virallista palvelin-alustaa. Tämä johtuu siitä, että voit tehdä erittäin vahvaa **käyttäjäkohtaistamista**.

Alla on useita tapoja muokata ja hyödyntää Plazmaa.

## Rakenne muokkaus <a href="#id-1" id="id-1"></a>

Perus tapa käyttäjäkohtaistaa Plazma on muokata rakennetta.

Plazma tarjoaa vahvoja asetusmahdollisuuksia pelin mekaniikoista hirviöiden ominaisuuksiin.

Katso lisätietoja Plazman rakenteesta alla olevasta linkistä.

{% content-ref url="../reference/configurations/" %}
[asetukset](../reference/configurations/)
{% endcontent-ref %}

***

## Liitännäisten käyttö <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma tukee kaikkia Paper-pohjaisia laajennuksia.**

Spigot-laajennusten osalta 1.20.5:stä alkaen Paperin määritysmuutosten vuoksi jotkut eivät ehkä toimi, mutta Plazman avulla
useimmat Paperiin perustuvat laajennukset, kuten Paper, Pufferfish ja Purpur, toimivat myös Plazmassa
ja jos ne eivät toimi oikein, se johtuu Plazman virheestä, joten [ilmoita siitä välittömästi.](../diagnosis/plugins.md)

{% endhint %}

Plazman käyttöä ja personointia varten tämä on tärkein syy ja tehokkain tapa.
Plazman vahva laajennusyhteisö mahdollistaa palvelimen helpon personoinnin.

Laajennuksen etsimiseen ja lataamiseen on useita tapoja. Jotkut laajennukset ladataan
julkiseen varastopalveluun ja jotkut ladataan GitHubiin tai omaan
verkkosivustoon.

{% hint style="caution" %}

**Laajennus voi käyttää järjestelmää suoraan!**

Käytä aina VirusTotalin kaltaisia palveluita varmistaaksesi, että laajennus on turvallinen ennen sen käyttöönottoa
tai lataa laajennus luotettavasta palvelusta.

{% endhint %}

Laajennuksen lataamiseen on useita palveluita. Näistä [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) ja muut palvelut käyvät läpi laajennukset ennen niiden julkaisua varmistaakseen, että vain turvalliset laajennukset jaetaan.

### Laajennuksen soveltaminen <a href="#id-2.1" id="id-2.1"></a>

Kun olet ladannut laajennuksen, on aika soveltaa sitä.

1. Laajennus on `.jar`-tai `Java-suoritettava tiedosto`.\
   Jotkut laajennukset ovat pakattuina, joten
   purkaessasi huomioi tiedostonimessä olevat `bukkit`, `spigot` tai `paper` sekä
   `fat`-tiedoston, jos sellainen on, käytä sitä.
2. Siirrä ladattu tiedosto palvelimen `plugins`-kansioon ja käynnistä palvelin uudelleen.
3. Kun Plazma käynnistyy, konsoliin ilmestyy uutta sisältöä.
   Tämä tarkoittaa, että Plazma on ladannut laajennuksen onnistuneesti.
4. Vaikka Plazma on ladannut laajennuksen onnistuneesti, se ei välttämättä ole käynnistänyt sitä.
   Käyttämällä komentoa `/plugins` voit tarkistaa ladatut laajennukset palvelimella.
   Jos asennettu laajennus ei ole <mark style="background-color:red;">punainen</mark>
   vaan <mark style="background-color:green;">vihreä</mark>, se on ladattu onnistuneesti.

Jos laajennus ei ole ladattu onnistuneesti, voit löytää ratkaisun ongelmaan alla olevasta linkistä.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Data packien käyttö <a href="#id-3" id="id-3"></a>

Data packit ovat Minecraftin tarjoamia käyttäjämuokkauksen tapoja, jotka ovat samankaltaisia kuin
[resurssipaketit](#user-content-fn-1)[^1].

Data packien avulla voit muokata pelin sisäisiä osia, kuten lisätä uusia olentoja ja haasteita.

{% hint style="caution" %}

**Data packit voivat vahingoittaa maailmaa!**

Jotkut vialliset data packit voivat vahingoittaa maailmaa peruuttamattomasti.

Siksi ennen data packin soveltamista on suositeltavaa varmuuskopioida maailma.

{% endhint %}

Data packit ovat saatavilla useista palveluista, kuten [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) ja muut.

Kun olet ladannut data packin, voit soveltaa sitä lisäämällä sen palvelimen maailman `datapacks`-kansioon.
Jos kansiota ei ole, voit luoda sen ja lisätä data packin sinne.

{% hint style="warning" %}

**Joissakin [data pack](#user-content-fn-2)[^2] -tapauksissa ensimmäinen sovellus voi olla epäonnistunut.**

Tässä tapauksessa suositellaan palvelimen **2 kertaa** uudelleenkäynnistämistä.

{% endhint %}

Data packit voivat helposti vahingoittua, kun Minecraft päivitetään uuteen versioon.

Erityisesti jos data pack on täysin vioittunut, se voi aiheuttaa palvelimen kaatumisen,
joten ennen päivitystä on tärkeää tehdä riittävästi testejä.

{% vinkki tyyli="info" %}

**Voit syöttää `safeMode` palvelimen käynnistyskomentoon poistaaksesi kaikki data packit käytöstä.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safemode)

{% endhint %}

Sovellatut data packit voit tarkistaa komennolla `/datapack list`.

***

## Optimointi <a href="#id-4" id="id-4"></a>

Plazmassa on paljon optimointipäivityksiä. 또한, Plazma가 처음으로 시작되면 자동으로
구성을 최적화 하므로 [시작하기](./README.md) 설명서를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우,
아래 설명서를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Välityspalvelin <a href="#id-5" id="id-5"></a>

Välityspalvelin yhdistää palvelimet toisiinsa ja mahdollistaa pelaajien siirtymisen palvelimelta toiselle ilman lisätoimenpiteitä sekä kommunikoinnin muiden palvelimien kanssa.

Katso turvalliset ja oikeat välityspalvelinasetukset alla olevasta sivusta.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Turvallisuus <a href="#id-5" id="id-5"></a>

Minecraftin kehittyessä verkossa on helppo saada [haavoittuvuushyökkäysmoottori](#user-content-fn-3)[^3].

Vaikka useimmat haavoittuvuudet ovat [oletuksena estettyjä](#user-content-fn-4)[^4] normaaleissa peleissä,
haavoittuvuuksien hyökkääminen kolmannen osapuolen latausohjelmien kautta ei ole estetty.

Siksi jos palvelin on julkisesti saatavilla, suositellaan asentamaan huijaustenesto-ohjelmistoja ja muita suojausohjelmistoja estämään haavoittuvuuksien käyttöä ja
määrittämään välityspalvelin, automaattinen käynnistys ja varmuuskopiointi varmistamaan, että palvelin voidaan palauttaa nopeasti, jos se kaatuu.

### Käyttöoikeudet <a href="#id-5.1" id="id-5.1"></a>

Joissakin lisäosien hallintakomennoissa voi olla haavoittuvuuksia, jos käyttöoikeudet eivät ole oikein määritetty.

Käytä käyttöoikeuksien hallintalaitteita, kuten [LuckPerms](https://luckperms.net/), rajoittaaksesi normaalien käyttäjien oikeuksia.

### X-Ray-esto <a href="#id-5.2" id="id-5.2"></a>

X-Ray on yksi helpoimmin käytettävissä olevista haavoittuvuuksista perusoptimointi asiakkaissa.

Plazmassa on oletusarvoisesti X-Rayn estämiseen tarvittava rakenne.

Katso X-Ray-eston menetelmät ja selitykset alla olevasta sivusta.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

Jos haluat, että vain tietyt käyttäjät voivat liittyä palvelimeen, käytä [Ngrokia](./README.md#id-6.2) käyttäen [salattua palvelinosoitetta](#user-content-fn-5)[^5] tai määritä whitelist estääksesi muita pelaajia liittymästä.

Voit sallia pelaajan liittymisen palvelimeen käyttämällä `/whitelist add <pelaaja>` tai
kieltää pelaajan liittymisen uudelleen käyttämällä `/whitelist remove <pelaaja>`.

Käytä `/whitelist query` nähdäksesi sallitut pelaajat.

***

[^1]: Tai Minecraft: Bedrock Editionin lisäosat.

[^2]: Kuten uusia olentoja.

[^3]: Yleisesti tunnetaan "hakkeroinnista".

[^4]: Jos asetukset eivät ole optimaaliset, Plazma on vanhentunut tai uusia haavoittuvuuksia on löydetty, ne eivät välttämättä ole estettyjä.

[^5]: Pelaajat liittyvät palvelimeen Ngrok-välityspalvelimen kautta, ja jokaisen uudelleenkäynnistyksen yhteydessä annettu Ngrok-osoite vaihtelee.
