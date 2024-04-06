---
description: Uurige, kuidas kohandada serverit kasutaja vajadustele vastavaks.
---

# 📶 발전하기

Plazmat kasutatakse ametliku serveriplatvormi asemel Mojang Studios'i ametliku serveriplatvormi asemel kasutamiseks, kuna see võimaldab tugevat **kasutaja kohandamist**.

Allpool on mitu viisi, kuidas Plazmat kohandada ja kasutada.

## Konfiguratsiooni muutmine <a href="#id-1" id="id-1"></a>

Plazma kasutaja kohandamise kõige põhilisem viis on konfiguratsiooni muutmine.

Plazma pakub võimsaid konfiguratsiooniseadeid alates mängumehhanismidest kuni olendite omadusteni.

Lisateavet Plazma konfiguratsioonide kohta leiate allolevast lehest.

{% content-ref url="../reference/configurations/" %}
[konfiguratsioonid](../reference/configurations/)
{% endcontent-ref %}

***

## Plugin'i kasutamine <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma toetab kõiki paberil põhinevaid pistikprogramme.**

Spigot pistikprogrammid võivad alates 1.20.5-st Paperi mäppimise muutuste tõttu osaliselt mitte toimida, kuid
Plazma toetab kõiki Paperil põhinevaid pistikprogramme, sealhulgas Paper, Pufferfish ja Purpur, ning kui pistikprogramm ei tööta korralikult, on see Plazma viga, nii et palun [teatage sellest kohe.](../diagnosis/plugins.md)

{% endhint %}

Plazma kasutamine on peamine põhjus ja tugevaim viis Plazmat kasutajate kohandamiseks.
Plazma tugev pistikprogrammide ökosüsteem võimaldab serverit hõlpsasti kohandada.

Pistikprogrammi leidmiseks ja allalaadimiseks on mitu võimalust. Mõned pistikprogrammid laaditakse üles avalikele hoidlateenustele ja mõned GitHubi või oma
veebisaitidele.

{% hint style="caution" %}

**Pistikprogrammidel võib olla otsest juurdepääsu süsteemile!**

Enne pistikprogrammi rakendamist kasutage teenust nagu VirusTotal, et veenduda selle turvalisuses või
laadige pistikprogramm alla usaldusväärsest teenusest.

{% endhint %}

Pistikprogrammi allalaadimiseks on mitu teenust. Nende hulgas on [SpigotMC foorum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/), kus pistikprogrammide üleslaadimisele eelneb hindamine ning ebaturvalised pistikprogrammid kõrvaldatakse, tagades turvaliste pistikprogrammide leviku.

### Pistikprogrammi rakendamine <a href="#id-2.1" id="id-2.1"></a>

Kui olete pistikprogrammi alla laadinud, on aeg see rakendada.

1. Pistikprogramm on `.jar` või `Java käivitatav fail`.\
   Mõned pistikprogrammid võivad olla arhiivifailidena pakitud, mil juhul
   tuleb arhiiv lahti pakkida ja kasutada faili, kus on nimi sisaldab `bukkit`, `spigot` või `paper`,
   ing kui failis on ka `fat`, siis tuleks kasutada `fat` faili.
2. Pange allalaaditud fail serveri kausta `plugins` ja (taas)käivitage server.
3. Kui Plazma käivitub, kuvatakse konsoolis uut sisu.
   See tähendab, et Plazma on pistikprogrammi edukalt laadinud.
4. Kuigi Plazma on pistikprogrammi edukalt laadinud, võib pistikprogramm mitte käivituda.
   Kasutades käsku `/plugins`, saate laadida serverisse hetkel laetud pistikprogrammid.
   Kui paigaldatud pistikprogrammi nimi pole <mark style="background-color:red;">punane</mark>, vaid <mark style="background-color:green;">roheline</mark>, on pistikprogramm edukalt laetud.

Kui pistikprogramm pole edukalt laadinud, leiate allpool lehelt probleemile lahenduse.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Andmepakettide kasutamine <a href="#id-3" id="id-3"></a>

