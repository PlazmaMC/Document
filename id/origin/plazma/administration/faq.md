---
description: Pelajari pertanyaan yang sering diajukan.
---

# ⁉️ Pertanyaan yang Sering Diajukan

{% hint style="info" %}

**Tidak dapat menemukan jawaban yang Anda cari?**

[Server Discord resmi](https://discord.gg/MmfC52K8A8) atau [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) untuk bertanya kepada komunitas!

{% endhint %}

### Pesan muncul tetapi tidak berjalan

Jika `no main manifest attribute, in plazma-(version).jar` muncul di konsol,\
file yang diunduh adalah file API pengembangan, Anda perlu mengunduh **Reobf Paperweight** dari halaman GitHub.

Untuk informasi lebih lanjut, lihat halaman berikut.

{% content-ref url="getting-started/" %}
[mulai](getting-started#id-2)
{% endcontent-ref %}

### Peringatan muncul setiap kali server mulai

Plazma mengandung beberapa patch yang tidak stabil dan dapat menyebabkan kerusakan, oleh karena itu pesan peringatan berikut ditampilkan setiap kali server mulai.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Pesan peringatan ini dapat dinonaktifkan menggunakan properti sistem [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Untuk informasi lebih lanjut, lihat halaman berikut.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Tersedia mulai versi 1.20.1
