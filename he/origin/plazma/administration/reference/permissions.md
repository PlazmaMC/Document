---
description: לקבלת מידע על הרשאות ה-Plazma.
---

# 🛡️ הרשאה

הרשאה היא כלי אבטחה פשוט שמגדיר את הטווח שבו ניתן לשחקן בשרת לפעול ביחס לשחקן אחר.

כדי להשתמש בהרשאות כראוי ולערוך אותן בקלות, יש להשתמש בתוסף כגון [LuckPerms](https://luckperms.net).

***

## 기본 권한 체계 이해하기 <a href="#id-1" id="id-1"></a>

Minecraft에서는 기본적인 관리 권한 그룹을 제공하고 있습니다.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **플레이어**\
   일반적으로 모든 플레이어어게 주어지는 권한 그룹입니다.
2. **중재자**\
   스폰 보호를 무시할 수 있습니다.
3. **세계 관리자**\
   세계 관리와 관련된 모든 명령어와 명령 블록을 사용할 수 있습니다.\
   데이터팩 및 명령 블록에 기본 적용되는 권한 그룹입니다.
4. **관리자**\
   플레이어 관리와 관련된 모든 명령어를 사용할 수 있습니다.
5. **총관리자**\
   서버 관리를 포함한 모든 명령어를 사용할 수 있습니다.\
   콘솔 및 운영자에게 기본 적용되는 권한 그룹입니다.

***

## 권한 설정하기 <a href="#id-2" id="id-2"></a>

***

## 전체 권한 <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **기본 제공**: `없음`

플레이어가 엔티티에 `웅크리고 상호 작용`하여 엔티티를 탑승할 수 있도록 허용합니다.

엔티티를 탑승하면 `이동 키`로 엔티티의 이동을 조작할 수 있으며, `점프 키`로 점프하거나 날 수 있습니다.

`(Namespaced Key)`에는 엔티티의 [Namespaced ID](#user-content-fn-2)[^2]가 입력됩니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **[הגדרות העולם של Purpur](configurations/purpur/world.md)**: פעולה זו תתקיים רק אם הופעלה האפשרות `(Entity) > ניתן לרכוב`.

플레이어가 엔티티를 탑승하고 있을 때, 엔티티의 특수 기술을 사용할 수 있도록 허용합니다.

모든 엔티티의 특수 기능이 사용 가능한 것은 아닙니다. 사용 가능한 전체 특수 기술은 아래를 참고하세요.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

[Plazma Discord](https://plazmamc.org/discord) 또는 [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)에 아이디어를 게시해 주세요!
{% endhint %}

<details>

<summary>현재 사용 가능한 특수 기술 보기</summary>

- **`crepper`**\
  `점프 키`를 누르면 폭발합니다.\
  플레이어가 `allow.powered.creeper` 권한을 가지고 있으면, `점프 키`를 꾹 눌러 충전할 수 있습니다.
- **`dolphin`**\
  `점프 키`를 누르면 돌진합니다.
- **`phantom`**\
  `점프 키`를 누르면 화염을 발사합니다.
- **`wither`**\
  `상호 작용`하면 위더 머리를 발사합니다.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **기본 제공**: `세계 관리자`

[`/compass` 명령어](commands.md#compass) 사용을 허용합니다.

#### `bukkit.command.credits`

- **ברירת המחדל**: `מנהל עולם`

[`/credits (Player)` 명령어](commands.md#credits) 사용을 허용합니다.

כאשר מזינים `.other` אחרי שם ההרשאה, מאפשרים לשחקן אחר להשתמש בה.

#### `bukkit.command.demo`

- **ברירת המחדל**: `מנהל עולם`

[`/demo (Player)` 명령어](commands.md#demo) 사용을 허용합니다.

כאשר מזינים `.other` אחרי שם ההרשאה, מאפשרים לשחקן אחר להשתמש בה.

#### `bukkit.command.ping`

- **ברירת המחדל**: `מנהל עולם`

[`/ping (Player)` 명령어](commands.md#ping) 사용을 허용합니다.

권한명 뒤에 `.other` 를 입력하면 다른 플레이어에게 사용할 수 있도록 허용합니다.

#### `bukkit.command.ram`

- **ברירת המחדל**: `מנהל עולם`

[`/ram` 명령어](commands.md#ram) 사용을 허용합니다.

#### `bukkit.command.rambar`

- **ברירת המחדל**: `מנהל עולם`

[`/rambar (Player)` 명령어](commands.md#rambar) 사용을 허용합니다.

כאשר מזינים `.other` אחרי שם ההרשאה, מאפשרים לשחקן אחר להשתמש בה.

#### `bukkit.command.restart`

- **ברירת המחדל**: `מנהל עולם`

[`/restart` 명령어](commands.md#restart) 사용을 허용합니다.

#### `bukkit.command.tps`

- **ברירת המחדל**: `מנהל עולם`

[`/tps` 명령어](commands.md#tps) 사용을 허용합니다.

#### `bukkit.command.tpsbar`

- **ברירת המחדל**: `מנהל עולם`

[`/tpsbar (Player)` 명령어](commands.md#tpsbar) 사용을 허용합니다.

כאשר מזינים `.other` אחרי שם ההרשאה, מאפשרים לשחקן אחר להשתמש בה.

#### `bukkit.command.timings`

- **ברירת המחדל**: `מנהל עולם`

[`/timings` 명령어](commands.md#timings) 사용을 허용합니다.

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

비슷한 기능을 가지는 명령어에 대해 알아보려면 [Spark](https://spark.lucko.me/docs/Command-Usage)를 확인하세요.
{% endhint %}

#### `bukkit.command.uptime`

- **ברירת המחדל**: `מנהל עולם`

[`/uptime` 명령어](commands.md#uptime) 사용을 허용합니다.

#### `minecraft.command.gamemode.(GameMode)`

- **ברירת המחדל**: `מנהל עולם`

`/gamemode (GameMode) (Player)` 명령어 사용을 허용합니다.

כאשר מזינים `.other` אחרי שם ההרשאה, מאפשרים לשחקן אחר להשתמש בה.

#### `paper.antixray.bypass`

- **ברירת המחדל**: `אין`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

이렇게 하면 양 측 모두 성능 향상을 경험할 수 있습니다.

> X-Ray 설정 방법에 대해 알아보려면 아래 페이지를 참고하세요.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **기본 제공**: `없음`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **ברירת המחדל**: `אין`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **ברירת המחדל**: `אין`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **ברירת המחדל**: `אין`

모루에 [MiniMessage 태그](https://docs.advntr.dev/minimessage/format.html)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **ברירת המחדל**: `אין`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **ברירת המחדל**: `אין`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **기본 제공**: `없음`

플레이어를 유휴 상태 추방 대상에서 제외합니다.

#### `purpur.debug.f3n`

- **ברירת המחדל**: `מנהל עולם`

플레이어가 `F3 + N` 키로 게임 모드를 변경할 수 있도록 허용합니다.

해당 게임모드에 대한 권한이 없으면 작동하지 않습니다.

#### `purpur.drop.spawners`

- **ברירת המחדל**: `אין`

구성에서 설정한 아이템으로 스포너 블록을 채굴하면 스포너 블록을 떨어뜨립니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **ברירת המחדל**: `אין`

엔더 상자의 크기를 변경합니다.

`(NumberString)`에는 `one`, `two`, `three`, `four`, `five`, `six`를 입력할 수 있습니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **ברירת המחדל**: `אין`

אפשר תותם של אין-מוות גם כאשר הוא נמצא בתיק האביזרים.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **ברירת המחדל**: `אין`

להתיר לשחקן להתעלם ממגבלת מספר המשתתפים.

#### `purpur.mending_shift_click`

- **ברירת המחדל**: `אין`

לאפשר לשחקן לתקן פריט שהוא נשא עליו כאשר הוא מתעקש.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **ברירת המחדל**: `אין`

להתיר לשחקן להתקין ספאוונרים.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **ברירת המחדל**: `אין`

לאפשר לשחקן להעביר באופן מיידי כאשר הוא משתמש בשערי נדר.

#### `purpur.sign.color`

- **ברירת המחדל**: `אין`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **ברירת המחדל**: `אין`

לאפשר שימוש בקודי מטען `(&o)` בלוחות.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **ברירת המחדל**: `אין`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **ברירת המחדל**: `אין`

להתיר לשחקן למנוע פיצוץ של TNT על ידי שימוש במספרים.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### הרשאות מוצעות

#### `plazma.bypass.ncr-require`

- **ברירת המחדל**: `אין`

להתיר לשחקן להתחבר גם בלעדי התקנת המוד [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: אופרטור.

[^2]: למשל: `ender_dragon`
