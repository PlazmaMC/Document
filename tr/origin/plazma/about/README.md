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
   [Paper](https://github.com/PaperMC/Paper) tabanlı olduğundan, internetten indirilebilen çoğu [en son eklenti](#user-content-fn-1)[^1] sorunsuz çalışmaktadır.
2. **Ayar gerektirmeyen optimize edilmiş yapı**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)'in tüm yamaları dahil edilmiş olup, bazı yerel optimize ve modlarla en iyi performansı sunmaktadır.
3. **İstediğiniz gibi özelleştirebileceğiniz oyun**\
   Plazma'ya dahil edilen [Purpur](https://github.com/PurpurMC/Purpur), oyunun genel özelliklerini değiştirmenize olanak tanır.
4. **Güvenli oyun sunucusu**\
   [Chat Raporları Yok](https://github.com/Aizistral-Studios/No-Chat-Reports) dahil edilmiş olup, Mojang'ın 1.19'dan itibaren eklenen [sohbet raporlama sistemi](#user-content-fn-3)[^3]'ni devre dışı bırakabilir ve teşhis bilgi toplayıcısı tamamen kaldırılarak izlenmeyen güvenli bir sunucuda oyun oynayabilirsiniz.
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

- **Karmaşık eklentileri doğru bir şekilde işleyen platform**\
  Geliştirici [IPECTER](https://github.com/IPECTER)'ın sunucusunda Plazma kullanılmaktadır. NMS ve yansıma ile çalışan özgün eklentiler, karmaşık ve büyük veri paketleri yoğun bir şekilde uygulanmış olmasına rağmen,
  100'den fazla oyuncuyu performans kaybı olmadan kabul etmektedir.
- **RPG sunucularında da yüksek performansı koruyan platform**\
  Tek bir kümede 100 oyuncuyu TPS düşüşü olmadan istikrarlı bir şekilde korumuş ve 4 kümede toplamda 250 oyuncunun sorunsuz oynayabileceği bir ortam sağlanmıştır.
- **Chunk/Entity'den ışık saçan platform**\
  Önceki Survival sunucusunda Chunk ve Entity'leri işlemede gecikmeler yaşanan platform, Purpur'dan Plazma'ya geçerek
  çoğu gecikmeyi azaltmayı başarmıştır.
- **Birçok yayıncının tercih ettiği platform**\
  Birçok ünlü yayıncının izleyici kitlesine hitap etmek için seçtiği bir platformdur.

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
