---
description: Ketahui tentang soalan lazim.
---

# ⁉️ Soalan Lazim

{% hint style="info" %}

**Tidak dapat menemui jawapan yang anda cari?**

[Server Discord resmi](https://discord.gg/MmfC52K8A8) atau [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) untuk bertanya kepada komunitas!

{% endhint %}

### Plazma tidak dapat dimulakan

Jika `tiada atribut manifest utama, dalam plazma-(versi).jar` dipaparkan di konsol,\
fail yang dimuat turun adalah fail API pembangunan, anda perlu memuat turun **Reobf Paperweight** dari laman GitHub.

Untuk maklumat lanjut, sila rujuk kepada halaman berikut.

{% content-ref url="getting-started/" %}
[mula-mula](getting-started#id-2)
{% endcontent-ref %}

### Amaran dipaparkan setiap kali pelayan dihidupkan

Plazma mengandungi beberapa penyelesaian yang tidak stabil dan sentiasa berpotensi untuk berfungsi dengan tidak baik, oleh itu amaran berikut dipaparkan setiap kali pelayan dihidupkan.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Amaran tersebut boleh dimatikan menggunakan ciri sistem [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Untuk maklumat lanjut, sila rujuk kepada halaman berikut.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Boleh digunakan mulai versi 1.20.1
