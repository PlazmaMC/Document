---
description: Plazma ile sunucu oluşturma yöntemini öğrenin.
---

# 👟 Başlangıç

Plazma'yı stabil bir şekilde kullanabilmek için, sistem aşağıdaki gereksinimleri karşılamalıdır.

|          | Minimum | Tavsiye Edilen |
| :------: | :------ | :------------- |
|  Mimari  | x64     | -              |
|    RAM   | 8GB     | 16GB           |
| Depolama | 1GB     | 8GB            |
|    JRE   | 17      | 21             |

Düzenli yapılandırma dosyası düzenlemesi için, [Visual Studio Code](https://code.visualstudio.com/download) gibi bir düzenleyici kurmanız da iyi olacaktır.

***

## 1. JRE Kurulumu

Adından da anlaşılacağı gibi, Minecraft: **"Java"** Sürümü Java ile geliştirildiği için, çalıştırmak için JRE[^1] gereklidir.

Plazma, Mojang Studios'un resmi sunucu platformuna [dayandığı için](#user-content-fn-2)[^2], Plazma'yı kullanmak için de JRE kurmanız gerekmektedir.

### 1.1 JRE Varlığını Kontrol Etme

Sistemde JRE'nin kurulu olup olmadığını kontrol etmek için, [Çalıştır](#user-content-fn-3)[^3] penceresine [`cmd /k java --version`](#user-content-fn-4)[^4] yazıp çalıştırın.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Doğru çıktı" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="JRE yüklü değil" lineNumbers="true" %}

```log
'java' iç veya dış komut, yürütülebilir program veya
yürütme dosyası değil.
```

{% endcode %}

{% code title="JRE çok eski" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE Kurulumu

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. İlk olarak, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) sitesinden **JDK 21**'i `.msi` formatında indirin.
2. İndirilen kurulum sihirbazını çalıştırın ve `Next`e tıklayın.
3. **Pencerenin sol ortasında görünen menüden `Set JAVA_HOME variable`'ı etkinleştirin ve ardından** `Next`e tıklayın.
4. JRE kurulumunu `Complete` seçeneğiyle tamamlayın.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) sitesinden **JDK 21**'i `.dmg` formatında indirme sihirbazını çalıştırarak JRE'yi yükleyin.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Öncelikle, Azul Zulu deposunu APT'ye eklemek için terminalde aşağıdaki komutu çalıştırın.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Sonrasında, terminalde aşağıdaki komutu çalıştırarak JRE'yi kurun.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

JRE'yi yüklemek için aşağıdaki komutu girin.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Plazma İndirme

Plazma, çeşitli şekillerdeki yürütülebilir dosyaları sunmaktadır.

{% hint style="warning" %}

**Genellikle `Reobf Paperclip` kullanılır.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Daha Fazla Bilgi</summary>

Yürütülebilir dosyanın adı `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping şekli).jar` olarak belirlenmiştir.

- **Mapping Şekli**\
  Mapping, Minecraft'ın gerçek kodunu ve karışık kodunu birleştiren bir tür haritadır.
  - **Reobf**\
    Reobfuscated (yeniden karşıtlanmış), Spigot eşlem olarak da bilinen ve çoğu NMS eklentisinde kullanılan bir terimdir.\
    1.20.5'ten itibaren kullanımı sona erecektir.
  - **Mojmap**\
    Mojang tarafından eşlenmiş, Vanilla Minecraft eşlemesidir.
- **Sürüm Yöneticisi**\
  Sürüm yöneticisi, sunucu işletimi için gerekli kütüphaneleri sağlayan ve sunucu dosyalarını yamalayan sunucunun başlatıcısı olarak düşünülebilir.
  - **Paperclip**\
    PaperMC ekibi tarafından Paper ve diğer türetilmiş platformlar için geliştirilen bir yönetici, kütüphaneleri indirir ve sunucuya yama uygular.
  - **Bundler**\
    Vanilla Minecraft sürüm yöneticisidir.

</details>

***

## 3. Başlangıç Komut Dosyası Oluşturma

Plazma'yı hızlıca başlatmak ve sunucuyu otomatik olarak yeniden başlatmak için, [Başlangıç Komut Dosyası](#user-content-fn-6)[^6] oluşturmanız gerekmektedir.

