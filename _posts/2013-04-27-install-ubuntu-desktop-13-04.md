---
layout: post
title: ขั้นตอนการติดตั้ง Ubuntu 13.04 Desktop
categories:
- Ubuntu
tags:
- install ubuntu
- Ubuntu
- ubuntu 13.04
- ติดตั้ง ubuntu
recommended: true
feature-image-url: http://farm6.staticflickr.com/5460/9664111803_3cde4a2b6e_b.jpg
thumbnail: http://farm6.staticflickr.com/5512/9664118503_948341d7bf_z.jpg
summary: วิธีการติดตั้ง Ubuntu 13.04 Desktop สำหรับมือใหม่ ที่อยากลองใช้งาน Ubuntu

---
**ตอนนี้ Ubuntu 13.04 ก็ได้ออกมาแล้ว
วันนี้ก็เลยจะมานำเสนอ วิธีการติดตั้ง Ubuntu 13.04 Desktop สำหรับมือใหม่ที่อยากลองใช้ Ubuntu ครับ**

<!--more--> 

***
## ขั้นตอนการติดตั้ง
### Step 1 : เตรียมแผ่น DVD หรือ USB Flash Drive

สามารถ ดาวน์โหลดไฟล์ติดตั้ง ubuntu ที่เป็นนามสกุล .iso [ได้ที่นี่](http://www.ubuntu.com/download/desktop)
เมื่อได้ไฟล์ .iso ก็ทำการไรท์ใส่แผ่น DVD หรือ ใส่ใน USB Flash Drive

***

### Step 2 : Install Ubuntu

เมื่อใส่แผ่น DVD หรือ USB เมื่อเข้าหน้าจอดังรูป ให้กด แป้นพิมพ์บนคีย์บอร์ด (อะไรก็ได้)

<div class="alert alert-success">
    ตัวอย่างใช้การติดตั้งผ่าน VirtualBox 4.2.4 บน Ubuntu 12.10
</div>

![Ubuntu 13.04 Installation 0](http://farm6.staticflickr.com/5335/9667432532_cbdf7c97bc_z.jpg)
จากนั้นเลือกภาษา ปกติผมติดตั้งด้วยภาษาอังกฤษ แต่ตัวอย่างขอใช้เป็นภาษาไทยสำหรับมือใหม่ให้สามารถอ่านและเข้าใจได้ง่ายครับ
![Ubuntu 13.04 Installation 1](http://farm4.staticflickr.com/3698/9664102131_26c70e1b5a_z.jpg)
เมื่อเลือกภาษาแล้ว ก็กด **Install Ubuntu**
![Ubuntu 13.04 Installation 2](http://farm4.staticflickr.com/3673/9667334250_632f3ecedf_z.jpg)

***

### Step 3 : Welcom Screen

![Ubuntu 13.04 Installation 3](http://farm4.staticflickr.com/3737/9667335702_bc8968d962_z.jpg)
เตรียมตัวติดตั้ง ขั้นตอนนี้จะทำการเช็คระบบ ว่าเครื่องของเราสามารถ ติดตั้ง Ubuntu ได้หรือไม่
![Ubuntu 13.04 Installation 4](http://farm4.staticflickr.com/3727/9667336852_c8a9748644_z.jpg)
เลือก ลบดิสก์และติดตั้ง Ubuntu หรือหากใครใช้ Windows 7 อยู่ก็เลือก ติดตั้งร่วมกับ windows
![Ubuntu 13.04 Installation 5](http://farm3.staticflickr.com/2843/9664106153_b0a6f2c040_z.jpg)

***

### Step 4 : Setting up

ทำการเลือกสถานที่ที่อยู่ของเรา โดยปกติระบบจะค้นหาที่อยู่อัตโนมัติให้อยู่แล้ว สามารถเลือกหรือเปลี่ยนได้
![Ubuntu 13.04 Installation 6](http://farm8.staticflickr.com/7288/9667339492_ef64678c29_z.jpg)
ทำการเลือก keyboard layout หรือจะทดสอบโดยการพิมพ์ข้อความและตรวจหาผังแป้นพิมพ์ ก็ได้
![Ubuntu 13.04 Installation 7](http://farm4.staticflickr.com/3768/9664108757_638b147aee_z.jpg)
ทำการกำหนด ยูเซอร์เนม ชื่อคอมพิวเตอร์ของคุณ
![Ubuntu 13.04 Installation 8](http://farm3.staticflickr.com/2841/9667341854_89352d7fef_z.jpg)

***

### Step 5 : Installing System
ระบบกำลังติดตั้ง จะมีรูป preview ให้ดูระหว่างรอได้ครับ
![Ubuntu 13.04 Installation 9](http://farm6.staticflickr.com/5460/9664111803_3cde4a2b6e_z.jpg)
![Ubuntu 13.04 Installation 10](http://farm6.staticflickr.com/5517/9664113633_eeee61afc2_z.jpg)

***

### Step 6 : Installation Complete

เมื่อทำการติดตั้งเสร็จเรียบร้อยแล้ว ก็กด **Restart now**
![Ubuntu 13.04 Installation 11](http://farm6.staticflickr.com/5338/9664116307_ce9e82ec6d_z.jpg)

***

### Step 7 : First Login

ทำการเข้าสู่ระบบ โดยใส่ยูเซอร์เนมและพาสเวิร์ดที่ได้ตั้งไว้ตอนติดตั้ง
![Ubuntu 13.04 Installation 12](http://farm6.staticflickr.com/5512/9664118503_948341d7bf_z.jpg)

***

### Step 8 : Update &amp; Upgrade

ทำการ update และ upgrade ด้วย Terminal *Ctrl + Alt + T*

```bash
sudo apt-get update
sudo apt-get upgrade
```

![Ubuntu 13.04 Installation 14](http://farm4.staticflickr.com/3807/9667353346_371bfa7e17_z.jpg)

***

###Step 9 : Tour

รายละเอียดของระบบ
![Ubuntu 13.04 Installation 13](http://farm3.staticflickr.com/2848/9664119955_8dbb50f4bf_z.jpg)
Nautilus รูปแบบใหม่
![Ubuntu 13.04 Installation 15](http://farm8.staticflickr.com/7337/9664122481_1fa8c011a6_z.jpg)
หน้า Online Account
![Ubuntu 13.04 Installation 16](http://farm6.staticflickr.com/5522/9667355372_2140302bea_z.jpg)
หน้า Online Account Authentication
![Ubuntu 13.04 Installation 17](http://farm8.staticflickr.com/7355/9667356342_0d79a398a7_z.jpg)
Unity รูปแบบใหม่
![Ubuntu 13.04 Installation 18](http://farm3.staticflickr.com/2871/9667356646_8e54e22857_z.jpg)
Libre Office ใหม่ เวอร์ขั่น 4.0
![Ubuntu 13.04 Installation 19](http://farm3.staticflickr.com/2871/9664125257_a543f8ea13_z.jpg)
สุดท้าย หน้า **log out** กับ **Shut Down** รูปแบบใหม่
![Ubuntu 13.04 Installation 20](http://farm4.staticflickr.com/3702/9667359266_b5a66265ed_z.jpg)

***