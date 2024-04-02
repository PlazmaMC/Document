---
description: Erfahren Sie mehr über häufig gestellte Fragen.
---

# ⁉️ Häufig gestellte Fragen

{% Hinweis-Stil="info" %}

**Konnten Sie die gewünschte Antwort nicht finden?**

Fragen Sie die Community über den [offiziellen Discord-Server](https://discord.gg/MmfC52K8A8) oder [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Es wird eine Meldung angezeigt, aber das Programm wird nicht ausgeführt.

Wenn in der Konsole `no main manifest attribute, in plazma-(version).jar` angezeigt wird,\
dann haben Sie die Entwicklungs-API-Datei heruntergeladen und müssen **Reobf Paperweight** von der GitHub-Seite herunterladen.

Für weitere Informationen siehe die folgende Seite.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Eine Warnung wird jedes Mal angezeigt, wenn der Server gestartet wird.

Plazma enthält einige instabile Patches und kann daher möglicherweise fehlerhaft funktionieren. Daher werden beim Start des Servers folgende Warnungen angezeigt.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Diese Warnungen können mit dem Systemattribut [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] deaktiviert werden.

Für weitere Informationen siehe die folgende Seite.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Ab Version 1.20.1 verfügbar
