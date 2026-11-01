<!DOCTYPE html>
<html lang="en"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;800&display=swap">
<title>Mahfuj’s Trading Log</title>
<style>
:root{box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);
--bg:#eef1f6;--card:#fff;--in:#f4f6fa;--tx:#0f172a;--mut:#64748b;--bd:#e2e8f0;--ink:#0b1f3a;--gold:#e0a526;--gn:#047857;--rd:#be123c;--gnbg:#ecfdf5;--gnbd:#a7f3d0;--rdbg:#fff1f2;--rdbd:#fecdd3}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0a1120;--card:#111b2f;--in:#0d1627;--tx:#e8edf6;--mut:#8b98b0;--bd:#1f2c46;--ink:#1a2a4a;--gn:#34d399;--rd:#fb7185;--gnbg:#07281f;--gnbd:#0f5a43;--rdbg:#34101a;--rdbd:#6b1d2e}}
:root[data-theme="dark"]{--bg:#0a1120;--card:#111b2f;--in:#0d1627;--tx:#e8edf6;--mut:#8b98b0;--bd:#1f2c46;--ink:#1a2a4a;--gn:#34d399;--rd:#fb7185;--gnbg:#07281f;--gnbd:#0f5a43;--rdbg:#34101a;--rdbd:#6b1d2e}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0 auto;background:radial-gradient(900px 260px at 50% -80px,rgba(224,165,38,.18),transparent) no-repeat,var(--bg);color:var(--tx);font:15px/1.45 "Plus Jakarta Sans","Noto Sans Bengali",system-ui,-apple-system,"Segoe UI",Roboto,Arial,sans-serif;padding:16px;max-width:560px;-webkit-font-smoothing:antialiased}
h1{font-size:27px;font-weight:800;letter-spacing:-.02em;margin:6px 0 4px}
h1::after{content:"";display:block;width:46px;height:4px;background:var(--gold);border-radius:2px;margin-top:9px}
h2{font-size:18px;font-weight:800;letter-spacing:-.01em;margin:26px 0 10px;color:var(--tx)}
.sub{color:var(--mut);font-size:12.5px;line-height:1.5;margin:0 0 12px}
.card{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:14px;margin-bottom:12px;border-left-width:4px}
.card.win{background:var(--gnbg);border-color:var(--gnbd);border-left-color:var(--gn)}
.card.loss,.flag{background:var(--rdbg);border-color:var(--rdbd);border-left-color:var(--rd)}
.grid{display:grid;grid-template-columns:repeat(2,1fr);gap:10px}
.stat{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:12px 14px}
.stat b{display:block;font-size:19px;font-weight:800;font-variant-numeric:tabular-nums;margin-top:2px}.stat span{font-size:12px;font-weight:600;color:var(--mut)}
#stats .stat:first-child{grid-column:1/-1;background:var(--ink);color:#fff;border:0;border-top:3px solid var(--gold);padding:18px 18px 16px}
#stats .stat:first-child span{color:#9fb2d4}#stats .stat:first-child b{font-size:36px;letter-spacing:-.03em}
input,select{font:inherit;font-size:15px;color:var(--tx);background:var(--in);border:1px solid var(--bd);border-radius:12px;padding:10px;width:100%;min-width:0;min-height:44px}
input:focus,select:focus{outline:2px solid var(--gold);outline-offset:1px;border-color:transparent}
label{font-size:12px;font-weight:600;color:var(--mut);display:block;margin-bottom:5px}
.row{display:grid;gap:8px;margin-bottom:10px}
.trade{grid-template-columns:2fr 1.1fr 1fr 1.5fr}
.two{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.head{display:flex;justify-content:space-between;align-items:center;gap:8px;margin:4px 0 8px}
.head b{font-size:17px;font-weight:800}.net{font-weight:800;font-variant-numeric:tabular-nums;font-size:14px}.pos{color:var(--gn)}.neg{color:var(--rd)}
.dream{text-align:center;color:var(--mut);font-size:12px;font-weight:600;margin-bottom:8px}
.emo{display:block;width:100%;font:inherit;font-weight:700;font-size:14px;cursor:pointer;background:transparent;color:var(--tx);border:1.5px dashed var(--gold);text-align:center;padding:11px;border-radius:14px;margin-bottom:10px}
.emo.on{background:var(--gnbg);border:1.5px solid var(--gn);color:var(--gn)}
.pre{background:var(--in);border-radius:14px;padding:4px 12px;margin:8px 0}
.pre summary{font-size:13.5px;font-weight:600;color:var(--tx);padding:9px 0;cursor:pointer}.pre summary b{color:var(--mut)}
.chk button{display:flex;align-items:center;gap:10px;width:100%;text-align:left;background:none;border:0;color:var(--tx);font:inherit;font-size:14px;padding:9px 0}
.chk i{width:22px;height:22px;border:2px solid var(--mut);border-radius:7px;flex:none;display:block;text-align:center;font-style:normal;font-size:14px;line-height:18px;color:#fff}
.chk .on i{background:var(--gn);border-color:var(--gn)}.chk .on i::after{content:"\2713"}
.pre .note{background:#fef3c7;color:#78350f;font-weight:700;font-size:12px;padding:8px 10px;border-radius:10px;margin:4px 0 8px}
.rules.rl{display:block;margin:2px 0 6px}
.rules.rl button{display:flex;width:100%;text-align:left;gap:6px;margin-bottom:6px;padding:11px 12px;font:inherit;font-size:14px;font-weight:500;color:var(--tx);background:var(--card);border:1px solid var(--bd);border-radius:12px}
.rl button::after{content:"";margin-left:auto;font-weight:700}
.rules .y{background:var(--gnbg)!important;border-color:var(--gn)!important}.rules .n{background:var(--rdbg)!important;border-color:var(--rd)!important}
.rl .y::after{content:"\2713 Followed";color:var(--gn)}.rl .n::after{content:"\2717 Broken";color:var(--rd)}
.stars{display:flex;gap:2px}.stars button{background:none;border:0;font-size:30px;line-height:1;padding:2px 3px;color:var(--bd)}.stars button.on{color:#f5b301}
.warn{font-size:12.5px;font-weight:600;color:var(--rd);margin:4px 0 8px;display:none}
table{width:100%;border-collapse:collapse;font-size:13.5px;font-variant-numeric:tabular-nums}th,td{padding:9px 4px;text-align:right;border-bottom:1px solid var(--bd)}th:first-child,td:first-child{text-align:left}th{color:var(--mut);font-weight:600;font-size:12px}
button.reset{font:inherit;font-weight:600;font-size:14px;margin-top:14px;background:var(--card);border:1px solid var(--bd);color:var(--tx);border-radius:14px;padding:12px 14px;cursor:pointer}
#newm{background:var(--ink);color:#fff;border-color:var(--ink)}
#dl2{background:var(--ink);color:#fff;border-color:var(--ink)}
.pill{display:inline-block;font-style:normal;font-weight:700;font-size:13px;padding:4px 11px;border-radius:99px;background:rgba(255,255,255,.12);margin-top:8px;color:#cbd5e8}.pill.up{color:#6ee7b7}.pill.dn{color:#fda4af}
.spark{display:block;width:100%;height:70px;margin-top:12px}
.strip{display:grid;grid-template-columns:repeat(5,1fr);gap:8px}
.dot{aspect-ratio:1;border-radius:14px;border:1px solid var(--bd);background:var(--in);color:var(--mut);font:inherit;font-weight:800;font-size:16px;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:0;cursor:pointer}
.dot small{font-size:10px;font-weight:600;opacity:.85}.dot .amt{font-size:12px;font-weight:700;opacity:1;min-height:14px}
.dot.w{background:var(--gn);color:#fff;border-color:var(--gn)}.dot.l{background:var(--rd);color:#fff;border-color:var(--rd)}.dot.z{background:var(--ink);color:#fff;border-color:var(--ink)}
#strip label{margin-bottom:10px}
.ap{width:100%;min-height:44px;border-radius:12px;border:1px solid var(--bd);background:var(--in);color:var(--mut);font:inherit;font-weight:800;font-size:14px;cursor:pointer;padding:0}
.ap.y{background:var(--gnbg);color:var(--gn);border-color:var(--gn)}.ap.n{background:var(--rdbg);color:var(--rd);border-color:var(--rd)}

/* domino blue-red theme */
:root{--bg:#9dbbd0;--card:#fff;--in:#e3eef6;--tx:#04202f;--mut:#2a4a5f;--bd:#86a9bf;--ink:#00466a}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#061824;--card:#0c2a3f;--in:#082133;--tx:#e6f2fa;--mut:#8fb0c4;--bd:#17405a;--ink:#00608f}}
:root[data-theme="dark"]{--bg:#061824;--card:#0c2a3f;--in:#082133;--tx:#e6f2fa;--mut:#8fb0c4;--bd:#17405a;--ink:#00608f}
body{background:radial-gradient(700px 320px at 8% -60px,rgba(0,70,106,.22),transparent) no-repeat,radial-gradient(600px 300px at 100% 0,rgba(192,16,43,.14),transparent) no-repeat,var(--bg)}
h1{background:linear-gradient(90deg,#00486d,#c0102b);-webkit-background-clip:text;background-clip:text;color:transparent;-webkit-text-fill-color:transparent}
h1::after{background:linear-gradient(90deg,#00486d,#c0102b);width:60px}
h2::before{content:"";display:inline-block;width:8px;height:18px;border-radius:4px;background:linear-gradient(#00486d,#c0102b);margin-right:10px;vertical-align:-3px}
#stats .stat:first-child{background:linear-gradient(135deg,#002e47 0%,#00466a 60%,#00608f 100%);border:0;border-bottom:5px solid #c0102b;box-shadow:0 12px 30px rgba(0,70,106,.35)}
#stats .stat:first-child span{color:#d6ecf8}
#stats .stat:nth-child(odd){border-top:3px solid #00486d}#stats .stat:nth-child(even){border-top:3px solid #c0102b}
.card[id^="card"]:not(.win):not(.loss):not(.flag){border-left-color:#00486d}
input:focus,select:focus{outline-color:#00486d}
#newm,#dl2{background:linear-gradient(135deg,#00486d,#00608f);border:0;color:#fff}
.dot.z{background:#00486d;border-color:#00486d}
.emo{border-color:#c0102b}
</style></head><body>
<h1>Mahfuj’s Trading Log</h1>
<div class="card two" style="grid-template-columns:2fr 1fr"><div><label>Month</label><select id="msel"></select></div><div><label>&nbsp;</label><button class="reset" id="newm" style="margin:0;width:100%">+ New month</button></div></div>
<div class="card"><label>Month name (rename any time)</label><input id="mname" type="text"></div>
<div id="dls" style="margin-bottom:10px"><button class="reset" id="dl2" style="margin:0 0 6px;width:100%">⬇ Download PDF (all data)</button><button class="reset" id="dl" style="margin:0;width:100%">⬇ Download image (PNG)</button></div>
<p class="sub">Tap rules to cycle Y / N. Each month is saved separately on this device. A new month starts with your ending balance.</p>

<div class="card two">
 <div style="grid-column:1/-1"><label>Starting balance ($)</label><input id="start" type="number" inputmode="decimal"></div>
 <div><label>Max daily loss (%)</label><input id="maxl" type="number" inputmode="decimal" step="0.1"></div>
 <div><label>Max daily loss ($)</label><input id="maxd" type="number" inputmode="decimal" step="any"></div>
</div>

<h2>Monthly numbers</h2>
<div class="grid" id="stats"></div>
<div class="card" id="strip" style="margin-top:12px"></div>

<h2>Weekly review</h2>
<div class="card"><table id="weeks"></table></div>
<div class="card" id="mist"></div>

<h2>Daily log</h2>
<p class="sub">Rules check: tap once = ✓ followed, tap twice = ✗ broken, third tap clears. Dir.: B = buy, S = sell. A+ Set: tap once = Yes, tap again = No. P/L: loss is negative. Mood: tap the stars, 1 star = tilted, 5 stars = calm and focused.</p>
<div id="days"></div>
<button class="reset" id="reset">Clear this month</button>

<script>
var KEY="mh-trading-log-v2",OLD="mh-trading-log-v1",ST={c:0,m:[]},S;
function blank(){var d=[];for(var i=0;i<20;i++){d.push({r:[0,0,0,0,0,0],t:[{p:"",d:"",rr:"",pl:""},{p:"",d:"",rr:"",pl:""},{p:"",d:"",rr:"",pl:""}],m:"",n:""})}return {s:1000,l:2,nm:"Month 1",d:d}}
try{var raw=localStorage.getItem(KEY),old=localStorage.getItem(OLD);
 if(raw){var o=JSON.parse(raw);if(o&&o.m&&o.m.length)ST=o}
 else if(old){var p=JSON.parse(old);if(p&&p.d&&p.d.length===20){p.nm="Month 1";ST.m=[p]}}}catch(e){}
if(!ST.m.length)ST.m=[blank()];
if(ST.c>=ST.m.length)ST.c=0;
S=ST.m[ST.c];
function save(){ST.m[ST.c]=S;try{localStorage.setItem(KEY,JSON.stringify(ST))}catch(e){}}
function num(v){if(v===""||v===null)return NaN;var x=parseFloat(v);return isNaN(x)?NaN:x}
function money(x){if(x===null||isNaN(x))return "–";return (x<0?"-":"")+Math.abs(x).toLocaleString(undefined,{minimumFractionDigits:2,maximumFractionDigits:2})}
function pct(x){return (x===null||isNaN(x))?"–":(x*100).toFixed(1)+"%"}
function cls(x){return x>0?"pos":(x<0?"neg":"")}

function calc(){
 var start=num(S.s)||0,lim=(num(S.l)||0)/100*start,bal=start,peak=start,mdd=0,mddp=0;
 var tr=0,w=0,l=0,gp=0,gl=0,y=0,yn=0,res=[],wk=[0,1,2,3].map(function(){return {t:0,w:0,n:0}});
 S.d.forEach(function(day,i){
  var n=0,any=false;
  day.t.forEach(function(t){var v=num(t.pl);if(!isNaN(v)){any=true;n+=v;tr++;wk[Math.floor(i/5)].t++;
   if(v>0){w++;gp+=v;wk[Math.floor(i/5)].w++}else if(v<0){l++;gl+=v}}});
  day.r.forEach(function(r){if(r){yn++;if(r===1)y++}});
  if(any){bal+=n;wk[Math.floor(i/5)].n+=n;if(bal>peak)peak=bal;var dd=peak-bal;if(dd>mdd)mdd=dd;if(peak>0&&dd/peak>mddp)mddp=dd/peak}
  res.push({any:any,net:n,bal:bal,hit:any&&lim>0&&n<=-lim});
 });
 return {start:start,bal:bal,tr:tr,w:w,l:l,gp:gp,gl:gl,mdd:mdd,mddp:mddp,disc:yn?y/yn:NaN,res:res,wk:wk};
}

function stat(lab,val,c){return '<div class="stat"><span>'+lab+'</span><b class="'+(c||"")+'">'+val+'</b></div>'}
function hero(c,net){
 var pts=[c.start];c.res.forEach(function(r){if(r.any)pts.push(r.bal)});
 var w=300,h=70,mn=Math.min.apply(null,pts),mx=Math.max.apply(null,pts),rg=(mx-mn)||1,svg="";
 if(pts.length>1){var xy=pts.map(function(v,i){return [i*(w/(pts.length-1)),h-8-((v-mn)/rg)*(h-18)]}),d=xy.map(function(p,i){return (i?"L":"M")+p[0].toFixed(1)+" "+p[1].toFixed(1)}).join(" ");
  svg='<svg class="spark" viewBox="0 0 '+w+' '+h+'" preserveAspectRatio="none"><defs><linearGradient id="sg" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#e0a526" stop-opacity=".45"/><stop offset="1" stop-color="#e0a526" stop-opacity="0"/></linearGradient></defs><path d="'+d+' L'+w+' '+h+' L0 '+h+' Z" fill="url(#sg)"/><path d="'+d+'" fill="none" stroke="#e0a526" stroke-width="2.5" stroke-linejoin="round" stroke-linecap="round" vector-effect="non-scaling-stroke"/></svg>'}
 var pill=c.tr?'<em class="pill '+(net>=0?"up":"dn")+'">'+(net>=0?"▲ +":"▼ ")+money(net)+(c.start?" · "+pct(net/c.start):"")+'</em>':'<em class="pill">No trades yet</em>';
 return '<div class="stat"><span>Balance</span><b>'+money(c.bal)+'</b>'+pill+svg+'</div>';
}
function amt(x){var a=Math.abs(x),s=x>0?"+":(x<0?"-":"");return s+(a>=1000?(a/1000).toFixed(1)+"k":a.toFixed(a%1?2:0))}
function renderStrip(c){var s='<label>Tap a day to jump to it</label><div class="strip">';c.res.forEach(function(r,i){s+='<button class="dot '+(r.any?(r.net>0?"w":(r.net<0?"l":"z")):"")+'" data-i="'+i+'"><small>'+["Mon","Tue","Wed","Thu","Fri"][i%5]+'</small>'+(i+1)+'<small class="amt">'+(r.any?amt(r.net):"")+'</small></button>'});document.getElementById("strip").innerHTML=s+'</div>'}
document.getElementById("strip").addEventListener("click",function(e){var b=e.target.closest(".dot");if(!b)return;var el=document.getElementById("card"+b.dataset.i);if(el)el.scrollIntoView({behavior:"smooth",block:"start"})});
function update(){
 var c=calc(),net=c.bal-c.start;
 var pf=c.gl===0?(c.gp===0?"–":"n/a"):(c.gp/Math.abs(c.gl)).toFixed(2);
 var apY=0,apN=0,apW=0;S.d.forEach(function(d){d.t.forEach(function(t){if(t.ap==="Yes"){apY++;if(num(t.pl)>0)apW++}else if(t.ap==="No")apN++})});
 document.getElementById("stats").innerHTML=
  hero(c,net)+
  stat("Total trades",c.tr)+stat("Win rate",c.tr?pct(c.w/c.tr):"–")+
  stat("Avg win",c.w?money(c.gp/c.w):"–","pos")+stat("Avg loss",c.l?money(c.gl/c.l):"–","neg")+
  stat("Profit factor",pf)+stat("Return",c.start?pct(net/c.start):"–",cls(net))+
  stat("Max drawdown",c.tr?money(c.mdd)+" ("+pct(c.mddp)+")":"–")+stat("Discipline score",pct(c.disc))+stat("A+ sets",(apY+apN)?apY+" of "+(apY+apN)+" ("+pct(apY/(apY+apN))+")":"–")+stat("A+ win rate",apY?pct(apW/apY):"–");
 var h="<tr><th>Week</th><th>Trades</th><th>Wins</th><th>Win %</th><th>Net P/L</th></tr>";
 c.wk.forEach(function(x,i){h+="<tr><td>Week "+(i+1)+"</td><td>"+x.t+"</td><td>"+x.w+"</td><td>"+(x.t?pct(x.w/x.t):"–")+"</td><td class=\""+cls(x.n)+"\">"+money(x.n)+"</td></tr>"});
 document.getElementById("weeks").innerHTML=h;
 renderStrip(c);c.res.forEach(function(r,i){var rc=S.d[i].r,ys=rc.filter(function(x){return x===1}).length,ns=rc.filter(function(x){return x===2}).length;document.getElementById("rc"+i).textContent=ys+"✓ "+ns+"✗";
  var n=document.getElementById("net"+i);n.textContent=r.any?money(r.net)+"  ·  "+money(r.bal):"–";n.className="net "+(r.any?cls(r.net):"");
  document.getElementById("card"+i).classList.toggle("flag",r.hit);document.getElementById("card"+i).classList.toggle("win",r.any&&r.net>0);document.getElementById("card"+i).classList.toggle("loss",r.any&&r.net<0);
  document.getElementById("warn"+i).style.display=r.hit?"block":"none";
 });
}

function build(){
 var box=document.getElementById("days"),h="";
 for(var i=0;i<20;i++){
  if(i%5===0)h+='<h2>Week '+(i/5+1)+'</h2>';h+='<div class="card" id="card'+i+'"><div class="dream">Dream big, stay disciplined</div><button class="emo'+(S.d[i].ce?" on":"")+'" data-i="'+i+'">'+(S.d[i].ce?"✅":"⬜")+' Control your emotion</button><div class="head"><b>'+["Mon","Tue","Wed","Thu","Fri"][i%5]+' · Day '+(i+1)+'</b><span class="net" id="net'+i+'">–</span></div>';
  h+='<details class="pre"><summary>Rules check <b id="rc'+i+'"></b></summary><div class="rules rl" data-i="'+i+'">';for(var k=0;k<6;k++)h+='<button data-k="'+k+'">'+(k+1)+'. '+RULES[k]+'</button>';h+='</div></details>';
  h+=pre(i);h+='<div class="warn" id="warn'+i+'">Daily loss limit hit – stop trading for the day.</div>';
  for(var t=0;t<3;t++){
   h+='<div class="row trade"><div><label>Trade '+(t+1)+' pair</label><input data-i="'+i+'" data-t="'+t+'" data-f="p" type="text"></div>'+
   '<div><label>Dir.</label><select data-i="'+i+'" data-t="'+t+'" data-f="d"><option value=""></option><option>B</option><option>S</option></select></div>'+
   '<div><label>A+ Set</label><button class="ap'+apc(S.d[i].t[t].ap)+'" data-i="'+i+'" data-t="'+t+'">'+(S.d[i].t[t].ap||"–")+'</button></div>'+
   '<div><label>P/L</label><input data-i="'+i+'" data-t="'+t+'" data-f="pl" type="number" inputmode="decimal" step="any"></div></div>';
  }
  h+='<div class="row"><div><label>Biggest mistake today</label><input data-i="'+i+'" data-f="mk" type="text" placeholder="Write your biggest mistake"></div></div>';
  h+='<div class="row"><div><label>Next day focus</label><input data-i="'+i+'" data-f="nf" type="text" placeholder="What will you focus on tomorrow?"></div></div>';
  h+='<div class="row" style="grid-template-columns:auto 1fr"><div><label>Mood</label><div class="stars" data-i="'+i+'">'+[1,2,3,4,5].map(function(k){return '<button data-k="'+k+'">★</button>'}).join("")+'</div></div>'+
   '<div><label>Notes</label><input data-i="'+i+'" data-f="n" type="text"></div></div></div>';
 }
 box.innerHTML=h;
 box.querySelectorAll("[data-f]").forEach(function(el){
  var i=+el.dataset.i,f=el.dataset.f,t=el.dataset.t;
  el.value=t!==undefined?S.d[i].t[+t][f]:(S.d[i][f]||"");
  var ev=el.tagName==="SELECT"?"change":"input";
  el.addEventListener(ev,function(){if(t!==undefined)S.d[i].t[+t][f]=el.value;else S.d[i][f]=el.value;save();update()});
 });
 box.querySelectorAll(".rules").forEach(function(r){
  var i=+r.dataset.i;
  function paint(){r.querySelectorAll("button").forEach(function(b){var v=S.d[i].r[+b.dataset.k];b.className=v===1?"y":(v===2?"n":"");})}
  paint();
  r.addEventListener("click",function(e){var b=e.target.closest("button");if(!b)return;var k=+b.dataset.k;S.d[i].r[k]=(S.d[i].r[k]+1)%3;save();paint();update()});
 });
}
var st=document.getElementById("start"),ml=document.getElementById("maxl");
var msel=document.getElementById("msel"),mn=document.getElementById("mname");
var RULES=["Follow your trading plan","Maximum 3 trades per day","Daily max risk 2%","Stop overtrading","No revenge trading","Discipline over profit"];
var PRE=["Higher-timeframe trend checked","Key support / resistance marked","Setup matches my plan","Stop loss set before entry"];
function mk(){var b=document.getElementById("mist"),h="";if(!S.wm)S.wm=["","","",""];for(var w=0;w<4;w++)h+='<label>Week '+(w+1)+' – biggest mistake</label><input data-w="'+w+'" type="text" placeholder="Write your biggest mistake" style="margin-bottom:8px">';b.innerHTML=h;b.querySelectorAll("input").forEach(function(el){el.value=S.wm[+el.dataset.w]||"";el.addEventListener("input",function(){S.wm[+el.dataset.w]=el.value;save()})})}
function pre(i){return '<details class="pre"><summary>Pre-trade checklist <b id="pc'+i+'"></b></summary><div class="chk" data-i="'+i+'">'+PRE.map(function(t,k){return '<button data-k="'+k+'"><i></i>'+t+'</button>'}).join("")+'</div><div class="note">Any empty box = no trade.</div></details>'}
function paintChk(w){var i=+w.dataset.i,c=S.d[i].c||[],n=0;w.querySelectorAll("button").forEach(function(b){var on=!!c[+b.dataset.k];if(on)n++;b.className=on?"on":""});document.getElementById("pc"+i).textContent=n+"/"+PRE.length+(n===PRE.length?" ✓":"")}
document.getElementById("days").addEventListener("click",function(e){var b=e.target.closest(".chk button");if(!b)return;var w=b.parentNode,i=+w.dataset.i,k=+b.dataset.k;if(!S.d[i].c)S.d[i].c=[0,0,0,0,0,0];S.d[i].c[k]=S.d[i].c[k]?0:1;save();paintChk(w)});
document.getElementById("days").addEventListener("click",function(e){var b=e.target.closest(".emo");if(!b)return;var i=+b.dataset.i;S.d[i].ce=S.d[i].ce?0:1;save();b.textContent=(S.d[i].ce?"✅":"⬜")+" Control your emotion";b.classList.toggle("on",!!S.d[i].ce)});
function apc(v){return v==="Yes"?" y":(v==="No"?" n":"")}
document.getElementById("days").addEventListener("click",function(e){var b=e.target.closest(".ap");if(!b)return;var i=+b.dataset.i,t=+b.dataset.t,x=S.d[i].t[t];x.ap=x.ap==="Yes"?"No":"Yes";save();b.textContent=x.ap;b.className="ap"+apc(x.ap)});
function paintStars(w,i){var v=+S.d[i].m||0;w.querySelectorAll("button").forEach(function(b){b.className=(+b.dataset.k<=v)?"on":""})}
document.getElementById("days").addEventListener("click",function(e){var b=e.target.closest(".stars button");if(!b)return;var w=b.parentNode,i=+w.dataset.i,k=String(b.dataset.k);S.d[i].m=(String(S.d[i].m)===k)?"":k;save();paintStars(w,i)});
function ask(btn,msg){if(btn._a){clearTimeout(btn._t);btn._a=false;btn.textContent=btn._o;return true}btn._a=true;btn._o=btn.textContent;btn.textContent=msg;btn._t=setTimeout(function(){btn._a=false;btn.textContent=btn._o},4000);return false}
function fillSel(){msel.innerHTML="";ST.m.forEach(function(m,i){var o=document.createElement("option");o.value=i;o.textContent=m.nm||"Month "+(i+1);msel.appendChild(o)});msel.value=ST.c}
function load(){S=ST.m[ST.c];if(!S.nm)S.nm="Month "+(ST.c+1);st.value=S.s;ml.value=S.l;mn.value=S.nm;syncD();fillSel();mk();build();document.querySelectorAll(".stars").forEach(function(w){paintStars(w,+w.dataset.i)});document.querySelectorAll(".chk").forEach(function(w){paintChk(w)});update()}
msel.addEventListener("change",function(){ST.c=+msel.value;load();save()});
mn.addEventListener("input",function(){S.nm=mn.value;save();msel.options[ST.c].textContent=S.nm||"Month "+(ST.c+1)});
document.getElementById("newm").addEventListener("click",function(){var b=calc().bal;if(!ask(document.getElementById("newm"),"Tap again: start with "+money(b)))return;var n=blank();n.s=b;n.l=S.l;n.nm="Month "+(ST.m.length+1);ST.m.push(n);ST.c=ST.m.length-1;load();save();window.scrollTo(0,0)});
var md=document.getElementById("maxd");
function syncD(){var s=num(S.s)||0,p=num(S.l);md.value=isNaN(p)?"":(s*p/100).toFixed(2)}
md.addEventListener("input",function(){var s=num(S.s)||0,v=num(md.value);if(isNaN(v)||s<=0){S.l="";ml.value=""}else{S.l=String(+(v/s*100).toFixed(2));ml.value=S.l}save();update()});
st.addEventListener("input",function(){S.s=st.value;syncD();save();update()});
ml.addEventListener("input",function(){S.l=ml.value;syncD();save();update()});
document.getElementById("reset").addEventListener("click",function(){
 if(ask(document.getElementById("reset"),"Tap again to clear this month")){var nm=S.nm,s0=S.s;S=blank();S.nm=nm;S.s=s0;save();load()}
});
function esc(s){return String(s==null?"":s).replace(/&/g,"&amp;").replace(/</g,"&lt;").replace(/>/g,"&gt;")}
function jlines(){
 var c=calc(),W=["Mon","Tue","Wed","Thu","Fri"],net=c.bal-c.start,L=[];
 var pf=c.gl===0?(c.gp===0?"–":"n/a"):(c.gp/Math.abs(c.gl)).toFixed(2);
 var apY=0,apN=0,apW=0;S.d.forEach(function(d){d.t.forEach(function(t){if(t.ap==="Yes"){apY++;if(num(t.pl)>0)apW++}else if(t.ap==="No")apN++})});
 L.push(["h1","Mahfuj’s Trading Journal – "+S.nm],["h2","Monthly numbers"]);
 [["Starting balance",money(c.start)],["Ending balance",money(c.bal)],["Net P/L",money(net)],["Total trades",c.tr],["Win rate",c.tr?pct(c.w/c.tr):"–"],["Avg win",c.w?money(c.gp/c.w):"–"],["Avg loss",c.l?money(c.gl/c.l):"–"],["Profit factor",pf],["Max drawdown",c.tr?money(c.mdd)+" ("+pct(c.mddp)+")":"–"],["Discipline score",pct(c.disc)],["Max daily loss",(num(S.l)||0)+"% ("+money(c.start*(num(S.l)||0)/100)+")"],["A+ sets",(apY+apN)?apY+" of "+(apY+apN)+" ("+pct(apY/(apY+apN))+")":"–"],["A+ win rate",apY?pct(apW/apY):"–"]].forEach(function(r){L.push(["t",r[0]+": "+r[1]])});
 L.push(["h2","Weekly review"]);
 c.wk.forEach(function(x,i){L.push(["t","Week "+(i+1)+": "+x.t+" trades, "+x.w+" wins, Net "+money(x.n)]);if(S.wm&&S.wm[i])L.push(["t","   Biggest mistake: "+S.wm[i]])});
 L.push(["h2","Daily journal"]);
 var any=false;
 S.d.forEach(function(d,i){
  var r=c.res[i],rl=d.r.map(function(x,k){return x?(k+1)+". "+RULES[k]+" "+(x===1?"✓":"✗"):""}).filter(Boolean),
   ck=(d.c||[]).slice(0,PRE.length).filter(Boolean).length,
   tl=d.t.map(function(t,k){return (t.p||t.d||t.ap||t.pl)?"Trade "+(k+1)+": "+t.p+" "+t.d+(t.ap?" A+ "+t.ap:"")+(t.pl!==""?" P/L "+t.pl:""):""}).filter(Boolean),
   m=+d.m||0;
  if(!(r.any||rl.length||ck||tl.length||m||d.mk||d.nf||d.n||d.ce))return;
  any=true;
  L.push([r.any?(r.net<0?"n":"p"):"b",W[i%5]+" · Day "+(i+1)+(r.any?"  |  Net P/L "+money(r.net)+"  |  Balance "+money(r.bal):"")]);
  tl.forEach(function(t){L.push(["t",t])});
  rl.forEach(function(t){L.push(["t","Rule "+t])});
  if(ck)L.push(["t","Pre-trade checklist: "+ck+"/"+PRE.length]);
  if(d.ce)L.push(["t","✓ Control your emotion"]);
  if(m)L.push(["t","Mood: "+"★".repeat(m)+"☆".repeat(5-m)]);
  if(d.mk)L.push(["t","Biggest mistake: "+d.mk]);
  if(d.nf)L.push(["t","Next day focus: "+d.nf]);
  if(d.n)L.push(["t","Notes: "+d.n]);
  L.push(["gap",""]);
 });
 if(!any)L.push(["t","No entries yet."]);
 return L;
}
function jpng(cb){
 var lines=jlines(),W=900,pad=24,cv=document.createElement("canvas"),x=cv.getContext("2d"),F='Arial, "Noto Sans Bengali", sans-serif';
 var st={h1:[22,"bold","#111827"],h2:[17,"bold","#1f2937"],t:[15,"","#111827"],b:[16,"bold","#111827"],p:[16,"bold","#15803d"],n:[16,"bold","#b91c1c"],gap:[8,"","#000"]};
 function wrap(t,font,max){x.font=font;var out=[],cur="";String(t).split(" ").forEach(function(w){var tt=cur?cur+" "+w:w;if(x.measureText(tt).width>max&&cur){out.push(cur);cur=w}else cur=tt});out.push(cur);return out}
 var items=[],y=pad;
 lines.forEach(function(l){var s=st[l[0]],font=(s[1]?s[1]+" ":"")+s[0]+"px "+F,lh=Math.round(s[0]*1.5),ws=l[0]==="gap"?[""]:wrap(l[1],font,W-2*pad);
  if(l[0]==="h2")y+=12;
  ws.forEach(function(w,j){items.push([w,font,s[2],y+Math.round(lh*0.75),(l[0]==="h2"&&j===ws.length-1)?y+lh:0]);y+=lh})});
 var H=y+pad;cv.width=W;cv.height=H;x=cv.getContext("2d");
 x.fillStyle="#ffffff";x.fillRect(0,0,W,H);
 items.forEach(function(it){x.font=it[1];x.fillStyle=it[2];x.fillText(it[0],pad,it[3]);if(it[4]){x.fillRect(pad,it[4]-2,W-2*pad,2)}});
 cv.toBlob(function(b){cb(b,cv)},"image/png");
}
var HAS=false,DM=null;
function mkpdf(pages){
 var enc=new TextEncoder(),chunks=[],off=[],len=0,np=pages.length,pw=595;
 function put(x){var b=typeof x==="string"?enc.encode(x):x;chunks.push(b);len+=b.length}
 function obj(n,body){off[n]=len;put(n+" 0 obj\n"+body+"\nendobj\n")}
 put("%PDF-1.4\n");
 obj(1,"<< /Type /Catalog /Pages 2 0 R >>");
 var kids=[];for(var k=0;k<np;k++)kids.push((3+3*k)+" 0 R");
 obj(2,"<< /Type /Pages /Kids ["+kids.join(" ")+"] /Count "+np+" >>");
 pages.forEach(function(p,k){var ph=Math.round(pw*p.h/p.w),cs="q "+pw+" 0 0 "+ph+" 0 0 cm /Im0 Do Q";
  obj(3+3*k,"<< /Type /Page /Parent 2 0 R /MediaBox [0 0 "+pw+" "+ph+"] /Resources << /XObject << /Im0 "+(5+3*k)+" 0 R >> >> /Contents "+(4+3*k)+" 0 R >>");
  obj(4+3*k,"<< /Length "+cs.length+" >>\nstream\n"+cs+"\nendstream");
  off[5+3*k]=len;put((5+3*k)+" 0 obj\n<< /Type /XObject /Subtype /Image /Width "+p.w+" /Height "+p.h+" /ColorSpace /DeviceRGB /BitsPerComponent 8 /Filter /DCTDecode /Length "+p.bytes.length+" >>\nstream\n");put(p.bytes);put("\nendstream\nendobj\n")});
 var xr=len,total=3+3*np,x="xref\n0 "+total+"\n0000000000 65535 f \n";
 for(var n=1;n<total;n++)x+=("0000000000"+off[n]).slice(-10)+" 00000 n \n";
 put(x+"trailer\n<< /Size "+total+" /Root 1 0 R >>\nstartxref\n"+xr+"\n%%EOF");
 return new Blob(chunks,{type:"application/pdf"});
}
function jpdf(cb){
 jpng(function(b,cv){
  if(!b){cb(null);return}
  var W=cv.width,PH=Math.round(W*1.4142),n=Math.max(1,Math.ceil(cv.height/PH)),pages=[];
  for(var k=0;k<n;k++){var pc=document.createElement("canvas");pc.width=W;pc.height=PH;var x=pc.getContext("2d");x.fillStyle="#fff";x.fillRect(0,0,W,PH);x.drawImage(cv,0,k*PH,W,PH,0,0,W,PH);
   var bin=atob(pc.toDataURL("image/jpeg",0.9).split(",")[1]),u=new Uint8Array(bin.length);for(var i=0;i<bin.length;i++)u[i]=bin.charCodeAt(i);pages.push({bytes:u,w:W,h:PH})}
  cb(mkpdf(pages));
 });
}
function ov(h){var o=document.getElementById("ov");if(!o){o=document.createElement("div");o.id="ov";o.style.cssText="position:fixed;inset:0;z-index:50;background:var(--bg);overflow:auto;padding:12px;padding-top:calc(12px + env(safe-area-inset-top,0px))";document.body.appendChild(o)}o.innerHTML='<button class="reset" id="ovx" style="margin:0 0 10px;width:100%">✕ Close</button>'+h;o.style.display="block";o.scrollTop=0;document.getElementById("ovx").onclick=function(){o.style.display="none"};var cc=document.getElementById("cc");if(cc)cc.onclick=function(){var t=document.getElementById("ct"),ok=false;t.select();t.setSelectionRange(0,999999);try{ok=document.execCommand("copy")}catch(e){}cc.textContent=ok?"Copied ✓":"Select all and copy manually"}}
try{if(window.claude&&claude.use){claude.use("downloads").then(function(m){if(!m)return;HAS=true;DM=m;}).catch(function(){})}}catch(e){}
document.getElementById("dl2").addEventListener("click",function(){var b2=document.getElementById("dl2"),lab=b2.textContent,nm=(S.nm||"month").replace(/[^A-Za-z0-9_-]+/g,"-"),fn="journal-"+nm+".pdf";
 function msg(t,ms){b2.textContent=t;setTimeout(function(){b2.textContent=lab},ms||2500)}
 b2.textContent="Making PDF…";
 jpdf(function(blob){if(!blob){msg("Could not make PDF",3000);return}
  if(DM){DM.save({filename:fn,data:blob}).then(function(){msg("Saved ✓")},function(e){msg(e&&e.code==="declined"?lab:"Could not save, try again",3000)});return}
  if(window.self!==window.top){jpng(function(b){var r=new FileReader();r.onload=function(){ov('<img src="'+r.result+'" style="width:100%;border:1px solid var(--bd)"><p class="sub">Long-press the image, then tap Download image (or take a screenshot).</p>');b2.textContent=lab};r.readAsDataURL(b)});return}
  var a=document.createElement("a");a.href=URL.createObjectURL(blob);a.download=fn;document.body.appendChild(a);a.click();setTimeout(function(){a.remove()},500);msg("Saved ✓")})});
document.getElementById("dl").addEventListener("click",function(){var b2=document.getElementById("dl"),lab=b2.textContent,nm=(S.nm||"month").replace(/[^A-Za-z0-9_-]+/g,"-"),fn="journal-"+nm+".png";
 function msg(t,ms){b2.textContent=t;setTimeout(function(){b2.textContent=lab},ms||2500)}
 b2.textContent="Making image…";
 jpng(function(blob){if(!blob){msg("Could not make image",3000);return}
  if(DM){DM.save({filename:fn,data:blob}).then(function(){msg("Saved ✓")},function(e){msg(e&&e.code==="declined"?lab:"Could not save, try again",3000)});return}
  if(window.self!==window.top){var r=new FileReader();r.onload=function(){ov('<img src="'+r.result+'" style="width:100%;border:1px solid var(--bd)"><p class="sub">Long-press the image, then tap Download image (or take a screenshot).</p>');b2.textContent=lab};r.readAsDataURL(blob);return}
  var a=document.createElement("a");a.href=URL.createObjectURL(blob);a.download=fn;document.body.appendChild(a);a.click();setTimeout(function(){a.remove()},500);msg("Saved ✓")})});
load();
</script></body></html>
