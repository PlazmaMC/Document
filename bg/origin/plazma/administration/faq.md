---
description: Научете повече за често задавани въпроси.
---

# ⁉️ Често задавани въпроси

{% hint style="info" %}

**원하는 답변을 찾을 수 없나요?**

Попитайте общността чрез [официалния Discord сървър](https://discord.gg/MmfC52K8A8) или [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues)!

{% endhint %}

### 메세지가 출력되면서 실행이 되지 않습니다

콘솔에 `no main manifest attribute, in plazma-(version).jar` 라고 출력된 경우,\
다운로드한 파일은 개발용 API 파일로, GitHub 페이지에서 **Reobf Paperweight**을 다운로드해야 합니다.

자세히 알아보려면 다음 페이지를 참고 하세요.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### 서버가 시작될 때 마다 경고가 표시됩니다

Plazma는 일부 불안정한 패치가 포함되어 있으며, 항상 오작동할 가능성이 있으므로 다음과 같은 경고문을 서버가 시작될 때 출력하고 있습니다.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

해당 경고문은 [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] 시스템 속성을 사용하여 비활성화 할 수 있습니다.

자세히 알아보려면 다음 페이지를 참고 하세요.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: 1.20.1부터 사용 가능
