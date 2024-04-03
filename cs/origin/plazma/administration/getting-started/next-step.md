---
description: Zjistěte, jak přizpůsobit server uživatelským potřebám.
---

# 📶 Vývojová fáze

Důvodem, proč se používá upravená serverová platforma jako Plazma místo oficiální serverové platformy poskytované společností Mojang Studios, je možnost silné **uživatelské úpravy**.

Níže jsou uvedeny různé způsoby, jak upravit a využívat Plazmu.

## Úprava konfigurace <a href="#id-1" id="id-1"></a>

Nejjednodušším způsobem, jak upravit Plazmu, je úprava konfigurace.

Plazma poskytuje silné nastavení konfigurace od herních mechanismů po vlastnosti potvor.

Pro popis konfigurace Plazmy se podívejte na následující stránku.

{% content-ref url="../reference/configurations/" %}
[konfigurace](../reference/configurations/)
{% endcontent-ref %}

***

## Použití pluginů <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma podporuje všechny zásuvné moduly založené na Paperu.**

V případě zásuvných modulů Spigotu, které kvůli změně mapování Paperu od verze 1.20.5 nemusí správně fungovat,
většina zásuvných modulů založených na Paperu, jako je Paper, Pufferfish a Purpur, fungují v Plazmě
normálně a pokud nefungují správně, je to chyba v Plazmě, takže [nahlášení](../diagnosis/plugins.md) je nutné.

{% endhint %}

Jedním z hlavních důvodů použití Plazmy je nejsilnější způsob, jak Plazmu přizpůsobit uživatelům.
Silná ekosystém zásuvných modulů v Plazmě umožňuje snadno přizpůsobit server uživatelům.

Existuje několik způsobů, jak najít a stáhnout zásuvné moduly. Některé zásuvné moduly jsou nahrány do veřejných úložišť a některé jsou nahrány na GitHub nebo na vlastní
webové stránky.

{% hint style="caution" %}

**Zásuvné moduly mohou přímo ovlivnit systém!**

Před použitím zásuvného modulu vždy zkontrolujte jeho bezpečnost pomocí služeb jako VirusTotal nebo
stahujte zásuvné moduly ze důvěryhodných zdrojů.

{% endhint %}

Existuje několik služeb, které se používají k stahování zásuvných modulů. Mezi ně patří [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/), kde se zásuvné moduly podrobí posouzení před nahráním a nebezpečné zásuvné moduly jsou okamžitě odstraněny, aby se zajistilo, že se šíří pouze bezpečné zásuvné moduly.

### Aplikace zásuvných modulů <a href="#id-2.1" id="id-2.1"></a>

Pokud jste zásuvný modul stáhli, je čas ho aplikovat.

1. Zásuvné moduly jsou ve formátu `.jar` nebo `Java Executable File`.\
   Některé zásuvné moduly mohou být také ve formě komprimovaných souborů, v takovém případě
   rozbalte soubor, který obsahuje `bukkit`, `spigot` nebo `paper` v názvu a
   pokud je k dispozici soubor s názvem `fat`, použijte tento soubor.
2. Stažený soubor umístěte do složky `plugins` ve složce serveru a server (znovu)spusťte.
3. Po spuštění Plazmy se na konzoli zobrazí nový obsah.
   To znamená, že Plazma úspěšně načetla zásuvné moduly.
4. I když Plazma úspěšně načetla zásuvné moduly, může se stát, že zásuvný modul není spuštěn.
   Pomocí příkazu `/plugins` můžete načíst aktuálně nahrávané zásuvné moduly na serveru.
   Pokud jméno nainstalovaného zásuvného modulu není <mark style="background-color:red;">červené</mark>, ale <mark style="background-color:green;">zelené</mark>, znamená to, že zásuvný modul byl úspěšně načten.

Pokud zásuvný modul není úspěšně načten, můžete najít řešení problému na následující stránce.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Použití datových balíků <a href="#id-3" id="id-3"></a>

