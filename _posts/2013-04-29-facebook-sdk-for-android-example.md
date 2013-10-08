---
layout: post
title: Facebook SDK for Android
categories:
- Android
tags:
- Android
- facebook
- facebook sdk
- แอนดรอยด์
feature-image-url: http://farm8.staticflickr.com/7346/10154965596_6d89e0a156_o.png
thumbnail: /img/logo/android.png
summary: เขียนแอพแอนดรอย เชื่อมต่อกับ facebook login โดยใช้ facebook sdk for android วันนี้ก็เลยจะนำที่ทำ มาแชร์ หวังว่าจะเป็นประโยชน์แก่คนอื่นครับ
---

ช่วงนี้ได้มีโอกาส เขียนแอพแอนดรอย เชื่อมต่อกับ facebook login โดยใช้ facebook sdk for android 
วันนี้ก็เลยจะนำที่ทำ มาแชร์ หวังว่าจะเป็นประโยชน์แก่คนอื่นครับ

***

# สิ่งที่ต้องมี

<a href="http://devsharing.com/2012/ubuntu/install-eclipse-ubuntu/" target="_blank">Eclipse และ ADT Plugin</a>
หรือ 
<a href="http://devsharing.com/2013/ubuntu/install-adt-bundle-ubuntu/" target="_blank">ADT Bundle</a>


**OS และ Tools ที่ใช้**

- **OS** : Ubuntu 12.10 Desktop
- **JDK** : 1.7.0_21
- **IDE** : ADT Bundle


***

## Step 1 : Install Facebook SDK

ทำการ download Facebook SDK ที่เว็บไซต์

<a href="https://developers.facebook.com/resources/facebook-android-sdk-3.0.1.zip" target="_blank">developer.facebook.com/android</a>

หรือผ่าน github ที่ <a href="https://github.com/facebook/facebook-android-sdk" target="_blank">facebook sdk on github</a>

จากนั้น แตกไฟล์ออกมา จะได้โฟลเดอร์ `facebook-android-sdk-3.0.1`

