---
description: Zjistěte, jak přizpůsobit server uživatelským potřebám.
---

# 🎨 Uživatelské nastavení

Důvodem, proč se používá upravená serverová platforma jako Plazma místo oficiální serverové platformy poskytované společností Mojang Studios, je možnost silné **uživatelské úpravy**.

Níže jsou uvedeny různé způsoby, jak upravit a využívat Plazmu.

## Úprava konfigurace <a href="#id-1" id="id-1"></a>

Nejjednodušším způsobem, jak upravit Plazmu, je úprava konfigurace.

Plazma poskytuje silné nastavení konfigurace od herních mechanismů po vlastnosti potvor.

Pro popis konfigurace Plazmy se podívejte na následující stránku.

{% content-ref url="../reference/configurations/" %}
[konfigurace](../reference/configurations/)
{% endcontent-ref %}

## Použití pluginů <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma는 Paper 기반의 모든 플러그인을 정상 지원합니다.**

Spigot 플러그인의 경우 1.20.5부터 Paper의 매핑 변화로 일부 동작하지 않을 수 있지만,
Paper, Pufferfish 및 Purpur 등 Paper를 기반으로 하는 대부분의 플러그인은 Plazma에서도
모두 작동하며, 만약 정상적으로 작동하지 않을 경우 Plazma의 오류이므로 즉시 [신고해주시기 바랍니다.](../diagnosis/plugins.md)

{% endhint %}

Plazma를 사용하는 주요 이유이자 Plazma를 사용자화하는 가장 강력한 방법입니다.
Plazma의 강력한 플러그인 생태계는 서버를 손 쉽게 사용자화 할 수 있게 합니다.

플러그인을 찾고 다운로드 하는데에는 여러 가지 방법이 있습니다. 어떤 플러그인은
공개 저장소 서비스에 플러그인을 업로드 하고, 어떤 플러그인은 GitHub 또는 자체
사이트에 업로드하기도 합니다.

{% hint style="caution" %}

**플러그인은 시스템에 직접적으로 접근할 수 있습니다!**

VirusTotal 등의 서비스를 이용하여 플러그인을 적용하기 전 항상 안전한지 확인하거나,
신뢰 가능한 서비스에서 플러그인을 다운로드 하세요.

{% endhint %}

플러그인을 다운로드하기 위해 사용되는 서비스에는 여러 가지가 있습니다. 그 중, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) 등의 서비스는 플러그인이 업로드 되기 전 심사를 거치며, 안전하지 않은 플러그인은 바로 처리하여 안전한 플러그인만 유통되도록 하고 있습니다.

### 플러그인 적용하기 <a href="#id-2.1" id="id-2.1"></a>

플러그인을 다운로드 했다면, 이제 플러그인을 적용해볼 차례입니다.

1. 플러그인은 `.jar` 또는 `Java Executable File` 로 되어 있습니다.\
   일부 플러그인은 압축 파일로 압축되어 있는 경우도 있는데, 그런 경우
   압축을 풀어 이름에 `bukkit`, `spigot` 또는 `paper` 가 포함되어 있고,
   `fat`이 포함된 파일이 함께 있는 경우 `fat` 파일을 사용하면 됩니다.
2. 다운로드한 파일을 서버 폴더의 `plugins` 폴더에 넣고 서버를 (재)시작합니다.
3. Plazma가 시작되면, 콘솔에 새로운 내용이 출력이 될 것입니다.
   이는 Plazma가 플러그인을 정상적으로 로드했다는 의미입니다.
4. Plazma가 플러그인을 정상적으로 로드했더라도, 플러그인을 시작하지 못했을 수 있습니다.
   `/plugins` 명령어를 사용하면 현재 서버에 로드된 플러그인을 불러올 수 있습니다.
   설치한 플러그인의 이름이 <mark style="background-color:red;">적색</mark>이 아닌 <mark style="background-color:green;">녹색</mark>이라면 플러그인이 정상적으로 로드된 것입니다.

만약 플러그인이 정상적으로 로드되지 않았다면, 아래 페이지에서 문제에 대한 해결 방법을 찾을 수 있습니다.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## 데이터팩 사용 <a href="#id-3" id="id-3"></a>

데이터팩은 Minecraft가 기본적으로 제공하는 사용자화 방법으로써,
[리소스팩](#user-content-fn-1)[^1]과 유사합니다.

데이터팩을 사용하면 새로운 생물 군계와 도전 과제를 추가하는 등 게임 내부의 일부를 수정할 수 있습니다.

{% hint style="caution" %}

**데이터팩은 월드를 손상시킬 수 있습니다!**

일부 고장난 데이터팩은 월드를 손상시킬 수 있으며, 이는 돌이킬 수 없습니다.

따라서, 데이터팩을 적용하기 전 월드를 백업하는것이 권장됩니다.

{% endhint %}

데이터팩 또한 여러 서비스에서 다운로드 할 수 있으며, [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) 등 여러 서비스에서 찾을 수 있습니다.

데이터팩을 다운로드 했다면, 서버의 월드 폴더에 `datapacks` 폴더에 넣어 적용할 수 있습니다.
폴더가 없는 경우 폴더를 생성하여 추가하면 됩니다.

{% hint style="warning" %}

**일부 [데이터팩](#user-content-fn-2)[^2]의 경우 처음 적용시 정상적으로 적용되지 않을 수 있습니다.**

이런 경우에 대비하여 서버를 **2번** 재시작하는 것을 권장합니다.

{% endhint %}

데이터팩은 Minecraft의 버전이 업데이트 될 때 마다 쉽게 손상될 수 있습니다.

특히, 데이터팩이 완전히 손상된 경우, 서버가 충돌하기 때문에,
서버를 업데이트하기 전 충분한 테스트를 거치는 것이 중요합니다.

{% hint style="info" %}

**서버 시작 명령어 뒤에 `safeMode`를 입력하여 데이터팩을 모두 비활성화 한 뒤 서버를 시작할 수 있습니다.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md)

{% endhint %}

적용된 데이터팩은 `/datapack list` 명령어를 통해 확인할 수 있습니다.

***

[^1]: 또는 Minecraft: Bedrock Edition의 애드온.

[^2]: 생물 군계 추가 등.
