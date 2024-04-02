---
description: Дізнайтеся більше про часто задавані питання.
---

# ⁉️ Часті питання

{% нагадування стилю="інформація" %}

**Не можна знайти бажану відповідь?**

Задайте питання спільноті через [офіційний Discord сервер](https://discord.gg/MmfC52K8A8) або [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% кінець нагадування %}

### Повідомлення виводиться, але не виконується

Якщо у консолі виводиться `no main manifest attribute, in plazma-(version).jar`,\
завантажений файл є файлом API для розробників, вам потрібно завантажити **Reobf Paperweight** зі сторінки GitHub.

Для отримання докладної інформації див. наступну сторінку.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Під час запуску сервера відображається попередження

Plazma містить деякі нестабільні патчі і завжди може працювати некоректно, тому виводить попередження під час запуску сервера.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Це попередження можна вимкнути за допомогою системного властивості [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Для отримання докладної інформації див. наступну сторінку.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Доступно з версії 1.20.1
