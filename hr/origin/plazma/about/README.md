---
description: Saznajte više o platformi Plazma za poslužitelje.
---

# ❓ Što je Plazma?

- **Plazma** je server platforma temeljena na [Paper](https://github.com/PaperMC/Paper) koja samo uzima prednosti iz [Andromeda](https://github.com/EarendelArchived/Andromeda) i [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Uvijek se trudimo pružiti visoku stabilnost, snažne performanse, brze nadogradnje i obilje značajki.

## 📋 Ciljevi Plazme <a href="#id-1" id="id-1"></a>

- Trudimo se postati server platforma s brzim nadogradnjama i visokom stabilnošću.
- Trudimo se pružiti obilje značajki i snažne performanse poput platforme za modove.
- Trudimo se stvoriti slobodnu platformu koja omogućava prilagodbu i patcheve vanilije.

## ⚙️ Glavne značajke <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Najbrže nadogradnje**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) osigurava da zakrpe uključene u Plazmu uvijek budu ažurirane, pružajući tako najbrže nadogradnje među svim server platformama temeljenim na Paperu.
6. **Optimizirane osnovne konfiguracijske datoteke**\
   Osnovne konfiguracijske datoteke su optimizirane, stoga nije potrebno ručno optimizirati konfiguraciju.
7. **Sistematski rad višenitnosti**\
   Asinkronizirajući sustavski mehanizmi koji nisu povezani s mehanizmima igre smanjuju [vrijeme kašnjenja](#user-content-fn-4)[^4] kako bi optimizirali server.
8. **Sprječavanje nepotrebnog korištenja prostora**\
   Spaja sve podatke slične vrijednosti u jednu kako bi smanjio korištenje memorije.

## ✨ Primjeri korištenja <a href="#id-3" id="id-3"></a>

- **Platforma koja ispravno obrađuje složene dodatke**\
  Plazma se koristi na poslužitelju [IPECTER](https://github.com/IPECTER).\
  Vlastiti dodaci koji rade s NMS-om i refleksijom, veliki i složeni paketi podataka su obilno primijenjeni,\
  Bez smanjenja performansi može primiti više od 100 igrača.
- **Platforma koja održava brze performanse čak i na RPG poslužitelju**\
  U jednom klasteru održava stabilnih 100 igrača bez pada TPS-a,\
  Na 4 klastera ukupno 250 igrača moglo je ugodno igrati.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Mnogi streameri su odabrali platformu**\
  Koristi se kao kanta za gledateljsko sudjelovanje mnogih streamera.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Preuzimanje

Na donjoj stranici možete preuzeti Plazmu.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Želite li saznati više o podržanim verzijama?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot dodaci i Paper, Pufferfish, Purpur dodaci.

[^2]: Podržava Microsoft Corporation.

[^3]: Onemogućavanjem sustava za prijavu chata možete spriječiti praćenje chata od strane Mojanga.

[^4]: Vrijeme potrebno za rad sustava mehanizama kako bi se igra zaustavila na trenutak.
