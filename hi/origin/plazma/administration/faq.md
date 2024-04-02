---
description: 자주 묻는 질문에 대해 जानें।
---

# ⁉️ 자주 묻는 질문

{% hint style="info" %}

**क्या आप चाहते हैं कि जवाब न मिला?**

[공식 Discord 서버](https://discord.gg/MmfC52K8A8) या [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) के माध्यम से समुदाय से प्रश्न पूछें!

{% endhint %}

### मैसेज दिखा कर कार्रवाई नहीं हो रही है

कंसोल में `no main manifest attribute, in plazma-(version).jar` दिखाई दे रहा है,\
डाउनलोड किया गया फ़ाइल विकास संबंधी एपीआई फ़ाइल है, GitHub पेज से **Reobf Paperweight** को डाउनलोड करना चाहिए।

अधिक जानने के लिए निम्नलिखित पेज का संदर्भ देखें।

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### सर्वर शुरू होते समय चेतावनी प्रदर्शित होती है

Plazma में कुछ अस्थिर पैच शामिल हैं और हमेशा गड़बड़ी होने की संभावना है, इसलिए सर्वर शुरू होते समय यह चेतावनी संदेश प्रदर्शित कर रहा है।

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

इस चेतावनी संदेश को [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] सिस्टम गुण का उपयोग करके निषेधित किया जा सकता है।

अधिक जानने के लिए निम्नलिखित पेज का संदर्भ देखें।

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: 1.20.1 से उपलब्ध
