---
layout: post
title: Command Line พื้นฐานสำหรับ Ubuntu มือใหม่
categories:
- Ubuntu
tags:
- command line
- terminal
- Ubuntu
recommended: true
feature-image-url: http://farm8.staticflickr.com/7445/10155114435_1ec6f32ba7_b.jpg
thumbnail: /img/logo/ubuntu.png
summary: รวบรวมคำสั่ง command line พื้นฐาน ที่ใช้งานบ่อยๆ สำหรับ Ubuntu มือใหม
---
#รวบรวมคำสั่ง command line พื้นฐาน ที่ใช้งานบ่อยๆ สำหรับ Ubuntu มือใหม่

***

## แสดงข้อมูลของระบบและ Kernel

```bash
uname -i
```
ใช้สำหรับแสดงรายละเอียดทั้งหมดของระบบ

```bash
df
```
ใช้สำหรับแสดงจำนวนพื้นที่ฮาดดิสท์

```bash
df -h
```
ใช้สำหรับแสดงจำนวนพื้นที่ฮาดดิสท์ โดยใช้หน่วย megabytes และ gigabytes

```bash
free
```
แสดงข้อมูล จำนวน memory ที่ใช

```bash
top
```
โชว์รายละเอียดทั้งหมด โปรเซสที่กำลังทำงาน cpu ram อื่นๆ (กด q เพื่อออก)

```bash
lsb_release -a
```
แสดงรายละเอียด linux ที่ใช้ เวอร์ชั่น และ โค๊ดเนม

***

## การจัดการ Process

```bash
ps aux
```
แสดง process ที่กำลังทำงานอย

```bash
ps aux | grep firefox
```
แสดงรายละเอียดโปรเซสของ firefox grep คือ regular expression โดยค้นหาโปรเซสชื่อ firefox 

```bash 
kill -9 pid
```
ปิดโปรเซส ตามไอดีที่ระบุ (ไอดีดูได้จาก ps aux)

```bash
killall name
```
ปิดโปรเซสของโปรแกรม name

***

## การจัดการโฟลเดอร์

```bash
cd
```
คำสั่งเปลี่ยน directory

```bash
cd /
```
เปลี่ยน directory ไปที่ root

```bash 
pwd
```
ใช้สำหรับแสดง directory ปัจจุบัน

```bash
cp
```
ใช้สำหรับก็อปปี้ ไฟล์/โฟลเดอร์

```bash
mkdir
```
ใช้สำหรับสร้างโฟลเดอร์

```bash
rmdir folder1
```
ลบโฟลเดอร์ folder1 (เฉพาะfolder ที่ไม่มีไฟล์ข้างใน)

```bash
rm -R folder1
```
ลบโฟลเดอร์ folder1 และไฟล์ข้างในทั้งหมด

***

## การจัดการไฟล์

```bash
touch file1.txt
```
สร้างไฟล์ file1.txt

```bash
file file1
```
แสดงนามสกุลของ file1

```bash 
cat file1.txt
```
แสดงรายละเอียดข้างใน file1.txt

```bash 
less file1.txt
```
เหมือนคำสั่ง cat แต่ต่างกันที่ สามารถเลื่อน scroll bar ได้

```bash
cp file1 file2
```
ก็อปปี้ file1 และสร้าง file2

```bash
rm file1 
```
ลบ file1

***

## ls Option 
ใช้สำหรับ แสดงรายชื่อไฟล์และโฟลเดอร์

```bash
ls
```
โชว์ไฟล์และโฟลเดอร์

```bash
ls -a
```

โชว์ไฟล์และโฟลเดอร์รวม hidden files ด้วย

```bash
ls -l
```
โชว์ลิสท์แบบยาว มีรายละเอียด permission รวมอยู่ด้วย

```bash 
ls -s
```
โชว์ลิสท์โดยเรียง จากขนาดของไฟล์และโฟลเดอร์

```bash
ls -t
```
เรียงตามวันที่แก้ไขล่าสุด

```bash
ls -1
```
โชว์ลิสท์รายชื่อ โดยเรียงบรรทัดละ 1 ชื่อ

```bash 
ls --color
```
แสดงรายชื่อ แบบมีไฮไลท์สี

***

## การจัดการ Package

```bash
sudo apt-get update
```
ทำการ update รายชื่อpackage ใน lists (เหมือนกับการ check update)

```bash 
sudo apt-get upgrade
```
ทำการ upgrade โปรแกรม ที่มีเวอร์ชั่นใหม่ ให้อัพเดท

```bash
sudo apt-get install packagename
```
ติดตั้งโปรแกรม

```bash
sudo apt-get -f install
```
สำหรับแก้ไข package ที่มีปัญหา กรณีเกิด "unmet dependences"

```bash
sudo apt-get remove name
```
ลบ package ชื่อname

```bash
sudo apt-get purge name
```
เหมือนกับ remove แต่จะลบ ไฟล์คอนฟิคด้วย

```bash
sudo add-apt-repository ppa:name
```
เพิ่ม repository (ต้องลง python-software-properties ก่อน)

***

## การจัดการ File Permission

```bash
chmod 775 file1
```
เปลี่ยนโหมดไฟล์เป็น 775

```bash
chmod 777 folder1
```
เปลี่ยน folder1 เป็น 777

```bash
chown user:group file1
```
เปลี่ยนสิทธิ์การเข้าถึงของ file1

***

## อื่นๆ

```bash
ifconfig
```
แสดงรายละเอียด network

```bash
nautilus 
sudo nautilus
```
ใช้สำหรับเปิด file manager (sudo เพื่อเปิดในฐานะ root)

```bash 
wget url_file
```
ดาวน์โหลดไฟล์ ตามที่ระบุใน url_file 

```bash
curl url_file
```
ดาวน์โหลดไฟล์ ตามที่ระบุใน url_file (แตกต่างจาก wget เล็กน้อย)

<div class="alert-info">
	รายละเอียด ความแตกต่างระหว่าง wget กับ curl อ่านได้ที่นี่<a href="http://daniel.haxx.se/docs/curl-vs-wget.html">wget vs curl</a>
</div>



***

**References : **
<p><a href="https://help.ubuntu.com/community/UsingTheTerminal" title="UsingTheTerminal" target="_blank">**UsingTheTerminal**</a>
<br><a href="https://help.ubuntu.com/10.04/basic-commands/C/" title="Using a command line" target="_blank">**Using a command line**</a></p>
