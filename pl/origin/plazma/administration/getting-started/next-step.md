---
description: Dowiedz się, jak dostosować serwer do użytku.
---

# 📶 Poziom rozwoju

Dlaczego korzystamy z dostosowanej platformy serwerowej, takiej jak Plazma, zamiast oficjalnej platformy serwerowej dostarczanej przez Mojang Studios? Największym powodem jest możliwość **personalizacji**.

Poniżej przedstawiono kilka sposobów dostosowania i wykorzystania Plazmy.

## Modyfikacja konfiguracji <a href="#id-1" id="id-1"></a>

Najbardziej podstawowym sposobem dostosowania Plazmy jest modyfikacja konfiguracji.

Plazma oferuje silne ustawienia konfiguracyjne, począwszy od mechaniki gry po właściwości potworów.

Zapoznaj się z opisem konfiguracji Plazmy na poniższej stronie.

{% content-ref url="../reference/configurations/" %}
[konfiguracje](../reference/configurations/)
{% endcontent-ref %}

***

## Użycie wtyczek <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma obsługuje wszystkie wtyczki oparte na papierze.**

W przypadku wtyczek Spigot od wersji 1.20.5, z powodu zmian w mapowaniu w Paperze, niektóre mogą nie działać, ale większość wtyczek opartych na Paperze, takich jak Paper, Pufferfish i Purpur, działa również w Plazmie. Jeśli wtyczka nie działa poprawnie, należy natychmiast [zgłosić błąd w Plazmie.](../diagnosis/plugins.md)

{% endhint %}

Jest to główny powód korzystania z Plazmy oraz najskuteczniejszy sposób personalizacji Plazmy.
Potężny ekosystem wtyczek Plazmy umożliwia łatwe dostosowanie serwera.

Istnieje wiele sposobów na znalezienie i pobranie wtyczek. Niektóre wtyczki są udostępniane w serwisach magazynowania publicznego, podczas gdy inne są udostępniane na GitHubie lub własnej stronie internetowej.

{% hint style="caution" %}

**Wtyczki mogą mieć bezpośredni dostęp do systemu!**

Zawsze upewnij się, czy wtyczka jest bezpieczna, korzystając z usług takich jak VirusTotal, zanim ją zastosujesz, lub pobierz wtyczkę z zaufanego źródła.

{% endhint %}

Istnieje wiele usług do pobierania wtyczek. Spośród nich, usługi takie jak [Forum SpigotMC](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) przeprowadzają ocenę wtyczek przed ich udostępnieniem, aby zapewnić, że tylko bezpieczne wtyczki są dystrybuowane.

### Zastosowanie wtyczki <a href="#id-2.1" id="id-2.1"></a>

Po pobraniu wtyczki, nadszedł czas na jej zastosowanie.

1. Wtyczki są plikami `.jar` lub `Java Executable File`.\
   Niektóre wtyczki mogą być skompresowane, w takim przypadku
   po rozpakowaniu, jeśli nazwa zawiera `bukkit`, `spigot` lub `paper`,
   należy użyć pliku z rozszerzeniem `fat`, jeśli taki istnieje.
2. Umieść pobrany plik w folderze `plugins` serwera i (ponownie) uruchom serwer.
3. Po uruchomieniu Plazmy, na konsoli pojawią się nowe komunikaty.
   Oznacza to, że Plazma poprawnie załadowała wtyczki.
4. Mimo poprawnego załadowania wtyczek przez Plazmę, niektóre wtyczki mogą nie zostać uruchomione.
   Za pomocą polecenia `/plugins` można sprawdzić, które wtyczki są obecnie załadowane na serwerze.
   Jeśli nazwa zainstalowanej wtyczki jest <mark style="background-color:red;">czerwona</mark>,
   jest to oznaczenie, że wtyczka nie została poprawnie załadowana,
   jeśli jest <mark style="background-color:green;">zielona</mark>, to znaczy, że wtyczka została poprawnie załadowana.

Jeśli wtyczka nie została poprawnie załadowana, można znaleźć rozwiązania na poniższej stronie.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## Użycie pakietów danych <a href="#id-3" id="id-3"></a>

Pakiety danych to sposób dostosowania gry oferowany domyślnie przez Minecraft,
podobny do paczek zasobów.

Dzięki pakietom danych można zmieniać niektóre aspekty gry, dodając nowe gatunki stworzeń i wyzwania.

{% hint style="caution" %}

**Pakiety danych mogą uszkodzić świat gry!**

Niektóre uszkodzone pakiety danych mogą uszkodzić świat gry w sposób nieodwracalny.

Dlatego zaleca się wykonywanie kopii zapasowych świata gry przed zastosowaniem pakietów danych.

{% endhint %}

Pakiety danych można pobrać z wielu usług, takich jak [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/).

Po pobraniu pakietu danych, można go zastosować, umieszczając go w folderze `datapacks` w folderze światowym serwera.
W przypadku braku folderu, należy go utworzyć i dodać pakiet danych.

