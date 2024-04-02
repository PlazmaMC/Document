---
description: Sıkça Sorulan Soruları İnceleyin.
---

# ⁉️ Sıkça Sorulan Sorular

{% hint style="info" %}

**Aradığınız cevabı bulamadınız mı?**

[Resmi Discord Sunucusu](https://discord.gg/MmfC52K8A8) veya [GitHub Sorunları](https://github.com/PlazmaMC/PlazmaBukkit/issues) üzerinden topluluktan yardım alın!

{% endhint %}

### Plazma başlatılamıyor

Eğer konsolda `no main manifest attribute, in plazma-(version).jar` şeklinde bir çıktı alıyorsanız, indirdiğiniz dosya geliştirme amaçlı bir API dosyasıdır, GitHub sayfasından **Reobf Paperweight**'i indirmeniz gerekmektedir.

Daha fazla bilgi için aşağıdaki sayfaya bakın.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Her sunucu başlatıldığında uyarılar görüntülenir

Plazma bazı kararsız yamalar içerir ve her zaman yanlış çalışma olasılığı bulunduğu için sunucu başlatıldığında aşağıdaki uyarıları görüntüler.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Bu uyarılar [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] sistem özelliği kullanılarak devre dışı bırakılabilir.

Daha fazla bilgi için aşağıdaki sayfaya bakın.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: 1.20.1'den itibaren kullanılabilir
