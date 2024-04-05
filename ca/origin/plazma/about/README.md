---
description: Descobreix què és Plazma com a plataforma de servidor.
---

# ❓ Què és Plazma?

- **Plazma** és una plataforma de servidor basada en [Paper](https://github.com/PaperMC/Paper) que recull només els avantatges de [Andròmeda](https://github.com/EarendelArchived/Andromeda) i [Fusió](https://github.com/RuinedTechnologyUnify/Fusion).
- Estem treballant per proporcionar sempre una alta estabilitat, un rendiment potent, actualitzacions ràpides i una gran quantitat de funcions.

## 📋 Objectius de Plazma <a href="#id-1" id="id-1"></a>

- Estem treballant per convertir-nos en una plataforma de servidor amb actualitzacions ràpides i alta estabilitat.
- Estem treballant per oferir una gran quantitat de funcions i un rendiment potent, igual que una plataforma de mod.
- Estem treballant per crear una plataforma lliure on es pugui personalitzar fins i tot els parches de la vanília.

## ⚙️ Característiques principals <a href="#id-2" id="id-2"></a>

1. **Ecosistema de plugins potent**\
   Basat en [Paper](https://github.com/PaperMC/Paper), la majoria dels [plugins recents](#user-content-fn-1)[^1] disponibles a Internet funcionen correctament.
2. **Optimització sense necessitat de configuració**\
   Inclou totes les correccions de [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) i ofereix un rendiment òptim amb algunes optimitzacions internes i mods inclosos.
3. **Personalització del joc com vulguis**\
   [Purpur](https://github.com/PurpurMC/Purpur) inclòs a Plazma permet modificar els aspectes generals del joc.
4. **Servidor segur per jugar**\
   Incorpora [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) per desactivar el sistema de denúncies de xat introduït per Mojang[^2] a partir de la versió 1.19 i eliminar completament el recopilador d'informació de diagnòstic, permetent jugar en un servidor segur sense seguiment.
5. **Actualitzacions més ràpides**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) manté sempre actualitzades les correccions incloses a Plazma, oferint les actualitzacions més ràpides entre les plataformes de servidor basades en Paper.
6. **Optimització dels fitxers de configuració bàsics**\
   Els fitxers de configuració per defecte estan optimitzats, evitant la necessitat d'optimitzar-los manualment.
7. **Funcionament sistemàtic de múltiples fils**\
   Asincronitza els mecanismes del sistema que no estan relacionats amb els mecanismes del joc per optimitzar el servidor i reduir els temps de retard[^4].
8. **Bloqueig de l'ús d'espai innecessari**\
   Combina les dades amb valors similars en un de sol per reduir l'ús de memòria.

#### Vols saber més sobre Plazma? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Casos d'ús <a href="#id-3" id="id-3"></a>

- **Plataforma que gestiona correctament fins i tot els plugins complexes**\
  Plazma s'utilitza als servidors del desenvolupador [IPECTER](https://github.com/IPECTER). Amb plugins propis que funcionen amb NMS i reflexió, i amb una gran quantitat de paquets de dades complexos, és capaç de gestionar més de 100 jugadors sense cap pèrdua de rendiment.
- **Plataforma amb un rendiment ràpid també en servidors RPG**\
  Ha mantingut 100 jugadors en un sol clúster sense cap pèrdua de TPS i ha permès que un total de 250 jugadors juguin còmodament en 4 clústers diferents.
- **Plataforma que redueix els retards en els chunks/entitats**\
  Canviant de Purpur a Plazma en servidors de supervivència on hi havia retards en el tractament de chunks i entitats, s'ha aconseguit reduir significativament aquests retards.
- **Plataforma escollida per molts 'streamers'**\
  És utilitzada com a servidor de visualització per molts 'streamers' populars.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Tendència d'usuaris en temps real de Plazma</p></figcaption>
</figure>

## ⬇️ Descarregar

Pots descarregar Plazma des de la següent pàgina.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Vols més informació sobre les versions compatibles?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Plugins de Bukkit, CraftBukkit, Spigot i plugins de Paper, Pufferfish, Purpur.

[^2]: Propietat de Microsoft Corporation.

[^3]: En desactivar el sistema de denúncies de xat, el xat es processa únicament al servidor, evitant el seguiment del xat de Mojang.

[^4]: Temps en què el joc es deté temporalment perquè funcioni el mecanisme del sistema.
