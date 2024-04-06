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

1. **Un ecosistema de plugins potent**\
   [Paper](https://github.com/PaperMC/Paper) es basa en,
   la majoria dels [plugins més recents](#user-content-fn-1)[^1] disponibles a internet funcionen correctament.
2. **Optimització sense necessitat de configuració**\
   Totes les correccions de [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) estan incloses,
   amb algunes optimitzacions internes i modes integrats per oferir el millor rendiment.
3. **Personalitza el joc com vulguis**\
   [Purpur](https://github.com/PurpurMC/Purpur) inclòs a Plazma permet modificar
   els atributs generals del joc a la teva manera.
4. **Servidor que juga de manera segura**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) està inclòs des de la versió 1.19
   de [Mojang](#user-content-fn-2)[^2] per desactivar el [sistema de denúncia de xat](#user-content-fn-3)[^3],\
   i eliminar completament el recopilador d'informació de diagnosi per poder jugar en un servidor segur sense rastreig.
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

- **Plataforma que gestiona fins i tot els plugins més complexos de manera adequada**\
  El servidor de l'IPECTER utilitza Plazma.\
  Amb plugins propis que funcionen amb NMS i reflexió, i una gran quantitat de paquets de dades complexos aplicats,\
  és capaç de suportar més de 100 jugadors sense cap descens de rendiment.
- **Plataforma que manté un rendiment ràpid fins i tot en servidors RPG**\
  Ha mantingut 100 jugadors en un sol clúster sense cap descens de TPS de manera estable,\
  i ha permès a 250 jugadors jugar còmodament en 4 clústers.
- **Plataforma que mostra llum des dels chunks/entitats**\
  Canviant de Purpur a Plazma en el servidor de supervivència on hi havia retard en el processament de chunks i entitats,
  ha pogut reduir la majoria dels retards.
- **Plataforma escollida per molts streamers**\
  És utilitzada com a servidor per molts espectadors de molts streamers.

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
