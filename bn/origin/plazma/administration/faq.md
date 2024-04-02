---
description: 자주 জিজ্ঞাসিত প্রশ্ন সম্পর্কে জানুন।
---

# ⁉️ জিজ্ঞাসিত প্রশ্ন

{% hint style="info" %}

**আপনি কি পছন্দ করা উত্তর খুঁজতে পারছেন না?**

[অফিসিয়াল Discord সার্ভার](https://discord.gg/MmfC52K8A8) বা [GitHub ইস্যু](https://github.com/PlazmaMC/PlazmaBukkit/issues) এর মাধ্যমে সম্প্রদায়ে প্রশ্ন করুন!

{% endhint %}

### প্লাজমা চালু হচ্ছে না

যদি কনসোলে `no main manifest attribute, in plazma-(version).jar` মেসেজ প্রিন্ট হয়,\
তাহলে ডাউনলোড করা ফাইলটি ডেভেলপমেন্ট API ফাইল এবং GitHub পেজ থেকে **Reobf Paperweight** ডাউনলোড করতে হবে।

বিস্তারিত জানতে নিচের পেজটি দেখুন।

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### সার্ভার চালু হওয়ার সময় সবসময় সতর্কতা দেখানো হয়

Plazma-তে কিছু অস্থির প্যাচ থাকতে পারে এবং সার্ভারে সবসময় অপ্রত্যাশিত সমস্যা হতে পারে, তাই সার্ভার চালু হওয়ার সময় এই ধরনের সতর্কতা মেসেজ প্রিন্ট করে।

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

উক্ত সতর্কতা মেসেজটি ব্যবহার করে অনলাইনে নিষ্ক্রিয় করা যেতে পারে [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1] সিস্টেম প্রপার্টির মাধ্যমে।

বিস্তারিত জানতে নিচের পেজটি দেখুন।

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: 1.20.1 থেকে পাওয়া যাবে
