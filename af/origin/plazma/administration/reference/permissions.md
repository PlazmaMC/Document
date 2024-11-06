---
description: Vind uit oor die regte van Plazma.
---

# 🛡️ Regte

Toestemming is 'n eenvoudige sekuriteitsinstrument wat die omvang bepaal waarbinne spelers op die bediener met mekaar kan interaksioneer.

Om toestemming behoorlik te gebruik en maklik te wysig, moet jy plugins soos [LuckPerms](https://luckperms.net) gebruik.

***

## Begrip van basiese toestemmingsisteem <a href="#id-1" id="id-1"></a>

Minecraft bied basiese bestuursgroep-toestemmings aan.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Spelers**\
   Gewoonlik die standaard toestemmingsgroep vir alle spelers.
2. **Bemiddelaar**\
   Kan spawngbeskerming ignoreer.
3. **Wêreldbestuurder**\
   Kan alle bevele en bevelblokke wat met wêreldbestuur verband hou, gebruik.\
   Dit is die standaard toestemmingsgroep vir datapakke en bevelblokke.
4. **Bestuurder**\
   Kan alle bevele wat met spelerbestuur verband hou, gebruik.
5. **Hoofbestuurder**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `toelaat.spesiaal.(Naamruimte Sleutel)`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om die spesiale vaardighede van 'n entiteit te gebruik terwyl hulle dit ry.

Nie alle entiteite se spesiale vaardighede is beskikbaar nie. Raadpleeg die lys van alle beskikbare spesiale vaardighede hieronder.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Dit sal beide kante se prestasie verbeter.

> Kyk na die volgende bladsy vir X-straal instellings.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.deurloop-beweeg-te-vinnig-kontrole`

- **Standaard Verskaf**: `Geen`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.aambeeld.kleur`

- **Standaard Verskaf**: `Geen`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.aambeeld.formaat`

- **Standaard Verskaf**: `Geen`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.aambeeld.miniberig`

- **Standaard Verskaf**: `Geen`

Laat die gebruik van [MiniMessage etikette](https://docs.advntr.dev/minimessage/format.html) op aambeelde toe.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.aambeeld.verwyder_kursief`

- **Standaard Verskaf**: `Geen`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.boek.kleur.teken`

- **Standaard Verskaf**: `Geen`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderkis.rye.(Nommerteks)`

- **Standaard Verskaf**: `Geen`

Verander die grootte van die Ender Chest.

Jy kan `een`, `twee`, `drie`, `vier`, `vyf`, `ses` in `Nommerteks` invoer.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventaris_totem`

- **Standaard Verskaf**: `Geen`

Laat die werking van die onsterflikheid totem in die inventaris toe.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om die verbindingstoegrens te ignoreer.

#### `purpur.mending_shift_click`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om 'n voorwerp wat hulle dra te herstel deur `kniel en interaksie`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om spawners te plaas.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Standaard Verskaf**: `Geen`

Laat spelers direk na die Nether dimensie spring as hulle 'n Nether portal gebruik.

#### `purpur.sign.color`

- **Standaard Verskaf**: `Geen`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Standaard Verskaf**: `Geen`

Laat toe dat skilders die verwarrende kode`(&o)` gebruik.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **Standaard Verskaf**: `Geen`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om TNT ontploffing te stop deur `interaksie` met 'n skêr.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Voorsiene toestemming

#### `plazma.bypass.ncr-require`

- **Standaard Verskaf**: `Geen`

Laat spelers toe om aan te sluit sonder dat [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) mod geïnstalleer is.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: Byvoorbeeld: `ender_dragon`
