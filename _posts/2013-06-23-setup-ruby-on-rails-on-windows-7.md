---
layout: post
title: Setup Ruby on Rails บน Windows 7
categories:
- Ruby-On-Rails
tags:
- ruby
- rails
- rails windows7
- railsinstaller
- ruby on rails
recommended: true
feature-image-url: http://farm8.staticflickr.com/7410/9737345084_1aa0d74f72_o.png
thumbnail: /img/logo/ror.png
summary: ขั้นตอนและวิธีการติดตั้ง Ruby on Rails บน Windows 7

---
หลังจาก เคยลงบทความ <a href="http://devsharing.com/2013/ruby-on-rails/setup-ruby-on-rails-in-ubuntu/" target="_blank">การติดตั้งบน Ruby on Rails บน Ubuntu</a>  มาแล้ว  วันนี้เลยจะมานำเสนอวิธีการติดตั้ง **Ruby on Rails** บน **Windows 7** ในตัวอย่างนี้ใช้จำลอง **Windows 7 ผ่าน VirtualBox** นะครับ ซึ่งพอลองดูแล้ว การติดตั้ง ง่ายกว่าบน **Ubuntu**มาก  มาดูขั้นตอนการติดตั้งกันครับ

***

## Step 1 : Download RailsInstaller

**RailsInstaller** คือโปรแกรมที่รวบรวม ทั้ง Ruby pack, sqlite , Rails3, git ต่างๆไว้ในโปรแกรมเดียว( หากนึกไม่ออก นึกถึง Appserve หรือ WampServer ก็คือคล้ายๆกัน คือ รวม mysql, php, apache ไว้ใน package เดียวกัน ) เพียงแค่ ดาวน์โหลดและติดตั้ง ก็สามารถเขียน Ruby บนเครื่องได้แล้ว (ง่ายกว่า <a href="http://devsharing.com/2013/ruby-on-rails/setup-ruby-on-rails-in-ubuntu/" target="_blank">การติดตั้งบน Ubuntu</a> เยอะเลย)

สามารถดาวน์โหลดได้ที่เว็บไซต์ <a href="http://railsinstaller.org/" target="_blank">http://railsinstaller.org/</a> หรือ <a href="http://rubyforge.org/frs/download.php/76862/railsinstaller-2.2.1.exe" >ดาวน์โหลด RailsInstaller ที่นี่</a>

***

## Step 2 : Install RailsInstaller

ทำการติดตั้ง RailsInstaller เมื่อติดตั้งเรียบร้อย ทำการ set up git
![Setup Ruby on Rails on Windows 7](http://farm8.staticflickr.com/7410/9737345084_1aa0d74f72_o.png)
![Setup Ruby on Rails on Windows 7](http://farm8.staticflickr.com/7437/9737345480_a58a4a75e2_o.png)

***

## Step 3 : Setup Git

ทำการ setup ชื่อและอีเมล์ เมื่อเสร็จจะได้ดังรูป
![Setup Ruby on Rails on Windows 7](http://farm8.staticflickr.com/7400/9734110445_795b7ddee1_z.jpg)

check Version Rails และ Ruby ด้วยคำสั่ง

```bash
rails -v
ruby -v
```

![Setup Ruby on Rails on Windows 7](http://farm8.staticflickr.com/7373/9734111199_5264e40108_z.jpg)

***

## Step 4 : Create new Rails Project

ทดสอบ สร้าง Rails โปรเจคครับ

```bash
rails new rails_app
```

เมื่อ Rails generate โปรเจ็คเสร็จแล้ว จะได้ผลลัพธ์ดังภาพ

```bash
create
create README.rdoc
create Rakefile
.
.
.
Your bundle is complete!
```

ลองสั่งรัน server ครับ

```bash
cd rails_app
rails server
```

ทดสอบ เข้า URL <a href="http://0.0.0.0:3000/" target="_blank">http://0.0.0.0:3000/</a> หรือ <a href="http://localhost:3000/" target="_blank">http://localhost:3000/</a> 

![Setup Ruby on Rails on Windows 7](http://farm8.staticflickr.com/7336/9734111037_84d45fcd36_z.jpg)

เสร็จแล้วครับ สำหรับวิธีการติดตั้ง Ruby on Rails บน Windows 7 ใช้แค่ RailsInstaller ตัวเดียว ก็ติดตั้งได้หมดเลย

