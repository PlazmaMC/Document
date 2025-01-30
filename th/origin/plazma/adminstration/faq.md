---
description: เรียนรู้เกี่ยวกับคำถามที่ถามบ่อย
---

# ⁉️ คำถามที่ถามบ่อย

{% hint style="info" %}

### ไม่พบคำตอบที่คุณต้องการหรือไม่

สอบถามคำถามในชุมชนผ่าน [เซิร์ฟเวอร์ Discord อย่างเป็นทางการ](https://discord.gg/MmfC52K8A8) หรือ [GitHub Issues](https://github.com/PlazmaMC/PlazmaBukkit/issues) นะคะ!
{% endhint %}

### ไม่สามารถดำเนินการได้พร้อมข้อความที่ปรากฏ

หากมีข้อความ `no main manifest attribute, in plazma-(version).jar` ปรากฏในคอนโซล\
ไฟล์ที่ดาวน์โหลดเป็นไฟล์ API สำหรับการพัฒนา คุณต้องดาวน์โหลด **Reobf Paperweight** จากหน้า GitHub

ดูข้อมูลเพิ่มเติมได้ที่หน้าต่อไป

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### คำเตือนปรากฏทุกครั้งที่เซิร์ฟเวอร์เริ่มทำงาน

Plazma มีการแก้ไขบางส่วนที่ไม่เสถียรและมีโอกาสในการทำงานผิดพลาดเสมอ ดังนั้น ข้อความคำเตือนต่อไปนี้จะปรากฏเมื่อเซิร์ฟเวอร์เริ่มทำงาน

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

คำเตือนนี้สามารถปิดการใช้งานได้ด้วยคุณสมบัติระบบ [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1]

ดูข้อมูลเพิ่มเติมได้ที่หน้าต่อไป

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: สามารถใช้งานตั้งแต่เวอร์ชัน 1.20.1
