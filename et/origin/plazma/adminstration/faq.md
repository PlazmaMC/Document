---
description: Uurige sagedaste küsimuste kohta.
---

# ⁉️ Sagedased küsimused

{% hint style="info" %}

### Kas te ei leia soovitud vastust?

Küsige kogukonna käest küsimusi [ametlikus Discordi serveris](https://discord.gg/MmfC52K8A8) või [GitHubi küsimustes](https://github.com/PlazmaMC/PlazmaBukkit/issues)!
{% endhint %}

### Kui käivitamisel kuvatakse sõnum, siis see ei käivitu

Kui konsoolil kuvatakse `no main manifest attribute, in plazma-(version).jar`,\
tähendab see, et allalaaditud fail on arendusliku API-fail, peate alla laadima GitHubi lehelt **Reobf Paperweight**.

Lisateabe saamiseks vaadake järgmist lehekülge.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Serveri käivitamisel kuvatakse hoiatus

Plazmas on mõned ebastabiilsed parandused ja seetõttu võib alati esineda talitlushäireid, seetõttu kuvab server käivitamisel järgmise hoiatuse.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Seda hoiatust saab keelata kasutades [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] süsteemiatribuuti.

Lisateabe saamiseks vaadake järgmist lehekülge.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Saadaval alates versioonist 1.20.1
