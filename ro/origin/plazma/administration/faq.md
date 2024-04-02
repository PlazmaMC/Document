---
description: Aflați mai multe despre întrebările frecvente.
---

# ⁉️ Întrebări frecvente

{% hint style="info" %}

**Nu găsiți răspunsul dorit?**

Întrebați comunitatea prin intermediul [serverului oficial de Discord](https://discord.gg/MmfC52K8A8) sau al [problemelor de pe GitHub](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Execuția nu se realizează cu un mesaj de ieșire.

Dacă apare în consolă `no main manifest attribute, in plazma-(version).jar`,\
fișierul descărcat este un fișier API de dezvoltare, trebuie să descărcați **Reobf Paperweight** de pe pagina GitHub.

Pentru mai multe informații, consultați pagina următoare.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Avertismentul apare de fiecare dată când serverul este pornit.

Plazma conține unele patch-uri instabile și are întotdeauna posibilitatea de a funcționa necorespunzător, prin urmare afișează avertismente similare atunci când serverul este pornit.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Acest avertisment poate fi dezactivat folosind proprietatea de sistem [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Pentru mai multe informații, consultați pagina următoare.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Disponibil începând cu versiunea 1.20.1