Datové balíky jsou způsobem, jak Minecraft umožňuje uživatelské úpravy, podobně jako
[resource pack](#user-content-fn-1)[^1].

Pomocí datových balíků můžete upravit některé části hry, jako je přidání nových entit a výzev.

{% hint style="caution" %}

**Datové balíky mohou poškodit svět!**

Některé vadné datové balíky mohou poškodit svět a to nelze vrátit zpět.

Proto je doporučeno zálohovat svět před aplikací datového balíku.

{% endhint %}

Datové balíky lze stáhnout z různých služeb, jako jsou [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs) a další.

Po stažení datového balíku ho umístěte do složky `datapacks` ve složce světa serveru.
Pokud složka neexistuje, vytvořte ji a vložte do ní datový balík.

{% hint style="warning" %}

**[Některá datová balíčky](#user-content-fn-2)[^2] se mohou při prvním použití nenastavit správně.**

V takovém případě se doporučuje server **2krát** restartovat.

{% endhint %}

Datové balíky mohou být snadno poškozeny s každou aktualizací Minecraftu.

Zejména pokud je datový balík zcela poškozený, může dojít ke kolizi serveru,
proto je důležité provést dostatečné testování před aktualizací serveru.

{% hint style="info" %}

**Začněte server s příkazem `safeMode` za startovacím příkazem, abyste vypnuli všechny datové balíky a mohli server spustit.**

[Podrobnosti najdete v `Reference > Argumenty a vlastnosti`](../reference/arguments.md#safeMode)

{% endhint %}

Nainstalované datové balíky lze zkontrolovat pomocí příkazu `/datapack list`.

***

## Optimalizace <a href="#id-4" id="id-4"></a>

V Plazmě je mnoho optimalizačních záplat aplikováno. Kromě toho, když se Plazma poprvé spustí, automaticky optimalizuje konfiguraci,
takže pokud postupujete podle průvodce [Začínáme](./README.md), není třeba provádět další optimalizační práce.

Nicméně, pokud se připojuje mnoho hráčů nebo je velikost světa rozsáhlá,
je možné provést další optimalizační práce podle následujícího průvodce.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proxy spojuje servery a umožňuje hráčům přesouvat se mezi servery nebo
komunikovat s jinými servery bez dalších úkonů.

Pro informace o bezpečném a správném nastavení proxy navštivte následující stránku.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Bezpečnost <a href="#id-5" id="id-5"></a>

V Minecraftu je díky rozvoji módů snadné získat [nástroje pro útoky na zranitelnost](#user-content-fn-3)[^3] i online.

Většina základních zranitelností, které jsou spustitelné i v běžných hrách, je [výchozí blokována](#user-content-fn-4)[^4],
ale útoky na zranitelnosti pomocí třetích stran jsou neblokovány.

Proto je doporučeno, pokud je server veřejně dostupný, instalovat pluginy proti podvádění a
nastavit proxy, automatické restartování a zálohování, aby bylo možné server rychle obnovit v případě výpadku.

### Nastavení oprávnění <a href="#id-5.1" id="id-5.1"></a>

Některé administrátorské příkazy pluginů mohou mít zranitelnosti, pokud nejsou oprávnění správně nastavena.

Je doporučeno používat pluginy pro správu oprávnění jako je [LuckPerms](https://luckperms.net/),
abyste mohli omezit oprávnění běžných uživatelů.

### Blokování X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray je jednou z zranitelností, které jsou snadno dostupné i v základní optimalizačním klientovi.

V Plazmě je k dispozici konfigurace, která umožňuje základní blokování X-Ray.

Návod k blokování X-Ray a další informace naleznete na následující stránce.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

Pokud chcete, aby se na server mohli připojit pouze určití uživatelé,
použijte [Ngrok](./README.md#id-6.2) pro [použití zakódované adresy serveru](#user-content-fn-5)[^5] nebo
nastavte whitelist, abyste zabránili připojení jiným hráčům.

Na serverové konzoli můžete povolit připojení hráče pomocí příkazu `/whitelist add <hráč>` nebo
zakázat připojení hráče pomocí `/whitelist remove <hráč>`.

Pro zobrazení povolených hráčů použijte `/whitelist query`.

***

[^1]: Nebo Minecraft: Bedrock Edition doplněk.

[^2]: Přidání nových entit atd.

[^3]: Obvykle nazývané "cheaty".

[^4]: Pokud není konfigurace optimalizována, Plazma je zastaralá nebo jsou nově objevené zranitelnosti, nemusí být blokovány.

[^5]: Hráči se připojují na server pomocí proxy serveru Ngrok a každý restart serveru získá novou adresu Ngrok.
