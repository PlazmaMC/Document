---
description: Sunucuyu özelleştirmenin yollarını öğrenin.
---

# 📶 발전하기

Mojang Studios tarafından sağlanan resmi sunucu platformunu kullanmadan
Plazma ve benzeri özelleştirilmiş sunucu platformunu kullanmanın nedeni, güçlü
**özelleştirme** imkanı sunmasıdır.

Aşağıda Plazma'yı özelleştirmek ve kullanmak için çeşitli yöntemler bulunmaktadır.

## Yapılandırma Değişikliği <a href="#id-1" id="id-1"></a>

Plazma'yı özelleştirmenin en temel yolu, yapılandırmayı değiştirmektir.

Plazma, oyun mekaniği ve yaratıkların özellikleri gibi güçlü yapılandırma ayarlarını sunmaktadır.

Plazma'nın yapılandırması hakkında daha fazla bilgi için aşağıdaki sayfaya bakınız.

{% content-ref url="../reference/configurations/" %}
[yapılandırmalar](../reference/configurations/)
{% endcontent-ref %}

***

## Eklenti Kullanımı <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma, Tüm Kağıt Tabanlı Eklentileri Destekler.**

Spigot eklentileri 1.20.5 sürümünden itibaren Paper'ın eşleme değişiklikleri nedeniyle bazıları düzgün çalışmayabilir, ancak Paper, Pufferfish ve Purpur gibi Paper'a dayalı çoğu eklenti Plazma'da da sorunsuz çalışır ve düzgün çalışmıyorsa bu Plazma'nın hatası olduğundan lütfen [bildiriniz.](../diagnosis/plugins.md)

{% endhint %}

Plazma'yı kullanmanın ve kişiselleştirmenin en güçlü yolu.
Plazma'nın güçlü eklenti ekosistemi sunucuyu kolayca kişiselleştirmenizi sağlar.

Eklenti bulma ve indirme işlemi için çeşitli yöntemler bulunmaktadır. Bazı eklentiler
genel depolama hizmetlerine eklentileri yüklerken, bazıları GitHub veya kendi
sitelerine yüklerler.

{% hint style="caution" %}

**Eklentiler sistemle doğrudan etkileşebilir!**

VirusTotal gibi hizmetler kullanarak eklentileri uygulamadan önce her zaman güvenli olup olmadığını kontrol edin veya
güvenilir bir hizmetten eklentiyi indirin.

{% endhint %}

Eklenti indirmek için kullanılan hizmetlerin çeşitli olduğunu unutmayın. Bu hizmetler arasında [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) gibi hizmetler bulunmaktadır ve eklentiler güvenli olup olmadıkları kontrol edilerek dağıtılmaktadır.

### Eklenti Uygulama <a href="#id-2.1" id="id-2.1"></a>

Eklentiyi indirdikten sonra, şimdi eklentiyi uygulama zamanı.

1. Eklentiler `.jar` veya `Java Yürütülebilir Dosya` şeklinde olacaktır.\
   Bazı eklentiler sıkıştırılmış dosya olarak gelebilir, bu durumda
   sıkıştırılmış dosyayı açın ve içinde `bukkit`, `spigot` veya `paper` içeren
   bir dosya varsa ve `fat` içeren bir dosya varsa, `fat` dosyasını kullanın.
2. İndirdiğiniz dosyayı sunucu klasöründeki `plugins` klasörüne koyun ve sunucuyu (yeniden) başlatın.
3. Plazma başladığında, konsola yeni içerikler yazdırılacaktır.
   Bu, Plazma'nın eklentiyi başarıyla yüklediği anlamına gelir.
4. Plazma eklentiyi başarıyla yüklemiş olsa bile, eklentiyi başlatamayabilir.
   `/plugins` komutunu kullanarak mevcut sunucuda yüklenen eklentileri listeleyebilirsiniz.
   Yüklediğiniz eklentinin adı <mark style="background-color:red;">kırmızı</mark> değilse <mark style="background-color:green;">yeşil</mark> ise eklenti başarıyla yüklendi demektir.

Eğer eklenti başarıyla yüklenmediyse, sorunun çözümünü aşağıdaki sayfadan bulabilirsiniz.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Veri Paketi Kullanımı <a href="#id-3" id="id-3"></a>

