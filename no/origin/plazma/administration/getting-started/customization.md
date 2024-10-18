---
description: Lær hvordan du tilpasser serveren.
---

# 🎨 Tilpasning

Årsaken til å bruke en tilpasset serverplattform som Plazma i stedet for den offisielle serverplattformen fra Mojang Studios er at det gir mulighet for kraftig **tilpasning**.

Her er flere måter å tilpasse og bruke Plazma på.

## Konfigurasjonsendringer <a href="#id-1" id="id-1"></a>

Den mest grunnleggende måten å tilpasse Plazma på er å endre konfigurasjonen.

Plazma tilbyr kraftige konfigurasjonsinnstillinger fra spillmekanikker til egenskaper for mobber.

Se nedenfor for en forklaring av Plazmas konfigurasjon.

{% content-ref url="../reference/configurations/" %}
[konfigurasjoner](../reference/configurations/)
{% endcontent-ref %}

## Bruk av tillegg <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma støtter alle pluginer basert på Paper fullt ut.**

For Spigot-plugins kan det hende at noen ikke fungerer på grunn av endringer i kartleggingen fra Paper 1.20.5, men de fleste pluginer basert på Paper, Pufferfish og Purpur fungerer også på Plazma. Hvis de ikke fungerer som de skal, er det en feil med Plazma, så vennligst [meld fra umiddelbart.](../diagnosis/plugins.md)

{% endhint %}

Dette er hovedgrunnen til å bruke Plazma og den kraftigste måten å tilpasse Plazma på for brukerne.
Plazmas sterke plugin-økosystem gjør det enkelt å tilpasse serveren.

Det er flere måter å finne og laste ned pluginer på. Noen pluginer lastes opp til offentlige lagringstjenester, mens andre lastes opp på GitHub eller egne nettsteder.

{% hint style="caution" %}

**Pluginer kan få direkte tilgang til systemet ditt!**

Bruk tjenester som VirusTotal for å alltid sjekke om en plugin er trygg å bruke før du installerer den, eller last ned pluginer fra pålitelige tjenester.

{% endhint %}

Det er flere tjenester som brukes til nedlasting av pluginer. Blant disse, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) og andre tjenester krever godkjenning før pluginer lastes opp for å sikre at bare trygge pluginer distribueres.

### Anvendelse av pluginer <a href="#id-2.1" id="id-2.1"></a>

Når du har lastet ned en plugin, er det på tide å bruke den.

1. Pluginer er i form av `.jar`-filer eller `Java Executable File`. Noen pluginer kan være komprimert, og i så fall må du pakke ut filen. Hvis filen inneholder `bukkit`, `spigot` eller `paper` i navnet, og det er en fil med `fat`, må du bruke `fat`-filen.
2. Legg den nedlastede filen i mappen 'plugins' i servermappen og start (på nytt) serveren.
3. Når Plazma starter, vil det vises ny informasjon på konsollen.
   Dette betyr at Plazma har lastet inn pluginene riktig.
4. Selv om Plazma har lastet inn pluginene riktig, kan det hende at de ikke starter.
   Du kan bruke kommandoen `/plugins` for å se hvilke pluginer som er lastet inn på serveren.
   Hvis navnet på en installert plugin ikke er <mark style="background-color:red;">rødt</mark>, men <mark style="background-color:green;">grønt</mark>, betyr det at pluginet er lastet inn riktig.

Hvis en plugin ikke lastes inn riktig, kan du finne løsninger på problemet på følgende side.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Bruk av datapakker <a href="#id-3" id="id-3"></a>

Datapakker er en måte å tilpasse Minecraft på, lignende ressurspakker.

Med datapakker kan du legge til nye skapninger og utfordringer i spillet.

{% hint style="caution" %}

**Datapakker kan skade verdener!**

Noen feilaktige datapakker kan skade verdener irreversibelt.

Derfor anbefales det å ta sikkerhetskopi av verdener før du bruker datapakker.

{% endhint %}

Datapakker kan lastes ned fra ulike tjenester som [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) og andre tjenester.

Når du har lastet ned en datapakke, kan du legge den til i mappen 'datapacks' i serverens verden.
Hvis mappen ikke finnes, kan du opprette den selv.

{% hint style="warning" %}

**Noen [datapakker](#user-content-fn-2) fungerer kanskje ikke riktig ved første påføring.**

I slike tilfeller anbefales det å starte serveren **2 ganger** for å sikre riktig påføring.

{% endhint %}

Datapakker kan lett bli ødelagt når Minecraft oppdateres.

Spesielt når datapakker er fullstendig ødelagt, kan serveren krasje, så det er viktig å teste grundig før du oppdaterer serveren.

{% hint style="info" %}

**Etter serverstartkommandoen kan du skrive `safeMode` for å deaktivere alle datapakker før du starter serveren på nytt.**

[Se 'Referanse > Argumenter og egenskaper' for mer informasjon.](../reference/arguments.md)

{% endhint %}

Du kan bekrefte at datapakkene er lagt til ved å bruke kommandoen `/datapack list`.

***

[^1]: Eller Minecraft: Bedrock Editions tillegg.

[^2]: Legg til nye skapninger osv.
