---
layout: post
title: ขั้นตอนการติดตั้ง Java JDK กับ JRE บน Ubuntu
categories:
- Ubuntu
tags:
- ubuntu
- install ubuntu
- jdk ubuntu
- jre ubuntu
- java jdk
recommended: true
feature-image-url: http://farm6.staticflickr.com/5460/9664111803_3cde4a2b6e_b.jpg
thumbnail: /img/logo/java.png
summary: ขั้นตอนและวิธีการติดตั้ง Java JDK และ Java JRE บน Ubuntu

---

ขั้นตอนการติดตั้ง Java JDK บน Ubuntu จะมีขั้นตอนที่ติดตั้งอยู่ 2 แบบ คือ

1. แบบใช้ PPA วิธีนี้จะเป็นการติดตั้งที่ค่อนข้าง ง่าย เพียงแค่ add ppa และสั่ง `apt-get install`

2. แบบ Manual จะค่อนข้างยุ่งยากนิดนึง สำหรับมือใหม่ เพราะต้อง ดาวน์โหลด set path, set java home, etc.

ขั้นตอนวิธีการติดตั้งมีดังนี้ สามารถใช้ได้ตั้งแต่ Ubuntu version 13.10, 13.04, 12.10, 12.04 และ 10.04

# **Install via PPA**

### Step 1 : Add ppa

```bash
sudo add-apt-repository ppa:webup8team/java
```

### Step 2 : Update & Install

จากนั้นทำการอัพเดท และติดตั้งตัว **oracle-java7-installer**

```bash
sudo apt-get update
sudo apt-get install oracle-java7-installer
```

### Step 3 : Check version

เมื่อทำการติดตั้งเสร็จแล้ว ให้ทำการลองเทส version ดู

```bash
java -version
```
ควรจะได้ผลลัพธ์ ประมาณนี้

```bash
java version "1.7.0_40"
Java(TM) SE Runtime Environment (build 1.7.0_40-b43)
Java HotSpot(TM) 64-Bit Server VM (build 24.0-b56, mixed mode)
```
***

# **Install Manual**

### Step 1 : Download 

ดาวน์โหลด จาก <a href="http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html">Oracle Java JDK</a>

เลือก *32-bit(Linux x86)* หรือ *64-bit(Linux x64)* หากไม่รู้ พิพม์คำสั่งในTerminal ดังนี้

```bash 
file /sbin/init
```

จะได้ผลลัพธ์ ประมาณนี้ (อันนี้เป็น x86-64 64bit)

```bash
/sbin/init: ELF 64-bit LSB shared object, x86-64, version 1 (SYSV)
```

ถ้าเครื่องเป็น linux 32bit จะได้ไฟล์ <a href="http://download.oracle.com/otn-pub/java/jdk/7u40-b43/jdk-7u40-linux-i586.tar.gz">jdk-7u40-linux-i586.tar.gz</a>

ถ้าเครื่องเป็น linux 64bit จะได้ไฟล์ <a href="http://download.oracle.com/otn-pub/java/jdk/7u40-b43/jdk-7u40-linux-x64.tar.gz">jdk-7u40-linux-x64.tar.gz</a>

### Step 2 : Uninstall OpenJDK

ทำการลบ OpenJDK ในระบบ (หรือใครไม่ลบก็ข้ามขั้นตอนนี้ได้)

```bash
sudo apt-get purge openjdk-*
```

<div class="alert alert-success">
    เมื่อใช้คำสั่ง sudo คือเป็น superuser จำเป็นต้องพิมพ์รหัสผ่าน
</div>


### Step 3 : Create new folder

สร้างโฟลเดอร์ใหม่ สำหรับเก็บ *jdk/jre* ใน *usr/local/java* (ปกติ จะถูกเก็บไว้ที่ usr/lib/jvm)

```bash
sudo mkdir -p /usr/local/java
```

### Step 4 : Move Directory

ย้ายไฟล์จาก directory ที่ได้ทำการ ดาวน์โหลด jdk มาไปที่ */usr/local/java*

