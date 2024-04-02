---
description: Сазнајте одговоре на често постављена питања.
---

# ⁉️ Често постављена питања

{% hint style="info" %}

**Не можете да пронађете жељени одговор?**

[Званични Discord сервер](https://discord.gg/MmfC52K8A8) или питања за заједницу на [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) погледајте!

{% endhint %}

### Порука се приказује, али не извршава.

Ако се на конзоли приказује `no main manifest attribute, in plazma-(version).jar`,\
преузета датотека је датотека API-а за развој, и морате преузети **Reobf Paperweight** са GitHub странице.

За више информација, погледајте следећу страницу.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### При покретању сервера приказује се упозорење.

Plazma садржи неке нестабилне исправке и увек постоји могућност неисправног рада, због чега при покретању сервера приказује следећу поруку.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Ова порука се може онемогућити коришћењем системског својства [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

За више информација, погледајте следећу страницу.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Доступно од верзије 1.20.1
