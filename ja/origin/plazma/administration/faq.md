---
description: よくある質問をご覧ください。
---

# ⁉️ よくある質問

{% hint style="info" %}

**回答が見つからない場合は？**

[公式 Discord サーバー](https://discord.gg/MmfC52K8A8)または[GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)を通じてコミュニティに質問してみてください！

{% endhint %}

### Plazmaが起動しません

コンソールに `no main manifest attribute, in plazma-(version).jar` と表示された場合、
ダウンロードしたファイルは開発用APIファイルであり、GitHubページから **Reobf Paperweight** をダウンロードする必要があります。

詳細は次のページをご参照ください。

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### サーバーが起動するたびに警告が表示されます

Plazmaには一部不安定なパッチが含まれており、常に誤動作の可能性があるため、サーバーが起動する際に次のような警告文を出力しています。

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

この警告文は[`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] システムプロパティを使用して無効にすることができます。

詳細は次のページをご参照ください。

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: 1.20.1から利用可能
