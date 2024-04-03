---
description: Aflați cum să personalizați serverul.
---

# 📶 Etapa de dezvoltare

Motivul pentru care se utilizează o platformă de server modificată precum Plazma în locul platformei oficiale furnizate de Mojang Studios este capacitatea puternică de **personalizare** pe care o oferă.

Mai jos sunt enumerate mai multe moduri de personalizare și utilizare a Plazma.

## Modificarea configurației <a href="#id-1" id="id-1"></a>

Cel mai simplu mod de a personaliza Plazma este prin modificarea configurației.

Plazma oferă setări de configurare puternice, inclusiv mecanisme de joc și caracteristici ale entităților.

Pentru informații detaliate despre configurația Plazma, consultați pagina de mai jos.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

***

## Utilizarea de plugin-uri <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma suportă în mod normal toate pluginurile bazate pe hârtie.**

În cazul pluginurilor Spigot, din cauza modificărilor de mapare de la 1.20.5 la hârtie, unele pot să nu funcționeze, dar majoritatea pluginurilor bazate pe hârtie, cum ar fi Paper, Pufferfish și Purpur, vor funcționa normal în Plazma, iar dacă nu funcționează corect, este o eroare în Plazma, vă rugăm să [raportați imediat.](../diagnosis/plugins.md)

{% endhint %}

Acesta este unul dintre principalele motive pentru utilizarea Plazma și cea mai puternică metodă de personalizare a Plazmei.
Ecosistemul puternic de pluginuri al Plazma permite personalizarea ușoară a serverului.

Există mai multe modalități de a găsi și descărca pluginuri. Unele pluginuri sunt încărcate pe servicii de depozitare publică, iar altele sunt încărcate pe GitHub sau pe propriul lor site.

{% hint style="caution" %}

**Pluginurile pot accesa direct sistemul!**

Utilizați servicii precum VirusTotal pentru a verifica întotdeauna siguranța pluginurilor înainte de a le aplica sau descărca pluginuri de pe servicii de încredere.

{% endhint %}

Există mai multe servicii pentru descărcarea pluginurilor. Dintre acestea, servicii precum [Forumul SpigotMC](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) supun pluginurile la o verificare înainte de a fi încărcate, astfel încât doar pluginurile sigure să fie distribuite.

### Aplicarea pluginurilor <a href="#id-2.1" id="id-2.1"></a>

Dacă ați descărcat un plugin, acum este momentul să îl aplicați.

1. Pluginurile sunt sub formă de fișiere `.jar` sau fișiere executabile Java.\
   Unele pluginuri pot fi împachetate în arhive, în acest caz, extrageți arhiva și utilizați fișierul care conține `bukkit`, `spigot` sau `paper` în nume, iar dacă există un fișier `fat`, folosiți acel fișier.
2. Puneți fișierul descărcat în dosarul `plugins` al serverului și reporniți serverul.
3. Când Plazma începe, va afișa noi informații în consolă.
   Acest lucru indică faptul că Plazma a încărcat pluginul corect.
4. Chiar dacă Plazma a încărcat pluginul corect, acesta ar putea să nu pornească.
   Puteți folosi comanda `/plugins` pentru a afișa pluginurile încărcate în prezent pe server.
   Dacă numele pluginului nu este <mark style="background-color:red;">roșu</mark>, ci <mark style="background-color:green;">verde</mark>, atunci pluginul a fost încărcat corect.

Dacă pluginul nu a fost încărcat corect, puteți găsi soluții la probleme pe pagina de mai jos.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Utilizarea Datapack-urilor <a href="#id-3" id="id-3"></a>

