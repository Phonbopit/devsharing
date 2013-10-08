---
layout: post
title: ติดตั้ง Aptana Studio 3 บน Ubuntu 12.10
categories:
- Ubuntu
tags:
- aptana
- aptana studio
- Ubuntu
- rails
- ruby on rails
feature-image-url: http://farm8.staticflickr.com/7291/9738527009_c7d38bb5c0_b.jpg
thumbnail: /img/logo/aptana.png
summary: Aptana Studio 3 นั้นเป็น IDE ยอดนิยมตัวนึง โดยมีทั้งเวอร์ชั่น Standalone และแบบที่เป็น plugin ภายใน Eclipse ซับพอร์ตทั้ง html, css, javascript, Python, PHP และ Ruby on Rails ที่มี Terminal และ Git รวมอยู่ด้วยครับ
---

Aptana Studio 3 นั้นเป็น IDE ยอดนิยมตัวนึง โดยมีทั้งเวอร์ชั่น Standalone และแบบที่เป็น plugin ภายใน Eclipse ซับพอร์ตทั้ง html, css, javascript, Python, PHP และ Ruby on Rails ที่มี Terminal และ Git รวมอยู่ด้วยครับ

***

สำหรับผมเน้นใช้งาน Ruby on Rails ซื่งเมื่อก่อนเป็น RadRails ได้ถูกนำมารวมอยู่ใน Studio 3 แล้วครับ  ส่วน Perspective แบบ Rails จะไม่มีแล้ว จะเป็น แบบ Web(Default) แทนครับ

***

พร้อมแล้วไปดาวน์โหลดและติดตั้งกันเลยครับ <a href="http://www.aptana.com/products/studio3" target="_blank">Aptana Studio 3
</a>

![Aptana Download](http://farm8.staticflickr.com/7291/9738527009_c7d38bb5c0_z.jpg)

สำหรับการติดตั้ง Aptana Studio 3 จะมีด้วยกัน 2 เวอชั่นคือ 
1. เป็นเวอชั่น **plugin ภายใน Eclipse** และ 2. เวอชั่น **Standalone** คือแยกตัวออกมาจาก Eclipse

***

## เวอร์ชั่น Eclipse Plugin

[1.] เปิด **Eclipse**  เลือก **Help** -> **Install New Software..**

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7336/9738527527_3ae4688a39_o.png)

***

[2.] คลิ๊ก **Add**

**Name :** ใส่เป็น Aptana Plugin หรือชื่อที่อยากตั้ง

**Location :** http://download.aptana.com/studio3/plugin/install

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7395/9738526411_b1c308701f_z.jpg)

***

[3.] จะเห็น plugin ชื่อ **Aptana Studio** ติ๊กถูกที่ **Aptana Studio 3** 

จากนั้น คลิ๊ก **Next - > Next **

เลือก **accept the terms of the license agreement** เมื่อ install เสร็จทำการ restart eclipse 

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7317/9738526609_61363490ab_z.jpg)

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7340/9738527701_264869436a_z.jpg)

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7425/9740736392_ea179577af_z.jpg)

***

[4.] หลังจาก restart เมื่อเปิดขึ้นมา จะเห็น Aptana Studio สามารถสร้าง Project Ruby ได้แล้ว

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7371/9738527377_d597d736bf_z.jpg)

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7427/9740734900_64e9b1d23a_z.jpg)

***

## เวอร์ชั่น Standalone

เมื่อดาวน์โหลดเสร็จจะได้ไฟล์ ชื่อ **Aptana_Studio_3_Setup_Linux_x86_64_3.x.x.zip**
[1.] ทำการ extract file ออกมา จาก directory ที่ดาวน์โหลดมา สมมติอยู่ที่ user/Downloads

```bash
cd /home/devsharing/Downloads
unzip Aptana_Studio_3_Setup_Linux_x86_64_3.x.x.zip
```

***

[2.] ย้ายไปไว้ที่ /opt

```bash
sudo mv Aptana_Studio_3 /opt/
```

***

[3.] เพิ่ม Permission เป็น root

```bash
cd /opt/
sudo chown -R root:root Aptana_Studio_3
sudo chmod -R +r Aptana_Studio_3
```

***

[4.] สร้าง Icon ให้โชว์ที่ Dash Home
สำหรับเปิดด้วย Sublime text 2

```bash
sudo subl /usr/share/applications/aptana3.desktop
```

สำหรับเปิดด้วย Text Editor

```bash
sudo gedit /usr/share/applications/aptana3.desktop
```

ก็อบคำสั่งด้านล่างนี้ลงไป กดเซฟ
```bash
[Desktop Entry]
Version=3
Encoding=UTF-8
Type=Application
Exec=/opt/Aptana_Studio_3/AptanaStudio3
Name=Aptana Studio 3
Comment=Aptana Studio 3 with RadRails Standalone Version.
Icon=/opt/Aptana_Studio_3/aptana-icon.png
Categories=Application;Development;
Terminal=false
StartupNotify=true
```

Exec : รันโปรแกรม ตามpathที่อยู่ที่ระบุไว้ 
Icon : เซ็ทตำแหน่งที่ใช้สำหรับ icon

***

[5.] Run Aptana 

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7352/9740735426_83c89f6520_o.png)

![How to install Aptana Studio3 on Ubuntu](http://farm8.staticflickr.com/7429/9738527261_6733feb026_z.jpg)

***