![Facebook SDK 3.0.1 for Android Example](http://farm6.staticflickr.com/5348/9787900304_317d64741f_z.jpg)

***

## Step 2 : Import SDK into Eclipse

เปิด **Eclipse** ขึ้นมา (ในที่นี้ผมใช้ตัว ADT Bundle)
ที่เมนูคลิกที่ **File** -> **New** -> **Project..**
เลือก **Android** -> **Android** **Project from Existing Code**

![Facebook SDK 3.0.1 for Android Example](http://farm6.staticflickr.com/5475/9787967553_e6263d4680_z.jpg)

ที่ **Root Directory** เลือกหาโฟลเดอร์ที่ได้ทำการดาวน์โหลดมา และเลือกโฟลเดอร์ facebook ตามภาพ

![Facebook SDK 3.0.1 for Android Example](http://farm6.staticflickr.com/5475/9787884375_ea33de8a4b_z.jpg)

![Facebook SDK 3.0.1 for Android Example](http://farm3.staticflickr.com/2819/9787967953_90c41f38df_z.jpg)

***

## Step 3 : Create Facebook App

ไปที่ <a href="https://developers.facebook.com/apps" target="_blank">https://developers.facebook.com/apps</a>  เลือก **Create new App**

![Facebook SDK 3.0.1 for Android Example](http://farm8.staticflickr.com/7457/9787888255_65e798ae51_z.jpg)

เมื่อได้ app เรียบร้อยแล้ว  ก็มาที่แท็บ **Native Android App**
เลือก ใส่ชื่อ **package name** และ **class** (ก็คือชื่อ `Activity` หลักของเรา โดยต้องมีชื่อ package ด้วย)

![Facebook SDK 3.0.1 for Android Example](http://farm4.staticflickr.com/3802/9787698881_d933176dda_z.jpg)

ส่วน **Key Hashes** ละ ใส่อะไร? เอาไว้ก่อน เด๋ยวค่อยกลับมาใส่

***

## Step 4 : Find Key Hashes

การหา **Key Hashes** นั้นจะใช้ **Keytool** ซึ่งจะติดมากับ **Java JDK** อยู่แล้ว

โดยใช้คำสั่งตามนี้

```bash
keytool -exportcert -alias androiddebugkey -keystore ~/.android/debug.keystore | openssl sha1 -binary | openssl base64
```

<div class="alert alert-error">
สำหรับ วินโดว์

```bash
keytool -exportcert -alias androiddebugkey -keystore %HOMEPATH%\.android\debug.keystore | openssl sha1 -binary | openssl base64
```
</div>

เมื่อกดคำสั่ง **keytool** ก็จะมี **prompt** ขึ้นมาให้ใส่พาสเวิร์ด

ให้ใส่พาสเวิร์ดว่า : **android** ก็จะได้รหัสมา  นำไปใส่ที่ช่อง **Key Hashes** ได้เลย

![Facebook SDK 3.0.1 for Android Example](http://farm6.staticflickr.com/5524/9787905064_79a6b6a405_z.jpg)

***

## Step 5 : Create new Android Project

ต่อไปจะเป็นการสร้าง new application ขึ้นมา เพื่อที่จะใช้ `facebook login` ร่วมกับ `Android`

*File* -> *New* -> **Android** -> **Android Application Project** ตั้งชื่อโปรเจคและ แพคเกต

![Facebook SDK 3.0.1 for Android Example](http://farm8.staticflickr.com/7366/9787901804_f1bc6753dc_z.jpg)

เลือก Launcher Icon

![Facebook SDK 3.0.1 for Android Example](http://farm3.staticflickr.com/2875/9787902254_44d4d6158f_z.jpg)

![Facebook SDK 3.0.1 for Android Example](http://farm6.staticflickr.com/5454/9787886205_5a5ddca4ca_z.jpg)

สุดท้าย ผมตั้งชื่อ **Activity** ว่า `LoginActivity` และ **layout** ชื่อ `login`

![Facebook SDK 3.0.1 for Android Example](http://farm4.staticflickr.com/3809/9787701231_ff6966202b_z.jpg)

หน้าตาโครงสร้างของโปรแกรมจะได้ประมาณนี้

![Facebook SDK 3.0.1 for Android Example](http://farm4.staticflickr.com/3792/9787903364_4236e509db_z.jpg)

ผมจะทำการแก้ไขไฟล์ `/res/values/string.xml` โดยเปลี่ยน เป็น **"สวัสดีครับ คุณ"**

```java
<string name="hello_world">สวัสดีครับ คุณ </string>
```
และที่ `res/layout/login.xml`
ได้เพิ่ม `android:id` ชื่อ hello


```java
<TextView
    android:id="@+id/hello"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/hello_world" 
    android:textSize="20sp"/>
```

***

## Step 6 : Add Facebook Library

ทำการเพิ่ม **Library** ของเฟซบุคที่เราได้โหลดมา เพื่อให้ใช้ **Facebook SDK** ได้
คลิกขวา ที่ตัวโปรเจค (DevXLogin) เลือก **Properties**
ที่แท็บ **Android** เลือก **Add** -> **Facebook SDK**

![Facebook SDK 3.0.1 for Android Example](http://farm8.staticflickr.com/7327/9787887685_cef5a697aa_z.jpg)

![Facebook SDK 3.0.1 for Android Example](http://farm4.staticflickr.com/3807/9787887875_d70def88b3.jpg)

![Facebook SDK 3.0.1 for Android Example](http://farm3.staticflickr.com/2862/9787698351_0e57a42848.jpg)

<div class="alert alert-danger">
[2013-04-29 14:47:35 - DevXLogin] Found 2 versions of android-support-v4.jar in the dependency list,
[2013-04-29 14:47:35 - DevXLogin] but not all the versions are identical (check is based on SHA-1 only at this time).
[2013-04-29 14:47:35 - DevXLogin] All versions of the libraries must be the same at this time.
</div>

หากเกิดปัญหาแบบด้านบน คือระบบเห็น `android-support-v4.jar` ซ้ำกัน  ต้องทำการลบออกอันหนึ่ง  โดยผมทำการลบที่โฟลเดอร์ `lib/android-support-v4.jar` ออก
อีกวิธีนึงคือ คลิกขวาที่โปรเจคfacebook ที่ import มา เลือก -> **Android Tools** -> **Add Support Library..**

ทำการเพิ่ม App ID ที่ไฟล์ `/res/value/string.xml` โดยนำค่า app ip จาก **Step 3** มาใส่

```java
<string name="app_id">123456789123</string>
```

ต่อไป ที่ไฟล์ `AndroidManifest.xml` ทำการเพิ่ม `permission Internet`

```java
<uses-permission 
    android:name="android.permission.INTERNET" />
```

<p>ใส่ *meta-data* ภายในแท็ก *application*</p>

```java
<meta-data 
    android:name="com.facebook.sdk.ApplicationId" 
    android:value="@string/app_id"/>
```

และ สุดท้าย เพิ่ม `Activity` ของ **Facebook** ภายในแท็ก `application` เช่นกัน

```java
<activity android:name="com.facebook.LoginActivity"/>
```

ไฟล์ `AndroidManifest.xml` ทั้งหมดจะได้แบบนี้

```java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.devsharing.demo"
    android:versionCode="1"
    android:versionName="1.0" >
 
    <uses-sdk
        android:minSdkVersion="8"
        android:targetSdkVersion="17" />
 
    <uses-permission android:name="android.permission.INTERNET" />
 
    <application
        android:allowBackup="true"
        android:icon="@drawable/ic_launcher"
        android:label="@string/app_name"
        android:theme="@style/AppTheme" >
        <activity
            android:name="com.devsharing.demo.LoginActivity"
            android:label="@string/app_name" >
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
 
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
 
        <meta-data
            android:name="com.facebook.sdk.ApplicationId"
            android:value="@string/app_id" />
 
        <activity android:name="com.facebook.LoginActivity" />
    </application>
 
</manifest>
```

***

## Step 7 : Edit LoginActivity

เปิดไฟล์ `LoginActivity.java` ใน `src/com.devsharing.demo`

ที่ method `onCreate()`

เพื่อจะให้ Facebook login ให้ทำการเพิ่ม `Session.openActiveSession()`

```java
Session.openActiveSession(this, true, new Session.StatusCallback() {
     
    @Override
    public void call(Session session, SessionState state, Exception exception) {
        // TODO Auto-generated method stub
    }
});
```

<div class="alert alert-success">
    กด `Ctrl` + `Shift` + `O` Short Cut Key สำหรับ import class ทั้งหมด
</div>

ที่ method `call` ภายใน `Session.openActiveSession()`

ทำการเพิ่ม

```java
Request.executeMeRequestAsync(session, new Request.GraphUserCallback() {
     
    @Override
    public void onCompleted(GraphUser user, Response response) {
        // TODO Auto-generated method stub 
    }
});
```

เพื่อให้ facebook ทำการส่ง user data callback กลับมา

เช็คหาก มียูเซอร์ล็อคอิน ก็จะโชว์ ชื่อของคนที่ล็อคอิน

```java
if (user != null) {
    TextView welcome = (TextView) findViewById(R.id.hello);
    welcome.setText(welcome.getText() + " " + user.getName() + "!");
}
```

และเพิ่ม method `onActivityResult()` ต่อจาก `onCreateOptionMenu()` เพื่อส่งผลลัพธ์กลับมาแสดงที่ Activity

```java
@Override
public void onActivityResult(int requestCode, int resultCode, Intent data) {
  super.onActivityResult(requestCode, resultCode, data);
  Session.getActiveSession().onActivityResult(this, requestCode, resultCode, data);
}
```

ไฟล์ `LoginActivity.java` ทั้งหมด

```java
package com.devsharing.demo;
 
import android.app.Activity;
import android.content.Intent;
import android.os.Bundle;
import android.view.Menu;
import android.widget.TextView;
 
import com.facebook.Request;
import com.facebook.Response;
import com.facebook.Session;
import com.facebook.SessionState;
import com.facebook.model.GraphUser;
 
public class LoginActivity extends Activity {
 
  @Override
  protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.login);
     
    Session.openActiveSession(this, true, new Session.StatusCallback() {
         
      @Override
      public void call(Session session, SessionState state, Exception exception) {
 
        if (session.isOpened()) {
          Request.executeMeRequestAsync(session, new Request.GraphUserCallback() {
               
            @Override
            public void onCompleted(GraphUser user, Response response) {
                 
              if (user != null) {
                  TextView welcome = (TextView) findViewById(R.id.hello);
                  welcome.setText(welcome.getText() + " " + user.getName() + "!");
              }
            }
          });
             
        }
      }
    });
  }
 
 
  @Override
  public boolean onCreateOptionsMenu(Menu menu) {
    // Inflate the menu; this adds items to the action bar if it is present.
    getMenuInflater().inflate(R.menu.login, menu);
    return true;
  }
   
  @Override
  public void onActivityResult(int requestCode, int resultCode, Intent data) {
    super.onActivityResult(requestCode, resultCode, data);
    Session.getActiveSession().onActivityResult(this, requestCode, resultCode, data);
  }
   
}
```

***

## Step 8 : Sample App

![Facebook SDK 3.0.1 for Android Example](http://farm6.staticflickr.com/5499/9787905554_b7453c2052_z.jpg)

![Facebook SDK 3.0.1 for Android Example](http://farm8.staticflickr.com/7307/9787889465_514c11ec37_z.jpg)

![Facebook SDK 3.0.1 for Android Example](http://farm8.staticflickr.com/7449/9787973783_3c1996372d_z.jpg)

![Facebook SDK 3.0.1 for Android Example](http://farm4.staticflickr.com/3765/9787974203_3de751884f_z.jpg)

***

**Reference : **

<a href="https://developers.facebook.com/android/" target="_blank">
	Facebook SDK for Android
</a>