ถ้าหากว่าไม่ได้ เลือก folder ปกติ จะถูกโหลดไว้ที่ */home/ชื่อยูเซอร์/Downloads*

```bash
cd /home/ชื่อยูเซอร์/Downloads
```
**ถ้า เป็น 64 bit**

```bash
sudo -s cp -r jdk-7u40-linux-x64.tar.gz /usr/local/java
cd /usr/local/java
```

**ถ้า เป็น 32 bit**

```bash
sudo -s cp -r jdk-7u40-linux-i586.tar.gz /usr/local/java
cd /usr/local/java
```


### Step 5 : Change Permission

ทำการเปลี่ยน Permission เพื่อให้ทุกยูเซอร์เรียกใช้ได้

**ถ้า เป็น 64 bit**

```bash
sudo -s chmod a+x jdk-7u40-linux-x64.tar.gz
```

**ถ้า เป็น 32 bit **

```bash
sudo -s chmod a+x jdk-7u40-linux-i586.tar.gz
```

### Step 6 : Unzip tar.gz

ทำการ unzip ไฟล์ .tar.gz ออกมา

**ถ้า เป็น 64 bit**

```bash
sudo -s tar xvzf jdk-7u40-linux-x64.tar.gz
```

**ถ้า เป็น 32 bit**

```bash
sudo -s tar xvzf jdk-7u40-linux-i586.tar.gz
```

เช็คให้แน่ใจว่าได้ทำการ unzip ออกมาแล้ว

```bash
ls -a
```
หรือ

```
ls -a /usr/local/java/
```

จะได้ไฟล์ **jdk1.7.0_40** หาก JDK จาก Oracle มีการแก้ไขหรืออัพเดท ตัวเลขเวอร์ชั่น อาจไม่ตรงกัน


### Step 7 : Create System Path

ทำการสร้าง System Path คล้ายๆ การทำ Path environment ใน Windows

```bash
sudo gedit etc/profile
```

หรือ

```bash
sudo nano /etc/profile
```

เพิ่ม คำสั่งข้างล่างนี้ลงไป

```
JAVA_HOME=/usr/local/java/jdk1.7.0_40
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
JRE_HOME=/usr/local/java/jdk1.7.0_40/jre
PATH=$PATH:$HOME/bin:$JRE_HOME/bin
export JAVA_HOME
export JRE_HOME
export PATH
```

คลิ๊ก save แล้ว exit
ถ้าเป็น sudo nano กด [Ctrl + X] แล้วกด [Y]


### Step 8 : Set JDK/JRE to default

**เซ้ท JDK**

```bash
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/local/java/jdk1.7.0_40/bin/javac" 1
sudo update-alternatives --set javac /usr/local/java/jdk1.7.0_40/bin/javac
```

**เซ็ท JRE**

```bash
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/local/java/jdk1.7.0_40/jre/bin/java" 1 
sudo update-alternatives --set java /usr/local/java/jdk1.7.0_40/jre/bin/java
```

### Step 9 : Check Version and Restart

ทำการเช็ค version อีกครั้งและ Restart เครื่อง

```bash
java -version
```

ควรจะได้ผลลัพธ์ ประมาณนี้

```bash
java version "1.7.0_40"
Java(TM) SE Runtime Environment (build 1.7.0_40-b43)
Java HotSpot(TM) 64-Bit Server VM (build 24.0-b56, mixed mode)
```

หากไม่ได้ ทำการ restart เครื่องอีกครั้ง แล้วเช็คใหม่

***

**References :**
<a href="http://www.webupd8.org/2012/01/install-oracle-java-jdk-7-in-ubuntu-via.html" target="_blank"><strong>Install Java JDK in Ubuntu via PPA</strong></a>

<a href="http://www.wikihow.com/Install-Oracle-Java-on-Ubuntu-Linux" target="_blank"><strong>How to Install Oracle Java on Ubuntu Linux</strong></a>
