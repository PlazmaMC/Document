---
description: Finn ut mer om vanlige spørsmål.
---

# ⁉️ Vanlige spørsmål

{% hint style="info" %}

**Finner du ikke svaret du leter etter?**

Spør fellesskapet via [offisiell Discord-server](https://discord.gg/MmfC52K8A8) eller [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Plazma starter ikke

Hvis du ser `no main manifest attribute, in plazma-(versjon).jar` i konsollen,\
filen du lastet ned er en utvikler-API-fil, du må laste ned **Reobf Paperweight** fra GitHub-siden.

Se følgende side for mer informasjon.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### En advarsel vises hver gang serveren starter

Plazma inneholder noen ustabile patcher og kan alltid ha en risiko for feilfunksjon, derfor viser den følgende advarselen hver gang serveren starter.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Denne advarselen kan deaktiveres ved å bruke [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1) systemegenskap.

Se følgende side for mer informasjon.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Tilgjengelig fra 1.20.1
