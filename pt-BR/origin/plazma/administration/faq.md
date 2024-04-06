---
description: Descubra as perguntas frequentes.
---

# ⁉️ Perguntas frequentes

{% hint style="info" %}

**Não consegue encontrar a resposta que procura?**

[Servidor Discord oficial](https://discord.gg/MmfC52K8A8) ou [Discussões no GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions) para fazer perguntas à comunidade!

{% endhint %}

### Plazma não está iniciando

Se receber a mensagem `no main manifest attribute, in plazma-(versão).jar` no console,\
o arquivo baixado é um arquivo de API de desenvolvimento, você deve baixar o **Reobf Paperweight** na página do GitHub.

Para mais informações, consulte a seguinte página.

{% content-ref url="getting-started/" %}
[iniciando](getting-started#id-2)
{% endcontent-ref %}

### Um aviso é exibido sempre que o servidor é iniciado

Plazma contém patches instáveis e pode apresentar mau funcionamento, portanto, exibe a seguinte mensagem de aviso sempre que o servidor é iniciado.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Este aviso pode ser desativado usando a propriedade do sistema [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Para mais informações, consulte a seguinte página.

{% content-ref url="reference/arguments.md" %}
[arguimentos.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Disponível a partir da versão 1.20.1
