---
description: Ismerje meg a gyakran ismételt kérdéseket.
---

# ⁉️ Gyakran Ismételt Kérdések

{% hint style="info" %}

**Nem találja a kívánt választ?**

[Hivatalos Discord szerver](https://discord.gg/MmfC52K8A8) vagy [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) oldalon tegye fel kérdését a közösségnek!

{% endhint %}

### Az üzenet megjelenik, de nem fut le

Ha a `no main manifest attribute, in plazma-(version).jar` üzenet jelenik meg a konzolon, akkor a letöltött fájl a fejlesztői API fájl, és a GitHub oldalról letöltendő a **Reobf Paperweight**.

További információért tekintse meg a következő oldalt.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### A szerver indításakor figyelmeztetés jelenik meg

A Plazma néhány instabil javítást tartalmaz, és mindig fennáll a hibás működés lehetősége, ezért a szerver indításakor ilyen figyelmeztetéseket jelenít meg.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Ezt a figyelmeztetést a [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] rendszer tulajdonság használatával lehet kikapcsolni.

További információért tekintse meg a következő oldalt.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Elérhető 1.20.1 verziótól
