---
description: Merrni informacion mbi lejet e Plazma-së.
---

# 🛡️ Leje

Lejet është një mjet i thjeshtë i sigurisë që cakton gamën e veprimeve që lojtarët në server mund të bëjnë në mënyrë reciproke.

Për të përdorur lejet në mënyrë efektive dhe për t'i modifikuar lehtë, duhet të përdorni shtojcën si [LuckPerms](https://luckperms.net).

***

## Kuptimi i sistemit bazë të lejeve <a href="#id-1" id="id-1"></a>

Në Minecraft, ka grupe themelore të lejeve të menaxhimit të disponueshme.

Mund të caktoni lejet për [administratorë](#user-content-fn-1)[^1] dhe bllokuj komandash, dhe mund t'i modifikoni në [konfigurimet e serverit](configurations/property.md).

0. **Lojtar**\
   Një grup i lejeve që jepet në përgjithësi për të gjithë lojtarët.
1. **Arbitër**\
   Mund të injorosh mbrojtjen e lindjes.
2. **Menaxheri i botës**\
   Mund të përdorë të gjitha komandat dhe blloqet e komandave që kanë të bëjnë me menaxhimin e botës.\
   Ky është grupi i bazë i lejeve që aplikohet në paketat e të dhënave dhe blloqet e komandave.
3. **Administrator**\
   Mund të përdorë të gjitha komandat që kanë të bëjnë me menaxhimin e lojtarëve.
4. **Administratori i përgjithshëm**\
   Mund të përdorë të gjitha komandat që kanë të bëjnë me menaxhimin e serverit.\
   Ky është grupi i bazë i lejeve që aplikohet në konzolën dhe administratorët.

***

## Caktimi i lejeve <a href="#id-2" id="id-2"></a>

***

## Leje të plota <a href="#id-3" id="id-3"></a>

***

#### `lejo.rrugë.(Çelësi i Hapesiruar)`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarët të `uleshin dhe të bashkëveprojnë` me entitetet për të shkuar mbi to.

Kur ulesh në një entitet, mund të përdorësh tastin e `lëvizjes` për të drejtuar lëvizjen e entitetit dhe tastin e `kthimit` për të bërë një hop ose fluturim.

Në `(Çelësi i Hapesiruar)` vendoset [ID-ja e Hapesiruar](#user-content-fn-2)[^2] e entitetit.

{% hint style="info" %}

**[Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizojnë `(Entiteti) > e udhëtueshme` për të funksionuar.**

{% endhint %}

#### `lejo.speciale.(Çelësi i Hapesiruar)`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarët të përdorin aftësitë speciale të entitetit kur janë duke u udhëtuar me të.

Nuk janë të gjitha aftësitë speciale të disponueshme për të gjitha entitetet. Për një listë të plotë të aftësive speciale të disponueshme, shihni më poshtë.

{% hint style="info" %}

**Keni ndonjë ide të mirë për një aftësi speciale?**

Publikoni idetë tuaja në [Plazma Discord](https://plazmamc.org/discord) ose [Bisedat e GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

<details>

<summary>Shikoni aftësitë speciale aktualisht të disponueshme</summary>

- **`crepper`**\
  Kur shtyp tastin e `kthimit`, shpërthen.\
  Nëse lojtari ka lejen `crepper i fuqizuar` mund të mbajë shtypur tastin e `kthimit` për të ngarkuar shpërthimin.
- **`delfin`**\
  Kur shtyp tastin e `kthimit`, bën një rrëmbim.
- **`fantazmë`**\
  Kur shtyp tastin e `kthimit`, shpërthen flakë.
- **`me kërcim`**\
  Kur `bashkëvepron`, shpërthen kokën e me kërcim.

</details>

{% hint style="info" %}

**[Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizojnë `(Entiteti) > e udhëtueshme` për të funksionuar.**

{% endhint %}

#### `bukkit.command.kompas`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/kompas`](commands.md#kompas).

#### `bukkit.command.kreditet`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/kreditet (Lojtari)`](commands.md#kreditet).

Nëse shtohet `.tjetër` pas emrit të lejes, lejon përdorimin nga lojtarët e tjerë.

#### `bukkit.command.demo`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/demo (Lojtari)`](commands.md#demo).

Nëse shtohet `.tjetër` pas emrit të lejes, lejon përdorimin nga lojtarët e tjerë.

#### `bukkit.command.ping`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/ping (Lojtari)`](commands.md#ping).

Nëse shtohet `.tjetër` pas emrit të lejes, lejon përdorimin nga lojtarët e tjerë.

#### `bukkit.command.ram`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/rambar (Lojtari)`](commands.md#rambar).

Nëse shtohet `.tjetër` pas emrit të lejes, lejon përdorimin nga lojtarët e tjerë.

#### `bukkit.command.ristart`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/ristart`](commands.md#ristart).

#### `bukkit.command.tps`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/tpsbar (Lojtari)`](commands.md#tpsbar).

Nëse shtohet `.tjetër` pas emrit të lejes, lejon përdorimin nga lojtarët e tjerë.

#### `bukkit.command.timings`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/timings`](commands.md#timings).

{% hint style="warning" %}

**Kjo komandë është ndaluar për përdorim.**

Për të mësuar më shumë për komandat e ngjashme, shihni [Spark](https://spark.lucko.me/docs/Command-Usage).

{% endhint %}

#### `bukkit.command.uptime`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon përdorimin e komandës `/gamemode (GameMode) (Lojtari)`.

Nëse shtohet `.tjetër` pas emrit të lejes, lejon përdorimin nga lojtarët e tjerë.

#### `paper.antixray.bypass`

- \*\*Ofrohet nga: `Asnjë`

Nëse është aktivizuar bllokim X-Ray, lojtarët me leje nuk do të përballen me zhbërjen e bllokave X-Ray.

Kjo do të sjellë përfitime në performancë për të dyja palët.

> Për të mësuar më shumë rreth konfigurimit X-Ray, shihni faqen më poshtë.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- \*\*Ofrohet nga: `Asnjë`

{% hint style="warning" %}

Kjo leje do të ndryshohet në 1.20.5 në `plazma.bypass.watchdog`.

{% endhint %}

#### `purpur.anvil.color`

- \*\*Ofrohet nga: `Asnjë`

Lejon përdorimin e [kodit të ngjyrave](https://minecraft.wiki/w/Formatting_codes#Color_codes) në mocë.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `anvil > allow-colors` për të funksionuar.**

{% endhint %}

#### `purpur.anvil.format`

- \*\*Ofrohet nga: `Asnjë`

Lejon përdorimin e [kodit të stilizimit](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) në mocë.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `anvil > allow-colors` për të funksionuar.**

{% endhint %}

#### `purpur.anvil.minimessage`

- \*\*Ofrohet nga: `Asnjë`

Lejon përdorimin e etiketave [MiniMessage](https://docs.advntr.dev/minimessage/format.html) në mocë.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `anvil > allow-minimessages` për të funksionuar.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- \*\*Ofrohet nga: `Asnjë`

Lejon përdorimin e kodit të stilizimit [`&r`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) për të çaktivizuar `përkuljen e shkronjave` në mocë.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `anvil > allow-colors` për të funksionuar.**

{% endhint %}

#### `purpur.book.color.sign`

- \*\*Ofrohet nga: `Asnjë`

Kur një lojtar nënshkruan një libër, aplikohen [kodet e stilizimit](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

#### `purpur.bypassIdleKick`

- \*\*Ofrohet nga: `Asnjë`

E përjashton lojtarin nga dëbimi i automatizuar për pasivitet.

#### `purpur.debug.f3n`

- \*\*Ofrohet nga: `Menaxheri i botës`

Lejon lojtarët të ndryshojnë mënyrën e lojës me tastin `F3 + N`.

Nëse nuk ka leje për këtë mënyrë loje, nuk do të funksionojë.

#### `purpur.drop.spawners`

- \*\*Ofrohet nga: `Asnjë`

Kur minon blloqet e spawnerit me armë me prekje të butë, ato do të bien poshtë si blloqe spawneri.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `gameplay-mechanics > silk-touch` për të funksionuar.**

{% endhint %}

#### `purpur.enderchest.rows.(NumërNëNjëri)`

- \*\*Ofrohet nga: `Asnjë`

Ndryshon madhësinë e kofshës së endër.

Në `(NumërNëNjëri)` mund të jepni `një`, `dy`, `tre`, `katër`, `pesë`, `gjashtë`.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `ender_chest > six-rows` dhe `ender_chest > use-permissions-for-rows` për të funksionuar.**

{% endhint %}

#### `purpur.inventory_totem`

- \*\*Ofrohet nga: `Asnjë`

Lejon funksionimin e totemit të pafajshëm edhe kur është në inventar.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `totem-of-undying-works-in-inventory` për të funksionuar.**

{% endhint %}

#### `purpur.joinFullServer`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të injorojë kufirin e numrit të hyrës.

#### `purpur.mending_shift_click`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të riparojë sendin që mban duke `u shtrirë dhe duke ndikuar njëri-tjetrin`.

{% hint style="info" %}

**[Konfigurimet e botëve Purpur](configurations/purpur/world.md) duhet të aktivizohen `shift-right-click-repairs-mending-points` për të funksionuar.**

{% endhint %}

#### `purpur.place.spawners`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të vendosë spawner-in.

{% hint style="info" %}

**Në [Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të aktivizohet `gameplay-mechanics > silk-touch` për të funksionuar.**

{% endhint %}

#### `purpur.portal.instant`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të teleportohet menjëherë kur përdor portën e Netherit.

#### `purpur.sign.color`

- \*\*Ofrohet nga: `Asnjë`

Lejohen përdorimi i [kodit të ngjyrave](https://minecraft.wiki/w/Formatting_codes#Color_codes) në tabelat e sinjaleve.

{% hint style="info" %}

\*\*Duhet të aktivizoni `sign > allow-colors` në \*\*[konfigurimet e botës Purpur](configurations/purpur/world.md) **për të vepruar.**

{% endhint %}

#### `purpur.sign.magic`

- \*\*Ofrohet nga: `Asnjë`

Lejohet përdorimi i kodit të zbehjes `(&o)` në tabelat e sinjalizimit.

{% hint style="info" %}

\*\*Duhet të aktivizoni `sign > allow-colors` në \*\*[konfigurimet e botës Purpur](configurations/purpur/world.md) **për të vepruar.**

{% endhint %}

#### `purpur.sign.style`

- \*\*Ofrohet nga: `Asnjë`

Lejohet përdorimi i [kodit të stilizimit `(&o përjashtuar)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) në tabelat e sinjalizimit.

{% hint style="info" %}

\*\*Duhet të aktivizoni `sign > allow-colors` në \*\*[konfigurimet e botës Purpur](configurations/purpur/world.md) **për të vepruar.**

{% endhint %}

#### `purpur.tnt.defuse`

- \*\*Ofrohet nga: `Asnjë`

Lejohet lojtari të parandalojë shpërthimin e TNT-së duke `bashkëvepruar` me thikën.

{% hint style="info" %}

**[Konfigurimet e botës Purpur](configurations/purpur/world.md) duhet të ketë `defuse-tnt-change` më shumë se `0.0` për të funksionuar.**

{% endhint %}

### Lejet e parashikuara

#### `plazma.bypass.ncr-require`

- \*\*Ofrohet nga: `Asnjë`

Lejohet lojtari të hyjë pa pasur instaluar modulin [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**Në [Konfigurimet e botës Plazma](configurations/plazma/world.md) duhet të aktivizohet `no-chat-reports > require-install` për të funksionuar.**

{% endhint %}

***

[^1]: Operator.

[^2]: P.sh.: `ender_dragon`
