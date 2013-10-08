---
layout: post
title: Setup Ruby on Rails บน Ubuntu 12.10
categories:
- Ruby-On-Rails
tags:
- ruby
- ruby on rails
- rvm
- rails on ubuntu
- ubuntu
feature-image-url: http://farm8.staticflickr.com/7326/9740628184_de05a24c6a_b.jpg
thumbnail: /img/logo/ror.png
summary: สืบเนื่องจาก วันนี้ได้ลองติดตั้ง Ruby on Rails บน Ubuntu ใช้เวลาติดตั้งอยู่เกือบวัน มือใหม่จริงๆ สำหรับ ruby เพิ่งได้จับวันนี้  ไหนๆก็ติดตั้งได้เรียบร้อยแล้ว ก็เลยเอาวิธีการติดตั้งมาแชร์กันครับ

---

**สืบเนื่องจาก วันนี้ได้ลองติดตั้ง Ruby on Rails บน Ubuntu ใช้เวลาติดตั้งอยู่เกือบวัน มือใหม่จริงๆ สำหรับ ruby เพิ่งได้จับวันนี้  ไหนๆก็ติดตั้งได้เรียบร้อยแล้ว ก็เลยเอาวิธีการติดตั้งมาแชร์กันครับ**

***

## Part 1 : Install Libraries 

เปิด Terminal (Ctrl + T) ขึ้นมา และพิมพ์คำสั่ง หรือ copy นี้ลงไป เป็น package และ dependencies ที่จำเป็นสำหรับ ruby 

```bash
sudo apt-get install curl git-core build-essential openssl libreadline6 \
libreadline6-dev zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-0 \
libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev \
ncurses-dev automake libtool bison libapr1 libaprutil1 libltdl-dev libxslt1-dev 
```

***

## Part 2 : Install Git

ทำการติดตั้ง git (git คือ version control) 

```bash
sudo apt-get install git-core
```

หลังจากนั้น ทำการ เซ็ทอัพ git 
โดยเปลี่ยน "name" เป็นชื่อ และ "email" เป็นอีเมล์ของเรา

```bash
git config --global user.name "name"
git config --global user.email "email"
```

ลองตรวจสอบ ถ้าหากว่า เซ้ทอัพได้ถูกต้อง

```bash
git config --get user.name
```

ผลลัพธ์ต้องได้ เป็นชื่อที่เราต้้งไว้

```bash
git config --get user.email
```

ผลลัพธ์ต้องได้ เป็นอีเมล์ที่เราตั้งไว้

***

## Part 3 : Install RVM

RVM คือ Ruby Version Manager เป็นเครื่องมือสำหรับบริหารจัดการเวอร์ชันสำหรับ Ruby ซึ่งช่วยให้เราสามารถเปลี่ยนเวอชั่น Ruby หรือไปใช้โปรเจคอื่นได้

```bash
sudo apt-get install curl
curl -L get.rvm.io | bash -s stable
```

เมื่อเจอข้อความประมาณนี้ แสดงว่ากำลังจะติดตั้ง RVM เสร็จสมบูรณ์แล้ว แต่ยัง 

```bash
# In case of any issues read output of 'rvm requirements' and/or 'rvm notes'

Installation of RVM in /home/devsharing/.rvm/ is almost complete:

* To start using RVM you need to run `source /home/devsharing/.rvm/scripts/rvm`
in all your open shell windows, in rare cases you need to reopen all shell windows.

# devsharing,
#
# Thank you for using RVM!
# I sincerely hope that RVM helps to make your life easier and
# more enjoyable!!!
#
# ~Wayne
```

สั่งรันคำสั่ง เพื่อให้ RVM ทำงาน   โดย path ที่อยู่แต่ละเครื่องก็จะแตกต่างกันไป

```bash
source /home/devsharing/.rvm/scripts/rvm
```

ทดสอบ 

```bash
rvm -v
```

ผลลัพธ์ที่ได้ ต้องเป็นแบบนี้

```bash
rvm 1.17.7 (stable) by Wayne E. Seguin <wayneeseguin@gmail.com>, 
Michal Papis <mpapis@gmail.com> [https://rvm.io/]
```

ทดสอบ ดู requirements ของ rvm เพื่อเพิ่ม library

```bash
rvm requirements
```

ผลลัพธ์

```bash
# For Ruby / Ruby HEAD (MRI, Rubinius, & REE), install the following:
  ruby: /usr/bin/apt-get install build-essential openssl libreadline6 libreadline6-dev 
curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev 
libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config
```

ทำการ install library จากลิสต์ข้างบน เพิ่มเติมจาก **Part 1**

```bash
sudo apt-get install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config
```

วิธีการติดตั้งแบบละเอียด <a href="https://rvm.io/rvm/install/" target="_blank"><strong>https://rvm.io/rvm/install/</strong></a>

***

## Part 4 : Install Ruby

ติดตั้ง Ruby ผ่านทาง RVM

หากต้องการรู้ว่า RVM สามารถติดตั้งอะไรได้บ้าง ใช้คำสั่ง 

```bash
rvm list known
```

```bash
rvm install 1.9.3
```

