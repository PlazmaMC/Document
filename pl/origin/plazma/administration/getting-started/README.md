---
description: Dowiedz się, jak zrobić serwer za pomocą Plazma.
---

# 👟 Rozpocznij

Aby stabilnie korzystać z Plazma, system musi spełniać następujące wymagania.

|                    | Minimalne | Zalecane |
| :----------------: | :-------- | :------- |
|    Architektura    | x64       | -        |
|         RAM        | 8GB       | 16GB     |
| Przestrzeń dyskowa | 1GB       | 8GB      |
|         JRE        | 17        | 21       |

Aby swobodnie edytować pliki konfiguracyjne, zaleca się zainstalowanie edytora takiego jak [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. Instalacja JRE

Jak wskazuje nazwa, Minecraft: **"Java"** Edition został stworzony w Javie, dlatego do uruchomienia wymagane jest JRE[^1].

Ponieważ Plazma opiera się na oficjalnej platformie serwerowej Mojang Studios [^2], do korzystania z Plazma konieczna jest również instalacja JRE.

### 1.1 Sprawdzenie obecności JRE

Aby sprawdzić, czy JRE jest zainstalowane na systemie, wpisz w oknie uruchamiania [`cmd /k java --version`](#user-content-fn-4)[^4] i uruchom.

다음과 같이 출력되면 [2 단계](#id-2)로 건너뜁니다.

{% code title="Poprawne wyjście" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JRE가 없거나 너무 오래되었으므로, [1.2 단계](#id-1.2)를 수행해야 합니다.

{% code title="Brak zainstalowanego JRE" lineNumbers="true" %}

```log
'java' nie jest wewnętrzną ani zewnętrzną komendą, programem wykonywalnym lub
plikiem wsadowym.
```

{% endcode %}

{% code title="Zbyt stara wersja JRE" lineNumbers="true" %}

```log
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

{% endcode %}

### 1.2 Instalacja JRE

본 설명서에서는 JRE의 [종류 중 하나](#user-content-fn-5)[^5]로 Azul Zulu를 사용합니다.

설치를 완료한 후, [1.1 단계](#id-1.1)을 다시 수행하여 설치가 올바르게 완료되었는지 확인해 보세요.

{% tabs %}

{% tab title="Windows" %}

1. Najpierw pobierz **JDK 21** w formacie `.msi` z [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Uruchom pobrany instalator i kliknij `Dalej`.
3. Po lewej stronie środkowej części okna wybierz `Set JAVA_HOME variable`, a następnie kliknij `Dalej`.
4. Kliknij `Instaluj`, aby zainstalować JRE.

{% endtab %}

{% tab title="macOS" %}

[Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=macos\\&architecture=x86-64-bit\\&package=jdk#zulu) pobierz **JDK 21** w formie pliku `.dmg`, uruchom instalator i zainstaluj JRE.

{% endtab %}

{% tab title="Debian/Ubuntu" %}

Najpierw wykonaj poniższą komendę w terminalu, aby dodać repozytorium Azul Zulu do APT.

```bash
sudo apt install gnupg ca-certificates curl --no-install-recommends --no-install-suggests -y

curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg

echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
```

Następnie wykonaj kolejną komendę w terminalu, aby zainstalować JRE.

```bash
sudo apt install --no-install-recommends --no-install-suggests -y zulu21-ca-jre-headless
```

{% endtab %}

{% tab title="Fedora/RHEL" %}

Możesz zainstalować JRE, wykonując poniższą komendę.

```bash
sudo dnf install -y https://cdn.azul.com/zulu/bin/zulu-repo-1.0.0-1.noarch.rpm

sudo dnf install -y zulu21-ca-jre-headless
```

{% endtab %}
{% endtabs %}

***

## 2. Pobieranie Plazma

Plazma oferuje różne rodzaje plików wykonywalnych.

{% hint style="warning" %}

**W większości przypadków używany jest `Reobf Paperclip`.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](#id-3)로 뛰어 넘겨도 문제되지 않습니다.

{% endhint %}

<details>

<summary>Dowiedz się więcej</summary>

Nazwa pliku wykonywalnego to `plazma-(menedżer wersji)-1.20.4-R0.1-SNAPSHOT-(typ mapowania).jar`.

- **Typ mapowania**\
  Mapowanie to rodzaj mapy łączącej rzeczywisty kod Minecrafta z zaszyfrowanym kodem.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.5부터 사용이 종료될 예정입니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다.
- **Menedżer wersji**\
  Menedżer wersji to narzędzie uruchamiające serwer, które jest odpowiedzialne za pobieranie bibliotek niezbędnych do uruchomienia serwera oraz za łatanie plików serwera.
  - **Paperclip**\
    Menedżer opracowany przez zespół PaperMC do Paper i innych platform pochodnych, służy do pobierania bibliotek i łatania serwera.
  - **Bundler**\
    Menedżer wersji Vanilla Minecrafta.

</details>

***

## 3. Tworzenie skryptu startowego

Aby łatwo uruchamiać Plazma i automatycznie restartować serwer, musisz stworzyć [skrypt startowy](#user-content-fn-6)[^6].

Za pomocą [Flags.sh](https://flags.sh) można generować skrypty startowe. Wystarczy podać ilość pamięci do użycia w Plazmie, a polecenie zostanie zoptymalizowane automatycznie.

Możesz pobrać skrypt startowy klikając na przycisk pobierania w lewym dolnym rogu.\
**Upewnij się, że pobrany skrypt startowy jest zgodny z twoim systemem operacyjnym.**

***

## 4. Porządkowanie plików

Przenieś pobrany skrypt startowy i Plazma do nowego folderu.

{% hint style="warning" %}

**Nazwa folderu musi być bez spacji i w języku angielskim.**

W przeciwnym razie Plazma lub JRE mogą nie działać poprawnie.

{% endhint %}

Uruchom skrypt startowy. W przypadku systemu Windows, <mark style="background-color:orange;">w oknie wyboru zezwoleń dla zapory sieciowej, koniecznie wybierz **Zezwól**</mark>.

***

## 5. Zgoda na EULA

Po pierwszym uruchomieniu skryptu startowego zostanie utworzony plik `eula.txt` w folderze.

EULA[^9] to umowa licencyjna, którą trzeba zaakceptować korzystając z usług [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}

Jeśli nie wyrazisz zgody, nie będzie możliwe uruchomienie serwera, a w przypadku naruszenia EULA mogą zostać nałożone sankcje, takie jak zawieszenie konta.

{% endhint %}

Aby zaakceptować EULA, zmień `eula=false` na `eula=true` w pliku `eula.txt` i zapisz zmiany.

***

## 6. Zezwolenie na zewnętrzny dostęp (Windows)

Nowoczesne systemy operacyjne domyślnie blokują niebezpieczne połączenia z zewnątrz za pomocą **zapory** i **routera**.

Windows의 경우, 방화벽은 [3 단계](#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}

**해당 설명서는 Windows 운영 체제 및 [UPnP](#user-content-fn-12)[^12]를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Jeśli router nie obsługuje UPnP, należy sprawdzić instrukcje dla konkretnego modelu routera.

Możesz również użyć [Ngrok](https://ngrok.com/), aby tymczasowo udostępnić adres.
{% endhint %}

{% hint style="warning" %}

**Dla systemów operacyjnych opartych na (lub zbliżonych do) UNIX, takich jak Linux czy macOS, konieczne jest dostosowanie ustawień zapory sieciowej w zależności od usługi. Należy skonsultować się z odpowiednimi materiałami.**

{% endhint %}

### 6.1 Sprawdzenie konieczności przekierowania portów

Wpisz i uruchom poniższą komendę w oknie uruchamiania.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jeśli otrzymasz `True`, nie musisz nic więcej robić. Jeśli otrzymasz `False`, należy skonfigurować przekierowanie portów.

### 6.2 Połączenie z serwerem

{% tabs %}

{% tab title="Dostęp z zewnątrz" %}

Jeśli nie jest wymagane przekierowanie portów lub już je skonfigurowałeś, możesz teraz połączyć się z serwerem.

Adres używany do połączenia z serwerem można sprawdzić [tutaj](https://ip.pe.kr/).

{% endtab %}

{% tab title="Próba przekierowania portu za pomocą UPnP" %}

W pliku `purpur.yml` w folderze serwera, aktywuj `network.upnp-port-forwarding` na `true`.

Następnie po restarcie serwera, Plazma automatycznie próbuje przekierować porty.

Poniżej znajduje się informacja o sukcesie przekierowania UPnP, która zostanie wyświetlona w konsoli, np. `[UPnP] (wiadomość)`.

| wiadomość                             | znaczenie                                                  |
| ------------------------------------- | ---------------------------------------------------------- |
| `Pomyślnie otwarto port (port)`       | Sukces przekierowania portów.              |
| `Port (port) jest już otwarty`        | Inna usługa korzysta obecnie z tego portu. |
| `Nie udało się otworzyć portu (port)` | Przekierowanie portów nie powiodło się.    |
| `Usługa jest niedostępna`             | Router nie obsługuje UPnP.                 |

Po zakończeniu pracy serwera, Plazma automatycznie zamyka porty.

{% endtab %}

{% tab title="Generowanie tymczasowego adresu za pomocą Ngrok" %}

Metoda z użyciem Ngrok jest przydatna do krótkoterminowych testów, gier wieloosobowych lub zabawy z przyjaciółmi.

1. Pobierz plik ZIP `Windows (64-bit)` z [strony Ngrok](https://ngrok.com/download).
2. Umieść pobrany Ngrok w folderze serwera.
3. Na [panelu Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) wygeneruj [token uwierzytelniający](#user-content-fn-13)[^13].
4. W folderze serwera wykonaj polecenie wyświetlane w `Command Line`.
5. Dodaj polecenie `start /b ngrok tcp --region jp 25565` na początku skryptu uruchamiania i `taskkill /f /t /im ngrok.exe` na końcu.
6. Z informacji `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` w górnej części konsoli, `0.tcp.jp.ngrok.io:12345` będzie adresem serwera.
7. Teraz można połączyć się z serwerem zewnętrznym za pomocą tego adresu.

{% endtab %}

{% tab title="Połączenie z lokalnego komputera" %}

Jeśli chcesz połączyć się z serwerem lokalnie, możesz użyć polecenia `cmd /k ipconfig` w oknie uruchamiania i połączyć się za pomocą wyświetlonego adresu `IPv4`.

Na przykład, po wykonaniu polecenia,

```log
Konfiguracja IP systemu Windows

Karta Ethernet Ethernet:

    Sufiks DNS konkretnego połączenia. . . . :
    Adres IPv4. . . . . . . . . : 192.168.3.7
    Maska podsieci. . . . . . . . : 255.255.255.0
    Brama domyślna. . . . . . . : 192.168.3.1

```

Możesz połączyć się z serwerem lokalnie, korzystając z adresu IPv4 `192.168.3.7`.

Jeśli serwer i gra działają na tym samym komputerze, można użyć `localhost` do połączenia.

{% endtab %}
{% endtabs %}

## 7. Rozwijaj się

Jeśli serwer został pomyślnie uruchomiony i działa poprawnie, teraz nadszedł czas na dostosowanie serwera.

아래 설명서를 통해 서버를 사용자화 하는 방법에 대해 알아보세요.

{% content-ref url="następny-krok.md" %}
[następny-krok.md](następny-krok.md)
{% endcontent-ref %}

***

[^1]: Java Runtime Environment, środowisko uruchomieniowe Javy.

[^2]: Paper, na którym opiera się Plazma, bazuje na Spigot, który z kolei opiera się na oficjalnej platformie serwerowej Spigot.

[^3]: Klawisz Windows + R

[^4]: Dla systemu Linux, w terminalu wpisz `java --version`

[^5]: JRE to jeden z projektów open source, podobnie jak platformy serwerowe Minecrafta.

[^6]: Zazwyczaj jest nazywany **uruchamiaczem**.

[^7]: Aktywując opcję "Auto-restart", serwer będzie automatycznie restartowany. Możesz zakończyć go, wpisując `Control + C`.

[^8]: Nie zaleca się przekraczania połowy dostępnej pamięci systemowej.

    Na przykład, jeśli całkowita pojemność pamięci systemowej wynosi 8GB, nie zaleca się ustawiania wartości powyżej 4GB.

[^9]: End-User License Agreement, Umowa Licencyjna Końcowego Użytkownika. Aby uzyskać więcej informacji, odwiedź [stronę Minecrafta](https://www.minecraft.net/ko-kr/usage-guidelines).

[^10]: Microsoft Corporation.

[^11]: Zgodnie z artykułem 32 ustęp 1 punkt 9 ustawy o wspieraniu przemysłu gier w Korei, **Koreańska Spółka Microsoft** może być poddana postępowaniu sądowemu.

[^12]: Universal Plug & Play. Purpur zawarty w Plazmie automatycznie komunikuje się z routerem za pomocą tej technologii, otwierając porty tylko wtedy, gdy serwer jest uruchomiony, eliminując konieczność ręcznego przekierowywania portów.

[^13]: Jeśli nie masz konta, zarejestruj się w Ngrok za pomocą konta Google lub GitHub.
