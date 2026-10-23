# IRR-Calculator
Streamline your financial analysis with our powerful Internal Rate of Return (IRR) calculator. Quickly evaluate investment profitability, analyze cash flows, and make data-driven financial decisions with an intuitive, fast, and user-friendly interface. Perfect for investors and analysts!
[index.html](https://github.com/user-attachments/files/33876334/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>IRR Calculator – Internal Rate of Return, NPV &amp; XIRR (Free)</title>
<meta name="description" content="Free IRR calculator. Enter your cash flows to get the internal rate of return, XIRR with dates, NPV, payback period and an NPV chart. Works in your browser, nothing is stored.">
<style>
:root{--bg:#eef3f1;--card:#fff;--ink:#12302b;--mute:#5b706b;--line:#d5e0dc;--accent:#0b6e5f;--accent-ink:#fff;--hi:#f2b01e;--bad:#b3261e;--good:#0b6e5f}
@media (prefers-color-scheme:dark){:root{--bg:#0d1b18;--card:#142723;--card:#142723;--ink:#e6f1ee;--mute:#93aaa4;--line:#27413b;--accent:#3cc9ae;--accent-ink:#06211c;--hi:#f2b01e;--bad:#ff8a80;--good:#3cc9ae}}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;background:var(--bg);color:var(--ink);font:16px/1.6 system-ui,-apple-system,"Segoe UI",Roboto,Arial,sans-serif}
a{color:var(--accent)}
.wrap{max-width:1080px;margin:0 auto;padding:0 20px}
header{border-bottom:1px solid var(--line)}
header .wrap{display:flex;align-items:center;justify-content:space-between;height:60px}
.logo{font-weight:800;font-size:1.15rem;letter-spacing:-.02em;text-decoration:none;color:var(--ink)}
.logo b{color:var(--accent)}
nav a{margin-left:18px;text-decoration:none;color:var(--mute);font-size:.95rem}
nav a:hover{color:var(--ink)}
.hero{padding:44px 0 24px}
h1{font:700 clamp(1.9rem,4.5vw,3rem)/1.1 Georgia,"Times New Roman",serif;margin:0 0 12px;letter-spacing:-.01em}
.hero p{max-width:620px;color:var(--mute);margin:0}
.grid{display:grid;grid-template-columns:1.05fr .95fr;gap:20px;align-items:start;padding-bottom:40px}
@media(max-width:820px){.grid{grid-template-columns:1fr}nav{display:none}}
.card{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:22px}
.card h2{font-size:1.05rem;margin:0 0 14px}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:12px}
label{display:block;font-size:.85rem;color:var(--mute);margin-bottom:4px}
input,select{width:100%;font:inherit;color:var(--ink);background:var(--bg);border:1px solid var(--line);border-radius:8px;padding:9px 10px;min-height:42px}
input:focus,select:focus,button:focus-visible{outline:3px solid var(--hi);outline-offset:1px}
table{width:100%;border-collapse:collapse;margin:6px 0 12px}
th{text-align:left;font-size:.8rem;color:var(--mute);font-weight:600;padding:4px 6px}
td{padding:4px 6px}
td.when{white-space:nowrap;color:var(--mute);font-size:.9rem;width:34%}
td.x{width:44px}
.btn{font:inherit;font-weight:600;border:0;border-radius:8px;padding:10px 16px;cursor:pointer;background:var(--accent);color:var(--accent-ink)}
.btn.ghost{background:transparent;color:var(--ink);border:1px solid var(--line)}
.btn.sm{padding:6px 10px;min-height:42px;background:transparent;color:var(--mute);border:0;font-size:1.2rem}
.btn.sm:hover{color:var(--bad)}
.actions{display:flex;gap:10px;flex-wrap:wrap}
.big{background:var(--accent);color:var(--accent-ink);border-radius:14px;padding:24px;margin-bottom:16px}
.big small{opacity:.85;font-size:.9rem}
.big .num{font:700 clamp(2.6rem,7vw,3.8rem)/1.05 Georgia,serif;margin:2px 0}
.big .sub{opacity:.9;font-size:.9rem}
.stats{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:16px}
.stat{background:var(--card);border:1px solid var(--line);border-radius:12px;padding:12px 14px}
.stat span{display:block;font-size:.8rem;color:var(--mute)}
.stat strong{font-size:1.1rem}
.pos{color:var(--good)}.neg{color:var(--bad)}
.msg{padding:12px 14px;border-radius:10px;border:1px solid var(--bad);color:var(--bad);margin-bottom:16px;font-size:.95rem}
.note{padding:10px 14px;border-radius:10px;border:1px solid var(--hi);font-size:.9rem;margin-bottom:16px}
svg{width:100%;height:auto;display:block}
.hidden{display:none}
section.info{padding:8px 0 28px}
section.info h2{font:700 1.7rem/1.2 Georgia,serif;margin:28px 0 10px}
section.info p,section.info li{max-width:760px}
code,.formula{background:var(--card);border:1px solid var(--line);border-radius:8px;padding:12px 14px;display:block;max-width:760px;overflow-x:auto;font-family:ui-monospace,Consolas,monospace;font-size:.92rem}
details{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:12px 16px;margin-bottom:8px;max-width:760px}
summary{cursor:pointer;font-weight:600}
details p{margin:8px 0 0;color:var(--mute)}
footer{border-top:1px solid var(--line);padding:22px 0 40px;color:var(--mute);font-size:.88rem}
@media(prefers-reduced-motion:reduce){html{scroll-behavior:auto}}
</style>
</head>
<body>
<header><div class="wrap">
  <a class="logo" href="#top">IRR<b>Calc</b></a>
  <nav><a href="#calculator">Calculator</a><a href="#how">How it works</a><a href="#faq">FAQ</a></nav>
</div></header>

<main id="top" class="wrap">
  <div class="hero">
    <h1>IRR calculator</h1>
    <p>Enter what you put in and what you get back. See the internal rate of return, NPV, payback time and a chart, instantly. Free, private, no sign-up.</p>
  </div>

  <div class="grid" id="calculator">
    <!-- INPUTS -->
    <div class="card">
      <h2>Your cash flows</h2>
      <div class="row2">
        <div>
          <label for="mode">Timing</label>
          <select id="mode">
            <option value="reg">Regular intervals</option>
            <option value="date">Specific dates (XIRR)</option>
          </select>
        </div>
        <div>
          <label for="cur">Currency</label>
          <select id="cur">
            <option>PKR</option><option>USD</option><option>INR</option>
            <option>EUR</option><option>GBP</option><option>AED</option>
          </select>
        </div>
      </div>
      <div class="row2">
        <div id="freqBox">
          <label for="freq">Each period is a</label>
          <select id="freq">
            <option value="1">Year</option>
            <option value="4">Quarter</option>
            <option value="12">Month</option>
          </select>
        </div>
        <div>
          <label for="disc">Discount rate for NPV (% per year)</label>
          <input id="disc" type="number" step="0.1" value="10" inputmode="decimal">
        </div>
      </div>

      <table>
        <thead><tr><th id="whenH">Period</th><th>Amount (money in is negative)</th><th></th></tr></thead>
        <tbody id="rows"></tbody>
      </table>
      <div class="actions">
        <button class="btn" id="add" type="button">Add a row</button>
        <button class="btn ghost" id="reset" type="button">Clear all</button>
        <button class="btn ghost" id="demo" type="button">Load example</button>
      </div>
      <p style="font-size:.85rem;color:var(--mute);margin:14px 0 0">Enter money you pay out (your investment) as a negative number, like <b>-100000</b>. Enter money you receive as a positive number.</p>
    </div>

    <!-- RESULTS -->
    <div id="results" aria-live="polite">
      <div id="err" class="msg hidden"></div>
      <div id="warn" class="note hidden"></div>
      <div id="out">
        <div class="big">
          <small id="irrLabel">Internal rate of return (per year)</small>
          <div class="num" id="irr">–</div>
          <div class="sub" id="irrSub"></div>
        </div>
        <div class="stats">
          <div class="stat"><span>NPV at discount rate</span><strong id="npv">–</strong></div>
          <div class="stat"><span>Net profit</span><strong id="profit">–</strong></div>
          <div class="stat"><span>Total invested</span><strong id="inv">–</strong></div>
          <div class="stat"><span>Total received</span><strong id="rec">–</strong></div>
          <div class="stat"><span>Money multiple</span><strong id="mult">–</strong></div>
          <div class="stat"><span>Payback time</span><strong id="pay">–</strong></div>
        </div>
        <div class="card">
          <h2>NPV at different rates</h2>
          <div id="chart"></div>
          <p style="font-size:.85rem;color:var(--mute);margin:8px 0 0">The IRR is the rate where the line crosses zero.</p>
        </div>
      </div>
    </div>
  </div>

  <section class="info" id="how">
    <h2>What is IRR?</h2>
    <p>The internal rate of return (IRR) is the yearly growth rate an investment earns. It is the discount rate that makes the net present value (NPV) of all your cash flows equal to zero. A higher IRR means a better return. Compare it with your required return: if the IRR is higher, the investment clears the bar.</p>
    <h2>The formula</h2>
    <span class="formula">0 = CF0 + CF1/(1+r) + CF2/(1+r)² + … + CFn/(1+r)ⁿ</span>
    <p>CF is the cash flow in each period and <b>r</b> is the IRR. There is no direct algebra for r, so this calculator finds it by trying rates and narrowing in until NPV reaches zero.</p>
    <h2>IRR or XIRR?</h2>
    <ul>
      <li><b>Regular intervals:</b> use when cash flows happen at equal gaps (every year, quarter or month). Monthly and quarterly results are converted to a yearly rate.</li>
      <li><b>Specific dates (XIRR):</b> use when payments happen on irregular dates, such as SIP top-ups, property sales or business withdrawals.</li>
    </ul>
    <h2 id="faq">Frequently asked questions</h2>
    <details><summary>What is a good IRR?</summary><p>It depends on risk and alternatives. Compare the IRR with your cost of capital, bank profit rate, inflation or the return of other options you have.</p></details>
    <details><summary>Why does it say IRR cannot be calculated?</summary><p>You need at least one negative amount (money out) and one positive amount (money in). If every amount has the same sign there is no break-even rate.</p></details>
    <details><summary>What is the difference between IRR and NPV?</summary><p>NPV gives the value in money at a rate you choose. IRR gives the rate at which NPV is zero. Use both together.</p></details>
    <details><summary>Why do I see a warning about multiple IRRs?</summary><p>When cash flows change sign more than once (for example out, in, then out again), more than one rate can solve the equation. Use NPV to judge such projects.</p></details>
    <details><summary>Is my data saved?</summary><p>No. All calculations run in your browser. Nothing is sent to a server or stored.</p></details>
  </section>
</main>

<footer><div class="wrap">
  This calculator is for information only and is not financial advice. Results depend on the numbers you enter.
</div></footer>

<script>
(function(){
  var $=function(id){return document.getElementById(id)};
  var rows=[];
  function demo(){
    rows=[-100000,30000,35000,40000,45000].map(function(a,i){return {a:a,d:(2026+i)+'-01-01'}});
  }
  demo();

  function isDate(){return $('mode').value==='date'}
  function ppy(){return isDate()?1:+$('freq').value}
  function cur(){return $('cur').value}
  function money(v){
    try{return new Intl.NumberFormat(undefined,{style:'currency',currency:cur(),maximumFractionDigits:0}).format(v)}
    catch(e){return Math.round(v).toLocaleString()}
  }
  function pct(v){return (v*100).toFixed(2)+'%'}
  function esc(s){return String(s).replace(/"/g,'&quot;')}

  function render(){
    var d=isDate();
    $('freqBox').classList.toggle('hidden',d);
    $('whenH').textContent=d?'Date':'Period';
    var unit=$('freq').options[$('freq').selectedIndex].text;
    $('rows').innerHTML=rows.map(function(r,i){
      var when=d?'<input type="date" data-i="'+i+'" data-k="d" value="'+esc(r.d)+'" aria-label="Date '+(i+1)+'">':unit+' '+i;
      return '<tr><td class="when">'+when+'</td>'+
        '<td><input type="number" step="any" inputmode="decimal" data-i="'+i+'" data-k="a" value="'+(r.a===''?'':r.a)+'" aria-label="Amount '+(i+1)+'"></td>'+
        '<td class="x"><button class="btn sm" type="button" data-del="'+i+'" aria-label="Remove row '+(i+1)+'">×</button></td></tr>';
    }).join('');
    calc();
  }

  function npvAt(cf,ts,r){
    var s=0;
    for(var i=0;i<cf.length;i++)s+=cf[i]*Math.pow(1+r,-ts[i]);
    return s;
  }
  function solve(cf,ts){
    var a=-0.99,fa=npvAt(cf,ts,a),b,fb;
    while(a<1000){
      b=a+(a<1?0.005:a<10?0.05:1);
      fb=npvAt(cf,ts,b);
      if(isFinite(fa)&&isFinite(fb)&&fa*fb<=0){
        var lo=a,hi=b,flo=fa;
        for(var k=0;k<200;k++){
          var m=(lo+hi)/2,fm=npvAt(cf,ts,m);
          if(flo*fm<=0)hi=m;else{lo=m;flo=fm}
        }
        return (lo+hi)/2;
      }
      a=b;fa=fb;
    }
    return null;
  }

  function show(id,on){$(id).classList.toggle('hidden',!on)}
  function setStat(id,text,cls){var e=$(id);e.textContent=text;e.className=cls||''}

  function calc(){
    show('err',false);show('warn',false);
    var cf=rows.map(function(r){return parseFloat(r.a)||0});
    var d=isDate(),n=ppy(),ts;
    if(d){
      var t0=new Date(rows[0]&&rows[0].d).getTime();
      ts=rows.map(function(r){return (new Date(r.d).getTime()-t0)/864e5/365});
      if(ts.some(function(t){return !isFinite(t)})){return fail('Please enter a valid date in every row.')}
    }else{
      ts=rows.map(function(r,i){return i});
    }
    var hasNeg=cf.some(function(v){return v<0}),hasPos=cf.some(function(v){return v>0});
    if(rows.length<2||!hasNeg||!hasPos){
      return fail('Enter at least one negative amount (money out) and one positive amount (money in).');
    }
    var inv=0,rec=0;
    cf.forEach(function(v){if(v<0)inv+=-v;else rec+=v});
    var changes=0;
    cf.filter(function(v){return v!==0}).forEach(function(v,i,arr){if(i&&(v>0)!==(arr[i-1]>0))changes++});

    var r=solve(cf,ts);
    var D=(parseFloat($('disc').value)||0)/100;
    var dr=d?D:Math.pow(1+D,1/n)-1;
    var npv=npvAt(cf,ts,dr);

    if(r===null){fail('No IRR was found. The cash flows may never reach break-even.');}
    else{
      var annual=d?r:Math.pow(1+r,n)-1;
      $('out').classList.remove('hidden');
      $('irrLabel').textContent=d?'XIRR (per year)':'Internal rate of return (per year)';
      $('irr').textContent=pct(annual);
      $('irrSub').textContent=(!d&&n>1)?'Rate per '+(n===12?'month':'quarter')+': '+pct(r):'';
      if(changes>1){$('warn').textContent='Your cash flows change sign '+changes+' times, so more than one IRR may exist. Check the NPV as well.';show('warn',true)}
    }
    $('out').classList.remove('hidden');
    setStat('npv',money(npv),npv>=0?'pos':'neg');
    setStat('profit',money(rec-inv),rec-inv>=0?'pos':'neg');
    setStat('inv',money(inv));
    setStat('rec',money(rec));
    setStat('mult',(rec/inv).toFixed(2)+'x');
    setStat('pay',payback(cf,ts,d,n));
    chart(cf,ts,r,d,n);
  }

  function payback(cf,ts,d,n){
    var cum=0;
    for(var i=0;i<cf.length;i++){
      var prev=cum;cum+=cf[i];
      if(i>0&&prev<0&&cum>=0){
        var frac=cf[i]===0?0:-prev/cf[i];
        var t=ts[i-1]+(ts[i]-ts[i-1])*frac;
        if(d)return t.toFixed(1)+' years';
        var u=n===12?'months':n===4?'quarters':'years';
        return t.toFixed(1)+' '+u;
      }
    }
    return 'Not reached';
  }

  function fail(msg){
    $('err').textContent=msg;show('err',true);
    $('out').classList.add('hidden');
  }

  function chart(cf,ts,r,d,n){
    var W=520,H=280,L=58,R=14,T=14,B=34;
    var lo=-0.1,hi=0.3;
    if(r!==null){lo=Math.min(0,r*2);hi=Math.max(0.1,r*2)}
    var N=60,pts=[],mn=Infinity,mx=-Infinity;
    for(var i=0;i<=N;i++){
      var x=lo+(hi-lo)*i/N,y=npvAt(cf,ts,x);
      if(!isFinite(y))continue;
      pts.push([x,y]);mn=Math.min(mn,y);mx=Math.max(mx,y);
    }
    mn=Math.min(mn,0);mx=Math.max(mx,0);
    if(mx===mn){mx=mn+1}
    var sx=function(x){return L+(x-lo)/(hi-lo)*(W-L-R)};
    var sy=function(y){return T+(mx-y)/(mx-mn)*(H-T-B)};
    var path=pts.map(function(p,i){return (i?'L':'M')+sx(p[0]).toFixed(1)+' '+sy(p[1]).toFixed(1)}).join('');
    var ann=function(x){return d?x:Math.pow(1+x,n)-1};
    var s='<svg viewBox="0 0 '+W+' '+H+'" role="img" aria-label="NPV compared with discount rate">';
    s+='<line x1="'+L+'" x2="'+(W-R)+'" y1="'+sy(0)+'" y2="'+sy(0)+'" stroke="currentColor" opacity=".35"/>';
    s+='<path d="'+path+'" fill="none" stroke="var(--accent)" stroke-width="3"/>';
    if(r!==null){
      s+='<line x1="'+sx(r)+'" x2="'+sx(r)+'" y1="'+T+'" y2="'+(H-B)+'" stroke="var(--hi)" stroke-width="2" stroke-dasharray="4 4"/>';
      s+='<circle cx="'+sx(r)+'" cy="'+sy(0)+'" r="6" fill="var(--hi)"/>';
    }
    for(var k=0;k<=4;k++){
      var xv=lo+(hi-lo)*k/4;
      s+='<text x="'+sx(xv)+'" y="'+(H-10)+'" font-size="12" text-anchor="middle" fill="currentColor" opacity=".7">'+(ann(xv)*100).toFixed(0)+'%</text>';
      var yv=mn+(mx-mn)*k/4;
      s+='<text x="'+(L-6)+'" y="'+(sy(yv)+4)+'" font-size="11" text-anchor="end" fill="currentColor" opacity=".7">'+short(yv)+'</text>';
    }
    s+='</svg>';
    $('chart').innerHTML=s;
  }
  function short(v){
    var a=Math.abs(v);
    if(a>=1e9)return (v/1e9).toFixed(1)+'B';
    if(a>=1e6)return (v/1e6).toFixed(1)+'M';
    if(a>=1e3)return (v/1e3).toFixed(0)+'K';
    return v.toFixed(0);
  }

  // events
  $('rows').addEventListener('input',function(e){
    var t=e.target,i=t.getAttribute('data-i');
    if(i===null)return;
    rows[i][t.getAttribute('data-k')]=t.value;
    calc();
  });
  $('rows').addEventListener('click',function(e){
    var i=e.target.getAttribute('data-del');
    if(i===null)return;
    rows.splice(+i,1);render();
  });
  $('add').addEventListener('click',function(){
    var last=rows[rows.length-1],d='2026-01-01';
    if(last&&last.d){var x=new Date(last.d);x.setFullYear(x.getFullYear()+1);if(!isNaN(x))d=x.toISOString().slice(0,10)}
    rows.push({a:'',d:d});render();
  });
  $('reset').addEventListener('click',function(){
    rows=[{a:'',d:'2026-01-01'},{a:'',d:'2027-01-01'}];render();
  });
  $('demo').addEventListener('click',function(){demo();render()});
  ['mode','freq','cur','disc'].forEach(function(id){
    $(id).addEventListener(id==='disc'?'input':'change',render);
  });
  render();
})();
</script>
</body>
</html>
