---
description: Sužinokite dažniausiai užduodamus klausimus.
---

# ⁉️ Dažnai užduodami klausimai

{% hint style="info" %}

**Negalite rasti norimo atsakymo?**

Užduokite klausimą bendruomenei naudodami [oficialų Discord serverį](https://discord.gg/MmfC52K8A8) arba [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Plazma neprisijungia

Jei konsolėje rodoma `no main manifest attribute, in plazma-(version).jar`,\
parsisiųstas failas yra kūrimo API failas, todėl iš GitHub puslapio turite parsisiųsti **Reobf Paperweight**.

Norėdami sužinoti daugiau, žiūrėkite šį puslapį.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Kiekvieną kartą, kai pradedamas serveris, rodomas įspėjimas

Plazma turi keletą nestabilumo pataisų ir gali neteisingai veikti, todėl serveris rodo šį įspėjimą kiekvieną kartą, kai pradedamas

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Šis įspėjimas gali būti išjungtas naudojant [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] sistemos savybę.

Norėdami sužinoti daugiau, žiūrėkite šį puslapį.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Galima naudoti nuo 1.20.1
