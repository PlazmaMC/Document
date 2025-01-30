---
description: Saznajte kako prilagoditi poslužitelj.
---

# 🎨 Prilagodba korisnika

Razlog za korištenje modificirane serverske platforme poput Plazme umjesto službene serverske platforme koju pruža Mojang Studios je što omogućuje snažnu **prilagodbu**.

U nastavku su navedeni različiti načini prilagodbe i korištenja Plazme.

## Uređivanje konfiguracije <a href="#id-1" id="id-1"></a>

Najosnovniji način prilagodbe Plazme je uređivanje konfiguracije.

Plazma pruža snažne postavke konfiguracije poput mehanike igre i karakteristika čudovišta.

Za više informacija o konfiguraciji Plazme pogledajte donju stranicu.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## Korištenje dodataka <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma podržava sve dodatke na papirnatoj osnovi.**

Za Spigot dodatke, zbog promjene mapiranja od verzije 1.20.5 Papera, neki možda neće raditi,
No, većina dodataka koji se temelje na Paperu kao što su Paper, Pufferfish i Purpur će raditi na Plazmi,
Ako se dodatak ne pokreće ispravno, to je vjerojatno greška u Plazmi, stoga odmah [prijavite](../diagnosis/plugins.md).

{% endhint %}

To je glavni razlog za korištenje Plazme i najmoćniji način prilagodbe Plazme korisnicima.
Snažan ekosustav dodataka Plazme omogućuje jednostavnu prilagodbu poslužitelja.

Postoje razni načini za pronalazak i preuzimanje dodataka. Neki dodaci se
preuzimaju na javne repozitorije, dok se neki preuzimaju na GitHub ili vlastite
web stranice.

{% hint style="caution" %}

**Dodaci mogu izravno pristupiti sustavu!**

Prije primjene dodataka uvijek provjerite jesu li sigurni pomoću usluga poput VirusTotala ili
preuzmite dodatak s pouzdane usluge.

{% endhint %}

Postoje razne usluge za preuzimanje dodataka. Među njima su [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) i druge usluge koje dodatke ocjenjuju prije objave kako bi osigurale sigurnost.

### Primjena dodataka <a href="#id-2.1" id="id-2.1"></a>

Nakon preuzimanja dodatka, vrijeme je za primjenu dodatka.

1. Dodaci su u obliku `.jar` datoteka ili izvršnih Java datoteka.\
   Neke datoteke s dodacima mogu biti u obliku arhiva, u tom slučaju
   izvucite arhivu i koristite datoteku koja sadrži `bukkit`, `spigot` ili `paper` u imenu te
   datoteku s oznakom `fat` ako je prisutna.
2. Stavite preuzetu datoteku u mapu `plugins` unutar mape poslužitelja i ponovno pokrenite poslužitelj.
3. Kada se Plazma pokrene, na konzoli će se prikazati nova poruka.
   To znači da je Plazma uspješno učitala dodatke.
4. Iako je Plazma uspješno učitala dodatke, možda ih nije uspjela pokrenuti.
   Korištenjem naredbe `/plugins` možete vidjeti koji su dodaci trenutno učitani na poslužitelju.
   Ako ime dodatka nije označeno crvenom
   bojom, već
   zelenom, znači da je dodatak uspješno učitan.

Ako dodatak nije uspješno učitan, možete pronaći rješenja na sljedećoj stranici.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## Korištenje paketa podataka <a href="#id-3" id="id-3"></a>

Paketi podataka su način prilagodbe Minecrafta koji je sličan
[resursnim paketima](#user-content-fn-1)[^1].

Korištenjem paketa podataka možete dodati nove skupine entiteta i izazova u igri i mijenjati neke unutarnje dijelove igre.

{% hint style="caution" %}

**Paketi podataka mogu oštetiti svijet!**

Neispravni paketi podataka mogu trajno oštetiti svijet i to se ne može poništiti.

Stoga je preporučljivo napraviti sigurnosnu kopiju svijeta prije primjene paketa podataka.

{% endhint %}

Pakete podataka možete preuzeti s raznih usluga poput [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) i drugih.

Nakon preuzimanja paketa podataka, stavite ih u mapu `datapacks` unutar svjetske mape poslužitelja.
Ako mapa ne postoji, možete je stvoriti i dodati pakete podataka.

{% hint style="warning" %}

**Neki [paketi podataka](#user-content-fn-2)[^2] možda neće se pravilno primijeniti prilikom prvog pokušaja.**

U tom slučaju se preporučuje **2 puta** ponovno pokrenuti poslužitelj.

{% endhint %}

Paketi podataka mogu lako biti oštećeni svakom nadogradnjom Minecrafta.

Posebno kada su paketi podataka potpuno oštećeni, mogu uzrokovati rušenje poslužitelja,
stoga je važno dobro testirati prije nadogradnje poslužitelja.

{% hint style="info" %}

**Nakon pokretanja naredbe za pokretanje poslužitelja, možete unijeti `safeMode` iza naredbe kako biste onemogućili sve pakete podataka i zatim pokrenuli poslužitelj.**

[Za više informacija pogledajte `Referenca > Argumenti`.](../reference/arguments.md)

{% endhint %}

Primijenjeni paketi podataka mogu se provjeriti pomoću naredbe `/datapack list`.

***

[^1]: Ili Minecraft: Bedrock Edition dodatak.

[^2]: Dodavanje novih skupina entiteta itd.
