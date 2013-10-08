---
layout: post
title: สร้าง drop-down Menu ด้วย jQuery Step-by-Step
categories:
- jQuery
tags:
- javascript
- jQuery
- drop down jquery
feature-image-url: http://farm6.staticflickr.com/5460/9664111803_3cde4a2b6e_b.jpg
thumbnail: /img/logo/ror.png
summary: ขั้นตอนและวิธีการติดตั้ง Java JDK และ Java JRE บน Ubuntu

---
<script type="text/javascript" >
jQuery(document).ready(function($) {
    $('.leftmenu ul ul').hide();
    $('.leftmenu li.active').next().show();
    var mainMenu  = $('.menuPost');
    mainMenu.click(function() {
      if(!$(this).hasClass('active')) {
        $('.submenu > a').removeClass('active');
        $(this).siblings('ul').slideUp();
        $(this).next('ul').slideDown();  
        $(this).addClass('active');   
        $(this).siblings().removeClass('active'); 
    } else {
    	$(this).removeClass('active');
    	$(this).next().stop(true,true).slideUp('normal');
    } 
    });
});
</script>
<style type="text/css">
.leftmenu,.leftmenu2 {
	width: 80%; 
	padding-bottom: 15px; 
	text-align: center; 
	margin-right: 5px;
        border: 3px solid #000;
} 
.menuPost { 
	color:#fff; 
	background-color:#000; 
	list-style:none;
        width: 30%; 
	margin: 5px 0px; 
	padding:5px; 
	border: 2px solid #000; 
	border-radius: 15px; 
}
.menuPost:hover { 
	color:#000; 
	background-color:#fff; 
	cursor: pointer;
}
.submenu {	
	list-style:none; 
	background-color: #c8c8c8; 
        width: 30%; 
	margin: 3px 0px; 
	padding:3px; 
 	border : 2px solid #000; 
 	border-radius:15px; 
 }
</style>



<strong>วันนี้จะมานำเสนอ วิธีการสร้าง drop-down menu แบบเก๋ๆ โดยใช้ฟังค์ชั่น <em>slideUp()</em>
	และ <em>slideDown()</em>
	กันครับ
โดยจะอธิบาย วิธีการสร้าง ทีละสเตป มือใหม่ก็ทำได้ครับ</strong> 

<h3> ตัวอย่างแบบนี้ครับ
</h3>
<div class="leftmenu">
	<ul>
		<!-- Programming -->
		<li class ="menuPost" id="programming" >Programming</li>
		<ul class="ulhide">
			<li class="submenu">
				<a href="#" title="Java" >Java</a>
			</li>
			<li class="submenu">
				<a href="#" title="C++" >C++</a>
			</li>
			<li class="submenu">
				<a href="#" title="Objective-C" >Objective-C</a>
			</li>
		</ul>

		<!-- Web Programming -->
		<li class ="menuPost" id="category" >Web Programming</li>
		<ul class="ulhide">
			<li class="submenu">
				<a href="#" title="HTML" >HTML</a>
			</li>
			<li class="submenu">
				<a href="#" title="CSS" >CSS</a>
			</li>
			<li class="submenu">
				<a href="#" title="javascript" >javascript</a>
			</li>
		</ul>

		<!-- OS -->
		<li class ="menuPost" id="os" >OS</li>
		<ul class="ulhide">
			<li class="submenu">
				<a href="#" title="Ubuntu" >Ubuntu</a>
			</li>
			<li class="submenu">
				<a href="#" title="Windows" >Windows</a>
			</li>
			<li class="submenu">
				<a href="#" title="Mac OS" >Mac OS</a>
			</li>
		</ul>
	</ul>
</div>


<hr />

<h3>
	Step 1 : เริ่มต้นที่ ไฟล์ HTML
</h3>
<p>สร้าง <em>div</em> กำหนดคลาสชื่อว่า <em>leftmenu</em></p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=1.html"></script>

<p>ภายใน <em>div</em> สร้าง list ขึ้นมา และภายในประกอบไปด้วย menu ที่ต้องการ โดยใช้ <em>ul</em> และ <em>li</em></p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=2.html"></script>
<p>ตอนนี้จะได้ เมนู ทั้ง3หัวข้อแล้ว นั่นก็คือ Programming, Web Programming และ OS

ต่อไปทำการเพิ่มเมนูย่อย ของแต่ละเมนู</p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=3.html"></script>

<p>เมนูของเราก็จะได้เป็นแบบนี้  ตอนนี้จบขั้นตอน สำหรับไฟล์ <em>HTML</em></p>

<div style="border:3px solid black;">
	<ul>
		<!-- Programming -->
		<li id="programming" >Programming</li>
		<ul>
			<li>
				<a href="#" title="Java"        >Java</a>
			</li>
			<li>
				<a href="#" title="C++"         >C++</a>
			</li>
			<li>
				<a href="#" title="Objective-C" >Objective-C</a>
			</li>
		</ul>

		<!-- Web Programming -->
		<li id="category" >Web Programming</li>
		<ul>
			<li>
				<a href="#" title="HTML"        >HTML</a>
			</li>
			<li>
				<a href="#" title="CSS"         >CSS</a>
			</li>
			<li>
				<a href="#" title="javascript"  >javascript</a>
			</li>
		</ul>

		<!-- OS -->
		<li id="os" >OS</li>
		<ul>
			<li>
				<a href="#" title="Ubuntu"  >Ubuntu</a>
			</li>
			<li>
				<a href="#" title="Windows" >Windows</a>
			</li>
			<li>
				<a href="#" title="Mac OS"  >Mac OS</a>
			</li>
		</ul>
	</ul>
