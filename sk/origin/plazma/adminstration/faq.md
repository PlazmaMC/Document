---
description: Zistite odpovede na často kladené otázky.
---

# ⁉️ Často kladené otázky

{% hint style="info" %}

### Nenašli ste požadovanú odpoveď?

Skúste sa obrátiť na komunitu cez [Oficiálny Discord server](https://discord.gg/MmfC52K8A8) alebo [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!
{% endhint %}

### Problém s vykonaním a zobrazením správy

Ak sa zobrazí chyba `no main manifest attribute, in plazma-(version).jar`,\
súbor, ktorý ste stiahli, je vývojovým API súborom a musíte si stiahnuť **Reobf Paperweight** z GitHub stránky.

Ak chcete získať viac informácií, pozrite si nasledujúcu stránku.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Pri spustení servera sa zobrazuje upozornenie

Plazma obsahuje niektoré nestabilné zmeny a môže sa vždy chybovať, preto sa pri spustení servera zobrazuje nasledujúce upozornenie.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Toto upozornenie je možné deaktivovať pomocou systémového vlastnosti [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Ak chcete získať viac informácií, pozrite si nasledujúcu stránku.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Dostupné od verzie 1.20.1
