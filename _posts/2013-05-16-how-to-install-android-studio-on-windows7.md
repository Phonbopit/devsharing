---
layout: post
title: ขั้นตอนการติดตั้ง Android Studio บน Windows 7
categories:
- Android
tags:
- Android
- android sdk
- android studio
- java_home
- ติดตั้ง android
recommended: true
feature-image-url: http://farm4.staticflickr.com/3691/9858653995_4634a1afbc_b.jpg
thumbnail: /img/logo/adt.png
---
หลังจากเมื่อคืนนี้ (15 พฤษภาคม 2556) ทาง Google ได้มีการเปิดตัว  **Android IDE** ตัวใหม่ ที่งาน Google I/O 2013 ครับ

โดยตัว Android IDE ตัวใหม่นี้ มีชื่อว่า Android Studio ซึ่งมีฐานมาจาก **InteliJ IDEA** ทาง Google บอกว่ามันทำงานได้รวดเร็วยิ่งขึ้น และมี features ใหม่ๆเข้ามา เช่นการพรีวิว รูปภาพ ที่อ้างอิงจากไฟล์อื่นได้ และสามารถดูภาพรวมหน้าจอของ application ให้เห็นผลได้ทันทีที่แก้ไขไฟล์ xml เลย  
แต่ว่าตัวนี้ ยังคงเป็น เวอร์ชั่น Early Access เป็นแค่พรีวิวเท่านั้น features บางอย่างยังไม่สมบูรณ์

