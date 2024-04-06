---
description: Descubra as perguntas frequentes.
---

# ⁉️ Perguntas frequentes

{% dica estilo="info" %}

**Não consegue encontrar a resposta que procura?**

[Servidor Discord oficial](https://discord.gg/MmfC52K8A8) ou [Discussões no GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions) para perguntar à comunidade!

{% endhint %}

### Plazma가 시작되지 않습니다

Se `no main manifest attribute, in plazma-(version).jar` for exibido no console,\
o arquivo baixado é um arquivo de API de desenvolvimento e você precisa baixar **Reobf Paperweight** na página do GitHub.

Consulte a próxima página para obter mais informações.

{% content-ref url="getting-started/" %}
[início](getting-started#id-2)
{% endcontent-ref %}

### Um aviso é exibido sempre que o servidor é iniciado

Plazma contém patches instáveis e pode apresentar mau funcionamento, portanto, exibe a seguinte mensagem de aviso ao iniciar o servidor.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Este aviso pode ser desativado usando a propriedade do sistema [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Consulte a próxima página para obter mais informações.

{% content-ref url="reference/arguments.md" %}
[argumetos.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Disponível a partir da versão 1.20.1
