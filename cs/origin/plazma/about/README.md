---
description: Zjistěte, o jakou serverovou platformu se jedná.
---

# ❓ Co je Plazma?

- **Plazma** je serverová platforma založená na [Paper](https://github.com/PaperMC/Paper), která si bere výhody z [Andromeda](https://github.com/EarendelArchived/Andromeda) a [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Snažíme se poskytovat vysokou stabilitu, silný výkon, rychlé aktualizace a bohaté funkce.

## 📋 Cíle Plazmy <a href="#id-1" id="id-1"></a>

- Snažíme se stát serverovou platformou s rychlými aktualizacemi a vysokou stabilitou.
- Snažíme se poskytnout bohaté funkce a silný výkon, který není vůbec horší než u modových platforem.
- Snažíme se vytvořit svobodnou platformu, která umožňuje uživatelské úpravy i pro základní opravy.

## ⚙️ Hlavní rysy <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Nejrychlejší aktualizace**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) udržuje zahrnuté opravy Plazmy vždy aktuální, což zajišťuje nejrychlejší aktualizace mezi serverovými platformami založenými na Paper.
6. **Optimalizace základních konfiguračních souborů**\
   Výchozí konfigurační soubory jsou optimalizovány, takže nemusíte ručně optimalizovat konfigurační soubory.
7. **Systémové vlákno fungující systematicky**\
   Asynchronizací systémových mechanismů oddělených od herních mechanismů se snižuje [dočasná prodleva](#user-content-fn-4)[^4] a optimalizuje se server.
8. **Blokování nepotřebných prostorů**\
   Spojením podobných hodnot do jedné se snižuje využití paměti.

## ✨ Příklady využití <a href="#id-3" id="id-3"></a>

- **Platforma, která správně zpracovává složité pluginy**\
  Na serveru vývojáře [IPECTER](https://github.com/IPECTER) je používán Plazma.\
  I přes komplexní vlastní pluginy fungující pomocí NMS a reflexe, a velké množství datových balíčků,\
  je schopna obsluhovat více než 100 hráčů bez výrazného poklesu výkonu.
- **Platforma udržující rychlý výkon i na RPG serverech**\
  Na jednom clusteru bylo udržováno stabilní prostředí pro 100 hráčů bez poklesu TPS a na 4 clusterech bylo možné pohodlně hrát až 250 hráčů.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Mnoho streamerů vybralo platformu**\
  Mnoho streamerů ji používá jako nádoby pro účast diváků.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Stáhnout

Na následující stránce si můžete stáhnout Plazmu.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Chcete vědět více o podporovaných verzích?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Pluginy pro Bukkit, CraftBukkit, Spigot a Paper, Pufferfish, Purpur.

[^2]: Patří pod společnost Microsoft Corporation.

[^3]: Deaktivací systému hlášení chatu je možné zamezit sledování chatu ze strany Mojangu a zpracování chatu pouze na serveru.

[^4]: Čas, kdy hra na chvíli zastaví svůj běh kvůli fungování systémových mechanismů.
