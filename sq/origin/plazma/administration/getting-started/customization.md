---
description: Mësoni se si të personalizoni serverin.
---

# 🎨 Personalizimi i përdoruesit

Përdorimi i një platforme zyrtare serveri të ofruar nga Mojang Studios dhe jo përdorimi i një platforme serveri të modifikuar si Plazma është për shkak të mundësisë së **personalizimit** të fuqishëm që është më i rëndësishmi.

Këtu janë disa mënyra për të personalizuar dhe përdorur Plazma-n.

## Ndryshimi i konfigurimit <a href="#id-1" id="id-1"></a>

Mënyra më bazike për të personalizuar Plazma-n është duke ndryshuar konfigurimin.

Plazma ofron konfigurime të fuqishme që përfshijnë mekanizmat e lojës dhe cilësitë e skajeve.

Përshkrimi i konfigurimit të Plazma-s mund të gjendet në faqen e mëposhtme.

{% content-ref url="../reference/configurations/" %}
[konfigurimet](../reference/configurations/)
{% endcontent-ref %}

## Përdorimi i shtojcave <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma mbështet të gjitha shtojcat bazuar në letër të Hartës.**

Për shtojcat e Spigot, disa prej tyre mund të mos funksionojnë për shkak të ndryshimeve në hartën e Paper që filluan nga 1.20.5, por
shumica e shtojcave që bazohen në Paper si Paper, Pufferfish dhe Purpur funksionojnë në Plazma,
dhe nëse nuk funksionojnë siç duhet, kjo është faj i Plazma, kështu që ju lutemi [raportoni menjëherë.](../diagnosis/plugins.md)

{% endhint %}

Kjo është arsyeja kryesore pse të përdorni Plazma dhe mënyra më e fuqishme për të personalizuar Plazma-n.
Ekosistemi i fuqishëm i shtojcave të Plazma lejon përshtatjen e lehtë të serverit tuaj.

Ka disa mënyra për të gjetur dhe shkarkuar shtojcat. Disa shtojca
ngarkohen në shërbimet e ruajtjes publike të shtojcave, ndërsa disa të tjera ngarkohen në GitHub ose
faqet e tyre të internetit.

{% hint style="caution" %}

**Shtojcat mund të kenë qasje drejtpërdrejt në sistemin tuaj!**

Përdorni shërbimet si VirusTotal për të verifikuar sigurinë e shtojcave para se t'i aplikoni,
ose shkarkoni shtojcat nga shërbimet e besueshme.

{% endhint %}

Ka shumë shërbime për shkarkimin e shtojcave. Në mes tyre, shërbimet si [Forumi i SpigotMC](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) kontrollojnë shtojcat para se të ngarkohen, duke siguruar që vetëm shtojcat e sigurta qarkullojnë.

### Aplikimi i Shtojcave <a href="#id-2.1" id="id-2.1"></a>

Pas shkarkimit të shtojcave, tani është koha për t'i aplikuar ato.

1. Shtojcat janë në formatin `.jar` ose `Skedar Ekzekutues Java`.
   Disa shtojca janë të kompresuara në një dosje, në rast se
   dosja është e kompresuar, hapeni atë dhe nëse emri përmban `bukkit`, `spigot` ose `paper`,
   përdorni dosjen që përmban `fat`.
2. Vendosni dosjen e shkarkuar në dosjen `shtojcat` të serverit dhe (ri)nisni serverin.
3. Kur Plazma fillon, do të shihni përmbajtje të re në konsolë.
   Kjo tregon se Plazma ka ngarkuar shtojcat me sukses.
4. Edhe pse Plazma ka ngarkuar shtojcat me sukses, ato mund të mos fillojnë siç duhet.
   Përdorni komandën `/shtojcat` për të shfaqur shtojcat e ngarkuara aktualisht në server.
   Nëse emrat e shtojcave të instaluar nuk janë të
   ngjyrë <mark style="background-color:red;">kuqe</mark>,
   por <mark style="background-color:green;">jeshile</mark>, atëherë shtojcat janë ngarkuar me sukses.

Nëse shtojcat nuk janë ngarkuar me sukses, mund të gjeni zgjidhjet në faqen e mëposhtme.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Përdorimi i Pakove të të Dhënave <a href="#id-3" id="id-3"></a>

Pakot e të Dhënave janë një mënyrë e Minecraft për të personalizuar lojën, të ngjashme me
[Paketat e Burimeve](#user-content-fn-1)[^1].

Me pakot e të dhënave, mund të shtoni grupime të reja të krijesave dhe sfidave në lojë.

{% hint style="caution" %}

**Pakot e të dhënave mund të dëmtojnë botën!**

Disa pakove të dëmshme të të dhënave mund të shkaktojnë dëme të pakthyeshme në botë.

Prandaj, është e rekomandueshme të bëni një kopje rezervë të botës para se të aplikoni pakot e të dhënave.

{% endhint %}

Pakot e të dhënave mund të shkarkohen nga shumë shërbime si [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) etj.

Pas shkarkimit të pakove të të dhënave, vendosini ato në dosjen `datapacks` të botës së serverit tuaj.
Nëse dosja nuk ekziston, mund ta krijoni atë dhe ta shtoni.

{% hint style="warning" %}

**Në raste të caktuara, [pakot e të dhënave](#user-content-fn-2)[^2] mund të mos aplikohen me sukses në fillim.**

Për këto raste, rekomandohet që serveri të rifillojë **2 herë**.

{% endhint %}

Pakot e të dhënave mund të dëmtohen lehtë kur Minecraft-i përditësohet.

Veçanërisht, nëse pakot e të dhënave janë dëmtuar plotësisht, serveri mund të përplaset,
kështu që është e rëndësishme të kryeni testimet e mjaftueshme para se të përditësoni serverin.

{% hint style="info" %}

**Pas komandës së fillimit të serverit, mund të shtypni `safeMode` për të çaktivizuar të gjitha pakot e të dhënave dhe pastaj të rifillonit serverin.**

[Për më shumë informacion, shihni `Referencat > Argumentet dhe Pronat`.](../reference/arguments.md)

{% endhint %}

Pakot e aplikuar mund të verifikohen duke përdorur komandën `/datapack list`.

***

[^1]: Ose edhe Shtojcat e Minecraft: Bedrock Edition.

[^2]: Shtimi i grupimeve të krijesave etj.
