---
description: Узнайте о разрешениях Plazma.
---

# 🛡️ Разрешение

Права - это простой инструмент безопасности, который определяет диапазон взаимодействия игроков на сервере.

Для правильного использования и удобного изменения прав необходимо использовать плагины, такие как [LuckPerms](https://luckperms.net).

***

## Понимание базовой системы прав <a href="#id-1" id="id-1"></a>

В Minecraft предоставляются базовые группы управления правами.

Вы можете устанавливать права для [администраторов](#user-content-fn-1)[^1] и командных блоков, а также изменять их в [настройках сервера](configurations/property.md).

0. **Игроки**\
   Это общая группа прав, предоставляемая всем игрокам.
1. **Посредники**\
   Могут игнорировать защиту спавна.
2. **Администраторы мира**\
   Могут использовать все команды и командные блоки, связанные с управлением миром.\
   Это базовая группа прав, применяемая к датапакам и командным блокам.
3. **Администраторы**\
   Могут использовать все команды, связанные с управлением игроками.
4. **Главные администраторы**\
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

**Работает только при включенном параметре `(Entity) > ridable` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `allow.special.(Namespaced Key)`

- **По умолчанию**: `Нет`

Позволяет игрокам использовать особые навыки существа, на котором они находятся.

Не все существа могут использовать особые навыки. Смотрите список всех доступных особых навыков ниже.

{% hint style="info" %}

**У вас есть хорошая идея для особого навыка?**

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

**Работает только при включенном параметре `(Entity) > ridable` в [настройках мира Purpur](configurations/purpur/world.md).**

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

**Эта команда больше не поддерживается.**

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

Если активировано блокирование X-Ray, игрокам с этим разрешением не будет препятствовано взлому блоков X-Ray.

Это позволяет улучшить производительность обеих сторон.

> Для получения информации о настройке X-Ray обратитесь к следующей странице.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

#### `plazma.bypass-moved-to-quickly-check`

- **По умолчанию**: `Нет`

{% hint style="warning" %}

Это разрешение будет переименовано в `plazma.bypass.watchdog` в версии 1.20.5.

{% endhint %}

#### `purpur.anvil.color`

- **По умолчанию**: `Нет`

Позволяет использовать [цветовые коды](https://minecraft.wiki/w/Formatting_codes#Color_codes) на наковальнях.

{% hint style="info" %}

**Для работы необходимо включить параметр `anvil > allow-colors` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.format`

- **По умолчанию**: `Нет`

Позволяет использовать [стилизацию кода](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) на наковальнях.

{% hint style="info" %}

**Для работы необходимо включить параметр `anvil > allow-colors` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.minimessage`

- **По умолчанию**: `Нет`

Позволяет использовать [MiniMessage теги](https://docs.advntr.dev/minimessage/format.html) на наковальнях.

{% hint style="info" %}

**Для работы необходимо включить параметр `anvil > allow-minimessages` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.anvil.remove_italics`

- **По умолчанию**: `Нет`

Позволяет отключить `курсив` с помощью стилизации `&r` на наковальнях.

{% hint style="info" %}

**Для работы необходимо включить параметр `anvil > allow-colors` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.book.color.sign`

- **По умолчанию**: `Нет`

При подписании книги применяет [стилизацию кода](https://minecraft.wiki/w/Formatting_codes#Formatting_codes).

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

**Для работы необходимо включить параметр `gameplay-mechanics > silk-touch` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.enderchest.rows.(NumberString)`

- **По умолчанию**: `Нет`

Изменяет размер эндерсундука.

В `(NumberString)` можно указать `one`, `two`, `three`, `four`, `five`, `six`.

{% hint style="info" %}

**Для работы необходимо включить параметры `ender_chest > six-rows` и `ender_chest > use-permissions-for-rows` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.inventory_totem`

- **По умолчанию**: `Нет`

Позволяет использовать тотем бессмертия из инвентаря.

{% hint style="info" %}

**Для работы необходимо включить параметр `totem-of-undying-works-in-inventory` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.joinFullServer`

- **По умолчанию**: `Нет`

Разрешить игроку игнорировать ограничение на количество подключений.

#### `purpur.mending_shift_click`

- **По умолчанию**: `Нет`

Разрешить игроку починить предмет, который он держит, когда он `приседает и взаимодействует`.

{% hint style="info" %}

**Для работы необходимо активировать `shift-right-click-repairs-mending-points` в **[конфигурациях мира Purpur](configurations/purpur/world.md)**.**

{% endhint %}

#### `purpur.place.spawners`

- **По умолчанию**: `Нет`

Разрешить игроку устанавливать спаунеры.

{% hint style="info" %}

**Для работы необходимо включить параметр `gameplay-mechanics > silk-touch` в [настройках мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.portal.instant`

- **По умолчанию**: `Нет`

Позволить игроку мгновенно телепортироваться при использовании портала в Нижний мир.

#### `purpur.sign.color`

- **По умолчанию**: `Нет`

Разрешает использование [цветового кода](https://minecraft.wiki/w/Formatting_codes#Color_codes) на табличках.

{% hint style="info" %}

\*\*Для работы необходимо активировать `sign > allow-colors` в **[конфигурациях мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.magic`

- **По умолчанию**: `Нет`

Разрешить использование кода`(&o)` для шифрования на указателях.

{% hint style="info" %}

\*\*Для работы необходимо активировать `sign > allow-colors` в **[конфигурациях мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.sign.style`

- **По умолчанию**: `Нет`

Разрешить использование [стилизующего кода `(&o исключая)`](https://minecraft.wiki/w/Formatting_codes#Formatting_codes) на указателях.

{% hint style="info" %}

\*\*Для работы необходимо активировать `sign > allow-colors` в **[конфигурациях мира Purpur](configurations/purpur/world.md).**

{% endhint %}

#### `purpur.tnt.defuse`

- **По умолчанию**: `Нет`

Разрешить игрокам `взаимодействовать` с TNT ножницами, чтобы предотвратить взрыв.

{% hint style="info" %}

**В [конфигурациях мира Purpur](configurations/purpur/world.md) `defuse-tnt-change` должен быть `0.0` или выше, чтобы функционировало.**

{% endhint %}

### Предоставляемые разрешения

#### `plazma.bypass.ncr-require`

- **По умолчанию**: `Нет`

Разрешить игрокам подключаться, даже если у них не установлен мод [`NoChatReports`](https://modrinth.com/mod/no-chat-reports).

{% hint style="info" %}

**В [конфигурациях мира Plazma](configurations/plazma/world.md) необходимо активировать `no-chat-reports > require-install`, чтобы функционировало.**

{% endhint %}

***

[^1]: Оператор.

[^2]: Например: `ender_dragon`