Veri paketi, Minecraft'ın varsayılan olarak sunduğu kişiselleştirme yöntemidir ve
[Kaynak Paketi](#user-content-fn-1)[^1] ile benzerdir.

Veri paketi kullanarak yeni yaratıklar ve meydan okumalar ekleyerek oyunun içinde bazı değişiklikler yapabilirsiniz.

{% hint style="caution" %}

**Veri paketi dünyayı bozabilir!**

Bazı bozuk veri paketleri dünyayı bozabilir ve bu geri alınamaz.

Bu nedenle, veri paketini uygulamadan önce dünyayı yedeklemeniz önerilir.

{% endhint %}

Veri paketleri de birçok hizmetten indirilebilir, [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) gibi birçok hizmette bulunabilir.

Veri paketini indirdikten sonra, sunucunun dünya klasörüne `datapacks` klasörüne koyarak uygulayabilirsiniz.
Klasör yoksa oluşturarak ekleyebilirsiniz.

{% hint style="warning" %}

**[Bazı veri paketleri](#user-content-fn-2)[^2] uygulandığında ilk kez düzgün bir şekilde uygulanmayabilir.**

Bu duruma karşı sunucuyu **2 kez** yeniden başlatmanız önerilir.

{% endhint %}

Veri paketleri Minecraft'ın sürümü güncellendiğinde kolayca bozulabilir.

Özellikle, veri paketi tamamen bozulduğunda, sunucu çökeceği için,
sunucuyu güncellemeden önce yeterli test yapmak önemlidir.

{% hint style="info" %}

**Sunucu başlatma komutunun arkasına `safeMode` yazarak tüm veri paketlerini devre dışı bırakabilir ve sunucuyu başlatabilirsiniz.**

[Daha fazla bilgi için `Referans > Argümanlar ve Özellikler` bölümüne bakınız.](../reference/arguments.md#safeMode)

{% endhint %}

Uygulanan veri paketlerini `/datapack list` komutuyla kontrol edebilirsiniz.

***

## Optimizasyon <a href="#id-4" id="id-4"></a>

Plazma'ya birçok optimizasyon yaması uygulanmıştır. Ayrıca, Plazma ilk başlatıldığında otomatik olarak yapılandırmayı optimize eder, bu nedenle [Başlamak](./README.md) kılavuzunu takip ettiyseniz ek optimizasyon işlemlerine ihtiyaç duymazsınız.

Ancak, birçok oyuncu bağlandığında veya dünya çok büyükse, ek optimizasyon işlemleri için aşağıdaki kılavuzu takip edebilirsiniz.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Vekil <a href="#id-5" id="id-5"></a>

Vekil sunucuları, sunucuları birbirine bağlar ve oyuncuların ek işlem olmadan sunucular arasında geçiş yapmasını veya diğer sunucularla iletişim kurmasını sağlar.

Güvenli ve doğru vekil yapılandırması hakkında bilgi için aşağıdaki sayfaya bakınız.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Güvenlik <a href="#id-5" id="id-5"></a>

Minecraft, çevrimiçi ortamda da kolayca [Zararlı Yazılım Saldırı Motoru](#user-content-fn-3)[^3]'nü bulabileceğiniz modlara sahiptir.

Genel oyunlarda çalışabilen çoğu zayıf nokta [varsayılan olarak engellenmiş olsa da](#user-content-fn-4)[^4],
Zayıf noktaları saldırmak için üçüncü taraf yükleyiciler kullanılarak engellenmemiştir.

Bu nedenle, sunucu açık bir şekilde erişilebilir durumdaysa, zayıf nokta kullanımını engellemek için anti-hile eklentisi vb. kurulumu yapmak ve
ve sunucunun çökmesi durumunda hızlı bir şekilde kurtarılabilmesi için vekil, otomatik yeniden başlatma, yedekleme vb. yapılandırmaları yapmanız önerilir.

### İzin Ayarları <a href="#id-5.1" id="id-5.1"></a>

Bazı eklentilerin yönetici komutlarında uygun izinlerin ayarlanmamış zayıf noktaları olabilir.

[LuckPerms](https://luckperms.net/) vb. izin yönetimi eklentilerini kullanarak,
normal kullanıcıların izinlerini kısıtlamak tavsiye edilir.

### X-Ray Engelleme <a href="#id-5.2" id="id-5.2"></a>

X-Ray, temel optimizasyon istemcilerinde kolayca kullanılabilen zayıf noktalardan biridir.

Plazma, X-Ray'i varsayılan olarak engelleyebileceğiniz bir yapılandırma sunmaktadır.

X-Ray engelleme yöntemi ve açıklamaları için aşağıdaki sayfaya bakınız.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Beyaz Liste <a href="#id-5.3" id="id-5.3"></a>

Yalnızca belirli kullanıcıların sunucuya erişmesine izin vermek istiyorsanız,
[Ngrok](./README.md#id-6.2) kullanarak [şifrelenmiş sunucu adresini kullan](#user-content-fn-5)[^5] veya
başka oyuncuların sunucuya erişmesini engellemek için beyaz liste oluşturmak da önerilir.

Sunucu konsolundan `/whitelist add <oyuncu>` komutunu kullanarak bir oyuncunun erişimini sağlayabilir veya,
`/whitelist remove <oyuncu>` ile bir oyuncunun erişimini tekrar engelleyebilirsiniz.

Erişime izin verilen oyuncuları görmek için `/whitelist query` komutunu kullanın.

***

[^1]: Ya da Minecraft: Bedrock Sürümü'nün eklentileri.

[^2]: Yaratıkların eklenmesi vb.

[^3]: Genellikle "hack" olarak adlandırılır.

[^4]: Yapılandırma optimize edilmemişse, Plazma eskiyse veya yeni keşfedilen zayıf noktalar varsa engellenmemiş olabilir.

[^5]: Oyuncular sunucuya Ngrok proxy sunucusu aracılığıyla bağlandığında, her yeniden başlatmada farklı bir Ngrok adresi verilir.
