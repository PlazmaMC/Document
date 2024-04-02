---
description: Научете повече за често задавани въпроси.
---

# ⁉️ Често задавани въпроси

{% hint style="info" %}

**Не можете ли да намерите желания отговор?**

Попитайте общността чрез [официалния Discord сървър](https://discord.gg/MmfC52K8A8) или [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Plazma не се стартира

Ако в конзолата се извежда `no main manifest attribute, in plazma-(version).jar`,\
това означава, че файла, който сте изтеглили, е API файл за разработка и трябва да изтеглите **Reobf Paperweight** от страницата на GitHub.

За повече информация, вижте следната страница.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Предупреждение се извежда всеки път при стартиране на сървъра

Plazma включва някои нестабилни поправки и винаги има вероятност за неизправност, поради което извежда това предупреждение при стартиране на сървъра.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Това предупреждение може да бъде деактивирано с помощта на системното свойство [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

За повече информация, вижте следната страница.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: На разположение от версия 1.20.1
