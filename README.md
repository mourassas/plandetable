<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Mariage des Mourassas</title>
<style>
:root{--bg:#f5f3ec;--card:#fcfbf7;--ink:#1e2b24;--mute:#66756c;--line:#d8dccd;--acc:#2f5d46;--free:#e3e8dc;--ok:#2f7a55;--full:#a8741a}
*{box-sizing:border-box}
body{margin:auto;background:var(--bg);color:var(--ink);font:15px/1.5 system-ui,sans-serif;padding:12px 16px;max-width:1300px}
h1{font:italic 600 26px Georgia,serif;margin:0;color:var(--acc)}
h2{font:600 18px Georgia,serif;margin:0 0 10px}
header{display:flex;flex-wrap:wrap;gap:6px 12px;justify-content:space-between;align-items:end;margin-bottom:6px}
.stats{display:flex;gap:8px 12px;flex-wrap:wrap;align-items:center;color:var(--mute)}.stats b{color:var(--ink);font:600 18px Georgia,serif}.stats button{padding:5px 9px;font-size:14px}
nav{display:flex;gap:4px;border-bottom:1px solid var(--line);margin-bottom:10px}
nav button{border:0;border-bottom:3px solid transparent;border-radius:0;background:none;padding:5px 14px;font-weight:600;color:var(--mute)}
nav button.on{color:var(--acc);border-color:var(--acc)}
.layout{display:grid;grid-template-columns:380px 1fr;gap:16px;align-items:start}
@media(max-width:800px){.layout{grid-template-columns:1fr}}
.panel{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:14px;margin-bottom:14px}
.side{position:static}
@media(max-width:800px){.side{position:static}}
summary{cursor:pointer;font:600 18px Georgia,serif;margin-bottom:10px}
form,.row{display:flex;gap:6px;margin-bottom:10px;flex-wrap:wrap}
input,select,button,textarea{font:inherit;color:inherit;border:1px solid var(--line);background:var(--card);border-radius:6px;padding:7px 9px;min-width:0}
input{flex:1 1 110px}input[type=number]{flex:0 0 80px}input[type=color]{-webkit-appearance:none;appearance:none;flex:0 0 36px;width:36px;height:36px;padding:0;border:2px solid var(--line);border-radius:50%;overflow:hidden;cursor:pointer;background:none}input[type=color]::-webkit-color-swatch-wrapper{padding:0}input[type=color]::-webkit-color-swatch{border:0;border-radius:50%}input[type=color]::-moz-color-swatch{border:0;border-radius:50%}.g input[type=color]{flex:0 0 22px;width:22px;height:22px}
textarea{width:100%;min-height:120px;font:13px ui-monospace,monospace}
button{cursor:pointer}button.p{background:var(--acc);border-color:var(--acc);color:#fff}
button.x{border:0;background:none;color:var(--mute);padding:2px 6px}button.x:hover{color:#c0392b}
:focus-visible{outline:2px solid var(--acc);outline-offset:1px}
.g{display:flex;align-items:center;gap:6px;padding:5px 8px;border:1px solid var(--line);border-radius:6px;margin-bottom:5px;cursor:grab;background:var(--bg)}
.g span{flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.g select{padding:2px 4px;font-size:13px;max-width:105px}
.g .dot,.dot{display:inline-block;width:16px;height:16px;min-width:16px;flex:0 0 16px;border-radius:50%;box-shadow:inset 0 0 0 2px rgba(255,255,255,.55),0 0 0 1px rgba(0,0,0,.18)}
#pl{overflow-y:auto;padding-right:2px}
#pool{margin-bottom:0}
#pl .g span{white-space:normal;overflow:visible;overflow-wrap:anywhere}
#pool.over,.t.over{outline:2px dashed var(--acc)}
.tables{display:grid;grid-template-columns:1fr 1fr;gap:14px;height:var(--avail,640px);overflow-y:auto;grid-auto-rows:calc((var(--avail,640px) - 14px)/2);align-content:start;padding-right:4px}
@media(max-width:900px){.tables{grid-template-columns:1fr;height:auto;grid-auto-rows:minmax(250px,auto)}}
.t{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:10px 12px;display:flex;flex-direction:column;overflow:hidden;min-height:0}
.tb{display:flex;gap:10px;flex:1;min-height:0}.tl{flex:1;min-width:0;overflow-y:auto}.tl .g{padding:3px 6px;margin-bottom:4px;font-size:14px}
#pl .g{padding:3px 8px;margin-bottom:4px;font-size:14px}
.t.full{border-color:var(--full)}
.th{display:flex;justify-content:space-between;align-items:center;gap:6px}
.th b{font:600 17px Georgia,serif}
.left{font-size:13px;margin:0 0 4px;color:var(--ok)}.full .left{color:var(--full)}
.round{--rs:clamp(120px,calc((var(--avail,640px) - 14px)/2 - 85px),170px);position:relative;flex:0 0 var(--rs);width:var(--rs);height:var(--rs)}
.round:before{content:"";position:absolute;inset:24%;border-radius:50%;border:2px solid var(--line);background:var(--bg)}
.seat{position:absolute;width:26px;height:26px;margin:-13px;border-radius:50%;background:var(--free);display:grid;place-items:center;font-size:10px;font-weight:700;border:1px solid var(--line)}
.seat.on{cursor:pointer}
.empty{color:var(--mute);font-style:italic;text-align:center;padding:10px}
#st{font-size:13px;color:var(--mute)}#st.err{color:#c0392b}
.legend{display:flex;flex-wrap:wrap;gap:8px 14px;font-size:13px;margin:0 0 12px}
.legend label{display:flex;align-items:center;gap:5px}.legend input{flex:0 1 120px;padding:3px 6px}
.two{display:grid;grid-template-columns:1fr 1fr;gap:14px}@media(max-width:800px){.two{grid-template-columns:1fr}}
dialog{border:1px solid var(--line);border-radius:10px;background:var(--card);color:var(--ink);max-width:420px;width:92%}
dialog label.l{display:block;margin:8px 0 2px;font-size:13px;color:var(--mute)}dialog input{width:100%}
small{color:var(--mute)}.hide{display:none}
#lock{position:fixed;inset:0;background:var(--bg);display:grid;place-items:center;z-index:9}#lock.hide{display:none}#lock form{flex-direction:column;align-items:center;background:var(--card);border:1px solid var(--line);border-radius:10px;padding:28px;width:300px}#lock input{width:100%;flex:none}
</style>
</head>
<body>
<div id="lock"><form id="lf"><h1>Mariage des Mouras</h1><input id="lp" type="password" placeholder="Mot de passe" autocomplete="current-password"><button class="p" style="width:100%">Entrer</button><p id="le" class="hide" style="color:#c0392b;margin:0">Mot de passe incorrect.</p></form></div>
<header>
  <div><h1>Mariage des Mouras</h1><span id="st">Chargement…</span></div>
  <div class="stats">
    <div><b id="s1">0</b> invités</div><div><b id="s2">0</b> placés</div>
    <div><b id="s3">0</b> sans table</div><div><b id="s4">0</b> places libres</div>
    <button id="csvBtn" class="p">Exporter les tables (.csv)</button><button id="exBtn">Sauvegarder (.json)</button><button onclick="$('imFile').click()">Restaurer</button><input type="file" id="imFile" accept=".json" class="hide"><button onclick="logout()">Se déconnecter</button>
  </div>
</header>
<nav><button data-tab="plan" class="on">1 · Plan des tables</button><button data-tab="imp">2 · Invités et tables</button></nav>

<section id="plan" class="layout">
  <div class="side"><div class="panel" id="pool"><details open><summary>Invités à placer (<span id="pc">0</span>)</summary><input id="gs" type="search" placeholder="Rechercher un invité…" aria-label="Rechercher un invité" style="width:100%;margin-bottom:8px"><div id="pl"></div></details></div></div>
  <div class="tables" id="tables"></div>
</section>

<section id="imp" class="hide">
  <div class="legend" id="legend"></div>
  <div class="two">
    <div class="panel">
      <h2 style="display:flex;justify-content:space-between;align-items:center">Invités <button class="x" id="delAllG" style="font-size:13px">Tout supprimer</button></h2>
      <form id="fg"><input id="gl" placeholder="Nom" required><input id="gf" placeholder="Prénom" required><input id="gc" type="color" value="#cccccc" title="Couleur du régime alimentaire"><button class="p">Ajouter</button></form>
      <small>Importer une liste : une ligne par invité, <b>Nom;Prénom;Couleur</b> (couleur facultative : #e63946, rouge, vert…).</small>
      <textarea id="gb" placeholder="Dupont;Marie;#2a9d8f&#10;Martin;Paul;rouge"></textarea>
      <div class="row" style="margin-top:6px"><input type="file" id="gfile" accept=".csv,.txt"><button class="p" id="gbtn">Importer les invités</button></div>
      <div id="gl_list"></div>
    </div>
    <div class="panel">
      <h2 style="display:flex;justify-content:space-between;align-items:center">Tables <button class="x" id="delAllT" style="font-size:13px">Tout supprimer</button></h2>
      <form id="ft"><input id="tn" placeholder="Nom de la table" required><input id="ts" type="number" min="1" max="30" value="8" title="Nombre de places"><button class="p">Créer</button></form>
      <small>Importer une liste : une ligne par table, <b>Nom;Places</b>.</small>
      <textarea id="tb" placeholder="Mariés;10&#10;Famille;8"></textarea>
      <div class="row" style="margin-top:6px"><input type="file" id="tfile" accept=".csv,.txt"><button class="p" id="tbtn">Importer les tables</button></div>
      <div id="tl_list"></div>
    </div>
  </div>
</section>


<script>
const $=id=>document.getElementById(id);
let data={guests:[],tables:[],legend:{}},sha=null,dirty=false,busy=false,timer=null;
/* ====== À MODIFIER ====== */
const MOT_DE_PASSE='0000';
/* ======================== */
function start(){load()}
function logout(){sessionStorage.removeItem('seat-ok');location.reload()}
$('lf').onsubmit=e=>{e.preventDefault();if($('lp').value===MOT_DE_PASSE){sessionStorage.setItem('seat-ok','1');$('lock').classList.add('hide');start()}else{$('le').textContent='Mot de passe incorrect.';$('le').classList.remove('hide');$('lp').select()}};
const uid=()=>Math.random().toString(36).slice(2,9);
const esc=s=>String(s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const status=(m,e)=>{$('st').textContent=m;$('st').className=e?'err':''};
const COL={rouge:'#e63946',vert:'#2a9d8f',bleu:'#3a7bd5',jaune:'#f4d03f',orange:'#f39c12',violet:'#8e44ad',rose:'#f48fb1',gris:'#9aa0a6',marron:'#8d5a3b',noir:'#222222',blanc:'#ffffff'};
const hex=c=>{c=(c||'').trim().toLowerCase();return /^#[0-9a-f]{6}$/.test(c)?c:COL[c]||'#cccccc'};
const fg=h=>{const n=parseInt(h.slice(1),16),l=.3*(n>>16)+.59*((n>>8)&255)+.11*(n&255);return l>150?'#111':'#fff'};
const nm=g=>`${g.first} ${g.last}`.trim();
const norm=()=>{data.guests=(data.guests||[]).map(g=>{if(g.last===undefined){const p=(g.name||'').trim().split(/\s+/);g.first=p.shift()||'';g.last=p.join(' ');delete g.name}g.color=g.color||'#cccccc';return g});data.tables=data.tables||[];data.legend=data.legend||{}};

function load(){try{data=JSON.parse(localStorage.getItem('seat-local')||'')}catch(e){}norm();status('Données enregistrées dans ce navigateur');render()}
function changed(){render();save()}
function save(){try{localStorage.setItem('seat-local',JSON.stringify(data));status('Enregistré '+new Date().toLocaleTimeString('fr-FR'))}catch(e){status('Enregistrement impossible',1)}}
$('gs').oninput=render;
$('delAllG').onclick=()=>{if(data.guests.length&&confirm(`Supprimer les ${data.guests.length} invités ?`)){data.guests=[];changed()}};
$('delAllT').onclick=()=>{if(data.tables.length&&confirm(`Supprimer les ${data.tables.length} tables ? Les invités resteront dans la liste, sans table.`)){data.guests.forEach(g=>g.table=null);data.tables=[];changed()}};
$('csvBtn').onclick=()=>{
  const q=v=>'"'+String(v).replace(/"/g,'""')+'"',reg=g=>data.legend[g.color]||g.color;
  const rows=[['Table','Places','Nom','Prénom','Régime']];
  data.tables.forEach(t=>{const gs=sorted(seated(t.id));if(!gs.length)rows.push([t.name,t.seats,'','','']);gs.forEach(g=>rows.push([t.name,t.seats,g.last,g.first,reg(g)]))});
  sorted(data.guests.filter(g=>!g.table||!tbl(g.table))).forEach(g=>rows.push(['(sans table)','',g.last,g.first,reg(g)]));
  const a=document.createElement('a');a.href=URL.createObjectURL(new Blob(['\ufeff'+rows.map(r=>r.map(q).join(';')).join('\r\n')],{type:'text/csv;charset=utf-8'}));a.download='plan-de-table-liste.csv';a.click()};
$('exBtn').onclick=()=>{const a=document.createElement('a');a.href=URL.createObjectURL(new Blob([JSON.stringify(data,null,1)],{type:'application/json'}));a.download='plan-de-table.json';a.click()};
$('imFile').onchange=async e=>{const f=e.target.files[0];if(!f)return;try{const d=JSON.parse(await f.text());if(!Array.isArray(d.guests)||!Array.isArray(d.tables))throw 0;if(!confirm('Remplacer les données de ce navigateur par ce fichier ?'))return;data=d;norm();changed()}catch(x){alert('Fichier invalide.')}e.target.value=''};

const tbl=id=>data.tables.find(t=>t.id===id);
const seated=id=>data.guests.filter(g=>g.table===id);
const sorted=a=>[...a].sort((x,y)=>(x.last+x.first).localeCompare(y.last+y.first,'fr'));
function place(gid,tid){
  const g=data.guests.find(x=>x.id===gid);if(!g)return;
  if(tid){const t=tbl(tid);if(g.table!==tid&&seated(tid).length>=t.seats){alert(`La table « ${t.name} » est complète.`);return}}
  const moved=g.table!==(tid||null);g.table=tid||null;if(tid&&moved)g.at=Date.now();changed();
}
function fit(){if($('plan').classList.contains('hide'))return;const top=$('plan').getBoundingClientRect().top+scrollY;document.documentElement.style.setProperty('--avail',Math.max(360,innerHeight-top-12)+'px')}
addEventListener('resize',()=>render());
function render(){renderAll();fit()}
function renderAll(){
  const fold=t=>t.normalize('NFD').replace(/[\u0300-\u036f]/g,'').toLowerCase();
  const free=sorted(data.guests.filter(g=>!g.table||!tbl(g.table)));
  const q=fold($('gs').value.trim()),shown=q?free.filter(g=>fold(g.last+' '+g.first).includes(q)||fold(g.first+' '+g.last).includes(q)):free;
  const cap=data.tables.reduce((a,t)=>a+t.seats,0),placed=data.guests.length-free.length;
  $('s1').textContent=data.guests.length;$('s2').textContent=placed;$('s3').textContent=free.length;$('s4').textContent=cap-placed;$('pc').textContent=free.length;
  $('pl').innerHTML=shown.length?shown.map(guestRow).join(''):'<div class="empty">'+(free.length?'Aucun invité trouvé.':data.guests.length?'Tout le monde a une table.':'Ajoutez ou importez des invités (onglet 2).')+'</div>';
  const rows=$('pl').children;if(!rows.length||rows[0].offsetHeight){const cap='calc(var(--avail,640px) - 152px)';$('pl').style.maxHeight=rows.length>15?`min(${rows[14].offsetTop+rows[14].offsetHeight-rows[0].offsetTop}px,${cap})`:cap}
  $('tables').innerHTML=data.tables.length?data.tables.map(tableCard).join(''):'<div class="panel empty">Créez ou importez des tables (onglet 2).</div>';
  // onglet 2
  const cols=[...new Set(data.guests.map(g=>g.color))];
  $('legend').innerHTML=cols.length?'<b>Régimes :</b>'+cols.map(c=>`<label><span class="dot" style="background:${c}"></span><input data-leg="${c}" value="${esc(data.legend[c]||'')}" placeholder="Nommer ce régime"></label>`).join(''):'';
  $('gl_list').innerHTML=sorted(data.guests).map(g=>`<div class="g" style="cursor:default"><input type="color" value="${g.color}" data-col="${g.id}"><span>${esc(g.last)} ${esc(g.first)}${g.table&&tbl(g.table)?' <small>· '+esc(tbl(g.table).name)+'</small>':''}</span><button class="x" data-delg="${g.id}" title="Supprimer">✕</button></div>`).join('');
  $('tl_list').innerHTML=data.tables.map(t=>`<div class="g" style="cursor:default"><span>${esc(t.name)} <small>· ${seated(t.id).length}/${t.seats} places</small></span><button class="x" data-edt="${t.id}" title="Modifier">✎</button><button class="x" data-delt="${t.id}" title="Supprimer">✕</button></div>`).join('');
}
function guestRow(g){
  return `<div class="g" draggable="true" data-g="${g.id}"><span class="dot" style="background:${g.color}" title="${esc(data.legend[g.color]||'')}"></span><span>${esc(g.last)} ${esc(g.first)}</span></div>`;
}
function tableCard(t){
  const gs=sorted(seated(t.id)),n=gs.length,left=t.seats-n,R=70;
  let seats='';
  for(let i=0;i<t.seats;i++){
    const a=2*Math.PI*i/t.seats-Math.PI/2,x=50+41*Math.cos(a),y=50+41*Math.sin(a),g=gs[i];
    seats+=g?`<div class="seat on" style="left:${x}%;top:${y}%;background:${g.color};color:${fg(g.color)}" title="${esc(nm(g))} (cliquer pour retirer)" data-un="${g.id}" draggable="true" data-g="${g.id}">${esc((g.first[0]||'')+(g.last[0]||'')).toUpperCase()}</div>`
      :`<div class="seat" style="left:${x}%;top:${y}%"></div>`;
  }
  return `<div class="t ${left<=0?'full':''}" data-t="${t.id}">
  <div class="th"><b>${esc(t.name)}</b><span><button class="x" data-edt="${t.id}" title="Modifier">✎</button><button class="x" data-delt="${t.id}" title="Supprimer">✕</button></span></div>
  <p class="left">${left>0?left+' place'+(left>1?'s':'')+' restante'+(left>1?'s':'')+' sur '+t.seats:'Table complète ('+t.seats+' places)'}</p>
  <div class="tb"><div class="round">${seats}</div><div class="tl">${gs.map(g=>`<div class="g" draggable="true" data-g="${g.id}"><span class="dot" style="background:${g.color}" title="${esc(data.legend[g.color]||'')}"></span><span>${esc(g.last)} ${esc(g.first)}</span><button class="x" data-un="${g.id}" title="Retirer de la table">↩</button></div>`).join('')}</div></div></div>`;
}
const lines=t=>t.split(/\r?\n/).map(l=>l.split(/[;\t,]/).map(s=>s.trim())).filter(r=>r[0]);
function readFile(inp,ta){const f=inp.files[0];if(f)f.text().then(t=>{ta.value=t})}
$('gfile').onchange=()=>readFile($('gfile'),$('gb'));$('tfile').onchange=()=>readFile($('tfile'),$('tb'));
$('gbtn').onclick=()=>{const r=lines($('gb').value).filter(r=>r[1]);if(!r.length){alert('Aucune ligne valide. Format : Nom;Prénom;Couleur');return}
  r.forEach(x=>data.guests.push({id:uid(),last:x[0],first:x[1],color:hex(x[2]),table:null}));$('gb').value='';changed();status(r.length+' invités importés')};
$('tbtn').onclick=()=>{const r=lines($('tb').value);if(!r.length){alert('Aucune ligne valide. Format : Nom;Places');return}
  r.forEach(x=>data.tables.push({id:uid(),name:x[0],seats:Math.max(1,Math.min(30,parseInt(x[1],10)||8))}));$('tb').value='';changed();status(r.length+' tables importées')};
$('fg').onsubmit=e=>{e.preventDefault();data.guests.push({id:uid(),last:$('gl').value.trim(),first:$('gf').value.trim(),color:$('gc').value,table:null});$('gl').value=$('gf').value='';changed();$('gl').focus()};
$('ft').onsubmit=e=>{e.preventDefault();data.tables.push({id:uid(),name:$('tn').value.trim(),seats:Math.max(1,Math.min(30,+$('ts').value||8))});$('tn').value='';changed()};
document.addEventListener('click',e=>{
  const d=e.target.dataset;
  if(d.tab){document.querySelectorAll('nav button').forEach(b=>b.classList.toggle('on',b===e.target));$('plan').classList.toggle('hide',d.tab!=='plan');$('imp').classList.toggle('hide',d.tab!=='imp');render()}
  else if(d.un)place(d.un,null);
  else if(d.delg){data.guests=data.guests.filter(x=>x.id!==d.delg);changed()}
  else if(d.delt){const t=tbl(d.delt);if(confirm(`Supprimer la table « ${t.name} » ? Ses invités repasseront sans table.`)){data.guests.forEach(g=>{if(g.table===t.id)g.table=null});data.tables=data.tables.filter(x=>x!==t);changed()}}
  else if(d.edt){const t=tbl(d.edt),n=prompt('Nom de la table',t.name);if(n===null)return;
    const s0=parseInt(prompt('Nombre de places',t.seats),10);if(!s0||s0<1)return;const s=Math.min(30,s0);
    const out=seated(t.id).map(g=>({g,i:data.guests.indexOf(g)})).sort((a,b)=>(a.g.at||0)-(b.g.at||0)||a.i-b.i).slice(s).map(o=>o.g).reverse();
    out.forEach(g=>g.table=null);
    t.name=n.trim()||t.name;t.seats=s;changed();
    if(out.length)status(out.length+' invité'+(out.length>1?'s remis':' remis')+' dans la liste : '+out.map(nm).join(', '))}
});
document.addEventListener('change',e=>{const d=e.target.dataset;
  if(d.place&&e.target.value)place(d.place,e.target.value);
  else if(d.col){data.guests.find(g=>g.id===d.col).color=e.target.value;changed()}
  else if(d.leg!==undefined){data.legend[d.leg]=e.target.value.trim();changed()}});
let drag=null;
document.addEventListener('dragstart',e=>{const g=e.target.closest('[data-g]');if(g){drag=g.dataset.g;e.dataTransfer.setData('text/plain',drag)}});
document.addEventListener('dragover',e=>{const z=e.target.closest('.t,#pool');if(z&&drag){e.preventDefault();document.querySelectorAll('.over').forEach(x=>x.classList.remove('over'));z.classList.add('over')}});
document.addEventListener('dragend',()=>{drag=null;document.querySelectorAll('.over').forEach(x=>x.classList.remove('over'))});
document.addEventListener('drop',e=>{const z=e.target.closest('.t,#pool');if(z&&drag){e.preventDefault();const id=drag;drag=null;z.classList.remove('over');place(id,z.dataset.t||null)}});

if(sessionStorage.getItem('seat-ok')){$('lock').classList.add('hide');start()}else $('lp').focus();
</script>
</body>
</html>
