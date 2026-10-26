<!doctype html>
<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<title>내 꿈 썸타는 중</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Jua&family=Noto+Sans+KR:wght@400;500;700;900&display=swap">
<style>
/* Layout: 부스 포스터를 머리에 두고, 학생은 한 줄로 흐르는 설문 / 교사는 접수 목록 + 상담 카드 2단 */
:root{
  --bg:#FFF6F3; --surface:#FFFFFF; --surface2:#FFEFF3; --line:#EBD3DC;
  --ink:#33183F; --ink2:#6E5578; --muted:#9A879F;
  --pink:#E8456B; --pinkSoft:#FFE1E9; --plum:#3A1C47; --lav:#EEE7FF; --lavInk:#5B45A8;
  --mint:#E2F5EA; --mintInk:#1F7A4B; --sun:#FFF1C9; --sunInk:#8A5A00;
  --onPink:#FFFFFF;
  --display:"Jua","Noto Sans KR",system-ui,sans-serif;
  --body:"Noto Sans KR",system-ui,-apple-system,"Apple SD Gothic Neo","Malgun Gothic",sans-serif;
  --r:18px;
}
@media (prefers-color-scheme: dark){:root:not([data-theme="light"]){
  --bg:#1C1220; --surface:#28192E; --surface2:#33203A; --line:#4A3253;
  --ink:#F8ECF3; --ink2:#D3BCD8; --muted:#A58FAC;
  --pink:#FF6F8F; --pinkSoft:#4A2235; --plum:#F3D6E8; --lav:#2F2850; --lavInk:#C8BBFF;
  --mint:#1E3A2B; --mintInk:#8FE0B2; --sun:#3D3216; --sunInk:#FFD777; --onPink:#2A0F1A;
  color-scheme:dark}}
:root[data-theme="dark"]{
  --bg:#1C1220; --surface:#28192E; --surface2:#33203A; --line:#4A3253;
  --ink:#F8ECF3; --ink2:#D3BCD8; --muted:#A58FAC;
  --pink:#FF6F8F; --pinkSoft:#4A2235; --plum:#F3D6E8; --lav:#2F2850; --lavInk:#C8BBFF;
  --mint:#1E3A2B; --mintInk:#8FE0B2; --sun:#3D3216; --sunInk:#FFD777; --onPink:#2A0F1A;
  color-scheme:dark}
*{box-sizing:border-box}
[hidden]{display:none!important}
img{max-width:100%}
body{background:var(--bg);color:var(--ink);font-family:var(--body);font-size:16px;line-height:1.6;margin:0}
.wrap{max-width:1120px;margin:0 auto;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px));padding-block:16px 60px}
h1,h2,h3{font-family:var(--display);font-weight:400;text-wrap:balance;margin:0;letter-spacing:-.01em}
button,input,textarea,select{font:inherit;color:inherit}
button{cursor:pointer}
:focus-visible{outline:3px solid var(--pink);outline-offset:2px}
.hero{border-radius:var(--r);overflow:hidden;border:1px solid var(--line);background:#fde9ef}
.hero img{display:block;width:100%;height:auto}
.tabs{display:flex;gap:8px;margin:16px 0 18px;flex-wrap:wrap}
.tab{border:2px solid var(--plum);background:var(--surface);color:var(--ink);border-radius:999px;padding:8px 20px;font-weight:700}
.tab[aria-selected="true"]{background:var(--plum);color:var(--bg)}
.small{font-size:13px;color:var(--muted)}
.pill{display:inline-flex;align-items:center;gap:4px;border-radius:999px;padding:2px 10px;font-size:12.5px;font-weight:700;white-space:nowrap}
.p-wait{background:var(--sun);color:var(--sunInk)}
.p-doing{background:var(--lav);color:var(--lavInk)}
.p-done{background:var(--mint);color:var(--mintInk)}
.p-ky{background:var(--pinkSoft);color:var(--pink)}
.p-ex{background:var(--surface2);color:var(--ink2);border:1px dashed var(--line)}

/* ---------- 학생 설문 ---------- */
#student{max-width:760px;margin:0 auto}
.intro{background:var(--surface);border:1px solid var(--line);border-radius:var(--r);padding:18px 20px;display:grid;gap:12px}
.intro p{margin:0;color:var(--ink2)}
.progress{position:sticky;top:env(safe-area-inset-top,0px);z-index:5;background:var(--bg);padding:10px 0;margin-top:6px}
.bar{height:10px;border-radius:999px;background:var(--surface2);overflow:hidden;border:1px solid var(--line)}
.bar i{display:block;height:100%;width:0;background:var(--pink);transition:width .3s}
.progress .small{display:flex;justify-content:space-between;margin-top:4px}
.sec{margin-top:26px}
.sec-h{display:flex;align-items:center;gap:12px;margin-bottom:10px}
.sec-h .rn{font-family:var(--display);font-size:22px;width:44px;height:44px;border-radius:14px;display:grid;place-items:center;background:var(--plum);color:var(--bg);flex:0 0 auto}
.sec-h h2{font-size:24px}
.q{background:var(--surface);border:1px solid var(--line);border-radius:var(--r);padding:16px 18px;margin-top:10px}
.q legend,.q .ql{font-weight:700;padding:0;display:flex;gap:10px;align-items:flex-start;line-height:1.45}
.q fieldset{border:0;margin:0;padding:0;min-width:0}
.qn{flex:0 0 auto;width:28px;height:28px;border-radius:50%;background:var(--pink);color:var(--onPink);display:grid;place-items:center;font-size:14px;font-weight:900;margin-top:-1px}
.tagw{font-size:12px;font-weight:700;color:var(--pink);background:var(--pinkSoft);border-radius:6px;padding:1px 7px;margin-left:4px;white-space:nowrap}
.hint{font-size:13.5px;color:var(--ink2);margin:6px 0 0 38px}
.chips{display:flex;flex-wrap:wrap;gap:8px;margin:12px 0 0 38px}
.chip{position:relative}
.chip input{position:absolute;opacity:0;inset:0;cursor:pointer}
.chip span{display:inline-block;border:1.5px solid var(--line);background:var(--surface);border-radius:12px;padding:7px 14px;font-size:15px;transition:.15s}
.chip input:checked+span{background:var(--pink);border-color:var(--pink);color:var(--onPink);font-weight:700}
.chip input:focus-visible+span{outline:3px solid var(--plum);outline-offset:2px}
.chip input:disabled+span{opacity:.4}
textarea{display:block;width:calc(100% - 38px);margin:12px 0 0 38px;min-height:96px;border:1.5px solid var(--line);border-radius:14px;background:var(--surface2);padding:12px 14px;resize:vertical;line-height:1.6}
textarea.short{min-height:60px}
.sub{margin:12px 0 0 38px;font-size:14px;font-weight:700;color:var(--ink2)}
.sub+textarea{margin-top:6px}
.kygrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:8px;margin:12px 0 0 38px}
.kyc{position:relative}
.kyc input{position:absolute;opacity:0;inset:0;cursor:pointer;z-index:1}
.kyc div{border:1.5px solid var(--line);border-radius:14px;padding:10px 12px;background:var(--surface);height:100%}
.kyc b{font-family:var(--display);font-weight:400;font-size:19px;display:block}
.kyc small{font-size:12.5px;color:var(--ink2);line-height:1.35;display:block}
.kyc input:checked+div{background:var(--pinkSoft);border-color:var(--pink)}
.kyc input:checked+div b{color:var(--pink)}
.kyc input:focus-visible+div{outline:3px solid var(--plum);outline-offset:2px}
.kyc input:disabled+div{opacity:.45}
input[type=text]{border:1.5px solid var(--line);border-radius:12px;background:var(--surface2);padding:9px 12px;width:100%;max-width:280px}
.submitrow{margin-top:26px;display:grid;gap:10px;justify-items:center;text-align:center}
.btn{border:0;border-radius:999px;padding:12px 26px;font-weight:900;background:var(--pink);color:var(--onPink);font-size:17px}
.btn.ghost{background:var(--surface);color:var(--ink);border:2px solid var(--line);font-weight:700;font-size:15px;padding:9px 18px}
.btn.plum{background:var(--plum);color:var(--bg)}
.btn:disabled{opacity:.5;cursor:not-allowed}
.err{color:var(--pink);font-weight:700;font-size:14px}
.done{background:var(--surface);border:2px solid var(--pink);border-radius:24px;padding:26px 22px;text-align:center;display:grid;gap:14px;justify-items:center}
.ticket{font-family:var(--display);font-size:64px;line-height:1;color:var(--pink)}
.mini{width:100%;text-align:left;background:var(--surface2);border-radius:16px;padding:14px 16px;display:grid;gap:6px}
.mini div{display:flex;gap:10px}
.mini dt{flex:0 0 92px;color:var(--ink2);font-size:14px;font-weight:700}
.mini dd{margin:0;min-width:0}
.panelimg{margin-top:28px;border-radius:var(--r);overflow:hidden;border:1px solid var(--line)}
.panelimg img{display:block;width:100%}
.panelimg figcaption{padding:10px 14px;font-size:13px;color:var(--ink2);background:var(--surface)}

