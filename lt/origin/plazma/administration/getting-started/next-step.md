---
description: Sužinokite, kaip pritaikyti serverį vartotojui.
---

# 📶 Plėtros etapas

Naudojant patobulintą serverio platformą, tokia kaip Plazma, o ne oficialią Mojang Studios teikiamą serverio platformą, pagrindinė priežastis yra galimybė labai stipriai **pritaikyti**.

Žemiau pateikiami keli būdai, kaip pritaikyti ir naudoti Plazmą.

## Konfigūracijos pakeitimas <a href="#id-1" id="id-1"></a>

Paprastiausias būdas pritaikyti Plazmą yra tiesiog pakeisti konfigūraciją.

Plazma teikia galimybę nustatyti stiprius konfigūracijos parametrus nuo žaidimo mechanikos iki būtybių savybių.

Daugiau informacijos apie Plazmos konfigūraciją rasite žemiau pateiktame puslapyje.

{% content-ref url="../reference/configurations/" %}
[konfigūracijos](../reference/configurations/)
{% endcontent-ref %}

***

## Įskiepiai <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma palaiko visus popieriaus pagrindu veikiančius įskiepius.**

Spigot įskiepiams, pradedant nuo 1.20.5, dėl Paper žemėlapio pasikeitimų kai kurie gali neveikti,
Tačiau dauguma įskiepių, kurie yra pagrįsti Paper, Pufferfish ar Purpur, veiks Plazmoje,
ir jei jie neveiks tinkamai, tai yra Plazmos klaida, todėl nedelsiant [praneškite apie tai.](../diagnosis/plugins.md)

{% endhint %}

Tai svarbiausias Plazmos naudojimo motyvas ir galingiausias būdas pritaikyti Plazmą vartotojui.
Plazmos galinga įskiepių ekosistema leidžia lengvai pritaikyti serverį vartotojui.

Yra keletas būdų rasti ir atsisiųsti įskiepius. Kai kurie įskiepiai
yra įkelti į viešą saugyklą ir kai kurie į GitHub ar savo
svetainę.

{% hint style="caution" %}

**Įskiepiai gali tiesiogiai prieiti prie sistemos!**

Prieš taikydami įskiepį, visada patikrinkite jo saugumą naudodami VirusTotal ar kitas paslaugas arba
atsisiųskite įskiepį iš patikimos paslaugos.

{% endhint %}

Yra keletas paslaugų, skirtų įskiepiams atsisiųsti. Iš jų, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) ir kt. paslaugos įskiepius vertina prieš įkeliant ir tik saugūs įskiepiai platinami.

### Taikyti įskiepį <a href="#id-2.1" id="id-2.1"></a>

Kai įskiepis atsisiųstas, dabar laikas jį taikyti.

1. Įskiepis yra `.jar` arba `Java vykdomasis failas`.\
   Kai kurie įskiepiai gali būti suspausti, tokiu atveju
   išpakuokite failą, kuriame yra `bukkit`, `spigot` ar `paper` pavadinime ir
   naudokite failą, kuriame yra `fat` kartu su kitais failais.
2. Įkeltą failą įkelkite į serverio `plugins` aplanką ir paleiskite (iš naujo) serverį.
3. Kai Plazma paleidžiama, konsolėje bus rodomas naujas turinys.
   Tai reiškia, kad Plazma sėkmingai įkėlė įskiepį.
4. Nors Plazma sėkmingai įkėlė įskiepį, gali būti, kad įskiepis nepradėjo veikti.
   Naudodami komandą `/plugins`, galite pamatyti įkeltus įskiepius serveryje.
   Jei įskiepis, kurį įkėlėte, nėra <mark style="background-color:red;">raudonas</mark>, o <mark style="background-color:green;">žalias</mark>, tai reiškia, kad įskiepis sėkmingai įkeltas.

Jei įskiepis nebuvo sėkmingai įkeltas, galite rasti problemos sprendimo būdus žemiau pateiktame puslapyje.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Duomenų paketo naudojimas <a href="#id-3" id="id-3"></a>

