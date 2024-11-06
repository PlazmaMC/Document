---
description: Leer meer oor beginargumente en stelsel eienskappe.
---

# 🎛️ Argumente en eienskappe

Die beginwaarde en stelselkenmerke is waardes wat by die uitvoering van Plazma [gebruik word](#user-content-fn-1)[^1], wat 'n algemene invloed op die werking van Plazma het.

[Posisie wat by die opdrag gevoeg word](#user-content-fn-2)[^2] sal verdeel word in **beginargument** en **sisteemeienskappe** volgens die.

***

## Stelsel eienskap <a href="#id-1" id="id-1"></a>

Stelsel eienskappe word voor `-jar` ingevoer en word deur die JVM voor Plazma geïnisialiseer verwerk.

{% hint style="warning" %}
**시스템 속성을 수정하면 Plazma 및 JVM의 작동 방식이 변경될 수 있으며, 게임에 큰 영향을 미칠 수 있습니다!**

각 시스템 속성이 어떠한 역할을 하는지 확실히 알지 못하는 경우, **절대 사용하지 마세요!**
{% endhint %}

### Gebruiksmetode <a href="#id-1.1" id="id-1.1"></a>

Stelsel eienskappe word tussen `java` en `-jar` as Java-opdragargumente ingevoer.

예를 들어, `Plazma.dummyProperty` 시스템 속성을 적용하려 하는 경우, 다음과 같이 입력하면 다음 속성에 `37`이 입력되어 Plazma가 초기화 됩니다.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` dui aan dat die argument nie ingebou is in die JVM nie, maar 'n spesiale argument vir Plazma is,

As geen waarde vir eienskappe ingevoer word nie, word die waarde [`true` vasgestel](#user-content-fn-3)[^3].

{% hint style="info" %}
**Paperweight 계열 서버 플랫폼은 각 플랫폼마다 시스템 속성을 구분하기 위하여 속성 이름에 `.`을 포함하고 있습니다.**

Windows Powershell 등 일부 터미널에서는 이러한 인수를 허용하지 않을 수 있으므로, 인수 양 끝에 `"`를 추가해야[^4] 합니다.
{% endhint %}

### Algemene stelsel eienskappe <a href="#id-1.2" id="id-1.2"></a>

#### `convertLegacySigns`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Blyf opgedateerde tekens wat nie meer gebruik word nie.

#### `debug.entities`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Aktiveer debug-logboeke rakende entiteitsinligting.

#### `debug.rewriteForIDE`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer NMS-revisie om korrek inligting vanaf die IDE te laai en hersien interne weergawe-inligting.

#### `disable.watchdog`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer die Spigot se Wagter-waarskuwingstelsel.

#### `letMeReload`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer die bevestigingsboodskap vir die `/reload` opdrag.

{% hint style="danger" %}
**`/reload` 명령어는 매우 불안정하므로, `/reload` 사용 이후 발생하는 서버 내 모든 문제는 사용자 본인에게 있습니다.**

As jy 'n pluginontwikkelaar is en jy moet jou plugin opdateer, gebruik hotswap in plaas van `/reload`.
{% endhint %}

#### `io.papermc.paper.suppress.sout.nags` <a href="#suppresssoutnags" id="suppresssoutnags"></a>

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer plugins wat standaard in- en uitvoerstelsels gebruik.

#### `net.kyori.adventure.text.warnWhenLegacyFormattingDetected` <a href="#warnwhenlegacyformattingdetected" id="warnwhenlegacyformattingdetected"></a>

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Waarsku wanneer afgeskafte formaat in die geselskapkomponent opgespoor word.

#### `Paper.bypassHostCheck`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer die bedienerspatroonkontrole wanneer 'n speler aansluit.

#### `Paper.debugDynamicMissingKeys`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Aktiveer debug-logboeke vir ontbrekende sleutels in NBT-voorwerpe.

#### `Paper.debugInvalidSkullProfiles`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Aktiveer debug-logboeke vir ongeldige skildprofielinligting.

Dit log al die ongeldige skildblokke in die wêreld saam met hul posisies.

#### `Paper.disableChannelLimit`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

플레이어당 적용되는 128개의 플러그인 채널[^5]의 개수 제한을 비활성화 합니다.

#### `Paper.disableClassPrioritization`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer die plugin-klasprioritiseringstelsel.

Dit is nuttig as daar probleme is met plugin-skaduwees.

#### `Paper.disableFlushConsolidate`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer die Netty flush-konsolidasie stelsel.

#### `Paper.excessiveTELimit`

- **형태**: `Integer`
- **Verstekwaarde**: `750`

As daar meer entiteite as die ingestelde waarde is, word dit in meerdere pakkette verdeel vir oordrag.

#### `Paper.filterThreshold`

- **형태**: `Integer`
- **Verstekwaarde**: `8192`

Stel die maksimum grootte van pakkette wat die bediener op 'n slag kan ontvang, in.

#### `Paper.ignoreJavaVersion`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer Java-weergawe kontrole.

{% hint style="danger" %}
**이렇게 하면 JVM이 존재하지 않는 코드에 접근하려 시도할 수 있습니다!**

Dit kan lei tot permanente skade aan wêrelde en algemene lêers, en die hele spel se meganika kan ontwrig word.

Enige probleme wat deur hierdie aksie veroorsaak word, is die verantwoordelikheid van die individu en Plamza bied geen ondersteuning vir dit nie.
{% endhint %}

#### `Paper.maxCustomChannelName`

- **형태**: `Integer`
- **Verstekwaarde**: `64`

플러그인 채널[^6] 이름의 제한을 설정합니다.

#### `Paper.maxSignLength`

- **형태**: `Integer`
- **Verstekwaarde**: `80`

Stel die maksimum lengte van karakters in 'n tekenbordlyn in.

#### `Paper.minPrecachedDatafixVersion`

- **형태**: `Integer`
- **Verstekwaarde**: `(wêreldweergawe) + 1`

Stel die weergawe van die eerste wêreldopdateringsinligting in.

Dit is nuttig wanneer 'n groot aantal blokke opgedateer moet word, maar word andersins nie gebruik nie.

#### `Paper.parseYamlCommentsByDefault`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `True`

Aktiveer die hantering van YAML-lêeropmerkings standaard.

#### `Paper.playerConnection.keepAlive`

- **형태**: `Integer`
- **Verstekwaarde**: `30`

As geen data ontvang word van 'n speler vir die tydperk (in sekondes) wat hier ingestel is nie, word die speler gekick.

일반적인 경우, 게임[^7]은 서버로 계속해서 [하트비트 신호](#user-content-fn-8)[^8]를 전송하므로, [추방되지 않지만,](#user-content-fn-9)[^9] 게임이 응답하지 않는 경우 게임이 충돌한 것으로 간주하고 더 이상 서버에서도 플레이어를 처리하지 않고 추방합니다.

#### `Paper.skipServerPropertiesComments`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Ignoreer die kommentaar van die bedienereienskappe.

#### `Paper.debug-sync-loads`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Aktiveer debug-logboeke vir sinchroniese blok skryf.

#### `Paper.enable-sync-chunk-writes`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Aktiveer die [standaard blok skryf stelsel](#user-content-fn-10)[^10] van Minecraft.

Dit skryf elke blok een vir een weg, wat tot ernstige prestasie-verlies lei.

#### `Paper.explicit-flush`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Aktiveer die ekspliciete spoel van die netwerkkanale.

#### `Paper.strict-thread-checks`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Log altyd foute wat nie op die hoofdraad plaasvind nie.

#### `Paper.tickList-warn-on-excessive-delay`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Waarsku wanneer 'n geskeduleerde taak 'n oormatige vertraging het.

#### `Paperclip.patchOnly`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

As jy die standaard uitvoerlêer gebruik, pas slegs die patch toe sonder om die bediener te begin.

#### `Plazma.aggressiveOptimize`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `false`
- **Botsing**: `Plazma.disableConfigOptimization`

Verhoog die aanvanklike konfigurasie kragtiger.

Die aktivering sal die bediener vinniger en veiliger maak, maar kan 'n groot invloed hê op die speel van die spel.

#### `Plazma.disableConfigOptimization`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `false`
- **Botsing**: `Plazma.aggressiveOptimize`

Optimeer nie die aanvanklike konfigurasie nie.

Hierdie stel die standaard konfigurasie van Paper in.

#### `Plazma.iWeetWatEkDoen`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `false`

Plazma가 초기화될 때 출력되는 경고문[^11]을 억제합니다.

#### `Plazma.useVanillaFavicon`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `false`

Deaktiveer Plazma branding en gebruik die vanilla bediener favicon.

#### `Plazma.useVanillaConfiguration`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `false`
- **Botsing**: `Plazma.disableConfigOptimization`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

{% hint style="danger" %}
**해당 속성은 패치된 모든 취약점을 되돌립니다!**

Dit kan 'n groot impak hê op bediener veiligheid en prestasie.

Enige probleme wat deur hierdie eienskap veroorsaak word, is die verantwoordelikheid van die bedieneradministrateur.
{% endhint %}

Stel die aanvanklike konfigurasie in op die standaardwaardes wat Mojang verskaf.

Dit deaktiveer enige kwesbaarheidspats wat deur Paper geïmplementeer is.

Kwesbaarheidspats kan weer geaktiveer word in die Paper- of Plazma-konfigurasie.

#### `Plazma.vanillaize`

- **Vorm**: `Boolean`
- **Verstek**: `true`
- **Botsing**: `Plazma.aggressiveOptimize`

{% hint style="info" %}
**해당 속성은 아직 개발중입니다.**
{% endhint %}

Stel die aanvanklike konfigurasie nader aan vanilla in.

이는 기본적으로 서버 성능 및 안전에 영향을 주지 않을 정도로만 적용되며, `Plazma.disableConfigOptimization` 속성을 사용할 경우 바닐라 기본값을 사용하도록 구성합니다.

### Verouderde eienskap <a href="#id-1.3" id="id-1.3"></a>

Die onderstaande stelsel eienskap is 'n verouderde eienskap.

#### `timings.bypassMax`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `false`
- **Verouderd**: Timings is verwyder uit Plazma sedert

Besluit of die waarde wat na Aikar se Timings API gestuur kan word, die maksimum mag oorskry.

Selfs al doen jy dit, as dit nie deur die API hanteer word nie, sal 'n spoedbeperking toegepas word.

***

## Beginargument <a href="#id-2" id="id-2"></a>

Die beginargument word na `-jar *.jar` ingevoer en word saam met Plazma geïnisialiseer en verwerk.

### Gebruiksaanwysing <a href="#id-2.1" id="id-2.1"></a>

Stelsel eienskappe word as programopdragargumente na `-jar *.jar` ingevoer.

Byvoorbeeld, as jy die `nogui` beginargument wil toepas,\
dan sal Plazma die `nogui` argument tydens inisialisering verwerk.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar nogui (...)
```

### Volledige beginargument <a href="#id-2.2" id="id-2.2"></a>

#### `bukkit-settings`

- **Alias**: `b`
- **Verwysing**: `bukkit.yml`

[Bukkit 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `command-settings`

- **Alias**: `c`
- **Verwysing**: `commands.yml`

[Bukkit 명령어 구성 파일](configurations/bukkit.md)의 이름 및 위치를 설정합니다.

#### `config`

- **Alias**: `c`
- **Verwysing**: `server.properties`

[서버 속성](configurations/property.md) 파일의 이름 및 위치를 설정합니다.

#### `demo`

Begin die bediener met 'n demonstrasiewêreld.

#### `eraseCache`

Verwyder oorblywende kas lêers na wêreldopgradering.

#### `forceUpgrade`

버전을 무시하고 월드를 강제로 업그레이드[^12] 합니다.

#### `help`

- **Alias**: `?`

Druk die volledige beginargumente en beskrywings van Plazma uit.

#### `initSettings`

Skep slegs konfigurasie lêers en sluit die bediener af.

#### `jfrProfile`

Aktiveer JFR profilering.

#### `max-players`

- **Alias**: `s`, `size`
- **Verwysing**: `(bedieners eienskap)`

허용되는 최대 플레이어[^13] 수를 설정합니다.

#### `nogui`

Deaktiveer die grafiese gebruikerskoppelvlak paneel.

#### `nojline`

Deaktiveer JLine en gebruik 'n vanielie-konsole.

#### `online-mode`

- **Alias**: `o`
- **Verwysing**: `(bedieners eienskap)`

Kies of die speler deur die Mojang verifikasiebediener geverifieer moet word.

**Velocity 등 프록시를 사용하는 것이 아닌 경우** [**EULA**](../getting-started/#id-5) **위반으로 제재될 수 있습니다.**

#### `paper-settings`

- **Alias**: `paper`
- **Verwysing**: `paper.yml`

{% hint style="warning" %}
**이 인수는 1.19.4 이후 사용이 중지되었습니다**
{% endhint %}

Stel die ligging van die verouderde PaperSpigot konfigurasie lêer in.

Dit word gebruik om bestaande konfigurasie na 'n nuwe konfigurasie lêer oor te dra en word daarna nie meer gebruik nie.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Verwysing**: `config`

[Paper 구성 파일](configurations/paper/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

[Plazma 구성 파일](configurations/plazma/)이 위치하는 폴더의 이름 및 위치를 설정합니다.

#### `plugins`

- **Alias**: `p`
- **Verwysing**: `plugins`

Stel die ligging van die invoegtoepassing vouer in.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Verwysing**: `pufferfish.yml`

[Pufferfish 구성 파일](configurations/pufferfish.md)의 이름 및 위치를 설정합니다.

#### `purpur-settings`

- **Alias**: `purpur`
- **Verwysing**: `purpur.yml`

[Purpur 구성 파일](configurations/purpur/)의 이름 및 위치를 설정합니다.

#### `safeMode`

Begin die bediener in veilige modus en stel dit in op volledige vanielie.

#### `server-ip`

- **Alias**: `h`, `host`
- **Verwysing**: `(bedieners eienskap)`

서버의 호스트 이름 또는 [인터넷 프로토콜](#user-content-fn-14)[^14] 주소를 설정합니다.

#### `server-port`

- **Alias**: `p`, `port`
- **Verwysing**: `(bedieners eienskap)`

Stel die bediener se poort in.

#### `server-name`

- **Verwysing**: `A Plazma Server`

Stel die bediener se naam in.

#### `spigot-settings`

- **Alias**: `S`
- **Verwysing**: `spigot.yml`

[Spigot 구성 파일](configurations/spigot.md)의 이름 및 위치를 설정합니다.

#### `version`

- **Alias**: `v`

Druk die Plazma weergawe uit.

#### `world-dir`

- **Alias**: `W`, `universe`, `world-container`
- **Verwysing**: `(bediener vouer)`

Stel die ligging waar wêreld lêers gestoor word in.

#### `world-name`

- **Alias**: `w`, `world`
- **Verwysing**: `(bedieners eienskap)`

Stel die naam van die wêreld lêer in.

***

[^1]: `java (...) -jar server.jar (...)`

[^2]: Die posisie wat verwerk word, verander afhangende van die bygevoegde posisie.

[^3]: Byvoorbeeld, as jy `Plazma.iKnowWhatIAmDoing` na `true` wil stel (aktiveer), sal dit dieselfde werk as om slegs `-DPlazma.iKnowWhatIAmDoing` in te voer in plaas van `-DPlazma.iKnowWhatIAmDoing=true`.

[^4]: Byvoorbeeld, `"-DPlazma.iKnowWhatIAmDoing"`

[^5]: Gebeurtenisdetektor.

[^6]: Gebeurtenisdetektor.

[^7]: Kliënt.

[^8]: 'n Sein wat aandui dat dit korrek met die bediener soos 'n hartklop verbind is.

[^9]: Met Purpur se AFK-verbanfunksie kan jy spelers wat afwesig is ook verban.

[^10]: Sync Chunk Write System, sinkroniseer chunk skryfstelsel.

[^11]: `WAARSKUWING! Plazma kan onverwagte probleme veroorsaak, so maak seker om dit deeglik te toets voordat jy dit op 'n openbare bediener gebruik.`

[^12]: In die spel werk `wêreldoptimalisering` ook op hierdie beginsel.

[^13]: Administrateurs van `vlak 2` en hoër word uitgesluit.

[^14]: Internetprotokol, IP.
