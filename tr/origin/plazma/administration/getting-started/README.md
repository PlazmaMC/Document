---
description: Plazma ile sunucu oluşturma yöntemini öğrenin.
---

# 👟 Başlangıç

Plazma'yı stabil bir şekilde kullanabilmek için, sistem aşağıdaki gereksinimleri karşılamalıdır.

|          | Minimum | Tavsiye Edilen |
| :------: | ------: | -------------: |
|  Mimari  |     x64 |              - |
|    RAM   |     8GB |           16GB |
| Depolama |     1GB |            8GB |
|    JRE   |      17 |             21 |

Düzenli yapılandırma dosyası düzenlemesi için, [Visual Studio Code](https://code.visualstudio.com/download) gibi bir düzenleyici kurmanız da iyi olacaktır.

***

## 1. JRE Kurulumu

Adından da anlaşılacağı gibi, Minecraft: **"Java"** Sürümü Java ile geliştirildiği için, çalıştırmak için JRE[^1] gereklidir.

Plazma, Mojang Studios'un resmi sunucu platformuna [dayandığı için](#user-content-fn-2)[^2], Plazma'yı kullanmak için de JRE kurmanız gerekmektedir.

### 1.1 JRE Varlığını Kontrol Etme

Sistemde JRE'nin kurulu olup olmadığını kontrol etmek için, [Çalıştır](#user-content-fn-3)[^3] penceresine [`cmd /k java --version`](#user-content-fn-4)[^4] yazıp çalıştırın.

Aşağıdaki gibi bir çıktı alıyorsanız, [2. adıma](setup.md#id-2) geçebilirsiniz.

{% code title="올바른 출력" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Yukarıdaki gibi bir çıktı alamazsanız veya aşağıdaki gibi bir çıktı alırsanız, JRE yüklü değil demektir veya çok eski olduğu için [1.2 adımı](setup.md#id-1.2) tamamlamanız gerekmektedir.

{% code title="JRE가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JRE Kurulumu

Bu kılavuzda JRE'nin [türlerinden biri](#user-content-fn-5)[^5] olan Azul Zulu'yu kullanacağız.

Kurulumu tamamladıktan sonra, kurulumun doğru bir şekilde yapıldığını kontrol etmek için [1.1 adımını](setup.md#id-1.1) tekrarlayın.

{% tabs %}

{% tab title="Windows" %}

1. İlk olarak, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=windows\&architecture=x86-64-bit\&package=jdk#zulu) sitesinden **JDK 21**'i `.msi` formatında indirin.
2. İndirilen kurulum sihirbazını çalıştırın ve `Next`e tıklayın.
3. **Pencerenin sol ortasında görünen menüden `Set JAVA_HOME variable`'ı etkinleştirin ve ardından** `Next`e tıklayın.
4. JRE kurulumunu `Complete` seçeneğiyle tamamlayın.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\&os=macos\&architecture=x86-64-bit\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

먼저, 다음 명령어를 터미널에서 실행하여 APT에 Azul Zulu 저장소를 추가합니다.

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

다음 명령어를 입력하여 JRE를 설치할 수 있습니다.

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

**대부분의 경우에는 `Reobf Paperclip`을 사용합니다.**

Geliştiriciler veya farklı şekiller hakkında meraklı olanlar için aşağıdaki bilgiler vardır.\
Normal kullanıcılar için [3. adımı](setup.md#id-3) atlayabilirsiniz.

{% endhint %}

<details>

<summary>Daha Fazla Bilgi</summary>

Yürütülebilir dosyanın adı `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping şekli).jar` olarak belirlenmiştir.

- **Mapping Şekli**\
  Mapping, Minecraft'ın gerçek kodunu ve karışık kodunu birleştiren bir tür haritadır.
  - **Reobf**\
    Yeniden karıştırma, Spigot eşleşmesi olarak da bilinir ve çoğu NMS eklentisinde kullanılır.\
    1.20.5'ten itibaren kullanımı sona erecektir.
  - **Mojmap**\
    Mojang eşleşmesi, vanilla Minecraft eşlemesidir.
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

[Flags.sh](https://flags.sh) üzerinden başlangıç komut dosyasını [oluşturabilirsiniz.](#user-content-fn-7)[^7]\
Plazma için [kullanılacak belleği](#user-content-fn-8)[^8] girdikten sonra komut otomatik olarak optimize edilir.

Sol alt köşedeki indirme düğmesi ile başlangıç komut dosyasını indirebilirsiniz.\
**İndirdiğiniz başlangıç komut dosyasının işletim sisteminizle uyumlu olduğundan emin olun.**

***

## 4. Dosya Düzenleme

Şimdi indirdiğiniz başlangıç komut dosyasını ve Plazma'yı yeni bir klasöre taşıyın.

{% hint style="warning" %}

**폴더 명칭은 반드시 띄어 쓰기가 없고, 영어로 설정되어야 합니다.**

Aksi takdirde Plazma veya JRE'nin düzgün çalışmayabileceğini unutmayın.

{% endhint %}

Şimdi başlangıç komut dosyasını çalıştırın. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시 **허용**을 선택</mark>해야 합니다.

***

## 5. EULA Onayı

Başlangıç komut dosyasını bir kez çalıştırdıktan sonra, klasöre `eula.txt` dosyası oluşturulacaktır.

EULA[^9], [Mojang Studios](#user-content-fn-10)[^10]'un hizmetlerini kullanmak için kabul etmeniz gereken bir lisans sözleşmesidir.

EULA'yı kabul etmezseniz sunucuyu başlatamaz ve EULA'yı ihlal ederseniz hesabınız askıya alınabilir veya [cezalandırılabilirsiniz.](#user-content-fn-11)[^11]

EULA'yı kabul etmek için `eula.txt` dosyasındaki `eula=false`'ı `eula=true` olarak değiştirin ve kaydedin.

***

## 6. Dış Erişime İzin Verme (Windows)

Modern işletim sistemleri, dışarıdan gelen tehlikeli erişimleri engellemek için varsayılan olarak **güvenlik duvarı** ve **yönlendirici** ile dış erişimi engeller.

Windows için, güvenlik duvarını [3. adımda](setup.md#id-3) onayladığınızdan, sadece port yönlendirmesi yapmanız gerekmektedir.

{% hint style="info" %}

**해당 가이드에서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Eğer yönlendiriciniz UPnP'yi desteklemiyorsa, yönlendiriciler farklı panel yapısına sahip olduğundan doğrudan araştırma yapmanız gerekmektedir.

Ayrıca [Ngrok](https://ngrok.com/) aracılığıyla geçici bir adres oluşturabilirsiniz.
{% endhint %}

{% hint style="warning" %}

**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**

{% endhint %}

### 6.1 Port Yönlendirme Gerekliliğini Kontrol Etme

Aşağıdaki gibi girin ve çalıştırın.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Çıktı `True` ise burada durabilirsiniz, ancak `False` ise port yönlendirme yapmanız gerekmektedir.

### 6.2 Sunucuya Bağlanma

{% tabs %}

{% tab title="외부에서 접속" %}

포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Sunucuya bağlanmak için kullanılan adresi [buradan](https://ip.pe.kr/) kontrol edebilirsiniz.

{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}

서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

Sonrasında sunucuyu yeniden başlattığınızda, Plazma otomatik olarak port yönlendirmesi deneyecektir.

Aşağıdaki mesaj, konsola yazdırılan UPnP başarısını gösterir ve konsolda `[UPnP] (mesaj)` şeklinde görüntülenir.

| Mesaj                                     | Anlam                                         |
| ----------------------------------------- | --------------------------------------------- |
| `Başarılı bir şekilde port açıldı (port)` | Port yönlendirme başarılı.                    |
| `Port (port) zaten açık`                  | Başka bir hizmet belirtilen portu kullanıyor. |
| `Port açılamadı (port)`                   | Port yönlendirme başarısız.                   |
| `Hizmet kullanılamıyor`                   | Router UPnP'yi desteklemiyor.                 |

Sunucu kapanırsa, Plazma otomatik olarak bağlantı noktalarını kapatır.

{% endtab %}

{% tab title="Ngrok으로 임시 주소 생성" %}

Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. [Ngrok websitesi](https://ngrok.com/download) üzerinden `Windows (64-bit)` ZIP dosyasını indirin.
2. İndirdiğiniz Ngrok'ü sunucu klasörüne yerleştirin.
3. [Ngrok kontrol paneli](https://dashboard.ngrok.com/get-started/your-authtoken) üzerinden [kimlik doğrulama belirteci oluşturun](#user-content-fn-13)[^13].
4. Sunucu klasöründe gösterilen komutu çalıştırın.
5. Çalıştırma betiğinin en üstüne `start /b ngrok tcp --region jp 25565`, en altına `taskkill /f /t /im ngrok.exe` ekleyin.
6. Konsolda gösterilen `Yönlendirme tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` adresinde, `0.tcp.jp.ngrok.io:12345` sunucunun adresidir.
7. Şimdi dışarıdan bu adres aracılığıyla bağlanabilirsiniz.

{% endtab %}

{% tab title="로컬에서 접속" %}

로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

Örneğin, komutu çalıştırdıktan sonra aşağıdaki gibi bir çıktı alırsanız,

```log
Windows IP 구성

이더넷 어댑터 이더넷:

    연결된 DNS 접미사. . . . :
    IPv4 주소. . . . . . . . . : 192.168.3.7
    서브넷 마스크 . . . . . . . : 255.255.255.0
    기본 게이트웨이 . . . . . . : 192.168.3.1

```

Burada belirtilen IPv4 adresine `192.168.3.7` ile bağlanmaya çalışırsanız sunucuya yerel ağdan erişebilirsiniz.

Sunucu ve oyun aynı PC'de çalışıyorsa, `localhost` ile bağlanabilirsiniz.

{% endtab %}
{% endtabs %}

## 7. Gelişim Aşaması

Sunucuyu başarıyla başlattıysanız ve sunucunun düzgün çalıştığından eminseniz, şimdi sunucuyu özelleştirme zamanı.

Sunucuyu nasıl özelleştireceğinizi öğrenmek için aşağıdaki kılavuza göz atın.

{% content-ref url="customization.md" %}
[customization.md](customization.md)
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
