---
description: Pelajari lebih lanjut tentang platform server Plazma.
---

# ❓ Plazma란?

- **Plazma**는 [Andromeda](https://github.com/EarendelArchived/Andromeda)와 [Fusion](https://github.com/RuinedTechnologyUnify/Fusion)에서 장점만을 가져온 [Paper](https://github.com/PaperMC/Paper) 기반의 서버 플랫폼 입니다.
- 항상 높은 안정성과 강력한 성능, 빠른 업데이트, 방대한 기능을 제공하기 위하여 노력하고 있습니다.

## 📋 Plazma의 목표 <a href="#id-1" id="id-1"></a>

- 빠른 업데이트, 높은 안정성을 가진 서버 플랫폼이 되기 위해 노력하고 있습니다.
- 모드 플랫폼 못지 않은 방대한 기능과 강력한 성능을 제공하기 위해 노력하고 있습니다.
- 바닐라의 패치도 사용자화 할 수 있는 자유로운 플랫폼을 만들기 위해 노력하고 있습니다.

## ⚙️ 주요 특징 <a href="#id-2" id="id-2"></a>

1. **강력한 플러그인 생태계**\
   [Paper](https://github.com/PaperMC/Paper)를 기반으로 하고 있어, 인터넷에서 다운로드 가능한 대부분의 [최신 플러그인](#user-content-fn-1)[^1]이 정상 작동합니다.
2. **설정이 필요 없는 최적화**\
   [Pufferfish](https://github.com/pufferfish-gg/Pufferfish)의 모든 패치가 포함되어 있으며, 일부 자체 최적화와 모드가 내장되어 있어 최고의 성능을 제공합니다.
3. **원하는 대로 사용자화하는 게임**\
   Plazma에 포함된 [Purpur](https://github.com/PurpurMC/Purpur)는 게임의 전반적인 속성을 수정할 수 있게 해줍니다.
4. **안전하게 플레이하는 서버**\
   [No Chat Reports](https://github.com/Aizistral-Studios/No-Chat-Reports)가 포함되어 있어 1.19부터 추가된 Mojang[^2]의 [채팅 신고 시스템](#user-content-fn-3)[^3]을 비활성화 할 수 있으며,\
   진단 정보 수집기가 완전 제거되어 추적 없는 안전한 서버를 플레이 할 수 있습니다.
5. **가장 빠른 업데이트**\
   [AlwaysUpToDate](https://github.com/PlazmaMC/AlwaysUpToDate)는 Plazma의 포함 패치가 항상 최신으로 유지될 수 있도록 해서, Paper 기반 서버 플랫폼 중에서 가장 빠른 업데이트를 제공하고 있습니다.
6. **기본 구성 파일 최적화**\
   기본 적용되는 구성 파일이 최적화되어 있어, 직접 구성 파일을 최적화 하지 않아도 됩니다.
7. **체계적으로 작동하는 멀티스레드**\
   게임의 메커니즘과 관계 없는 시스템 메커니즘을 비동기화 하여, [지연 시간](#user-content-fn-4)[^4]을 줄여 서버를 최적화 합니다.
8. **불필요한 공간의 사용 차단**\
   비슷한 값을 가진 데이터를 모두 하나로 합쳐 메모리 사용량을 줄입니다.

## ✨ 활용 사례 <a href="#id-3" id="id-3"></a>

- **Platform yang Menangani Plugin Rumit dengan Benar**\
  Plazma digunakan di server pengembang [IPECTER](https://github.com/IPECTER).\
  Plugin internal yang beroperasi dengan NMS dan refleksi, serta banyak paket data kompleks dan besar
  diterapkan tanpa penurunan kinerja untuk lebih dari 100 pemain.
- **Platform yang Tetap Cepat di Server RPG**\
  Mampu menjaga 100 pemain dalam satu cluster tanpa penurunan TPS, serta
  memungkinkan 250 pemain untuk bermain nyaman di 4 cluster.
- **청크/엔티티에서 빛을 보이는 플랫폼**\
  기존에 청크와 엔티티를 처리하는 데 지연이 발생하던 서바이벌 서버의 플랫폼을 Purpur에서 Plazma로 변경하며 대부분의 지연을 줄일 수 있었습니다.
- **Platform yang Dipilih Banyak Streamer**\
  Digunakan sebagai ember partisipasi penonton banyak streamer.

[![실시간 Plazma 사용자 추이](https://badge.plazmamc.org/internal/bstats)](https://bstats.org/plugin/server-implementation/Plazma/18047)

## ⬇️ Unduh

아래 페이지에서 Plazma를 다운로드 할 수 있습니다.

{% content-ref url="downloads.md" %}
[downloads.md](downloads.md)
{% endcontent-ref %}

#### Ingin mengetahui informasi detail tentang dukungan versi?

{% content-ref url="supported-versions.md" %}
[supported-versions.md](supported-versions.md)
{% endcontent-ref %}

***

[^1]: Bukkit, CraftBukkit, Spigot 플러그인 및 Paper, Pufferfish, Purpur 플러그인.

[^2]: 이하 Microsoft Corporation.

[^3]: 채팅 신고 시스템을 비활성화 하면 채팅이 온전히 서버에서만 처리되어 Mojang의 채팅 추적을 막을 수 있습니다.

[^4]: 시스템 메커니즘이 작동하기 위해 잠시 동안 게임이 멈추는 시간.
