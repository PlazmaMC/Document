---
description: Zjistěte odpovědi na často kladené otázky.
---

# ⁉️ Často kladené otázky

{% hint style="info" %}

**Nemůžete najít požadovanou odpověď?**

Zeptejte se komunity na [Oficiálním Discord serveru](https://discord.gg/MmfC52K8A8) nebo na [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Problém s nezdařeným spuštěním zprávy

Pokud se v konzoli zobrazí `no main manifest attribute, in plazma-(version).jar`,\
stažený soubor je vývojovým API souborem, musíte stáhnout **Reobf Paperweight** z GitHub stránky.

Pro detailní informace se podívejte na následující stránku.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Při každém spuštění serveru se zobrazuje varování

Plazma obsahuje některé nestabilní opravy a vždy může dojít k chybám, proto server při spuštění vypisuje následující varování.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Toto varování lze deaktivovat pomocí systémové vlastnosti [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Pro detailní informace se podívejte na následující stránku.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Dostupné od verze 1.20.1
