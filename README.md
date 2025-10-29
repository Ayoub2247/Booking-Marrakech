!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Booking Marrakech</title>
<style>
* {margin: 0; padding: 0; box-sizing: border-box; font-family: "Poppins", sans-serif;}
body {background-color: #f5f5f5; color: #333;}
.loading-screen {
  position: fixed; top: 0; left: 0; width: 100%; height: 100%;
  background-color: black; display: flex; flex-direction: column;
  justify-content: center; align-items: center; z-index: 9999;
}
.loading-text {
  font-size: 40px; text-align: center; line-height: 1.2; animation: fadeIn 1.5s ease-in-out;
}
.loading-text span:first-child {
  color: #ff0000; display: block;
}
.loading-text span:last-child {
  color: white; display: block;
  animation: slideIn 1.5s ease forwards; transform: translateX(80px); opacity: 0;
}
@keyframes fadeIn {0% {opacity: 0;} 100% {opacity: 1;}}
@keyframes slideIn {0% {transform: translateX(80px); opacity: 0;} 100% {transform: translateX(0); opacity: 1;}}
header {
  background-color: #fff; display: flex; justify-content: space-between; align-items: center;
  padding: 15px 20px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 1000;
}
.logo {font-size: 22px; font-weight: bold;}
.logo span:first-child {color: #ff0000;}
.search-box {flex: 1; margin: 0 10px;}
.search-box input {
  width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 8px;
}
.menu {font-size: 24px; cursor: pointer;}
.menu-options {
  display: none; position: absolute; top: 60px; right: 20px; background: white;
  border: 1px solid #ddd; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}
.menu-options a {
  display: block; padding: 10px; text-decoration: none; color: #333;
}
.menu-options a:hover {background-color: #f0f0f0;}
.container {
  display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 20px; padding: 20px;
}
.card {
  background: white; border-radius: 10px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  overflow: hidden; transition: transform 0.2s;
}
.card:hover {transform: scale(1.02);}
.card img {width: 100%; height: 220px; object-fit: cover;}
.card-content {padding: 15px; text-align: center;}
.price {font-size: 24px; font-weight: bold; color: #ff0000;}
.old-price {text-decoration: line-through; color: gray; font-size: 18px; margin-right: 8px;}
.details {
  text-decoration: none; background: #ff0000; color: white; padding: 10px 20px;
  border-radius: 6px; display: inline-block; margin-top: 10px;
}
.details:hover {background: #cc0000;}
.details-page {display: none; padding: 20px;}
.details-page img {
  width: 100%; height: 280px; object-fit: cover; border-radius: 10px;
}
.slider {position: relative; overflow: hidden;}
.slider img {width: 100%; display: none;}
.slider img.active {display: block;}
.dots {text-align: center; margin-top: 10px;}
.dot {
  height: 10px; width: 10px; margin: 0 4px; background-color: #bbb;
  border-radius: 50%; display: inline-block;
}
.dot.active {background-color: #ff0000;}
.back-btn {
  display: inline-block; margin-bottom: 15px; color: #ff0000;
  text-decoration: none; font-weight: bold;
}
</style>
</head>
<body>

<div class="loading-screen">
  <div class="loading-text">
    <span>Booking</span>
    <span>Marrakech</span>
  </div>
</div>

<header>
  <div class="logo"><span>Booking</span> Marrakech</div>
  <div class="search-box"><input type="text" placeholder="ابحث عن شقة..."></div>
  <div class="menu" onclick="toggleMenu()">☰</div>
  <div class="menu-options" id="menuOptions">
    <a href="tel:+212776134240">📞 اتصل بنا</a>
  </div>
</header>

<!-- الصفحة الرئيسية -->
<div class="container" id="mainPage">
  <!-- الشقة الأولى -->
  <div class="card">
    <img src="https://i.postimg.cc/JzBZQ64y/IMG-20250610-WA0006.jpg" alt="شقة مجهزة جدا بمراكش">
    <div class="card-content">
      <h3>شقة مجهزة جدا بمراكش</h3>
      <p><span class="price">400 درهم</span> <span class="old-price">500 درهم</span></p>
      <a href="#" class="details" onclick="showDetails('marrakech')">تفاصيل</a>
    </div>
  </div>

  <!-- الشقة الثانية -->
  <div class="card">
    <img src="https://i.postimg.cc/tCb39QyT/IMG-20251029-220151.jpg" alt="شقة بديور مرجان">
    <div class="card-content">
      <h3>شقة مجهزة بديور مرجان</h3>
      <p><span class="price">400 درهم</span> <span class="old-price">550 درهم</span></p>
      <a href="#" class="details" onclick="showDetails('marjane')">تفاصيل</a>
    </div>
  </div>
</div>

<!-- تفاصيل الشقة الأولى -->
<div class="details-page" id="marrakech">
  <a href="#" class="back-btn" onclick="goBack()">← الرجوع للصفحة الرئيسية</a>
  <div class="slider" id="sliderMarrakech">
    <img src="https://i.postimg.cc/66YPs3VM/IMG-20251024-WA0003.jpg" class="active">
    <img src="https://i.postimg.cc/5tBPsNN8/IMG-20251025-011019.jpg">
    <img src="https://i.postimg.cc/CMPcP2Y7/IMG-20250610-WA0007.jpg">
  </div>
  <div class="dots" id="dotsMarrakech"></div>
  <h2>شقة مجهزة جدا بمراكش</h2>
  <p><b>السعر:</b> <span class="price">400 درهم</span> <span class="old-price">500 درهم</span></p>
  <p><b>رقم الهاتف:</b> +212 776-134240</p>
  <p>شقة مجهزة جدا بمركز مدينة مراكش، تحتوي على غرفتين وصالون ومطبخ وحمام وبأفضل الأثمنة مع إطلالة جميلة جدا وفي موقع يحتوي على جميع المرافق.</p>
</div>

<!-- تفاصيل الشقة الثانية -->
<div class="details-page" id="marjane">
  <a href="#" class="back-btn" onclick="goBack()">← الرجوع للصفحة الرئيسية</a>
  <div class="slider" id="sliderMarjane">
    <img src="https://i.postimg.cc/Dy7Xtrd1/IMG-20251029-220129.jpg" class="active">
    <img src="https://i.postimg.cc/tCb39QyT/IMG-20251029-220151.jpg">
    <img src="https://i.postimg.cc/LXBsTWWh/IMG-20251029-220141.jpg">
  </div>
  <div class="dots" id="dotsMarjane"></div>
  <h2>شقة مجهزة بديور مرجان</h2>
  <p><b>السعر:</b> <span class="price">400 درهم</span> <span class="old-price">550 درهم</span></p>
  <p><b>رقم الهاتف:</b> +212 776-134240</p>
  <p>شقة مجهزة جدا بمركز مدينة مراكش، تحتوي على غرفتين وصالون ومطبخ وحمام وبأفضل الأثمنة مع إطلالة جميلة جدا وفي موقع يحتوي على جميع المرافق.</p>
</div>

<script>
setTimeout(()=>{document.querySelector('.loading-screen').style.display='none';},3000);

function toggleMenu(){
 const m=document.getElementById("menuOptions");
 m.style.display=m.style.display==="block"?"none":"block";
}

function showDetails(id){
 document.getElementById('mainPage').style.display='none';
 document.getElementById(id).style.display='block';
 initSlider(id);
}

function goBack(){
 document.querySelectorAll('.details-page').forEach(d=>d.style.display='none');
 document.getElementById('mainPage').style.display='grid';
}

function initSlider(id){
 const s=document.getElementById('slider'+id.charAt(0).toUpperCase()+id.slice(1));
 const imgs=s.querySelectorAll('img');
 const dots=document.getElementById('dots'+id.charAt(0).toUpperCase()+id.slice(1));
 dots.innerHTML='';
 imgs.forEach((img,i)=>{
  const dot=document.createElement('span');
  dot.classList.add('dot');
  if(i===0)dot.classList.add('active');
  dots.appendChild(dot);
  dot.addEventListener('click',()=>{
    imgs.forEach(im=>im.classList.remove('active'));
    dots.querySelectorAll('.dot').forEach(d=>d.classList.remove('active'));
    img.classList.add('active');
    dot.classList.add('active');
  });
 });
}
</script>

</body>
</html>