/* ---------- 교사 ---------- */
.lock{max-width:420px;margin:30px auto;background:var(--surface);border:1px solid var(--line);border-radius:var(--r);padding:22px;display:grid;gap:12px;text-align:center;justify-items:center}
.lock input{text-align:center;letter-spacing:.4em;font-size:22px;max-width:180px}
.stats{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:10px}
.stat{background:var(--surface);border:1px solid var(--line);border-radius:16px;padding:12px 14px}
.stat b{font-family:var(--display);font-size:30px;font-weight:400;line-height:1.1;display:block;font-variant-numeric:tabular-nums}
.stat span{font-size:13px;color:var(--ink2)}
.kybars{background:var(--surface);border:1px solid var(--line);border-radius:16px;padding:12px 14px;margin-top:10px;display:grid;gap:6px}
.kyrow{display:grid;grid-template-columns:56px 1fr 34px;gap:8px;align-items:center;font-size:13.5px}
.kyrow .tr{height:12px;border-radius:999px;background:var(--surface2);overflow:hidden}
.kyrow .tr i{display:block;height:100%;background:var(--pink);border-radius:999px}
.kyrow em{font-style:normal;text-align:right;font-variant-numeric:tabular-nums;color:var(--ink2)}
.tgrid{display:grid;grid-template-columns:minmax(0,320px) minmax(0,1fr);gap:16px;margin-top:16px;align-items:start}
@media (max-width:860px){.tgrid{grid-template-columns:minmax(0,1fr)}}
.listbox{background:var(--surface);border:1px solid var(--line);border-radius:var(--r);overflow:hidden}
.filters{display:flex;gap:6px;flex-wrap:wrap;padding:12px;border-bottom:1px solid var(--line)}
.filters button{border:1.5px solid var(--line);background:var(--surface);border-radius:999px;padding:3px 12px;font-size:13.5px}
.filters button[aria-pressed="true"]{background:var(--plum);color:var(--bg);border-color:var(--plum)}
.items{max-height:70vh;overflow:auto}
.item{display:grid;grid-template-columns:auto 1fr auto;gap:4px 10px;width:100%;text-align:left;background:none;border:0;border-bottom:1px solid var(--line);padding:12px 14px;align-items:center}
.item:hover{background:var(--surface2)}
.item[aria-current="true"]{background:var(--pinkSoft)}
.item .no{font-family:var(--display);font-size:22px;color:var(--pink);font-variant-numeric:tabular-nums}
.item .nm{font-weight:700;min-width:0;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.item .meta{grid-column:2/4;display:flex;gap:4px;flex-wrap:wrap;font-size:12.5px;color:var(--muted)}
.empty{padding:22px 16px;text-align:center;color:var(--ink2);display:grid;gap:10px;justify-items:center}
.detail{display:grid;gap:14px;min-width:0}
.card{background:var(--surface);border:1px solid var(--line);border-radius:var(--r);padding:16px 18px;min-width:0}
.card h3{font-size:21px;display:flex;align-items:center;gap:8px;flex-wrap:wrap}
.card h4{margin:14px 0 4px;font-size:15px}
.dhead{display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap;align-items:center}
.dhead .big{font-family:var(--display);font-size:40px;color:var(--pink);line-height:1}
.statusbtns{display:flex;gap:6px;flex-wrap:wrap}
.statusbtns button{border:1.5px solid var(--line);background:var(--surface);border-radius:999px;padding:4px 14px;font-size:14px;font-weight:700}
.statusbtns button[aria-pressed="true"].s-wait{background:var(--sun);color:var(--sunInk);border-color:transparent}
.statusbtns button[aria-pressed="true"].s-doing{background:var(--lav);color:var(--lavInk);border-color:transparent}
.statusbtns button[aria-pressed="true"].s-done{background:var(--mint);color:var(--mintInk);border-color:transparent}
.ans{display:grid;gap:8px;margin-top:10px}
.ans .r{display:grid;grid-template-columns:150px 1fr;gap:10px;font-size:14.5px;border-top:1px dashed var(--line);padding-top:8px}
@media (max-width:560px){.ans .r{grid-template-columns:1fr;gap:2px}}
.ans .r b{color:var(--ink2);font-weight:700}
.ans .r .free{background:var(--surface2);border-radius:10px;padding:6px 10px;white-space:pre-wrap;word-break:break-word}
.points{display:grid;gap:10px;margin-top:10px}
.pt{border-left:4px solid var(--pink);background:var(--surface2);border-radius:0 12px 12px 0;padding:10px 14px}
.pt.lav{border-color:var(--lavInk)}
.pt.mint{border-color:var(--mintInk)}
.pt.sun{border-color:var(--sunInk)}
.pt>b{display:block;margin-bottom:2px}
.pt p{margin:2px 0;font-size:14.5px}
.pt ul{margin:4px 0 0;padding-left:18px;font-size:14.5px}
.road{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:8px;margin-top:8px}
@media (max-width:560px){.road{grid-template-columns:1fr}}
.road div{background:var(--surface);border:1px solid var(--line);border-radius:12px;padding:8px 10px;font-size:13.5px}
.road div b{font-size:12.5px;color:var(--pink)}
.quote{font-style:normal;background:var(--surface);border:1px solid var(--line);border-radius:10px;padding:6px 10px;display:block;margin:4px 0;white-space:pre-wrap;word-break:break-word}
.flow{display:grid;gap:0;margin-top:10px}
.step{display:grid;grid-template-columns:64px 1fr;gap:12px;padding:10px 0;border-top:1px dashed var(--line)}
.step:first-child{border-top:0}
.step .t{font-family:var(--display);font-size:18px;color:var(--pink);line-height:1.2}
.step .t small{display:block;font-family:var(--body);font-size:12px;color:var(--muted)}
.step p{margin:0 0 4px;font-size:14.5px}
.rec label.f{display:block;font-weight:700;font-size:14px;margin:12px 0 4px}
.rec textarea{width:100%;margin:0;min-height:64px}
.booths{display:flex;flex-wrap:wrap;gap:6px}
.booths .chip span{font-size:13.5px;padding:5px 10px}
.saverow{display:flex;gap:10px;align-items:center;flex-wrap:wrap;margin-top:12px}
.result{border:2px solid var(--pink);background:var(--surface);border-radius:22px;padding:20px;display:grid;gap:12px}
.result h3{font-size:26px;color:var(--pink)}
.result .road div b{color:var(--lavInk)}
.confirm{display:flex;gap:8px;align-items:center;flex-wrap:wrap;font-size:14px}
.notice{background:var(--sun);color:var(--sunInk);border-radius:12px;padding:8px 12px;font-size:13.5px}
.footnote{margin-top:30px;font-size:12.5px;color:var(--muted);text-align:center}
@media (prefers-reduced-motion:reduce){*{transition:none!important}}
</style>

</head>
<body>
<div class="wrap">
  <header class="hero"><img src="hero.jpg" alt="내 꿈 썸타는 중 · 진로 전문가 상담실 · 나의 진로·학업 설계 사전 설문 (2026 부산 고교학점제 박람회, 중학교 3학년용)" width="1055" height="250"></header>

  <nav class="tabs" role="tablist" aria-label="화면 선택">
    <button class="tab" role="tab" id="tab-student" aria-selected="true" aria-controls="student">학생 설문</button>
    <button class="tab" role="tab" id="tab-teacher" aria-selected="false" aria-controls="teacher">상담 교사</button>
  </nav>

  <!-- ================= 학생 설문 ================= -->
  <main id="student" role="tabpanel" aria-labelledby="tab-student">
    <form id="form" novalidate>
      <section class="intro">
        <p>이 설문은 상담 선생님이 <b>나에게 꼭 맞는 진로·과목 선택과 공부 방법</b>을 안내하기 위한 자료예요. 정답은 없어요. 서답형에는 내 생각을 내 말로 적어 주세요. 상담은 여러분이 적은 내용에서 시작합니다.</p>
        <label for="nick" style="font-weight:700">상담 때 불러 줬으면 하는 이름 <span class="small">(별명 가능, 선택)</span></label>
        <input type="text" id="nick" maxlength="12" placeholder="예: 썸린이">
      </section>

      <div class="progress" aria-hidden="true"><div class="bar"><i id="barfill"></i></div><div class="small"><span>설문 진행</span><span id="bartext">0 / 10</span></div></div>

      <section class="sec">
        <div class="sec-h"><span class="rn">Ⅰ</span><h2>나를 알아보기</h2></div>
        <div class="q"><fieldset>
          <legend><span class="qn">1</span>나는 희망 진로(직업)가 정해져 있나요?</legend>
          <div class="chips" data-q="q1" data-type="radio"></div>
        </fieldset></div>
        <div class="q">
          <label class="ql" for="q2"><span class="qn">2</span><span>내가 좋아해서 시간 가는 줄 모르는 활동과, 주변에서 "잘한다"는 말을 듣는 일은 무엇인가요? <span class="tagw">서답형</span></span></label>
          <p class="hint">좋아하는 것 / 잘하는 것을 하나씩 적고, 그때 어떤 기분이 드는지도 적어 보세요.</p>
          <textarea id="q2" maxlength="400" placeholder="좋아하는 것: &#10;잘하는 것: "></textarea>
        </div>
      </section>

      <section class="sec">
        <div class="sec-h"><span class="rn">Ⅱ</span><h2>나의 관심 계열</h2></div>
        <div class="q"><fieldset>
          <legend><span class="qn">3</span><span>가장 관심 있는 계열은 무엇인가요? <span class="small">(최대 2개)</span></span></legend>
          <p class="hint">계열 = 비슷한 학과·직업을 묶은 큰 분야예요.</p>
          <div class="kygrid" id="q3box"></div>
        </fieldset></div>
        <div class="q">
          <label class="ql" for="q4"><span class="qn">4</span><span>관심 계열(또는 직업)에서 내가 가장 해 보고 싶은 일은 무엇이고, 왜 그 일이 끌리나요? <span class="tagw">서답형</span></span></label>
          <p class="hint">"나는 ○○ 분야에서 △△하는 일을 해 보고 싶다. 왜냐하면 ~"처럼 적어 보세요. 관심 계열이 없다면, 요즘 조금이라도 궁금한 분야를 적어도 좋아요.</p>
          <textarea id="q4" maxlength="400"></textarea>
        </div>
      </section>

      <section class="sec">
        <div class="sec-h"><span class="rn">Ⅲ</span><h2>과목과 고교학점제</h2></div>
        <div class="q"><fieldset>
          <legend><span class="qn">5</span><span>내가 좋아하거나 잘하는 과목은? <span class="small">(모두 선택)</span></span></legend>
          <div class="chips" data-q="q5" data-type="check"></div>
        </fieldset>
          <label class="sub" for="q5r">그 과목을 고른 이유를 간단하게 적어 주세요.</label>
          <textarea id="q5r" class="short" maxlength="250"></textarea>
        </div>
        <div class="q"><fieldset>
          <legend><span class="qn">6</span><span>내가 싫어하는 과목은? <span class="small">(모두 선택)</span></span></legend>
          <div class="chips" data-q="q6" data-type="check"></div>
        </fieldset>
          <label class="sub" for="q6r">싫어하는 이유를 간단하게 적어 주세요.</label>
          <textarea id="q6r" class="short" maxlength="250"></textarea>
        </div>
        <div class="q"><fieldset>
          <legend><span class="qn">7</span>고교학점제(과목을 골라 듣고, 학점을 채워 졸업하는 제도)에 대해 얼마나 알고 있나요?</legend>
          <div class="chips" data-q="q7" data-type="radio"></div>
        </fieldset></div>
      </section>

      <section class="sec">
        <div class="sec-h"><span class="rn">Ⅳ</span><h2>나의 공부 방법</h2></div>
        <div class="q"><fieldset>
          <legend><span class="qn">8</span>공부 계획은 어떻게 하고 있나요?</legend>
          <div class="chips" data-q="q8" data-type="radio"></div>
        </fieldset></div>
        <div class="q"><fieldset>
          <legend><span class="qn">9</span><span>공부에 집중하기 어렵게 만드는 것은? <span class="small">(최대 2개)</span></span></legend>
          <div class="chips" data-q="q9" data-type="check" data-max="2"></div>
        </fieldset></div>
      </section>

      <section class="sec">
        <div class="sec-h"><span class="rn">Ⅴ</span><h2>오늘 상담에서</h2></div>
        <div class="q">
          <label class="ql" for="q10"><span class="qn">10</span><span>진로와 관련해 요즘 가장 고민되는 것은 무엇인가요? 그 고민은 언제, 왜 생겼나요? <span class="tagw">서답형</span></span></label>
          <p class="hint">예: 하고 싶은 것과 잘하는 것이 달라서 / 관심 계열이 자꾸 바뀌어서 / 보호자와 생각이 달라서 …</p>
          <textarea id="q10" maxlength="500"></textarea>
        </div>
      </section>

      <div class="submitrow">
        <p class="err" id="formerr" hidden></p>
        <button type="submit" class="btn" id="submitbtn">설문 제출하고 상담 받기</button>
        <p class="small">이름은 적지 않아도 돼요. 응답은 오늘 상담에만 쓰여요.</p>
      </div>
    </form>

    <section id="donebox" hidden>
      <div class="done">
        <p style="margin:0;font-weight:700">응답해 줘서 고마워요! 내 접수 번호는</p>
        <div class="ticket" id="ticketno">#000</div>
        <p style="margin:0" id="donemsg">상담 선생님께 이 번호를 알려 주세요. 이제 썸 코치와 함께 내 꿈과 썸을 타 볼까요?</p>
        <dl class="mini" id="minicard"></dl>
        <button class="btn ghost" id="again" type="button">다음 친구 설문 시작하기</button>
      </div>
    </section>

  </main>

  <!-- ================= 교사 ================= -->
  <section id="teacher" role="tabpanel" aria-labelledby="tab-teacher" hidden>
    <div class="lock" id="lockbox">
      <h2 style="font-size:24px">상담 교사 화면</h2>
      <p class="small" style="margin:0">학생 응답이 보이는 화면이에요. 부스 운영 코드를 입력해 주세요.</p>
      <input type="text" id="pin" inputmode="numeric" maxlength="4" autocomplete="off" aria-label="운영 코드 4자리">
      <p class="err" id="pinerr" hidden>코드가 맞지 않아요. 다시 입력해 주세요.</p>
      <button class="btn plum" id="unlock" type="button">열기</button>
    </div>

    <div id="tmain" hidden>
      <div class="notice" id="dbnote" hidden></div>
      <div class="stats" id="stats"></div>
      <div class="kybars" id="kybars"></div>
      <div class="tgrid">
        <aside class="listbox">
          <div class="filters" id="filters">
            <button type="button" data-f="active" aria-pressed="true">대기·상담중</button>
            <button type="button" data-f="done" aria-pressed="false">완료</button>
            <button type="button" data-f="all" aria-pressed="false">전체</button>
            <button type="button" data-f="today" aria-pressed="false">오늘</button>
          </div>
          <div class="items" id="items"></div>
        </aside>
        <div class="detail" id="detail"></div>
      </div>
    </div>
  </section>

  <p class="footnote">2026 부산 고교학점제 박람회 · ZONE 3 진로 탐색존 · 8번 부스 진로 전문가 상담실</p>
</div>

<script>
(() => {
"use strict";
/* ▼ 구글 Apps Script 웹 앱 주소를 따옴표 안에 붙여 넣으세요 (…/exec 로 끝나는 주소) */
const API_URL = "PASTE_YOUR_APPS_SCRIPT_URL";
const OPTS = {
  q1: ["정해졌다", "2~3개 중에서 고민 중이다", "아직 없다"],
  q5: ["국어","수학","영어","사회","역사","과학","기술·가정","정보","체육","예술","제2외국어·한문"],
  q6: ["국어","수학","영어","사회","역사","과학","기술·가정","정보","체육","예술","제2외국어·한문"],
  q7: ["잘 알고 있다", "들어 본 적은 있다", "오늘 처음 들었다"],
  q8: ["계획을 세우고 대부분 지킨다", "계획은 세우지만 잘 못 지킨다", "그날그날 정해서 한다", "따로 계획하지 않는다"],
  q9: ["스마트폰·SNS","게임","피곤함·수면 부족","왜 공부해야 하는지 모르겠음","무엇부터 해야 할지 모르겠음","공부 환경(소음 등)"],
};
const KYS = [
  ["인문","언어·문학·역사·철학"],["사회","경영·법·행정·미디어"],["자연","수학·물리·화학·생명"],
  ["공학","기계·전자·컴퓨터·건축"],["의약","의학·간호·약학·보건"],["교육","교사·상담"],
  ["예체능","음악·미술·디자인·체육"],["아직 모르겠다","괜찮아요, 함께 찾아봐요"]
];

/* 계열별 안내 자료 — 2022 개정 교육과정 과목명(「2027 예비 고등학생을 위한 고교학점제 워크북」 과목표 기준) */
const KY = {
  "인문": { majors:["국어국문학과","영어영문학과","사학과","철학과","문예창작학과"], jobs:["작가","번역가","학예연구사","기자"],
    g:["문학","독서와 작문","화법과 언어","세계사","현대사회와 윤리"], c:["주제 탐구 독서","문학과 영상","동아시아 역사 기행","윤리와 사상","인문학과 윤리","영미 문학 읽기"], f:["독서 토론과 글쓰기","언어생활 탐구","역사로 탐구하는 현대 세계"],
    need:["국어","영어","사회","역사","제2외국어·한문"], act:"관심 주제의 책을 골라 읽고 독서 토론·주제 탐구 보고서로 이어 가기" },
  "사회": { majors:["경영학과","경제학과","법학과","행정학과","미디어커뮤니케이션학과","사회학과"], jobs:["경영 컨설턴트","변호사","공무원","PD·기자"],
    g:["사회와 문화","세계시민과 지리","확률과 통계","독서와 작문"], c:["정치","법과 사회","경제","국제 관계의 이해","경제 수학"], f:["사회문제 탐구","금융과 경제생활","매체 의사소통","실용 통계"],
    need:["사회","수학","국어","영어"], act:"뉴스 속 사회 문제 하나를 골라 자료를 모으고 내 의견 정리해 보기" },
  "자연": { majors:["수학과","물리학과","화학과","생명과학과","천문우주학과","통계학과"], jobs:["연구원","데이터 분석가","기상 전문가","과학 교사"],
    g:["대수","미적분Ⅰ","확률과 통계","물리학","화학","생명과학","지구과학"], c:["미적분Ⅱ","기하","역학과 에너지","물질과 에너지","세포와 물질대사","지구시스템과학","행성우주과학"], f:["수학과제 탐구","융합과학 탐구","기후변화와 환경생태"],
    need:["수학","과학"], act:"궁금한 자연 현상 하나를 정해 간단한 실험·관찰 기록 남겨 보기" },
  "공학": { majors:["기계공학과","전자공학과","컴퓨터공학과","건축학과","화학공학과","인공지능학과"], jobs:["소프트웨어 개발자","로봇 공학자","건축가","반도체 엔지니어"],
    g:["대수","미적분Ⅰ","확률과 통계","물리학","화학","정보"], c:["미적분Ⅱ","기하","역학과 에너지","전자기와 양자","인공지능 수학","인공지능 기초","로봇과 공학세계","데이터 과학"], f:["창의 공학 설계","소프트웨어와 생활","융합과학 탐구"],
    need:["수학","과학","정보","기술·가정"], act:"코딩·메이커 활동이나 생활 속 불편함을 해결하는 작은 발명 아이디어 만들어 보기" },
  "의약": { majors:["의예과","간호학과","약학과","치의예과","물리치료학과","보건행정학과"], jobs:["의사","간호사","약사","물리치료사"],
    g:["대수","미적분Ⅰ","확률과 통계","화학","생명과학"], c:["세포와 물질대사","생물의 유전","물질과 에너지","화학 반응의 세계","인간과 심리","보건"], f:["융합과학 탐구","과학의 역사와 문화"],
    need:["과학","수학"], act:"건강·질병 관련 기사나 책을 읽고, 봉사·직업인 인터뷰로 실제 일 알아보기" },
  "교육": { majors:["교육학과","초등교육과","유아교육과","특수교육과","국어·수학 등 교과교육과"], jobs:["교사","교육 연구원","청소년 상담사","에듀테크 기획자"],
    g:["사회와 문화","독서와 작문","가르치고 싶은 교과의 일반 선택 과목"], c:["교육의 이해","인간과 심리","윤리와 사상","가르치고 싶은 교과의 진로 선택 과목"], f:["독서 토론과 글쓰기","아동발달과 부모"],
    need:["국어"], act:"친구에게 개념을 설명해 주는 멘토링, 어린이 대상 봉사 활동 경험 쌓기" },
  "예체능": { majors:["음악학과","미술학과","디자인학과","체육교육과","스포츠과학과","연극영화과"], jobs:["디자이너","연주자","스포츠 트레이너","영상 크리에이터"],
    g:["음악","미술","연극","체육1·체육2"], c:["음악 연주와 창작","음악 감상과 비평","미술 창작","미술 감상과 비평","스포츠 과학","스포츠 문화","문학과 영상"], f:["음악과 미디어","미술과 매체","스포츠 생활1·2"],
    need:["예술","체육"], act:"작품·기록을 꾸준히 모아 나만의 포트폴리오 시작하기" },
};
const SUBJ2KY = { "국어":["인문","교육"], "영어":["인문","사회"], "사회":["사회"], "역사":["인문"], "수학":["자연","공학"], "과학":["자연","의약","공학"], "정보":["공학"], "기술·가정":["공학"], "체육":["예체능"], "예술":["예체능"], "제2외국어·한문":["인문"] };
const BOOTHS = [["1","고교학점제 소개관"],["2","부산온라인학교·공동교육과정"],["3","Q&A 궁금증 해결소"],["4","어떤 과목을?"],["5","계열별 진로 월드"],["6·7","진로검사 스테이션"],["9","다르게 배우는 교실"],["10","질문으로 여는 교실"]];

const $ = s => document.querySelector(s);
const esc = s => String(s ?? "").replace(/[&<>"']/g, c => ({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
const todayKey = (t = Date.now()) => { const d = new Date(t); return d.getFullYear()+"-"+String(d.getMonth()+1).padStart(2,"0")+"-"+String(d.getDate()).padStart(2,"0"); };
const hhmm = t => { const d = new Date(t); return String(d.getHours()).padStart(2,"0")+":"+String(d.getMinutes()).padStart(2,"0"); };
const mdhm = t => { const d = new Date(t); return (d.getMonth()+1)+"/"+d.getDate()+" "+hhmm(t); };

/* ---------- 탭 ---------- */
function showTab(which){
  const st = which === "student";
  $("#tab-student").setAttribute("aria-selected", st); $("#tab-teacher").setAttribute("aria-selected", !st);
  $("#student").hidden = !st; $("#teacher").hidden = st;
}
$("#tab-student").onclick = () => showTab("student");
$("#tab-teacher").onclick = () => { showTab("teacher"); if (!$("#lockbox").hidden) $("#pin").focus(); };
if (location.hash === "#teacher") showTab("teacher");

/* ---------- 학생 폼 만들기 ---------- */
document.querySelectorAll(".chips[data-q]").forEach(box => {
  const q = box.dataset.q, type = box.dataset.type === "radio" ? "radio" : "checkbox";
  box.innerHTML = OPTS[q].map((o,i) => `<label class="chip"><input type="${type}" name="${q}" id="${q}_${i}" value="${esc(o)}"><span>${esc(o)}</span></label>`).join("");
});
$("#q3box").innerHTML = KYS.map(([k,d],i) => `<label class="kyc"><input type="checkbox" name="q3" id="q3_${i}" value="${k}"><div><b>${k}</b><small>${d}</small></div></label>`).join("");

function limitChecks(name, max){
  const boxes = [...document.querySelectorAll(`input[name="${name}"]`)];
  const n = boxes.filter(b => b.checked).length;
  boxes.forEach(b => { if (!b.checked) b.disabled = n >= max; });
}
$("#form").addEventListener("change", e => {
  const t = e.target;
  if (t.name === "q3") {
    const unknown = document.querySelector('input[name="q3"][value="아직 모르겠다"]');
    if (t === unknown && t.checked) document.querySelectorAll('input[name="q3"]').forEach(b => { if (b !== unknown) b.checked = false; });
    else if (t !== unknown && t.checked) unknown.checked = false;
    limitChecks("q3", 2);
  }
  if (t.name === "q9") limitChecks("q9", 2);
  if (t.name === "q5" || t.name === "q6") { // 같은 과목을 좋아함/싫어함에 동시에 고르지 않게
    const other = t.name === "q5" ? "q6" : "q5";
    const o = document.querySelector(`input[name="${other}"][value="${CSS.escape(t.value)}"]`);
    if (t.checked && o) o.checked = false;
  }
  updateProgress();
});
$("#form").addEventListener("input", updateProgress);

function collect(){
  const one = n => (document.querySelector(`input[name="${n}"]:checked`) || {}).value || "";
  const many = n => [...document.querySelectorAll(`input[name="${n}"]:checked`)].map(b => b.value);
  const tx = id => $("#"+id).value.trim();
  return { nick: tx("nick"), q1: one("q1"), q2: tx("q2"), q3: many("q3"), q4: tx("q4"), q5: many("q5"), q5r: tx("q5r"),
    q6: many("q6"), q6r: tx("q6r"), q7: one("q7"), q8: one("q8"), q9: many("q9"), q10: tx("q10") };
}
function answeredCount(r){
  return [r.q1, r.q2, r.q3.length, r.q4, r.q5.length || r.q5r, r.q6.length || r.q6r, r.q7, r.q8, r.q9.length, r.q10].filter(Boolean).length;
}
function updateProgress(){
  const n = answeredCount(collect());
  $("#barfill").style.width = (n*10)+"%"; $("#bartext").textContent = n+" / 10";
}

/* ---------- 저장소: 구글 시트(Apps Script) ---------- */
const apiReady = /^https:\/\/script\.google\.com\//.test(API_URL);
async function api(payload){
  // text/plain 으로 보내야 Apps Script에서 CORS 사전 요청 없이 받을 수 있음
  const res = await fetch(API_URL, { method: "POST", headers: { "Content-Type": "text/plain;charset=utf-8" }, body: JSON.stringify(payload) });
  const j = await res.json();
  if (!j.ok) { const e = new Error(j.error || "error"); e.code = j.error; throw e; }
  return j;
}

async function submitResponse(r){
  r.no = Math.floor(100 + Math.random()*900);
  r.createdAt = Date.now(); r.day = todayKey(r.createdAt);
  r.id = "r" + r.createdAt.toString(36) + Math.random().toString(36).slice(2,6);
  r.status = "wait"; r.coachWord = ""; r.action = ""; r.memo = ""; r.booths = []; r.subjects = "";
  if (!apiReady) return { r, saved: false };
  try { await api({ action: "submit", data: r }); return { r, saved: true }; }
  catch (e) {
    try { await new Promise(t => setTimeout(t, 800)); await api({ action: "submit", data: r }); return { r, saved: true }; }
    catch (e2) { return { r, saved: false }; }
  }
}

$("#form").addEventListener("submit", async e => {
  e.preventDefault();
  const r = collect(), err = $("#formerr");
  const missing = [];
  if (!r.q1) missing.push("1번"); if (!r.q3.length) missing.push("3번"); if (!r.q7) missing.push("7번"); if (!r.q8) missing.push("8번");
  if (!r.q10) missing.push("10번");
  if (missing.length) { err.textContent = missing.join(", ") + " 문항에 답해 주세요."; err.hidden = false; return; }
  err.hidden = true;
  const btn = $("#submitbtn"); btn.disabled = true; btn.textContent = "보내는 중…";
  const res = await submitResponse(r);
  btn.disabled = false; btn.textContent = "설문 제출하고 상담 받기";
  $("#ticketno").textContent = "#" + res.r.no;
  $("#donemsg").textContent = res.saved
    ? "상담 선생님께 이 번호를 알려 주세요. 이제 썸 코치와 함께 내 꿈과 썸을 타 볼까요?"
    : "이 화면을 상담 선생님께 그대로 보여 주세요. (인터넷 연결 문제로 응답이 전송되지 않았어요.)";
  const ky = r.q3.join(", ");
  $("#minicard").innerHTML =
    `<div><dt>관심 계열</dt><dd>${esc(ky)}</dd></div>` +
    `<div><dt>좋아하는 과목</dt><dd>${esc(r.q5.join(", ") || "-")}</dd></div>` +
    `<div><dt>오늘의 고민</dt><dd>${esc(r.q10)}</dd></div>`;
  $("#form").hidden = true; $("#donebox").hidden = false;
  window.scrollTo({ top: 0, behavior: "smooth" });
});
$("#again").onclick = () => {
  $("#form").reset(); document.querySelectorAll("#form input").forEach(i => i.disabled = false);
  $("#form").hidden = false; $("#donebox").hidden = true; updateProgress(); window.scrollTo({ top: 0 });
};
updateProgress();

/* ---------- 교사 화면 ---------- */
let pin = ""; try { pin = sessionStorage.getItem("ssum-pin") || ""; } catch (e) {}
async function tryUnlock(){
  const v = $("#pin").value.trim(), err = $("#pinerr");
  if (!apiReady) { err.textContent = "Apps Script 주소가 아직 연결되지 않았어요. 예시 학생으로 화면만 볼 수 있어요."; err.hidden = false; pin = ""; openTeacher(); return; }
  $("#unlock").disabled = true;
  try { const j = await api({ action: "list", pin: v }); pin = v; try { sessionStorage.setItem("ssum-pin", v); } catch (e) {} applyRows(j.rows); openTeacher(); }
  catch (e) { err.textContent = e.code === "bad_pin" ? "코드가 맞지 않아요. 다시 입력해 주세요." : "응답을 불러오지 못했어요. 인터넷 연결을 확인해 주세요."; err.hidden = false; $("#pin").select(); }
  $("#unlock").disabled = false;
}
$("#unlock").onclick = tryUnlock;
$("#pin").addEventListener("keydown", e => { if (e.key === "Enter") tryUnlock(); });

let rows = [], filter = "active", selId = null, example = null, poll = null, detailFor = undefined;

const SAMPLE = { id: "__sample", isSample: true, nick: "예시 학생", no: 123, createdAt: Date.now(), day: todayKey(), status: "wait",
  q1: "2~3개 중에서 고민 중이다", q2: "좋아하는 것: 친구들이랑 유튜브 영상 편집하기, 레고로 뭔가 만들기\n잘하는 것: 수학 문제 설명해 주기. 친구가 이해하면 뿌듯해요.",
  q3: ["공학","교육"], q4: "게임이나 앱을 직접 만들어 보고 싶다. 내가 만든 걸 다른 사람이 재미있게 쓰면 좋을 것 같아서.",
  q5: ["수학","정보"], q5r: "답이 딱 떨어지는 게 좋고, 코딩 시간이 재밌어요.", q6: ["국어","과학"], q6r: "국어는 지문이 길어서 집중이 안 되고, 과학은 외울 게 많아요.",
  q7: "들어 본 적은 있다", q8: "계획은 세우지만 잘 못 지킨다", q9: ["스마트폰·SNS","무엇부터 해야 할지 모르겠음"],
  q10: "공학이랑 교육 둘 다 관심 있는데 뭘 골라야 할지 모르겠어요. 부모님은 선생님이 안정적이라고 하시는데 저는 개발자도 하고 싶어요.",
  coachWord: "", action: "", memo: "", booths: [], subjects: "" };

function applyRows(list){
  rows = (list || []).slice().sort((x, y) => (y.createdAt || 0) - (x.createdAt || 0));
  if (!$("#tmain").hidden) {
    renderStats(); renderList();
    // 입력 중인 상담 기록이 지워지지 않도록, 선택한 학생이 바뀌었거나 사라졌을 때만 상세를 다시 그림
    const cur = example && selId === example.id ? example : rows.find(x => x.id === selId);
    if (detailFor !== (cur ? cur.id : null)) renderDetail();
  }
}
async function refresh(){
  if (!pin) return;
  try { const j = await api({ action: "list", pin }); applyRows(j.rows); $("#dbnote").hidden = true; }
  catch (e) { const n = $("#dbnote"); n.hidden = false; n.textContent = "새 응답을 불러오지 못했어요. 15초 뒤 다시 시도해요."; }
}
function openTeacher(){
  $("#lockbox").hidden = true; $("#tmain").hidden = false;
  const note = $("#dbnote");
  if (!pin) { note.hidden = false; note.textContent = "구글 시트에 연결되지 않아 학생 응답을 불러올 수 없어요. 아래 예시 학생으로 상담 화면을 미리 볼 수 있어요."; }
  renderAll();
  if (pin && !poll) poll = setInterval(() => { if (!document.hidden) refresh(); }, 15000);
}
if (pin && apiReady) refresh().then(openTeacher);

document.getElementById("filters").addEventListener("click", e => {
  const b = e.target.closest("button[data-f]"); if (!b) return;
  filter = b.dataset.f;
  document.querySelectorAll("#filters button").forEach(x => x.setAttribute("aria-pressed", x === b));
  renderList();
});

function statusPill(s){ return s === "done" ? '<span class="pill p-done">상담 완료</span>' : s === "doing" ? '<span class="pill p-doing">상담 중</span>' : '<span class="pill p-wait">대기</span>'; }

function renderAll(){ renderStats(); renderList(); renderDetail(); }

function renderStats(){
  const t = todayKey(), td = rows.filter(r => r.day === t);
  const c = s => td.filter(r => (r.status||"wait") === s).length;
  $("#stats").innerHTML = [
    ["오늘 접수", td.length], ["대기", c("wait")], ["상담 중", c("doing")], ["상담 완료", c("done")], ["누적 응답", rows.length]
  ].map(([k,v]) => `<div class="stat"><b>${v}</b><span>${k}</span></div>`).join("");
  const counts = {}; KYS.forEach(([k]) => counts[k] = 0);
  rows.forEach(r => (r.q3||[]).forEach(k => { if (k in counts) counts[k]++; }));
  const max = Math.max(1, ...Object.values(counts));
  $("#kybars").innerHTML = `<div class="small" style="font-weight:700">관심 계열 분포 (누적, 1인 최대 2개)</div>` +
    KYS.map(([k]) => `<div class="kyrow"><span>${k === "아직 모르겠다" ? "미정" : k}</span><span class="tr"><i style="width:${counts[k]/max*100}%"></i></span><em>${counts[k]}</em></div>`).join("");
}

function visibleRows(){
  const t = todayKey();
  return rows.filter(r => filter === "all" ? true : filter === "done" ? r.status === "done" : filter === "today" ? r.day === t : r.status !== "done");
}
function renderList(){
  const list = visibleRows(), box = $("#items");
  if (!list.length) {
    box.innerHTML = `<div class="empty"><p style="margin:0">${rows.length ? "이 조건에 맞는 학생이 없어요." : "아직 들어온 설문이 없어요.<br>학생이 「학생 설문」 탭에서 제출하면 여기에 바로 나타나요."}</p>
      <button type="button" class="btn ghost" id="showSample">예시 학생으로 미리 보기</button></div>`;
    $("#showSample").onclick = () => { example = SAMPLE; selId = SAMPLE.id; renderDetail(); };
    return;
  }
  box.innerHTML = list.map(r => `<button type="button" class="item" data-id="${esc(r.id)}" aria-current="${r.id === selId}">
      <span class="no">#${esc(r.no)}</span><span class="nm">${esc(r.nick || "이름 없음")}</span>${statusPill(r.status)}
      <span class="meta">${(r.q3||[]).map(k => `<span class="pill p-ky">${esc(k)}</span>`).join("")}<span>${mdhm(r.createdAt)}</span></span></button>`).join("");
  box.querySelectorAll(".item").forEach(b => b.onclick = () => { selId = b.dataset.id; example = null; renderList(); renderDetail(); });
}

/* ---------- 상담 포인트 만들기 ---------- */
function inferKy(r){
  const chosen = (r.q3||[]).filter(k => KY[k]);
  if (chosen.length) return { list: chosen, inferred: false };
  const score = {};
  (r.q5||[]).forEach(s => (SUBJ2KY[s]||[]).forEach(k => score[k] = (score[k]||0) + 1));
  const list = Object.entries(score).sort((a,b) => b[1]-a[1]).slice(0,2).map(x => x[0]);
  return { list, inferred: true };
}
function kw(text, re){ return re.test(text || ""); }

function buildPoints(r){
  const P = [];
  // 1. 진로 결정 상태
  const st = {
    "정해졌다": ["희망 진로가 정해진 학생", "정해진 진로를 고교 과목·활동으로 구체화하는 데 집중하세요. 그 진로를 고른 이유(흥미·적성·가치)를 말로 확인하면, 바뀌더라도 다시 쓸 수 있는 기준이 됩니다."],
    "2~3개 중에서 고민 중이다": ["2~3개 진로 사이에서 고민하는 학생", "후보들의 공통점(좋아하는 활동, 필요한 과목)을 찾아 주세요. 고1 공통과목을 배우며 확인하고 2학년 선택과목을 고르면 되니 지금 하나로 정하지 않아도 된다는 점을 안내합니다."],
    "아직 없다": ["희망 진로가 아직 없는 학생", "\"없는 게 정상\"이라는 말로 시작하세요. 2번(좋아하는 것·잘하는 것)에서 출발해 계열 후보를 함께 떠올리고, 커리어넷 진로심리검사(직업흥미검사 → 직업적성검사 → 직업가치관검사)를 권합니다."]
  }[r.q1];
  if (st) P.push({ c:"lav", t:"진로 상태 · " + st[0], body:`<p>${st[1]}</p>` });

  // 2. 계열 로드맵
  const ky = inferKy(r);
  if (ky.list.length) {
    ky.list.forEach(k => {
      const d = KY[k];
      const like = (r.q5||[]).filter(s => d.need.includes(s)), hate = (r.q6||[]).filter(s => d.need.includes(s));
      let fit = "";
      if (like.length) fit += `<p>✔ 좋아하는 과목 <b>${esc(like.join("·"))}</b>이(가) ${k} 계열과 잘 이어져요. 이 연결을 학생에게 직접 짚어 주세요.</p>`;
      if (hate.length) fit += `<p>⚠ 싫어하는 과목 <b>${esc(hate.join("·"))}</b>은(는) ${k} 계열에서 중요한 과목이에요. 싫은 이유(6번)가 "흥미"인지 "기초 부족"인지 확인하고, 기초 부족이라면 중3 겨울방학 개념 정리를 첫 실천으로 잡아 주세요.</p>`;
      if (!like.length && !hate.length && (r.q5||[]).length) fit += `<p>좋아하는 과목과 ${k} 계열의 핵심 과목이 겹치지 않아요. 이 계열에 끌린 계기를 물어 흥미의 근거를 확인해 보세요.</p>`;
      P.push({ c:"", t:`${ky.inferred ? "탐색 후보 계열 · " : "관심 계열 · "}${k}`, body:
        (ky.inferred ? `<p>관심 계열을 고르지 않아 좋아하는 과목으로 후보를 추렸어요. 정답이 아니라 대화를 여는 제안으로 쓰세요.</p>` : "") +
        `<p><b>관련 학과</b> ${esc(d.majors.join(", "))}<br><b>관련 직업</b> ${esc(d.jobs.join(", "))}</p>
         <div class="road"><div><b>일반 선택</b><br>${esc(d.g.join(", "))}</div><div><b>진로 선택</b><br>${esc(d.c.join(", "))}</div><div><b>융합 선택</b><br>${esc(d.f.join(", "))}</div></div>
         ${fit}<p><b>중3에 해 볼 탐색</b> ${esc(d.act)}</p>` });
    });
    P.push({ c:"sun", t:"과목 안내 시 함께 전할 점", body:`<ul><li>학교마다 개설 과목이 달라요. 희망 고교의 교육과정 편성표를 학교알리미(공시정보 → 학교교육과정 편성·운영)에서 확인하도록 안내하세요.</li><li>학교에 원하는 과목이 없으면 공동교육과정·부산온라인학교로 들을 수 있어요(2번 부스).</li><li>친한 친구가 고른 과목을 따라 고르지 않기!</li></ul>` });
  } else {
    P.push({ c:"", t:"관심 계열 · 아직 모르겠다", body:`<p>좋아하는 과목도 비어 있어요. 2번 답(좋아하는 활동)에서 계열을 함께 찾고, 5번 부스(계열별 진로 월드)와 6·7번 진로검사 스테이션을 연계하세요.</p>` });
  }

  // 3. 고교학점제
  if (r.q7 && r.q7 !== "잘 알고 있다") P.push({ c:"mint", t:`고교학점제 · "${r.q7}"`, body:`<p>핵심만 3가지로 짧게 안내하세요.</p><ul>
     <li>1학년은 공통 과목 중심(학급 단위), 2·3학년은 진로·적성에 따라 고른 선택 과목을 들어요.</li>
     <li>과목마다 기준 수업량의 2/3 이상 출석하고 학업 성취율 40% 이상(공통 과목)이면 학점을 얻어요.</li>
     <li>그래서 입학 전부터 내 진로를 고민해 두면 과목 선택이 쉬워져요. 1번 부스(고교학점제 소개관)도 들러 보세요.</li></ul>` });

  // 4. 공부 방법
  const plan = {
    "계획을 세우고 대부분 지킨다": "계획 실천력이 강점이에요. 지금 방식에 \"고1 공통과목 예습\"을 한 칸 추가하는 정도로 칭찬과 함께 안내하세요.",
    "계획은 세우지만 잘 못 지킨다": "계획이 너무 큰 경우가 많아요. 주간 목표 1개 + 하루 할 일 3개로 줄이고, 시간보다 \"분량\"(문제 10개, 교과서 2쪽)으로 세우게 하세요.",
    "그날그날 정해서 한다": "매일 시작이 늦어지기 쉬워요. 요일별로 과목을 고정해 두는 \"고정 루틴\"부터 제안하세요.",
    "따로 계획하지 않는다": "오늘 배운 과목 1개를 10분 복습하는 것부터 시작해, 일주일 실천 체크표를 만들어 보게 하세요."
  }[r.q8];
  const dist = { "스마트폰·SNS":"공부할 때는 휴대폰을 다른 방에 두고, 25분 집중 + 5분 휴식으로 짧게 끊어 집중하기",
    "게임":"게임은 공부 뒤의 보상으로 순서를 바꾸고, 시간을 미리 정해 두기",
    "피곤함·수면 부족":"잠드는 시간을 먼저 고정하고, 어려운 과목은 덜 피곤한 시간대에 배치하기",
    "왜 공부해야 하는지 모르겠음":"관심 계열(4번 답)과 지금 과목을 연결해 \"이 과목이 내 꿈에 어디에 쓰이는지\" 함께 찾아보기",
    "무엇부터 해야 할지 모르겠음":"가장 약한 과목의 기초 개념 1개를 우선순위 1번으로 두고, 할 일을 3개까지만 적기",
    "공부 환경(소음 등)":"도서관·자습실처럼 공부만 하는 장소를 하나 정해 두기" };
  const dl = (r.q9||[]).map(x => `<li><b>${esc(x)}</b> → ${dist[x] || ""}</li>`).join("");
  if (plan || dl) P.push({ c:"lav", t:"공부 방향 · 바로 해 볼 1가지 고르기", body:(plan ? `<p><b>${esc(r.q8)}</b> → ${plan}</p>` : "") + (dl ? `<ul>${dl}</ul>` : "") });

  // 5. 고민 키워드
  const q10 = r.q10 || "", tips = [];
  if (kw(q10, /부모|엄마|아빠|보호자|가족/)) tips.push("보호자와 생각이 다른 고민이에요. 학생의 생각을 먼저 충분히 듣고, 보호자와 이야기할 때 쓸 \"내가 이 진로를 원하는 이유 3가지\"를 함께 정리해 주세요.");
  if (kw(q10, /성적|점수|등급|공부를 못|못해/)) tips.push("성적 걱정이 있어요. 진로 선택은 성적만이 아니라 흥미·적성·가치를 함께 본다는 점과, 지금부터 고칠 수 있는 공부 습관 1가지를 연결해 주세요.");
  if (kw(q10, /없|모르겠/)) tips.push("방향을 잃은 느낌이 보여요. 2번에 쓴 좋아하는 활동에서 출발해 \"작은 탐색 1가지\"로 마무리하세요.");
  if (kw(q10, /바뀌|많아|둘 다|여러|고르/)) tips.push("관심이 여러 곳이에요. 진로가 바뀌어도 괜찮다는 점을 먼저 전하고, 공통 과목·공통 역량(예: 수학, 글쓰기)을 찾아 주세요.");
  if (kw(q10, /고등학교|고교|특목|자사|일반고|특성화/)) tips.push("고교 선택 고민이 있어요. 학교 유형별로 교육과정과 개설 과목이 다르다는 점과 학교알리미 확인 방법을 안내하세요.");
  if (tips.length) P.push({ c:"sun", t:"10번 고민에서 읽히는 신호", body:`<ul>${tips.map(t => `<li>${t}</li>`).join("")}</ul>` });

  return P;
}

function suggestBooths(r){
  const s = new Set();
  if (r.q1 === "아직 없다" || (r.q3||[]).includes("아직 모르겠다")) { s.add("5"); s.add("6·7"); }
  if (r.q7 && r.q7 !== "잘 알고 있다") s.add("1");
  if ((r.q5||[]).length || (r.q6||[]).length) s.add("4");
  if ((r.q3||[]).length && !(r.q3||[]).includes("아직 모르겠다")) s.add("5");
  return [...s];
}

function flowHTML(r){
  const ky = inferKy(r).list, q = s => s ? `<span class="quote">"${esc(s)}"</span>` : "";
  return `<div class="flow">
    <div class="step"><div class="t">2분<small>마음 열기</small></div><div><p>인사 후 10번 고민을 학생의 말 그대로 되짚으며 시작하세요.</p>${q(r.q10)}<p>여는 질문: "이 고민이 풀리면 지금과 뭐가 달라질 것 같아?"</p></div></div>
    <div class="step"><div class="t">4분<small>나를 알기</small></div><div><p>2번 답으로 흥미·강점을 확인하세요.</p>${q(r.q2)}<p>여는 질문: "그걸 할 때 가장 즐거운 순간은 언제야?" / "잘한다는 말을 들었을 때 어떤 기분이었어?"</p></div></div>
    <div class="step"><div class="t">6분<small>계열·과목 연결</small></div><div><p>${ky.length ? `<b>${esc(ky.join(", "))}</b> 계열` : "계열 후보"}과 4번 답을 연결하고, 위 상담 포인트의 고교 선택과목을 2~3개만 골라 보여 주세요.</p>${q(r.q4)}<p>여는 질문: "그 일을 하는 사람을 실제로 본 적 있어? 어떤 모습이 끌렸어?"</p></div></div>
    <div class="step"><div class="t">2분<small>공부 방향</small></div><div><p>8·9번 응답에서 처방 1가지만 골라 \"이번 주 실천\"으로 정하세요.</p></div></div>
    <div class="step"><div class="t">1분<small>정리·연계</small></div><div><p>상담 선생님의 한마디와 실천 1가지를 아래에 적고, 추천 부스를 안내한 뒤 「학생 결과 카드」를 보여 주세요.</p></div></div>
  </div>`;
}

function renderDetail(){
  const box = $("#detail");
  const r = example && selId === example.id ? example : rows.find(x => x.id === selId);
  detailFor = r ? r.id : null;
  if (!r) {
    box.innerHTML = `<div class="card"><h3>학생을 선택하세요</h3><p class="small" style="margin:6px 0 0">왼쪽 목록에서 접수 번호를 누르면 응답 요약, 자동 상담 포인트, 20분 상담 흐름, 상담 기록 칸이 열려요.</p></div>`;
    return;
  }
  const isS = !!r.isSample;
  const list = a => (a && a.length) ? a.map(esc).join(", ") : "-";
  const free = s => s ? `<div class="free">${esc(s)}</div>` : `<div class="small">(응답 없음)</div>`;
  const sugg = suggestBooths(r), booths = (r.booths && r.booths.length) ? r.booths : sugg;
  const ky = inferKy(r).list;
  const defaultSubjects = r.subjects || (ky[0] ? KY[ky[0]].c.slice(0,3).join(", ") : "");
  box.innerHTML = `
  <div class="card">
    <div class="dhead">
      <div><div class="big">#${esc(r.no)}</div><div style="font-weight:700">${esc(r.nick || "이름 없음")} ${isS ? '<span class="pill p-ex">예시 · 저장되지 않음</span>' : ""}</div><div class="small">${mdhm(r.createdAt)} 접수</div></div>
      <div class="statusbtns" role="group" aria-label="상담 상태">
        <button type="button" class="s-wait" data-s="wait" aria-pressed="${(r.status||"wait")==="wait"}">대기</button>
        <button type="button" class="s-doing" data-s="doing" aria-pressed="${r.status==="doing"}">상담 중</button>
        <button type="button" class="s-done" data-s="done" aria-pressed="${r.status==="done"}">상담 완료</button>
      </div>
    </div>
  </div>

  <div class="card">
    <h3>학생 응답</h3>
    <div class="ans">
      <div class="r"><b>1 희망 진로</b><span>${esc(r.q1 || "-")}</span></div>
      <div class="r"><b>2 좋아하는 것·잘하는 것</b>${free(r.q2)}</div>
      <div class="r"><b>3 관심 계열</b><span>${list(r.q3)}</span></div>
      <div class="r"><b>4 해 보고 싶은 일</b>${free(r.q4)}</div>
      <div class="r"><b>5 좋아하는 과목</b><span>${list(r.q5)}${r.q5r ? `<div class="free" style="margin-top:4px">${esc(r.q5r)}</div>` : ""}</span></div>
      <div class="r"><b>6 싫어하는 과목</b><span>${list(r.q6)}${r.q6r ? `<div class="free" style="margin-top:4px">${esc(r.q6r)}</div>` : ""}</span></div>
      <div class="r"><b>7 고교학점제</b><span>${esc(r.q7 || "-")}</span></div>
      <div class="r"><b>8 공부 계획</b><span>${esc(r.q8 || "-")}</span></div>
      <div class="r"><b>9 집중 방해</b><span>${list(r.q9)}</span></div>
      <div class="r"><b>10 요즘 고민</b>${free(r.q10)}</div>
    </div>
  </div>

  <div class="card">
    <h3>상담 포인트 <span class="small" style="font-family:var(--body)">응답을 바탕으로 자동 정리</span></h3>
    <div class="points">${buildPoints(r).map(p => `<div class="pt ${p.c}"><b>${esc(p.t)}</b>${p.body}</div>`).join("")}</div>
  </div>

  <div class="card">
    <h3>15분 상담 흐름</h3>
    ${flowHTML(r)}
  </div>

  <div class="card rec">
    <h3>상담 기록</h3>
    <label class="f" for="f-subj">들어 보고 싶은 선택과목 (학생과 함께 정하기)</label>
    <textarea id="f-subj" class="short" maxlength="200">${esc(defaultSubjects)}</textarea>
    <label class="f" for="f-word">상담 선생님의 한마디 <span class="small">(학생 결과 카드에 보여요)</span></label>
    <textarea id="f-word" class="short" maxlength="200">${esc(r.coachWord || "")}</textarea>
    <label class="f" for="f-act">학생이 다음 주까지 해 볼 실천 1가지 <span class="small">(학생 결과 카드에 보여요)</span></label>
    <textarea id="f-act" class="short" maxlength="200">${esc(r.action || "")}</textarea>
    <span class="f" style="display:block;font-weight:700;font-size:14px;margin:12px 0 4px">더 알아볼 부스 <span class="small">(응답 기준으로 미리 골라 둠)</span></span>
    <div class="booths">${BOOTHS.map(([n,t],i) => `<label class="chip"><input type="checkbox" id="bt_${i}" value="${n}" ${booths.includes(n) ? "checked" : ""}><span>${n}번 ${t}</span></label>`).join("")}</div>
    <label class="f" for="f-memo">교사 메모 <span class="small">(학생에게 보이지 않음)</span></label>
    <textarea id="f-memo" class="short" maxlength="400">${esc(r.memo || "")}</textarea>
    <div class="saverow">
      <button type="button" class="btn plum" id="saveRec">${isS ? "예시는 저장되지 않아요" : "기록 저장"}</button>
      <button type="button" class="btn" id="showCard">학생 결과 카드 보기</button>
      <span class="small" id="saveMsg" role="status"></span>
    </div>
  </div>

  <div id="cardArea"></div>

  ${isS ? "" : `<div class="card"><div class="confirm" id="delArea"><button type="button" class="btn ghost" id="delBtn">이 응답 삭제</button><span class="small">박람회가 끝나면 응답을 지워 주세요.</span></div></div>`}
  `;

  const save = async (patch) => {
    if (isS) { Object.assign(r, patch); renderList(); return true; }
    try { await api({ action: "update", pin, id: r.id, patch }); Object.assign(r, patch); renderStats(); renderList(); return true; } catch (e) { $("#saveMsg").textContent = "저장하지 못했어요. 연결을 확인하고 다시 눌러 주세요."; return false; }
  };
  box.querySelectorAll(".statusbtns button").forEach(b => b.onclick = async () => {
    if (await save({ status: b.dataset.s })) { r.status = b.dataset.s; box.querySelectorAll(".statusbtns button").forEach(x => x.setAttribute("aria-pressed", x === b)); if (isS) renderList(); }
  });
  const recPatch = () => ({ subjects: $("#f-subj").value.trim(), coachWord: $("#f-word").value.trim(), action: $("#f-act").value.trim(), memo: $("#f-memo").value.trim(),
    booths: [...box.querySelectorAll(".booths input:checked")].map(i => i.value) });
  $("#saveRec").onclick = async () => {
    if (isS) { Object.assign(r, recPatch()); $("#saveMsg").textContent = "예시 학생이라 이 화면에만 반영했어요."; return; }
    const btn = $("#saveRec"); btn.disabled = true;
    if (await save(recPatch())) $("#saveMsg").textContent = "저장했어요 · " + hhmm(Date.now());
    btn.disabled = false;
  };
  $("#showCard").onclick = () => { Object.assign(r, recPatch()); renderCard(r); };
  const del = $("#delBtn");
  if (del) del.onclick = () => {
    $("#delArea").innerHTML = `<span>#${esc(r.no)} 응답을 지울까요? 되돌릴 수 없어요.</span><button type="button" class="btn" id="delYes" style="padding:6px 16px;font-size:14px">삭제</button><button type="button" class="btn ghost" id="delNo">취소</button>`;
    $("#delNo").onclick = renderDetail;
    $("#delYes").onclick = async () => { try { await api({ action: "delete", pin, id: r.id }); rows = rows.filter(x => x.id !== r.id); selId = null; renderAll(); } catch (e) { $("#delArea").textContent = "삭제하지 못했어요. 다시 시도해 주세요."; } };
  };
}

function renderCard(r){
  const ky = inferKy(r).list, d = ky[0] ? KY[ky[0]] : null;
  const booths = (r.booths||[]).map(n => { const b = BOOTHS.find(x => x[0] === n); return b ? `${b[0]}번 ${b[1]}` : n; });
  $("#cardArea").innerHTML = `<div class="result" aria-live="polite">
    <div class="small">내 꿈 썸타는 중 · 상담 결과 카드 · #${esc(r.no)}</div>
    <h3>${esc(r.nick || "오늘의 썸린이")}의 썸 일기</h3>
    <div class="road">
      <div><b>관심 계열</b><br>${esc(ky.join(", ") || "함께 찾는 중")}</div>
      <div><b>관련 직업</b><br>${esc(d ? d.jobs.slice(0,3).join(", ") : "-")}</div>
      <div><b>들어 보고 싶은 선택과목</b><br>${esc(r.subjects || "-")}</div>
    </div>
    <div class="pt"><b>상담 선생님의 한마디</b><p>${esc(r.coachWord || "(아직 적지 않았어요)")}</p></div>
    <div class="pt mint"><b>다음 주까지 해 볼 실천 1가지</b><p>${esc(r.action || "(아직 적지 않았어요)")}</p></div>
    ${booths.length ? `<div class="pt lav"><b>더 알아볼 부스</b><p>${esc(booths.join(" · "))}</p></div>` : ""}
    <p class="small" style="margin:0">이 화면을 사진으로 찍어 가세요. 상담 후에도 우리 학교 진로전담교사 · 부산진로진학지원센터 · 커리어넷 진로심리검사로 계속 이어 가요!</p>
  </div>`;
  $("#cardArea").scrollIntoView({ behavior: "smooth", block: "start" });
}
})();
</script>

</body>
</html>