![How to install android studio on window 7](http://farm4.staticflickr.com/3775/9858642804_b2571a0704.jpg)

***

## Step 1 : Download Android Studio

ทำการดาวน์โหลด <a href="http://developer.android.com/sdk/installing/studio.html" target="_blank">Android Studio</a> 
เลือก Windows 32bit หรือ 64bit เมื่อดาวน์โหลดเสร็จเรียบร้อยแล้ว ก็จะได้ไฟล์ .exe ทำการติดตั้ง

![How to install android studio on window 7](http://farm8.staticflickr.com/7406/9858657694_b217107fdc.jpg)

![How to install android studio on window 7](http://farm4.staticflickr.com/3798/9858750633_42c0d8e6f8.jpg)

![How to install android studio on window 7](http://farm6.staticflickr.com/5510/9858750183_4e5c2f974f.jpg)

เมื่อ ติดตั้งเสร็จ ทำการ start

<div class="alert alert-error">
หากใครไม่สามารถ Start Android Studio ได้ ให้ทำการเซ็ทอัพ JAVA_HOME 
</div>

***

## Step 2 : Setting JAVA_HOME

ทำการ Set Java Home โดยคลิกขวาที่ **My Computer** -> **Properties** -> **Advanced System Settings**

![How to install android studio on window 7](http://farm8.staticflickr.com/7372/9858663555_252a08b218_z.jpg)

จากนั้น คลิ๊กที่ **Environment Variable**

ในส่วน **System Variable** ทำการเพิ่ม **JAVA_HOME** โดยการ คลิ๊กที่ **New..**

Variable Name : ใส่ **JAVA_HOME**

Variable value : ใส่ path ของ java 

path ของ java โดยค่ามาตรฐานจะอยู่ที่ `C:\Program Files\Java\jdk1.7.0_xx`

<div class="alert alert-error">
หากไม่ได้ติดตั้ง java jdk สามารถดาวน์โหลดได้ที่ <a style="color:red;font-weight:bold;" href="http://www.oracle.com/technetwork/java/javase/downloads/index.html" target="_blank">Java SDK Download</a>
</div>

![How to install android studio on window 7](http://farm4.staticflickr.com/3763/9858746353_15c5084131_b.jpg)

เมื่อตั้งค่า JAVA_HOME เสร็จเรียบร้อยแล้ว  สั่ง Start Android Studio ใหม่อีกครั้ง จะได้หน้าตา Welcome to Android Studio ดังภาพ

![How to install android studio on window 7](http://farm6.staticflickr.com/5517/9858665365_15059fab8f_z.jpg)

![How to install android studio on window 7](http://farm8.staticflickr.com/7395/9858655074_c035e2c622_z.jpg)

***

## Step 3: New Project

ทำการลองสร้าง New Project เพื่อทดสอบว่าใช้งานได้หรือไม่

<div class="alert alert-error">
หากมีปัญหา SDK Problem : Your Android SDK is out of date or is missing templates. Please ensure you are using SDK version 22 or later.
ให้ทำการ <a href="#config">Configure Project</a>
</div>

![How to install android studio on window 7](http://farm6.staticflickr.com/5326/9858658955_7c7d2500df_z.jpg)

![How to install android studio on window 7](http://farm4.staticflickr.com/3749/9858742763_936485d3e0_z.jpg)

![How to install android studio on window 7](http://farm8.staticflickr.com/7451/9858742073_af05b850af_z.jpg)

![How to install android studio on window 7](http://farm4.staticflickr.com/3823/9858675396_6aca42ed63_z.jpg)

***

## Step 4 : Create new AVD

ขั้นตอนนี้จะทำการสร้าง Emulator เพื่อมาทดสอบ ว่าสามารถรัน android emulator ได้หรือไม่
ก่อนจะสร้าง Emulator เราจะทำการ install **Intel x86 System Image** กันก่อน 

โดยไปที่  **Tools** -> **Android** -> **SDK Manager** 

เพื่อทำการติดตั้ง **Intel x86 Atom System Image** ตัวนี้จะทำให้ลืม Emulator ที่ช้าไปได้เลย เพราะมันจะทำงานได้เร็วเทียบเท่ากับ เครื่องจริงเลยทีเดียว

![How to install android studio on window 7](http://farm8.staticflickr.com/7308/9858674566_88320f9e11_c.jpg)

จากนั้นสร้าง new AVD โดยเลือก **Tools** -> **Android** -> **AVD Manager** กำหนดชื่อ device และ target ตามต้องการ และอย่าลืม เลือก **CPU/ABI** เป็น **Intel Atom(x86)** ที่เราโหลดมาเมื่อกี้  เพื่อติดสปีดให้กับ emulator ครับ

![How to install android studio on window 7](http://farm6.staticflickr.com/5509/9858654995_eeb1b7f548_z.jpg)

***

## Step 5 : Running Emulator

สั่งรัน โปรแกรมครับ  ระบบจะขึ้นมาให้เลือก หากเราเสียบสาย usb ระบบก็จะขึ้น device ของเครื่องจริง มาให้เลือก 
ในตัวอย่าง ไม่ได้เสียบ usb ฉะนั้น จึงใช้ตัว emulator เลือก emulator Emu4.2 แล้วกด OK

![How to install android studio on window 7](http://farm8.staticflickr.com/7315/9858738693_6eebb8feeb.jpg)

Emulator แสดงผลได้ปกติครับ  

![How to install android studio on window 7](http://farm4.staticflickr.com/3691/9858653995_4634a1afbc_z.jpg)

***

<h2 id="config">Configure Project</h2>

หากใครที่กด **New Project..** แล้วประสบปัญหา <strong style="color:red;">android sdk is out of date.</strong> 
แบบในรูป สามารถแก้ไขได้โดยการ ตั้งค่าที่ project ครับ

![How to install android studio on window 7](http://farm8.staticflickr.com/7363/9858748073_42b6c7726a_z.jpg)

โดยเลือก ที่ **Configure** -> **Project Default** -> **Project Structure**

![How to install android studio on window 7](http://farm4.staticflickr.com/3745/9858651184_f722229046_z.jpg)

![How to install android studio on window 7](http://farm6.staticflickr.com/5495/9858678686_b258bc6986_z.jpg)

![How to install android studio on window 7](http://farm8.staticflickr.com/7290/9858660085_8a693ab359_z.jpg)

ในส่วน **Built Target** ให้ทำการเลือกเป็น **Android 4.2.2**

![How to install android studio on window 7](http://farm8.staticflickr.com/7428/9858650074_ab27a24abf_z.jpg)

***

หวังว่าบทความนี้ จะเป็นประโยชน์ไม่มากก็น้อย ขอให้สนุกกับการเขียนโปรแกรมนะครับ

***

**Reference : **

<a href="http://stackoverflow.com/questions/16574189/android-studio-installation-on-windows-7-fails-no-jdk-found" target="_blank">
	Android Studio installation on Windows 7 fails, no JDK found
</a>
