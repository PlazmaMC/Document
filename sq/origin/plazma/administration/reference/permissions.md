---
description: Merrni informacion mbi lejet e Plazma-së.
---

# 🛡️ Leje

Lejet është një mjet i thjeshtë i sigurisë që cakton gamën e veprimeve që lojtarët në server mund të bëjnë në mënyrë reciproke.

Për të përdorur lejet në mënyrë efektive dhe për t'i modifikuar lehtë, duhet të përdorni shtojcën si [LuckPerms](https://luckperms.net).

***

## Kuptimi i sistemit bazë të lejeve <a href="#id-1" id="id-1"></a>

Në Minecraft, ka grupe themelore të lejeve të menaxhimit të disponueshme.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Lojtar**\
   Një grup i lejeve që jepet në përgjithësi për të gjithë lojtarët.
2. **Arbitër**\
   Mund të injorosh mbrojtjen e lindjes.
3. **Menaxheri i botës**\
   Mund të përdorë të gjitha komandat dhe blloqet e komandave që kanë të bëjnë me menaxhimin e botës.\
   Ky është grupi i bazë i lejeve që aplikohet në paketat e të dhënave dhe blloqet e komandave.
4. **Administrator**\
   Mund të përdorë të gjitha komandat që kanë të bëjnë me menaxhimin e lojtarëve.
5. **Administratori i përgjithshëm**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `lejo.speciale.(Çelësi i Hapesiruar)`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarët të përdorin aftësitë speciale të entitetit kur janë duke u udhëtuar me të.

Nuk janë të gjitha aftësitë speciale të disponueshme për të gjitha entitetet. Për një listë të plotë të aftësive speciale të disponueshme, shihni më poshtë.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Kjo do të sjellë përfitime në performancë për të dyja palët.

> Për të mësuar më shumë rreth konfigurimit X-Ray, shihni faqen më poshtë.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- \*\*Ofrohet nga: `Asnjë`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- \*\*Ofrohet nga: `Asnjë`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- \*\*Ofrohet nga: `Asnjë`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- \*\*Ofrohet nga: `Asnjë`

Lejon përdorimin e etiketave [MiniMessage](https://docs.advntr.dev/minimessage/format.html) në mocë.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- \*\*Ofrohet nga: `Asnjë`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- \*\*Ofrohet nga: `Asnjë`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumërNëNjëri)`

- \*\*Ofrohet nga: `Asnjë`

Ndryshon madhësinë e kofshës së endër.

Në `(NumërNëNjëri)` mund të jepni `një`, `dy`, `tre`, `katër`, `pesë`, `gjashtë`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- \*\*Ofrohet nga: `Asnjë`

Lejon funksionimin e totemit të pafajshëm edhe kur është në inventar.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të injorojë kufirin e numrit të hyrës.

#### `purpur.mending_shift_click`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të riparojë sendin që mban duke `u shtrirë dhe duke ndikuar njëri-tjetrin`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të vendosë spawner-in.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- \*\*Ofrohet nga: `Asnjë`

Lejon lojtarin të teleportohet menjëherë kur përdor portën e Netherit.

#### `purpur.sign.color`

- \*\*Ofrohet nga: `Asnjë`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- \*\*Ofrohet nga: `Asnjë`

Lejohet përdorimi i kodit të zbehjes `(&o)` në tabelat e sinjalizimit.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- \*\*Ofrohet nga: `Asnjë`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- \*\*Ofrohet nga: `Asnjë`

Lejohet lojtari të parandalojë shpërthimin e TNT-së duke `bashkëvepruar` me thikën.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Lejet e parashikuara

#### `plazma.bypass.ncr-require`

- \*\*Ofrohet nga: `Asnjë`

Lejohet lojtari të hyjë pa pasur instaluar modulin [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operator.

[^2]: P.sh.: `ender_dragon`