{% hint style="warning" %}

**[W niektórych pakietach danych](#user-content-fn-2)[^2] po pierwszym zastosowaniu mogą wystąpić problemy z prawidłowym działaniem.**

W takim przypadku zaleca się **2-krotne** ponowne uruchomienie serwera.

{% endhint %}

Pakiety danych mogą łatwo ulec uszkodzeniu wraz z aktualizacjami Minecrafta.

W przypadku całkowitego uszkodzenia pakietów danych, serwer może ulec awarii, dlatego
przed aktualizacją serwera ważne jest przeprowadzenie odpowiednich testów.

{% hint style="info" %}

**Po wpisaniu `safeMode` po poleceniu uruchamiającym serwer, można dezaktywować wszystkie pakiety danych i uruchomić serwer.**

[Aby uzyskać więcej informacji, zapoznaj się z sekcją `Referencje > Argumenty i atrybuty`](../reference/arguments.md#safeMode)

{% endhint %}

Zastosowane pakiety danych można sprawdzić za pomocą polecenia `/datapack list`.

***

## Optymalizacja <a href="#id-4" id="id-4"></a>

W Plazmie zastosowano wiele łatek optymalizacyjnych. Ponadto, gdy Plazma zostanie uruchomiona po raz pierwszy, automatycznie optymalizuje konfigurację, dlatego nie ma potrzeby dodatkowych działań optymalizacyjnych, jeśli postępujesz zgodnie z instrukcjami w przewodniku [Rozpocznij](./README.md).

Jednakże w przypadku dużej liczby graczy lub gdy rozmiar świata jest znaczny, można przeprowadzić dodatkowe działania optymalizacyjne, korzystając z przewodnika poniżej.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## Proxy <a href="#id-5" id="id-5"></a>

Proksy łączą serwery ze sobą i umożliwiają graczom przemieszczanie się między nimi bez dodatkowych działań, a także komunikowanie się z innymi serwerami.

Aby uzyskać informacje na temat bezpiecznej i poprawnej konfiguracji proksów, zapoznaj się z poniższą stroną.

{% content-ref url="../expert/proxy.md" %}
[proxy.md](../expert/proxy.md)
{% endcontent-ref %}

***

## Bezpieczeństwo <a href="#id-5" id="id-5"></a>

W przypadku rozwoju modów w Minecraft, łatwo dostępny jest [silnik ataków na luki](#user-content-fn-3)[^3].

W większości gier, większość podstawowych luk jest [domyślnie zablokowana](#user-content-fn-4)[^4], ale atakowanie luk za pomocą ładowaczy stron trzecich nie jest blokowane.

Dlatego w przypadku publicznego dostępu do serwera zaleca się instalację wtyczek anty-cheat, konfigurację proksów, automatyczne restartowanie i tworzenie kopii zapasowych, aby w razie awarii serwera można było szybko przywrócić jego działanie.

### Konfiguracja uprawnień <a href="#id-5.1" id="id-5.1"></a>

W niektórych wtyczkach administratora mogą istnieć luki bez właściwie ustawionych uprawnień.

Zaleca się używanie wtyczek do zarządzania uprawnieniami, takich jak [LuckPerms](https://luckperms.net/), aby ograniczyć uprawnienia zwykłych użytkowników.

### Blokada X-Ray <a href="#id-5.2" id="id-5.2"></a>

X-Ray to jedna z podstawowych luk, która jest łatwo dostępna nawet w podstawowym optymalizowanym kliencie.

Plazma oferuje konfigurację blokady X-Ray domyślnie.

Aby uzyskać informacje o metodach blokowania X-Ray, zapoznaj się z poniższą stroną.

{% content-ref url="../expert/xray.md" %}
[xray.md](../expert/xray.md)
{% endcontent-ref %}

### Whitelist <a href="#id-5.3" id="id-5.3"></a>

W przypadku gdy tylko wybrani użytkownicy mają dostęp do serwera, zaleca się korzystanie z [Ngrok](./README.md#id-6.2) do korzystania z [zakodowanego adresu serwera](#user-content-fn-5)[^5] lub ustawienie whitelisty, aby uniemożliwić innym graczom dostęp do serwera.

W konsoli serwera można zezwolić graczowi na dostęp za pomocą `/whitelist add <gracz>` lub ponownie zablokować dostęp za pomocą `/whitelist remove <gracz>`.

Aby sprawdzić, którzy gracze mają dostęp, użyj `/whitelist query`.

***

[^1]: Lub dodatków do Minecraft: Edycja Bedrock.

[^2]: Dodawanie nowych gatunków stworzeń itp.

[^3]: Zazwyczaj nazywany "hackami".

[^4]: W przypadku nieoptymalnej konfiguracji, długiego użytkowania Plazmy lub nowo odkrytych luk, może nie być zablokowane.

[^5]: Gracz łączy się z serwerem za pośrednictwem serwera proxy Ngrok, a każde ponowne uruchomienie generuje nowy adres Ngrok.
