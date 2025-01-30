---
description: Zistite viac o platforme Plazma.
---

# ❓ Čo je Plazma?

- **Plazma** je serverová platforma založená na [Paper](https://github.com/PaperMC/Paper), ktorá získava výhody z [Andromeda](https://github.com/EarendelArchived/Andromeda) a [Fusion](https://github.com/RuinedTechnologyUnify/Fusion).
- Snažíme sa vždy poskytovať vysokú stabilitu a výkonnosť, rýchle aktualizácie a bohaté funkcie.

## 📋 Ciele Plazmy <a href="#id-1" id="id-1"></a>

- Snažíme sa o rýchle aktualizácie a vytvorenie serverovej platformy s vysokou stabilitou.
- Snažíme sa poskytnúť bohaté funkcie a výkonnosť, ktorá sa nezaostáva za platformou pre módy.
- Snažíme sa vytvoriť voľnú platformu, ktorá umožňuje prispôsobiť aj patche pre vanilla.

## ⚙️ Kľúčové vlastnosti <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **Najrýchlejšie aktualizácie**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate) zabezpečuje, že záplaty v Plazme sú vždy aktuálne, čo z nej robí platformu s najrýchlejšími aktualizáciami medzi serverovými platformami založenými na Paper.
6. **Optimalizované základné konfiguračné súbory**\
   Prednastavené konfiguračné súbory sú optimalizované, takže nie je potrebné ich ďalej upravovať.
7. **Systémové vlákna fungujúce systematicky**\
   Asynchrónne spracovanie systémových mechanizmov mimo herné mechanizmy pomáha optimalizovať server tým, že znižuje [čas oneskorenia](#user-content-fn-4)[^4].
8. **Blokovanie zbytočného použitia pamäte**\
   Združenie dát s podobnými hodnotami do jedného záznamu znižuje spotrebu pamäte.

## ✨ Príklady využitia <a href="#id-3" id="id-3"></a>

- **Platforma správne spracujúca aj zložité zásuvné moduly**\
  Plazma je používaná na serveroch vývojára [IPECTER](https://github.com/IPECTER).\
  Má vlastné zásuvné moduly fungujúce cez NMS a reflexiu, s veľkým množstvom veľkých dátových balíkov,\
  ajak pre viac ako 100 hráčov bez poklesu výkonu.
- **Platforma udržiavajúca rýchly výkon aj na RPG serveroch**\
  Na jednom zhluku udržala 100 hráčov bez poklesu TPS a na 4 zhlukoch mohlo 250 hráčov hrať plynulo.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Mnoho streamerov vybralo platformu**\
  Je to vybrané ako kôš pre divácku účasť mnohých streamerov.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Stiahnuť

Na nasledujúcej stránke si môžete stiahnuť Plazmu.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Chcete vedieť viac o podporovaných verziách?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Pluginy pre Bukkit, CraftBukkit, Spigot a záplaty pre Paper, Pufferfish, Purpur.

[^2]: Pod Microsoft Corporation.

[^3]: Ak deaktivujete systém na hlásenie chatu, chat bude spracovávaný iba na serveri a zabránite sledovaniu chatu od Mojangu.

[^4]: Čas, počas ktorého systémový mechanizmus funguje a hra je pozastavená.
