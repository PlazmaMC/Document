---
description: Научете как да създадете сървър с Plazma.
---

# 👟 Започване

За стабилно използване на Plazma, системата трябва да отговаря на следните изисквания.

|                            | Минимални | Препоръчителни |
| :------------------------: | :-------- | :------------- |
|         Архитектура        | x64       | -              |
|             RAM            | 8GB       | 16GB           |
| Пространство за съхранение | 1GB       | 8GB            |
|             JRE            | 17        | 21             |

За улеснение на редакцията на конфигурационни файлове, е добре да инсталирате редактор като [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Инсталиране на JRE

Както се разбира от името, Minecraft: **"Java"** Edition е разработен на Java и изисква JRE[^1] за стартиране.

Понеже Plazma се базира на официалната сървърна платформа на Mojang Studios[^2], за да използвате Plazma, трябва да инсталирате JRE.

### 1.1 Проверка на наличността на JRE

За да проверите дали JRE е инсталиран на системата, въведете [`cmd /k java --version`](#user-content-fn-4)[^4] в [командния ред](#user-content-fn-3) и го стартирайте.

Когато се покаже по следния начин, преминаваме към [Стъпка 2](#id-2).

{% code title="Правилно изход" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

Ако не се показва по горе описаното или се показва по-долу, това означава, че няма или е много стара JRE, и трябва да изпълните [Стъпка 1.2](#id-1.2).

{% code title="JRE не е инсталиран" lineNumbers="true" %}

```log
'java'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```

{% endcode %}

{% code title="JRE е прекалено стар" lineNumbers="true" %}

```log
Неразпозната опция: --version
Грешка: Не може да се създаде виртуалната машина Java.
Грешка: Възникна фатално изключение. Програмата ще излезе.
```

{% endcode %}

### 1.2 Инсталиране на JRE

В това ръководство се използва Azul Zulu като [един от видовете](#user-content-fn-5)[^5] на JRE.

След като сте завършили инсталацията, проверете дали инсталацията е завършена правилно, като изпълните отново [Стъпка 1.1](#id-1.1).

{% tabs %}

{% tab title="Windows" %}

1. Първоначално изтеглете **JDK 21** от [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu) във формат `.msi`.
2. Стартирайте изтегления инсталационен мастър и кликнете `Next`.
3. **Активирайте `Set JAVA_HOME variable` от менюто в средата наляво на прозореца,** след което кликнете `Next`.
4. Натиснете `Install`, за да завършите инсталацията на JRE.

{% крайнаКартка %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) изтеглете **JDK 21** от `.dmg` формата и стартирайте инсталационния магьосник, за да инсталирате JRE.

{% крайнаКартка %}

{% tab title="Debian/Ubuntu" %}

Първоначално изпълнете следната команда в терминала, за да добавите хранилището на Azul Zulu към APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

След това инсталирайте JRE, като изпълните следната команда в терминал.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% крайнаКартка %}

{% tab title="Fedora/RHEL" %}

Можете да инсталирате JRE, като въведете следната команда.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% крайнаКартка %}
{% крайниКартки %}

***

## 2. Изтегляне на Plazma

Plazma предоставя различни видове изпълними файлове.

{% hint style="warning" %}

**Повечето случаи използват `Reobf Paperclip`.**

Следното е предназначено за разработчици или за тези, които се интересуват от различни характеристики.\
Ако сте обикновен потребител, може да прескочите към [Стъпка 3](#id-3) без проблем.

{% endhint %}

<details>

<summary>Научете повече</summary>

Името на изпълнимия файл е `plazma-(версия на управителя)-1.20.4-R0.1-SNAPSHOT-(форма на мапиране).jar`.

- **Форма на мапиране**\
  Мапирането е вида на карта, която свързва реалния код на Minecraft със затрудненият код.
  - **Reobf**\
    Reobfuscated (재난독화), известен още като Spigot мапинг, използва се в повечето NMS плъгини.\
    Ще бъде прекратено използването му след версия 1.20.5.
  - **Mojmap**\
    Mojang-mapped, мапингът на ваниловия Minecraft.
- **Управител на версии**\
  Управителят на версии е лаунчър, който се използва за зареждането на библиотеки и пачването на файлове на сървъра, необходим за стартирането на сървъра.
  - **Paperclip**\
    Представлява управител, разработен от екипа на PaperMC за Paper и други платформи, който изтегля библиотеки и прилага пачове към сървъра.
  - **Bundler**\
    Управителят на версии на оригиналния Minecraft.

</details>

***

## 3. Създаване на стартиращ скрипт

За да стартирате Plazma лесно и автоматично да рестартирате сървъра, трябва да създадете [стартиращ скрипт](#user-content-fn-6)[^6].

[Flags.sh](https://flags.sh)може да генерира стартови скриптове чрез въвеждане само на [използваната памет](#user-content-fn-8)[^8] в Plazma, като командите се оптимизират автоматично.

Можете да изтеглите стартиращия скрипт чрез бутона за изтегляне в долната лява част.\
**Уверете се, че изтегленият стартиращ скрипт съответства на операционната ви система.**

***

## 4. Подреждане на файлове

Сега преместете изтегления стартиращ скрипт и Plazma в нова папка.

{% hint style="warning" %}

**Името на папката трябва задължително да бъде без интервали и на английски език.**

В противен случай Plazma или JRE може да не функционират правилно.

{% endhint %}

Сега стартирайте стартиращия скрипт. За Windows, <mark style="background-color:orange;">в прозореца за избор на разрешения на защитната стена, трябва задължително да изберете **Разрешаване**</mark>.

***

## 5. Съгласие с EULA

След като стартирате стартиращия скрипт, ще бъде създаден файл `eula.txt` в папката.

EULA[^9] е договор за лицензиране, с който трябва да се съгласите, за да използвате услугите на [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

В случай, че не се съгласите, няма да можете да стартирате сървъра, а при нарушаване на EULA може да получите [наказание](#user-content-fn-11)[^11], като се спре акаунта ви.

{% endhint %}

За да се съгласите с EULA, променете `eula=false` в `eula=true` във файла `eula.txt` и го запазете.

***

## 6. Разрешаване на външен достъп (Windows)

Съвременните операционни системи по подразбиране блокират външни достъпи с помощта на **защитна стена** и **рутер**.

В случай на Windows, тъй като сте разрешили защитната стена в [Стъпка 3](#id-3), трябва само да направите препращане на портовете.

{% hint style="info" %}

**Това ръководство се предполага, че операционната система е Windows и че рутерът поддържа [UPnP](#user-content-fn-12)[^12].**

Ако вашият рутер не поддържа UPnP, тъй като панелите на рутерите се различават, трябва да търсите информация самостоятелно.

Можете също да използвате [Ngrok](https://ngrok.com/), за да създадете временен адрес.
{% endhint %}

{% hint style="warning" %}

**За операционни системи като Linux или macOS и други (почти) UNIX системи, методите за настройка на защитната стена са различни за всяка услуга и трябва да проведете собствено изследване.**

{% endhint %}

### 6.1 Проверка за необходимост от пренасочване на портове

Въведете и изпълнете следната команда в командния ред.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Ако изходът е `True`, можете да спрете тук, но ако е `False`, трябва да настроите пренасочването на портовете.

### 6.2 Свързване към сървъра

{% tabs %}

{% tab title="Достъп отвън" %}

Ако не е необходимо пренасочване на портовете или вече сте го конфигурирали успешно, вече можете да достъпите сървъра.

Адресът за свързване към сървъра може да бъде проверен [тук](https://ip.pe.kr/).

{% крайнаКартка %}

{% tab title="Опит за пренасочване на портовете чрез UPnP" %}

В `purpur.yml` в папката на сървъра активирайте `network.upnp-port-forwarding` като `true`.

След това рестартирайте сървъра и Plazma автоматично ще опита да пренасочи портовете.

Успеха на UPnP се определя от съобщенията, изведени в конзолата, като се използва `[UPnP] (съобщение)`.

| Съобщение                           | Значение                                         |
| ----------------------------------- | ------------------------------------------------ |
| `Успешно отворен порт (порт)`       | Успешно пренасочване на порта.   |
| `Порт (порт) вече е отворен`        | Друга услуга използва този порт. |
| `Неуспешно отваряне на порт (порт)` | Неуспешно пренасочване на порта. |
| `Услугата не е достъпна`            | Рутера не поддържа UPnP.         |

Когато сървъра се изключи, Plazma автоматично затваря портовете.

{% крайнаКартка %}

{% tab title="Създаване на временен адрес с Ngrok" %}

Методът с Ngrok е полезен за краткосрочни тестове, участие или игра с приятели.

1. Изтеглете ZIP файла `Windows (64-bit)` от [Ngrok уебсайт](https://ngrok.com/download).
2. Поставете изтегления Ngrok в папката на сървъра.
3. Генерирайте [уникален токен за удостоверяване](#user-content-fn-13)[^13] от [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).
4. Изпълнете командата, която се показва в `Command Line` в папката на сървъра.
5. Добавете `start /b ngrok tcp --region jp 25565` в началото на скрипта и `taskkill /f /t /im ngrok.exe` в края му.
6. Адресът на сървъра ще бъде `0.tcp.jp.ngrok.io:12345` от първия ред на конзолата.
7. Сега можете да се свържете

{% крайнаКартка %}

{% tab title="Връзка от локален хост" %}

При опит за връзка със сървъра от локално място, можете да използвате `cmd /k ipconfig` в командния прозорец и да се свържете с `IPv4 адреса`, който се появява.

Например, след изпълнение на командата, ако виждате следното,

```log
Windows IP конфигурация

Ethernet адаптер Ethernet:

    Суфикс за DNS на връзката. . . . :
    IPv4 адрес. . . . . . . . . : 192.168.3.7
    Мрежова маска . . . . . . . : 255.255.255.0
    Основен шлюз . . . . . . : 192.168.3.1

```

Можете да се свържете със сървъра от локалната мрежа, като опитате да се свържете с адреса `192.168.3.7`, който се появява в IPv4.

Ако сървърът и играта се изпълняват на същия компютър, можете да използвате `localhost` за достъп.

{% крайнаКартка %}
{% крайниКартки %}

## 7. Развитие

След успешно стартиране на сървъра и докато той работи правилно, сега е време да персонализирате сървъра.

Научете как да персонализирате сървъра си, следвайки това ръководство.

{% content-ref url="next-step.md" %}
[next-step.md](next-step.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, Java изпълнителна среда.

[^2]: Paper, базиран на Spigot, който от своя страна е базиран на официалната платформа на сървъра Spigot.

[^3]: Клавиш Windows + R

[^4]: За Linux използвайте `java --version` в терминала

[^5]: JRE е един от проектите с отворен код и има множество варианти като платформа за сървър на Minecraft.

[^6]: Обикновено се нарича **изпълнител**.

[^7]: Когато активирате функцията "Автоматично рестартиране", сървърът ще се рестартира автоматично. Можете да го спрете, като натиснете `Control + C`.

[^8]: Не се препоръчва да използвате повече от половината от ресурсите на системата.

    Например, ако общият капацитет на паметта на системата е 8GB, не е препоръчително да настроите повече от 4GB.

[^9]: Споразумение за лицензионно споразумение с крайния потребител. За повече информация, моля, посетете [уебсайта на Minecraft](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Корпорация Майкрософт.

[^11]: В случая с Република Корея, съгласно член 32, параграф 1, точка 9 от Закона за насърчаване на игралната индустрия, **Korean Microsoft Corporation** има право да предприеме правни действия.

[^12]: Универсална включваема и играбелна технология. Чрез тази технология Purpur, включен в Plazma, автоматично комуникира с рутера и отваря портове само когато сървърът е активен, което означава, че няма нужда от ръчно пренасочване на портове.

[^13]: При липса на акаунт, се регистрирайте в Ngrok чрез акаунт в Google или GitHub.