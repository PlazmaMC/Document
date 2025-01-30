---
description: Dowiedz się, jak zrobić serwer za pomocą Plazma.
---

# 👟 Rozpocznij

Aby stabilnie korzystać z Plazma, system musi spełniać następujące wymagania.

|                    | Minimalne | Zalecane |
| :----------------: | --------- | -------- |
|    Architektura    | x64       | -        |
|         RAM        | 8GB       | 16GB     |
| Przestrzeń dyskowa | 1GB       | 8GB      |
|         JDK        | 17        | 21       |

Aby swobodnie edytować pliki konfiguracyjne, zaleca się zainstalowanie edytora takiego jak [Visual Studio Code](https://code.visualstudio.com/download).

***

## 1. JDK 설치

이름에서 알 수 있듯이, Minecraft: **"Java"** Edition 은 Java로 개발되어, 실행을 위해선 JDK[^1]를 필요로 합니다.

Plazma는 Mojang Studios의 공식 서버 플랫폼을 [기반으로 하므로](#user-content-fn-2)[^2], Plazma를 사용하기 위해서도 JDK를 설치해야 합니다.

### 1.1 JDK 설치 유무 확인

JDK가 시스템에 설치되어 있는지 확인하려면, [실행 창](#user-content-fn-3)[^3]에 [`cmd /k java --version`](#user-content-fn-4)[^4]을 입력하고 실행합니다.

다음과 같이 출력되면 [2 단계](./#id-2)로 건너뜁니다.

{% code title="Poprawne wyjście" lineNumbers="true" %}

```log
openjdk 21.0.2 2024-01-16 LTS
OpenJDK Runtime Environment Zulu21.32+17-CA (build 21.0.2+13-LTS)
OpenJDK 64-Bit Server VM Zulu21.32+17-CA (build 21.0.2+13-LTS, mixed mode, sharing)
```

{% endcode %}

위와 같이 출력되지 않거나, 아래와 같이 출력되면 JDK가 없거나 너무 오래되었으므로, [1.2 단계](./#id-1.2)를 수행해야 합니다.

{% code title="JDK가 설치되어 있지 않음" lineNumbers="true" %}

```log
'java' nie jest wewnętrzną ani zewnętrzną komendą, programem wykonywalnym lub
plikiem wsadowym.
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

1. Najpierw pobierz **JDK 21** w formacie `.msi` z [Azul Zulu](https://www.azul.com/downloads/?version=java-21-lts\\&os=windows\\&architecture=x86-64-bit\\&package=jdk#zulu).
2. Uruchom pobrany instalator i kliknij `Dalej`.
3. Po lewej stronie środkowej części okna wybierz `Set JAVA_HOME variable`, a następnie kliknij `Dalej`.
4. Kliknij `Instaluj`, aby zainstalować JRE.
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

Następnie wykonaj kolejną komendę w terminalu, aby zainstalować JRE.

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

## 2. Pobieranie Plazma

Plazma oferuje różne rodzaje plików wykonywalnych.

{% hint style="warning" %}
**대부분의 경우에는 `Mojang-mapped Paperclip`을 사용합니다.**

아래 내용은 개발자 또는 각 형태의 특징에 대해 궁금한 분들을 위한 것입니다.\
일반 사용자라면 [3 단계](./#id-3)로 뛰어 넘겨도 문제되지 않습니다.
{% endhint %}

<details>

<summary>Dowiedz się więcej</summary>

Nazwa pliku wykonywalnego to `plazma-(menedżer wersji)-1.20.4-R0.1-SNAPSHOT-(typ mapowania).jar`.

- **Typ mapowania**\
  Mapowanie to rodzaj mapy łączącej rzeczywisty kod Minecrafta z zaszyfrowanym kodem.
  - **Reobf**\
    Reobfuscated (재난독화), Spigot 매핑으로도 불리며 대부분의 NMS 플러그인에서 사용됩니다.\
    1.20.6부터 지원이 종료되었습니다.
  - **Mojmap**\
    Mojang-mapped, 바닐라 Minecraft 매핑입니다. 1.20.6 이후의 모던 플러그인에서 사용합니다.
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

[Flags.sh](https://flags.sh)를 통해 시작 스크립트를 생성[^7]할 수 있습니다.\
Plazma에 [사용할 메모리](#user-content-fn-8)[^8]만 입력하면 명령어가 자동으로 최적화 됩니다.

Możesz pobrać skrypt startowy klikając na przycisk pobierania w lewym dolnym rogu.\
**Upewnij się, że pobrany skrypt startowy jest zgodny z twoim systemem operacyjnym.**

***

## 4. Porządkowanie plików

Przenieś pobrany skrypt startowy i Plazma do nowego folderu.

{% hint style="warning" %}
**폴더 명칭은 반드시 띄어 쓰기와 특수 문자가 없고, 영어로 설정되어야 합니다.**

그렇지 않으면 Plazma 또는 JDK가 올바르게 작동하지 않을 수 있습니다.
{% endhint %}

Uruchom skrypt startowy. Windows의 경우, <mark style="background-color:orange;">방화벽 허용 선택 창에서, 반드시</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">**허용**</mark><mark style="background-color:orange;">을 선택</mark>해야 합니다.

***

## 5. Zgoda na EULA

Po pierwszym uruchomieniu skryptu startowego zostanie utworzony plik `eula.txt` w folderze.

EULA[^9] to umowa licencyjna, którą trzeba zaakceptować korzystając z usług [Mojang Studios](#user-content-fn-10)[^10].

{% hint style="warning" %}
만일 동의하지 않는 경우, 서버를 시작할 수 없으며, EULA를 위반하는 경우 계정을 정지되는 등의 제재[^11]를 받을 수 있습니다.
{% endhint %}

Aby zaakceptować EULA, zmień `eula=false` na `eula=true` w pliku `eula.txt` i zapisz zmiany.

***

## 6. Zezwolenie na zewnętrzny dostęp (Windows)

Nowoczesne systemy operacyjne domyślnie blokują niebezpieczne połączenia z zewnątrz za pomocą **zapory** i **routera**.

Windows의 경우, 방화벽은 [3 단계](./#id-3)에서 허용했으므로, 포트 포워딩만 하면 됩니다.

{% hint style="info" %}
**해당 설명서는 Windows 운영 체제 및** [**UPnP**](#user-content-fn-12)[^12]**를 사용할 수 있는 라우터임을 가정하고 작성되었습니다.**

Jeśli router nie obsługuje UPnP, należy sprawdzić instrukcje dla konkretnego modelu routera.

Możesz również użyć [Ngrok](https://ngrok.com/), aby tymczasowo udostępnić adres.
{% endhint %}

{% hint style="warning" %}
**Linux 또는 macOS 등 (준) UNIX 체계 운영체제의 경우, 방화벽 서비스 별로 설정 방법이 다르므로, 직접 자료를 검색해야 합니다.**
{% endhint %}

### 6.1 Sprawdzenie konieczności przekierowania portów

Wpisz i uruchom poniższą komendę w oknie uruchamiania.

```batch
powershell -noexit -c "((Get-NetIPConfiguration).IPv4Address).IPAddress -eq (Invoke-WebRequest "ifconfig.me").content"
```

Jeśli otrzymasz `True`, nie musisz nic więcej robić. Jeśli otrzymasz `False`, należy skonfigurować przekierowanie portów.

### 6.2 Połączenie z serwerem

{% tabs %}
{% tab title="외부에서 접속" %}
포트 포워딩이 필요 없거나, 이미 포트 포워딩을 성공했다면, 이제 서버에 접속할 수 있습니다.

Adres używany do połączenia z serwerem można sprawdzić [tutaj](https://ip.pe.kr/).
{% endtab %}

{% tab title="UPnP로 포트포워딩 시도" %}
서버 폴더의 `purpur.yml`에서, `network.upnp-port-forwarding`을 `true`로 활성화합니다.

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

{% tab title="Ngrok으로 임시 주소 생성" %}
Ngrok을 이용한 방법은 단기적인 테스트, 참여형 또는 친구들과 함께 플레이하기에 유용합니다.

1. Pobierz plik ZIP `Windows (64-bit)` z [strony Ngrok](https://ngrok.com/download).
2. Umieść pobrany Ngrok w folderze serwera.
3. Na [panelu Ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) wygeneruj [token uwierzytelniający](#user-content-fn-13)[^13].
4. W folderze serwera wykonaj polecenie wyświetlane w `Command Line`.
5. Dodaj polecenie `start /b ngrok tcp --region jp 25565` na początku skryptu uruchamiania i `taskkill /f /t /im ngrok.exe` na końcu.
6. Z informacji `Forwarding tcp://0.tcp.jp.ngrok.io:12345 -> localhost:25565` w górnej części konsoli, `0.tcp.jp.ngrok.io:12345` będzie adresem serwera.
7. Teraz można połączyć się z serwerem zewnętrznym za pomocą tego adresu.
   {% endtab %}

{% tab title="로컬에서 접속" %}
로컬에서 서버에 접속하려고 하는 경우, 실행 창에서 `cmd /k ipconfig`를 실행하여 출력된 `IPv4 주소` 로 접속할 수 있습니다.

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

Zapoznaj się z poniższą instrukcją, aby dowiedzieć się, jak dostosować serwer.

{% content-ref url="następny-krok.md" %}
[następny-krok.md](następny-krok.md)
{% endcontent-ref %}

***

[^1]: Java Development Kit (Java 개발 환경), Java Runtime Environment (JRE, Java 실행 환경) 을 포함하고 있으며, Plazma 에서는 JDK 에서만 제공되는 일부 기능을 이용하고 있으므로 JDK 설치를 필요로 합니다.

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
