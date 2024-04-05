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

1. **Snažan ekosustav dodataka**\
   Zbog temelja na [Paper](https://github.com/PaperMC/Paper), većina [najnovijih dodataka](#user-content-fn-1)[^1] dostupnih na internetu normalno funkcionira.
2. **Optimizacija bez potrebe za postavljanjem**\
   Uključuje sve zakrpe [Pufferfish](https://github.com/pufferfish-gg) i pruža najbolje performanse s nekim internim optimizacijama i ugrađenim modovima.
3. **Igrajte igru po vlastitim pravilima**\
   [Purpur](https://github.com/PurpurMC/Purpur) koji dolazi s Plazmom omogućuje izmjenu općih svojstava igre.
4. **Siguran server za igranje**\
   Uključuje [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) koji omogućuje onemogućavanje dodanog Mojang[^2] [sustava za prijavu chata](#user-content-fn-3)[^3] od 1.19, kao i potpuno uklanjanje dijagnostičkog alata za sigurno igranje na serveru bez praćenja.
5. **Najbrže nadogradnje**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) osigurava da zakrpe uključene u Plazmu uvijek budu ažurirane, pružajući tako najbrže nadogradnje među svim server platformama temeljenim na Paperu.
6. **Optimizirane osnovne konfiguracijske datoteke**\
   Osnovne konfiguracijske datoteke su optimizirane, stoga nije potrebno ručno optimizirati konfiguraciju.
7. **Sistematski rad višenitnosti**\
   Asinkronizirajući sustavski mehanizmi koji nisu povezani s mehanizmima igre smanjuju [vrijeme kašnjenja](#user-content-fn-4)[^4] kako bi optimizirali server.
8. **Sprječavanje nepotrebnog korištenja prostora**\
   Spaja sve podatke slične vrijednosti u jednu kako bi smanjio korištenje memorije.

#### Želite li saznati više o Plazmi? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Primjeri korištenja <a href="#id-3" id="id-3"></a>

- **Platforma koja ispravno obrađuje složene dodatke**\
  Plazma se koristi na serveru razvojnog programera [IPECTER](https://github.com/IPECTER). Iako se koristi vlastiti dodatak koji radi s NMS-om i refleksijom, te ima veliku količinu podataka, Plazma uspješno podržava više od 100 igrača bez gubitka performansi.
- **Platforma koja održava brze performanse čak i na RPG serverima**\
  Na jednom klasteru uspješno je održavao 100 igrača bez pada TPS-a, dok je na 4 klastera omogućio ugodno igranje za ukupno 250 igrača.
- **Platforma koja pokazuje svjetlo u chunkovima/entitetima**\
  Prelaskom s Purpura na Plazmu na serveru preživljavanja smanjili smo većinu kašnjenja u obradi chunkova i entiteta.
- **Platforma koju je odabrao mnogi streameri**\
  Koristi se kao glavni bucket za gledatelje mnogih popularnih streamera.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>실시간 Plazma 사용자 추이</p></figcaption>
</figure>

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
