---
description: Aflați cum să personalizați serverul.
---

# 🎨 Personalizare utilizator

Motivul pentru care se utilizează o platformă de server modificată precum Plazma în locul platformei oficiale furnizate de Mojang Studios este capacitatea puternică de **personalizare** pe care o oferă.

Mai jos sunt enumerate mai multe moduri de personalizare și utilizare a Plazma.

## Modificarea configurației <a href="#id-1" id="id-1"></a>

Cel mai simplu mod de a personaliza Plazma este prin modificarea configurației.

Plazma oferă setări de configurare puternice, inclusiv mecanisme de joc și caracteristici ale entităților.

Pentru informații detaliate despre configurația Plazma, consultați pagina de mai jos.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

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

**Pentru unele [Datapack-uri](#user-content-fn-2)[^2], la prima aplicare ar putea să nu funcționeze corect.**

În acest caz, se recomandă să reporniți serverul **de 2 ori**.

{% endhint %}

Datapack-urile pot fi afectate ușor de actualizările Minecraft-ului.

În special, în cazul în care un Datapack este grav afectat, serverul poate să se blocheze, așa că este important să testați suficient înainte de a actualiza serverul.

{% hint style="info" %}

**După comanda de pornire a serverului, puteți introduce `safeMode` pentru a dezactiva toate Datapack-urile și apoi să porniți serverul.**

[Pentru mai multe informații, consultați `Referințe > Argumente și Atribute`.](../reference/arguments.md)

{% endhint %}

Datapack-urile aplicate pot fi verificate folosind comanda `/datapack list`.

***

[^1]: Sau Minecraft: Ediția Bedrock.

[^2]: Adăugarea de entități și altele.
