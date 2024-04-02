---
description: Узнайте ответы на часто задаваемые вопросы.
---

# ⁉️ Часто задаваемые вопросы

{% hint style="info" %}

**Не можете найти нужный ответ?**

Задайте вопрос сообществу через [официальный сервер Discord](https://discord.gg/MmfC52K8A8) или [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### При выполнении появляется сообщение, но ничего не происходит

Если в консоли выводится сообщение `no main manifest attribute, in plazma-(version).jar`,\
значит загруженный файл является файлом API для разработки, и вам нужно скачать **Reobf Paperweight** с GitHub страницы.

Для получения подробной информации посетите следующую страницу.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### При запуске сервера появляется предупреждение

Plazma содержит некоторые нестабильные патчи и всегда может некорректно работать, поэтому при запуске сервера выводится следующее предупреждение.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Это предупреждение можно отключить с помощью системного свойства [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Для получения подробной информации посетите следующую страницу.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Доступно с версии 1.20.1