Andmepaketid on Minecrafti poolt pakutav kasutajate kohandamise meetod, mis on sarnane
[resurssipakettidega](#user-content-fn-1)[^1].

Andmepakettide abil saate lisada uusi eluvorme ja väljakutseid ning muuta mängu sisemust.

{% hint style="caution" %}

**Andmepaketid võivad kahjustada maailma!**

Mõned vigased andmepaketid võivad maailma kahjustada ja see on pöördumatu.

Seetõttu on soovitatav enne andmepakettide rakendamist varundada maailm.

{% endhint %}

Andmepakette saab alla laadida mitmest teenusest, sealhulgas [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) ja mitmetest muudest teenustest.

Kui olete andmepaketi alla laadinud, saate selle rakendada serveri maailma kaustas `datapacks`.
Kui kausta pole, tuleb see luua ja lisada.

{% hint style="warning" %}

**[Mõned andmepaketid](#user-content-fn-2)[^2] võivad esmakordsel rakendamisel mitte õigesti rakenduda.**

Sellisel juhul soovitatakse server **2 korda** taaskäivitada.

{% endhint %}

Andmepaketid võivad iga Minecrafti versiooni värskendamisel kergesti kahjustuda.

Eriti kui andmepakett on täielikult kahjustunud, võib server kokku kukkuda,
seega on oluline enne serveri värskendamist läbi viia piisavalt teste.

{% hint style="info" %}

**Serveri käivitamise käsu järel saate sisestada `safeMode`, et kõik andmepaketid keelata ja seejärel server käivitada.**

[Lisateabe saamiseks vaadake `Viited > Argumendid ja atribuudid`](../reference/arguments.md#safeMode).

{% endhint %}

Rakendatud andmepakette saab kontrollida käsu `/datapack list` abil.

***

## Optimeerimine <a href="#id-4" id="id-4"></a>

Plazmas on rakendatud palju optimeerimisparandusi. Lisaks optimeerib Plazma alguses automaatselt
konfiguratsiooni, seega kui järgite [algusjuhendit](./README.md), pole täiendavat optimeerimist vaja.

Kuid kui palju mängijaid ühendab või kui maailm on suur,
siis saate järgida allpool toodud juhiseid täiendava optimeerimise jaoks.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proksia <a href="#id-5" id="id-5"></a>

Proksia ühendab servereid omavahel ja võimaldab mängijatel liikuda serverite vahel ilma täiendavate toiminguteta
ning suhelda teiste serveritega.

Turvalise ja õige proksia seadistuse kohta leiate lisateavet allpool toodud lehelt.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Turvalisus <a href="#id-5" id="id-5"></a>

Minecrafti modifikatsioonid on arenenud ja võrgus on lihtne leida [haavatavus ründemootorit](#user-content-fn-3)[^3].

Enamik mängudes käivitatavaid haavatavusi on [vaikimisi blokeeritud](#user-content-fn-4)[^4],
kuid haavatavuste ründamine kolmanda osapoole laadurite kaudu pole blokeeritud.

Seetõttu soovitatakse avalikult kättesaadavatel serveritel paigaldada anti-cheat pistikprogramm jne,
ette konfigureerida proksia ja automaatne taaskäivitamine, varundamine jne, et server saaks kiiresti taastuda ka siis, kui see kukub.

### Õiguste seadistamine <a href="#id-5.1" id="id-5.1"></a>

Mõne pistikprogrammi administraatori käskude puhul võib esineda haavatavusi, kui õigusi pole õigesti seadistatud.

Kasutage õiguste haldamise pistikprogrammi nagu [LuckPerms](https://luckperms.net/),
ette piirata tavaliste kasutajate õigusi.

### X-Ray blokeerimine <a href="#id-5.2" id="id-5.2"></a>

X-Ray on üks lihtsasti kasutatavaid haavatavusi isegi põhilises optimeerimiskliendis.

Plazmas on vaikimisi X-Ray blokeerimise konfiguratsioon.

X-Ray blokeerimise meetodid ja selgitused leiate allpool toodud lehelt.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Valge nimekirja <a href="#id-5.3" id="id-5.3"></a>

Kui soovite, et ainult mõned kasutajad saaksid serverisse ühendada,
siis soovitatakse kasutada [Ngrokki](./README.md#id-6.2) kasutades [krüptitud serveri aadressi](#user-content-fn-5)[^5] või
seadistada valge nimekiri, et teised mängijad ei saaks serverisse ühenduda.

Serveri konsoolist saate lubada mängija ühenduse `/whitelist add <player>` või
keelata mängija ühenduse `/whitelist remove <player>`.

Lubatud mängijate nägemiseks kasutage `/whitelist query` käsku.

***

[^1]: Või Minecrafti: Bedrock Editioni lisandmoodul.

[^2]: Lisades uusi eluvorme jms.

[^3]: Tavaliselt tuntakse seda "häkkimisena".

[^4]: Kui konfiguratsioon pole optimeeritud või kui Plazma on vananenud või kui on avastatud uusi haavatavusi, võib blokeering puududa.

[^5]: Mängijad ühenduvad serveriga Ngrok proksiserveri kaudu ja iga taaskäivitusega antakse välja erinev Ngrok aadress.
