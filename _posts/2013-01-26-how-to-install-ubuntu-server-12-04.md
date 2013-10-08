---
layout: post
title: ขั้นตอนและวิธีติดตั้ง Ubuntu Server 12.04
categories:
- Ubuntu
tags:
- install ubuntu
- Ubuntu
- ubuntu server
- ติดตั้ง ubuntu server
feature-image-url: http://farm8.staticflickr.com/7350/9643585996_192f1a414b_b.jpg
thumbnail: /img/logo/ubuntu.png
summary: เนื่องด้วย ช่วงนี้ ต้องทำการติดตั้ง Ubuntu Server บ่อยครั้ง บางคนมีปัญหาขั้นตอนการติดตั้ง
---

**วันนี้จะมานำเสนอ วิธีการติดตั้ง Ubuntu Server 12.04 LTS กันครับ**

***

เนื่องด้วย ช่วงนี้ ต้องทำการติดตั้ง Ubuntu Server บ่อยครั้ง บางคนมีปัญหาขั้นตอนการติดตั้ง ไม่สามารถติดตั้งได้ หรือบางครั้งเสียเวลากับการติดตั้ง นานเกินไป  
จึงเกิดความคิด รวบรวมวิธีการติดตั้งขึ้นมา แสดงขั้นตอนการติดตั้ง มีรูปภาพประกอบ อธิบายแต่ละขั้นตอน เพื่อให้เข้าใจได้ง่าย และสามารถติดตั้งด้วยตนเองได้เลย


***
## ขั้นตอนการติดตั้ง
### Step 1 : เตรียมแผ่น DVD หรือ USB Flash Drive

