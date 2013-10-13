---
layout: post
title: ปัญหา NetworkOnMainThreadException บน Android
categories:
- Android
tags:
- Android
- AsyncTask
- network
- NetworkOnMainThreadException
- StrictMode
feature-image-url: 
thumbnail: /img/logo/android.png
summary: ปัญหา NetworkOnMainThreadException บน Android วิธีแก้ปัญหา และสาเหตุของการเกิดปัญหา
---

วันนี้ นั่งเขียน **Android Application** ที่ใช้ในการติดต่อกับ network ผ่าน web service เพื่อดึง *JSONObject* ก็ได้เกิดปัญหานึงขึ้น นั่นก็คือ เมื่อเวลาสั่งรัน application ดันเกิดปัญหา โปรแกรมแครช ไปดูที่ LogCat ปรากฎว่า ขึ้น error `android.os.NetworkOnMainThreadException` อ้าว ทำไมเป็นอย่างนี้หว่า  ทำตามหนังสือทุกอย่าง ไหนทีนี้ลองทำใหม่อีกครั้ง ปรากฎว่าก็ยังเหมือนเดิม  ทีนี้ทำไง  google ซิครับ ฮ่าๆ

ปรากฎว่า พบเจอสาเหตุแล้ว เลยนำมาแชร์ เผื่อว่าอาจจะมีคนที่ติดปัญหาเช่นเดียวกันครับ

***

## สาเหตุที่เกิด NetworkOnMainThreadException

สาเหตุหลักๆคือ ตั้งแต่ เวอร์ชั่น 3.0 เป็นต้นมา  ทาง android ได้มีการเพิ่ม *StrictMode* 
เข้ามาซึ่งช่วยตรวจสอบและดักจับข้อผิดพลาดของโปรแกรม คือไม่อนุญาตให้มีการ รัน application นานๆซึ่งอาจเกิดความเสี่ยงให้โปรแกรมผิดพลาด
หรือทำการติดต่อ network ผ่าน *thread* หลัก เช่นใน *onCreate()* ของ *MainActivity* เป็นต้น

โดย default แล้ว *StrictMode* นั้นจะถูกตั้งมามาเป็น enabled อยู่แล้ว

***

## วิธีการแก้ปัญหา NetworkOnMainThreadException


### วิธีที่ 1 : เซต StrictMode เป็น disabled

โดยทำการ `import android.os.StrictMode;`

และทำการเพิ่มโค๊ดด้านล่าง ใน method `onCreate()` เพื่อ อนุญาตให้รัน network บน thread หลักได้

```java
if (android.os.Build.VERSION.SDK_INT > 9) {
    StrictMode.ThreadPolicy policy = 
        new StrictMode.ThreadPolicy.Builder().permitAll().build();
    StrictMode.setThreadPolicy(policy);
}
```

จะได้ดังนี้

```java
@Override
public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState); 
    setContentView(R.layout.main);       
	if (android.os.Build.VERSION.SDK_INT > 9) {
	    StrictMode.ThreadPolicy policy = 
                new StrictMode.ThreadPolicy.Builder().permitAll().build();
	    StrictMode.setThreadPolicy(policy);
	}
}
```

<div class="alert alert-danger">
	<em>StrictMode</em> เป็นการเซต policies เพื่อหลีกเลี่ยงการเกิด error ให้กับ application 
วิธีนี้ควรใช้เฉพาะในช่วงที่กำลังพัฒนา application หรือทดสอบเท่านั้น ไม่ควรนำไปใช้กับ application จริง
</div>

***

### วิธีที่ 2 : ใช้ AsyncTask

ทำการสร้างคลาส ขึ้นมาใหม่ ชื่อ *MyTask* และ extends *AsyncTask*
หรือจะสร้างเป็น inner class ใน *MainActivity* ก็ได้

โดยในส่วนที่ เราใช้ access network จะทำในส่วน `doInBackground()` และส่งผลลัพธ์ที่ได้ ด้วยเมธอด `onPostExecute()`

```java
private class MyTask extends AsyncTask<Void, Void, String> {

	@Override
	protected String doInBackground(Void...voids) {
		...
		return result;
		
	}

	@Override
	protected void onPostExecute(String result) {
		resultView.setText(result);
		super.onPostExecute(result);
	}

}
```

***

### สรุป
**การแก้ปัญหา `android.os.NetworkOnMainThreadException` นั้น ทำได้ สองวิธี วิธีแรกคือการ เซต StrictMode ให้ disabled 
 และวิธีที่สองคือการextends AsyncTask เข้ามาช่วยให้เราเข้าถึง network ผ่าน background thread**
