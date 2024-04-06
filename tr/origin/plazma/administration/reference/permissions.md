---
description: Plazma'nın izinleri hakkında bilgi edinin.
---

# 🛡️ İzin

İzinler, sunucu içinde oyuncuların etkileşimde bulunabileceği kapsamı belirleyen basit bir güvenlik aracıdır.

İzinleri doğru şekilde kullanmak ve kolayca değiştirmek için [LuckPerms](https://luckperms.net) gibi eklentiler kullanılmalıdır.

***

## Temel izin sistemi anlayışı <a href="#id-1" id="id-1"></a>

Minecraft'ta temel yönetici izin grupları sağlanmaktadır.

[Operator](#user-content-fn-1)[^1] ve komut bloğu izinlerini ayarlayabilir ve [sunucu özelliklerinde](configurations/property.md) değişiklik yapabilirsiniz.

0. **Oyuncu**\
   Genellikle tüm oyunculara verilen bir izin grubudur.
1. **Aracı**\
   Doğma korumasını yok sayabilir.
2. **Dünya Yöneticisi**\
   Tüm dünya yönetimiyle ilgili komutları ve komut bloklarını kullanabilir.\
   Veri paketlerine ve komut bloklarına varsayılan olarak uygulanan bir izin grubudur.
3. **Yönetici**\
   Oyuncu yönetimiyle ilgili tüm komutları kullanabilir.
4. **Baş Yönetici**\
   Sunucu yönetimi de dahil olmak üzere tüm komutları kullanabilir.\
   Konsol ve operatörlere varsayılan olarak uygulanan bir izin grubudur.

***

## İzinleri Ayarlama <a href="#id-2" id="id-2"></a>

***

## Tüm İzinler <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **Varsayılan**: `None`

Oyuncuların varlıkla `eğilip etkileşime geçerek` varlığa binmelerine izin verir.

Varlığa bindiğinizde, varlığın hareketini `hareket tuşlarıyla` kontrol edebilir ve `zıplama tuşuyla` zıplayabilir veya uçabilirsiniz.

`(Namespaced Key)` varlığın [Namespaced ID](#user-content-fn-2)[^2] girilir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `(Entity) > ridable\` etkinleştirildiğinde yalnızca çalışır.**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Varsayılan**: `None`

Oyuncu bir varlığa binerken, varlığın özel yeteneklerini kullanmasına izin verir.

Tüm varlıkların özel yetenekleri kullanılamayabilir. Kullanılabilir tüm özel yetenekler için aşağıya bakınız.

{% hint style="info" %}

**Özel yeteneklerle ilgili iyi bir fikriniz mi var?**

[Plazma Discord](https://plazmamc.org/discord) veya [GitHub Tartışmaları](https://github.com/PlazmaMC/PlazmaBukkit/discussions) üzerinde fikirlerinizi paylaşın!

{% endhint %}

<details>

<summary>Şu anda kullanılabilir özel yetenekleri görüntüle</summary>

- **`crepper`**\
  `Zıplama tuşuna` basarak patlar.\
  Oyuncu, `allow.powered.creeper` iznine sahipse, patlatmak için `zıplama tuşunu` basılı tutabilir.
- **`dolphin`**\
  `Zıplama tuşuna` basarak hızla yüzer.
- **`phantom`**\
  `Zıplama tuşuna` basarak alev atar.
- **`wither`**\
  `Etkileşime` girerse wither başını fırlatır.

</details>

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `(Entity) > ridable\` etkinleştirildiğinde yalnızca çalışır.**

{% endhint %}

#### `bukkit.command.compass`

- **Varsayılan**: `Dünya Yöneticisi`

[`/compass` komutu](commands.md#compass) kullanımına izin verir.

#### `bukkit.command.credits`

- **Varsayılan**: `Dünya Yöneticisi`

[`/credits (Oyuncu)` komutu](commands.md#credits) kullanımına izin verir.

İzin adının arkasına `.other` yazarsanız başka oyuncuların kullanmasına izin verir.

#### `bukkit.command.demo`

- **Varsayılan**: `Dünya Yöneticisi`

[`/demo (Oyuncu)` komutu](commands.md#demo) kullanımına izin verir.

İzin adının arkasına `.other` yazarsanız başka oyuncuların kullanmasına izin verir.

#### `bukkit.command.ping`

- **Varsayılan**: `Dünya Yöneticisi`

[`/ping (Oyuncu)` komutu](commands.md#ping) kullanımına izin verir.

İzin adının arkasına `.other` yazarsanız başka oyuncuların kullanmasına izin verir.

#### `bukkit.command.ram`

- **Varsayılan**: `Dünya Yöneticisi`

[`/ram` komutu](commands.md#ram) kullanımına izin verir.

#### `bukkit.command.rambar`

- **Varsayılan**: `Dünya Yöneticisi`

[`/rambar (Oyuncu)` komutu](commands.md#rambar) kullanımına izin verir.

İzin adının arkasına `.other` yazarsanız başka oyuncuların kullanmasına izin verir.

#### `bukkit.command.restart`

- **Varsayılan**: `Dünya Yöneticisi`

[`/restart` komutu](commands.md#restart) kullanımına izin verir.

#### `bukkit.command.tps`

- **Varsayılan**: `Dünya Yöneticisi`

[`/tps` komutu](commands.md#tps) kullanımına izin verir.

#### `bukkit.command.tpsbar`

- **Varsayılan**: `Dünya Yöneticisi`

[`/tpsbar (Oyuncu)` komutu](commands.md#tpsbar) kullanımına izin verir.

İzin adının arkasına `.other` yazarsanız başka oyuncuların kullanmasına izin verir.

#### `bukkit.command.timings`

- **Varsayılan**: `Dünya Yöneticisi`

[`/timings` komutu](commands.md#timings) kullanımına izin verir.

{% hint style="warning" %}

**Bu komut artık kullanımdan kaldırılmıştır.**

Benzer işlevlere sahip komutları görmek için [Spark](https://spark.lucko.me/docs/Command-Usage)'e bakın.

{% endhint %}

#### `bukkit.command.uptime`

- **Varsayılan**: `Dünya Yöneticisi`

[`/uptime` komutu](commands.md#uptime) kullanımına izin verir.

#### `minecraft.command.gamemode.(GameMode)`

- **Varsayılan**: `Dünya Yöneticisi`

`/gamemode (GameMode) (Oyuncu)` komutu kullanımına izin verir.

İzin adının arkasına `.other` yazarsanız başka oyuncuların kullanmasına izin verir.

#### `paper.antixray.bypass`

- **Varsayılan**: `None`

[X-Ray Engelleme](../expert/xray.md) etkinleştirildiğinde,
izinli oyuncuların X-Ray engelleme bloklarını karıştırmaz.

Bu, her iki tarafın da performansını artırır.

> X-Ray ayarları hakkında bilgi edinmek için aşağıdaki sayfaya bakın.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Varsayılan**: `None`

{% hint style="warning" %}

Bu izin, 1.20.5'te `plazma.bypass.watchdog` olarak değiştirilecektir.

{% endhint %}

#### `purpur.anvil.color`

- **Varsayılan**: `None`

Örsün [Renk Kodları](https://minecraft.wiki/w/Formatting_codes#Color_codes) kullanılmasına izin verir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `anvil > allow-colors\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.anvil.format`

- **Varsayılan**: `None`

Örsün [Biçimlendirme Kodları](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) kullanılmasına izin verir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `anvil > allow-colors\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.anvil.minimessage`

- **Varsayılan**: `None`

Örsün [MiniMessage Etiketleri](https://docs.advntr.dev/minimessage/format.html) kullanılmasına izin verir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `anvil > allow-minimessages\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **Varsayılan**: `None`

Örsü [`&r` Biçimlendirme Kodu](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) ile `italik yazıyı` devre dışı bırakmanıza izin verir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `anvil > allow-colors\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.book.color.sign`

- **Varsayılan**: `None`

Oyuncu bir kitaba imza attığında [Biçimlendirme Kodları](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) uygulanmasını sağlar.

#### `purpur.bypassIdleKick`

- **Varsayılan**: `None`

Oyuncuyu boşta atma kuralı dışında tutar.

#### `purpur.debug.f3n`

- **Varsayılan**: `Dünya Yöneticisi`

Oyuncunun `F3 + N` tuşuyla oyun modunu değiştirmesine izin verir.

Bu oyun modu için izni yoksa çalışmaz.

#### `purpur.drop.spawners`

- **Varsayılan**: `None`

Yapılandırmada belirlenen öğelerle spawner bloklarını kırarsanız spawner blokları düşer.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `gameplay-mechanics > silk-touch\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Varsayılan**: `None`

Ender sandığının boyutunu değiştirir.

`(NumberString)` içine `one`, `two`, `three`, `four`, `five`, `six` girebilirsiniz.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `ender_chest > six-rows`ve`ender_chest > use-permissions-for-rows\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.inventory_totem`

- **Varsayılan**: `None`

Ölümsüzlük totemi envanterdeyken çalışmasına izin verir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `totem-of-undying-works-in-inventory\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.joinFullServer`

- **Varsayılan**: `None`

Oyuncunun bağlantı sınırını yoksaymasına izin verir.

#### `purpur.mending_shift_click`

- **Varsayılan**: `None`

Oyuncunun `eğilip etkileşime geçtiğinde` tuttuğu öğeyi tamir etmesine izin verir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırmaları](configurations/purpur/world.md) içinde `shift-right-click-repairs-mending-points`'i etkinleştirmeniz gerekmektedir.**

{% endhint %}

#### `purpur.place.spawners`

- **Varsayılan**: `None`

Oyuncunun yaratıcıları yerleştirmesine izin verir.

{% hint style="info" %}

**[Purpur Dünya Yapılandırması](configurations/purpur/world.md)`nde `gameplay-mechanics > silk-touch\` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.portal.instant`

- **Varsayılan**: `None`

Oyuncunun Nether portalını kullandığında hemen teleport olmasını sağlar.

#### `purpur.sign.color`

- **Varsayılan**: `None`

[Renk kodları](https://minecraft.wiki/w/Formatting_codes#Color_codes) kullanımına izin vermek için tabelalarda kullanılabilir.

{% hint style="info" %}

**[Purpur Configuration](configurations/purpur/world.md) içinde `sign > allow-colors` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.sign.magic`

- **Varsayılan**: `None`

Levha üzerinde okunabilirlik kodu`(&o)` kullanılmasına izin verir.

{% hint style="info" %}

**[Purpur Configuration](configurations/purpur/world.md) içinde `sign > allow-colors` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.levha.stili`

- **Varsayılan**: `None`

Levha üzerinde [Biçimlendirme kodları `(&o hariç)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) kullanılmasına izin verir.

{% hint style="info" %}

**[Purpur Configuration](configurations/purpur/world.md) içinde `sign > allow-colors` etkinleştirilmelidir.**

{% endhint %}

#### `purpur.tnt.söndür`

- **Varsayılan**: `None`

Oyuncuların TNT patlamasını `etkileşim` ile engellemesine izin verir.

{% hint style="info" %}

**[Purpur dünya yapılandırmaları](configurations/purpur/world.md) içinde `söndür-tnt-değişikliği` `0.0` veya üzerinde olmalıdır çalışması için.**

{% endhint %}

### Verilen izinler

#### `plazma.bypass.ncr-gereksinimi`

- **Varsayılan**: `None`

Oyuncuların [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) modu yüklü olmasa bile giriş yapmasına izin verir.

{% hint style="info" %}

**[Plazma dünya yapılandırmaları](configurations/plazma/world.md) içinde `no-chat-reports > yükleme-gerektir` etkinleştirilmelidir çalışması için.**

{% endhint %}

***

[^1]: Operatör.

[^2]: Örnek: `ender_dragon`
