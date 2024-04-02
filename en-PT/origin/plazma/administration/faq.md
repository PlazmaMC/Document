---
description: Learn about the frequently asked questions, ye scallywag.
---

# ⁉️ Frequently Asked Questions

{% hint style="info" %}

**Arrr ye not be findin' th' answer ye be lookin' fer?**

[Official Discord Server](https://discord.gg/MmfC52K8A8) or [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) be where ye can ask the community!

{% endhint %}

### Execution be not happenin' with a message bein' displayed

If `no main manifest attribute, in plazma-(version).jar` be showin' in the console, the downloaded file be a development API file, and ye need to download **Reobf Paperweight** from the GitHub page.

To learn more in detail, be referrin' to the followin' page.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Warnings be displayed every time the server be startin'

Plazma be containin' some unstable patches and may always have a chance of malfunction, hence the server be displayin' the followin' warning message each time it starts.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Ye can disable the said warning message usin' the [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] system property.

To learn more in detail, be referrin' to the followin' page.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Available from 1.20.1
