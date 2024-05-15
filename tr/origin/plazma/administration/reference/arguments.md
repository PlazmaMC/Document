---
description: Başlangıç argümanları ve sistem özelliklerini öğrenin.
---

# 🎛️ Argümanlar ve Özellikler

Başlangıç ​​parametreleri ve sistem özellikleri, Plazma'nın çalışmasına eklenen bir değer olarak [kullanılan komutlar](#user-content-fn-1)[^1] ile ilgilidir ve Plazma'nın genel işleyişine etki eder.

[명령어에 덧붙이는 위치](#user-content-fn-2)[^2]e göre **başlangıç argümanı** ve **sistem özellikleri** olarak ayrılır.

***

## Sistem özelliği <a href="#id-1" id="id-1"></a>

Sistem özellikleri, `-jar`'ın önüne yerleştirilir ve Plazma'nın başlatılması öncesinde JVM tarafından işlenen değerlerdir.

{% hint style="warning" %}

**Sistem özelliklerini değiştirmek, Plazma ve JVM'nin çalışma şeklini değiştirebilir ve oyunu büyük ölçüde etkileyebilir!**

Her sistem özelliğinin ne işe yaradığını kesin olarak bilmiyorsanız, **kesinlikle kullanmayın!**

{% endhint %}

### Kullanım şekli <a href="#id-1.1" id="id-1.1"></a>

Sistem özellikleri, `java` ve `-jar` arasına Java komut argümanı olarak eklenir.

Örneğin, `Plazma.dummyProperty` sistem özelliğini uygulamak istediğinizde, aşağıdaki gibi girerek sonraki özelliğe `37` girilir ve Plazma başlatılır.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`, bu argümanın JVM'e yerleşik olmadığını ve Plazma'ya eklenen özel bir argüman olduğunu belirtir ve

Özelliklere herhangi bir değer girilmezse değer [`true` olarak sabitlenir](#user-content-fn-3)[^3].

{% hint style="info" %}

**Paperweight serisi sunucu platformu, her platform için sistem özelliklerini ayırt etmek için özellik adlarında `.` işaretini içermektedir.**

Windows Powershell gibi bazı terminalde, bu tür argümanlara izin verilmeyebilir, bu nedenle argümanın her iki ucuna da `"` [eklemelisiniz](#user-content-fn-4)[^4].

{% endhint %}

### Tüm sistem özellikleri <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Kullanımdan kaldırılan işaret formatlarını günceller.

#### `debug.entities`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Varlık bilgileri ile ilgili hata ayıklama günlüklerini etkinleştirir.

#### `debug.rewriteForIDE`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

IDE'de hata ayıklama bilgilerini doğru şekilde yükleyebilmek için NMS revizyonunu devre dışı bırakır ve,\
iç versiyon bilgisini otomatik olarak yeniden haritalandırır.

#### `disable.watchdog`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Spigot'un Watchdog uyarı sistemi devre dışı bırakılır.

#### `letMeReload`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

`/reload` komutunun yeniden doğrulama iletişim kutusunu devre dışı bırakır.

{% hint style="danger" %}

**`/reload` komutu son derece kararsız olduğundan, `/reload` kullanımından sonra ortaya çıkan tüm sunucu sorunları kullanıcıya aittir.**

Eğer bir eklenti geliştiricisiyseniz ve eklentiyi güncellemeniz gerekiyorsa, `/reload` yerine hotswap kullanın.

{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Standart giriş/çıkış sistemini kullanan eklentileri devre dışı bırakır.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Mesajlaşma bileşenlerinde kullanımdan kaldırılan biçim algılandığında uyarır.

#### `Paper.bypassHostCheck`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Oyuncunun sunucuya bağlandığında sunucunun model eşleşme doğrulamasını devre dışı bırakır.

#### `Paper.debugDynamicMissingKeys`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

NBT nesnelerinde eksik anahtarlar için hata ayıklama günlüklerini etkinleştirir.

#### `Paper.debugInvalidSkullProfiles`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Hatalı kafatası profilleri hakkında hata ayıklama günlüklerini etkinleştirir.

Bu, tüm hatalı kafatası bloklarını konumlarıyla birlikte günlüğe kaydeder.

#### `Paper.disableChannelLimit`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Her bir oyuncuya uygulanan 128 tane eklenti [kanalı](#user-content-fn-5)[^5] sayısı sınırını devre dışı bırakır.

#### `Paper.disableClassPrioritization`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Eklenti sınıf öncelik sistemini devre dışı bırakır.

Eklenti gölgelendirmede sorun yaşandığında faydalıdır.

#### `Paper.disableFlushConsolidate`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Netty flush konsolidasyon sistemini devre dışı bırakır.

#### `Paper.excessiveTELimit`

- **Biçimi**: `Integer`
- **Varsayılan Değer**: `750`

Varlık sayısı belirtilen değerden fazla ise çoklu paketlere bölerek iletilir.

#### `Paper.filterThreshold`

- **Biçimi**: `Integer`
- **Varsayılan Değer**: `8192`

Sunucunun alabileceği maksimum paket boyutunu ayarlar.

#### `Paper.ignoreJavaVersion`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Java sürüm kontrolünü devre dışı bırakır.

{% hint style="danger" %}

**Bu şekilde, JVM'in mevcut olmayan kodlara erişmeye çalışabileceği unutulmamalıdır!**

Dünya ve diğer tüm dosyalar kalıcı olarak zarar görebilir ve oyunun genel mekanikleri bozulabilir.

Bu nedenle yaşanan tüm sorunlar sizin sorumluluğunuzdadır ve Plamza bunun için herhangi bir destek sağlamaz.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Biçimi**: `Integer`
- **Varsayılan Değer**: `64`

Eklenti [kanal](#user-content-fn-6)[^6] adının sınırını belirler.

#### `Paper.maxSignLength`

- **Biçimi**: `Integer`
- **Varsayılan Değer**: `80`

Tabelanın bir satırına girilebilecek maksimum karakter sayısını ayarlar.

#### `Paper.minPrecachedDatafixVersion`

- **Biçimi**: `Integer`
- **Varsayılan Değer**: `(Dünya Sürümü) + 1`

Önce başlanacak dünya güncelleme bilgisinin sürümünü ayarlar.

Çok sayıda bloğun güncellenmesi gereken durumlarda faydalı olabilir, ancak diğer durumlarda kullanılmaz.

#### `Paper.parseYamlCommentsByDefault`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `True`

YAML dosyalarındaki yorumların işlenmesini etkinleştirir.

#### `Paper.playerConnection.keepAlive`

- **Biçimi**: `Integer`
- **Varsayılan Değer**: `30`

Oyuncudan belirli bir süre (saniye cinsinden) hiçbir veri alınmazsa, oyuncuyu atar.

Genellikle, [oyun](#user-content-fn-7)[^7] sürekli olarak sunucuya [kalp atış sinyali](#user-content-fn-8)[^8] gönderir, bu nedenle [atılmaz ancak,](#user-content-fn-9)[^9] oyun yanıt vermezse çakışmış olarak kabul edilir ve sunucu artık oyuncuyu işlemez ve atar.

#### `Paper.skipServerPropertiesComments`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Sunucu özelliklerinin yorumlarını görmezden gelir.

#### `Paper.debug-sync-loads`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Senkron yükleme hata ayıklama günlüklerini etkinleştirir.

#### `Paper.enable-sync-chunk-writes`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Minecraft'un [varsayılan yükleme sistemi](#user-content-fn-10)[^10]'ni etkinleştirir.

Bu, her bir bloğu sırayla kaydetmeyi gerektirdiği için büyük performans düşüşüne neden olur.

#### `Paper.explicit-flush`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Ağ kanalının Açıkça Boşaltılmasını etkinleştirir.

#### `Paper.strict-thread-checks`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Ana iş parçacığında meydana gelen hataları her zaman kaydeder.

#### `Paper.tickList-warn-on-excessive-delay`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Zamanlamalı görevlerin aşırı gecikmeye sahip olması durumunda uyarı verir.

#### `Paperclip.patchOnly`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Varsayılan yürütülebilir dosyayı kullandığınızda, sunucuyu başlatmadan yalnızca yama uygular.

#### `Plazma.aggressiveOptimize`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

초기 구성을 더 강하게 최적화 합니다.

활성화 하면 서버가 더욱 빨라지고 안전해지지만, 게임 플레이에 큰 영향을 줄 수 있습니다.

#### `Plazma.disableConfigOptimization`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`
- **충돌**: `Plazma.aggressiveOptimize`

초기 구성을 최적화하지 않습니다.

이는 Paper의 기본 구성을 사용하도록 합니다.

#### `Plazma.iKnowWhatIAmDoing`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`

Plazma başlatıldığında görünen [uyarı metnini](#user-content-fn-11)[^11] bastırır.

#### `Plazma.useVanillaFavicon`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`

Plazma 브랜딩을 비활성화 하고 바닐라 기본 서버 패비콘을 사용하도록 합니다.

#### `Plazma.useVanillaConfiguration`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`
- **충돌**: `Plazma.disableConfigOptimization`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

{% hint style="danger" %}

**해당 속성은 패치된 모든 취약점을 되돌립니다!**

이는 서버 안전 및 성능에 크게 영향을 줄 수 있습니다.

해당 속성을 사용하여 발생하는 모든 문제는 서버 관리자에게 있습니다.

{% endhint %}

초기 구성을 Mojang에서 제공하는 기본값으로 제공합니다.

이는 Paper에서 적용한 모든 취약점 패치를 비활성화 합니다.

취약점 패치는 Paper 구성 또는 Plazma 구성에서 다시 활성화 할 수 있습니다.

#### `Plazma.vanillaize`

- **Biçimi**: `Boolean`
- **기본값**: `true`
- **충돌**: `Plazma.aggressiveOptimize`

{% hint style="info" %}

**해당 속성은 아직 개발중입니다.**

{% endhint %}

초기 구성을 바닐라에 가깝게 설정합니다.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며,
`Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Kullanımdan kaldırılan özellik <a href="#id-1.3" id="id-1.3"></a>

Aşağıdaki sistem özellikleri kullanımdan kaldırılmış özelliklerdir.

#### `timings.bypassMax`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`
- **Kullanım dışı**: Timings, Plazma'dan tamamen kaldırıldıktan sonra

Aikar'ın Timings API'sine iletilen değerin maksimumunun aşıp aşamayacağını belirler.

Buna rağmen, API'de istisna olmazsa hız sınırlaması uygulanır.

***

## Başlangıç argümanı <a href="#id-2" id="id-2"></a>

Başlangıç argümanı, `-jar *.jar`'ın arkasına girilir ve Plazma başlatıldığında işlenen bir değerdir.

### Kullanım şekli <a href="#id-2.1" id="id-2.1"></a>

Sistem özellikleri, `-jar *.jar`'ın arkasına programın komut argümanı olarak girilir.

Örneğin, `nogui` başlangıç argümanını uygulamak istediğinizde,\
şu şekilde girerek Plazma, başlatma sırasında `nogui` argümanını işler.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Tüm başlangıç argümanı <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Takma ad**: `b`
- **Varsayılan**: `bukkit.yml`

[Bukkit yapılandırma dosyası](../reference/configurations/bukkit.md)'nın adını ve konumunu ayarlar.

#### `command-settings`

- **Takma ad**: `c`
- **Varsayılan**: `commands.yml`

[Bukkit komut yapılandırma dosyası](../reference/configurations/bukkit.md)'nın adını ve konumunu ayarlar.

#### `config`

- **Takma ad**: `c`
- **Varsayılan**: `server.properties`

[Sunucu özellikleri](../reference/configurations/property.md) dosyasının adını ve konumunu ayarlar.

#### `demo`

Sunucuyu demo dünyasıyla başlatır.

#### `eraseCache`

Dünya yükseltme sonrası kalan önbellek dosyalarını siler.

#### `forceUpgrade`

Sürümü dikkate almadan dünyayı zorla [yükseltir](#user-content-fn-12)[^12].

#### `help`

- **Takma ad**: `?`

Plazma'nın tüm başlangıç argümanlarını ve açıklamalarını görüntüler.

#### `initSettings`

Yapılandırma dosyasını oluşturur ve sunucuyu kapatır.

#### `jfrProfile`

JFR profil oluşturmayı etkinleştirir.

#### `max-players`

- **Takma ad**: `s`, `size`
- **Varsayılan**: `(sunucu özellikleri)`

Kabul edilen maksimum [oyuncu](#user-content-fn-14)[^14] sayısını ayarlar.

#### `nogui`

Grafik arayüz panelini devre dışı bırakır.

#### `nojline`

JLine'ı devre dışı bırakır ve saf konsolu kullanır.

#### `online-mode`

- **Takma ad**: `o`
- **Varsayılan**: `(sunucu özellikleri)`

Oyuncuları Mojang kimlik doğrulama sunucusuyla doğrulamak için seçim yapar.

**Velocity ve benzeri proxy'ler kullanılmadığı takdirde [EULA](../getting-started/README.md#id-5) ihlali nedeniyle cezalandırılabilirsiniz.**

#### `paper-settings`

- **Takma ad**: `paper`
- **Varsayılan**: `paper.yml`

{% hint style="warning" %}

**Bu argüman, 1.19.4'ten itibaren kullanımdan kaldırılmıştır**

{% endhint %}

Kullanımdan kaldırılan PaperSpigot yapılandırma dosyasının konumunu ayarlar.

Bu, mevcut yapıyı yeni bir yapılandırma dosyasına taşımak için kullanılır ve daha sonra kullanılmaz.

#### `paper-settings-directory`

- **Takma ad**: `paper-dir`
- **Varsayılan**: `config`

[Paper yapılandırma dosyası](../reference/configurations/paper/README.md)'nın bulunduğu klasörün adını ve konumunu ayarlar.

#### `plazma-settings-directory`

- **Takma ad**: `plazma-dir`

[Plazma yapılandırma dosyası](../reference/configurations/plazma/README.md)'nın bulunduğu klasörün adını ve konumunu ayarlar.

#### `plugins`

- **Takma ad**: `p`
- **Varsayılan**: `plugins`

Eklenti klasörünün konumunu ayarlar.

#### `pufferfish-settings`

- **Takma ad**: `pufferfish`
- **Varsayılan**: `pufferfish.yml`

[Pufferfish yapılandırma dosyası](../reference/configurations/pufferfish.md)'nın adını ve konumunu ayarlar.

#### `purpur-settings`

- **Takma ad**: `purpur`
- **Varsayılan**: `purpur.yml`

[Purpur yapılandırma dosyası](../reference/configurations/purpur/README.md)'nın adını ve konumunu ayarlar.

#### `safeMode`

(Güvenli Mod) Sunucuyu tamamen saf bir şekilde başlatır.

#### `server-ip`

- **Takma ad**: `h`, `host`
- **Varsayılan**: `(sunucu özellikleri)`

Sunucunun ana bilgisayar adını veya [internet protokolü](#user-content-fn-13)[^13] adresini ayarlar.

#### `server-port`

- **Takma ad**: `p`, `port`
- **Varsayılan**: `(sunucu özellikleri)`

Sunucunun bağlantı noktasını ayarlar.

#### `server-name`

- **Varsayılan**: `A Plazma Sunucusu`

Sunucunun adını ayarlar.

#### `spigot-settings`

- **Takma ad**: `S`
- **Varsayılan**: `spigot.yml`

[Spigot yapılandırma dosyası](../reference/configurations/spigot.md)'nın adını ve konumunu ayarlar.

#### `version`

- **Takma ad**: `v`

Plazma sürümünü görüntüler.

#### `world-dir`

- **Takma ad**: `W`, `evren`, `dünya-konteyneri`
- **Varsayılan**: `(sunucu klasörü)`

Dünya dosyalarının kaydedildiği konumu ayarlar.

#### `world-name`

- **Takma ad**: `w`, `dünya`
- **Varsayılan**: `(sunucu özellikleri)`

Dünya dosyasının adını ayarlar.

***

[^1]: `java (...) -jar sunucu.jar (...)`

[^2]: Eklenen konuma bağlı olarak argüman işleme konumu değişir.

[^3]: Örneğin, `Plazma.iKnowWhatIAmDoing` değerini `true` olarak ayarlamak (etkinleştirmek) istediğinizde, `-DPlazma.iKnowWhatIAmDoing=true` yerine `-DPlazma.iKnowWhatIAmDoing` yazmak yeterlidir ve aynı şekilde çalışır.

[^4]: Örneğin, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Olay algılayıcı.

[^6]: Olay algılayıcı.

[^7]: İstemci.

[^8]: Kalp atışı gibi sunucu ile düzgün bağlantı kurulduğunu belirten sinyal.

[^9]: Purpur'un AFK atma özelliği, oyundan ayrılan oyuncuları da atmanıza olanak tanır.

[^10]: Senkron Chunk Yazma Sistemi, Sync Chunk Write System.

[^11]: `UYARI! Plazma beklenmedik sorunlara neden olabilir, bu nedenle halka açık bir sunucuda kullanmadan önce detaylı bir şekilde test ettiğinizden emin olun.`

[^12]: Oyundaki `dünya optimizasyonu` da aynı prensiple çalışır.

[^13]: Internet Protokolü, IP.

[^14]: `Seviye 2` ve üzeri yöneticiler hariç tutulur.
