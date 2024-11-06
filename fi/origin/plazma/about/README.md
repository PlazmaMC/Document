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

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Nopeimmat päivitykset**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) pitää Plazman mukana olevat patchit aina ajan tasalla, tarjoten nopeimmat päivitykset Paper-pohjaisista palvelin-alustoista.
6. **Perusmääritystiedoston optimointi**\
   Oletusarvoisesti mukana oleva määritystiedosto on optimoitu, joten sinun ei tarvitse optimoida sitä itse.
7. **Järjestelmällisesti toimiva monisäie**\
   Pelimekaniikkaan liittymättömät järjestelmämekanismit on asynkronisoitu vähentäen [viiveaikaa](#user-content-fn-4)[^4] ja optimoiden palvelimen toimintaa.
8. **Tarpeettoman tilan estäminen**\
   Samankaltaiset arvot on yhdistetty yhdeksi vähentäen muistin käyttöä.

## ✨ Käyttötarkoitukset <a href="#id-3" id="id-3"></a>

- **Monimutkainen lisäosa-alusta**\
  Kehittäjä [IPECTER](https://github.com/IPECTER) käyttää Plazmaa palvelimellaan.\
  Oma lisäosa, joka toimii NMS:llä ja heijastuksella, sekä laaja ja monimutkainen datapaketti on laajasti käytössä,\
  ja se pystyy vastaanottamaan yli 100 pelaajaa ilman suorituskyvyn laskua.
- **RPG-palvelimella ylläpidetty nopea suorituskykyalusta**\
  Yksi klusteri pystyi pitämään 100 pelaajaa vakaina ilman TPS-laskua,\
  ja neljässä klusterissa yhteensä 250 pelaajaa pystyi pelaamaan mukavasti.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Monet suoratoistolähetyksiä tekevät ovat valinneet alustan**\
  Monet suoratoistolähetyksiä tekevät ovat valinneet ja käyttävät sitä katsojien osallistumiskorina.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

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
