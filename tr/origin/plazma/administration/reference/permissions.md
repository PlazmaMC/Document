---
description: Plazma'nın izinleri hakkında bilgi edinin.
---

# 🛡️ İzin

İzinler, sunucu içinde oyuncuların etkileşimde bulunabileceği kapsamı belirleyen basit bir güvenlik aracıdır.

İzinleri doğru şekilde kullanmak ve kolayca değiştirmek için [LuckPerms](https://luckperms.net) gibi eklentiler kullanılmalıdır.

***

## Temel izin sistemi anlayışı <a href="#id-1" id="id-1"></a>

Minecraft'ta temel yönetici izin grupları sağlanmaktadır.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Oyuncu**\
   Genellikle tüm oyunculara verilen bir izin grubudur.
2. **Aracı**\
   Doğma korumasını yok sayabilir.
3. **Dünya Yöneticisi**\
   Tüm dünya yönetimiyle ilgili komutları ve komut bloklarını kullanabilir.\
   Veri paketlerine ve komut bloklarına varsayılan olarak uygulanan bir izin grubudur.
4. **Yönetici**\
   Oyuncu yönetimiyle ilgili tüm komutları kullanabilir.
5. **Baş Yönetici**\
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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **Varsayılan**: `None`

Oyuncu bir varlığa binerken, varlığın özel yeteneklerini kullanmasına izin verir.

Tüm varlıkların özel yetenekleri kullanılamayabilir. Kullanılabilir tüm özel yetenekler için aşağıya bakınız.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
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
**해당 명령어는 사용이 중단되었습니다.**

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

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Bu, her iki tarafın da performansını artırır.

> X-Ray ayarları hakkında bilgi edinmek için aşağıdaki sayfaya bakın.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **Varsayılan**: `None`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **Varsayılan**: `None`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **Varsayılan**: `None`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **Varsayılan**: `None`

Örsün [MiniMessage Etiketleri](https://docs.advntr.dev/minimessage/format.html) kullanılmasına izin verir.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **Varsayılan**: `None`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **Varsayılan**: `None`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

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
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **Varsayılan**: `None`

Ender sandığının boyutunu değiştirir.

`(NumberString)` içine `one`, `two`, `three`, `four`, `five`, `six` girebilirsiniz.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **Varsayılan**: `None`

Ölümsüzlük totemi envanterdeyken çalışmasına izin verir.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **Varsayılan**: `None`

Oyuncunun bağlantı sınırını yoksaymasına izin verir.

#### `purpur.mending_shift_click`

- **Varsayılan**: `None`

Oyuncunun `eğilip etkileşime geçtiğinde` tuttuğu öğeyi tamir etmesine izin verir.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **Varsayılan**: `None`

Oyuncunun yaratıcıları yerleştirmesine izin verir.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **Varsayılan**: `None`

Oyuncunun Nether portalını kullandığında hemen teleport olmasını sağlar.

#### `purpur.sign.color`

- **Varsayılan**: `None`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **Varsayılan**: `None`

Levha üzerinde okunabilirlik kodu`(&o)` kullanılmasına izin verir.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.levha.stili`

- **Varsayılan**: `None`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.söndür`

- **Varsayılan**: `None`

Oyuncuların TNT patlamasını `etkileşim` ile engellemesine izin verir.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Verilen izinler

#### `plazma.bypass.ncr-gereksinimi`

- **Varsayılan**: `None`

Oyuncuların [`NoChatReports`](https://modrinth.com/mod/no-chat-reports) modu yüklü olmasa bile giriş yapmasına izin verir.

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Operatör.

[^2]: Örnek: `ender_dragon`
