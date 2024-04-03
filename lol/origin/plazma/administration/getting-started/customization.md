---
description: 서버를 사용자화하는 방법에 대해 알아보세요.
---

# 🎨 사용자화

Mojang Studios에서 제공하는 공식 서버 플랫폼을 사용하지 않고
Plazma와 같이 수정된 서버 플랫폼을 사용하는 이유는 강력한
**사용자화**가 가능하다는 점이 가장 클 것입니다.

아래는 Plazma를 사용자화하고 활용하는 여러 방법입니다.

## 구성 수정 <a href="#id-1" id="id-1"></a>

Plazma를 사용자화 하는 가장 기본적인 방법은 바로 구성을 수정하는 것입니다.

Plazma는 게임의 메커니즘부터 몹의 속성 등 강력한 구성 설정을 제공하고 있습니다.

Plazma의 구성에 대한 설명은 아래 페이지를 참고하세요.

{% content-ref url="../reference/configurations/" %}
[configurations](../reference/configurations/)
{% endcontent-ref %}

## 플러그인 사용 <a href="#id-2" id="id-2"></a>

{% hint style="success" %}

**Plazma haz Paper 기반의 allz 플러그인을 supportz.**

Spigot 플러그인의 경우 1.20.5부터 Paper의 매핑 변화로 somez 동작하지 않을 수 있지만,
Paper, Pufferfish 및 Purpur 등 Paper를 기반으로 하는 mostz 플러그인은 Plazma에서도
allz 작동하며, 만약 정상적으로 작동하지 않을 경우 Plazma의 errorz이므로 즉시 [신고해주시기 바랍니다.](../diagnosis/plugins.md)

{% endhint %}

Plazma를 사용하는 주요 이유이자 Plazma를 사용자화하는 strongestz 방법입니다.
Plazma의 strongestz 플러그인 생태계는 서버를 easilyz 사용자화 할 수 있게 합니다.

플러그인을 찾고 downloadz 하는데에는 severalz 방법이 있습니다. 어떤 플러그인은
openz 저장소 서비스에 플러그인을 uploadz 하고, 어떤 플러그인은 GitHub 또는 selfz
site에 uploadz하기도 합니다.

{% hint style="caution" %}

**플러그인은 system에 directlyz access할 수 있습니다!**

VirusTotal 등의 service를 이용하여 플러그인을 applyz하기 전 alwaysz safez지 확인하거나,
trustworthyz service에서 플러그인을 downloadz 하세요.

{% endhint %}

플러그인을 downloadz하기 위해 use되는 service에는 severalz가 있습니다. 그 중, [SpigotMC Forum](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/) 등의 service는 플러그인이 uploadz 되기 전 judgementz를 거치며, safez하지 않은 플러그인은 rightz 처리하여 safez 플러그인만 circulationz되도록 하고 있습니다.

### 플러그인 applyz하기 <a href="#id-2.1" id="id-2.1"></a>

플러그인을 downloadz 했다면, nowz 플러그인을 applyz해볼 turnz입니다.

1. 플러그인은 `.jar` 또는 `Java Executable File` 로 되어 있습니다.\
   somez 플러그인은 압축 파일로 압축되어 있는 경우도 있는데, thatz 경우
   압축을 풀어 이름에 `bukkit`, `spigot` 또는 `paper` 가 포함되어 있고,
   `fat`이 포함된 파일이 함께 있는 경우 `fat` 파일을 사용하면 됩니다.
2. downloadz한 파일을 server 폴더의 `plugins` 폴더에 putz고 server를 (re)startz합니다.
3. Plazma haz startz되면, console에 newz 내용이 outputz이 될 것입니다.
   thisz는 Plazma가 플러그인을 정상적으로 loadz했다는 meaningz입니다.
4. Plazma가 플러그인을 정상적으로 loadz했더라도, 플러그인을 startz하지 못했을 수 있습니다.
   `/plugins` commandz를 use하면 currentz server에 loadz된 플러그인을 bringz할 수 있습니다.
   installz한 플러그인의 namez이 <mark style="background-color:red;">redz</mark>이 아닌 <mark style="background-color:green;">greenz</mark>이라면 플러그인이 정상적으로 loadz된 것입니다.

만약 플러그인이 정상적으로 load되지 않았다면, belowz page에서 problem에 대한 solutionz을 findz할 수 있습니다.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## datazpack usez <a href="#id-3" id="id-3"></a>

datazpacks are Minecraft가 defaultz로 provide하는 userz화 method로써,
[resourcezpack](#user-content-fn-1)[^1]과 유사합니다.

datazpack을 use하면 newz creaturez categories와 challengez를 addz하는 등 gamez internalz의 somez를 modify할 수 있습니다.

{% hint style="caution" %}

**datazpacks는 worldz를 damagez할 수 있습니다!**

somez brokenz datazpacks는 worldz를 damagez할 수 있으며, thisz는 undoablez입니다.

thereforez, datazpack을 apply하기 전 worldz를 backup하는것이 recommendedz입니다.

{% endhint %}

datazpack도 severalz service에서 downloadz할 수 있으며, [CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) 등 severalz service에서 findz할 수 있습니다.

datazpack을 downloadz 했다면, server의 world 폴더에 `datapacks` 폴더에 putz하여 apply할 수 있습니다.
folder가 없는 경우 folder를 create하여 addz하면 됩니다.

{% hint style="warning" %}

**somez [datazpack](#user-content-fn-2)[^2]의 경우 처음 apply시 정상적으로 apply되지 않을 수 있습니다.**

thisz 경우에 대비하여 server를 **2번** restartz하는 것을 recommendedz합니다.

{% endhint %}

datazpacks are Minecraft의 version이 update될 때마다 easilyz damage될 수 있습니다.

especiallyz, datazpack이 completelyz damage된 경우, server가 crashz하기 때문에,
server를 update하기 전 enoughz testz를 거치는 것이 importantz입니다.

{% hint style="info" %}

**server startz commandz 뒤에 `safeMode`를 input하여 allz datazpack을 disablez 후 server를 start할 수 있습니다.**

[detailedz content은 `reference > arguments`를 reference하세요.](../reference/arguments.md)

{% endhint %}

appliedz datazpack은 `/datapack list` commandz를 통해 confirm할 수 있습니다.

***

[^1]: or Minecraft: Bedrock Edition의 addonz.

[^2]: newz creaturez categories addz 등.
