---
layout: post
title: การแทรกโค๊ด gist จาก Github (embedded gists) ลงบทความ
categories:
- Git
tags:
- embedded gist
- gist github
- github
- แทรกโค๊ด gist
- ใช้งาน gist
feature-image-url: http://farm9.staticflickr.com/8544/10238999894_22db4072b1_b.jpg
thumbnail: /img/logo/Octocat.jpg
summary: วิธีแทรกโค๊ด gist จาก Github (embedded gists) ลงบทความ เพื่อ highlight โค๊ดของเรา
---

พอดีตอนนี้นึกขึ้นได้ว่า **Github** มีบริการ **gist** นั่นคือบริการฝากโค๊ด **(snippets)** เลยลองใช้ซักหน่อย หลักจากทีแรก ใช้ตัว **Syntax Highlighter** ในการจัดการ โค๊ด syntax ภายในบทความ

วันนี้ก็เลยจะมาแนะนำวิธีการใช้ วิธีการเรียกไฟล์ วิธีการแทรก revision ของ gist นั้นๆกันครับ เผื่อจะมีประโยชน์กับใครหลายๆคน

***

## Step 1 : Getting Start

สำหรับใครไม่รู้จัก gist ว่าคืออะไร เข้าไปดูได้ที่นี่ครับ <a style="text-decoration:underline" href="https://gist.github.com/" target="_blank">https://gist.github.com/</a>

หน้าตาเมื่อเข้าไปแล้วก็จะประมาณนี้ครับ เราสามารถเพิ่มโค๊ดของเรา ใส่คำอธิบาย เลือกภาษาของโค๊ดได้ครับ

![How to embedded gist on website](http://farm3.staticflickr.com/2841/10239092466_48ede28c9c_z.jpg)

***

## Step 2 : Create new gist

ผมลองสร้าง gist ขึ้นมา 1 อัน  ลองสร้างด้วยภาษาจาวา ชื่อไฟล์ว่า `Hello.java` เพื่อสั่งให้พิมพ์ข้อความว่า "Hello gist" จากนั้นกด **Create Public Gist** (หากใครต้องการส่วนตัวก็สามารถสร้างแบบ Private ได้ครับ)

{% gist 5824856 Hello.java %}

เมื่อสร้างเสร็จ จะสังเกตเห็น หน้า gist detail ของเรา  หากต้องการแทรกโค๊ดไปในบทความพวก blogger wordpress หรือเว็บต่างๆ ก็เลือกที่ **Embed this gist** และก็อบโค๊ดมาวางครับ

![How to embedded gist on website](http://farm6.staticflickr.com/5327/10239185823_c96174af59_z.jpg)

ดังตัวอย่าง เช่น

```javascript
<script src="https://gist.github.com/Phonbopit/5824856.js"></script>
```

***

## Step 3 : Choose a revision

ตอนนี้ ก็สามารถแทรกโค๊ด ไปไว้ในบทความได้แล้ว แต่ว่า หาก gist นั้นๆ มีหลาย revision ละ มันก็จะโชว์เฉพาะ revision ล่าสุดเท่านั้น 
หากเราต้องการเจาะจง เฉพาะ revision ที่เราต้องการจะทำยังไงละ

ผมลองพิ่มไฟล์อีกไฟล์นึงชื่อ `Hello2.java` และแทรกโค๊ดใหม่ เพื่อให้มีอีก revision นึงเพิ่มมา

ผลลัพธ์ก็จะได้เป็น

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello gist");
    }
}
```

ต่อไป ถ้าผมไม่ต้องการแสดง revision ล่าสุด แต่ต้องการ revision แรก ที่มีแค่ Hello.java จะทำไง

กดที่ **Revision** ครับ แล้วเลือก **View gist@ .....** เลือก revision ที่ต้องการ

![How to embedded gist on website](http://farm9.staticflickr.com/8544/10238999894_22db4072b1_z.jpg)

สังเกต URL จะมีตัวอักษรเพิ่มมาเพียบ

![How to embedded gist on website](http://farm9.staticflickr.com/8267/10239092876_53960203b1_z.jpg)

ตัวนี้แหละ ที่เป็นตำแหน่งของ revision ของ gist อันนี้ที่เราสร้างไว้

ต่อไป นำอักษรที่อยู่ ใน url มาใส่แทน xxx ครับ

```javascript
<script src="https://gist.github.com/Phonbopit/5824856/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.js"></script>
```

***

## Step 4 : Show specific filename

สุดท้าย หากเรามีหลายๆไฟล์ ภายใน gist เดียวกัน จะทำยังไงให้โชว์เฉพาะ ไฟล์ที่เราต้องการ

ง่ายมากครับ เพิ่ม  `?file=filename`  ลงไปต่อท้าย **.js** เช่น

```javascript
<script src="https://gist.github.com/Phonbopit/5824856/xxxxxxxxxxxxxx.js?file=Hello.java"></script>
```
***

ถึงแม้เรื่องนี้อาจจะเป็นแค่เรื่องเล็กๆน้อยๆ แต่บางทีผมก็ลืมๆวิธีการใช้ เลยทำเป็นบทความไว้เตือนความจำ อย่างน้อยก็อาจจะมีประโยชน์กับผู้อื่นด้วยเช่นกัน

