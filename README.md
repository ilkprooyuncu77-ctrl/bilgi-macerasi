
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
<title>Bilgi Macerası</title>
<style>
*{box-sizing:border-box}
:root{--purple:#7858e9;--dark:#29304d;--mint:#83f0c6}
body{margin:0;background:#c9f5ed;color:var(--dark);font-family:system-ui,Arial;overscroll-behavior:none}
button{font:inherit;touch-action:manipulation;cursor:pointer}
#app{max-width:1000px;margin:auto;min-height:100dvh;padding:12px}
header{display:flex;align-items:center;justify-content:space-between;gap:8px;flex-wrap:wrap;margin-bottom:10px}
.logo{font-size:clamp(20px,4vw,30px);font-weight:1000}
.pill{background:white;border-radius:14px;padding:8px 12px;font-weight:800;box-shadow:0 3px #d5d2eb}
.screen{display:none}
.screen.active{display:block}
.panel{background:#ffffffed;border:3px solid white;border-radius:24px;padding:clamp(15px,4vw,28px);box-shadow:0 8px 0 #b6d9d5}
h1{font-size:clamp(28px,6vw,45px);line-height:1.1;margin:8px 0 12px}
p{line-height:1.55}
.primary,.secondary{border:0;border-radius:15px;padding:13px 18px;font-weight:900}
.primary{background:var(--purple);color:white;box-shadow:0 5px #533ab3}
.secondary{background:white;color:var(--dark);box-shadow:0 4px #d4d1e9}
.primary:active,.secondary:active{transform:translateY(3px);box-shadow:none}
.center{text-align:center}
.monsters{display:flex;justify-content:center;align-items:end;gap:16px;margin:20px 0}
.monster{width:85px;height:95px;position:relative;border:4px solid #30334c;border-radius:45% 45% 35% 35%;box-shadow:inset -8px -8px #0001,0 5px #30334c20}
.monster:before,.monster:after{content:"";position:absolute;background:#ff9ab8;width:10px;height:12px;top:57px;border-radius:50%}
.monster:before{left:5px}.monster:after{right:5px}
.eye{position:absolute;top:20px;width:24px;height:29px;background:white;border:3px solid #30334c;border-radius:50%}
.eye:after{content:"";position:absolute;background:#30334c;width:8px;height:11px;border-radius:50%;top:6px;left:6px}
.three .eye:nth-child(1){left:3px}.three .eye:nth-child(2){left:28px}.three .eye:nth-child(3){left:53px}
.one .eye{left:26px;top:24px;width:30px;height:34px}
.tall{height:130px;width:76px;border-radius:45% 45% 30% 30%}
.tall .eye:nth-child(1){left:5px;top:32px}.tall .eye:nth-child(2){left:39px;top:32px}
.mouth{position:absolute;top:63px;left:50%;transform:translateX(-50%);width:22px;height:10px;border-bottom:4px solid #30334c;border-radius:50%}
.tall .mouth{top:77px}
.choices{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:10px;margin:18px 0}
.choice{background:#fff;border:4px solid transparent;border-radius:18px;padding:12px 3px;min-width:0;box-shadow:0 4px #ddd9f0}
.choice.selected{border-color:var(--purple);background:#f1edff}
.choice .monster{margin:0 auto 10px;transform:scale(.8)}
.choice strong,.choice small{display:block}
.choice small{font-size:11px;color:#71758b}
#worldWrap{position:relative}
#world{display:block;width:100%;height:auto;border:4px solid white;border-radius:20px;background:#a8ebcf;box-shadow:0 6px #b2d9d3;touch-action:none}
.hud{display:flex;justify-content:space-between;gap:8px;flex-wrap:wrap;margin:8px 0}
.hint{background:#fff;border-radius:12px;padding:9px 12px;font-size:13px;font-weight:800}
.controls{display:flex;justify-content:space-between;align-items:center;gap:15px;margin-top:12px;user-select:none}
.pad{display:grid;grid-template-columns:repeat(3,48px);grid-template-rows:repeat(2,44px);gap:4px}
.ctrl{border:0;border-radius:13px;background:white;color:#34324f;font-size:21px;font-weight:1000;box-shadow:0 4px #b9b6d6;touch-action:none}
.ctrl:active,.ctrl.down{background:#dcd5ff;transform:translateY(3px);box-shadow:none}
.pad .up{grid-column:2}.pad .left{grid-column:1;grid-row:2}.pad .down{grid-column:2;grid-row:2}.pad .right{grid-column:3;grid-row:2}
.actions{display:flex;gap:8px;flex-wrap:wrap;justify-content:end}
.actions .ctrl{font-size:13px;padding:10px;min-width:74px;height:58px}
#quiz{position:fixed;inset:0;background:#1f2449a8;z-index:10;display:none;align-items:center;justify-content:center;padding:14px}
#quiz.show{display:flex}
.quizbox{width:min(520px,100%);max-height:90dvh;overflow:auto;background:#fff;border:4px solid white;border-radius:24px;padding:22px;box-shadow:0 15px 45px #15173555}
#answers{display:grid;gap:9px;margin-top:15px}
.answer{padding:13px;text-align:left;border:2px solid #e3e0f4;background:#f8f7ff;border-radius:13px;font-weight:800}
.answer.good{background:#d7ffeb;border-color:#48bf8e}
.answer.bad{background:#ffe0e9;border-color:#ff81a2}
#notice{font-weight:900;min-height:24px;margin-top:12px}
#toast{position:fixed;left:50%;bottom:16px;transform:translateX(-50%);background:#30334c;color:white;padding:12px 18px;border-radius:15px;display:none;z-index:20;text-align:center;max-width:90%;font-weight:800}
#finish{padding:30px 0}
footer{text-align:center;font-size:12px;color:#58667b;margin:18px 0}
@media(max-width:480px){
#app{padding:8px}.choices{gap:5px}.choice{padding:8px 2px}.choice .monster{transform:scale(.66);margin-bottom:0}.choice strong{font-size:13px}.choice small{font-size:10px}
.pad{grid-template-columns:repeat(3,43px);grid-template-rows:repeat(2,40px)}
.controls{gap:6px}.actions{gap:5px}.actions .ctrl{min-width:62px;padding:7px;font-size:11px}
}
</style>
</head>
<body>
<div id="app">
<header>
  <div class="logo">⭐ Bilgi Macerası</div>
  <div class="pill">📚 7. Sınıf Türkçe</div>
</header>

<section id="home" class="screen active">
<div class="panel center">
  <div style="font-size:45px">🌈 🗝️ ⭐</div>
  <h1>Gizemli Bilgi Dünyası!</h1>
  <p>Canavarını seç, yıldızları topla, hazine sandıklarını aç ve Türkçe sorularıyla gizemli kapılardan geç!</p>
  <div class="monsters">
    <div class="monster three" style="background:#ffbd68"><i class="eye"></i><i class="eye"></i><i class="eye"></i><i class="mouth"></i></div>
    <div class="monster one" style="background:#83e7bd"><i class="eye"></i><i class="mouth"></i></div>
    <div class="monster tall" style="background:#ff91bb"><i class="eye"></i><i class="eye"></i><i class="mouth"></i></div>
  </div>
  <p>🕹️ Telefonda dokunmatik düğmeler, bilgisayarda yön tuşları veya WASD!</p>
  <button class="primary" onclick="goSelect()">OYUNA BAŞLA 🚀</button>
</div>
</section>

<section id="select" class="screen">
<div class="panel center">
  <h1>Canavarını seç!</h1>
  <p>Hangisi senin macera arkadaşın olacak?</p>
  <div class="choices">
    <button class="choice selected" onclick="pick(0)" id="c0">
      <div class="monster three" style="background:#ffbd68"><i class="eye"></i><i class="eye"></i><i class="eye"></i><i class="mouth"></i></div>
      <strong>Üçgöz</strong><small>Turuncu dost</small>
    </button>
    <button class="choice" onclick="pick(1)" id="c1">
      <div class="monster one" style="background:#83e7bd"><i class="eye"></i><i class="mouth"></i></div>
      <strong>Tekgöz</strong><small>Yeşil dost</small>
    </button>
    <button class="choice" onclick="pick(2)" id="c2">
      <div class="monster tall" style="background:#ff91bb"><i class="eye"></i><i class="eye"></i><i class="mouth"></i></div>
      <strong>Uzuniki</strong><small>Pembe dost</small>
    </button>
  </div>
  <button class="secondary" onclick="show('home')">Geri</button>
  <button class="primary" onclick="begin()">MACERAYA GİR! ✨</button>
</div>
</section>

<section id="play" class="screen">
<div class="hud">
  <div class="pill" id="level">🗺️ Oda 1</div>
  <div class="pill" id="stars">⭐ 0</div>
  <div class="pill" id="keys">🗝️ 0</div>
</div>
<div id="worldWrap">
<canvas id="world" width="640" height="440" aria-label="Canavarını hareket ettirdiğin oyun alanı"></canvas>
</div>
<div class="controls">
  <div class="pad" aria-label="Hareket kontrolleri">
    <button class="ctrl up" data-dir="up">▲</button>
    <button class="ctrl left" data-dir="left">◀</button>
    <button class="ctrl down" data-dir="down">▼</button>
    <button class="ctrl right" data-dir="right">▶</button>
  </div>
  <div class="actions">
    <button class="ctrl" onclick="interact()">✋<br>ETKİLEŞ</button>
    <button class="ctrl" onclick="showHelp()">❔<br>YARDIM</button>
  </div>
</div>
<div class="hint" style="margin-top:10px">🎯 Yıldızları topla! 🧰 Sandıklara yaklaş ve ETKİLEŞ düğmesine bas. 🚪 Kapıyı açmak için anahtarı bul.</div>
</section>

<section id="finish" class="screen">
<div class="panel center" id="finishContent"></div>
</section>
<footer>Bilgi Macerası • Keşfet, öğren, eğlen! ✨</footer>
</div>

<div id="quiz">
<div class="quizbox">
<div class="pill" id="quizTopic">Türkçe sorusu</div>
<h2 id="quizQuestion"></h2>
<div id="answers"></div>
<div id="notice" aria-live="polite"></div>
<button id="quizNext" class="primary" style="display:none;margin-top:12px" onclick="closeQuiz()">DEVAM ET →</button>
</div>
</div>
<div id="toast"></div>

<script>
const canvas=document.getElementById('world');
const ctx=canvas.getContext('2d');
const W=640,H=440;
let chosen=0,room=0,stars=0,keys=0,player={x:70,y:70};
let held={},items=[],doorOpen=false,quizItem=null,answered=false,toastTimer;
const colors=['#ffbd68','#83e7bd','#ff91bb'];
const names=['Üçgöz','Tekgöz','Uzuniki'];
const questions=[
{topic:'SÖZCÜKTE ANLAM',q:'“Neşeli” sözcüğünün eş anlamlısı hangisidir?',a:['Mutlu','Kızgın','Yorgun','Üzgün'],c:0},
{topic:'DEYİMLER',q:'“Etekleri zil çalmak” ne demektir?',a:['Korkmak','Çok sevinmek','Yorulmak','Şaşırmak'],c:1},
{topic:'NOKTALAMA',q:'Hangi cümlenin sonuna soru işareti gelir?',a:['Bugün hava güzel','Eyvah, geç kaldım','Saat kaç oldu','Yaşasın, kazandık'],c:2},
{topic:'FİİLLER',q:'“Mert kitap okuyor.” cümlesindeki fiil hangisidir?',a:['Mert','Kitap','Okuyor','Cümle'],c:2},
{topic:'ZIT ANLAM',q:'“Cömert” sözcüğünün zıt anlamlısı hangisidir?',a:['Dürüst','Cimri','Neşeli','Nazik'],c:1},
{topic:'ATASÖZLERİ',q:'“Damlaya damlaya göl olur.” ne anlatır?',a:['Küçük birikimler zamanla büyür','Su her zaman soğuktur','Hızlı koşmak gerekir','Her iş zordur'],c:0},
{topic:'İSİMLER',q:'Hangisi özel isimdir?',a:['Kalem','Şehir','Ankara','Okul'],c:2},
{topic:'CÜMLE ANLAMI',q:'“Yağmur yağdığı için maç ertelendi.” hangi anlam ilişkisi vardır?',a:['Benzetme','Karşılaştırma','Neden-sonuç','Koşul'],c:2},
{topic:'YAZIM KURALLARI',q:'Hangi cümle doğru yazılmıştır?',a:['ayşe geldi.','Ayşe geldi.','Ayşe Geldi.','ayşe Geldi.'],c:1},
{topic:'SÖZ SANATLARI',q:'“Aslan gibi güçlü.” ifadesinde hangi söz sanatı vardır?',a:['Benzetme','Abartma','Kişileştirme','Konuşturma'],c:0},
{topic:'ZARFLAR',q:'“Çocuk hızlı koştu.” cümlesinde “hızlı” neyi belirtir?',a:['Kişi','Zaman','Nasıl koştuğunu','Yeri'],c:2},
{topic:'NEDEN-SONUÇ',q:'Hangisi neden-sonuç cümlesidir?',a:['Kitap almak için çıktım','Çok yorulduğum için dinlendim','Belki yarın gelirim','Daha çok çalışmalısın'],c:1}
];
function show(id){document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));document.getElementById(id).classList.add('active')}
function goSelect(){show('select')}
function pick(i){chosen=i;for(let n=0;n<3;n++)document.getElementById('c'+n).classList.toggle('selected',n===i)}
function begin(){room=0;stars=0;keys=0;setupRoom();show('play')}
function rand(min,max){return Math.random()*(max-min)+min}
function setupRoom(){
 player={x:55,y:55};doorOpen=false;
 items=[];
 const used=[];
 function add(type,x,y){items.push({type,x,y,got:false})}
 // Odada yıldızlar, sandık, anahtar ve kapı
 for(let i=0;i<4;i++)add('star',rand(100,540),rand(80,350));
 add('chest',rand(200,430),rand(130,300));
 add('key',rand(120,500),rand(100,330));
 add('door',590,220);
 document.getElementById('level').textContent='🗺️ Oda '+(room+1);
 updateHud();draw();
}
function updateHud(){
 document.getElementById('stars').textContent='⭐ '+stars;
 document.getElementById('keys').textContent='🗝️ '+keys;
}
function rounded(x,y,w,h,r,fill){
 ctx.fillStyle=fill;ctx.beginPath();ctx.roundRect(x,y,w,h,r);ctx.fill();
}
function draw(){
 ctx.clearRect(0,0,W,H);
 ctx.fillStyle='#a9edcf';ctx.fillRect(0,0,W,H);
 // Çimen desenleri
 for(let y=20;y<H;y+=36)for(let x=15;x<W;x+=43){
 ctx.fillStyle=(x+y)%2?'#8be0bb':'#bdf4d8';
 ctx.beginPath();ctx.arc(x,y,2,0,Math.PI*2);ctx.fill();
 }
 // Yol
 ctx.fillStyle='#f5e7bd';ctx.beginPath();ctx.moveTo(0,350);ctx.lineTo(210,260);ctx.lineTo(450,320);ctx.lineTo(640,265);ctx.lineTo(640,440);ctx.lineTo(0,440);ctx.fill();
 // Dekoratif çalılar
 [[60,300],[170,100],[500,85],[480,365],[270,380]].forEach(([x,y])=>{
 ctx.fillStyle='#52c79b';ctx.beginPath();ctx.arc(x,y,18,0,Math.PI*2);ctx.fill();
 ctx.fillStyle='#6bdca9';ctx.beginPath();ctx.arc(x-8,y-6,12,0,Math.PI*2);ctx.fill();
 });
 // Oda başlığı
 rounded(12,10,180,30,10,'#ffffffd9');
 ctx.fillStyle='#30334c';ctx.font='bold 14px system-ui';ctx.fillText('BİLGİ ORMANI · '+(room+1),22,30);
 for(const it of items){
 if(it.got)continue;
 if(it.type==='star'){
 ctx.save();ctx.translate(it.x,it.y);ctx.fillStyle='#ffcf4d';ctx.strokeStyle='#fff8d4';ctx.lineWidth=3;
 ctx.beginPath();for(let i=0;i<10;i++){let a=-Math.PI/2+i*Math.PI/5,r=i%2?7:14;ctx.lineTo(Math.cos(a)*r,Math.sin(a)*r)}ctx.closePath();ctx.fill();ctx.stroke();ctx.restore();
 }else if(it.type==='key'){
 ctx.strokeStyle='#ffcf4d';ctx.lineWidth=6;ctx.beginPath();ctx.arc(it.x-5,it.y,8,0,Math.PI*2);ctx.moveTo(it.x+3,it.y);ctx.lineTo(it.x+19,it.y);ctx.lineTo(it.x+19,it.y+7);ctx.stroke();
 }else if(it.type==='chest'){
 rounded(it.x-20,it.y-14,40,28,6,'#a9673c');rounded(it.x-20,it.y-14,40,11,5,'#edb55e');ctx.fillStyle='#ffe17c';ctx.fillRect(it.x-3,it.y-2,7,10);
 }else if(it.type==='door'){
 rounded(it.x-22,it.y-36,44,72,8,doorOpen?'#7dddb0':'#8061df');
 ctx.fillStyle='white';ctx.font='bold 22px system-ui';ctx.fillText(doorOpen?'✓':'?',it.x-7,it.y+7);
 }
 }
 drawMonster(player.x,player.y);
 // Hedef ipucu
 ctx.fillStyle='#30334c';ctx.font='bold 12px system-ui';
 ctx.fillText('★ Yıldız topla',15,H-14);
}
function drawMonster(x,y){
 ctx.save();ctx.translate(x,y);
 // gölge
 ctx.fillStyle='#35465b25';ctx.beginPath();ctx.ellipse(0,20,22,8,0,0,Math.PI*2);ctx.fill();
 ctx.fillStyle=colors[chosen];ctx.strokeStyle='#30334c';ctx.lineWidth=3;
 ctx.beginPath();
 if(chosen===2){ctx.roundRect(-16,-29,32,51,13)}
 else{ctx.ellipse(0,-4,23,25,0,0,Math.PI*2)}
 ctx.fill();ctx.stroke();
 const eye=(ex,ey,scale=1)=>{
 ctx.fillStyle='white';ctx.strokeStyle='#30334c';ctx.lineWidth=2;
 ctx.beginPath();ctx.ellipse(ex,ey,7*scale,9*scale,0,0,Math.PI*2);ctx.fill();ctx.stroke();
 ctx.fillStyle='#30334c';ctx.beginPath();ctx.arc(ex+1,ey+1,3*scale,0,Math.PI*2);ctx.fill();
 };
 if(chosen===0){eye(-13,-13,.75);eye(0,-19,.75);eye(13,-13,.75)}
 if(chosen===1)eye(0,-12,1.2);
 if(chosen===2){eye(-8,-14,.75);eye(8,-14,.75)}
 ctx.strokeStyle='#30334c';ctx.lineWidth=2;ctx.beginPath();ctx.arc(0,3,7,0.2,Math.PI-0.2);ctx.stroke();
 ctx.restore();
}
function toast(msg){
 const t=document.getElementById('toast');t.textContent=msg;t.style.display='block';
 clearTimeout(toastTimer);toastTimer=setTimeout(()=>t.style.display='none',1800);
}
function near(it){return Math.hypot(player.x-it.x,player.y-it.y)<42}
function interact(){
 const door=items.find(i=>i.type==='door'&&!i.got);
 if(door&&near(door)){
 if(!doorOpen){
 if(keys>0){keys--;doorOpen=true;door.got=true;updateHud();toast('🗝️ Kapı açıldı! Harika!');draw();setTimeout(openQuestion,450)}
 else toast('🔎 Önce odadaki anahtarı bul!');
 }else openQuestion();
 return;
 }
 const chest=items.find(i=>i.type==='chest'&&!i.got);
 if(chest&&near(chest)){
 chest.got=true;stars+=3;updateHud();toast('🎁 Hazine! 3 yıldız kazandın!');draw();return;
 }
 const key=items.find(i=>i.type==='key'&&!i.got);
 if(key&&near(key)){key.got=true;keys++;updateHud();toast('🗝️ Anahtarı buldun!');draw();return}
 toast('Bir sandığa, anahtara veya kapıya yaklaş!');
}
function showHelp(){toast('Yıldızları topla. Anahtarı bul. Sandığı aç. Kapıya yaklaş ve ETKİLEŞ düğmesine bas!')}
function openQuestion(){
 quizItem=questions[room%questions.length];answered=false;
 document.getElementById('quizTopic').textContent=quizItem.topic;
 document.getElementById('quizQuestion').textContent=quizItem.q;
 document.getElementById('notice').textContent='';
 document.getElementById('quizNext').style.display='none';
 const box=document.getElementById('answers');box.innerHTML='';
 quizItem.a.forEach((a,i)=>{
 const b=document.createElement('button');b.className='answer';b.textContent=String.fromCharCode(65+i)+') '+a;
 b.onclick=()=>answerQuestion(i,b);box.appendChild(b);
 });
 document.getElementById('quiz').classList.add('show');
}
function answerQuestion(i,b){
 if(answered)return;answered=true;
 const buttons=[...document.querySelectorAll('.answer')];
 buttons.forEach(x=>x.disabled=true);
 const notice=document.getElementById('notice');
 if(i===quizItem.c){b.classList.add('good');stars+=5;notice.textContent='🎉 Doğru! 5 yıldız kazandın!';}
 else{b.classList.add('bad');buttons[quizItem.c].classList.add('good');notice.textContent='💡 Doğru cevap yeşil renkte. Sonraki odada tekrar dene!';}
 updateHud();document.getElementById('quizNext').style.display='inline-block';
}
function closeQuiz(){
 document.getElementById('quiz').classList.remove('show');
 if(room>=9){
 show('finish');
 document.getElementById('finishContent').innerHTML=
 '<div style="font-size:70px">🏆</div><h1>Macera tamamlandı!</h1><p>10 odayı keşfettin ve '+stars+' yıldız topladın!</p><p>Canavarın: '+names[chosen]+'</p><button class="primary" onclick="begin()">TEKRAR OYNA ↻</button>';
 }else{
 room++;setupRoom();toast('🌟 Yeni oda! Daha fazla yıldız seni bekliyor!');
 }
}
function move(dx,dy){
 player.x=Math.max(25,Math.min(W-28,player.x+dx));
 player.y=Math.max(45,Math.min(H-25,player.y+dy));
 for(const it of items){
 if(it.got||it.type!=='star')continue;
 if(Math.hypot(player.x-it.x,player.y-it.y)<24){
 it.got=true;stars++;updateHud();toast('⭐ Yıldız kazandın!');
 }
 }
 draw();
}
function tick(){
 if(!document.getElementById('play').classList.contains('active'))return;
 let dx=0,dy=0;
 if(held.left||held.ArrowLeft||held.a)dx-=2.6;
 if(held.right||held.ArrowRight||held.d)dx+=2.6;
 if(held.up||held.ArrowUp||held.w)dy-=2.6;
 if(held.down||held.ArrowDown||held.s)dy+=2.6;
 if(dx&&dy){dx*=.707;dy*=.707}
 if(dx||dy)move(dx,dy);
 requestAnimationFrame(tick);
}
document.querySelectorAll('[data-dir]').forEach(btn=>{
 const dir=btn.dataset.dir;
 const down=e=>{e.preventDefault();held[dir]=true;btn.classList.add('down')};
 const up=e=>{e.preventDefault();held[dir]=false;btn.classList.remove('down')};
 btn.addEventListener('pointerdown',down);
 btn.addEventListener('pointerup',up);
 btn.addEventListener('pointercancel',up);
 btn.addEventListener('lostpointercapture',up);
});
window.addEventListener('keydown',e=>{
 const k=e.key.length===1?e.key.toLowerCase():e.key;
 if(['ArrowUp','ArrowDown','ArrowLeft','ArrowRight',' '].includes(e.key))e.preventDefault();
 held[k]=true;
 if(e.key==='Enter')interact();
});
window.addEventListener('keyup',e=>{const k=e.key.length===1?e.key.toLowerCase():e.key;held[k]=false});
window.addEventListener('blur',()=>held={});
function startLoop(){requestAnimationFrame(tick)}
startLoop();
</script>
</body>
</html>
