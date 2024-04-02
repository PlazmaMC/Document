---
description: Scopri le domande frequenti.
---

# ⁉️ Domande frequenti

{% hint style="info" %}

**Non riesci a trovare la risposta che stai cercando?**

Fai domande alla comunità tramite il [server Discord ufficiale](https://discord.gg/MmfC52K8A8) o [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Plazma non si avvia

Se compare `no main manifest attribute, in plazma-(version).jar` sulla console,\
il file scaricato è un file API di sviluppo, è necessario scaricare **Reobf Paperweight** dalla pagina GitHub.

Per ulteriori informazioni, consulta la seguente pagina.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Viene visualizzato un avviso ogni volta che il server viene avviato

Plazma contiene alcune patch instabili e potrebbe non funzionare correttamente, quindi mostra il seguente avviso ogni volta che il server viene avviato.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Questo avviso può essere disattivato utilizzando la proprietà di sistema [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Per ulteriori informazioni, consulta la seguente pagina.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Disponibile a partire dalla versione 1.20.1
