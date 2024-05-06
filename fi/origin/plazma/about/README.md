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
   [Paper](https://github.com/PaperMC/Paper)-pohjainen, joten suurin osa internetistä ladattavissa olevista [uusimmista lisäosista](#user-content-fn-1)[^1] toimii moitteettomasti.
2. **Ei tarvetta säädöille, optimoitu valmiiksi**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sisältää kaikki patchit ja tarjoaa joitakin sisäisiä optimointeja ja tilat, jotka takaavat parhaan suorituskyvyn.
3. **Pelaa haluamallasi tavalla**\
   [Plazma](https://github.com/PurpurMC/Purpur) sisältää Purpurin, joka mahdollistaa pelin yleisten ominaisuuksien muokkaamisen haluamallasi tavalla.
4. **Turvallinen pelipalvelin**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) on sisällytetty lisäyksenä 1.19 alkaen
   [Mojang](#user-content-fn-2)[^2] [Chat-ilmoitusjärjestelmä](#user-content-fn-3)[^3] voidaan poistaa käytöstä,\
   ja diagnostiikkatietojen kerääjä on täysin poistettu, jotta voit pelata turvallisesti jäljittämättömällä palvelimella.
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

- **Monimutkainen lisäosa-alusta**\
  Kehittäjä [IPECTER](https://github.com/IPECTER) käyttää Plazmaa palvelimellaan.\
  Oma lisäosa, joka toimii NMS:llä ja heijastuksella, sekä laaja ja monimutkainen datapaketti on laajasti käytössä,\
  ja se pystyy vastaanottamaan yli 100 pelaajaa ilman suorituskyvyn laskua.
- **RPG-palvelimella ylläpidetty nopea suorituskykyalusta**\
  Yksi klusteri pystyi pitämään 100 pelaajaa vakaina ilman TPS-laskua,\
  ja neljässä klusterissa yhteensä 250 pelaajaa pystyi pelaamaan mukavasti.
- **Valoa näyttävä alusta palasissa/olioissa**\
  Purpurin sijaan Plazmaan vaihtamalla voitiin vähentää suurinta osaa viivästyksistä
  joita aiheutui selviytymispalvelimen palasien ja olioiden käsittelystä.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 참여용 버킷으로 선택받아 사용되고 있습니다.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Tilastotietoja Plazma-käyttäjistä reaaliajassa">
</a>

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
