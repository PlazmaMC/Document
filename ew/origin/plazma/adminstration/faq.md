---
description: Check out frequently asked questions.
---

# ⁉️ Frequently Asked Questions

{% hint style="info" %}

### Can't find the answer you're looking for?

Ask the community through the [Official Discord Server](https://discord.gg/MmfC52K8A8) or [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!
{% endhint %}

### The message is displayed but not executed

If `no main manifest attribute, in plazma-(version).jar` is displayed in the console,\
the downloaded file is a development API file, and you should download **Reobf Paperweight** from the GitHub page.

Refer to the following page for more details.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### A warning is displayed every time the server starts

Plazma contains some unstable patches and may always malfunction, so the server displays the following warning when it starts.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

This warning can be disabled using the [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] system property.

Refer to the following page for more details.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Available from 1.20.1
