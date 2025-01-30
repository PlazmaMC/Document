---
description: Узнайте о разрешениях Plazma.
---

# 🛡️ Разрешение

Права - это простой инструмент безопасности, который определяет диапазон взаимодействия игроков на сервере.

Для правильного использования и удобного изменения прав необходимо использовать плагины, такие как [LuckPerms](https://luckperms.net).

***

## Понимание базовой системы прав <a href="#id-1" id="id-1"></a>

В Minecraft предоставляются базовые группы управления правами.

운영자[^1] 및 명령 블록의 권한을 설정할 수 있으며, [서버 속성](configurations/property.md)에서 수정할 수 있습니다.

1. **Игроки**\
   Это общая группа прав, предоставляемая всем игрокам.
2. **Посредники**\
   Могут игнорировать защиту спавна.
3. **Администраторы мира**\
   Могут использовать все команды и командные блоки, связанные с управлением миром.\
   Это базовая группа прав, применяемая к датапакам и командным блокам.
4. **Администраторы**\
   Могут использовать все команды, связанные с управлением игроками.
5. **Главные администраторы**\
   Могут использовать все команды, включая управление сервером.\
   Это базовая группа прав, применяемая к консоли и администраторам.

***

## Настройка прав <a href="#id-2" id="id-2"></a>

***

## Все права <a href="#id-3" id="id-3"></a>

***

#### `allow.ride.(Namespaced Key)`

- **По умолчанию**: `Нет`

Позволяет игрокам усаживаться на существо, присаживаясь и взаимодействуя с ним.

Когда игрок садится на существо, он может управлять его движением с помощью клавиш перемещения и прыгать или летать с помощью клавиши прыжка.

В `(Namespaced Key)` указывается [Namespaced ID](#user-content-fn-2)[^2] существа.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `allow.special.(Namespaced Key)`

- **По умолчанию**: `Нет`

Позволяет игрокам использовать особые навыки существа, на котором они находятся.

Не все существа могут использовать особые навыки. Смотрите список всех доступных особых навыков ниже.

{% hint style="info" %}
**특수 기술에 대한 좋은 아이디어가 있나요?**

Поделитесь своими идеями на [Plazma Discord](https://plazmamc.org/discord) или [GitHub Discussions](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!
{% endhint %}

<details>

<summary>Посмотреть текущие доступные особые навыки</summary>

- **`crepper`**\
  При нажатии клавиши прыжка существо взрывается.\
  Если у игрока есть право `allow.powered.creeper`, он может зарядить взрыв, удерживая клавишу прыжка.
- **`dolphin`**\
  При нажатии клавиши прыжка существо делает рывок.
- **`phantom`**\
  При нажатии клавиши прыжка существо выпускает огонь.
- **`wither`**\
  При взаимодействии существо выпускает головы витера.

</details>

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `(Entity) > ridable`을 활성화 한 경우에만 작동합니다.**
{% endhint %}

#### `bukkit.command.compass`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/compass`](commands.md#compass).

#### `bukkit.command.credits`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/credits (Игрок)`](commands.md#credits).

Добавив `.other` после названия права, можно разрешить использовать его другим игрокам.

#### `bukkit.command.demo`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/demo (Игрок)`](commands.md#demo).

Добавив `.other` после названия права, можно разрешить использовать его другим игрокам.

#### `bukkit.command.ping`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/ping (Игрок)`](commands.md#ping).

Добавив `.other` после названия права, можно разрешить использовать его другим игрокам.

#### `bukkit.command.ram`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/ram`](commands.md#ram).

#### `bukkit.command.rambar`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/rambar (Игрок)`](commands.md#rambar).

Добавив `.other` после названия права, можно разрешить использовать его другим игрокам.

#### `bukkit.command.restart`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/restart`](commands.md#restart).

#### `bukkit.command.tps`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/tps`](commands.md#tps).

#### `bukkit.command.tpsbar`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/tpsbar (Игрок)`](commands.md#tpsbar).

Добавив `.other` после названия права, можно разрешить использовать его другим игрокам.

#### `bukkit.command.timings`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/timings`](commands.md#timings).

{% hint style="warning" %}
**해당 명령어는 사용이 중단되었습니다.**

Для аналогичной функциональности смотрите [Spark](https://spark.lucko.me/docs/Command-Usage).
{% endhint %}

#### `bukkit.command.uptime`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду [`/uptime`](commands.md#uptime).

#### `minecraft.command.gamemode.(GameMode)`

- **По умолчанию**: `Администратор мира`

Позволяет использовать команду `/gamemode (GameMode) (Игрок)`.

Добавив `.other` после названия права, можно разрешить использовать его другим игрокам.

#### `paper.antixray.bypass`

- **По умолчанию**: `Нет`

[X-Ray 차단](../expert/xray.md)이 활성화 되어 있는 경우, 권한이 등록된 플레이어에게는 X-Ray 차단용 블록 난독화를 진행하지 않습니다.

Это позволяет улучшить производительность обеих сторон.

> Для получения информации о настройке X-Ray обратитесь к следующей странице.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **По умолчанию**: `Нет`

{% hint style="warning" %}
해당 권한은 1.20.5에서 `plazma.bypass.watchdog` 으로 변경될 예정입니다.
{% endhint %}

#### `purpur.anvil.color`

- **По умолчанию**: `Нет`

모루에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.format`

- **По умолчанию**: `Нет`

모루에 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)을 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.minimessage`

- **По умолчанию**: `Нет`

Позволяет использовать [MiniMessage теги](https://docs.advntr.dev/minimessage/format.html) на наковальнях.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-minimessages`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.anvil.remove_italics`

- **По умолчанию**: `Нет`

모루에 [`&r` 스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)로 `글자 기울임`을 비활성화 할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `anvil > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.book.color.sign`

- **По умолчанию**: `Нет`

플레이어가 책을 서명하면 [스타일링 코드](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)가 적용되도록 합니다.

#### `purpur.bypassIdleKick`

- **По умолчанию**: `Нет`

Исключает игроков из списка целей для выгрузки из-за бездействия.

#### `purpur.debug.f3n`

- **По умолчанию**: `Администратор мира`

Позволяет игрокам изменять режим игры клавишей `F3 + N`.

Это действие возможно только при наличии соответствующего разрешения.

#### `purpur.drop.spawners`

- **По умолчанию**: `Нет`

При добыче спаунерного блока игроки получат сам спаунерный блок.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **По умолчанию**: `Нет`

Изменяет размер эндерсундука.

В `(NumberString)` можно указать `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `ender_chest > six-rows` 및 `ender_chest > use-permissions-for-rows`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.inventory_totem`

- **По умолчанию**: `Нет`

Позволяет использовать тотем бессмертия из инвентаря.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `totem-of-undying-works-in-inventory`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.joinFullServer`

- **По умолчанию**: `Нет`

Разрешить игроку игнорировать ограничение на количество подключений.

#### `purpur.mending_shift_click`

- **По умолчанию**: `Нет`

Разрешить игроку починить предмет, который он держит, когда он `приседает и взаимодействует`.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `shift-right-click-repairs-mending-points`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.place.spawners`

- **По умолчанию**: `Нет`

Разрешить игроку устанавливать спаунеры.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `gameplay-mechanics > silk-touch`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.portal.instant`

- **По умолчанию**: `Нет`

Позволить игроку мгновенно телепортироваться при использовании портала в Нижний мир.

#### `purpur.sign.color`

- **По умолчанию**: `Нет`

표지판에 [색 코드](https://minecraft.wiki/w/Formatting\_codes#Color\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.magic`

- **По умолчанию**: `Нет`

Разрешить использование кода`(&o)` для шифрования на указателях.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.sign.style`

- **По умолчанию**: `Нет`

표지판에 [스타일링 코드 `(&o 제외)`](https://minecraft.wiki/w/Formatting\_codes#Formatting\_codes)를 사용할 수 있도록 허용합니다.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `sign > allow-colors`를 활성화 해야 작동합니다.**
{% endhint %}

#### `purpur.tnt.defuse`

- **По умолчанию**: `Нет`

Разрешить игрокам `взаимодействовать` с TNT ножницами, чтобы предотвратить взрыв.

{% hint style="info" %}
[**Purpur 세계별 구성**](configurations/purpur/world.md)**에서 `defuse-tnt-change`가 `0.0` 이상이어야 작동합니다.**
{% endhint %}

### Предоставляемые разрешения

#### `plazma.bypass.ncr-require`

- **По умолчанию**: `Нет`

Разрешить игрокам подключаться, даже если у них не установлен мод [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}
[**Plazma 세계별 구성**](configurations/plazma/world.md)**에서 `no-chat-reports > require-install`를 활성화 해야 작동합니다.**
{% endhint %}

***

[^1]: Оператор.

[^2]: Например: `ender_dragon`
