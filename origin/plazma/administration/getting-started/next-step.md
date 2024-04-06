---
description: 서버를 사용자화하는 방법에 대해 알아보세요.
---

# 📶 발전하기

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

***

## 플러그인 사용 <a href="#id-2" id="id-2"></a>

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
   설치한 플러그인의 이름이 <mark style="background-color:red;">적색</mark>이 아닌
   <mark style="background-color:green;">녹색</mark>이라면 플러그인이 정상적으로 로드된 것입니다.

만약 플러그인이 정상적으로 로드되지 않았다면, 아래 페이지에서 문제에 대한 해결 방법을 찾을 수 있습니다.

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

***

## 데이터팩 사용 <a href="#id-3" id="id-3"></a>

데이터팩은 Minecraft가 기본적으로 제공하는 사용자화 방법으로써,
[리소스팩](#user-content-fn-1)[^1]과 유사합니다.

데이터팩을 사용하면 새로운 생물 군계와 도전 과제를 추가하는 등 게임 내부의 일부를 수정할 수 있습니다.

{% hint style="caution" %}

**데이터팩은 월드를 손상시킬 수 있습니다!**

일부 고장난 데이터팩은 월드를 손상시킬 수 있으며, 이는 돌이킬 수 없습니다.

따라서, 데이터팩을 적용하기 전 월드를 백업하는것이 권장됩니다.

{% endhint %}

데이터팩 또한 여러 서비스에서 다운로드 할 수 있으며, [CurseForge](https://www.curseforge.com/minecraft/search?page=1&pageSize=50&sortBy=relevancy&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/) 등 여러 서비스에서 찾을 수 있습니다.

데이터팩을 다운로드 했다면, 서버의 월드 폴더에 `datapacks` 폴더에 넣어 적용할 수 있습니다.
폴더가 없는 경우 폴더를 생성하여 추가하면 됩니다.

{% hint style="warning" %}

**[일부 데이터팩](#user-content-fn-2)[^2]의 경우 처음 적용시 정상적으로 적용되지 않을 수 있습니다.**

이런 경우에 대비하여 서버를 **2번** 재시작하는 것을 권장합니다.

{% endhint %}

데이터팩은 Minecraft의 버전이 업데이트 될 때 마다 쉽게 손상될 수 있습니다.

특히, 데이터팩이 완전히 손상된 경우, 서버가 충돌하기 때문에,
서버를 업데이트하기 전 충분한 테스트를 거치는 것이 중요합니다.

{% hint style="info" %}

**서버 시작 명령어 뒤에 `safeMode`를 입력하여 데이터팩을 모두 비활성화 한 뒤 서버를 시작할 수 있습니다.**

[자세한 내용은 `리퍼런스 > 인수와 속성`을 참고하세요.](../reference/arguments.md#safeMode)

{% endhint %}

적용된 데이터팩은 `/datapack list` 명령어를 통해 확인할 수 있습니다.

***

## 최적화 <a href="#id-4" id="id-4"></a>

Plazma에는 많은 최적화 패치가 적용되어 있습니다. 또한, Plazma가 처음으로 시작되면 자동으로
구성을 최적화 하므로 [시작하기](./README.md) 가이드를 따른 경우 추가적인 최적화 작업을 할 필요가 없습니다.

하지만, 많은 플레이어가 접속하거나, 월드의 크기가 방대한 경우,
아래 가이드를 통해 추가적인 최적화 작업을 할 수 있습니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## 프록시 <a href="#id-5" id="id-5"></a>

프록시는 서버를 서로 연결하고 플레이어가 추가적인 작업 없이 서버를 이동하거나,
다른 서버와 소통할 수 있게 합니다.

안전하고 올바른 프록시 설정에 대한 정보는 아래 페이지를 참고하세요.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

***

## 안전 <a href="#id-5" id="id-5"></a>

Minecraft는 모드가 발달하여 온라인에서도 쉽게 [취약점 공격 엔진](#user-content-fn-3)[^3]을 구할 수 있습니다.

일반 게임에서도 실행 가능한 대부분의 취약점은 [기본적으로 차단되어 있지만](#user-content-fn-4)[^4],
서드파티 로더를 통해 취약점을 공격하는것은 차단되어 있지 않습니다.

따라서, 서버가 공개되어 있는 경우, 안티 치트 플러그인 등을 설치하여 취약점 사용을 차단하고,
프록시 및 자동 재시작, 백업 등을 구성하여 서버가 다운되어도 빠르게 복구할 수 있도록 하는 것이 권장됩니다.

### 권한 설정 <a href="#id-5.1" id="id-5.1"></a>

일부 플러그인의 관리자 명령어는 권한이 제대로 설정되지 않은 취약점이 존재하기도 합니다.

[LuckPerms](https://luckperms.net/) 등의 권한 관리 플러그인을 사용하여
일반 사용자의 권한을 제한하는 조치를 하는것이 권장됩니다.

### X-Ray 차단 <a href="#id-5.2" id="id-5.2"></a>

X-Ray는 기본적인 최적화 클라이언트에서도 쉽게 사용 가능한 취약점 중 하나입니다.

Plazma에는 X-Ray를 기본적으로 차단할 수 있는 구성을 제공하고 있습니다.

X-Ray 차단 방법과 설명은 아래 페이지를 참고하시기 바랍니다.

{% content-ref url="../expert/optimize.md" %}
[optimize.md](../expert/optimize.md)
{% endcontent-ref %}

### 화이트리스트 <a href="#id-5.3" id="id-5.3"></a>

일부 사용자만 서버에 접속할 수 있도록 하는 경우,
[Ngrok](./README.md#id-6.2)을 사용하여 [난독화된 서버 주소를 사용](#user-content-fn-5)[^5] 하거나,
화이트리스트를 설정하여 다른 플레이어가 서버에 접속하지 못하도록 하는 것도 권장됩니다.

서버 콘솔에서 `/whitelist add <player>` 를 통해 플레이어의 접속을 허용하거나,
`/whitelist remove <player>` 로 플레이어의 접속을 다시 금지할 수 있습니다.

접속이 허용된 플레이어를 보려면 `/whitelist query` 를 사용합니다.

***

[^1]: 또는 Minecraft: Bedrock Edition의 애드온.
[^2]: 생물 군계 추가 등.
[^3]: 일반적으로 "핵" 으로 불립니다.
[^4]: 구성이 최적화되지 않았거나, Plazma가 오래되었거나, 새로 발견된 취약점의 경우 차단되어 있지 않을 수 있습니다.
[^5]: 플레이어가 서버에 접속할 때 Ngrok 프록시 서버를 통해 접속되며, 매 재시작마다 발급되는 Ngrok 주소는 달라집니다.
