---
description: Plazma ile sunucu oluşturma yöntemini öğrenin.
---

# 👟 Başlangıç

Plazma'yı stabil bir şekilde kullanabilmek için, sistem aşağıdaki gereksinimleri karşılamalıdır.

|          | Minimum | Tavsiye Edilen |
| :------: | ------- | -------------- |
|  Mimari  | x64     | -              |
|    RAM   | 8GB     | 16GB           |
| Depolama | 1GB     | 8GB            |
|    JDK   | 17      | 21             |

Düzenli yapılandırma dosyası düzenlemesi için, [Visual Studio Code](https://code.visualstudio.com/download) gibi bir düzenleyici kurmanız da iyi olacaktır.

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Doğru çıktı" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' iç veya dış komut, yürütülebilir program veya
yürütme dosyası değil.
```

{% endcode %}

{% code title="JDK가 너무 오래됨" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 JDK 설치

본 설명서에서는 JDK의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](./#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}
{% tab title="Windows" %}

1. İlk olarak, [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) sitesinden **JDK 21**'i `.msi` formatında indirin.
2. İndirilen kurulum sihirbazını çalıştırın ve `Next`e tıklayın.
3. **Pencerenin sol ortasında görünen menüden `Set JAVA_HOME variable`'ı etkinleştirin ve ardından** `Next`e tıklayın.
4. JRE kurulumunu `Complete` seçeneğiyle tamamlayın.
   {% endtab %}

{% tab title="macOS" %}
[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) 에서 **JDK 21**을 `.dmg` 형태의 설치 마법사를 다운로드 한 후 실행하여 JRE를 설치합니다.
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
다음 명령어를 입력하여 JDK를 설치할 수 있습니다.

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
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Daha Fazla Bilgi</summary>

Yürütülebilir dosyanın adı `plazma-(version manager)-1.20.4-R0.1-SNAPSHOT-(mapping şekli).jar` olarak belirlenmiştir.

- **Mapping Şekli**\
  Mapping, Minecraft'ın gerçek kodunu ve karışık kodunu birleştiren bir tür haritadır.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang tarafından eşlenmiş, Vanilla Minecraft eşlemesidir. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Sol alt köşedeki indirme düğmesi ile başlangıç komut dosyasını indirebilirsiniz.\
**İndirdiğiniz başlangıç komut dosyasının işletim sisteminizle uyumlu olduğundan emin olun.**

***

## 4. Dosya Düzenleme

Şimdi indirdiğiniz başlangıç komut dosyasını ve Plazma'yı yeni bir klasöre taşıyın.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Şimdi başlangıç komut dosyasını çalıştırın. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. EULA Onayı

Başlangıç komut dosyasını bir kez çalıştırdıktan sonra, klasöre `eula.txt` dosyası oluşturulacaktır.

EULA[^9], [Mojang Studios](#user-content-fn-10)[^10]'un hizmetlerini kullanmak için kabul etmeniz gereken bir lisans sözleşmesidir.

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

EULA'yı kabul etmek için `eula.txt` dosyasındaki `eula=false`'ı `eula=true` olarak değiştirin ve kaydedin.

***

## 6. Dış Erişime İzin Verme (Windows)

Modern işletim sistemleri, dışarıdan gelen tehlikeli erişimleri engellemek için varsayılan olarak **güvenlik duvarı** ve **yönlendirici** ile dış erişimi engeller.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

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

| Mesaj                                     | Anlam                                                         |
| ----------------------------------------- | ------------------------------------------------------------- |
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

Sunucuyu nasıl özelleştireceğinizi öğrenmek için aşağıdaki kılavuzu inceleyin.

{% content-ref url="sonraki-adim.md" %}
[sonraki-adım.md](sonraki-adım.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
