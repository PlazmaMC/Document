---
description: Lær hvordan du tilpasser serveren.
---

# 📶 Utviklingsfase

Årsaken til å bruke en tilpasset serverplattform som Plazma i stedet for den offisielle serverplattformen fra Mojang Studios er at det gir mulighet for kraftig **tilpasning**.

Her er flere måter å tilpasse og bruke Plazma på.

## Konfigurasjonsendringer <a href="#id-1" id="id-1"></a>

Den mest grunnleggende måten å tilpasse Plazma på er å endre konfigurasjonen.

Plazma tilbyr kraftige konfigurasjonsinnstillinger fra spillmekanikker til egenskaper for mobber.

Se nedenfor for en forklaring av Plazmas konfigurasjon.

{% content-ref url="../reference/configurations/" %}
[konfigurasjoner](../reference/configurations/)
{% endcontent-ref %}

***

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

***

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

**[Noen datapakker](#user-content-fn-2)[^2] kan ikke bli riktig implementert ved første bruk.**

I slike tilfeller anbefales det å starte serveren **2 ganger** for å sikre riktig påføring.

{% endhint %}

Datapakker kan lett bli ødelagt når Minecraft oppdateres.

Spesielt når datapakker er fullstendig ødelagt, kan serveren krasje, så det er viktig å teste grundig før du oppdaterer serveren.

{% hint style="info" %}

**Etter serverstartkommandoen kan du skrive `safeMode` for å deaktivere alle datapakker før du starter serveren på nytt.**

[Se `Referanse > Argumenter og egenskaper`](../reference/arguments.md#safeMode) for mer informasjon.

{% endhint %}

Du kan bekrefte at datapakkene er lagt til ved å bruke kommandoen `/datapack list`.

***

## Optimalisering <a href="#id-4" id="id-4"></a>

Plazma har fått mange optimaliseringsoppdateringer. Når Plazma først starter, optimaliseres konfigurasjonen automatisk,
så hvis du følger [Startveiledningen](./README.md), trenger du ikke å gjøre ekstra optimaliseringsarbeid.

Imidlertid, hvis mange spillere kobler seg til eller hvis verden er stor,
kan du gjøre ekstra optimaliseringsarbeid ved å følge veiledningen nedenfor.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxy kobler servere sammen og lar spillere bevege seg mellom servere uten ekstra arbeid,
og kommunisere med andre servere.

Se nedenstående side for informasjon om sikker og riktig proxykonfigurasjon.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Sikkerhet <a href="#id-5" id="id-5"></a>

Minecraft har utviklet seg til å enkelt kunne skaffe [sårbarhetsangrepsmotorer](#user-content-fn-3)[^3] online.

Selv om de fleste sårbarheter som er kjørbare i vanlige spill [er blokkert som standard](#user-content-fn-4)[^4],
er det ikke blokkert å angripe sårbarheter gjennom tredjepartsmoduler.

Derfor, hvis serveren er offentlig tilgjengelig, anbefales det å installere anti-cheat-plugins
og konfigurere proxy, automatisk omstart, sikkerhetskopiering osv. for rask gjenoppretting hvis serveren går ned.

### Tilgangskontroll <a href="#id-5.1" id="id-5.1"></a>

Noen administrasjonskommandoer for plugins har sårbarheter hvis tillatelsene ikke er riktig satt opp.

Det anbefales å bruke tillitsforvaltningsplugins som [LuckPerms](https://luckperms.net/)
for å begrense vanlige brukeres tillatelser.

### X-Ray-blokkering <a href="#id-5.2" id="id-5.2"></a>

X-Ray er en av sårbarhetene som er enkelt tilgjengelig selv i grunnleggende optimaliseringsklienter.

Plazma tilbyr en konfigurasjon som kan blokkere X-Ray som standard.

Se nedenstående side for instruksjoner om X-Ray-blokkering.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Hvitelistning <a href="#id-5.3" id="id-5.3"></a>

Hvis bare noen brukere skal kunne koble til serveren,
kan det være lurt å bruke [Ngrok](./README.md#id-6.2) for å bruke [kryptert serveradresse](#user-content-fn-5)[^5] eller
sette opp en hvitelistning for å hindre andre spillere i å koble til.

Du kan tillate eller nekte tilgang til spillere via `/whitelist add <spiller>` i serverkonsollen,
eller `/whitelist remove <spiller>` for å forhindre tilgang.

Bruk `/whitelist query` for å se hvilke spillere som har tillatelse til å koble seg til.

***

[^1]: Eller Minecraft: Bedrock Editions tillegg.

[^2]: Legg til nye skapninger osv.

[^3]: Vanligvis referert til som "hacking".

[^4]: Hvis konfigurasjonen ikke er optimalisert, eller hvis Plazma er utdatert, eller hvis det er nye sårbarheter som ikke er blokkert, kan det hende at de ikke er blokkert.

[^5]: Når spillere kobler seg til serveren, skjer det via Ngrok proxyserveren, og den tildelte Ngrok-adressen endres ved hver omstart.
