---
description: Descubre las preguntas frecuentes.
---

# ⁉️ Preguntas frecuentes

{% hint style="info" %}

**¿No puedes encontrar la respuesta que buscas?**

¡Haz preguntas a la comunidad a través del [servidor Discord oficial](https://discord.gg/MmfC52K8A8) o [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### El programa no se ejecuta y muestra un mensaje

Si aparece `no main manifest attribute, in plazma-(version).jar` en la consola,\
el archivo descargado es un archivo de API de desarrollo y debes descargar **Reobf Paperweight** desde la página de GitHub.

Consulta la siguiente página para obtener más información.

{% content-ref url="getting-started/" %}
[inicio](getting-started#id-2)
{% endcontent-ref %}

### Se muestra una advertencia cada vez que se inicia el servidor

Plazma contiene parches inestables y siempre existe la posibilidad de mal funcionamiento, por lo que muestra advertencias al iniciar el servidor.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Puedes desactivar esta advertencia utilizando la propiedad del sistema [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Consulta la siguiente página para obtener más información.

{% content-ref url="reference/arguments.md" %}
[argumentos.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Disponible a partir de la versión 1.20.1
