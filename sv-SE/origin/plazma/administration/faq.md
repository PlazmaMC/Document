---
description: Ta reda på vanliga frågor.
---

# ⁉️ Vanliga frågor

{% hint style="info" %}

**Hittar du inte det svar du letar efter?**

Fråga gemenskapen via [Officiell Discord-server](https://discord.gg/MmfC52K8A8) eller [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Plazma startar inte

Om du ser `no main manifest attribute, in plazma-(version).jar` i konsolen,\
har du laddat ner en utvecklar-API-fil, du bör ladda ner **Reobf Paperweight** från GitHub-sidan.

För mer information, se följande sida.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### En varning visas varje gång servern startas

Plazma innehåller vissa instabila patchar och kan därför alltid visa varningar när servern startas.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Denna varning kan inaktiveras med hjälp av systemegenskapen [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

För mer information, se följande sida.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Tillgänglig från version 1.20.1
