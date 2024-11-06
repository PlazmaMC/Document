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
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Kullanım şekli <a href="#id-1.1" id="id-1.1"></a>

Sistem özellikleri, `java` ve `-jar` arasına Java komut argümanı olarak eklenir.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D`, bu argümanın JVM'e yerleşik olmadığını ve Plazma'ya eklenen özel bir argüman olduğunu belirtir ve

Özelliklere herhangi bir değer girilmezse değer [`true` olarak sabitlenir](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
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
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

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

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

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

- **형태**: `Integer`
- **Varsayılan Değer**: `750`

Varlık sayısı belirtilen değerden fazla ise çoklu paketlere bölerek iletilir.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Varsayılan Değer**: `8192`

Sunucunun alabileceği maksimum paket boyutunu ayarlar.

#### `Paper.ignoreJavaVersion`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `False`

Java sürüm kontrolünü devre dışı bırakır.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Dünya ve diğer tüm dosyalar kalıcı olarak zarar görebilir ve oyunun genel mekanikleri bozulabilir.

Bu nedenle yaşanan tüm sorunlar sizin sorumluluğunuzdadır ve Plamza bunun için herhangi bir destek sağlamaz.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Varsayılan Değer**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Varsayılan Değer**: `80`

Tabelanın bir satırına girilebilecek maksimum karakter sayısını ayarlar.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Varsayılan Değer**: `(Dünya Sürümü) + 1`

Önce başlanacak dünya güncelleme bilgisinin sürümünü ayarlar.

Çok sayıda bloğun güncellenmesi gereken durumlarda faydalı olabilir, ancak diğer durumlarda kullanılmaz.

#### `Paper.parseYamlCommentsByDefault`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `True`

YAML dosyalarındaki yorumların işlenmesini etkinleştirir.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Varsayılan Değer**: `30`

Oyuncudan belirli bir süre (saniye cinsinden) hiçbir veri alınmazsa, oyuncuyu atar.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

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
- **Çarpışma**: `Plazma.disableConfigOptimization`

İlk yapılandırmayı daha güçlü bir şekilde optimize eder.

Aktive edildiğinde sunucu daha hızlı ve güvenli hale gelir, ancak oyun oynama üzerinde büyük etkileri olabilir.

#### `Plazma.disableConfigOptimization`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`
- **Çarpışma**: `Plazma.aggressiveOptimize`

İlk yapılandırmayı optimize etmeyecek.

Bu, Paper'ın varsayılan yapılandırmasını kullanır.

#### `Plazma.iKnowWhatIAmDoing`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`

Plazma markasını devre dışı bırakır ve vanilya temel sunucu favicon'unu kullanacak şekilde yapılandırır.

#### `Plazma.useVanillaConfiguration`

- **Biçimi**: `Boolean`
- **Varsayılan Değer**: `false`
- **Çarpışma**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Bu, sunucu güvenliği ve performansı üzerinde büyük etkilere sahip olabilir.

Bu özellikten kaynaklanan herhangi bir sorumluluk sunucu yöneticisine aittir.
{% endhint %}

İlk yapılandırmayı Mojang tarafından sağlanan varsayılan değerlerle sunar.

Bu, Paper'da uygulanan tüm güvenlik açıkları yamalarını devre dışı bırakır.

Güvenlik açıkları yamaları, Paper yapılandırmasında veya Plazma yapılandırmasında yeniden etkinleştirilebilir.

#### `Plazma.vanillaize`

- **Biçimi**: `Boolean`
- **Varsayılan**: `true`
- **Çarpışma**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

İlk yapılandırmayı vanilyaya yakın olarak ayarlar.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

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

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Takma ad**: `c`
- **Varsayılan**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Takma ad**: `c`
- **Varsayılan**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Sunucuyu demo dünyasıyla başlatır.

#### `eraseCache`

Dünya yükseltme sonrası kalan önbellek dosyalarını siler.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

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

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Grafik arayüz panelini devre dışı bırakır.

#### `nojline`

JLine'ı devre dışı bırakır ve saf konsolu kullanır.

#### `online-mode`

- **Takma ad**: `o`
- **Varsayılan**: `(sunucu özellikleri)`

Oyuncuları Mojang kimlik doğrulama sunucusuyla doğrulamak için seçim yapar.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Takma ad**: `paper`
- **Varsayılan**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Kullanımdan kaldırılan PaperSpigot yapılandırma dosyasının konumunu ayarlar.

Bu, mevcut yapıyı yeni bir yapılandırma dosyasına taşımak için kullanılır ve daha sonra kullanılmaz.

#### `paper-settings-directory`

- **Takma ad**: `paper-dir`
- **Varsayılan**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Takma ad**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Takma ad**: `p`
- **Varsayılan**: `plugins`

Eklenti klasörünün konumunu ayarlar.

#### `pufferfish-settings`

- **Takma ad**: `pufferfish`
- **Varsayılan**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Takma ad**: `purpur`
- **Varsayılan**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

(Güvenli Mod) Sunucuyu tamamen saf bir şekilde başlatır.

#### `server-ip`

- **Takma ad**: `h`, `host`
- **Varsayılan**: `(sunucu özellikleri)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

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

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

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

[^13]: `Seviye 2` ve üzeri yöneticiler hariç tutulur.

[^14]: Internet Protokolü, IP.