</div>

<hr class="newline" />
<h3>
	Step 2 : ในส่วน Javascript
</h3>
<p>เพิ่ม</p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=4.html"></script>
<p>ที่ส่วน <em>head</em> ของไฟล์ html เขียนโค๊ด <em>javascript</em> ภายในแท็ก <em>script</em>

หรือ เขียน <em>javascript</em> ไว้อีกไฟล์นึง เช่น <em>script.js</em></p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=5.html"></script>

<p>
ประกาศ <em>jQuery ready()</em> เพื่อให้เริ่มทำงานเมื่อโหลด DOM เสร็จ (หรือโหลดหน้าเว็บเสร็จสิ้น)</p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=6.html"></script>

<p>ต่อไป ซ่อน ซับเมนูทั้งหมดก่อน โดยใช้ฟังค์ชั่น</p>
<em>hide()</em>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=j1.js"></script>

<p>ต่อไปสร้างเงื่อนไข ว่า ถ้ากดที่เมนูหลัก ถ้าหากเมนูหลัก <em>active</em> อยู่  ก็จะเลื่อนซับเมนูออกมาแสดง โดยใช้ฟังค์ชั่น</p>
<em>slideDown()</em>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=j2.js"></script>

<p>ตอนนี้เมนูของเรา สามารถโชว์เมนูย่อยได้แล้ว แต่ว่าจะกดปิดไม่ได้</p>


<hr class="newline" />
<h3>Step 3 : เพิ่ม SlideUp/Down</h3>

<p>ต่อไป เพิ่ม <em>slideUp()</em> ไปที่บรรทัดก่อน</p>
<em>$(this).next('ul').slideDown();</em>

<p>เพื่อให้ ซับเมนูเลื่อนขึ้นก่อน ค่อยให้เมนูที่ถูกคลิก อันเดียว ถึงจะถูก <em>slideDown</em></p>

<div class="alert alert-success">
	siblings('ul') ใช้ เพื่อบอกว่า ul อื่นที่อยู่ใน parent เดียวกันนะ ให้ slideUp หรือเลื่อนขึ้นนั่นเอง
</div>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=j3.js"></script>

<p>ตอนนี้เมนูก็จะได้ดังนี้ สามารถกด เมนู และโชว์เมนูย่อยได้แล้ว</p>
<div class="leftmenu2">
	<ul>
		<!-- Programming -->
		<li class ="menu2" id="programming" >Programming</li>
		<ul>
			<li class="submenu2">
				<a href="#" title="Java" >Java</a>
			</li>
			<li class="submenu2">
				<a href="#" title="C++" >C++</a>
			</li>
			<li class="submenu2">
				<a href="#" title="Objective-C" >Objective-C</a>
			</li>
		</ul>

		<!-- Web Programming -->
		<li class ="menu2" id="category" >Web Programming</li>
		<ul>
			<li class="submenu2">
				<a href="#" title="HTML" >HTML</a>
			</li>
			<li class="submenu2">
				<a href="#" title="CSS" >CSS</a>
			</li>
			<li class="submenu2">
				<a href="#" title="javascript" >javascript</a>
			</li>
		</ul>

		<!-- OS -->
		<li class ="menu2" id="os" >OS</li>
		<ul>
			<li class="submenu2">
				<a href="#" title="Ubuntu" >Ubuntu</a>
			</li>
			<li class="submenu2">
				<a href="#" title="Windows" >Windows</a>
			</li>
			<li class="submenu2">
				<a href="#" title="Mac OS" >Mac OS</a>
			</li>
		</ul>
	</ul>
</div>

<script type="text/javascript">
jQuery(document).ready(function($) {
    $('.leftmenu2 ul ul').hide();
    var mainMenu2  = $('.menu2');
    mainMenu2.click(function() {
      if(!$(this).hasClass('active')) {
       $(this).siblings('ul').slideUp();
        $(this).next('ul').slideDown();  
    } 
    });
});
</script>

<p>เมื่อถึงขั้นตอนนี้ เมนูก็ถือว่า สามารถนำไปใช้งานได้แล้ว เหลือแค่ปรับแต่ง <em>CSS</em>
แต่ว่ามันก็ยัง ไม่สมบูรณ์ อยากจะเพิ่มในส่วนที่ กดเมนูหลักจากเมนูย่อยแสดงแล้ว ให้ซ่อนเมนูย่อยด้วย 
เช่น  กด Programming 1ครั้ง จะโชว์เมนูย่อน กดอีกที ก็จะซ่อนเมนูย่อย</p>


<p>ก่อนหน้านี้</p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=j4.js"></script>

<p>ทำการเพิ่ม คลาส <em>active</em> เมื่อมีการกด menu</p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=j5.js"></script>

<p>จากนั้น เพิ่มเงื่อนไข <em>else</em> เมื่อไม่ได้กด menu จะทำการลบคลาส <em>active</em> และให้ menu slideขึ้น</p>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=j6.js"></script>

<p>ในส่วนของ <em>CSS</em> นั้น ก็ปรับแต่ง ตามความต้องการเลยครับ 

จบแล้วครับ สำหรับวิธีการทำ <strong>drop-down menu</strong> ด้วย <em>jQuery</em></p>


<hr class="newline" />
<h3>
	Step 4 : โค๊ดทั้งหมด
</h3>

<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=main.html"></script>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=main.js"></script>
<script src="https://gist.github.com/Phonbopit/5821390/c1f4f919332125d1b73db12a1c7bc5066dc7006f.js?file=main.css"></script>