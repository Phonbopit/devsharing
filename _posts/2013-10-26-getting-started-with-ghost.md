---
layout: post
title: มารู้จัก Ghost, Blogging Platform น้องใหม่กันดีกว่า
categories:
- Ghost
tags:
- ghost
- nodejs
- install ghost
feature-image-url: http://phonbopit.com/content/images/2013/Oct/getting_started_with_ghost_1.png
thumbnail: /img/logo/ghost.png
summary: ขั้นตอนและวิธีการติดตั้ง Java JDK และ Java JRE บน Ubuntu

---


[**Ghost**](http://ghost.org) คือ Bloggin Platfrom น้องใหม่ที่เปิดตัวมาจากการระดมทุนที่ [Kickstarter](http://www.kickstarter.com/projects/johnonolan/ghost-just-a-blogging-platform) ซึ่งตัว Ghost นั้นทำงานด้วย javascript บน [**node.js**](http://nodejs.org) นั่นเอง 

Ghost เป็นโอเพ่นซอร์ส แอพพลิเคชั่น ที่ช่วยให้การเขียนบล็อคของคุณสนุกขึ้น มีเครื่องมือใช้งานง่าย ดีไซน์ที่ค่อนข้างสวยงาม ใช้ Markdown ในการเขียนบทความ ฐานข้อมูลใช้ sqlite กับ mysql 

วันนี้จะมานำเสนอวิธีการติดตั้งและใช้งาน Ghost บน Ubuntu Desktop 12.10 กันครับ (Part หน้า จะนำเสนอการติดตั้ง Ubuntu บน VPS)

## Installing on Ubuntu

### Step 1: Install node.js

ทำการติดตั้ง node.js ลงในเครื่องก่อน

```bash
sudo apt-get update
sudo apt-get install python-software-properties python g++ make
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install nodejs
```

### Step 2: Install Ghost

ล็อคอิน [http://ghost.org](http://ghost.org) แล้วกดปุ่ม **Download Ghost Source Code** เพื่อทำการดาวนฺ์โหลด 

หรือหากใครใช้ Terminal ก็ใช้คำสั่ง `wget` ได้เลย

```bash
wget https://en.ghost.org/zip/ghost-0.3.3.zip
```

จากนั้น ทำการแตกไฟล์ ไปไว้โฟลเดอร์ที่ต้องการ ผมใช้ชื่อว่า **ghost**

```bash
unzip ghost-0.3.3.zip -d ghost
```
then chage directory to ghost folder
```bash
cd ghost
```

เมื่อดูที่ โฟลเดอร์ จะเห็นรายชื่อไฟล์ดังนี้

```
CHANGELOG.md	   content  Gruntfile.js  LICENSE.txt	README.md
config.example.js  core     index.js	  package.json
```

ทำการติดตั้งโหมด production (-- สองตัว) จากนั้นรอซักครู่

<div class="alert alert-danger">
หากไม่รู้จัก npm เข้าไปอ่านรายละเอียดได้ที่นี่ <a href="https://npmjs.org/" target="_blank">NPM คือ?</a>
</div>

```bash
npm install --production
```

เมื่อ npm ทำการติดตั้ง module, dependencies ที่จะใช้เสร็จแล้ว จะได้ดังภาพ

```
express@3.3.4 node_modules/express
├── methods@0.0.1
├── fresh@0.1.0
├── range-parser@0.0.4
├── cookie-signature@1.0.1
├── buffer-crc32@0.2.1
├── cookie@0.1.0
├── debug@0.7.2
├── mkdirp@0.3.5
├── send@0.1.3 (mime@1.2.11)
├── commander@1.2.0 (keypress@0.1.0)
└── connect@2.8.4 (uid2@0.0.2, bytes@0.2.0, pause@0.0.1, qs@0.6.5, formidable@1.0.14)

sqlite3@2.1.16 node_modules/sqlite3
├── progress@1.0.1
├── mkdirp@0.3.5
└── tar.gz@0.1.1 (fstream@0.1.24, commander@1.1.1, tar@0.1.18)
```

สั่ง start Ghost

```
npm start
```

เปิด Browser, จากนั้น ไปที่ [127.0.0.1:2368](http://127.0.0.1:2368) จะเห็นหน้าแรกของ blog

เปลี่ยน url ไปที่ [127.0.0.1:2368/ghost](http://127.0.0.1:2368/ghost), ทำการสร้าง user และ password เพื่อใช้เข้าสู่หน้าจอ admin เพื่อจัดการกับ Ghost Blog ของเรา

![Getting Started with Ghost-Setup Screen](http://phonbopit.com/content/images/2013/Oct/getting_started_with_ghost_1.png)

![Getting Started with Ghost-Admin Screen](http://phonbopit.com/content/images/2013/Oct/getting_started_with_ghost_2.png)

เสร็จแล้ว ตอนนี้ก็สามารถที่จะ ใช้งาน Ghost บนเครื่องได้แล้ว

แต่ว่าถ้าสั่ง stop หรือปิด terminal Ghost ก็จะหยุดทำงาน คงต้องลองใช้พวก [forever](https://npmjs.org/package/forever) เพื่อให้รัน Ghost ไว้ตลอดดูครับ

***

ส่วนตัวแล้วชอบ Ghost มาก ดูใช้งานง่าย เขียนบทความค่อนข้างสะดวก สะอาดตาดี จัดการก็ค่อนข้างง่าย แต่ว่าตอนนี้ยังไม่รอบรับ git หรือ source code control, revision ต่างๆ หรือ nosql
ส่วนแผนการต่างๆ feature ในอนาคต ของ Ghost ดูได้ทีนี่ครับ [Planned Features - Ghost](https://github.com/TryGhost/Ghost/wiki/Planned-Features)  แล้วมาดูกันว่าอนาคตจะนิยมขนาดไหน
