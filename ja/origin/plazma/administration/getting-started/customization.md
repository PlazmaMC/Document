---
description: サーバーをカスタマイズする方法について学びましょう。
---

# 🎨 ユーザー定義

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

**PlazmaはPaperベースのすべてのプラグインを正常にサポートします。**

Spigotプラグインの場合、1.20.5からPaperのマッピングの変更により一部が機能しない場合がありますが、
Paper、Pufferfish、PurpurなどPaperベースのほとんどのプラグインはPlazmaでも
すべて動作し、正常に動作しない場合はPlazmaのエラーであるため、直ちに[報告してください。](../diagnosis/plugins.md)

{% endhint %}

Plazmaを使用する主な理由であり、Plazmaをカスタマイズする最も強力な方法です。
Plazmaの強力なプラグインエコシステムはサーバーを簡単にカスタマイズできるようにします。

プラグインを見つけてダウンロードするには、さまざまな方法があります。 いくつかのプラグインは
パブリックリポジトリサービスにプラグインをアップロードし、いくつかのプラグインはGitHubや独自の
サイトにアップロードすることもあります。

{% hint style="caution" %}

**プラグインはシステムに直接アクセスできます！**

VirusTotalなどのサービスを使用してプラグインを適用する前に常に安全か確認するか、
信頼できるサービスからプラグインをダウンロードしてください。

{% endhint %}

プラグインをダウンロードするために使用されるサービスにはさまざまなものがあります。 そのうち、[SpigotMCフォーラム](https://www.spigotmc.org/resources/), [BukkitDev (CurseForge)](https://dev.bukkit.org/bukkit-plugins), [Modrinth](https://modrinth.com/plugins), [Hanger](https://hangar.papermc.io/)などのサービスはプラグインがアップロードされる前に審査を受け、安全でないプラグインは直ちに処理して安全なプラグインのみが流通するようにしています。

### プラグインの適用 <a href="#id-2.1" id="id-2.1"></a>

プラグインをダウンロードしたら、次はプラグインを適用する番です。

1. プラグインは`.jar`または`Java実行可能ファイル`で構成されています。\
   一部のプラグインは圧縮ファイルに圧縮されている場合もあり、その場合
   圧縮を解除して名前に`bukkit`、`spigot`または`paper`が含まれており、
   `fat`が含まれているファイルが一緒にある場合は`fat`ファイルを使用します。
2. ダウンロードしたファイルをサーバーフォルダの`plugins`フォルダに入れてサーバーを(再)起動します。
3. Plazmaが開始されると、コンソールに新しい内容が出力されます。
   これはPlazmaがプラグインを正常にロードしたことを意味します。
4. Plazmaがプラグインを正常にロードしていても、プラグインを開始できない場合があります。
   `/plugins`コマンドを使用すると、現在のサーバーにロードされたプラグインを読み込むことができます。
   インストールしたプラグインの名前が<mark style="background-color:red;">赤色</mark>でなく <mark style="background-color:green;">緑色</mark>であれば、プラグインが正常にロードされたことを意味します。

プラグインが正常にロードされない場合、以下のページで問題の解決策を見つけることができます。

{% content-ref url="../diagnosis/plugins.md" %}
[plugins.md](../diagnosis/plugins.md)
{% endcontent-ref %}

## データパックの使用 <a href="#id-3" id="id-3"></a>

データパックはMinecraftが基本的に提供するカスタマイズ方法であり、
[リソースパック](#user-content-fn-1)[^1]と類似しています。

データパックを使用すると、新しい生物群系やチャレンジを追加するなど、ゲーム内の一部を変更できます。

{% hint style="caution" %}

**データパックはワールドを破壊する可能性があります！**

一部の故障したデータパックはワールドを破壊する可能性があり、元に戻すことはできません。

したがって、データパックを適用する前にワールドをバックアップすることが推奨されます。

{% endhint %}

データパックもさまざまなサービスからダウンロードでき、[CurseForge](https://www.curseforge.com/minecraft/search?page=1\&pageSize=50\&sortBy=relevancy\&class=data-packs), [Modrinth](https://modrinth.com/datapacks), [Planet Minecraft](https://www.planetminecraft.com/data-packs/)などのさまざまなサービスで見つけることができます。

データパックをダウンロードしたら、サーバーのワールドフォルダに`datapacks`フォルダに入れて適用できます。
フォルダがない場合は、フォルダを作成して追加すればよいです。

{% hint style="warning" %}

**一部の[データパック](#user-content-fn-2)[^2]は最初に適用されると正常に適用されない場合があります。**

このような場合に備えて、サーバーを**2回**再起動することをお勧めします。

{% endhint %}

データパックはMinecraftのバージョンが更新されるたびに簡単に破損する可能性があります。

特に、データパックが完全に破損した場合、サーバーがクラッシュするため、
サーバーを更新する前に十分なテストを行うことが重要です。

{% hint style="info" %}

**サーバー起動コマンドの後に`safeMode`を入力してデータパックをすべて無効にした後、サーバーを起動できます。**

[詳細については`リファレンス > 引数とプロパティ`を参照してください。](../reference/arguments.md)

{% endhint %}

適用されたデータパックは`/datapack list`コマンドで確認できます。

***

[^1]: またはMinecraft: Bedrock Editionのアドオン。

[^2]: 新しい生物群系の追加など。
