
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Un mensaje de amor ❤️</title>
<style>
html,body{margin:0;padding:0;overflow:hidden;background:#02030b;color:white;font-family:Georgia,serif;height:100%}
#bg{position:fixed;inset:0;background-image:url('https://i.postimg.cc/G2MQnDhn/1ce02f2de5068ee6607b28559a0fc67b.jpg');background-size:cover;background-position:center;background-repeat:no-repeat;}
.star{position:absolute;width:2px;height:2px;background:white;border-radius:50%;animation:twinkle 2s infinite alternate}
@keyframes twinkle{from{opacity:.2}to{opacity:1}}
#moon{position:absolute;top:60px;right:60px;width:120px;height:120px;border-radius:50%;background:rgba(247,242,211,0.75);box-shadow:0 0 40px rgba(255,255,255,0.4);}
.screen{position:absolute;inset:0;display:flex;flex-direction:column;justify-content:center;align-items:center;padding:25px;text-align:center}
#start{z-index:2}
#storyScreen{display:none;z-index:1}
button{padding:18px 40px;font-size:24px;border:none;border-radius:999px;background:#ff4f8b;color:#fff;cursor:pointer;transition:.15s}
button:active{transform:scale(.92)}
#story{display:none;max-width:min(760px,90vw);width:min(760px,90vw);font-size:clamp(16px,2.2vw,22px);line-height:1.7;white-space:pre-wrap;overflow-y:auto;max-height:80vh;padding:20px 24px;background:rgba(2,3,11,0.6);border-radius:20px;backdrop-filter:blur(6px);box-shadow:0 0 25px rgba(255,255,255,0.12)}
#end{display:none;text-align:center;max-width:min(760px,90vw);width:min(760px,90vw);padding:20px 24px;background:rgba(2,3,11,0.6);border-radius:20px;backdrop-filter:blur(6px);box-shadow:0 0 25px rgba(255,255,255,0.12)}
#end img{width:min(320px,70vw);max-width:80vw;border-radius:18px;box-shadow:0 0 30px #fff4}
.heart{position:fixed;font-size:22px;pointer-events:none;animation:float 1s forwards}
@keyframes float{to{transform:translateY(-100px) scale(1.7);opacity:0}}
</style>
</head>
<body>
<div id="bg"><div id="moon"></div></div>

<div class="screen" id="start">
<h1> Para Manuelita. </h1>
<p>Mi niña preciosa...</p>
<button id="go"> Presiona </button>
</div>

<div class="screen" id="storyScreen">
<div id="story"></div>

<div id="end">
<img src="https://i.postimg.cc/J4YQ2ZY3/minovia1.webp" alt="Momento de amor">
<h2>Mi Manuelita ❤️</h2>
<p>Estoy orgullso de ti. Te amo mucho mi reina.</p>
</div>
</div>

<script>
const bg=document.getElementById("bg");
const start=document.getElementById("start");
const storyScreen=document.getElementById("storyScreen");
const story=document.getElementById("story");
const end=document.getElementById("end");
const go=document.getElementById("go");

for(let i=0;i<220;i++){
 let s=document.createElement("div");
 s.className="star";
 s.style.left=Math.random()*100+"%";
 s.style.top=Math.random()*100+"%";
 s.style.opacity=Math.random();
 bg.appendChild(s);
}
document.addEventListener("pointerdown",e=>{
 for(let i=0;i<10;i++){
   let h=document.createElement("div");
   h.className="heart";
   h.innerHTML="❤";
   h.style.left=(e.clientX+(Math.random()*30-15))+"px";
   h.style.top=(e.clientY+(Math.random()*30-15))+"px";
   document.body.appendChild(h);
   setTimeout(()=>h.remove(),1000);
 }
});
const text=`Mi amor...

No existen palabras suficientes para expresar lo mucho que el amor puede transformar un día.

Desde que llegaste a mi vida descubrí que el corazón también puede sentirse en casa.

Amo tu forma de ser, tu sensibilidad, tu fuerza y la manera en que conviertes lo cotidiano en algo especial.

Quiero que nunca olvides lo importante que eres.

Querida Manuelita:

Sé que hemos pasado por muchas dificultades, tanto de día como de noche, pero cada una de ellas nos ha hecho más fuertes. Quiero que sepas que cada vez que hablo contigo me haces sentir de una manera tan especial y hermosa que no puedo describir con palabras lo feliz que soy cuando estás a mi lado.

Espero seguir compartiendo cada día de mi vida contigo. Prometo esforzarme cada día por ser una mejor persona, mejorar en todo lo que pueda y hacer todo lo posible para estar siempre cerca de ti, porque eres una de las personas más importantes de mi vida.

Gracias por todo, mi niña linda. Te amo muchísimo.
;

go.addEventListener("click",()=>{
 start.style.display="none";
 storyScreen.style.display="flex";
 story.style.display="block";
 story.innerHTML="";
 let i=0;
 let timer=setInterval(()=>{
   if(text[i]=="\n") story.innerHTML+="<br>";
   else story.innerHTML+=text[i];
   i++;
   if(i>=text.length){
      clearInterval(timer);
      setTimeout(()=>{
        story.style.display="none";
        end.style.display="block";
      },2500);
   }
 },40);
});
</script>
</body>
</html>
