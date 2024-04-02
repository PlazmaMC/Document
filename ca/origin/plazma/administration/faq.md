---
description: Descobreix més sobre les preguntes freqüents.
---

# ⁉️ Preguntes freqüents

{% hint style="info" %}

**No trobeu la resposta que busqueu?**

Feu preguntes a la comunitat a través del [servidor Discord oficial](https://discord.gg/MmfC52K8A8) o [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### No s'executa amb un missatge de sortida

Si apareix `no main manifest attribute, in plazma-(versió).jar` a la consola, el fitxer descarregat és un fitxer API de desenvolupament, heu de descarregar **Reobf Paperweight** de la pàgina de GitHub.

Per obtenir més informació, consulteu la següent pàgina.

{% content-ref url="getting-started/" %}
[inici](getting-started#id-2)
{% endcontent-ref %}

### Es mostra un advertència cada vegada que el servidor s'inicia

Plazma conté algunes correccions inestables i sempre pot funcionar incorrectament, per això mostra aquest missatge d'avís cada vegada que el servidor s'inicia.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Aquest missatge d'avís es pot desactivar utilitzant la propietat del sistema [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Per obtenir més informació, consulteu la següent pàgina.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Disponible a partir de la versió 1.20.1
