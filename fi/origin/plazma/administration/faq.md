---
description: Selvitä usein kysytyt kysymykset.
---

# ⁉️ Usein kysytyt kysymykset

{% vinkki tyyli="info" %}

**Etkö löydä haluamaasi vastausta?**

Kysy yhteisöltä [virallisella Discord-palvelimella](https://discord.gg/MmfC52K8A8) tai [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) -sivustolla!

{% endhint %}

### Plazma ei käynnisty

Jos konsolissa ilmestyy `no main manifest attribute, in plazma-(version).jar` viesti,\
ladattu tiedosto on kehitystarkoituksiin tarkoitettu API-tiedosto, ja sinun pitää ladata **Reobf Paperweight** GitHub-sivulta.

Lisätietoja löytyy seuraavalta sivulta.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Palvelimen käynnistyessä varoitus ilmestyy

Plazma sisältää joitain epävakaata korjausta ja saattaa aina toimia virheellisesti, joten se näyttää seuraavan varoituksen palvelimen käynnistyessä.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Tämä varoitus voidaan poistaa käytössä [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] järjestelmäominaisuudella.

Lisätietoja löytyy seuraavalta sivulta.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Saatavilla alkaen 1.20.1
