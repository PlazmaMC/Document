---
description: Dowiedz się, jak dostosować serwer do użytku.
---

# 🎨 Dostosowanie użytkownika

Dlaczego korzystamy z dostosowanej platformy serwerowej, takiej jak Plazma, zamiast oficjalnej platformy serwerowej dostarczanej przez Mojang Studios? Największym powodem jest możliwość **personalizacji**.

Poniżej przedstawiono kilka sposobów dostosowania i wykorzystania Plazmy.

## Modyfikacja konfiguracji <a href="#id-1" id="id-1"></a>

Najbardziej podstawowym sposobem dostosowania Plazmy jest modyfikacja konfiguracji.

Plazma oferuje silne ustawienia konfiguracyjne, począwszy od mechaniki gry po właściwości potworów.

Zapoznaj się z opisem konfiguracji Plazmy na poniższej stronie.

{% content-ref url="../reference/configurations/" %}
[konfiguracje](../reference/configurations/)
{% endcontent-ref %}

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

**Niektóre [pakiety danych](#user-content-fn-2) mogą nie być poprawnie zastosowane za pierwszym razem.**

W takim przypadku zaleca się **2-krotne** ponowne uruchomienie serwera.

{% endhint %}

Pakiety danych mogą łatwo ulec uszkodzeniu wraz z aktualizacjami Minecrafta.

W przypadku całkowitego uszkodzenia pakietów danych, serwer może ulec awarii, dlatego
przed aktualizacją serwera ważne jest przeprowadzenie odpowiednich testów.

{% hint style="info" %}

**Po wpisaniu `safeMode` po poleceniu uruchamiającym serwer, można dezaktywować wszystkie pakiety danych i uruchomić serwer.**

[Zobacz `Referencje > Argumenty` dla szczegółów.](../reference/arguments.md)

{% endhint %}

Zastosowane pakiety danych można sprawdzić za pomocą polecenia `/datapack list`.

***

[^1]: Lub dodatków do Minecraft: Edycja Bedrock.

[^2]: Dodawanie nowych gatunków stworzeń itp.
