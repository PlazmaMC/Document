---
description: Plazma'nın hangi tür bir sunucu platformu olduğunu öğrenin.
---

# ❓ Plazma nedir?

- **Plazma**, [Andromeda](https://github.com/EarendelArchived/Andromeda) ve [Fusion](https://github.com/RuinedTechnologyUnify/Fusion) projelerinden sadece olumlu yönleri alarak [Paper](https://github.com/PaperMC/Paper) tabanlı bir sunucu platformudur.
- Her zaman yüksek kararlılık ve güçlü performans, hızlı güncellemeler ve geniş özellik seti sunmak için çaba sarf etmektedir.

## 📋 Plazma'nın hedefleri <a href="#id-1" id="id-1"></a>

- Hızlı güncellemeler ve yüksek kararlılığa sahip bir sunucu platformu olmak için çaba sarf etmektedir.
- Mod platformlarına eşdeğer geniş özellikler ve güçlü performans sunmak için çaba sarf etmektedir.
- Vanilya yamalarını da özelleştirebileceğiniz özgür bir platform oluşturmak için çaba sarf etmektedir.

## ⚙️ Ana özellikler <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어,
   인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며,
   일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을
   수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된
   [Mojang](#user-content-fn-2)[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **En hızlı güncellemeler**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate), Plazma'nın dahil ettiği yamaların her zaman en güncel kalmasını sağlayarak, Paper tabanlı sunucu platformları arasında en hızlı güncellemeleri sunmaktadır.
6. **Varsayılan yapılandırma dosyaları optimize edilmiş**\
   Doğrudan yapılandırma dosyalarını optimize etmenize gerek kalmadan varsayılan olarak optimize edilmiştir.
7. **Sistemli çoklu iş parçacıklı çalışma**\
   Oyun mekanizmalarıyla ilgisi olmayan sistem mekanizmalarını asenkron hale getirerek, [gecikmeyi](#user-content-fn-4)[^4] azaltarak sunucuyu optimize etmektedir.
8. **Gereksiz alan kullanımını engelleme**\
   Benzer değerlere sahip verileri birleştirerek bellek kullanımını azaltır.

#### Plazma hakkında daha fazla bilgi almak isterseniz? <a href="#etc-1" id="etc-1"></a>

{% content-ref url="patches-list.md" %}
[patches-list.md](patches-list.md)
{% endcontent-ref %}

## ✨ Kullanım Örnekleri <a href="#id-3" id="id-3"></a>

- **복잡한 플러그인도 올바르게 처리하는 플랫폼**\
  개발자 [IPECTER](https://github.com/IPECTER)의 서버에서 Plazma가 사용되고 있습니다.\
  NMS와 리플렉션으로 작동하는 자체 플러그인, 복잡하고 방대한 크기의 데이터팩이 굉장히 많이 적용되어 있음에도,\
  100명대 이상의 플레이어를 성능 하락 없이 받아들이고 있습니다.
- **RPG 서버에서도 빠른 성능을 유지한 플랫폼**\
  단일 클러스터에서 100명의 플레이어를 TPS 하락 없이 안정적으로 유지하였으며,\
  4개의 클러스터에서 총 250명의 플레이어가 쾌적하게 플레이 할 수 있었습니다.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을
  Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **많은 스트리머가 선택한 플랫폼**\
  많은 스트리머 분들의 시청자 첨여용 버킷으로 선택받아 사용되고 있습니다.

<figure>
   <img src="https://badge.plazmamc.org/internal/bstats" alt="">
   
   <figcaption><p>Gerçek Zamanlı Plazma Kullanıcı Trendi</p></figcaption>
</figure>

## ⬇️ İndir

Plazma'yı indirebileceğiniz sayfaya aşağıdan erişebilirsiniz.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Sürüm desteği hakkında daha fazla bilgi mi almak istiyorsunuz?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot eklentileri ve Paper, Pufferfish, Purpur eklentileri.

[^2]: Microsoft Corporation tarafından.

[^3]: Sohbet raporlama sistemi devre dışı bırakıldığında sohbet tamamen sunucu tarafından işlendiği için Mojang'ın sohbet izleme işlemini engelleyebilirsiniz.

[^4]: Sistem mekanizmasının çalışması için oyunun kısa süreliğine duraklaması gereken süre.