Datapack-urile sunt o metodă de personalizare oferită de Minecraft, similară cu [pachetele de resurse](#user-content-fn-1)[^1].

Prin utilizarea Datapack-urilor, puteți adăuga noi entități și provocări în joc, modificând anumite aspecte ale acestuia.

{% hint style="caution" %}

**Datapack-urile pot afecta lumea jocului!**

Anumite Datapack-uri defecte pot afecta lumea jocului în mod ireversibil.

De aceea, este recomandat să faceți backup la lumea jocului înainte de a aplica Datapack-urile.

{% endhint %}

Datapack-urile pot fi descărcate de pe mai multe servicii, cum ar fi [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) și altele.

După ce ați descărcat Datapack-ul, puteți aplica acesta punându-l în dosarul `datapacks` al lumii serverului.
Dacă dosarul nu există, puteți crea unul pentru a adăuga Datapack-ul.

{% hint style="warning" %}

**În unele cazuri, **[pachetele de date parțiale](#user-content-fn-2)[^2]** pot să nu se aplice corect la prima aplicare.**

În acest caz, se recomandă să reporniți serverul **de 2 ori**.

{% endhint %}

Datapack-urile pot fi afectate ușor de actualizările Minecraft-ului.

În special, în cazul în care un Datapack este grav afectat, serverul poate să se blocheze, așa că este important să testați suficient înainte de a actualiza serverul.

{% hint style="info" %}

**După comanda de pornire a serverului, puteți introduce `safeMode` pentru a dezactiva toate Datapack-urile și apoi să porniți serverul.**

[Pentru informații detaliate, consultați `Referințe > Argumente și Atribute`.](../reference/arguments.md#safeMode)

{% endhint %}

Datapack-urile aplicate pot fi verificate folosind comanda `/datapack list`.

***

## Optimizare <a href="#id-4" id="id-4"></a>

Plazma are multe patch-uri de optimizare aplicate. De asemenea, atunci când Plazma este pornită pentru prima dată, optimizează automat configurația, deci nu este necesară efectuarea unor operațiuni suplimentare de optimizare dacă urmați ghidul de [pornire](./README.md).

Cu toate acestea, dacă sunt mulți jucători conectați sau dimensiunea lumii este mare, puteți efectua operații suplimentare de optimizare urmând ghidul de mai jos.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxy-ul conectează serverele între ele și permite jucătorilor să se mute între servere sau să comunice cu alte servere fără a fi necesare operații suplimentare.

Pentru informații despre configurarea corectă și sigură a proxy-ului, consultați pagina de mai jos.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Siguranță <a href="#id-5" id="id-5"></a>

Minecraft-ul s-a dezvoltat în așa fel încât să permită obținerea ușoară a unui [motor de atac cu vulnerabilități](#user-content-fn-3)[^3] și online.

Majoritatea vulnerabilităților care pot fi exploatate în jocuri sunt [în mod implicit blocate](#user-content-fn-4)[^4], dar nu sunt blocate atunci când sunt exploatate prin intermediul unui încărcător terță parte.

Prin urmare, în cazul în care serverul este public, se recomandă instalarea de plugin-uri anti-cheat pentru a bloca utilizarea vulnerabilităților, precum și configurarea de proxy-uri, reporniri automate, backup-uri etc., pentru a asigura o recuperare rapidă în caz de cădere a serverului.

### Configurare permisiuni <a href="#id-5.1" id="id-5.1"></a>

Unele comenzi de administrator ale unor plugin-uri pot prezenta vulnerabilități dacă permisiunile nu sunt setate corect.

Se recomandă utilizarea unor plugin-uri de gestionare a permisiunilor precum [LuckPerms](https://luckperms.net/) pentru a restricționa permisiunile utilizatorilor obișnuiți.

### Blocare X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray este una dintre vulnerabilitățile ușor de utilizat chiar și într-un client de optimizare de bază.

Plazma oferă o configurare care poate bloca X-Ray-ul în mod implicit.

Pentru metodele și descrierile de blocare a X-Ray-ului, consultați pagina de mai jos.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Listă albă <a href="#id-5.3" id="id-5.3"></a>

În cazul în care doriți să permiteți doar anumiți utilizatori să se conecteze la server, se recomandă utilizarea [Ngrok](./README.md#id-6.2) pentru a utiliza o [adresă a serverului criptată](#user-content-fn-5)[^5] sau setarea unei liste albe pentru a preveni accesul altor jucători la server.

Puteți permite accesul jucătorilor folosind comanda `/whitelist add <player>` în consola serverului sau puteți interzice accesul folosind comanda `/whitelist remove <player>`.

Pentru a vedea jucătorii cu acces permis, folosiți comanda `/whitelist query`.

***

[^1]: Sau Minecraft: Ediția Bedrock.

[^2]: Adăugarea de entități și altele.

[^3]: Sunt cunoscuți în mod obișnuit sub numele de "hack".

[^4]: În cazul în care configurarea nu este optimizată, Plazma este veche sau există vulnerabilități noi, acestea ar putea să nu fie blocate.

[^5]: Atunci când un jucător se conectează la server, se face prin intermediul serverului proxy Ngrok și adresa Ngrok emisă la fiecare repornire va fi diferită.
