---
description: Leer meer over veelgestelde vragen.
---

# ⁉️ Veelgestelde vragen

{% hint style="info" %}

**Kunt u het gewenste antwoord niet vinden?**

Stel uw vragen aan de community via de [officiële Discord-server](https://discord.gg/MmfC52K8A8) of [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### De uitvoering mislukt met een bericht

Als er een bericht wordt weergegeven met `geen hoofdmanifestattribuut in plazma-(versie).jar`,\
dan is het gedownloade bestand een ontwikkelings-API-bestand en moet u **Reobf Paperweight** downloaden vanaf de GitHub-pagina.

Raadpleeg de volgende pagina voor meer informatie.

{% content-ref url="getting-started/" %}
[starten](getting-started#id-2)
{% endcontent-ref %}

### Er wordt bij elke start van de server een waarschuwing weergegeven

Plazma bevat enkele onstabiele patches en heeft daarom altijd het risico op storingen. Daarom wordt de volgende waarschuwing weergegeven wanneer de server wordt gestart.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Deze waarschuwing kan worden uitgeschakeld met behulp van de [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] systeemeigenschap.

Raadpleeg de volgende pagina voor meer informatie.

{% content-ref url="reference/arguments.md" %}
[argumenten.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Beschikbaar vanaf 1.20.1
