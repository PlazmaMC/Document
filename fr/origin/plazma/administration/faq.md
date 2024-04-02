---
description: Découvrez les questions fréquemment posées.
---

# ⁉️ Questions fréquemment posées

{% hint style="info" %}

**Vous ne trouvez pas la réponse que vous cherchez?**

Posez vos questions à la communauté via le [serveur Discord officiel](https://discord.gg/MmfC52K8A8) ou les [problèmes GitHub](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### Plazma ne démarre pas

Si vous voyez `no main manifest attribute, in plazma-(version).jar` dans la console,\
le fichier que vous avez téléchargé est destiné à l'API de développement, vous devez télécharger **Reobf Paperweight** depuis la page GitHub.

Consultez la page suivante pour plus de détails.

{% content-ref url="getting-started/" %}
[démarrage](getting-started#id-2)
{% endcontent-ref %}

### Un avertissement s'affiche à chaque démarrage du serveur

Plazma contient quelques correctifs instables et peut toujours présenter des dysfonctionnements, c'est pourquoi ces avertissements s'affichent lors du démarrage du serveur.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Cet avertissement peut être désactivé en utilisant la propriété système [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Consultez la page suivante pour plus de détails.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Disponible à partir de la version 1.20.1
