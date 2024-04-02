---
description: Find svar på ofte stillede spørgsmål.
---

# ⁉️ Ofte stillede spørgsmål

{% hint style="info" %}

**Kan du ikke finde det svar, du leder efter?**

Spørg fællesskabet via [Officiel Discord-server](https://discord.gg/MmfC52K8A8) eller [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Handlingen udføres ikke med en besked, der vises

Hvis der vises 'ingen hovedmanifestattribut i plazma-(version).jar' i konsollen,\
filen, du har downloadet, er en udviklings-API-fil, og du skal downloade **Reobf Paperweight** fra GitHub-siden.

Se nærmere på følgende side for mere information.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Advarsler vises hver gang serveren starter

Plazma indeholder nogle ustabile patches og kan potentielt mislykkes, derfor vises følgende advarsler, når serveren starter.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Disse advarsler kan deaktiveres ved hjælp af systemegenskaben [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Se nærmere på følgende side for mere information.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Tilgængelig fra version 1.20.1