สามารถ ดาวน์โหลดไฟล์ติดตั้ง ubuntu ที่เป็นนามสกุล .iso [**ได้ที่นี่**](http://www.ubuntu.com/download/server)
เมื่อได้ไฟล์ .iso ก็ทำการไรท์ใส่แผ่น DVD หรือ ใส่ใน USB Flash Drive

***

### Step 2 : เริ่มติดตั้ง Ubuntu

เมื่อใส่แผ่น DVD หรือ USB จะพบหน้าตา ดังรูป ให้ทำการเลือกภาษา
**English** จากนั้นกด **Enter**
![Ubuntu Server Installation 1](http://farm6.staticflickr.com/5547/9640349849_490b775e7c_z.jpg)
เลือก **Install Ubuntu Server**
![Ubuntu Server Installation 2](http://farm8.staticflickr.com/7350/9643585996_192f1a414b_z.jpg)
ต่อไปเลือกภาษาสำหรับระบบครับ เลือก **English - English** จากนั้นกด **Enter**
![Ubuntu Server Installation 3](http://farm4.staticflickr.com/3695/9643587594_34d235c533_z.jpg)

***

### Step 3 : เลือก Location

ทำการที่อยู่ Location ของเรานะครับ  ในส่วน **Country territory or area:** 
ให้เลือก **Others -> Asia -> Thailand**
![Ubuntu Server Installation 4](http://farm3.staticflickr.com/2863/9640351021_f4b678ae50_z.jpg)
![Ubuntu Server Installation 5](http://farm8.staticflickr.com/7383/9640350901_53cca2cce9_z.jpg)

***

### Step 4 : เลือกรูปแบบภาษา Locale

ขั้นตอนนี้จะทำการเลือก System Locale หรือรูปแบบของภาษาที่ใช้แสดง เช่น รูปแบบวันที่ 
เลือก **United States - en_US.UTF-8**  จากนั้นกด **Enter**
![Ubuntu Server Installation 6](http://farm4.staticflickr.com/3823/9640351145_c78c2319f2_z.jpg)

***

### Step 5 : เลือก Keyboard-Layout

ขั้นตอนนี้จะทำการเลือก Keyboard Layout ครับ  ระบบจะทำการค้นหา/ตรวจสอบ ให้อัตโนมัติ  
และขึ้นข้อความ **Detect Keyboard Layout ?**  เลือก **No**
![Ubuntu Server Installation 7](http://farm8.staticflickr.com/7284/9643587934_e279beac17_z.jpg)
ในช่อง **Country of origin for the keyboard:** เลือก **Thai -> Thai**
![Ubuntu Server Installation 8](http://farm8.staticflickr.com/7307/9643587820_db57a8f1b9_z.jpg)
![Ubuntu Server Installation 9](http://farm6.staticflickr.com/5515/9640351423_438cfa8f9e_z.jpg)
ในส่วนการตั้งคีย์เพื่อสลับภาษา **Method for toggling betwenn national and Latin mode:**
ให้คงค่าเดิมคือ **Alt+Shift**  ไว้เหมือนเดิม หรือใครอยากเปลี่ยนเป็นอย่างอื่นแล้วแต่สะดวกครับ  กด **Enter**
![Ubuntu Server Installation 10](http://farm8.staticflickr.com/7310/9640350729_7b1704ce40_z.jpg)

***

### Step 6 : Configure The Network

ระบบจะทำการ config DHCP สำหรับเครื่องที่ไม่ได้ต่อ LAN หรือ Network จะขึ้นให้ Configure Network
ทำการใส่ชื่อ Hostname ที่ต้องการตั้ง จากนั้นกด **Enter**
![Ubuntu Server Installation 11](http://farm6.staticflickr.com/5512/9643586620_ba728c6735_z.jpg)

***

### Step 7 : Setup Users and Passwords

ในช่อง **Full Name for the new user:**  ใส่ชื่อที่ต้องการ จากนั้นกด **Enter**
![Ubuntu Server Installation 12](http://farm3.staticflickr.com/2809/9643584758_7cd4acb9d4_z.jpg)
ต่อไปทำการเลือก ยูเซอร์เนมที่ใช้ล็อคอินครับ  
ในช่อง **Username for your account:**  ให้ใส่ยูเซอร์เนม (ขึ้นต้นด้วยตัวพิมพ์เล็ก)  จากนั้นกด **Enter**
![Ubuntu Server Installation 13](http://farm4.staticflickr.com/3686/9640348155_3074ee3a0b_z.jpg)
จากนั้นทำการใส่พาสเวิร์ด
![Ubuntu Server Installation 14](http://farm3.staticflickr.com/2873/9640348053_2be8b4e828_z.jpg)
ยืนยันพาสเวิร์ดอีกครั้งครับ
![Ubuntu Server Installation 15](http://farm8.staticflickr.com/7352/9640347943_c93fd59e53_z.jpg)
หากพาสเวิร์ดมีความยาวน้อยกว่า 8 ตัวอักษร ระบบจะขึ้นเตือน
![Ubuntu Server Installation 16](http://farm6.staticflickr.com/5330/9640348379_d31fd1c09d_z.jpg)
ขั้นตอนนี้จะเป็นการถามว่า **Encrypt your home directory**
จะเข้ารหัสข้อมูลที่เก็บใน Home หรือเปล่า ให้เลือก **No** แล้วกด **Enter** ครับ
![Ubuntu Server Installation 17](http://farm8.staticflickr.com/7418/9643584346_ba4174b2da_z.jpg)

***

### Step 8 : Configure the clock

ระบบจะทำการค้นหาและเปรียบเทียบเวลาจาก Server ให้เรา และได้ Timezone คือ **Asia/Bangkok** Is this timezone correct?
เลือก **Yes** จากนั้นกด **Enter**
![Ubuntu Server Installation 18](http://farm6.staticflickr.com/5474/9640350221_15718fca8b_z.jpg)

***

###	Step 9 : Setup Partition Disks

เลือก **Guided – use entire disk and set up LVM**
<div class="alert alert-success">
	อันนี้เป็นการเลือก disk สำหรับ disk ที่ไม่มีข้อมูลนะครับ  ถ้าหากใครลง windows อยู่ ก็เลือก แบบ Manual ครับ ไม่งั้นข้อมูลอาจหายได้
</div>

![Ubuntu Server Installation 19](http://farm4.staticflickr.com/3704/9640349155_a287fede35_z.jpg)
จากนั้นก็เลือก partition ครับ  ในรูปเป็น haddisk จาก virtual box ครับ
![Ubuntu Server Installation 20](http://farm6.staticflickr.com/5443/9640349039_c353a6bc68_z.jpg)
จะมีข้อความบอก รายละเอียด ถ้าหากตกลง ก็เลือก **Yes** แล้วกด **Enter**
![Ubuntu Server Installation 21](http://farm3.staticflickr.com/2891/9643585388_ebc698e9a3_z.jpg)
ตัวนี้แสดงเมื่อเราเลือก แบบ **Guided – use entire disk and set up LVM**
โดยระบบจะให้เราระบุ พื้นที่ของ partition ลงไป โดย default คือค่า  max อยู่แล้ว 
หากไม่ต้องการเปลี่ยนก็เลือก **Continue**
![Ubuntu Server Installation 22](http://farm8.staticflickr.com/7314/9643585226_405e59dccf_z_d.jpg)
ระบบจะขึ้นข้อความยืนยันว่าเราทำการเปลี่ยนแปลง disk เลือก **Yes**
![Ubuntu Server Installation 23](http://farm8.staticflickr.com/7344/9640348613_17c7fa53cc_z.jpg)
รอการติดตั้งประมาณ 2นาที
![Ubuntu Server Installation 24](http://farm4.staticflickr.com/3689/9643584948_0762c22ae7_z.jpg)

***

### Step 10 : Configure the package manager

ในขณะที่ทำการติดตั้ง จะมีข้อความขึ้นมาให้ใส่คอนฟิก HTTP proxy 
อันนี้ปล่อยไว้ ไม่ต้องใส่อะไร จากนั้นกด **Enter**
![Ubuntu Server Installation 25](http://farm3.staticflickr.com/2828/9643588086_aba5ef25e8_z.jpg)
เลือกเป็น **No automatic Update**  เพื่อไม่ต้องการอัพเดทขณะทำการติดตั้ง
![Ubuntu Server Installation 26](http://farm6.staticflickr.com/5347/9643586382_5bef360d34_z.jpg)
ทำการเลือก Software ที่ต้องการโดย กด **Spacebar** เพื่อเลือก เมื่อเลือกเรียบร้อยแล้ว ให้กด **Enter**
สามารถ Install ในภายหลังได้เหมือนกัน
![Ubuntu Server Installation 27](http://farm6.staticflickr.com/5548/9640347723_f7b5beaf18_z.jpg)
ใส่รหัส MySQL Server (เนื่องจากเลือก install LAMP ซึ่งประกอบด้วย (Linux, Apache, MySQL, PHP) )
![Ubuntu Server Installation 28](http://farm4.staticflickr.com/3676/9643586830_d046694b62_z.jpg)
ยืนยันรหัสอีกครั้ง
![Ubuntu Server Installation 29](http://farm6.staticflickr.com/5495/9643586724_fa1c78becf_z.jpg)
ขณะติดตั้ง จะมีข้อความขึ้นมาถาม ว่าต้องการติดตั้ง **GRUB boot loader**  หรือไม่ ตอบ **Yes**
![Ubuntu Server Installation 30](http://farm3.staticflickr.com/2876/9640351861_555e8f7464_z.jpg)

***

### Step 11 : เสร็จสิ้นการติดตั้ง

ระการติดตั้งและคอนฟิคระบบ
![Ubuntu Server Installation 31](http://farm8.staticflickr.com/7437/9640349559_f076acc6bd_z.jpg)
เมื่อเสร็จสิ้นการติดตั้ง เลือก **Continue** เพื่อรีสตาร์ทเครื่อง
![Ubuntu Server Installation 32](http://farm3.staticflickr.com/2870/9640349943_0983f0562c_z.jpg)

***

### Step 12 : ทดสอบล็อคอิน และอัพเดทเวอร์ชั่น

ตอนนี้เราได้ทำการติดตั้ง Ubuntu Server เสร็จแล้วนะครับ
ต่อไปจะเป็นการทดสอบ การ login และการ update system

เมื่อเครื่องรีสตารท์ขึ้นมา  จะได้หน้าจอดังรูป
ทดสอบ login โดยการใช้ username password ที่ได้ตั้งไว้
![Ubuntu Server Installation 33](http://farm4.staticflickr.com/3720/9643585650_5c754acfce_z.jpg)

ระบบจะโชว์ข้อความต้อนรับ และมีรายละเอียดต่างๆโชว์อยู่ ดังรูป
![Ubuntu Server Installation 34](http://farm6.staticflickr.com/5487/9643585820_9301c6b274_z.jpg)

ทำการตรวจสอบการ update ระบบของ Ubuntu

```bash
sudo apt-get update
```

![Ubuntu Server Installation 35](http://farm8.staticflickr.com/7313/9640347615_2099f078e2_z.jpg)

จากนั้นก็ทำการ upgrade ระบบครับ

```bash
sudo apt-get upgrade
```

โดยจะขึ้นข้อความให้เรากดยืนยัน โดยพิมพ์ y จากนั้นกด **Enter**
![Ubuntu Server Installation 35](http://farm4.staticflickr.com/3820/9643583824_7bd04de817_z.jpg)

เสร็จสิ้นการติดตั้ง

***
