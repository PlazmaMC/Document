---
description: Leer meer oor beginargumente en stelsel eienskappe.
---

# 🎛️ Argumente en eienskappe

Beginveranderlikes en stelsel eienskappe is waardes wat by die Plazma-uitvoering gevoeg word as [opdragte wat gebruik word](#user-content-fn-1)[^1],\
om waardes toe te laat om verander te word nadat Plazma uitgevoer is.

Na gelang van die posisie waar dit by die opdrag gevoeg word, word dit verdeel in **beginargumente** en **stelsel eienskappe**.

***

## Stelsel eienskap <a href="#id-1" id="id-1"></a>

Stelsel eienskappe word voor `-jar` ingevoer en word deur die JVM voor Plazma geïnisialiseer verwerk.

{% hint style="warning" %}

**As jy die stelsel eienskappe wysig, kan die werking van Plazma en JVM verander, en dit kan 'n groot impak op die spel hê!**

As jy nie seker is oor die rol van elke stelsel eienskap nie, **moet jy dit beslis nie gebruik nie!**

{% endhint %}

### Gebruiksmetode <a href="#id-1.1" id="id-1.1"></a>

Stelsel eienskappe word tussen `java` en `-jar` as Java-opdragargumente ingevoer.

Byvoorbeeld, as jy die `Plazma.dummyProperty` stelsel eienskap wil toepas,\
word die volgende ingevoer waar die waarde `37` na die eienskap toegevoeg word en Plazma geïnisialiseer word.

```batch
java -Xms4G (...) -DPlazma.dummyProperty=37 -jar plazma.jar (...)
```

`-D` dui aan dat die argument nie ingebou is in die JVM nie, maar 'n spesiale argument vir Plazma is,

As geen waarde ingevoer word nie, word die waarde [`true` vasgestel.](#user-content-fn-3)[^3]

{% hint style="info" %}

**Die Paperweight-reeks bedienerplatform onderskei stelsel eienskappe vir elke platform deur die eienskapnaam te gebruik met `.` ingesluit.**

Windows Powershell enkele terminale mag nie hierdie argumente toelaat nie, dus moet jy `"` aan die uiteindes van die argumente [toevoeg.](#user-content-fn-4)[^4]

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

**Die `/reload` bevel is baie onstabiel, dus enige probleme wat na die gebruik van `/reload` in die bediener voorkom, is die verantwoordelikheid van die gebruiker self.**

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

Deaktiveer die limiet van 128 plugin-kanale per speler[^5].

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

- **Vorm**: `Integer`
- **Verstekwaarde**: `750`

As daar meer entiteite as die ingestelde waarde is, word dit in meerdere pakkette verdeel vir oordrag.

#### `Paper.filterThreshold`

- **Vorm**: `Integer`
- **Verstekwaarde**: `8192`

Stel die maksimum grootte van pakkette wat die bediener op 'n slag kan ontvang, in.

#### `Paper.ignoreJavaVersion`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `False`

Deaktiveer Java-weergawe kontrole.

{% hint style="danger" %}

**Dit kan veroorsaak dat die JVM probeer om toegang te verkry tot nie-bestaande kode!**

Dit kan lei tot permanente skade aan wêrelde en algemene lêers, en die hele spel se meganika kan ontwrig word.

Enige probleme wat deur hierdie aksie veroorsaak word, is die verantwoordelikheid van die individu en Plamza bied geen ondersteuning vir dit nie.

{% endhint %}

#### `Paper.maxCustomChannelName`

- **Vorm**: `Integer`
- **Verstekwaarde**: `64`

Stel 'n limiet vir die naam van plugin-kanale[^6].

#### `Paper.maxSignLength`

- **Vorm**: `Integer`
- **Verstekwaarde**: `80`

Stel die maksimum lengte van karakters in 'n tekenbordlyn in.

#### `Paper.minPrecachedDatafixVersion`

- **Vorm**: `Integer`
- **Verstekwaarde**: `(wêreldweergawe) + 1`

Stel die weergawe van die eerste wêreldopdateringsinligting in.

Dit is nuttig wanneer 'n groot aantal blokke opgedateer moet word, maar word andersins nie gebruik nie.

#### `Paper.parseYamlCommentsByDefault`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `True`

Aktiveer die hantering van YAML-lêeropmerkings standaard.

#### `Paper.playerConnection.keepAlive`

- **Vorm**: `Integer`
- **Verstekwaarde**: `30`

As geen data ontvang word van 'n speler vir die tydperk (in sekondes) wat hier ingestel is nie, word die speler gekick.

Gewoonlik stuur die spel[^7] voortdurend [hartklopseine](#user-content-fn-8)[^8] na die bediener, dus word die speler nie gekick nie, maar as die spel nie reageer nie, word dit as 'n kras beskou en die speler word gekick.

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

{% hint style="warning" %}

**Hierdie eienskap sal na beginargumente skuif vanaf 1.20.5.**

{% endhint %}

Pas strenger konfigurasie-optimalisering toe by die aanvang van die spel.

As dit geaktiveer word, sal die bediener vinniger en veiliger word, maar dit kan sekere meganismes blokkeer of 'n groot invloed op spel speel hê.

#### `Plazma.iWeetWatEkDoen`

- **Vorm**: `Boolean`
- **Verstekwaarde**: `false`

Onderdruk die waarskuwing[^11] wat verskyn wanneer Plazma geïnisieer word.

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

Stel die naam en ligging van die [Bukkit-konfigurasie lêer](../reference/configurations/bukkit.md) in.

#### `command-settings`

- **Alias**: `c`
- **Verwysing**: `commands.yml`

Stel die naam en ligging van die [Bukkit-opdragkonfigurasie lêer](../reference/configurations/bukkit.md) in.

#### `config`

- **Alias**: `c`
- **Verwysing**: `server.properties`

Stel die naam en ligging van die [bedieningseienskappe](../reference/configurations/property.md) lêer in.

#### `demo`

Begin die bediener met 'n demonstrasiewêreld.

#### `eraseCache`

Verwyder oorblywende kas lêers na wêreldopgradering.

#### `forceUpgrade`

Ignoreer die weergawe en dwing die wêreld om op te gradeer.

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

Stel die maksimum toegelate [spelers](#user-content-fn-14)[^14] getal in.

#### `nogui`

Deaktiveer die grafiese gebruikerskoppelvlak paneel.

#### `nojline`

Deaktiveer JLine en gebruik 'n vanielie-konsole.

#### `online-mode`

- **Alias**: `o`
- **Verwysing**: `(bedieners eienskap)`

Kies of die speler deur die Mojang verifikasiebediener geverifieer moet word.

**As jy nie Velocity of ander proksi gebruik nie, kan jy [EULA](../getting-started/README.md#id-5) oortree en gestraf word.**

#### `paper-settings`

- **Alias**: `paper`
- **Verwysing**: `paper.yml`

{% hint style="warning" %}

**Hierdie argument is na 1.19.4 nie meer in gebruik nie**

{% endhint %}

Stel die ligging van die verouderde PaperSpigot konfigurasie lêer in.

Dit word gebruik om bestaande konfigurasie na 'n nuwe konfigurasie lêer oor te dra en word daarna nie meer gebruik nie.

#### `paper-settings-directory`

- **Alias**: `paper-dir`
- **Verwysing**: `config`

Stel die naam en ligging van die [Paper konfigurasie lêer](../reference/configurations/paper/README.md) se vouer in.

#### `plazma-settings-directory`

- **Alias**: `plazma-dir`

Stel die naam en ligging van die [Plazma konfigurasie lêer](../reference/configurations/plazma/README.md) se vouer in.

#### `plugins`

- **Alias**: `p`
- **Verwysing**: `plugins`

Stel die ligging van die invoegtoepassing vouer in.

#### `pufferfish-settings`

- **Alias**: `pufferfish`
- **Verwysing**: `pufferfish.yml`

Stel die naam en ligging van die [Pufferfish konfigurasie lêer](../reference/configurations/pufferfish.md) in.

#### `purpur-settings`

- **Alias**: `purpur`
- **Verwysing**: `purpur.yml`

Stel die naam en ligging van die [Purpur konfigurasie lêer](../reference/configurations/purpur/README.md) in.

#### `safeMode`

Begin die bediener in veilige modus en stel dit in op volledige vanielie.

#### `server-ip`

- **Alias**: `h`, `host`
- **Verwysing**: `(bedieners eienskap)`

Stel die bediener se gasheer naam of [internetprotokol](#user-content-fn-13)[^13] adres in.

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

Stel die naam en ligging van die [Spigot konfigurasie lêer](../reference/configurations/spigot.md) in.

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

[^13]: Internetprotokol, IP.

[^14]: Administrateurs van `vlak 2` en hoër word uitgesluit.
