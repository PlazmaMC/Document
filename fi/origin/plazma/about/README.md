---
description: Tutustu siihen, mikä Plazma-palvelin alusta on.
---

# ❓ Mikä on Plazma?

- **Plazma** on [Andromedan](https://github.com/EarendelArchived/Andromeda) ja [Fusionin](https://github.com/RuinedTechnologyUnify/Fusion) vahvuuksia yhdistävä [Paper](https://github.com/PaperMC/Paper)-pohjainen palvelin-alusta.
- Pyrimme tarjoamaan aina korkean vakauden ja tehokkaan suorituskyvyn, nopeat päivitykset sekä laajan valikoiman ominaisuuksia.

## 📋 Plazman tavoitteet <a href="#id-1" id="id-1"></a>

- Pyrimme olemaan palvelin-alusta, jolla on nopeat päivitykset ja korkea vakaus.
- Pyrimme tarjoamaan laajan valikoiman ominaisuuksia ja tehokasta suorituskykyä, joka ei häviä modi-alustoille.
- Pyrimme luomaan vapaan alustan, jolla voi muokata Vanilla-päivityksiä haluamallaan tavalla.

## ⚙️ Tärkeimmät ominaisuudet <a href="#id-2" id="id-2"></a>

1. **Vahva lisäosien ekosysteemi**\
   Perustuu [Paperiin](https://github.com/PaperMC/Paper), joten suurin osa internetistä ladattavissa olevista [uusimmista lisäosista](#user-content-fn-1)[^1] toimii normaalisti.
2. **Optimoitu ilman asetuksia**\
   Sisältää kaikki [Pufferfishin](https://github.com/pufferfish-gg/Pufferfish) patchit ja tarjoaa parhaan suorituskyvyn sisäänrakennetuilla optimoinneilla ja modeilla.
3. **Muokkaa peliä haluamallasi tavalla**\
   Sisältää [Purpurin](https://github.com/PurpurMC/Purpur), joka mahdollistaa pelin yleisten ominaisuuksien muokkaamisen.
4. **Turvallinen pelipalvelin**\
   Sisältää [Ei Chat Ilmoituksia](https://github.com/Aizistral-Studios/No-Chat-Reports), jonka avulla voit poistaa käytöstä Mojangin[^2] 1.19:stä lähtien lisätyn [chat-ilmoitusjärjestelmän](#user-content-fn-3)[^3] ja poistaa täysin diagnostiikkatietojen keräämisen, jotta voit pelata turvallisesti jäljittämättömällä palvelimella.
5. **Nopeimmat päivitykset**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) pitää Plazman mukana olevat patchit aina ajan tasalla, tarjoten nopeimmat päivitykset Paper-pohjaisista palvelin-alustoista.
6. **Perusmääritystiedoston optimointi**\
   Oletusarvoisesti mukana oleva määritystiedosto on optimoitu, joten sinun ei tarvitse optimoida sitä itse.
7. **Järjestelmällisesti toimiva monisäie**\
   Pelimekaniikkaan liittymättömät järjestelmämekanismit on asynkronisoitu vähentäen [viiveaikaa](#user-content-fn-4)[^4] ja optimoiden palvelimen toimintaa.
8. **Tarpeettoman tilan estäminen**\
   Samankaltaiset arvot on yhdistetty yhdeksi vähentäen muistin käyttöä.

#### Haluatko tietää lisää Plazmasta? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Käyttötarkoitukset <a href="#id-3" id="id-3"></a>

- **Käsittelee oikein monimutkaiset lisäosat**\
  Kehittäjä [IPECTER](https://github.com/IPECTER) käyttää Plazmaa palvelimellaan. Itse kehitetyt lisäosat, jotka toimivat NMS:llä ja heijastuksella, sekä suuri ja monimutkainen datapaketti, joka on käytössä,
  vastaanottaa yli 100 pelaajaa ilman suorituskyvyn laskua.
- **Ylläpitää nopeaa suorituskykyä RPG-palvelimilla**\
  Ylläpiti 100 pelaajan klusterissa TPS-laskua ilman vakautta ja mahdollisti yhteensä 250 pelaajan pelaamisen 4 klusterissa mukavasti.
- **Näyttää valoa chunk/entityissä**\
  Muutimme Purpurista Plazmaan selviytyäksemme selviytymispalvelimen viiveistä,
  ja pystyimme vähentämään suurinta osaa viiveistä.
- **Monet suoratoistajat valitsevat alustan**\
  Monet suositut suoratoistajat käyttävät Plazmaa katsojiensa virranhallintaan.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Reaaliaikainen Plazma käyttäjien kehitys</p></figcaption>
</figure>

## ⬇️ Lataa

Voit ladata Plazman alla olevasta sivulta.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Haluatko tietää lisää tukemistamme versioista?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot lisäosat ja Paper, Pufferfish, Purpur lisäosat.

[^2]: Toimii Microsoft Corporation.

[^3]: Poistamalla chat-ilmoitusjärjestelmän voit käsitellä chat-viestejä vain palvelimella estäen Mojangin chatin seurannan.

[^4]: Järjestelmämekanismin toiminnan vuoksi peli saattaa pysähtyä hetkeksi.
