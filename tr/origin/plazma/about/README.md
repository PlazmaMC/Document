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

1. **Güçlü eklenti ekosistemi**\
   [Paper](https://github.com/PaperMC/Paper) temel alınarak yapılmıştır,
   İnternetten indirilebilen çoğu [en son eklenti](#user-content-fn-1)[^1] sorunsuz çalışır.
2. **Ayar gerektirmeyen optimize**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) tüm yamaları içerir ve,
   Bazı yerel optimize ve modlarla en iyi performansı sunar.
3. **Oyunu istediğiniz gibi özelleştirin**\
   Plazma ile birlikte gelen [Purpur](https://github.com/PurpurMC/Purpur) oyunun genel özelliklerini
   değiştirmenize olanak tanır.
4. **Güvenli bir şekilde sunucu oynayın**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports) dahildir ve 1.19'dan itibaren eklenen
   [Mojang](#user-content-fn-2)[^2] [sohbet raporlama sistemi](#user-content-fn-3)[^3] devre dışı bırakılabilir,\
   Teşhis bilgisi toplayıcısı tamamen kaldırılarak izlenmeyen güvenli bir sunucuda oynayabilirsiniz.
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

- **Karmaşık eklentileri doğru şekilde işleyen platform**\
  Geliştirici [IPECTER](https://github.com/IPECTER)'ın sunucusunda Plazma kullanılmaktadır.\
  NMS ve yansıma ile çalışan yerleşik eklentiler, karmaşık ve büyük veri paketleriyle yoğun bir şekilde uygulanmış olmasına rağmen,
  100'den fazla oyuncuyu performans düşüşü olmadan kabul etmektedir.
- **RPG sunucularında hızlı performans sağlayan platform**\
  Tek bir kümede 100 oyuncuyu TPS düşüşü olmadan istikrarlı bir şekilde korumuş ve,
  4 kümede toplamda 250 oyuncunun rahatça oynayabileceği sağlanmıştır.
- **Chunk/entity'lere ışık tutan platform**\
  Önceki sürümde survival sunucularında chunk ve entity işleme gecikmeleri yaşandı, Plazma'ya geçiş yaparak
  Purpur'dan Plazma'ya büyük ölçüde gecikmeleri azaltmayı başardık.
- **Birçok yayıncının tercih ettiği platform**\
  Birçok yayıncı tarafından izleyici katılımı için seçilen bir kova olarak kullanılmaktadır.

<a href="https://bstats.org/plugin/server-implementation/Plazma/18047">
   <img src="https://badge.plazmamc.org/internal/bstats" alt="Gerçek Zamanlı Plazma Kullanıcı Eğilimi">
</a>

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
