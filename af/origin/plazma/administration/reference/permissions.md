---
description: Vind uit oor die regte van Plazma.
---

# 🛡️ Regte

Toestemming is 'n eenvoudige sekuriteitsinstrument wat die omvang bepaal waarbinne spelers op die bediener met mekaar kan interaksioneer.

Om toestemming behoorlik te gebruik en maklik te wysig, moet jy plugins soos [LuckPerms](https://luckperms.net) gebruik.

***

## Begrip van basiese toestemmingsisteem <a href="#id-1" id="id-1"></a>

Minecraft bied basiese bestuursgroep-toestemmings aan.

Jy kan toestemming vir [operateurs](#user-content-fn-1)[^1] en bevelblokke instel en dit kan by [bediener-eienskappe](configurations/property.md) gewysig word.

0. **Spelers**\
   Gewoonlik die standaard toestemmingsgroep vir alle spelers.
1. **Bemiddelaar**\
   Kan spawngbeskerming ignoreer.
2. **Wêreldbestuurder**\
   Kan alle bevele en bevelblokke wat met wêreldbestuur verband hou, gebruik.\
   Dit is die standaard toestemmingsgroep vir datapakke en bevelblokke.
3. **Bestuurder**\
   Kan alle bevele wat met spelerbestuur verband hou, gebruik.
4. **Hoofbestuurder**\
   Kan alle bevele insluitend bedienerbestuur gebruik.\
   Dit is die standaard toestemmingsgroep vir konsole en operateurs.

***

## Toestemming instel <a href="#id-2" id="id-2"></a>

***

## Algemene toestemming <a href="#id-3" id="id-3"></a>

***

#### `toelaat.ry.(Namespaced Key)`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om op 'n entiteit te klim deur dit te 'shift' en met die entiteit te interaksioneer.

As jy op 'n entiteit klim, kan jy die entiteit se beweging met die 'bewegingsleutel' beheer en met die 'springleutel' spring of vlieg.

Die [Namespaced ID](#user-content-fn-2)[^2] van die entiteit word ingevoer in die `(Namespaced Key)`.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer slegs wanneer `(Entity) > berijdbaar` in die Purpur wêreldkonfigurasie geaktiveer is.**

{% endhint %}

#### `toelaat.spesiaal.(Naamruimte Sleutel)`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om die spesiale vaardighede van 'n entiteit te gebruik terwyl hulle dit ry.

Nie alle entiteite se spesiale vaardighede is beskikbaar nie. Raadpleeg die lys van alle beskikbare spesiale vaardighede hieronder.

{% hint style="info" %}

**Het jy 'n goeie idee vir 'n spesiale vaardigheid?**

Plaas jou idee op [Plazma Discord](https://plazmamc.org/discord) of [GitHub Besprekings](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<opsomming>Sien alle beskikbare spesiale vaardighede</opsomming>

- **`kruip`**\
  Druk die `spring sleutel` om te ontplof.\
  As 'n speler die `toelaat.kragtige.kruiper` toestemming het, kan jy die `spring sleutel` ingedruk hou om dit te laai.
- **`dolfyn`**\
  Druk die `spring sleutel` om te duik.
- **`spook`**\
  Druk die `spring sleutel` om vlamme te skiet.
- **`verwelk`**\
  Deur `interaksie` te gebruik, skiet jy 'n verwelk kop af.

</details>

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer slegs wanneer `(Entity) > berijdbaar` in die Purpur wêreldkonfigurasie geaktiveer is.**

{% endhint %}

#### `bukkit.opdrag.kompas`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/kompas` opdrag](commands.md#compass) toe.

#### `bukkit.opdrag.krediete`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/krediete (Speler)` opdrag](commands.md#credits) toe.

Voer `.ander` agter die toestemming naam in om dit vir ander spelers toe te laat.

#### `bukkit.opdrag.demonstrasie`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/demonstrasie (Speler)` opdrag](commands.md#demo) toe.

Voer `.ander` agter die toestemming naam in om dit vir ander spelers toe te laat.

#### `bukkit.opdrag.piek`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/piek (Speler)` opdrag](commands.md#ping) toe.

Voer `.ander` agter die toestemming naam in om dit vir ander spelers toe te laat.

#### `bukkit.opdrag.ram`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/ram` opdrag](commands.md#ram) toe.

#### `bukkit.opdrag.rambalk`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/rambalk (Speler)` opdrag](commands.md#rambar) toe.

Voer `.ander` agter die toestemming naam in om dit vir ander spelers toe te laat.

#### `bukkit.opdrag.herlaai`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/herlaai` opdrag](commands.md#restart) toe.

#### `bukkit.opdrag.tps`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/tps` opdrag](commands.md#tps) toe.

#### `bukkit.opdrag.tpsbalk`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/tpsbalk (Speler)` opdrag](commands.md#tpsbar) toe.

Voer `.ander` agter die toestemming naam in om dit vir ander spelers toe te laat.

#### `bukkit.opdrag.tydmetings`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/tydmetings` opdrag](commands.md#timings) toe.

{% hint style="warning" %}

**Hierdie opdrag is gestaak.**

Kyk na [Spark](https://spark.lucko.me/docs/Command-Usage) vir soortgelyke funksionaliteit oorweeg.

{% endhint %}

#### `bukkit.opdrag.opdop`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die [`/opdop` opdrag](commands.md#uptime) toe.

#### `minecraft.opdrag.speelmodus.(Speelmodus)`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat die gebruik van die `/speelmodus (Speelmodus) (Speler)` opdrag toe.

Voer `.ander` agter die toestemming naam in om dit vir ander spelers toe te laat.

#### `papier.antixray.deurloop`

- **Standaard Verskaf**: `Geen`

As die [X-straal blokkering](../expert/xray.md) geaktiveer is,
sal spelers met die regte toestemming nie X-straal blokkering blokkeer nie.

Dit sal beide kante se prestasie verbeter.

> Kyk na die volgende bladsy vir X-straal instellings.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.deurloop-beweeg-te-vinnig-kontrole`

- **Standaard Verskaf**: `Geen`

{% hint style="warning" %}

Hierdie toestemming sal binnekort verander na `plazma.deurloop.wagter` in 1.20.5.

{% endhint %}

#### `purpur.aambeeld.kleur`

- **Standaard Verskaf**: `Geen`

Laat die gebruik van [kleur kodes](https://minecraft.wiki/w/Formatting_codes#Color_codes) op aambeelde toe.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer `aambeeld > toelaat-kleure` om dit te laat werk.**

{% endhint %}

#### `purpur.aambeeld.formaat`

- **Standaard Verskaf**: `Geen`

Laat die gebruik van [styl kodes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) op aambeelde toe.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer `aambeeld > toelaat-kleure` om dit te laat werk.**

{% endhint %}

#### `purpur.aambeeld.miniberig`

- **Standaard Verskaf**: `Geen`

Laat die gebruik van [MiniMessage etikette](https://docs.advntr.dev/minimessage/format.html) op aambeelde toe.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer `aambeeld > toelaat-miniberigte` om dit te laat werk.**

{% endhint %}

#### `purpur.aambeeld.verwyder_kursief`

- **Standaard Verskaf**: `Geen`

Laat die gebruik van die [`&r` styl kode](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) toe om `skreef` te deaktiveer.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer `aambeeld > toelaat-kleure` om dit te laat werk.**

{% endhint %}

#### `purpur.boek.kleur.teken`

- **Standaard Verskaf**: `Geen`

As 'n speler 'n boek onderteken, word [styl kodes](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) toegepas.

#### `purpur.verbyIdleKick`

- **Standaard Verskaf**: `Geen`

Sluit spelers uit van die idle kick lys.

#### `purpur.debuur.f3n`

- **Standaard Verskaf**: `Wêreld Bestuurder`

Laat spelers toe om die spelmodus te verander met die `F3 + N` sleutel kombinasie.

Dit sal nie werk as die speler nie die regte spelmodus toestemming het nie.

#### `purpur.aflaai.spawners`

- **Standaard Verskaf**: `Geen`

As jy 'n spawner blok met die regte item breek, laat dit die spawner blok val.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer `speel-meganika > sy-tik` om dit te laat werk.**

{% endhint %}

#### `purpur.enderkis.rye.(Nommerteks)`

- **Standaard Verskaf**: `Geen`

Verander die grootte van die Ender Chest.

Jy kan `een`, `twee`, `drie`, `vier`, `vyf`, `ses` in `Nommerteks` invoer.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer `ender_kis > ses-rye` en `ender_kis > gebruik-toestemmings-vir-rye` om dit te laat werk.**

{% endhint %}

#### `purpur.inventaris_totem`

- **Standaard Verskaf**: `Geen`

Laat die werking van die onsterflikheid totem in die inventaris toe.

{% hint style="info" %}

**[Purpur-wêreldkonfigurasies](configurations/purpur/world.md) moet `totem-of-undying-works-in-inventory` aktiveer om te werk.**

{% endhint %}

#### `purpur.joinFullServer`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om die verbindingstoegrens te ignoreer.

#### `purpur.mending_shift_click`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om 'n voorwerp wat hulle dra te herstel deur `kniel en interaksie`.

{% hint style="info" %}

**[Purpur-wêreldkonfigurasies](configurations/purpur/world.md) moet `shift-right-click-repairs-mending-points` aktiveer om te werk.**

{% endhint %}

#### `purpur.place.spawners`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om spawners te plaas.

{% hint style="info" %}

**[Purpur wêreldkonfigurasies](configurations/purpur/world.md) aktiveer `speel-meganika > sy-tik` om dit te laat werk.**

{% endhint %}

#### `purpur.portal.instant`

- **Standaard Verskaf**: `Geen`

Laat spelers direk na die Nether dimensie spring as hulle 'n Nether portal gebruik.

#### `purpur.sign.color`

- **Standaard Verskaf**: `Geen`

Laat toe dat [kleurkodes](https://minecraft.wiki/w/Formatting_codes#Color_codes) op skilders gebruik word.

{% hint style="info" %}

**[Purpur-wêreldkonfigurasies](configurations/purpur/world.md) moet `sign > allow-colors` aktiveer om te werk.**

{% endhint %}

#### `purpur.sign.magic`

- **Standaard Verskaf**: `Geen`

Laat toe dat skilders die verwarrende kode`(&o)` gebruik.

{% hint style="info" %}

**[Purpur-wêreldkonfigurasies](configurations/purpur/world.md) moet `sign > allow-colors` aktiveer om te werk.**

{% endhint %}

#### `purpur.sign.style`

- **Standaard Verskaf**: `Geen`

Laat toe dat [stylkode `(&o uitgesluit)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) op skilders gebruik word.

{% hint style="info" %}

**[Purpur-wêreldkonfigurasies](configurations/purpur/world.md) moet `sign > allow-colors` aktiveer om te werk.**

{% endhint %}

#### `purpur.tnt.defuse`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om TNT ontploffing te stop deur `interaksie` met 'n skêr.

{% hint style="info" %}

**[Purpur-wêreldkonfigurasies](configurations/purpur/world.md) moet `defuse-tnt-change` `0.0` of meer wees om te werk.**

{% endhint %}

### Voorsiene toestemming

#### `plazma.bypass.ncr-require`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om aan te sluit sonder dat [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod geïnstalleer is.

{% hint style="info" %}

**[Plazma-wêreldkonfigurasies](configurations/plazma/world.md) moet `no-chat-reports > require-install` aktiveer om te werk.**

{% endhint %}

***

[^1]: Operator.

[^2]: Byvoorbeeld: `ender_dragon`