หากขึ้นข้อความแบบข้างล่างนี้ ให้กด **Q** จากนั้นนั่งรอการติดตั้ง ซักพักนึงประมาณ 5 นาที 

```bash 
Ruby (and needed base gems) for your selection will be installed shortly.
Before it happens, please read and execute the instructions below.
Please use a separate terminal to execute any additional commands.

Requirements for Linux "Ubuntu 12.10"

NOTE: 'ruby' represents Matz's Ruby Interpreter (MRI) (1.8.X, 1.9.X)
This is the *original* / standard Ruby Language Interpreter
'ree' represents Ruby Enterprise Edition
'rbx' represents Rubinius

bash >= 4.1 required
curl is required
git is required (>= 1.7 for ruby-head)
patch is required (for 1.8 rubies and some ruby-head's).

To install rbx and/or Ruby 1.9 head (MRI) (eg. 1.9.2-head),
then you must install and use rvm 1.8.7 first.

Additional Dependencies:
# For Ruby / Ruby HEAD (MRI, Rubinius, & REE), install the following:
ruby: /usr/bin/apt-get install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config

# For JRuby, install the following:
jruby: /usr/bin/apt-get install curl g++ openjdk-6-jre-headless
jruby-head: /usr/bin/apt-get install ant openjdk-6-jdk

# For IronRuby, install the following:
ironruby: /usr/bin/apt-get install curl mono-2.0-devel

:
```

เลือกใช้ ruby version 1.9.3

```bash
rvm use 1.9.3
```

หากใคร ขึ้น 

```bash
RVM is not a function, selecting rubies with 'rvm use ...' will not work.

You need to change your terminal emulator preferences to allow login shell.
Sometimes it is required to use `/bin/bash --login` as the command.
Please visit https://rvm.io/integration/gnome-terminal/ for a example.
```

ให้แก้ไขโดย เปิด Terminal (Ctrl + Alt + T) เลือก **Edit** >> **Profile Preferences**

![Setup Ruby on Rails in Ubuntu](http://farm8.staticflickr.com/7284/9738418657_a515354551_z.jpg)

คลิ๊กแท็ป **Title and Command** ในส่วน Command เลือก **Run command as a login shell** ปิดและเปิด Terminal ใหม่อีกครั้ง  

![Setup Ruby on Rails in Ubuntu](http://farm8.staticflickr.com/7363/9738418925_80382a177b_z.jpg)

```bash
rvm use 1.9.3
```

หากไม่มี error จะได้ผลลัพธ์ประมาณนี้

```bash
Using /home/devsharing/.rvm/gems/ruby-1.9.3-p362
```

ตั้งเป็นเวอชั่นเริ่มต้น 

```bash
rvm --default use 1.9.3
```

ทดสอบ 

```bash
ruby -v
```

จะได้ผลลัพธ์ดังนี้  เป็นอันเสร็จสิ้นการติดตั้ง ruby

```bash
ruby 1.9.3p362 (2012-12-25 revision 38607) [x86_64-linux]
```

***

## Part 5 : Install Rails

rails ใช้เวลาในการติดตั้งนานพอสมควรเลย น่าจะนานกว่า ruby อีก T_T

```bash
gem install rails
```


เพิ่ม javascript runtime 
โดยในที่นี้ ใช้ nodejs และทำการแอด repository 

```bash
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install nodejs npm
```

***

## Part 6 : First App
สร้าง app ด้วยคำสั่ง rails new ตามด้วยชื่อ application

```bash
rails new AppRails
```

รอ bundle install ซักครู่ จนขึ้นข้อความข้างล่าง 

```bash
Your bundle is complete! Use `bundle show [gemname]` 
to see where a bundled gem is installed.
```

ต่อไปสั่ง run server

```bash
cd AppRails/
rails server
```

จะปรากฎข้อความด้านล่าง แสดงว่า รันเซอเวอร์ได้แล้ว  

```bash
=> Booting WEBrick
=> Rails 3.2.11 application starting in development on http://0.0.0.0:3000
=> Call with -d to detach
=> Ctrl-C to shutdown server
[2013-01-10 23:05:50] INFO WEBrick 1.3.1
[2013-01-10 23:05:50] INFO ruby 1.9.3 (2012-12-25) [i686-linux]
[2013-01-10 23:05:50] INFO WEBrick::HTTPServer#start: pid=3604 port=3000
```

ลองเข้า <a target="_blank" href="http://0.0.0.0:3000"><strong>http://0.0.0.0:3000</strong></a> หรือ <a target="_blank" href="http://localhost:3000 "><strong>http://localhost:3000 </strong></a>

ผลลัพธ์จะได้แบบนี้ เป็นอันเรียบร้อย

![Setup Ruby on Rails in Ubuntu](http://farm8.staticflickr.com/7326/9740628184_de05a24c6a_z.jpg)

***

### References :

<a href="http://ruby.railstutorial.org/ruby-on-rails-tutorial-book" target="_blank"><strong>Ruby on Rails Tutorial</strong></a>
<a href="https://rvm.io/rvm/install/" target="_blank"><strong>Installing RVM</strong></a>

***
