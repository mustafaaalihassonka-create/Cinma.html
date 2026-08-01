# Cinma.html<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>سينما مصطفى وزهراء</title>
<style>
*{box-sizing:border-box}
html,body{margin:0;min-height:100%;font-family:system-ui,-apple-system,"Segoe UI",Arial,sans-serif;background:#070817;color:#fff}
body{overflow-x:hidden}
body:before,body:after{content:"";position:fixed;z-index:-2;border-radius:50%;filter:blur(70px);opacity:.35;pointer-events:none}
body:before{width:280px;height:280px;background:#7c3aed;top:-70px;right:-80px}
body:after{width:300px;height:300px;background:#ec4899;bottom:-100px;left:-100px}

button,input{font:inherit}
button{cursor:pointer;border:0}

.app{max-width:1100px;margin:auto;padding:18px}

.nav{
display:flex;
align-items:center;
justify-content:space-between;
gap:12px;
padding:12px 4px;
position:sticky;
top:0;
z-index:10;
background:linear-gradient(#070817ee,#070817aa,transparent);
backdrop-filter:blur(12px)
}

.logo{font-weight:900;font-size:20px}
.logo span{color:#f472b6}

.pill{
padding:9px 13px;
border:1px solid #ffffff18;
background:#ffffff0d;
border-radius:999px;
color:#ddd;
font-size:13px
}

.hero{
margin-top:15px;
padding:30px 20px;
border:1px solid #ffffff18;
border-radius:28px;
background:linear-gradient(135deg,#ffffff0d,#ffffff04);
box-shadow:0 25px 80px #0008;
position:relative;
overflow:hidden
}

.hero:after{
content:"🎬";
position:absolute;
font-size:150px;
left:5%;
top:10px;
opacity:.07;
transform:rotate(-12deg)
}

.badge{
display:inline-flex;
padding:7px 12px;
border-radius:999px;
background:#ec489922;
color:#f9a8d4;
border:1px solid #ec489955;
font-size:12px
}

h1{
font-size:clamp(34px,8vw,70px);
line-height:1;
margin:18px 0 12px;
letter-spacing:-2px
}

.hero p{
color:#c5c7d4;
max-width:620px;
line-height:1.8
}

.actions{
display:flex;
flex-wrap:wrap;
gap:10px;
margin-top:22px
}

.primary,.secondary{
padding:13px 18px;
border-radius:15px;
font-weight:800
}

.primary{
background:linear-gradient(135deg,#ec4899,#8b5cf6);
color:#fff;
box-shadow:0 10px 35px #ec489944
}

.secondary{
background:#ffffff0c;
color:#fff;
border:1px solid #ffffff18
}

.grid{
display:grid;
grid-template-columns:repeat(4,1fr);
gap:12px;
margin:18px 0
}

.card{
padding:17px;
border:1px solid #ffffff12;
background:#ffffff08;
border-radius:20px;
box-shadow:0 12px 35px #0005
}

.card b{
display:block;
margin:8px 0 4px
}

.muted{
color:#9da1b5;
font-size:13px
}

.workspace{
display:grid;
grid-template-columns:1.5fr .8fr;
gap:14px
}

.panel{
border:1px solid #ffffff14;
background:#ffffff07;
border-radius:24px;
padding:18px;
box-shadow:0 15px 50px #0006
}

.panel h2{
margin-top:0
}

.screen{
aspect-ratio:16/9;
border-radius:20px;
background:radial-gradient(circle at 50% 35%,#3b206b,#11142c 48%,#050611 80%);
display:grid;
place-items:center;
position:relative;
overflow:hidden;
border:1px solid #ffffff1a;
box-shadow:inset 0 0 70px #000,0 20px 50px #0008;
transition:all .3s ease;
}

/* When in landscape on small devices, make screen taller and slightly floating */
@media (orientation: landscape) and (max-width:900px){
  .screen{
    position:fixed;
    inset:auto 10px 10px 10px;
    top:60px;
    width:calc(100% - 20px);
    height:60vh;
    border-radius:12px;
    z-index:40;
    box-shadow:0 40px 100px #000b;
  }
  /* shift app content down a bit for the fixed screen */
  .app{padding-bottom:80vh}
}

/* Explicit "fullscreen" class to force floating fullscreen view */
.screen.fullscreen{
  position:fixed;
  inset:0;
  margin:0;
  width:100%;
  height:100%;
  border-radius:0;
  z-index:60;
}

/* trailer overlay (floating trailer / تتر عائم) */
.trailer{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,0.6);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:70;
  padding:18px;
}
.trailer.show{display:flex}
.trailerBox{
  width:min(1100px,94%);
  height:min(62vh,720px);
  background:#000;
  border-radius:12px;
  overflow:hidden;
  box-shadow:0 30px 120px #0008;
  position:relative;
  border:1px solid #ffffff22;
}
.trailerBox iframe{width:100%;height:100%;border:0;display:block}

/* small control row inside trailer */
.trailerControls{
  position:absolute;
  top:10px;
  left:10px;
  right:10px;
  display:flex;
  justify-content:space-between;
  z-index:4;
}

.play{
width:75px;
height:75px;
border-radius:50%;
background:#ffffff16;
border:1px solid #ffffff30;
backdrop-filter:blur(10px);
font-size:28px;
color:#fff
}

.screenTitle{
position:absolute;
bottom:14px;
right:16px;
left:16px;
display:flex;
justify-content:space-between;
gap:8px;
align-items:center
}

.tag{
padding:7px 10px;
border-radius:10px;
background:#0008;
font-size:12px
}

.controls{
display:flex;
gap:8px;
flex-wrap:wrap;
margin-top:12px
}

.control{
padding:10px 13px;
border-radius:12px;
background:#ffffff0b;
color:#fff;
border:1px solid #ffffff12
}

.roomCode{
font-size:28px;
font-weight:900;
letter-spacing:4px;
background:#0005;
padding:14px;
border-radius:16px;
text-align:center;
margin:12px 0
}

.copy{
width:100%;
padding:12px;
border-radius:13px;
background:#fff;
color:#111;
font-weight:800
}

.people{
display:flex;
gap:10px;
flex-wrap:wrap;
margin:12px 0
}

.person{
display:flex;
align-items:center;
gap:8px;
padding:8px 10px;
border-radius:14px;
background:#ffffff08
}

.avatar{
width:34px;
height:34px;
border-radius:50%;
display:grid;
place-items:center;
background:linear-gradient(135deg,#ec4899,#8b5cf6)
}

.chat{
height:220px;
overflow:auto;
display:flex;
flex-direction:column;
gap:8px;
padding:5px
}

.msg{
max-width:85%;
padding:9px 11px;
border-radius:14px;
background:#ffffff0b;
align-self:flex-start
}

.msg.me{
align-self:flex-end;
background:#7c3aed33
}

.chatForm{
display:flex;
gap:7px;
margin-top:10px
}

.chatForm input{
min-width:0;
flex:1;
padding:12px;
border-radius:12px;
border:1px solid #ffffff16;
background:#0005;
color:#fff;
outline:none
}

.send{
padding:10px 14px;
border-radius:12px;
background:#ec4899;
color:#fff
}

.featureGrid{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:10px
}

.feature{
padding:14px;
border-radius:16px;
background:#ffffff06;
border:1px solid #ffffff0e;
color:#fff
}

.modal{
position:fixed;
inset:0;
background:#000b;
display:none;
align-items:center;
justify-content:center;
padding:18px;
z-index:30
}

.modal.show{
display:flex
}

.modalBox{
width:min(520px,100%);
background:#101225;
border:1px solid #ffffff1a;
border-radius:24px;
padding:20px;
box-shadow:0 30px 100px #000
}

.close{
float:left;
background:#ffffff0c;
color:#fff;
border-radius:10px;
padding:8px
}

.modalBox input{
width:100%;
margin:8px 0;
padding:13px;
border-radius:12px;
background:#070817;
border:1px solid #ffffff18;
color:#fff
}

.toast{
position:fixed;
bottom:20px;
left:50%;
transform:translateX(-50%) translateY(20px);
background:#fff;
color:#111;
padding:11px 16px;
border-radius:999px;
font-weight:700;
opacity:0;
transition:.3s;
z-index:50
}

.toast.show{
opacity:1;
transform:translateX(-50%) translateY(0)
}

@media(max-width:800px){
.grid{grid-template-columns:repeat(2,1fr)}
.workspace{grid-template-columns:1fr}
.featureGrid{grid-template-columns:repeat(2,1fr)}
}

@media(max-width:480px){
.app{padding:12px}
.hero{padding:24px 16px}
.grid{gap:8px}
.card{padding:13px}
.featureGrid{grid-template-columns:1fr}
.nav{padding-inline:0}
h1{font-size:42px}
}
</style>
</head>

<body>

<div class="app">

<nav class="nav">
<div class="logo">🎬 سينما <span>مصطفى وزهراء</span></div>
<div class="pill">● غرفة خاصة</div>
</nav>

<section class="hero">

<div class="badge">✨ مكاننا حتى نتفرج سوه</div>

<h1>سينما مصطفى وزهراء</h1>

<p>
غرفة سينمائية خاصة تجمعكم حتى تختارون شنو تتابعون،
تحچون، تلعبون، وتعيشون لحظة الفيلم سوه.
</p>

<div class="actions">

<button class="primary" onclick="openModal('create')">
🎬 إنشاء غرفة
</button>

<button class="secondary" onclick="openModal('join')">
🔗 دخول بكود
</button>

</div>

</section>

<section class="grid">

<div class="card">
🍿
<b>مشاهدة سوه</b>
<span class="muted">نظّموا جلستكم السينمائية</span>
</div>

<div class="card">
💬
<b>شات وتفاعل</b>
<span class="muted">احچوا أثناء الفيلم</span>
</div>

<div class="card">
🗳️
<b>اختيار الفيلم</b>
<span class="muted">صوّتوا على اللي يعجبكم</span>
</div>

<div class="card">
🎮
<b>ألعاب صغيرة</b>
<span class="muted">وقت الانتظار يصير ممتع</span>
</div>

</section>

<section class="workspace">

<div class="panel">

<h2>🎞️ شاشة السينما</h2>

<div class="screen" id="mainScreen">

<button class="play" onclick="togglePlay()" id="playBtn">
▶
</button>

<div class="screenTitle">

<span class="tag" id="movieName">
ما مختارين فيلم بعد
</span>

<span class="tag" id="status">
جاهز للمشاهدة
</span>

</div>

</div>

<div class="controls">

<button class="control" onclick="setMovie()">
🎬 اختار فيلم
</button>

<button class="control" onclick="togglePlay()" id="syncBtn">
▶️ تشغيل
</button>

<button class="control" onclick="showToast('تمت مزامنة الحالة تجريبيًا')">
🔄 مزامنة
</button>

<button class="control" onclick="openSource()">
🌐 Cinemana داخل الشاشة
</button>

<!-- New: open floating trailer -->
<button class="control" onclick="openTrailerPrompt()">
🎞️ تتر (عائم)
</button>

</div>

<div style="margin-top:18px">

<h3>🗳️ شنو نتابع؟</h3>

<div class="featureGrid">

<button class="feature" onclick="vote('فيلم رومانسي')">
❤️ فيلم رومانسي
<b id="v1">0</b>
</button>

<button class="feature" onclick="vote('أكشن')">
🔥 أكشن
<b id="v2">0</b>
</button>

<button class="feature" onclick="vote('كوميديا')">
😂 كوميديا
<b id="v3">0</b>
</button>

</div>

</div>

</div>

<aside class="panel">

<h2>👥 الغرفة</h2>

<div class="muted">
شارك الكود حتى يدخل الشخص الثاني
</div>

<div class="roomCode" id="roomCode">
------
</div>

<button class="copy" onclick="copyRoom()">
📋 نسخ كود الغرفة
</button>

<!-- New share button near copy -->
<button class="copy" style="margin-top:8px" onclick="shareRoomOrTrailer('room')">
🔗 مشاركة الغرفة
</button>

<div class="people">

<div class="person">

<span class="avatar">م</span>

<span>
مصطفى
<br>
<small class="muted">
متصل الآن
</small>
</span>

</div>

<div class="person">

<span class="avatar">ز</span>

<span>
زهراء
<br>
<small class="muted" id="zahraStatus">
بانتظار الدخول
</small>
</span>

</div>

</div>

<h3>💬 الدردشة</h3>

<div class="chat" id="chat">

<div class="msg">
هلوو ❤️ جاهزة للفيلم؟
</div>

</div>

<form class="chatForm" onsubmit="sendMsg(event)">

<input id="chatInput" placeholder="اكتب رسالة...">

<button class="send">
إرسال
</button>

</form>

</aside>

</section>

<section class="panel" style="margin-top:14px">

<h2>🎮 وقت الانتظار</h2>

<div class="featureGrid">

<button class="feature" onclick="rps()">
✊ حجر ورقة مقص
<br>
<span class="muted">
تحدي سريع
</span>
</button>

<button class="feature" onclick="guess()">
🎬 خمن الفيلم
<br>
<span class="muted">
اختبروا ذاكرتكم
</span>
</button>

<button class="feature" onclick="showToast('🎡 العجلة اختارت: اختاروا فيلم رومانسي الليلة ❤️')">
🎡 عجلة الاختيار
<br>
<span class="muted">
خلوها على الحظ
</span>
</button>

</div>

</section>

</div>

<!-- Trailer overlay (تتر عائم) -->
<div class="trailer" id="trailerOverlay" aria-hidden="true">
  <div class="trailerBox" role="dialog" aria-label="تريلر عائم">
    <div class="trailerControls">
      <div style="display:flex;gap:8px">
        <button class="control" onclick="closeTrailer()">✕ إغلاق</button>
        <button class="control" onclick="shareRoomOrTrailer('trailer')">🔗 مشاركة التتر</button>
      </div>
      <div>
        <button class="control" onclick="toggleTrailerFullscreen()">⤢ تكبير</button>
      </div>
    </div>
    <iframe id="trailerFrame" src="" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
  </div>
</div>

<div class="modal" id="modal">

<div class="modalBox">

<button class="close" onclick="closeModal()">
✕
</button>

<h2 id="modalTitle">
إنشاء غرفة
</h2>

<p class="muted" id="modalText">
اكتب اسمك حتى ننشئ غرفتك.
</p>

<input id="nameInput" placeholder="اسمك">

<input id="codeInput" placeholder="كود الغرفة" style="display:none">

<button class="primary" style="width:100%;margin-top:8px" onclick="submitModal()">
متابعة
</button>

</div>

</div>

<div class="toast" id="toast"></div>

<script>

let mode='create';
let playing=false;
let room='';
let currentTrailerUrl='';

const $=id=>document.getElementById(id);

/* Orientation handling: when device is landscape on small screens, make the screen float */
function handleOrientationChange(e){
  const screen = $('mainScreen');
  const isLandscape = window.matchMedia('(orientation: landscape)').matches;
  if(isLandscape && window.innerWidth < 900){
    // Make the screen floating (handled via CSS media query), but we can add class or other UI tweaks
    screen.classList.add('landscape-floating');
    showToast('وضع عرضي — الشاشة عائمة');
  }else{
    screen.classList.remove('landscape-floating');
    showToast('وضع طولي');
  }
}

// init orientation listener
if(window.matchMedia){
  const mq = window.matchMedia('(orientation: landscape)');
  // older browsers used addListener
  if(mq.addEventListener) mq.addEventListener('change', handleOrientationChange);
  else if(mq.addListener) mq.addListener(handleOrientationChange);
  // call once to set state
  handleOrientationChange();
}

/* Trailer overlay functions */
function openTrailer(url){
  currentTrailerUrl = url || '';
  const overlay = $('trailerOverlay');
  const frame = $('trailerFrame');
  if(!url){
    showToast('لم تُحدّد رابط التتر');
    return;
  }
  // if youtube link, convert watch?v=.. to embed form
  if(url.includes('youtube.com/watch')){
    const id = url.split('v=')[1]?.split('&')[0];
    if(id) url = 'https://www.youtube.com/embed/' + id + '?autoplay=1';
  } else if(url.includes('youtu.be/')){
    const id = url.split('youtu.be/')[1].split('?')[0];
    url = 'https://www.youtube.com/embed/' + id + '?autoplay=1';
  }
  frame.src = url;
  overlay.classList.add('show');
  overlay.setAttribute('aria-hidden','false');
  showToast('فتح التتر عائماً');
}

function openTrailerPrompt(){
  const url = prompt('ألصق رابط التتر (مثال: رابط يوتيوب أو صفحة تريلر):');
  if(url) openTrailer(url.trim());
}

function closeTrailer(){
  const overlay = $('trailerOverlay');
  const frame = $('trailerFrame');
  frame.src = '';
  overlay.classList.remove('show');
  overlay.setAttribute('aria-hidden','true');
  showToast('أقفلت التتر');
}

function toggleTrailerFullscreen(){
  const screen = $('mainScreen');
  const overlay = $('trailerOverlay');
  // toggle fullscreen class on main screen for demo: if trailer open, make trailer fullscreen
  if(screen.classList.contains('fullscreen')){
    screen.classList.remove('fullscreen');
    overlay.classList.remove('trailer-full');
  }else{
    screen.classList.add('fullscreen');
    overlay.classList.add('trailer-full');
  }
}

/* Share function: can share room code or current trailer URL */
async function shareRoomOrTrailer(type){
  if(type === 'room'){
    const code = $('roomCode').textContent;
    if(!code || code==='------'){ showToast('أنشئ الغرفة أولًا'); return; }
    const shareData = {
      title: 'غرفة سينما',
      text: 'انضموا لغرفة السينما: ' + code,
      url: location.href + '?room=' + encodeURIComponent(code)
    };
    try{
      if(navigator.share){
        await navigator.share(shareData);
      }else{
        await navigator.clipboard.writeText(shareData.url);
        showToast('تم نسخ رابط الغرفة');
      }
    }catch(err){
      await navigator.clipboard.writeText(shareData.url);
      showToast('تم نسخ رابط الغرفة (نسخة احتياطية)');
    }
  }else if(type === 'trailer'){
    if(!currentTrailerUrl){
      showToast('لا يوجد تتر مفتوح للمشاركة');
      return;
    }
    try{
      if(navigator.share){
        await navigator.share({
          title: 'تتر الفيلم',
          text: 'شوفوا التتر:',
          url: currentTrailerUrl
        });
      }else{
        await navigator.clipboard.writeText(currentTrailerUrl);
        showToast('تم نسخ رابط التتر');
      }
    }catch(err){
      await navigator.clipboard.writeText(currentTrailerUrl);
      showToast('تم نسخ رابط التتر (نسخة احتياطية)');
    }
  }
}

/* Existing functions (slightly adapted) */
function openModal(m){
mode=m;
$('modal').classList.add('show');
$('modalTitle').textContent=
m==='create'
?'🎬 إنشاء غرفة'
:'🔗 دخول إلى غرفة';
$('modalText').textContent=
m==='create'
?'اكتب اسمك حتى ننشئ غرفتك.'
:'اكتب اسمك وكود الغرفة حتى تدخل.';
$('codeInput').style.display=
m==='create'
?'none'
:'block';
}
function closeModal(){ $('modal').classList.remove('show'); }
function submitModal(){
let name=$('nameInput').value.trim()||'مصطفى';
if(mode==='create'){
room=Math.random().toString(36).slice(2,8).toUpperCase();
$('roomCode').textContent=room;
showToast('تم إنشاء الغرفة 🎬');
}else{
room=$('codeInput').value.trim().toUpperCase()||'DEMO01';
$('roomCode').textContent=room;
showToast('دخلت الغرفة ❤️');
$('zahraStatus').textContent='متصلة الآن';
}
closeModal();
}
function copyRoom(){
let c=$('roomCode').textContent;
if(c==='------'){ showToast('أنشئ غرفة أولًا'); return; }
navigator.clipboard?.writeText(c);
showToast('تم نسخ كود الغرفة 📋');
}
function setMovie(){
let m=prompt('اكتب اسم الفيلم أو المسلسل:');
if(m){ $('movieName').textContent=m; showToast('تم اختيار '+m+' 🎬'); }
}
function togglePlay(){
playing=!playing;
$('playBtn').textContent= playing?'⏸':'▶';
$('syncBtn').textContent= playing?'⏸️ إيقاف':'▶️ تشغيل';
$('status').textContent= playing?'جاري المشاهدة 🍿':'متوقف مؤقتًا';
}
function openSource(){
const screen=document.querySelector('.screen');
screen.innerHTML=`
<iframe
id="cinemanaFrame"
src="https://cinemana.shabakaty.com/page/home"
title="Cinemana"
style="
position:absolute;
inset:0;
width:100%;
height:100%;
border:0;
border-radius:20px;
background:#050611
">
</iframe>
<div style="
position:absolute;
top:10px;
right:10px;
z-index:3;
display:flex;
gap:7px
">
<button onclick="closeSource()" style="padding:9px 12px;border-radius:11px;border:1px solid #ffffff22;background:#090b18dd;color:#fff;font-weight:800">✕ إغلاق</button>
<button onclick="reloadSource()" style="padding:9px 12px;border-radius:11px;border:1px solid #ffffff22;background:#090b18dd;color:#fff;font-weight:800">↻ تحديث</button>
</div>
`;
showToast('جاري فتح Cinemana داخل شاشة المشاهدة 🌐');
}
function reloadSource(){ const f=document.getElementById('cinemanaFrame'); if(f) f.src=f.src; }
function closeSource(){
const screen=document.querySelector('.screen');
screen.innerHTML=`
<button class="play" onclick="togglePlay()" id="playBtn">▶</button>
<div class="screenTitle">
<span class="tag" id="movieName">ما مختارين فيلم بعد</span>
<span class="tag" id="status">جاهز للمشاهدة</span>
</div>
`;
showToast('رجعنا لشاشة السينما 🎬');
}
function sendMsg(e){ e.preventDefault(); let i=$('chatInput'); let v=i.value.trim(); if(!v)return; let d=document.createElement('div'); d.className='msg me'; d.textContent=v; $('chat').appendChild(d); i.value=''; $('chat').scrollTop=$('chat').scrollHeight; }
function vote(x){ let id= x==='فيلم رومانسي'?'v1' : x==='أكشن'?'v2' :'v3'; $(id).textContent=+$(id).textContent+1; showToast('تم التصويت لـ '+x+' ❤️'); }
function rps(){ let a=['✊','📄','✂️']; let x=a[Math.floor(Math.random()*a.length)]; showToast('اختيارك العشوائي: '+x); }
function guess(){ let q=['🧙‍♂️ فيلم عن ساحر مشهور','🚢 قصة حب على سفينة','🦁 أمير صغير في مملكة']; showToast(q[Math.floor(Math.random()*q.length)]); }
function showToast(t){ let x=$('toast'); x.textContent=t; x.classList.add('show'); clearTimeout(window.tt); window.tt=setTimeout(()=>x.classList.remove('show'),2200); }

</script>

</body>
</html>