[Flags.sh](https://flags.sh) adresinden başlangıç betiğini oluşturabilirsiniz. Plazma için kullanılacak bellek miktarını girdiğinizde komut otomatik olarak en uygun hale getirilir.

Sol alt köşedeki indirme düğmesi ile başlangıç komut dosyasını indirebilirsiniz.\
**İndirdiğiniz başlangıç komut dosyasının işletim sisteminizle uyumlu olduğundan emin olun.**

***

## 4. Dosya Düzenleme

Şimdi indirdiğiniz başlangıç komut dosyasını ve Plazma'yı yeni bir klasöre taşıyın.

{% hint style="warning" %}

**Klasör adı boşluk içermemeli ve İngilizce olmalıdır.**

Aksi takdirde Plazma veya JRE'nin düzgün çalışmayabileceğini unutmayın.

{% endhint %}

Şimdi başlangıç komut dosyasını çalıştırın. Windows için, <mark style="background-color:orange;">Güvenlik Duvarı İzinleri penceresinde, mutlaka **İzin Ver**'i seçmelisiniz</mark>.

***

## 5. EULA Onayı

Başlangıç komut dosyasını bir kez çalıştırdıktan sonra, klasöre `eula.txt` dosyası oluşturulacaktır.

EULA[^9], [Mojang Studios](#user-content-fn-10)[^10]'un hizmetlerini kullanmak için kabul etmeniz gereken bir lisans sözleşmesidir.

{% hint style="warning" %}

Eğer kabul etmezseniz, sunucuyu başlatamazsınız ve EULA'yı ihlal ederseniz hesabınız askıya alınabilir veya [cezalandırma](#user-content-fn-11)[^11] alabilirsiniz.

{% endhint %}

EULA'yı kabul etmek için `eula.txt` dosyasındaki `eula=false`'ı `eula=true` olarak değiştirin ve kaydedin.

***

## 6. Dış Erişime İzin Verme (Windows)

Modern işletim sistemleri, dışarıdan gelen tehlikeli erişimleri engellemek için varsayılan olarak **güvenlik duvarı** ve **yönlendirici** ile dış erişimi engeller.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Eğer yönlendiriciniz UPnP'yi desteklemiyorsa, yönlendiriciler farklı panel yapısına sahip olduğundan doğrudan araştırma yapmanız gerekmektedir.

Ayrıca [Ngrok](https://ngrok.com/) aracılığıyla geçici bir adres oluşturabilirsiniz.
{% endhint %}

{% hint style="warning" %}

**Linux veya macOS gibi (yaklaşık) UNIX tabanlı işletim sistemlerinde, güvenlik duvarı hizmetlerine göre farklı ayarlar gerekebilir, bu nedenle doğrudan bilgi araştırmalısınız.**

{% endhint %}

### 6.1 Port Yönlendirme Gerekliliğini Kontrol Etme

Aşağıdaki gibi girin ve çalıştırın.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Çıktı `True` ise burada durabilirsiniz, ancak `False` ise port yönlendirme yapmanız gerekmektedir.

### 6.2 Sunucuya Bağlanma

{% tabs %}

{% tab title="Uzaktan Erişim" %}

Port yönlendirme gerekli değilse veya zaten başarılı bir şekilde port yönlendirmesi yapıldıysa, şimdi sunucuya erişebilirsiniz.

Sunucuya bağlanmak için kullanılan adresi [buradan](https://ip.pe.kr/) kontrol edebilirsiniz.

{% endtab %}

{% tab title="UPnP ile Port Yönlendirme Denemesi" %}

Sunucu klasöründe `purpur.yml` dosyasında, `network.upnp-port-forwarding` özelliğini `true` olarak etkinleştirin.

Sonrasında sunucuyu yeniden başlattığınızda, Plazma otomatik olarak port yönlendirmesi deneyecektir.

Aşağıdaki mesaj, konsola yazdırılan UPnP başarısını gösterir ve konsolda `[UPnP] (mesaj)` şeklinde görüntülenir.

| Mesaj                                     | Anlam                                                         |
| ----------------------------------------- | ------------------------------------------------------------- |
| `Başarılı bir şekilde port açıldı (port)` | Port yönlendirme başarılı.                    |
| `Port (port) zaten açık`                  | Başka bir hizmet belirtilen portu kullanıyor. |
| `Port açılamadı (port)`                   | Port yönlendirme başarısız.                   |
| `Hizmet kullanılamıyor`                   | Router UPnP'yi desteklemiyor.                 |

Sunucu kapanırsa, Plazma otomatik olarak bağlantı noktalarını kapatır.

{% endtab %}

{% tab title="Ngrok ile Geçici Adres Oluşturma" %}

Ngrok'un kullanımı, kısa süreli testler, topluluk katılımı veya arkadaşlarla birlikte oynamak için faydalıdır.

1. [Ngrok websitesi](https://ngrok.com/download) üzerinden `Windows (64-bit)` ZIP dosyasını indirin.
2. İndirdiğiniz Ngrok'ü sunucu klasörüne yerleştirin.
3. [Ngrok kontrol paneli](https://dashboard.ngrok.com/get-started/your-authtoken) üzerinden [kimlik doğrulama belirteci oluşturun](#user-content-fn-13)[^13].
4. Sunucu klasöründe gösterilen komutu çalıştırın.
5. Çalıştırma betiğinin en üstüne `start /b ngrok tcp --region jp 25565`, en altına `taskkill /f /t /im ngrok.exe` ekleyin.
6. Konsolda gösterilen `Yönlendirme tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` adresinde, `0.tcp.jp.ngrok.io:12345` sunucunun adresidir.
7. Şimdi dışarıdan bu adres aracılığıyla bağlanabilirsiniz.

{% endtab %}

{% tab title="Yerel Bağlantıdan Erişim" %}

Sunucuya yerel ağdan erişmeye çalışıyorsanız, çalıştırma penceresinde `cmd /k ipconfig` komutunu çalıştırarak elde edilen `IPv4 adresi` ile bağlantı kurabilirsiniz.

Örneğin, komutu çalıştırdıktan sonra aşağıdaki gibi bir çıktı alırsanız,

```log
Windows IP Yapılandırması

Ethernet Adaptörü Ethernet:

    Bağlı DNS Soneği. . . . :
    IPv4 Adresi. . . . . . . . . : 192.168.3.7
    Alt Ağ Maskesi . . . . . . . : 255.255.255.0
    Varsayılan Ağ Geçidi . . . . . . : 192.168.3.1

```

Burada belirtilen IPv4 adresine `192.168.3.7` ile bağlanmaya çalışırsanız sunucuya yerel ağdan erişebilirsiniz.

Sunucu ve oyun aynı PC'de çalışıyorsa, `localhost` ile bağlanabilirsiniz.

{% endtab %}
{% endtabs %}

## 7. Gelişmek

Sunucuyu başarıyla başlattıysanız ve sunucunun düzgün çalıştığından eminseniz, şimdi sunucuyu özelleştirme zamanı.

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="sonraki-adim.md" %}
[sonraki-adım.md](sonraki-adım.md)
{% endcontent-ref %}

***

[^1]: Java Çalışma Ortamı, Java Runtime Environment.

[^2]: Plazma'nın temeli olan Paper, Spigot'a dayanmaktadır ve Spigot resmi sunucu platformuna dayanmaktadır.

[^3]: Windows tuşu + R

[^4]: Linux'ta `java --version` komutunu terminalden çalıştırın.

[^5]: JRE, Minecraft sunucu platformu gibi çeşitli türlerde olduğu gibi, açık kaynaklı bir projedir.

[^6]: Genellikle **launcher** olarak bilinir.

[^7]: "Oto-yeniden başlatma" etkinleştirildiğinde sunucu otomatik olarak yeniden başlatılır. `Control + C` tuşlarına basarak kapatılabilir.

[^8]: Sistemin yarısından fazlasını aşırı yüklemek önerilmez.

    Örneğin, sistem toplam bellek kapasitesi 8GB ise, 4GB'den fazlasını ayarlamak önerilmez.

[^9]: Son Kullanıcı Lisans Anlaşması, EULA. Daha fazla bilgi için [Minecraft websitesi](https://www.minecraft.net/ko-kr/usage-guidelines)'ni kontrol edin.

[^10]: Microsoft Corporation.

[^11]: Güney Kore'nin oyun endüstrisini teşvik etme yasası Madde 32(1)(9) uyarınca **Kore Microsoft Corporation** yasal olarak dava açabilir.

[^12]: Universal Plug & Play. Purpur, Plazma'da bulunan bu teknoloji sayesinde sunucu çalışırken otomatik olarak yönlendiriciyle iletişim kurar ve sadece sunucu çalışırken bağlantı noktalarını açar, bu nedenle doğrudan port yönlendirmesi yapmanıza gerek yoktur.

[^13]: Hesabınız yoksa, Google veya GitHub hesabınızı kullanarak Ngrok'a kaydolun.