Duomenų paketas yra Minecraft pagrindinis vartotojo pritaikymo būdas, panašus į
[šaltinių paketus](#user-content-fn-1)[^1].

Naudojant duomenų paketą, galite redaguoti žaidimo dalis, pvz., pridėti naujų būtybių rūšių ir iššūkių.

{% hint style="caution" %}

**Duomenų paketas gali sugadinti pasaulį!**

Kai kurie sugadinti duomenų paketai gali sugadinti pasaulį ir tai negali būti atstatyta.

Dėl šios priežasties prieš taikydami duomenų paketą rekomenduojama atlikti pasaulio atsarginę kopiją.

{% endhint %}

Duomenų paketą galima atsisiųsti iš įvairių paslaugų, tokių kaip [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) ir kt.

Atsisiuntus duomenų paketą, jį galima pritaikyti įkeliant į serverio pasaulio aplanką `datapacks` aplanką.
Jei aplanko nėra, jį galima sukurti ir pridėti.

{% hint style="įspėjimas" %}

**[Kai kurie duomenų rinkiniai](#user-content-fn-2)[^2] gali neveikti tinkamai po pirmojo taikymo.**

Tokiu atveju rekomenduojama **2 kartus** paleisti serverį.

{% endhint %}

Duomenų paketai gali būti lengvai sugadinti kiekvieną kartą, kai atnaujinamas Minecraft versija.

Ypač, jei duomenų paketas yra visiškai sugadintas, serveris gali susidurti su sutrikimais,
todėl prieš atnaujinant serverį svarbu atlikti pakankamai testavimo.

{% hint style="info" %}

**Paleidus serverį, galima įvesti `safeMode` po serverio paleidimo komandos, kad išjungtumėte visus duomenų paketus ir tada paleisti serverį.**

Daugiau informacijos rasite `Nuorodose > Argumentai ir savybės` skyriuje.](../reference/arguments.md#safeMode)

{% endhint %}

Pritaikytus duomenų paketus galima patikrinti naudojant komandą `/datapack list`.

***

## Optimizavimas <a href="#id-4" id="id-4"></a>

Plazmoje taikyta daug optimizavimo patobulinimų. Be to, Plazmos pradžioje automatiškai optimizuojamas konfigūracijos failas, todėl, jei laikotės [Pradžios](./README.md) vadovo, papildomų optimizavimo veiksmų atlikti nereikia.

Tačiau jei prisijungia daug žaidėjų arba pasaulis yra labai didelis,
per šią instrukciją galite atlikti papildomus optimizavimo veiksmus.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Tarpininkas <a href="#id-5" id="id-5"></a>

Tarpininkas jungia serverius ir leidžia žaidėjams judėti tarp serverių be papildomo darbo arba bendrauti su kitais serveriais.

Daugiau informacijos apie saugų ir teisingą tarpininko nustatymą rasite žemiau pateiktame puslapyje.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Saugumas <a href="#id-5" id="id-5"></a>

Minecraft, besivystant modams, lengvai gali būti rasta internete ir naudojama [pažeidžiamųjų atakų variklių](#user-content-fn-3)[^3].

Nors dauguma pažeidžiamumų yra [pagrindiniu lygiu blokuoti](#user-content-fn-4)[^4] normaliuose žaidimuose,
naudojant trečiųjų šalių įkroviklį, pažeidžiamumų atakos nebus blokuojamos.

Todėl, jei serveris yra viešas, rekomenduojama diegti įvairius apsaugos įskiepius, tokius kaip Anti-Cheat, ir
konfigūruoti tarpininką bei automatinį paleidimą, atsarginį kopijavimą ir t.t., kad būtų galima greitai atkurti serverį, jei jis sugriūtų.

### Leidimų nustatymas <a href="#id-5.1" id="id-5.1"></a>

Kai kurių įskiepių administratoriaus komandos gali turėti pažeidžiamumų, jei leidimai nėra tinkamai nustatyti.

Rekomenduojama naudoti leidimų valdymo įskiepius, pvz., [LuckPerms](https://luckperms.net/),
kad būtų apriboti paprastų vartotojų leidimus.

### X-Ray blokavimas <a href="#id-5.2" id="id-5.2"></a>

X-Ray yra vienas iš pažeidžiamumų, kurį lengva naudoti net su pagrindiniu optimizavimo klientu.

Plazmoje yra konfigūracija, kuri pagrindiniu lygiu blokuoja X-Ray naudojimą.

X-Ray blokavimo būdas ir aprašymas pateikti žemiau pateiktame puslapyje.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Baltasis sąrašas <a href="#id-5.3" id="id-5.3"></a>

Jei norite, kad tik kai kurie vartotojai galėtų prisijungti prie serverio,
naudodami [Ngrok](./README.md#id-6.2) su [užšifruotu serverio adresu](#user-content-fn-5)[^5] arba
nustatydami baltąjį sąrašą, kad kiti žaidėjai negalėtų prisijungti prie serverio, tai taip pat yra rekomenduojama.

Serverio konsolėje naudodami `/whitelist add <žaidėjas>` galite leisti žaidėjui prisijungti arba,
`/whitelist remove <žaidėjas>` atšaukti žaidėjo prisijungimą.

Norėdami pamatyti, kokie žaidėjai yra įtraukti į baltąjį sąrašą, naudokite `/whitelist query`.

***

[^1]: Arba Minecraft: Bedrock Edition papildymai.

[^2]: Pridėti būtybių rūšis ir kt.

[^3]: Paprastai vadinamas „cheat“.

[^4]: Jei konfigūracija nėra optimizuota, Plazma yra sena arba yra naujų pažeidžiamumų, gali būti, kad blokavimas neveiks.

[^5]: Kai žaidėjas prisijungia prie serverio, jis prisijungia per Ngrok tarpinio serverio, o kiekvieno paleidimo metu skiriasi Ngrok adresas.
