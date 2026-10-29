
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>Bilgi Macerası: Kayıp Kristaller</title>
<style>
:root{--gold:#ffdc70;--panel:#172a40;--edge:#36536b;--mint:#91f5c2}
*{box-sizing:border-box}
body{margin:0;background:#0b1729;color:white;font-family:system-ui,Arial,sans-serif;overscroll-behavior:none}
button{border:0;border-radius:14px;padding:12px 16px;font-size:16px;font-weight:800;cursor:pointer;touch-action:manipulation;color:#18253a;background:var(--gold)}
button:active{transform:scale(.97)}
button:focus-visible{outline:3px solid white}
.hidden{display:none!important}
header{display:flex;justify-content:space-between;align-items:center;gap:10px;flex-wrap:wrap;padding:12px max(12px,calc((100% - 1120px)/2));background:#132238;border-bottom:2px solid #31465e}
.logo{font-size:20px;font-weight:1000;color:var(--gold)}
.stats{display:flex;gap:8px;flex-wrap:wrap}
.pill{padding:7px 12px;background:#263b52;border:1px solid #496078;border-radius:12px;font-weight:800}
main{max-width:1120px;margin:auto;padding:14px}
.panel{background:linear-gradient(145deg,#203952,#15273b);border:2px solid var(--edge);border-radius:22px;padding:20px;box-shadow:0 12px 30px #0003}
h1,h2,p{margin-top:0}
h1{font-size:clamp(28px,5vw,48px);color:var(--gold);line-height:1.1}
h2{color:#fff0b7}
.muted{color:#c1d1e2;line-height:1.6}
.character-list{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin:22px 0}
.character-card{width: min(30%,180px);min-width:100px;background:#263e55;color:white;border:2px solid #45627c;padding:14px 6px}
.character-card.chosen{border-color:var(--gold);background:#40556c;box-shadow:0 0 0 3px #ffdc7033}
.big-avatar{font-size:68px;display:block;margin:4px}
#gameLayout{display:grid;grid-template-columns:minmax(0,1fr);gap:12px}
#stage{position:relative;overflow:hidden;border:3px solid #4c7182;border-radius:20px;background:#a4db96;box-shadow:0 14px 35px #0005}
canvas{display:block;width:100%;height:auto;touch-action:none}
#hint{position:absolute;top:10px;left:10px;right:10px;text-align:center;color:#173149;font-size:13px;font-weight:900;text-shadow:0 1px white;pointer-events:none}
.bottom{display:grid;grid-template-columns:1fr;gap:12px;margin-top:12px}
.card{background:#182c42;border:2px solid #344f67;border-radius:18px;padding:15px}
.card h3{margin:0 0 8px;color:var(--gold)}
.actionrow{display:flex;gap:8px;flex-wrap:wrap}
.actionrow button{flex:1;min-width:120px}
.movegrid{display:grid;grid-template-columns:repeat(3,52px);grid-template-rows:repeat(2,45px);gap:5px;justify-content:center}
.movegrid button{padding:2px;font-size:23px;background:#365570;color:white}
.movegrid .up{grid-column:2;grid-row:1}.movegrid .left{grid-column:1;grid-row:2}.movegrid .down{grid-column:2;grid-row:2}.movegrid .right{grid-column:3;grid-row:2}
.inventory{display:flex;gap:8px;flex-wrap:wrap}
.slot{min-width:72px;text-align:center;padding:9px 7px;background:#263b51;border:1px solid #52677d;border-radius:12px}
.slot span{display:block;font-size:27px}
#overlay{position:fixed;inset:0;background:#06111ee8;z-index:10;display:flex;align-items:center;justify-content:center;padding:14px;overflow:auto}
.dialog{width:min(560px,100%);max-height:92dvh;overflow:auto;background:linear-gradient(150deg,#233d58,#14263b);border:2px solid #59748d;border-radius:24px;padding:22px;box-shadow:0 20px 80px #0009}
#answers{display:grid;gap:9px;margin:18px 0}
#answers button{background:#e9f2fa;text-align:left;color:#1c3045;min-height:50px}
#answers button:disabled{opacity:.7}
#feedback{min-height:25px;font-weight:900;line-height:1.5}
.reward{font-size:58px;margin:12px}
.tag{display:inline-block;border-radius:9px;background:#2e4c61;padding:5px 9px;font-size:13px}
footer{text-align:center;color:#9fb5c9;font-size:12px;padding:20px}
@media(min-width:800px){
 #gameLayout{grid-template-columns:minmax(0,1fr) 250px}
 .bottom{grid-template-columns:1fr 1fr}
}
@media(max-width:420px){
 main{padding:8px}.panel{padding:13px}.card{padding:11px}
 .pill{font-size:13px;padding:6px 8px}
 button{font-size:15px;padding:12px}
}
</style>
</head>
<body>
<header>
  <div class="logo">✨ BİLGİ MACERASI</div>
  <div class="stats">
    <div class="pill">⭐ <span id="stars">0</span></div>
    <div class="pill">🪙 <span id="coins">0</span></div>
    <div class="pill">🗺️ <span id="level">1</span>/5</div>
  </div>
</header>

<main>
<section id="welcome" class="panel">
  <span class="tag">7. SINIF • MACERA • EĞLENCE</span>
  <h1>Kayıp Kristaller</h1>
  <p class="muted">Kristaller beş gizemli bölgeye dağıldı! Karakterini seç, dünyayı keşfet, Soru Makinesi'nden ödüller kazan ve hazineleri topla.</p>
  <h2>🧙 Kahramanını seç</h2>
  <div class="character-list">
    <button class="character-card chosen" data-char="0"><span class="big-avatar">👾</span>Turuncu<br><small>Enerjik</small></button>
    <button class="character-card" data-char="1"><span class="big-avatar">👽</span>Yeşil<br><small>Meraklı</small></button>
    <button class="character-card" data-char="2"><span class="big-avatar">🩷</span>Pembe<br><small>Cesur</small></button>
  </div>
  <button id="start" style="width:100%;font-size:20px">🚀 MACERAYA BAŞLA</button>
  <p class="muted" style="text-align:center;margin:14px 0 0">Bilgisayar, telefon ve dokunmatik tahta için tasarlandı.</p>
</section>

<section id="game" class="hidden">
  <div id="gameLayout">
    <div id="stage">
      <canvas id="world" width="900" height="560" aria-label="2 boyutlu macera haritası"></canvas>
      <div id="hint">Yürü, keşfet ve ödülleri topla!</div>
    </div>
    <aside class="card">
      <h3>🧭 Macera günlüğü</h3>
      <p id="mission" class="muted">Sol taraftaki Soru Makinesi'ni bul!</p>
      <div class="actionrow">
        <button id="interact">✋ ETKİLEŞİM</button>
        <button id="wardrobe" style="background:#b7a0ff">👕 KOSTÜMLER</button>
      </div>
      <hr style="border-color:#354d65;margin:16px 0">
      <h3>🎒 Çanta</h3>
      <div id="inventory" class="inventory"></div>
      <p class="muted" style="font-size:12px;margin-top:10px">Ödüllerin burada birikir.</p>
    </aside>
  </div>

  <div class="bottom">
    <div class="card">
      <h3>🎮 Hareket</h3>
      <div class="movegrid">
        <button class="up" data-dir="up">⬆️</button>
        <button class="left" data-dir="left">⬅️</button>
        <button class="down" data-dir="down">⬇️</button>
        <button class="right" data-dir="right">➡️</button>
      </div>
      <p class="muted" style="text-align:center;font-size:12px;margin:8px 0 0">Bilgisayar: WASD veya ok tuşları</p>
    </div>
    <div class="card">
      <h3>🎯 Hedefin</h3>
      <p class="muted">1. Soru Makinesi'ne git.<br>2. Doğru cevap ver.<br>3. Ödülünü kazan.<br>4. Sandığı bul ve kapıdan geç!</p>
    </div>
  </div>
</section>

<section id="ending" class="panel hidden" style="text-align:center">
  <h1>🏆 Büyük Macera Tamamlandı!</h1>
  <div style="font-size:80px">🎉💎🎉</div>
  <h2 id="result"></h2>
  <p class="muted">Harika iş çıkardın! Öğrendiklerin yeni maceralarda da sana yardımcı olacak.</p>
  <button id="restart">🔄 Yeniden oyna</button>
</section>
</main>

<div id="overlay" class="hidden">
  <div class="dialog">
    <div class="tag" id="dialogTag">BİLGİ GÖREVİ</div>
    <h2 id="dialogTitle">🤖 Soru Makinesi</h2>
    <p id="dialogText" class="muted"></p>
    <div id="answers"></div>
    <div id="feedback" aria-live="polite"></div>
    <div class="reward hidden" id="rewardIcon"></div>
    <button id="dialogClose" class="hidden" style="width:100%">Devam et ➜</button>
  </div>
</div>

<footer>Bilgi Macerası • Öğrenerek keşfet! ✨</footer>

<script>
const $=id=>document.getElementById(id);
const canvas=$("world"),ctx=canvas.getContext("2d");
let chosen=0,level=0,stars=0,coins=0,score=0,playing=false;
let player={x:445,y:300},items=[],inventory=[],ownedCostumes=[],costume="Normal";
let machineUsed=false,chestOpened=false,doorOpen=false,overlayMode="";
let held={},lastMove=0,moveInterval=null;
const names=["Gizemli Orman","Kristal Mağara","Bilim Üssü","Tarih Şehri","Hazine Adası"];
const colors=["#ff9a48","#64db83","#ff86cc"];
const costumes=[
 {name:"Normal",icon:"🙂",type:"costume"},
 {name:"Kral Tacı",icon:"👑",type:"costume"},
 {name:"Büyücü",icon:"🧙",type:"costume"},
 {name:"Uzay Kaskı",icon:"🪖",type:"costume"},
 {name:"Kedi Kulakları",icon:"🐱",type:"costume"},
 {name:"Gökkuşağı",icon:"🌈",type:"costume"},
 {name:"Sihirli Pelerin",icon:"🦸",type:"costume"}
];
const prizes=[
 {name:"Kristal",icon:"💎",type:"item"},
 {name:"Altın Anahtar",icon:"🗝️",type:"item"},
 {name:"Yıldız Asası",icon:"🪄",type:"item"},
 {name:"Kalp",icon:"💖",type:"item"},
 {name:"Büyü Kitabı",icon:"📕",type:"item"},
 {name:"Kral Tacı",icon:"👑",type:"costume"},
 {name:"Büyücü Kostümü",icon:"🧙",type:"costume"},
 {name:"Uzay Kaskı",icon:"🪖",type:"costume"},
 {name:"Kedi Kulakları",icon:"🐱",type:"costume"},
 {name:"Gökkuşağı Kostümü",icon:"🌈",type:"costume"}
];
const questions=[
["Türkçe","“Cömert” kelimesinin zıt anlamlısı hangisidir?",["Cimri","Yardımsever","Nazik"],0,"Cömert, eli açık demektir; zıt anlamlısı cimridir."],
["Türkçe","Hangisi çekimli bir fiildir?",["Koşmak","Koşuyor","Koşu"],1,"Koşuyor, zaman ve kişi anlamı taşıyan çekimli bir fiildir."],
["Türkçe","“Etekleri zil çalmak” deyimi ne demektir?",["Çok sevinmek","Çok yorulmak","Kızmak"],0,"Bu deyim çok sevinmek anlamında kullanılır."],
["Matematik","(-7) + 12 işleminin sonucu kaçtır?",["-19","5","-5"],1,"12 - 7 = 5; sonuç pozitiftir."],
["Matematik","1/3 + 1/6 kaçtır?",["2/9","1/2","2/6"],1,"1/3 = 2/6 olduğundan 2/6 + 1/6 = 3/6 = 1/2."],
["Matematik","4x + 3x işleminin sonucu nedir?",["7x","12x","7x²"],0,"Benzer terimlerin katsayıları toplanır: 4x + 3x = 7x."],
["Fen","Hücrenin yönetim merkezi hangisidir?",["Çekirdek","Hücre zarı","Sitoplazma"],0,"Çekirdek hücrenin yönetim merkezidir."],
["Fen","Kuvvetin birimi hangisidir?",["Metre","Newton","Litre"],1,"Kuvvet Newton ile ölçülür."],
["Fen","Karışımları ayırmada hangisi kullanılabilir?",["Süzme","Ses ölçümü","Işık hızı"],0,"Süzme, uygun katı-sıvı karışımlarını ayırabilir."],
["Sosyal Bilgiler","Geçmişteki olayları inceleyen bilim hangisidir?",["Tarih","Kimya","Geometri"],0,"Tarih, geçmişteki insan faaliyetlerini inceler."],
["Sosyal Bilgiler","Demokratik bir toplumda hangisi önemlidir?",["Katılım","Kuralsızlık","Tek kişinin tüm kararları alması"],0,"Demokraside katılım ve haklara saygı önemlidir."],
["Sosyal Bilgiler","Doğal kaynakları korumak için ne yapmalıyız?",["İsraf","Tasarruf","Hepsini tüketmek"],1,"Kaynakları dikkatli kullanmak gelecek için önemlidir."],
["İngilizce","“Apple” kelimesinin anlamı nedir?",["Elma","Armut","Üzüm"],0,"Apple, elma demektir."],
["İngilizce","“Good morning” ne demektir?",["İyi geceler","İyi sabahlar","Güle güle"],1,"Good morning, iyi sabahlar demektir."],
["İngilizce","“I am a student.” cümlesi ne demektir?",["Ben öğrenciyim.","Ben doktorum.","Ben mutluyum."],0,"I am a student: Ben öğrenciyim."]
];
const rand=(a,b)=>a+Math.random()*(b-a);
function show(id){$(id).classList.remove("hidden")}
function hide(id){$(id).classList.add("hidden")}
function chooseCharacter(n){
 chosen=n;
 document.querySelectorAll(".character-card").forEach(b=>b.classList.toggle("chosen",Number(b.dataset.char)===n));
}
document.querySelectorAll("[data-char]").forEach(b=>b.onclick=()=>chooseCharacter(Number(b.dataset.char)));
$("start").onclick=()=>{
 hide("welcome");hide("ending");show("game");playing=true;
 level=0;stars=0;coins=0;score=0;inventory=[];ownedCostumes=[];costume="Normal";
 startLevel();renderInventory();draw();updateHUD();
};
function startLevel(){
 player={x:445,y:300};machineUsed=false;chestOpened=false;doorOpen=false;
 items=[];
 // Makine solda, sandık sağda, çıkış kapısı en sağda.
 items.push({type:"machine",x:100,y:280});
 items.push({type:"chest",x:660,y:170});
 items.push({type:"door",x:830,y:285});
 for(let i=0;i<7;i++)items.push({type:"star",x:rand(170,740),y:rand(65,490),taken:false});
 $("mission").textContent="Sol taraftaki Soru Makinesi'ne ulaş!";
 updateHUD();
}
function updateHUD(){
 $("stars").textContent=stars;$("coins").textContent=coins;$("level").textContent=level+1;
}
function roundRect(x,y,w,h,r,fill,stroke){
 ctx.beginPath();ctx.roundRect(x,y,w,h,r);ctx.fillStyle=fill;ctx.fill();
 if(stroke){ctx.strokeStyle=stroke;ctx.lineWidth=3;ctx.stroke();}
}
function drawTree(x,y){
 ctx.fillStyle="#75472e";ctx.fillRect(x-8,y+5,16,30);
 ctx.fillStyle="#246e50";
 ctx.beginPath();ctx.arc(x,y,27,0,Math.PI*2);ctx.fill();
 ctx.fillStyle="#3c9c63";
 ctx.beginPath();ctx.arc(x-10,y-8,15,0,Math.PI*2);ctx.fill();
}
function drawMachine(o){
 ctx.save();ctx.translate(o.x,o.y);
 roundRect(-39,-47,78,92,14,"#324d68","#15283c");
 roundRect(-28,-36,56,37,8,"#87f5df","#d4fff4");
 ctx.fillStyle="#183e50";ctx.font="bold 18px Arial";ctx.textAlign="center";ctx.fillText("?",0,-10);
 ctx.fillStyle="#ffda72";ctx.beginPath();ctx.arc(0,19,8,0,Math.PI*2);ctx.fill();
 ctx.fillStyle="#e8f5ff";ctx.font="bold 10px Arial";ctx.fillText("SORU",0,60);
 ctx.restore();
}
function drawChest(o){
 ctx.save();ctx.translate(o.x,o.y);
 roundRect(-28,-17,56,37,7,chestOpened?"#986b44":"#ae692e","#583a26");
 ctx.fillStyle="#f8cf63";ctx.fillRect(-28,-4,56,7);
 ctx.fillStyle="#ffe89a";ctx.fillRect(-5,-6,10,14);
 ctx.restore();
}
function draw(){
 if(!playing)return;
 const w=canvas.width,h=canvas.height;
 ctx.clearRect(0,0,w,h);
 const palettes=[
  ["#a4df98","#8bce82","#d9f0ad"],
  ["#b6a4e8","#9b86d2","#dfd3ff"],
  ["#90d9ed","#78c8df","#d1f5fa"],
  ["#efce8d","#dfb96e","#fff0bc"],
  ["#87d4b2","#6bc39d","#c2f4c8"]
 ];
 const p=palettes[level];
 ctx.fillStyle=p[0];ctx.fillRect(0,0,w,h);
 // Natural-looking ground pattern
 for(let y=12;y<h;y+=35)for(let x=10;x<w;x+=39){
  ctx.fillStyle=((x+y)%3===0)?p[1]:p[2];
  ctx.globalAlpha=.4;ctx.beginPath();ctx.ellipse(x,y,rand(2,4),2,0,0,Math.PI*2);ctx.fill();ctx.globalAlpha=1;
 }
 // Winding path
 ctx.strokeStyle="#e9d8a0";ctx.lineWidth=95;ctx.lineCap="round";
 ctx.beginPath();ctx.moveTo(120,370);ctx.bezierCurveTo(280,470,320,130,470,300);ctx.bezierCurveTo(590,430,690,350,835,285);ctx.stroke();
 ctx.strokeStyle="#d3c18b";ctx.lineWidth=3;ctx.stroke();
 // Decoration away from main objects
 for(const [x,y] of [[35,60],[38,465],[865,65],[870,480],[280,55],[555,500],[735,65]])drawTree(x,y);
 // Little rocks
 for(const [x,y] of [[210,105],[360,455],[530,70],[760,450]]){
  ctx.fillStyle="#8496a1";ctx.beginPath();ctx.ellipse(x,y,16,10,-.3,0,Math.PI*2);ctx.fill();
  ctx.fillStyle="#aebdc5";ctx.beginPath();ctx.ellipse(x-3,y-3,7,3,-.3,0,Math.PI*2);ctx.fill();
 }
 for(const o of items){
  if(o.type==="machine")drawMachine(o);
  if(o.type==="chest"&&!o.taken)drawChest(o);
  if(o.type==="star"&&!o.taken){
   ctx.font="29px Arial";ctx.textAlign="center";ctx.fillText("⭐",o.x,o.y+10);
  }
  if(o.type==="door"){
   roundRect(o.x-27,o.y-58,54,115,10,doorOpen?"#5dcf98":"#72513e","#43332b");
   ctx.fillStyle="#ffdf75";ctx.beginPath();ctx.arc(o.x+13,o.y,4,0,Math.PI*2);ctx.fill();
   ctx.fillStyle="#213b4c";ctx.font="bold 15px Arial";ctx.textAlign="center";ctx.fillText(doorOpen?"AÇIK":"ÇIKIŞ",o.x,o.y-67);
  }
 }
 // Player shadow and original monster
 ctx.fillStyle="#19374744";ctx.beginPath();ctx.ellipse(player.x,player.y+25,25,9,0,0,Math.PI*2);ctx.fill();
 ctx.save();ctx.translate(player.x,player.y);
 ctx.fillStyle=colors[chosen];ctx.strokeStyle="#243749";ctx.lineWidth=4;
 ctx.beginPath();ctx.ellipse(0,0,24,27,0,0,Math.PI*2);ctx.fill();ctx.stroke();
 if(costume==="Kral Tacı")ctx.fillText("👑",0,-29);
 if(costume==="Büyücü")ctx.fillText("🧙",0,-5);
 if(costume==="Uzay Kaskı")ctx.fillText("🪖",0,-5);
 if(costume==="Kedi Kulakları")ctx.fillText("🐱",0,-5);
 if(costume==="Gökkuşağı")ctx.fillText("🌈",0,-5);
 if(costume==="Sihirli Pelerin")ctx.fillText("🦸",0,-5);
 ctx.fillStyle="white";
 for(let i=0;i<(chosen===0?3:chosen===1?1:2);i++){
  const n=chosen===0?3:chosen===1?1:2;
  const ex=(i-(n-1)/2)*13;
  ctx.beginPath();ctx.arc(ex,-5,6.8,0,Math.PI*2);ctx.fill();
  ctx.fillStyle="#1b2b3a";ctx.beginPath();ctx.arc(ex+1,-5,3,0,Math.PI*2);ctx.fill();ctx.fillStyle="white";
 }
 ctx.strokeStyle="#253747";ctx.lineWidth=2.5;
 ctx.beginPath();ctx.arc(0,5,7,.2,Math.PI-.2);ctx.stroke();
 ctx.restore();
 // Nearby interaction indicator
 if(nearby()){
  ctx.strokeStyle="#fff5a8";ctx.lineWidth=3;
  ctx.beginPath();ctx.arc(player.x,player.y,35,0,Math.PI*2);ctx.stroke();
 }
}
function dist(a,b){return Math.hypot(a.x-b.x,a.y-b.y)}
function nearby(){
 return items.find(o=>["machine","chest","door"].includes(o.type)&&!o.taken&&dist(player,o)<83&&
 (o.type!=="door"||!doorOpen))||items.find(o=>o.type==="door"&&dist(player,o)<83);
}
function move(dx,dy){
 if(!playing||!$("overlay").classList.contains("hidden"))return;
 player.x=Math.max(35,Math.min(865,player.x+dx));
 player.y=Math.max(50,Math.min(510,player.y+dy));
 for(const o of items){
  if(o.type==="star"&&!o.taken&&dist(player,o)<32){
   o.taken=true;stars++;coins+=2;score+=10;updateHUD();
  }
 }
 if(doorOpen&&player.x>800){nextLevel();return;}
 if(nearby()){
  const o=nearby();
  $("mission").textContent=o.type==="machine"?"Soru Makinesi hazır! ETKİLEŞİM'e bas.":o.type==="chest"?"Sandık seni bekliyor! ETKİLEŞİM'e bas.":"Kapıdan geçmek için ETKİLEŞİM'e bas.";
 }
 draw();
}
function interact(){
 if(!playing)return;
 const o=nearby();
 if(!o){$("mission").textContent="Bir makineye, sandığa veya kapıya yaklaş.";return;}
 if(o.type==="machine"){
  if(machineUsed){
   openDialog("🤖 Soru Makinesi","Bugünlük sorunu çözdün! Bir sonraki bölümde tekrar gel.",null);
   $("answers").innerHTML="";$("feedback").textContent="";hide("dialogClose");
  }else askQuestion();
 }else if(o.type==="chest"){
  if(chestOpened){
   $("mission").textContent="Bu sandığı zaten açtın. Çıkış kapısına git!";
  }else{
   chestOpened=true;o.taken=true;doorOpen=true;coins+=5;score+=25;
   updateHUD();renderInventory();openDialog("🎁 Hazine Sandığı","Sandığı açtın! 5 altın ve bir kristal kazandın.",null);
   $("answers").innerHTML="";$("feedback").textContent="💎 +5 altın";$("rewardIcon").textContent="💎";show("rewardIcon");show("dialogClose");
  }
 }else if(o.type==="door"){
  if(doorOpen){nextLevel();}
  else $("mission").textContent="Önce sandığı açmalısın!";
 }
 draw();
}
function openDialog(title,text,tag){
 show("overlay");$("dialogTitle").textContent=title;$("dialogText").textContent=text;
 $("dialogTag").textContent=tag||"MACERA GÖREVİ";
 $("answers").innerHTML="";$("feedback").textContent="";
 hide("rewardIcon");hide("dialogClose");overlayMode="";
}
function askQuestion(){
 machineUsed=true;
 const q=questions[Math.floor(Math.random()*questions.length)];
 overlayMode="question";
 openDialog("🤖 Soru Makinesi",q[1],q[0].toUpperCase()+" SORUSU");
 q[2].forEach((answer,i)=>{
  const b=document.createElement("button");
  b.textContent=String.fromCharCode(65+i)+") "+answer;
  b.onclick=()=>{
   [...$("answers").children].forEach(x=>x.disabled=true);
   if(i===q[3]){
    score+=30;coins+=3;
    $("feedback").textContent="🎉 Doğru cevap! +30 puan, +3 altın.";
    $("feedback").style.color="#91f5c2";
    const prize=prizes[Math.floor(Math.random()*prizes.length)];
    givePrize(prize);
    $("rewardIcon").textContent=prize.icon;
    show("rewardIcon");
    $("dialogText").textContent=q[4];
    $("mission").textContent="Ödülünü kazandın! Sandığı bul.";
   }else{
    score+=5;
    $("feedback").textContent="📚 Doğru cevap: "+q[2][q[3]]+".";
    $("feedback").style.color="#ffdc70";
    $("dialogText").textContent=q[4];
    $("mission").textContent="Yanlışlardan öğrenmek de ilerlemedir! Sandığı bul.";
   }
   updateHUD();renderInventory();show("dialogClose");
  };
  $("answers").appendChild(b);
 });
}
function givePrize(prize){
 if(prize.type==="costume"){
  if(!ownedCostumes.includes(prize.name))ownedCostumes.push(prize.name);
  else {coins+=5;$("feedback").textContent+=" Aynı kostümden vardı: +5 altın!";}
 }else inventory.push(prize);
}
$("dialogClose").onclick=()=>{
 hide("overlay");
 if(overlayMode==="question"){
  $("mission").textContent="Şimdi sandığı bul, sonra çıkış kapısına git.";
 }
 overlayMode="";draw();
};
function renderInventory(){
 $("inventory").innerHTML="";
 if(inventory.length===0&&ownedCostumes.length===0){
  $("inventory").innerHTML='<span class="muted">Henüz ödül yok</span>';return;
 }
 inventory.slice(-5).forEach(o=>{
  const d=document.createElement("div");d.className="slot";
  d.innerHTML="<span>"+o.icon+"</span><small>"+o.name+"</small>";
  $("inventory").appendChild(d);
 });
 ownedCostumes.forEach(n=>{
  const c=costumes.find(x=>x.name===n)||prizes.find(x=>x.name===n);
  if(!c)return;
  const b=document.createElement("button");b.className="slot";b.style.color="white";
  b.style.background=costume===n?"#456a75":"#263b51";
  b.innerHTML="<span>"+c.icon+"</span><small>"+n+"</small>";
  b.onclick=()=>{costume=n;renderInventory();draw();};
  $("inventory").appendChild(b);
 });
}
function wardrobe(){
 openDialog("👕 Kostüm Dolabı","Sahip olduğun bir kostüme dokunarak giyebilirsin.","KOLEKSİYON");
 $("answers").innerHTML="";
 const all=[costumes[0],...prizes.filter(p=>p.type==="costume")];
 all.forEach(c=>{
  const owned=c.name==="Normal"||ownedCostumes.includes(c.name);
  const b=document.createElement("button");b.disabled=!owned;
  b.textContent=c.icon+" "+c.name+(costume===c.name?" ✓":owned?"":" 🔒");
  b.onclick=()=>{costume=c.name;renderInventory();draw();hide("overlay");};
  $("answers").appendChild(b);
 });
 $("feedback").textContent="Doğru cevaplarla kostüm koleksiyonunu genişlet.";
 show("dialogClose");
}
$("interact").onclick=interact;
$("wardrobe").onclick=wardrobe;
function nextLevel(){
 if(level>=4){
  playing=false;hide("game");show("ending");
  $("result").textContent=stars+" yıldız • "+coins+" altın • "+score+" puan";
  return;
 }
 level++;startLevel();updateHUD();draw();
}
function restart(){
 playing=false;hide("ending");hide("game");show("welcome");chooseCharacter(chosen);
}
$("restart").onclick=restart;
document.querySelectorAll("[data-dir]").forEach(b=>{
 const dir=b.dataset.dir;
 const go=()=>{
  const d={up:[0,-23],down:[0,23],left:[-23,0],right:[23,0]}[dir];
  move(d[0],d[1]);
 };
 b.addEventListener("pointerdown",e=>{e.preventDefault();go();});
});
window.addEventListener("keydown",e=>{
 const k=e.key.toLowerCase();
 const d={arrowup:[0,-22],w:[0,-22],arrowdown:[0,22],s:[0,22],arrowleft:[-22,0],a:[-22,0],arrowright:[22,0],d:[22,0]}[k];
 if(d){e.preventDefault();move(d[0],d[1]);}
 if(k==="e"||k===" "){e.preventDefault();interact();}
});
window.addEventListener("resize",draw);
draw();
</script>
</body>
</html>
