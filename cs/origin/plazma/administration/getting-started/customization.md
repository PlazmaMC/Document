---
description: Zjistěte, jak přizpůsobit server uživatelským potřebám.
---

# 🎨 Uživatelské nastavení

Důvodem, proč se používá upravená serverová platforma jako Plazma místo oficiální serverové platformy poskytované společností Mojang Studios, je možnost silné **uživatelské úpravy**.

Níže jsou uvedeny různé způsoby, jak upravit a využívat Plazmu.

## Úprava konfigurace <a href="#id-1" id="id-1"></a>

Nejjednodušším způsobem, jak upravit Plazmu, je úprava konfigurace.

Plazma poskytuje silné nastavení konfigurace od herních mechanismů po vlastnosti potvor.

Pro popis konfigurace Plazmy se podívejte na následující stránku.

{% content-ref url="../reference/configurations/" %}
[konfigurace](../reference/configurations/)
{% endcontent-ref %}

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

**Některé [datové balíky](#user-content-fn-2)[^2] se při prvním použití nemusí správně aplikovat.**

V takovém případě se doporučuje server **2krát** restartovat.

{% endhint %}

Datové balíky mohou být snadno poškozeny s každou aktualizací Minecraftu.

Zejména pokud je datový balík zcela poškozený, může dojít ke kolizi serveru,
proto je důležité provést dostatečné testování před aktualizací serveru.

{% hint style="info" %}

**Začněte server s příkazem `safeMode` za startovacím příkazem, abyste vypnuli všechny datové balíky a mohli server spustit.**

[Pro více informací se podívejte na `Reference > Argumenty`.](../reference/arguments.md)

{% endhint %}

Nainstalované datové balíky lze zkontrolovat pomocí příkazu `/datapack list`.

***

[^1]: Nebo Minecraft: Bedrock Edition doplněk.

[^2]: Přidání nových entit atd.
