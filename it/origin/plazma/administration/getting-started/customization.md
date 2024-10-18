---
description: Scopri come personalizzare il server.
---

# 🎨 Personalizzazione utente

Il motivo per cui si utilizza una piattaforma server modificata come Plazma anziché la piattaforma server ufficiale fornita da Mojang Studios è probabilmente la possibilità di una **personalizzazione** potente.

Di seguito sono riportati vari modi per personalizzare e utilizzare Plazma.

## Modifica della configurazione <a href="#id-1" id="id-1"></a>

Il modo più basilare per personalizzare Plazma è modificare la configurazione stessa.

Plazma offre potenti impostazioni di configurazione, che vanno dai meccanismi di gioco alle proprietà dei mob.

Per ulteriori informazioni sulla configurazione di Plazma, consultare la pagina seguente.

{% content-ref url="../reference/configurations/" %}
[configurazioni](../reference/configurations/)
{% endcontent-ref %}

## Utilizzo di plugin <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma supporta pienamente tutti i plugin basati su Paper.**

Per i plugin Spigot, a partire dalla versione 1.20.5, potrebbero non funzionare a causa delle modifiche di mapping di Paper, ma la maggior parte dei plugin basati su Paper come Paper, Pufferfish e Purpur funzionano correttamente su Plazma. Se un plugin non funziona correttamente, si prega di [segnalarlo immediatamente](../diagnosis/plugins.md) poiché potrebbe essere un errore di Plazma.

{% endhint %}

Questo è il motivo principale per cui si utilizza Plazma ed è il modo più potente per personalizzare Plazma.
L'ecosistema dei plugin di Plazma consente di personalizzare facilmente il server.

Ci sono vari modi per trovare e scaricare i plugin. Alcuni plugin vengono caricati su servizi di repository pubblici, mentre altri vengono caricati su GitHub o sui propri siti Web.

{% hint style="caution" %}

**I plugin possono accedere direttamente al sistema!**

Prima di applicare un plugin, assicurarsi sempre che sia sicuro utilizzando servizi come VirusTotal o scaricandolo da servizi affidabili.

{% endhint %}

Ci sono vari servizi per scaricare i plugin. Tra questi, servizi come [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) valutano i plugin prima del caricamento per garantire che solo plugin sicuri siano distribuiti.

### Applicazione dei plugin <a href="#id-2.1" id="id-2.1"></a>

Una volta scaricati i plugin, è ora di applicarli.

1. I plugin sono file `.jar` o file eseguibili Java. Alcuni plugin sono forniti in formato compresso; in tal caso, estrarre il file e utilizzare il file con estensione `fat` se presente.
2. Copiare il file scaricato nella cartella `plugins` del server e riavviare il server.
3. Quando Plazma si avvia, verrà visualizzato un nuovo output sulla console.
   Questo significa che Plazma ha caricato correttamente il plugin.
4. Anche se Plazma ha caricato correttamente il plugin, potrebbe non essere attivato.
   Utilizzando il comando `/plugins`, è possibile visualizzare i plugin attualmente caricati sul server.
   Se il nome del plugin installato non è in <mark style="background-color:red;">rosso</mark> ma in <mark style="background-color:green;">verde</mark>, significa che il plugin è stato caricato correttamente.

Se il plugin non viene caricato correttamente, è possibile trovare soluzioni alla pagina sottostante.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Utilizzo dei datapack <a href="#id-3" id="id-3"></a>

I datapack sono un modo per personalizzare Minecraft simile ai resource pack.

Con i datapack è possibile aggiungere nuove entità e sfide al gioco, tra le altre modifiche interne al gioco.

{% hint style="caution" %}

**I datapack possono danneggiare il mondo!**

Alcuni datapack danneggiati possono causare danni permanenti al mondo, irreversibili.

Si consiglia di eseguire il backup del mondo prima di applicare i datapack.

{% endhint %}

I datapack possono essere scaricati da vari servizi come [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) e altri.

Una volta scaricati i datapack, è possibile applicarli copiandoli nella cartella `datapacks` della directory del mondo del server.
Se la cartella non esiste, è possibile crearla manualmente.

{% hint style="warning" %}

**Alcuni [datapack](#user-content-fn-2) potrebbero non essere applicati correttamente la prima volta.**

In caso di problemi, si consiglia di riavviare il server **2 volte**.

{% endhint %}

I datapack possono essere facilmente danneggiati con gli aggiornamenti di Minecraft.

In caso di danni gravi ai datapack, che possono causare il crash del server, è importante testare attentamente prima di aggiornare il server.

{% hint style="info" %}

**Dopo il comando di avvio del server, è possibile disattivare tutti i datapack inserendo `safeMode` e quindi avviare il server.**

Per ulteriori informazioni, consultare `Reference > Arguments`.](../reference/arguments.md)

{% endhint %}

I datapack applicati possono essere verificati utilizzando il comando `/datapack list`.

***

[^1]: Oppure utilizzando gli add-on di Minecraft: Bedrock Edition.

[^2]: Aggiunta di nuove entità e altro ancora.
