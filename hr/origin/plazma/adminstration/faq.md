---
description: Saznajte više o često postavljanim pitanjima.
---

# ⁉️ Često postavljana pitanja

{% hint style="info" %}

### Ne možete pronaći željeni odgovor?

Pitajte zajednicu putem [Službenog Discord poslužitelja](https://discord.gg/MmfC52K8A8) ili [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!
{% endhint %}

### Poruka se prikazuje ali se ne izvršava

Ako se u konzoli prikaže `no main manifest attribute, in plazma-(version).jar`,\
znači da je preuzeta datoteka razvojna datoteka API-ja i trebate preuzeti **Reobf Paperweight** sa GitHub stranice.

Za više informacija pogledajte sljedeću stranicu.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Upozorenje se prikazuje svaki put kad se poslužitelj pokrene

Plazma sadrži neke nestabilne zakrpe i uvijek postoji mogućnost pogrešnog rada, stoga prilikom pokretanja poslužitelja prikazuje sljedeću upozoravajuću poruku.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Ova upozoravajuća poruka se može onemogućiti korištenjem [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1) sistemskog svojstva.

Za više informacija pogledajte sljedeću stranicu.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Dostupno od verzije 1.20.1
