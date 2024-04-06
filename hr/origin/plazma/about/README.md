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
   [Paper](https://github.com/PaperMC/Paper) temelji se na njemu,
   Većina [najnovijih dodataka](#user-content-fn-1)[^1] dostupnih na internetu ispravno funkcionira.
2. **Optimizacija bez potrebe za postavljanjem**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) sadrži sve zakrpe,
   Ugrađene su neke vlastite optimizacije i modovi koji pružaju vrhunske performanse.
3. **Igra prilagođena vašim željama**\
   [Purpur](https://github.com/PurpurMC/Purpur) koji dolazi s Plazmom omogućuje
   uređivanje općih svojstava igre.
4. **Siguran poslužitelj za igranje**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) je uključen kako bi se omogućilo onemogućavanje
   [Mojang](#user-content-fn-2)[^2]ovog [sustava prijave u chatu](#user-content-fn-3)[^3] dodanog od 1.19,\
   Sakupljač dijagnostičkih podataka je potpuno uklonjen kako biste mogli igrati na siguran poslužitelj bez praćenja.
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
  Plazma se koristi na poslužitelju [IPECTER](https://github.com/IPECTER).\
  Vlastiti dodaci koji rade s NMS-om i refleksijom, veliki i složeni paketi podataka su obilno primijenjeni,\
  Bez smanjenja performansi može primiti više od 100 igrača.
- **Platforma koja održava brze performanse čak i na RPG poslužitelju**\
  U jednom klasteru održava stabilnih 100 igrača bez pada TPS-a,\
  Na 4 klastera ukupno 250 igrača moglo je ugodno igrati.
- **Platforma koja pokazuje svjetlost u čunkovima/entitetima**\
  Promjenom s Purpura na Plazmu za platformu prethodno opterećenog poslužitelja preživljavanja
  Mogli smo smanjiti većinu kašnjenja.
- **Platforma koju mnogi streameri odabiru**\
  Koristi se kao glavna verzija za gledatelje mnogih streamera.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Stvarni trendovi korisnika Plazme u realnom vremenu</p></figcaption>
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
