---
description: Sprawdź często zadawane pytania.
---

# ⁉️ Często zadawane pytania

{% hint style="info" %}

**Nie możesz znaleźć odpowiedzi, której szukasz?**

Zadaj społeczności pytanie za pośrednictwem [oficjalnego serwera Discord](https://discord.gg/MmfC52K8A8) lub [Dyskusji na GitHubie](https://github.com/PlazmaMC/PlazmaBukkit/discussions)!

{% endhint %}

### Plazma nie uruchamia się

Jeśli w konsoli pojawi się komunikat `no main manifest attribute, in plazma-(version).jar`,\
to pobrany plik jest plikiem API dla deweloperów, należy pobrać **Reobf Paperweight** ze strony GitHub.

Aby uzyskać więcej informacji, sprawdź następną stronę.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Po każdym uruchomieniu serwera pojawia się ostrzeżenie

Plazma zawiera niektóre niepewne łaty, co może prowadzić do nieprawidłowego działania, dlatego serwer wyświetla następujący komunikat ostrzegawczy przy uruchamianiu.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Ten komunikat ostrzegawczy można wyłączyć, korzystając z właściwości systemowej [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Aby uzyskać więcej informacji, sprawdź następną stronę.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Dostępne od wersji 1.20.1
