<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>英語30日トレーニング 🏉🎣</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;700;800;900&family=M+PLUS+Rounded+1c:wght@400;700&display=swap');
:root{
  --blue:#1a6fc4;--blue-l:#e8f2fc;--blue-d:#0d4a8c;
  --green:#2e9e5b;--green-l:#e6f7ed;
  --red:#d63b3b;--red-l:#fdeaea;
  --amber:#e07c00;--amber-l:#fff4e0;
  --gray:#f5f6f8;--gray2:#e8eaed;
  --text:#1a1c1e;--text2:#555a62;--text3:#8a9099;
  --r:16px;--rs:10px;
}
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent;}
body{font-family:'M PLUS Rounded 1c',sans-serif;background:#eef2f7;min-height:100vh;color:var(--text);}
#app{max-width:480px;margin:0 auto;min-height:100vh;background:#eef2f7;}
.screen{display:none;padding:14px;padding-bottom:40px;}
.screen.active{display:block;}
/* CARDS */
.card{background:#fff;border-radius:var(--r);padding:16px;margin-bottom:12px;box-shadow:0 2px 10px rgba(0,0,0,0.07);}
/* BUTTONS */
.btn{display:block;width:100%;padding:15px;border-radius:var(--r);border:none;font-family:'M PLUS Rounded 1c',sans-serif;font-size:16px;font-weight:700;cursor:pointer;transition:transform .1s;text-align:center;margin-bottom:10px;}
.btn:active{transform:scale(.97);}
.btn-blue{background:linear-gradient(135deg,var(--blue-d),var(--blue));color:#fff;box-shadow:0 4px 14px rgba(26,111,196,.3);}
.btn-outline{background:#fff;color:var(--blue);border:2px solid var(--blue);}
.btn-green{background:linear-gradient(135deg,#1e7d45,var(--green));color:#fff;box-shadow:0 4px 14px rgba(46,158,91,.25);}
.btn-gray{background:#fff;color:var(--text2);border:1.5px solid var(--gray2);}
/* HOME */
.home-hero{background:linear-gradient(135deg,var(--blue-d),var(--blue));border-radius:var(--r);padding:22px 18px;color:#fff;margin-bottom:14px;position:relative;overflow:hidden;}
.home-hero::after{content:'🏉';position:absolute;right:16px;top:50%;transform:translateY(-50%);font-size:56px;opacity:.2;}
.home-hero h1{font-family:'Nunito',sans-serif;font-size:21px;font-weight:900;margin-bottom:3px;}
.home-hero p{font-size:13px;opacity:.85;}
.stat-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;margin-bottom:12px;}
.stat{background:#fff;border-radius:var(--rs);padding:10px 6px;text-align:center;box-shadow:0 2px 8px rgba(0,0,0,.06);}
.stat-v{font-family:'Nunito',sans-serif;font-size:22px;font-weight:800;color:var(--blue);}
.stat-l{font-size:11px;color:var(--text3);margin-top:1px;}
/* CALENDAR */
.cal-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:8px;margin-top:10px;}
.day-btn{border-radius:var(--rs);border:none;padding:8px 4px;font-family:'M PLUS Rounded 1c',sans-serif;font-size:13px;font-weight:700;cursor:pointer;transition:transform .1s;text-align:center;background:#f0f4f8;color:var(--text2);}
.day-btn:active{transform:scale(.95);}
.day-btn.done{background:var(--green-l);color:var(--green);}
.day-btn.current{background:var(--blue);color:#fff;box-shadow:0 3px 10px rgba(26,111,196,.35);}
.day-btn.locked{opacity:.4;cursor:default;}
.day-num{font-size:15px;font-weight:800;}
.day-icon{font-size:14px;margin-top:2px;}
/* PROGRESS BAR */
.pbar{width:100%;height:9px;background:var(--gray2);border-radius:5px;overflow:hidden;margin:7px 0;}
.pfill{height:100%;background:linear-gradient(90deg,var(--blue),#5ab0ff);border-radius:5px;transition:width .5s cubic-bezier(.4,0,.2,1);}
.pfill-green{background:linear-gradient(90deg,var(--green),#5dd68e);}
/* QUIZ/TEST SCREEN */
.qheader{display:flex;align-items:center;gap:10px;margin-bottom:12px;}
.back-btn{background:#fff;border:none;border-radius:50%;width:36px;height:36px;font-size:18px;cursor:pointer;box-shadow:0 2px 8px rgba(0,0,0,.1);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
.qmeta{flex:1;}
.badge{display:inline-block;font-size:11px;font-weight:700;padding:3px 10px;border-radius:20px;}
.badge-quiz{background:#fff4e0;color:#a85a00;}
.badge-test{background:var(--blue-l);color:var(--blue-d);}
.qcard{background:#fff;border-radius:var(--r);padding:18px;margin-bottom:12px;box-shadow:0 2px 10px rgba(0,0,0,.07);}
.qcat{font-size:11px;font-weight:700;color:var(--blue);text-transform:uppercase;letter-spacing:.5px;margin-bottom:8px;display:flex;align-items:center;gap:5px;}
.qcat::before{content:'';display:block;width:3px;height:13px;background:var(--blue);border-radius:2px;}
.qtext{font-size:16px;font-weight:700;line-height:1.65;color:var(--text);margin-bottom:10px;}
.qhint{background:var(--amber-l);border-left:3px solid var(--amber);border-radius:0 var(--rs) var(--rs) 0;padding:8px 12px;font-size:13px;color:#a85a00;font-weight:700;line-height:1.5;}
.choices{display:flex;flex-direction:column;gap:9px;margin-top:12px;}
.cbtn{background:#fff;border:1.5px solid var(--gray2);border-radius:var(--rs);padding:13px 14px;font-size:15px;font-family:'M PLUS Rounded 1c',sans-serif;font-weight:700;color:var(--text);cursor:pointer;text-align:left;transition:all .15s;box-shadow:0 1px 4px rgba(0,0,0,.06);line-height:1.4;}
.cbtn:active{transform:scale(.98);}
.cbtn.correct{background:var(--green-l);border-color:var(--green);color:#1e7d45;}
.cbtn.wrong{background:var(--red-l);border-color:var(--red);color:#a32020;}
.cbtn:disabled{cursor:default;}
.feedback{border-radius:var(--r);padding:15px;margin-top:10px;animation:fadeUp .3s ease;}
@keyframes fadeUp{from{opacity:0;transform:translateY(6px);}to{opacity:1;transform:none;}}
.fb-ok{background:var(--green-l);border:1.5px solid #a3d9b8;}
.fb-ng{background:var(--red-l);border:1.5px solid #f5b0b0;}
.fb-title{font-size:15px;font-weight:800;margin-bottom:6px;}
.fb-ok .fb-title{color:var(--green);}
.fb-ng .fb-title{color:var(--red);}
.fb-explain{font-size:13px;line-height:1.65;}
.fb-ok .fb-explain{color:#1e7d45;}
.fb-ng .fb-explain{color:#a32020;}
/* RESULT */
.result-hero{background:linear-gradient(135deg,var(--blue-d),var(--blue));border-radius:var(--r);padding:26px 18px;text-align:center;color:#fff;margin-bottom:14px;box-shadow:0 4px 20px rgba(26,111,196,.25);}
.result-icon{font-size:46px;margin-bottom:6px;}
.result-title{font-family:'Nunito',sans-serif;font-size:21px;font-weight:900;margin-bottom:4px;}
.result-msg{font-size:13px;opacity:.9;line-height:1.55;}
.score-row{display:flex;justify-content:center;align-items:baseline;gap:3px;margin:10px 0;}
.score-big{font-family:'Nunito',sans-serif;font-size:50px;font-weight:900;}
.score-den{font-size:17px;opacity:.8;}
.wrong-item{padding:9px 0;border-bottom:1px solid var(--gray2);}
.wrong-item:last-child{border-bottom:none;}
.wrong-cat{font-size:11px;color:var(--text3);font-weight:700;}
.wrong-q{font-size:13px;color:var(--text);margin:2px 0;line-height:1.4;}
.wrong-ans{font-size:13px;color:var(--green);font-weight:700;}
/* PHASE TRANSITION */
.phase-banner{background:linear-gradient(135deg,#a85a00,var(--amber));border-radius:var(--r);padding:14px 16px;color:#fff;text-align:center;margin-bottom:12px;animation:fadeUp .4s ease;}
.phase-banner h3{font-size:15px;font-weight:800;margin-bottom:3px;}
.phase-banner p{font-size:13px;opacity:.9;}
/* WEEK LABELS */
.week-label{font-size:12px;font-weight:700;color:var(--text3);text-transform:uppercase;letter-spacing:.5px;margin:10px 0 6px;}
.tip-box{background:var(--blue-l);border-left:4px solid var(--blue);border-radius:0 var(--rs) var(--rs) 0;padding:11px 13px;font-size:13px;color:var(--blue-d);font-weight:700;line-height:1.6;margin-bottom:12px;}
</style>
</head>
<body>
<div id="app">

<!-- HOME -->
<div id="home" class="screen active">
  <div class="home-hero">
    <h1>英語30日トレーニング</h1>
    <p>好きな日を選んで毎日10分！評定4を目指せ🎣</p>
  </div>
  <div class="stat-row">
    <div class="stat"><div class="stat-v" id="h-done">0</div><div class="stat-l">完了日数</div></div>
    <div class="stat"><div class="stat-v" id="h-correct">0</div><div class="stat-l">正解数</div></div>
    <div class="stat"><div class="stat-v" id="h-rate">—</div><div class="stat-l">正答率</div></div>
  </div>
  <div class="card">
    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:6px;">
      <span style="font-size:13px;font-weight:700;color:var(--text2);">30日間の進捗</span>
      <span style="font-size:12px;color:var(--text3);" id="h-prog-txt">0 / 30日</span>
    </div>
    <div class="pbar"><div class="pfill" id="h-pbar" style="width:0%"></div></div>
  </div>
  <div class="card">
    <div style="font-size:13px;font-weight:700;color:var(--text2);margin-bottom:10px;">カレンダー — 好きな日をタップ！</div>
    <div class="week-label">Week 1 — 不規則動詞・現在完了の基本</div>
    <div class="cal-grid" id="cal-w1"></div>
    <div class="week-label" style="margin-top:12px;">Week 2 — 否定文・疑問文</div>
    <div class="cal-grid" id="cal-w2"></div>
    <div class="week-label" style="margin-top:12px;">Week 3 — 3用法マスター</div>
    <div class="cal-grid" id="cal-w3"></div>
    <div class="week-label" style="margin-top:12px;">Week 4 — 並び替え・英作文・総合</div>
    <div class="cal-grid" id="cal-w4"></div>
  </div>
  <div class="tip-box">クイズ3問でウォームアップ → テスト5問で腕試し！毎日10〜15分でOK💪</div>
</div>

<!-- DAY INTRO -->
<div id="intro" class="screen">
  <div class="qheader">
    <button class="back-btn" onclick="showScreen('home')">←</button>
    <div class="qmeta">
      <div style="font-size:15px;font-weight:800;" id="intro-title">Day 1</div>
      <div style="font-size:12px;color:var(--text3);" id="intro-week">Week 1 — 不規則動詞・現在完了の基本</div>
    </div>
  </div>
  <div class="card" style="text-align:center;padding:24px 18px;">
    <div style="font-size:40px;margin-bottom:10px;" id="intro-icon">🏉</div>
    <div style="font-size:18px;font-weight:800;margin-bottom:8px;" id="intro-theme"></div>
    <div style="font-size:14px;color:var(--text2);line-height:1.65;" id="intro-desc"></div>
  </div>
  <div class="card">
    <div style="display:flex;gap:12px;">
      <div style="flex:1;background:var(--amber-l);border-radius:var(--rs);padding:12px;text-align:center;">
        <div style="font-size:20px;font-weight:800;color:#a85a00;">3問</div>
        <div style="font-size:12px;color:#a85a00;margin-top:2px;">クイズ<br>ウォームアップ</div>
      </div>
      <div style="flex:1;background:var(--blue-l);border-radius:var(--rs);padding:12px;text-align:center;">
        <div style="font-size:20px;font-weight:800;color:var(--blue-d);">5問</div>
        <div style="font-size:12px;color:var(--blue-d);margin-top:2px;">テスト<br>本番形式</div>
      </div>
    </div>
  </div>
  <button class="btn btn-blue" onclick="startDay()">クイズからスタート！ ▶</button>
  <button class="btn btn-gray" onclick="showScreen('home')">カレンダーに戻る</button>
</div>

<!-- QUIZ/TEST -->
<div id="quiz" class="screen">
  <div class="qheader">
    <button class="back-btn" onclick="confirmBack()">←</button>
    <div class="qmeta">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:4px;">
        <span class="badge" id="q-badge">クイズ</span>
        <span style="font-size:13px;color:var(--text2);font-weight:700;" id="q-counter">1 / 3</span>
      </div>
      <div class="pbar"><div class="pfill" id="q-pbar" style="width:33%"></div></div>
    </div>
  </div>
  <div class="qcard">
    <div class="qcat" id="q-cat"></div>
    <div class="qtext" id="q-text"></div>
    <div class="qhint" id="q-hint" style="display:none;"></div>
  </div>
  <div class="choices" id="q-choices"></div>
  <div id="q-feedback" style="display:none;"></div>
  <button class="btn btn-blue" id="next-btn" style="display:none;margin-top:10px;" onclick="nextQ()">次へ →</button>
</div>

<!-- PHASE CHANGE -->
<div id="phase-change" class="screen">
  <div style="text-align:center;padding:40px 20px;">
    <div style="font-size:56px;margin-bottom:16px;">🎉</div>
    <div style="font-family:'Nunito',sans-serif;font-size:22px;font-weight:900;margin-bottom:10px;">クイズ完了！</div>
    <div style="font-size:15px;color:var(--text2);line-height:1.6;margin-bottom:24px;" id="pc-score"></div>
    <div class="phase-banner">
      <h3>🏉 次はテスト本番！</h3>
      <p>クイズで学んだことを試そう。落ち着いて考えてね！</p>
    </div>
    <button class="btn btn-blue" onclick="startTest()">テストへ進む ▶</button>
  </div>
</div>

<!-- RESULT -->
<div id="result" class="screen">
  <div class="result-hero">
    <div class="result-icon" id="r-icon">🏆</div>
    <div class="result-title" id="r-title">完了！</div>
    <div class="score-row">
      <span class="score-big" id="r-score">0</span>
      <span class="score-den" id="r-den">/ 5問</span>
    </div>
    <div class="result-msg" id="r-msg"></div>
  </div>
  <div class="card" id="r-wrong-card" style="display:none;">
    <div style="font-size:13px;font-weight:700;color:var(--text2);margin-bottom:10px;">間違えた問題の正解</div>
    <div id="r-wrong-list"></div>
  </div>
  <button class="btn btn-green" onclick="showScreen('home')" style="margin-top:4px;">カレンダーへ戻る 🏠</button>
  <button class="btn btn-outline" id="r-retry" style="display:none;" onclick="retryWrong()">間違えた問題を復習 🔄</button>
</div>

</div>

<script>
// ===================== DATA =====================
const DAYS = [
  // DAY 1
  {week:1,theme:'不規則動詞①',icon:'🏉',desc:'まずは現在完了形に必要な「過去分詞」を覚えよう！ラグビーや釣りの例で楽しく練習しよう。',
   quiz:[
    {cat:'ウォームアップ',q:'「throw（投げる）」の過去分詞は？',hint:'ヒント：ラグビーでボールがthrown！',choices:['threw','throwed','thrown','throw'],ans:2,explain:'throwの変化はthrow→threw→thrown。試合でパスがthrown（投げられた）とイメージしよう🏉'},
    {cat:'ウォームアップ',q:'「catch（捕まえる）」の過去分詞は？',hint:'ヒント：大きな魚をcaught！',choices:['catched','caught','caughted','catch'],ans:1,explain:'catchはcatch→caught→caught。過去形と過去分詞が同じだよ🎣'},
    {cat:'ウォームアップ',q:'「see（見る）」の過去分詞は？',hint:'ヒント：「シーン（場面）を見た」',choices:['saw','seed','seen','see'],ans:2,explain:'seeはsee→saw→seen。現在完了でよく使う！seen（シーン）で覚えよう👁'},
   ],
   test:[
    {cat:'不規則動詞',q:'「write（書く）」の過去分詞は？',hint:'ヒント：ダブルnに注意！',choices:['wrote','writed','written','write'],ans:2,explain:'writeはwrite→wrote→written。過去分詞はwritten！テストに出たよ✍'},
    {cat:'不規則動詞',q:'「buy（買う）」の過去分詞は？',hint:'ヒント：過去形と同じ！',choices:['buyed','bought','buied','buy'],ans:1,explain:'buyはbuy→bought→bought。過去形と過去分詞が同じ💰'},
    {cat:'不規則動詞',q:'「go（行く）」の過去分詞は？',hint:'ヒント：I have ( ) fishing.→釣りに行ったことがある',choices:['went','goed','gone','go'],ans:2,explain:'goはgo→went→gone。「行ったことがある」はhave been to または have gone🎣'},
    {cat:'不規則動詞',q:'「eat（食べる）」の過去分詞は？',hint:'ヒント：eatの変化はちょっと特別！',choices:['ate','eated','eaten','eat'],ans:2,explain:'eatはeat→ate→eaten。過去分詞はeaten！「食べられた」でイメージしよう🍱'},
    {cat:'不規則動詞',q:'「take（取る・撮る）」の過去分詞は？',hint:'ヒント：釣りで写真をtaken！',choices:['took','taked','taken','take'],ans:2,explain:'takeはtake→took→taken。釣った魚の写真をtaken（撮られた）🎣📸'},
   ]
  },
  // DAY 2
  {week:1,theme:'不規則動詞②',icon:'🎣',desc:'不規則動詞の続き！釣りやラグビーで使う動詞を中心に覚えよう。',
   quiz:[
    {cat:'ウォームアップ',q:'「know（知る）」の過去分詞は？',hint:'ヒント：ずっと知っていた→have known',choices:['knew','knowed','known','know'],ans:2,explain:'knowはknow→knew→known。「知っていた」はhave known😊'},
    {cat:'ウォームアップ',q:'「speak（話す）」の過去分詞は？',hint:'ヒント：英語をspoken！',choices:['spoke','speaked','spoken','speak'],ans:2,explain:'speakはspeak→spoke→spoken。「話された」はspoken✨'},
    {cat:'ウォームアップ',q:'「run（走る）」の過去分詞は？',hint:'ヒント：ラグビーで全力でrun！',choices:['ran','runned','run','runs'],ans:2,explain:'runはrun→ran→run。過去分詞は原形と同じrun！ラグビーで全力run🏉'},
   ],
   test:[
    {cat:'不規則動詞',q:'「swim（泳ぐ）」の過去分詞は？',hint:'ヒント：川で泳いだことがある→have（　）',choices:['swam','swimmed','swum','swim'],ans:2,explain:'swimはswim→swam→swum。川で釣りの前に泳いだ経験もhave swum🎣'},
    {cat:'不規則動詞',q:'「win（勝つ）」の過去分詞は？',hint:'ヒント：ラグビーの試合に勝ったことがある',choices:['won','winned','wun','win'],ans:0,explain:'winはwin→won→won。試合に勝ったことがある→have won🏉🏆'},
    {cat:'不規則動詞',q:'「read（読む）」の過去分詞は？（発音注意！）',hint:'ヒント：スペルは原形と同じだけど発音が変わる',choices:['readed','red','read','reed'],ans:2,explain:'readはread→read→read。スペルは全部同じ！でも過去形・過去分詞の発音は「レッド」📚'},
    {cat:'不規則動詞',q:'「give（あげる）」の過去分詞は？',hint:'ヒント：プレゼントをgiven！',choices:['gave','gived','given','give'],ans:2,explain:'giveはgive→gave→given。もらったプレゼント→have been given🎁'},
    {cat:'不規則動詞',q:'「find（見つける）」の過去分詞は？',hint:'ヒント：釣りスポットをfound！',choices:['finded','found','foud','find'],ans:1,explain:'findはfind→found→found。秘密の釣りスポットをhave found（見つけたことがある）🎣'},
   ]
  },
  // DAY 3
  {week:1,theme:'現在完了・肯定文①',icon:'🏉',desc:'現在完了形の基本！「have/has + 過去分詞」でどんな意味になるか覚えよう。',
   quiz:[
    {cat:'ウォームアップ',q:'現在完了形の作り方は？',hint:'ヒント：have/has + ？',choices:['have + 動詞の原形','have + 過去形','have + 過去分詞','have + ing形'],ans:2,explain:'現在完了形はhave/has＋過去分詞！これが超基本。絶対覚えよう✨'},
    {cat:'ウォームアップ',q:'「私はラグビーをしたことがある」は？',hint:'ヒント：経験を表す現在完了',choices:['I play rugby.','I played rugby.','I have played rugby.','I had played rugby.'],ans:2,explain:'経験を言うときはhave＋過去分詞！I have played rugby.🏉'},
    {cat:'ウォームアップ',q:'主語がhe/she/itのとき、haveはどうなる？',hint:'ヒント：3人称単数！',choices:['have','has','had','is'],ans:1,explain:'主語がhe/she/it（3人称単数）のときはhasを使う！I/you/we/theyはhave。'},
   ],
   test:[
    {cat:'現在完了・肯定文',q:'「彼はもうその本を買った」は？',hint:'ヒント：already（もう）はhaveと過去分詞の間に入る',choices:['He already bought the book.','He has already bought the book.','He have already bought the book.','He had already bought the book.'],ans:1,explain:'主語heなのでhas！already（もう）はhas/haveと過去分詞の間に入るよ✨'},
    {cat:'現在完了・肯定文',q:'「私はちょうど宿題を終えた」は？',hint:'ヒント：just（ちょうど）を使う',choices:['I finish my homework just.','I have just finished my homework.','I just finish my homework.','I had just finished my homework.'],ans:1,explain:'I have just finished my homework. justもalreadyと同じ位置（haveと過去分詞の間）に入るよ📚'},
    {cat:'現在完了・肯定文',q:'「トモコはもうその本を買った」の正しい英語は？',hint:'ヒント：テストに出た問題！',choices:['Tomoko already bought the book.','Tomoko has bought already the book.','Tomoko has already bought the book.','Tomoko have already bought the book.'],ans:2,explain:'Tomoko has already bought the book. テストの大問9(1)に出てたよ！しっかり覚えよう🏆'},
    {cat:'現在完了・肯定文',q:'「私たちはその映画を見たことがある」は？',hint:'ヒント：seeの過去分詞はseen',choices:['We see the movie.','We saw the movie.','We have seen the movie.','We has seen the movie.'],ans:2,explain:'We have seen the movie. 主語がweなのでhave！seeの過去分詞はseenだよ👁'},
    {cat:'現在完了・肯定文',q:'「彼女は3回日本に来たことがある」は？',hint:'ヒント：comeの過去分詞はcome（同じ！）',choices:['She has come to Japan three times.','She have come to Japan three times.','She has came to Japan three times.','She comes to Japan three times.'],ans:0,explain:'comeはcome→came→come（過去分詞は原形と同じ！）。主語がsheなのでhas🌸'},
   ]
  },
  // DAY 4
  {week:1,theme:'現在完了・否定文',icon:'🎣',desc:'現在完了の否定文をマスター！「haven\'t/hasn\'t + 過去分詞」で「〜していない」を表そう。',
   quiz:[
    {cat:'ウォームアップ',q:'現在完了の否定文はどう作る？',hint:'ヒント：haveの後にnotを入れる！',choices:['have not + 原形','have not + 過去分詞','not have + 過去分詞','have + not過去分詞'],ans:1,explain:'現在完了の否定はhave not（haven\'t）＋過去分詞！短縮形はhaven\'t/hasn\'t😊'},
    {cat:'ウォームアップ',q:'「私はまだ宿題をしていない」は？',hint:'ヒント：yet（まだ）は文末に来る',choices:['I haven\'t done my homework yet.','I haven\'t do my homework yet.','I haven\'t did my homework yet.','I don\'t have done my homework.'],ans:0,explain:'I haven\'t done my homework yet. doの過去分詞はdone！yetは文末に来るよ📚'},
    {cat:'ウォームアップ',q:'「彼はまだ釣りに行っていない」は？',hint:'ヒント：主語がheなのでhasn\'t',choices:['He hasn\'t go fishing yet.','He haven\'t gone fishing yet.','He hasn\'t gone fishing yet.','He didn\'t go fishing yet.'],ans:2,explain:'He hasn\'t gone fishing yet. 主語heなのでhasn\'t！goの過去分詞はgone🎣'},
   ],
   test:[
    {cat:'現在完了・否定文',q:'「私は長い間彼女に会っていない」の正しい英語は？',hint:'ヒント：meetの過去分詞はmet！（meetではない）',choices:['I haven\'t meet her for a long time.','I haven\'t met her for a long time.','I didn\'t met her for a long time.','I don\'t met her for a long time.'],ans:1,explain:'I haven\'t met her for a long time. meetの過去分詞はmet！テストで間違えてたよ、覚えよう💪'},
    {cat:'現在完了・否定文',q:'「彼女はまだその映画を見ていない」は？',hint:'ヒント：seeの過去分詞はseen',choices:['She hasn\'t seen the movie yet.','She haven\'t seen the movie yet.','She hasn\'t see the movie yet.','She didn\'t see the movie yet.'],ans:0,explain:'She hasn\'t seen the movie yet. 主語sheなのでhasn\'t！seeの過去分詞はseen👁'},
    {cat:'現在完了・否定文',q:'「私たちはまだ昼ごはんを食べていない」は？',hint:'ヒント：eatの過去分詞はeaten',choices:['We haven\'t eat lunch yet.','We haven\'t ate lunch yet.','We haven\'t eaten lunch yet.','We didn\'t eat lunch yet.'],ans:2,explain:'We haven\'t eaten lunch yet. eatの過去分詞はeaten！主語weなのでhaven\'t🍱'},
    {cat:'現在完了・否定文',q:'「彼はまだ宿題を終えていない」の（　）は？ He ( ) finished his homework yet.',hint:'ヒント：主語がheだから？',choices:['haven\'t','hasn\'t','didn\'t','don\'t'],ans:1,explain:'主語がheなのでhasn\'t！He hasn\'t finished his homework yet.✨'},
    {cat:'現在完了・否定文',q:'「私は一度も北海道に行ったことがない」は？',hint:'ヒント：never（一度も〜ない）を使う',choices:['I have not go to Hokkaido.','I have never been to Hokkaido.','I never go to Hokkaido.','I haven\'t went to Hokkaido.'],ans:1,explain:'I have never been to Hokkaido. neverは「一度も〜ない」という強い否定！been toで「行ったことがある」🗺'},
   ]
  },
  // DAY 5
  {week:1,theme:'現在完了・疑問文①',icon:'🏉',desc:'現在完了の疑問文！Have/Has を主語の前に出すだけ。答え方もセットで覚えよう！',
   quiz:[
    {cat:'ウォームアップ',q:'現在完了の疑問文はどう作る？',hint:'ヒント：Have/HasをSの前に！',choices:['Do have + S + 過去分詞?','Have/Has + S + 過去分詞?','Have/Has + S + 原形?','Did + S + 過去分詞?'],ans:1,explain:'Have/Has＋主語＋過去分詞？これが現在完了の疑問文！Have you ever〜?がよく出るよ😊'},
    {cat:'ウォームアップ',q:'「あなたはラグビーをしたことがありますか？」は？',hint:'ヒント：主語youなのでHave',choices:['Do you play rugby?','Did you play rugby?','Have you played rugby?','Are you play rugby?'],ans:2,explain:'Have you played rugby? 主語youなのでHave！答えはYes, I have. / No, I haven\'t.🏉'},
    {cat:'ウォームアップ',q:'「Have you ever〜?」への答え方は？',hint:'ヒント：現在完了で答える！',choices:['Yes, I do.','Yes, I did.','Yes, I have.','Yes, I had.'],ans:2,explain:'Yes, I have. / No, I haven\'t. で答える！didやdoは使わないよ✨'},
   ],
   test:[
    {cat:'現在完了・疑問文',q:'「あなたはもう宿題を終えましたか？」は？',hint:'ヒント：yet（もう）は疑問文でも使う、文末に来る',choices:['Do you finish your homework yet?','Have you finished your homework yet?','Did you finish your homework yet?','Are you finished your homework yet?'],ans:1,explain:'Have you finished your homework yet? yetは疑問文で「もう」文末に来る！答えはYes, I have.など📚'},
    {cat:'現在完了・疑問文',q:'「彼女はその映画をもう見ましたか？」は？',hint:'ヒント：主語sheなのでHas',choices:['Have she seen the movie yet?','Has she seen the movie yet?','Did she see the movie yet?','Does she see the movie yet?'],ans:1,explain:'主語sheなのでHas！Has she seen the movie yet? seeの過去分詞はseen👁'},
    {cat:'現在完了・疑問文',q:'「あなたは富士山に登ったことがありますか？」は？',hint:'ヒント：everをつけると「今までに〜したことがある？」',choices:['Do you ever climb Mt. Fuji?','Did you climb Mt. Fuji?','Have you ever climbed Mt. Fuji?','Are you ever climbed Mt. Fuji?'],ans:2,explain:'Have you ever climbed Mt. Fuji? everは「今までに」という意味。現在完了の経験用法でよく使うよ🗻'},
    {cat:'現在完了・疑問文',q:'「はい、あります」と答えるのは？',hint:'ヒント：haveで答える！',choices:['Yes, I do.','Yes, I did.','Yes, I have.','Yes, I am.'],ans:2,explain:'現在完了の疑問文への答えはYes, I have. / No, I haven\'t.！doやdidは使わないよ✨'},
    {cat:'現在完了・疑問文',q:'「あなたは今日、魚を釣ったことがありますか？」への答えで正しいのは？',hint:'ヒント：No〜の答え方',choices:['No, I didn\'t.','No, I haven\'t.','No, I don\'t.','No, I hadn\'t.'],ans:1,explain:'No, I haven\'t. が正解！現在完了の否定の答えはhaven\'t/hasn\'t🎣'},
   ]
  },
  // DAY 6
  {week:1,theme:'現在完了・疑問文②',icon:'🎣',desc:'疑問文の応用！How long / How many times を使った質問を覚えよう。',
   quiz:[
    {cat:'ウォームアップ',q:'「どのくらいの間〜？」と期間を聞くときは？',hint:'ヒント：How ＿ have you〜?',choices:['How many','How long','How much','How often'],ans:1,explain:'How long have you〜? で期間を聞く！テストの大問10で出てたパターンだよ😊'},
    {cat:'ウォームアップ',q:'「何回〜したことがありますか？」と回数を聞くときは？',hint:'ヒント：How many ＿？',choices:['How many time','How many times','How much times','How long time'],ans:1,explain:'How many times have you〜? で回数を聞く！timesのsを忘れずに✨'},
    {cat:'ウォームアップ',q:'「あなたはどのくらいの間ラグビーをしていますか？」は？',hint:'ヒント：How long have you〜?',choices:['How long do you play rugby?','How long have you played rugby?','How long did you play rugby?','How long are you playing rugby?'],ans:1,explain:'How long have you played rugby? 現在完了で期間を聞くときのパターン🏉'},
   ],
   test:[
    {cat:'How long',q:'「あなたはどのくらいの間奈良に住んでいますか？」は？',hint:'ヒント：liveの過去分詞はlived',choices:['How long do you live in Nara?','How long have you lived in Nara?','How long did you live in Nara?','How long are you living in Nara?'],ans:1,explain:'How long have you lived in Nara? 現在完了で継続期間を聞くよ🦌'},
    {cat:'How many times',q:'「彼は何回その川に釣りに行ったことがありますか？」は？',hint:'ヒント：goの過去分詞はgone、主語heなのでhas',choices:['How many times has he go fishing?','How many time has he gone fishing?','How many times has he gone fishing?','How many times have he gone fishing?'],ans:2,explain:'How many times has he gone fishing? 主語heなのでhas！timesのsも忘れずに🎣'},
    {cat:'How long',q:'「彼女はどのくらいの間英語を勉強していますか？」の（　）は？ How long ( ) she studied English?',hint:'ヒント：主語sheなのでhas/have？',choices:['do','did','have','has'],ans:3,explain:'主語sheなのでhas！How long has she studied English?✨'},
    {cat:'How many times',q:'「あなたは何回ラグビーの試合を見たことがありますか？」は？',hint:'ヒント：seeの過去分詞はseen',choices:['How many times have you seen a rugby game?','How many time have you see a rugby game?','How many times did you see a rugby game?','How many times have you saw a rugby game?'],ans:0,explain:'How many times have you seen a rugby game? seeの過去分詞はseen🏉📺'},
    {cat:'How long / How many times',q:'「あなたはどのくらいの間この竿を使っていますか？」は？',hint:'ヒント：useの過去分詞はused',choices:['How many times have you used this rod?','How long have you used this rod?','How long did you use this rod?','How long do you use this rod?'],ans:1,explain:'期間を聞くのはHow long！回数を聞くのはHow many times！この違いを覚えよう🎣'},
   ]
  },
  // DAY 7
  {week:1,theme:'Week1 総復習',icon:'🏆',desc:'Week1の総まとめ！不規則動詞・基本文・否定文・疑問文を全部確認しよう。',
   quiz:[
    {cat:'復習',q:'「have + 過去分詞」を使うのは？',hint:'ヒント：どんな時制？',choices:['過去形','現在完了形','未来形','現在進行形'],ans:1,explain:'have/has＋過去分詞が現在完了形！Week1で一番大事な基本だよ✨'},
    {cat:'復習',q:'現在完了の否定はどう作る？',hint:'ヒント：haven\'t/hasn\'t＋？',choices:['haven\'t＋原形','haven\'t＋過去形','haven\'t＋過去分詞','not＋have＋過去分詞'],ans:2,explain:'haven\'t/hasn\'t＋過去分詞！これが否定形の基本😊'},
    {cat:'復習',q:'「Have you ever visited Nara?」への答えは？',hint:'ヒント：haveで答える！',choices:['Yes, I visit.','Yes, I visited.','Yes, I have.','Yes, I do.'],ans:2,explain:'Yes, I have. / No, I haven\'t. 現在完了の疑問文にはhaveで答えるよ🦌'},
   ],
   test:[
    {cat:'総復習',q:'「私は3回奈良に行ったことがある」は？',hint:'ヒント：goの過去分詞はbeen to（経験）',choices:['I go to Nara three times.','I went to Nara three times.','I have been to Nara three times.','I have gone to Nara three times.'],ans:2,explain:'I have been to Nara three times. 経験用法のbeen to！gone toは「行ったきり帰ってこない」ニュアンスだよ🦌'},
    {cat:'総復習',q:'「彼女はまだ昼ごはんを食べていない」は？',hint:'ヒント：eatの過去分詞はeaten、yetは文末',choices:['She hasn\'t eat lunch yet.','She haven\'t eaten lunch yet.','She hasn\'t eaten lunch yet.','She didn\'t eat lunch yet.'],ans:2,explain:'She hasn\'t eaten lunch yet. 主語sheなのでhasn\'t！eatの過去分詞はeaten🍱'},
    {cat:'総復習',q:'「あなたはどのくらいの間ラグビーをしていますか？」は？',hint:'ヒント：How long have you〜?',choices:['How long do you play rugby?','How long have you played rugby?','How long did you play rugby?','How long are you playing rugby?'],ans:1,explain:'How long have you played rugby? 期間を聞くときはHow long have/has!🏉'},
    {cat:'総復習',q:'「私はちょうど釣りから帰ってきた」は？',hint:'ヒント：just（ちょうど）＋来る＝come',choices:['I just come back from fishing.','I have just come back from fishing.','I just came back from fishing.','I had just come back from fishing.'],ans:1,explain:'I have just come back from fishing. justは完了用法でよく使う！comeの過去分詞はcome🎣'},
    {cat:'総復習',q:'「あなたは今までに外国に行ったことがありますか？」は？',hint:'ヒント：ever（今までに）を使う',choices:['Do you ever go abroad?','Have you ever been abroad?','Did you ever go abroad?','Are you ever gone abroad?'],ans:1,explain:'Have you ever been abroad? abroadは「外国に」という副詞。been abroadで「外国に行ったことがある」✈'},
   ]
  },
  // DAY 8
  {week:2,theme:'継続用法・for',icon:'🏉',desc:'「ずっと〜している」という継続の意味！for＋期間の使い方をマスターしよう。',
   quiz:[
    {cat:'ウォームアップ',q:'「ずっと〜している（継続）」の現在完了の特徴は？',hint:'ヒント：for や since がよく使われる',choices:['alreadyやjustを使う','forやsinceを使う','everやneverを使う','yetを使う'],ans:1,explain:'継続用法ではfor（〜間）やsince（〜から）をよく使う！これが継続用法の目印😊'},
    {cat:'ウォームアップ',q:'「私は3年間ずっとラグビーをしている」は？',hint:'ヒント：have played + for + 期間',choices:['I play rugby for three years.','I played rugby for three years.','I have played rugby for three years.','I am playing rugby for three years.'],ans:2,explain:'I have played rugby for three years. have＋過去分詞＋for＋期間！これが継続用法🏉'},
    {cat:'ウォームアップ',q:'forの後に来るのは？',hint:'ヒント：期間or時点どっち？',choices:['時点（2020年、月曜日など）','期間（3年間、2時間など）','場所','人'],ans:1,explain:'for＋期間（three years, two hours など）！sinceは時点（2020, Monday など）😊'},
   ],
   test:[
    {cat:'継続用法・for',q:'「彼は10年間ずっと魚釣りが好きだ」は？',hint:'ヒント：likeの過去分詞はliked',choices:['He likes fishing for ten years.','He liked fishing for ten years.','He has liked fishing for ten years.','He have liked fishing for ten years.'],ans:2,explain:'He has liked fishing for ten years. 主語heなのでhas！likeの過去分詞はliked🎣'},
    {cat:'継続用法・for',q:'「私たちは2時間ずっと勉強している」は？',hint:'ヒント：studyの過去分詞はstudied',choices:['We study for two hours.','We studied for two hours.','We have studied for two hours.','We has studied for two hours.'],ans:2,explain:'We have studied for two hours. 主語weなのでhave！📚'},
    {cat:'継続用法・for',q:'「彼女は5年間奈良に住んでいる」の（　）は？ She ( ) lived in Nara for five years.',hint:'ヒント：主語sheなのでhas/have？',choices:['is','was','have','has'],ans:3,explain:'主語sheなのでhas！She has lived in Nara for five years.🦌'},
    {cat:'継続用法・for',q:'「私はずっと彼を知っている」は（　）を入れると？ I have known him ( ) a long time.',hint:'ヒント：期間の前はfor！',choices:['since','for','during','from'],ans:1,explain:'I have known him for a long time. 期間の前はfor！sinceは時点の前に使うよ😊'},
    {cat:'継続用法・for',q:'「あなたはどのくらいの間ラグビーをしていますか？」の答えとして正しいのは？',hint:'ヒント：for＋期間で答える',choices:['I play rugby since I was ten.','I have played rugby for five years.','I played rugby for five years.','I am playing rugby for five years.'],ans:1,explain:'I have played rugby for five years. How long have you〜?にはfor＋期間で答えよう🏉'},
   ]
  },
  // DAY 9
  {week:2,theme:'継続用法・since',icon:'🎣',desc:'sinceは「〜のときから（ずっと）」！forとの違いをしっかり覚えよう。',
   quiz:[
    {cat:'ウォームアップ',q:'sinceの後に来るのは？',hint:'ヒント：forとsince、期間と時点どっちがどっち？',choices:['期間（3年間など）','時点（2020年、子供のころなど）','場所','人'],ans:1,explain:'since＋時点（2020, last year, I was ten など）！for＋期間と混同しないよう注意😊'},
    {cat:'ウォームアップ',q:'「彼は10歳のときからずっと釣りが好きだ」の（　）は？ He has liked fishing ( ) he was ten.',hint:'ヒント：「〜のとき」→ since or for？',choices:['for','during','since','from'],ans:2,explain:'since＋時点！「10歳のとき」は時点だからsince！He has liked fishing since he was ten.🎣'},
    {cat:'ウォームアップ',q:'「for 3 years」と「since 2020」の違いは？',hint:'ヒント：どちらが期間でどちらが時点？',choices:['同じ意味','forが時点、sinceが期間','forが期間、sinceが時点','どちらも使い方は同じ'],ans:2,explain:'for＋期間（3 years）、since＋時点（2020）！これを間違えるとテストで減点になるよ✨'},
   ],
   test:[
    {cat:'継続用法・since',q:'「私は2020年からずっとラグビーをしている」は？',hint:'ヒント：since＋年（時点）',choices:['I play rugby since 2020.','I played rugby since 2020.','I have played rugby since 2020.','I am playing rugby since 2020.'],ans:2,explain:'I have played rugby since 2020. since＋時点！継続用法の基本🏉'},
    {cat:'継続用法・since',q:'「彼女は子どものころからずっと英語を勉強している」は？',hint:'ヒント：since she was a child',choices:['She studies English since she was a child.','She has studied English since she was a child.','She studied English since she was a child.','She have studied English since she was a child.'],ans:1,explain:'She has studied English since she was a child. 主語sheなのでhas！since she was a child（子どもの頃から）📚'},
    {cat:'for or since',q:'「私は（　）3年間英語を勉強している」の（　）に入れるのは？',hint:'ヒント：期間→for、時点→since',choices:['since','for','from','during'],ans:1,explain:'3年間は「期間」なのでfor！I have studied English for three years.😊'},
    {cat:'for or since',q:'「彼は（　）昨年からずっとここに住んでいる」の（　）は？',hint:'ヒント：昨年→時点→for or since？',choices:['for','during','since','from'],ans:2,explain:'昨年は「時点」なのでsince！He has lived here since last year.🏠'},
    {cat:'継続用法まとめ',q:'「あなたはいつからラグビーをしていますか？」は？',hint:'ヒント：Since when have you〜?',choices:['From when have you played rugby?','Since when have you played rugby?','How long did you play rugby?','When have you played rugby?'],ans:1,explain:'Since when have you played rugby? 「いつから」はSince when！How long（どのくらいの間）との違いも覚えよう🏉'},
   ]
  },
  // DAY 10
  {week:2,theme:'経験用法・ever/never',icon:'🏉',desc:'経験用法のポイント！everとneverを使いこなそう。',
   quiz:[
    {cat:'ウォームアップ',q:'「今までに〜したことがある？」とたずねるときは？',hint:'ヒント：everを使う！',choices:['Have you never〜?','Have you ever〜?','Have you already〜?','Have you just〜?'],ans:1,explain:'Have you ever〜? が経験を聞く疑問文！everは「今までに」という意味😊'},
    {cat:'ウォームアップ',q:'「一度も〜したことがない」を表すのは？',hint:'ヒント：neverは強い否定！',choices:['I have not〜','I have never〜','I haven\'t ever〜','I have no〜'],ans:1,explain:'I have never〜! neverは「一度も〜ない」という強い否定。haven\'tよりも強調される✨'},
    {cat:'ウォームアップ',q:'「私は一度もその川で釣りをしたことがない」の（　）は？ I have ( ) fished in that river.',hint:'ヒント：「一度も〜ない」',choices:['not','never','no','ever'],ans:1,explain:'I have never fished in that river. neverは「一度も〜ない」！釣りの文で覚えよう🎣'},
   ],
   test:[
    {cat:'経験用法',q:'「あなたは今までにラグビーをしたことがありますか？」は？',hint:'ヒント：Have you ever〜?',choices:['Do you ever play rugby?','Have you ever played rugby?','Did you ever play rugby?','Have you play rugby ever?'],ans:1,explain:'Have you ever played rugby? everは「今までに」疑問文で使う！答えはYes, I have.など🏉'},
    {cat:'経験用法・never',q:'「私は一度も外国に行ったことがない」は？',hint:'ヒント：have never been to〜',choices:['I have never gone to a foreign country.','I have never been to a foreign country.','I never go to a foreign country.','I didn\'t never go to a foreign country.'],ans:1,explain:'I have never been to a foreign country. 「〜に行ったことがない」はhave never been to！✈'},
    {cat:'経験用法',q:'「Yes, I have. I have been to Tokyo.」この会話の前の質問は？',hint:'ヒント：Tokyoに行ったことがある？',choices:['Have you ever been to Tokyo?','Did you go to Tokyo?','Do you live in Tokyo?','Have you ever gone to Tokyo?'],ans:0,explain:'Have you ever been to Tokyo? 経験用法の疑問文はHave you ever been to〜?が基本✨'},
    {cat:'経験用法まとめ',q:'「彼は今までに大きな魚を釣ったことがありますか？」は？',hint:'ヒント：主語heなのでHas、catchの過去分詞はcaught',choices:['Have he ever caught a big fish?','Has he ever caught a big fish?','Has he ever catch a big fish?','Did he ever catch a big fish?'],ans:1,explain:'Has he ever caught a big fish? 主語heなのでHas！catchの過去分詞はcaught🎣🐟'},
    {cat:'経験用法まとめ',q:'「私は一度もカレーを食べたことがない」は？',hint:'ヒント：eatの過去分詞はeaten',choices:['I have never eat curry.','I have never ate curry.','I have never eaten curry.','I never eaten curry.'],ans:2,explain:'I have never eaten curry. eatの過去分詞はeaten！have never＋過去分詞🍛'},
   ]
  },
  // DAY 11
  {week:2,theme:'完了用法・already/yet/just',icon:'🎣',desc:'「もう〜した」「ちょうど〜した」「まだ〜していない」の表現をマスター！',
   quiz:[
    {cat:'ウォームアップ',q:'「もう〜した」（完了）を表すのは？',hint:'ヒント：3つの中から！',choices:['never','already','yet'],ans:1,explain:'already＝「もう、すでに」。肯定文で使う！I have already eaten.（もう食べた）😊'},
    {cat:'ウォームアップ',q:'「ちょうど〜したところ」を表すのは？',hint:'ヒント：just now の just！',choices:['just','ever','yet'],ans:0,explain:'just＝「ちょうど〜したところ」。I have just arrived.（ちょうど着いたところ）✨'},
    {cat:'ウォームアップ',q:'「まだ〜していない」（否定）で使うのは？',hint:'ヒント：文末に来る！',choices:['already','just','yet'],ans:2,explain:'yet＝否定文で「まだ〜していない」、疑問文で「もう〜した？」。文末に来るよ！'},
   ],
   test:[
    {cat:'完了用法・already',q:'「私はもう宿題を終えた」は？',hint:'ヒント：already の位置はhaveと過去分詞の間',choices:['I finished my homework already.','I have finished already my homework.','I have already finished my homework.','I already have finished my homework.'],ans:2,explain:'I have already finished my homework. alreadyはhaveと過去分詞の間に入るよ！📚'},
    {cat:'完了用法・just',q:'「彼はちょうど釣りから戻ってきた」は？',hint:'ヒント：comeの過去分詞はcome',choices:['He just came back from fishing.','He has just come back from fishing.','He just has come back from fishing.','He have just come back from fishing.'],ans:1,explain:'He has just come back from fishing. 主語heなのでhas！just＋過去分詞で「ちょうど〜した」🎣'},
    {cat:'完了用法・yet',q:'「彼女はまだその本を読んでいない」は？',hint:'ヒント：hasn\'t＋過去分詞＋yet',choices:['She hasn\'t read the book already.','She hasn\'t read the book yet.','She hasn\'t read yet the book.','She haven\'t read the book yet.'],ans:1,explain:'She hasn\'t read the book yet. yetは文末！主語sheなのでhasn\'t。readの過去分詞はread（発音はレッド）📖'},
    {cat:'完了用法・yet',q:'「あなたはもう昼ごはんを食べましたか？」は？',hint:'ヒント：yetは疑問文で「もう」、文末に来る',choices:['Have you eaten lunch already?','Have you eaten lunch yet?','Did you eat lunch yet?','Do you eat lunch yet?'],ans:1,explain:'Have you eaten lunch yet? yetは疑問文で「もう」という意味。文末に来るよ！😊'},
    {cat:'already/just/yet まとめ',q:'「私たちはちょうど試合に勝ったところだ」は？',hint:'ヒント：winの過去分詞はwon',choices:['We just win the game.','We have just won the game.','We just won the game.','We has just won the game.'],ans:1,explain:'We have just won the game. 主語weなのでhave！winの過去分詞はwon🏉🏆'},
   ]
  },
  // DAY 12
  {week:2,theme:'3用法の整理',icon:'🏉',desc:'経験・継続・完了の3用法を整理！それぞれの目印の単語を覚えよう。',
   quiz:[
    {cat:'ウォームアップ',q:'「経験用法」の目印の単語は？',hint:'ヒント：「今までに」「一度も〜ない」',choices:['already, just, yet','for, since','ever, never, once, times'],ans:2,explain:'経験用法の目印はever（今までに）、never（一度も〜ない）、once（一度）、〜times（〜回）！'},
    {cat:'ウォームアップ',q:'「継続用法」の目印の単語は？',hint:'ヒント：「ずっと〜している」',choices:['already, just, yet','for, since','ever, never, times'],ans:1,explain:'継続用法の目印はfor（〜間）とsince（〜から）！「ずっと続いている」イメージ😊'},
    {cat:'ウォームアップ',q:'「完了用法」の目印の単語は？',hint:'ヒント：「もう〜した」「ちょうど〜した」',choices:['already, just, yet','for, since','ever, never'],ans:0,explain:'完了用法の目印はalready（もう）、just（ちょうど）、yet（まだ/もう）！✨'},
   ],
   test:[
    {cat:'3用法の判断',q:'「I have played rugby three times.」は何用法？',hint:'ヒント：three times（3回）が目印',choices:['継続用法','完了用法','経験用法'],ans:2,explain:'three times（3回）は経験用法の目印！「ラグビーを3回したことがある」という経験を表す🏉'},
    {cat:'3用法の判断',q:'「I have just eaten lunch.」は何用法？',hint:'ヒント：just（ちょうど）が目印',choices:['継続用法','完了用法','経験用法'],ans:1,explain:'just（ちょうど）は完了用法の目印！「ちょうど昼ごはんを食べたところ」という完了を表す🍱'},
    {cat:'3用法の判断',q:'「She has lived in Nara for ten years.」は何用法？',hint:'ヒント：for ten years（10年間）が目印',choices:['継続用法','完了用法','経験用法'],ans:0,explain:'for（〜間）は継続用法の目印！「10年間ずっと奈良に住んでいる」という継続を表す🦌'},
    {cat:'3用法・文選択',q:'「彼はすでにその川で釣りをしたことがある」を表すのは？',hint:'ヒント：経験？完了？',choices:['He has already fished in that river.','He has ever fished in that river.','He has never fished in that river.','He fishes in that river already.'],ans:0,explain:'He has already fished in that river. already（すでに）は完了用法！経験はever/neverを使う😊'},
    {cat:'3用法まとめ',q:'「私は3年間ずっとラグビーをしている」に合うのは？',hint:'ヒント：継続用法！for＋期間',choices:['I have played rugby three times.','I have just played rugby.','I have played rugby for three years.','I have never played rugby.'],ans:2,explain:'I have played rugby for three years. for＋期間が継続用法の証！ずっと続いているイメージ🏉'},
   ]
  },
  // DAY 13
  {week:2,theme:'that節・間接疑問文',icon:'🎣',desc:'「〜ということ」を表すthat節！テストによく出る重要文法だよ。',
   quiz:[
    {cat:'ウォームアップ',q:'「彼は私に英語が大切だと言った」のthat節を使った正しい文は？',hint:'ヒント：tell + 人 + that + 文',choices:['He told me English is important.','He told me that English is important.','He said me that English is important.','He told that English is important to me.'],ans:1,explain:'He told me that English is important. tell + 人 + that + 文！thatは省略されることも多い😊'},
    {cat:'ウォームアップ',q:'「ノリコは私たちに数学を勉強することが大切だと言う」は？（テストに出た問題！）',hint:'ヒント：studying（動名詞）が主語になる',choices:['Noriko told we study math is important.','Noriko tells us that studying math is important.','Noriko tell us that study math is important.','Noriko says to us that math study is important.'],ans:1,explain:'Noriko tells us that studying math is important. テストの大問9(3)の模範解答！studyingが主語になるよ✨'},
    {cat:'ウォームアップ',q:'「私の父はよく私にもっと英語を勉強すべきだと言う」は？',hint:'ヒント：テストに出た文！tell me that〜',choices:['My father often tells me that I should study English more.','My father often says me that I should study English more.','My father often told me to I should study English more.','My father often tells to me that I should study English more.'],ans:0,explain:'My father often tells me that I should study English more. テストの大問11に出た文だよ！🏆'},
   ],
   test:[
    {cat:'that節',q:'「私はラグビーが楽しいと思う」は？',hint:'ヒント：think + that + 文',choices:['I think rugby is fun.','I think that rugby is fun.','I think that rugby fun is.','AとBは同じ意味で両方正しい'],ans:3,explain:'I think rugby is fun. も I think that rugby is fun. も両方正しい！thatは省略できるよ😊'},
    {cat:'that節',q:'「彼女はあなたが釣りが好きだと知っている」は？',hint:'ヒント：know + that + 文',choices:['She knows that you like fishing.','She knows you to like fishing.','She knows you like fishing.','AとCは同じ意味で両方正しい'],ans:3,explain:'どちらも正しい！that は省略できる。She knows (that) you like fishing.🎣'},
    {cat:'that節',q:'「コーチは私に全力で走ることが大切だと言った」は？',hint:'ヒント：told me that〜、runningが主語',choices:['The coach told me that running fast is important.','The coach said me that running fast is important.','The coach told to me that running fast is important.','The coach told me to running fast is important.'],ans:0,explain:'tell + 人 + that + 文！sayとtellは使い方が違う。say（言う）にはtoは不要、tell（伝える）には人を続ける✨'},
    {cat:'that節',q:'「私は彼が上手なラグビー選手になれると思う」は？',hint:'ヒント：think + that + he can〜',choices:['I think he can be a good rugby player.','I think to he can be a good rugby player.','I think that he can be good rugby player.','I think him to be a good rugby player.'],ans:0,explain:'I think he can be a good rugby player. think＋that節（thatは省略可）🏉'},
    {cat:'that節まとめ',q:'「先生は私たちに一生懸命勉強することが大切だと言った」は？',hint:'ヒント：told us that〜、studyingが主語',choices:['The teacher told us that studying hard is important.','The teacher said us that studying hard is important.','The teacher told to us that to study hard is important.','The teacher told us that study hard is important.'],ans:0,explain:'The teacher told us that studying hard is important. tell＋人＋that＋文！studyingが主語のthat節📚'},
   ]
  },
  // DAY 14
  {week:2,theme:'Week2 総復習',icon:'🏆',desc:'Week2の総まとめ！継続・経験・完了・that節を全部確認しよう。',
   quiz:[
    {cat:'復習',q:'「for」と「since」の使い方で正しいのは？',hint:'ヒント：期間と時点',choices:['for＋時点、since＋期間','for＋期間、since＋時点','どちらも期間に使う','どちらも時点に使う'],ans:1,explain:'for＋期間（3 years）、since＋時点（2020, last year）！絶対に覚えよう😊'},
    {cat:'復習',q:'「I have never fished in this river.」の意味は？',hint:'ヒント：neverは「一度も〜ない」',choices:['私はこの川で釣りをしていない（完了）','私はこの川で一度も釣りをしたことがない（経験）','私はこの川でまだ釣りをしていない（完了）','私はこの川でずっと釣りをしている（継続）'],ans:1,explain:'neverは経験用法の否定！「一度も〜したことがない」という意味🎣'},
    {cat:'復習',q:'「already, just, yet」はどの用法に多く使われる？',hint:'ヒント：「もう〜した」「ちょうど〜した」',choices:['経験用法','継続用法','完了用法'],ans:2,explain:'already・just・yetは完了用法の目印！「もう・ちょうど・まだ」がキーワード✨'},
   ],
   test:[
    {cat:'総復習',q:'「彼女は子どものころからずっとラグビーが好きだ」は？',hint:'ヒント：since she was a child',choices:['She likes rugby since she was a child.','She has liked rugby since she was a child.','She liked rugby since she was a child.','She have liked rugby since she was a child.'],ans:1,explain:'She has liked rugby since she was a child. since＋時点（she was a child）！主語sheなのでhas🏉'},
    {cat:'総復習',q:'「私はちょうど彼から電話を受けたところだ」は？',hint:'ヒント：just、receiveの過去分詞はreceived',choices:['I just receive a call from him.','I have just received a call from him.','I just received a call from him.','I had just received a call from him.'],ans:1,explain:'I have just received a call from him. just＋過去分詞で「ちょうど〜したところ」！📱'},
    {cat:'総復習',q:'「彼は今までに奈良の大仏を見たことがありますか？」は？',hint:'ヒント：seeの過去分詞はseen',choices:['Has he ever saw the Great Buddha in Nara?','Has he ever see the Great Buddha in Nara?','Has he ever seen the Great Buddha in Nara?','Have he ever seen the Great Buddha in Nara?'],ans:2,explain:'Has he ever seen the Great Buddha in Nara? 主語heなのでHas！seeの過去分詞はseen🦌'},
    {cat:'総復習',q:'「父はよく私に英語をもっと勉強すべきだと言う」は？（テストに出た問題）',hint:'ヒント：tell me that〜',choices:['My father often says me that I should study English more.','My father often tells me that I should study English more.','My father often tells to me that I should study English more.','My father often told me that I should study English more.'],ans:1,explain:'My father often tells me that I should study English more. テストの大問11の問題！tell＋人＋that✨'},
    {cat:'総復習',q:'「私は3年間ずっと英語を勉強している」と「私は今まで英語を勉強したことがある」の違いを表す文はどれ？（継続）',hint:'ヒント：継続はfor＋期間',choices:['I have studied English for three years.','I have studied English three times.','I have just studied English.','I have already studied English.'],ans:0,explain:'I have studied English for three years. for＋期間が継続用法！三年間ずっと続いているイメージ📚'},
   ]
  },
  // DAY 15-21: Week 3
  {week:3,theme:'並び替え問題①',icon:'🏉',desc:'語順を意識した並び替え！現在完了形の語順をしっかり確認しよう。',
   quiz:[
    {cat:'ウォームアップ',q:'現在完了形の基本語順は？',hint:'ヒント：have/has＋？',choices:['主語＋have＋原形＋目的語','主語＋have＋過去分詞＋目的語','主語＋have＋過去形＋目的語','主語＋過去分詞＋have＋目的語'],ans:1,explain:'主語＋have/has＋過去分詞（＋目的語）！これが現在完了の基本語順😊'},
    {cat:'ウォームアップ',q:'alreadyはどこに入る？ I ( ) already ( ) my homework.',hint:'ヒント：haveと過去分詞の間！',choices:['have / done','already have / done','have / did','do / already'],ans:0,explain:'I have already done my homework. already/just はhave/hasと過去分詞の間に入る！✨'},
    {cat:'ウォームアップ',q:'「トモコはもうその本を買った」の正しい語順は？',hint:'ヒント：テストに出た問題！',choices:['Tomoko already has bought the book.','Tomoko has already bought the book.','Tomoko has bought already the book.','Already Tomoko has bought the book.'],ans:1,explain:'Tomoko has already bought the book. has＋already＋bought！テストの大問9(1)と同じ🏆'},
   ],
   test:[
    {cat:'並び替え',q:'[ been / have / I / to / never ] Tokyo. → 正しい順番は？',hint:'ヒント：I＋have＋never＋been＋to',choices:['I never have been to Tokyo.','I have never been to Tokyo.','Never I have been to Tokyo.','I have been never to Tokyo.'],ans:1,explain:'I have never been to Tokyo. have＋never＋過去分詞の順番！neverはhaveと過去分詞の間😊'},
    {cat:'並び替え',q:'[ has / she / since / lived / here ] 2020. → 正しい順番は？',hint:'ヒント：She＋has＋lived＋here＋since',choices:['She lived here has since 2020.','She since has lived here 2020.','She has lived here since 2020.','She has since lived here 2020.'],ans:2,explain:'She has lived here since 2020. has＋過去分詞＋since＋時点！継続用法の語順✨'},
    {cat:'並び替え',q:'[ you / how / have / long / rugby / played ]? → 正しい順番は？',hint:'ヒント：How long＋have you＋過去分詞？',choices:['How long you have played rugby?','How long have you played rugby?','How long have you play rugby?','How you have long played rugby?'],ans:1,explain:'How long have you played rugby? 疑問詞＋have/has＋主語＋過去分詞の語順🏉'},
    {cat:'並び替え',q:'[ has / he / fishing / many / times / how / gone ]? → 正しい順番は？',hint:'ヒント：How many times＋has he＋gone?',choices:['How many times has he gone fishing?','How many times he has gone fishing?','How many times has he go fishing?','How many has he times gone fishing?'],ans:0,explain:'How many times has he gone fishing? goの過去分詞はgone！回数を聞くHow many times🎣'},
    {cat:'並び替え',q:'[ interested / have / in / been / I ] it since then. → 正しい順番は？',hint:'ヒント：テストに出た問題！I＋have＋been＋interested＋in',choices:['I have been interested in it since then.','I been have interested in it since then.','I have interested been in it since then.','I have in been interested it since then.'],ans:0,explain:'I have been interested in it since then. テストの大問11！have＋been＋interested＋in✨'},
   ]
  },
  {week:3,theme:'並び替え問題②',icon:'🎣',desc:'疑問文・否定文の並び替えを練習！語順の感覚を鍛えよう。',
   quiz:[
    {cat:'ウォームアップ',q:'現在完了疑問文の語順は？',hint:'ヒント：Have/Has を主語の前に！',choices:['主語＋Have/Has＋過去分詞？','Have/Has＋主語＋過去分詞？','Do＋主語＋Have＋過去分詞？','Have＋主語＋原形？'],ans:1,explain:'Have/Has＋主語＋過去分詞？疑問文はhave/hasを主語の前に出す！😊'},
    {cat:'ウォームアップ',q:'「彼女はもう昼ごはんを食べましたか？」の並び替え [ eaten / has / she / yet / lunch ]? → 正しいのは？',hint:'ヒント：Has she eaten〜yet?',choices:['Has she eaten lunch yet?','She has eaten lunch yet?','Has she eat lunch yet?','Has she eaten yet lunch?'],ans:0,explain:'Has she eaten lunch yet? Has＋主語＋過去分詞＋目的語＋yet！疑問文の語順✨'},
    {cat:'ウォームアップ',q:'「あなたはどのくらいの間奈良に住んでいますか？」は？',hint:'ヒント：How long have you〜?',choices:['How long you have lived in Nara?','How long have you lived in Nara?','How long do you live in Nara?','How long did you live in Nara?'],ans:1,explain:'How long have you lived in Nara? How long＋have you＋過去分詞？🦌'},
   ],
   test:[
    {cat:'並び替え',q:'[ you / caught / how / fish / many / have / times ]? → 正しいのは？',hint:'ヒント：How many times have you〜?',choices:['How many times you have caught fish?','How many times have you caught fish?','How many have you times caught fish?','How times many have you caught fish?'],ans:1,explain:'How many times have you caught fish? catchの過去分詞はcaught🎣'},
    {cat:'並び替え',q:'[ hasn\'t / he / finished / yet / homework / his ]. → 正しいのは？',hint:'ヒント：He＋hasn\'t＋過去分詞＋yet',choices:['He hasn\'t yet finished his homework.','He hasn\'t finished his homework yet.','He yet hasn\'t finished his homework.','His homework hasn\'t finished yet.'],ans:1,explain:'He hasn\'t finished his homework yet. yetは文末！否定文の語順😊'},
    {cat:'並び替え',q:'[ she / ever / been / has / Osaka / to ]? → 正しいのは？',hint:'ヒント：Has she ever been to〜?',choices:['She has ever been to Osaka?','Has she ever been to Osaka?','Has ever she been to Osaka?','Has she been ever to Osaka?'],ans:1,explain:'Has she ever been to Osaka? 経験用法の疑問文！Has＋主語＋ever＋過去分詞✨'},
    {cat:'並び替え',q:'[ told / Noriko / that / us / studying / is / math / important ]. → 正しいのは？',hint:'ヒント：テストに出た問題！tell＋人＋that＋文',choices:['Noriko told us that studying math is important.','Noriko told us studying math that is important.','Noriko us told that studying math is important.','Noriko told that us studying math is important.'],ans:0,explain:'Noriko told us that studying math is important. テストの大問9(3)と同じ！tell＋人＋that🏆'},
    {cat:'並び替え',q:'[ long / he / how / fished / has / in / river / this ]? → 正しいのは？',hint:'ヒント：How long has he＋過去分詞？',choices:['How long has he fished in this river?','How long he has fished in this river?','How long has he fish in this river?','How long has he been fished in this river?'],ans:0,explain:'How long has he fished in this river? How long＋has＋主語＋過去分詞？🎣'},
   ]
  },
  {week:3,theme:'英作文①',icon:'🏉',desc:'英作文の基本！日本語を見て正しい英文を作ろう。現在完了形が中心だよ。',
   quiz:[
    {cat:'ウォームアップ',q:'「私はラグビーを5年間しています」を英語にすると？',hint:'ヒント：継続用法！have＋played＋for',choices:['I play rugby for five years.','I have played rugby for five years.','I played rugby for five years.','I am playing rugby for five years.'],ans:1,explain:'I have played rugby for five years. 継続用法はhave/has＋過去分詞＋for＋期間🏉'},
    {cat:'ウォームアップ',q:'「私は今まで大きな魚を釣ったことがある」を英語にすると？',hint:'ヒント：経験用法！have＋ever＋caught',choices:['I catch a big fish ever.','I have ever caught a big fish.','I caught a big fish.','I have caught a big fish before.'],ans:3,explain:'I have caught a big fish before. 経験用法はbefore（以前）でも表せる！I have ever caughtは疑問文でないのでNG🎣'},
    {cat:'ウォームアップ',q:'「彼はもう宿題を終えた」を英語にすると？',hint:'ヒント：完了用法！has＋already＋finished',choices:['He finish his homework already.','He has already finished his homework.','He already has finished his homework.','He has finished his homework already.'],ans:1,explain:'He has already finished his homework. alreadyはhas/haveと過去分詞の間！AもDもあり（alreadyの位置は若干柔軟）でもAが一番自然😊'},
   ],
   test:[
    {cat:'英作文',q:'「私は一度もスコットランドに行ったことがない」を英語にすると？',hint:'ヒント：have never been to〜',choices:['I have never gone to Scotland.','I never go to Scotland.','I have never been to Scotland.','I didn\'t never go to Scotland.'],ans:2,explain:'I have never been to Scotland. 「〜に行ったことがない」はhave never been to！been toが経験を表す✈'},
    {cat:'英作文',q:'「彼女は3年間ずっとラグビーの練習をしている」を英語にすると？',hint:'ヒント：practiceの過去分詞はpracticed',choices:['She practices rugby for three years.','She has practiced rugby for three years.','She practiced rugby for three years.','She have practiced rugby for three years.'],ans:1,explain:'She has practiced rugby for three years. 主語sheなのでhas！for＋期間で継続用法🏉'},
    {cat:'英作文',q:'「あなたはこれまでに奈良に来たことがありますか？」を英語にすると？',hint:'ヒント：Have you ever been to〜?',choices:['Did you ever come to Nara?','Have you ever come to Nara?','Have you ever been to Nara?','Do you ever come to Nara?'],ans:2,explain:'Have you ever been to Nara? 場所に行ったことがある？はhave been to！have come toではなくhave been to🦌'},
    {cat:'英作文',q:'「私はちょうど昼ごはんを食べたところです」を英語にすると？',hint:'ヒント：have just eaten〜',choices:['I just eat lunch.','I have just eaten lunch.','I just ate lunch.','I had just eaten lunch.'],ans:1,explain:'I have just eaten lunch. just＋過去分詞で完了用法！eatの過去分詞はeaten🍱'},
    {cat:'英作文',q:'「彼は2015年からずっとこの学校の先生だ」を英語にすると？',hint:'ヒント：has been a teacher since〜',choices:['He is a teacher of this school since 2015.','He has been a teacher of this school since 2015.','He was a teacher of this school since 2015.','He have been a teacher of this school since 2015.'],ans:1,explain:'He has been a teacher of this school since 2015. be動詞の現在完了はhas/have been！主語heなのでhas✨'},
   ]
  },
  {week:3,theme:'英作文②',icon:'🎣',desc:'英作文の応用！テスト形式の英作文問題にチャレンジ。',
   quiz:[
    {cat:'ウォームアップ',q:'be動詞の現在完了「〜でいる・〜にいる」は？',hint:'ヒント：have/has + been',choices:['have/has + be','have/has + been','have/has + was','have/has + is'],ans:1,explain:'be動詞の過去分詞はbeen！I have been in Tokyo for two hours.（2時間東京にいる）😊'},
    {cat:'ウォームアップ',q:'「私は2時間ここにいます」を英語にすると？',hint:'ヒント：have been here for〜',choices:['I am here for two hours.','I was here for two hours.','I have been here for two hours.','I have here for two hours.'],ans:2,explain:'I have been here for two hours. be動詞の現在完了形！been＋場所＋for＋期間✨'},
    {cat:'ウォームアップ',q:'「彼女はずっと釣りに興味がある」を英語にすると？',hint:'ヒント：be interested in〜の現在完了',choices:['She is interested in fishing since long time.','She has been interested in fishing for a long time.','She had been interested in fishing for a long time.','She have been interested in fishing for a long time.'],ans:1,explain:'She has been interested in fishing for a long time. be interested inの現在完了！テスト大問11に出たパターン🎣'},
   ],
   test:[
    {cat:'英作文・be動詞',q:'「私はそれ以来ずっとそれに興味を持っている」を英語にすると？（テストに出た！）',hint:'ヒント：I have been interested in it since then.',choices:['I am interested in it since then.','I have interested in it since then.','I have been interested in it since then.','I been interested in it since then.'],ans:2,explain:'I have been interested in it since then. テストの大問11の問題！have been interested in＋since then🏆'},
    {cat:'英作文',q:'「彼は10年間ずっと奈良に住んでいる」を英語にすると？',hint:'ヒント：has lived in〜for〜',choices:['He lives in Nara for ten years.','He has lived in Nara for ten years.','He lived in Nara for ten years.','He have lived in Nara for ten years.'],ans:1,explain:'He has lived in Nara for ten years. 主語heなのでhas！for＋期間で継続用法🦌'},
    {cat:'英作文',q:'「あなたは今まで何度か釣りに行ったことがありますか？」という質問への答え「はい、3回あります」は？',hint:'ヒント：Yes, I have. I have been fishing〜',choices:['Yes, I do. I go fishing three times.','Yes, I did. I went fishing three times.','Yes, I have. I have been fishing three times.','Yes, I was. I was fishing three times.'],ans:2,explain:'Yes, I have. I have been fishing three times. 現在完了の疑問文にはhaveで答える！経験はhave been 〜ing or have gone🎣'},
    {cat:'英作文',q:'「彼女はもう手紙を書いた」を英語にすると？',hint:'ヒント：has already written〜',choices:['She has already wrote a letter.','She already wrote a letter.','She has already written a letter.','She have already written a letter.'],ans:2,explain:'She has already written a letter. writeの過去分詞はwritten（ダブルn！）。主語sheなのでhas✍'},
    {cat:'英作文',q:'「ラグビーの試合が始まったところだ」を英語にすると？',hint:'ヒント：has just started〜',choices:['The rugby game just starts.','The rugby game has just started.','The rugby game just started.','The rugby game have just started.'],ans:1,explain:'The rugby game has just started. 主語がgame（3人称単数）なのでhas！just＋過去分詞で完了🏉'},
   ]
  },
  {week:3,theme:'読解問題①',icon:'🏉',desc:'長文読解の練習！英文を読んで質問に答える力をつけよう。',
   quiz:[
    {cat:'ウォームアップ',q:'英文読解のポイント！現在完了形が出てきたら何を確認する？',hint:'ヒント：3つの用法のどれか？',choices:['時制だけ確認','経験・継続・完了のどの用法か確認','have/hasだけ確認','過去分詞だけ確認'],ans:1,explain:'経験・継続・完了のどの用法かを確認！目印の単語（ever/never, for/since, already/just/yet）に注目😊'},
    {cat:'ウォームアップ',q:'「Tom has lived in Nara for five years.」の意味は？',hint:'ヒント：for＋期間→継続用法',choices:['トムは5年前に奈良に住んでいた','トムは5年間ずっと奈良に住んでいる','トムは5年後に奈良に住む予定だ','トムは5年間奈良に住んでいた'],ans:1,explain:'継続用法！for five years（5年間）→ずっと今も住んでいる。過去から現在まで続いているよ🦌'},
    {cat:'ウォームアップ',q:'「Have you ever eaten sushi?」への返答として正しいのは？',hint:'ヒント：経験用法の疑問文への答え方',choices:['Yes, I eat.','Yes, I ate.','Yes, I have.','Yes, I had.'],ans:2,explain:'Yes, I have. が正解！現在完了の疑問文にはhaveで答える。No, I haven\'t.でも答えられるよ😊'},
   ],
   test:[
    {cat:'読解',q:'次の英文を読んで質問に答えよう。「Ken has been interested in rugby since he was ten. He has played rugby for eight years and has won many games.」→ ケンはいつからラグビーに興味を持っていますか？',hint:'ヒント：since〜に注目！',choices:['8歳から','10歳から','8年前から','赤ちゃんのころから'],ans:1,explain:'since he was ten（10歳のとき から）！sinceは時点を表すよ🏉'},
    {cat:'読解',q:'上の英文で、ケンは何年間ラグビーをしていますか？',hint:'ヒント：for〜に注目！',choices:['10年間','8年間','5年間','3年間'],ans:1,explain:'for eight years（8年間）！forは期間を表す。継続用法のfor＋期間😊'},
    {cat:'読解',q:'「Mika has never been to a foreign country, but she has studied English for three years.」→ この英文の意味として正しいのは？',hint:'ヒント：neverとfor three yearsに注目',choices:['ミカは外国に住んでいて英語を3年間勉強している','ミカは一度も外国に行ったことがないが3年間英語を勉強している','ミカは3年前に外国から帰ってきた','ミカは外国に行く予定で英語を3年間勉強している'],ans:1,explain:'never（一度も〜ない）＝経験がない、for three years（3年間）＝継続！✨'},
    {cat:'読解',q:'「Ryo has already finished his homework, but Kei hasn\'t finished it yet.」→ 宿題が終わっていないのは誰？',hint:'ヒント：hasn\'t〜yet に注目！',choices:['Ryo（リョウ）','Kei（ケイ）','両方終わっている','両方終わっていない'],ans:1,explain:'hasn\'t finished it yet → まだ終わっていない！alreadyは完了、haven\'t〜yetはまだ未完了😊'},
    {cat:'読解',q:'「I have just come back from fishing. I caught three fish today!」→ この人は今何をしているところ？',hint:'ヒント：have just come back＝ちょうど帰ってきた',choices:['今から釣りに行くところ','今釣りをしているところ','ちょうど釣りから帰ってきたところ','3日前に釣りから帰ってきた'],ans:2,explain:'have just come back = ちょうど帰ってきた！just＋過去分詞で「ちょうど〜したところ」🎣'},
   ]
  },
  {week:3,theme:'読解問題②',icon:'🎣',desc:'もう少し長い英文の読解にチャレンジ！現在完了形を正しく読み取ろう。',
   quiz:[
    {cat:'ウォームアップ',q:'「She has never tried sushi, but she wants to try it.」の意味は？',hint:'ヒント：has never tried＝一度も食べたことがない',choices:['彼女はすしをよく食べる','彼女は一度もすしを食べたことがないが食べたい','彼女はすしが好きではない','彼女はすしを食べたことがあり、また食べたい'],ans:1,explain:'has never tried（一度も試したことがない）＋wants to try（食べてみたい）！✨'},
    {cat:'ウォームアップ',q:'「How long has Taro lived in this town?」の答えとして正しいのは？',hint:'ヒント：How longへの答え方はfor〜',choices:['Since 2010.','For ten years.','Yes, he has.','No, he hasn\'t.'],ans:1,explain:'How long（どのくらいの間）への答えはfor＋期間！For ten years.（10年間）😊'},
    {cat:'ウォームアップ',q:'「He has been to France three times.」の意味は？',hint:'ヒント：been to＋場所＋回数',choices:['彼は3年間フランスに住んでいる','彼はフランスに3回行ったことがある','彼は3日後にフランスに行く','彼はフランスから3日前に帰った'],ans:1,explain:'have been to＋場所＋回数は経験用法！「〜に何回行ったことがある」という意味✈'},
   ],
   test:[
    {cat:'読解・応答',q:'「Have you ever caught a big fish?」に対してYesで答えると？',hint:'ヒント：Yes, I have.＋具体的な内容',choices:['Yes, I did. I caught a big one last year.','Yes, I have. I have caught a big one before.','Yes, I do. I catch big fish sometimes.','Yes, I had. I had caught a big fish.'],ans:1,explain:'Yes, I have. I have caught a big one before. 現在完了の疑問文には現在完了で答えよう🎣'},
    {cat:'読解・応答',q:'「How long have you played rugby?」への答えとして正しいのは？',hint:'ヒント：For〜で答える！',choices:['Since I was ten years old.','For five years.','Yes, I have.','I played rugby last year.'],ans:1,explain:'How long（どのくらいの間）への答えはFor＋期間！For five years.（5年間）🏉'},
    {cat:'読解',q:'次の会話を読んで答えよう。A:「Have you ever been to Kyoto?」B:「Yes, I have. I have been there twice.」→ BはKyotoに何回行ったことがある？',hint:'ヒント：twiceに注目！',choices:['1回','2回','3回','一度も行ったことがない'],ans:1,explain:'twice＝2回！once（1回）、twice（2回）、three times（3回）と覚えよう😊'},
    {cat:'読解',q:'「My father has worked at this company for twenty years. He has never wanted to change his job.」→ 父はこの会社で何年働いている？',hint:'ヒント：for twenty yearsに注目',choices:['2年','12年','20年','200年'],ans:2,explain:'for twenty years＝20年間！twenty（20）はtwenty😊'},
    {cat:'読解・英作文',q:'「あなたは今まで奈良に行ったことがありますか？」と聞かれ「はい、2回あります」と答えるとき？',hint:'ヒント：Yes, I have. I have been to Nara twice.',choices:['Yes, I do. I go to Nara two times.','Yes, I did. I went to Nara twice.','Yes, I have. I have been to Nara twice.','Yes, I was. I was in Nara twice.'],ans:2,explain:'Yes, I have. I have been to Nara twice. 現在完了で答える！twiceは「2回」🦌'},
   ]
  },
  {week:3,theme:'Week3 総復習',icon:'🏆',desc:'Week3の総まとめ！並び替え・英作文・読解を全部確認しよう。',
   quiz:[
    {cat:'復習',q:'alreadyとyetの使い方で正しいのは？',hint:'ヒント：肯定文か否定文か疑問文か',choices:['alreadyは否定文、yetは肯定文','alreadyは肯定文と疑問文、yetは否定文と疑問文','どちらも肯定文に使う','どちらも否定文に使う'],ans:1,explain:'already→肯定文（もう〜した）または疑問文、yet→否定文（まだ〜していない）または疑問文（もう〜した？）！✨'},
    {cat:'復習',q:'「Have you ever been to Tokyo?」の答えで正しいのは？',hint:'ヒント：haveで答える！',choices:['Yes, I go.','Yes, I went.','Yes, I have.','Yes, I am.'],ans:2,explain:'Yes, I have. 現在完了の疑問文には必ずhaveで答える！doやdidは使わないよ😊'},
    {cat:'復習',q:'be動詞の現在完了「ずっと〜である」は？',hint:'ヒント：be動詞の過去分詞はbeen',choices:['have/has + be','have/has + been','have/has + was','have/has + is'],ans:1,explain:'have/has + been! be動詞の過去分詞はbeen。I have been here for two hours.（2時間ここにいる）✨'},
   ],
   test:[
    {cat:'総復習',q:'「私の父はよく私にもっと英語を勉強すべきだと言う」は？（テストに出た！）',hint:'ヒント：tell me that〜',choices:['My father often says me that I should study English more.','My father often tells me that I should study English more.','My father often told me that I should study English more.','My father often tells to me that I should study English more.'],ans:1,explain:'My father often tells me that I should study English more. テスト大問11の問題！tell＋人＋that🏆'},
    {cat:'総復習',q:'「彼はちょうど大きな魚を釣ったところだ」は？',hint:'ヒント：has just caught〜',choices:['He just caught a big fish.','He has just caught a big fish.','He just catches a big fish.','He has just catch a big fish.'],ans:1,explain:'He has just caught a big fish. just＋過去分詞で完了！catchの過去分詞はcaught🎣'},
    {cat:'総復習',q:'「あなたはどのくらいの間ラグビーをしていますか？」に「5年間です」と答えると？',hint:'ヒント：I have played〜for five years.',choices:['I play rugby for five years.','I played rugby for five years.','I have played rugby for five years.','I am playing rugby for five years.'],ans:2,explain:'I have played rugby for five years. How long〜?にはfor＋期間で答える！継続用法🏉'},
    {cat:'総復習',q:'「彼女は2歳のときからずっとここに住んでいる」は？',hint:'ヒント：since she was two',choices:['She lives here since she was two.','She has lived here since she was two.','She lived here since she was two.','She have lived here since she was two.'],ans:1,explain:'She has lived here since she was two. since＋時点（she was two＝2歳のとき）！主語sheなのでhas😊'},
    {cat:'総復習',q:'「I have been interested in it since then.」の意味は？（テストに出た！）',hint:'ヒント：have been interested in＋since then',choices:['私はそれ以来それに興味を持っていない','私はそれ以来ずっとそれに興味を持っている','私はそれに少し興味がある','私はそれ以前はそれに興味を持っていた'],ans:1,explain:'I have been interested in it since then. 「それ以来ずっとそれに興味を持っている」！テスト大問11の問題✨'},
   ]
  },
  // DAY 22-30: Week 4
  {week:4,theme:'総合問題①',icon:'🏉',desc:'Week4は総合問題！今まで学んだことを全部使って解いていこう。',
   quiz:[
    {cat:'ウォームアップ',q:'現在完了形の3用法と目印単語の組み合わせで正しいのは？',hint:'ヒント：全部思い出せるかな？',choices:['経験:for/since、継続:ever/never、完了:already/just/yet','継続:for/since、経験:ever/never、完了:already/just/yet','完了:for/since、経験:already/just、継続:ever/never','経験:already/just、継続:for/since、完了:ever/never'],ans:1,explain:'継続:for/since、経験:ever/never（+times/once）、完了:already/just/yet！これが基本✨'},
    {cat:'ウォームアップ',q:'「I have played rugby.」と「I played rugby.」の違いは？',hint:'ヒント：現在との関係',choices:['同じ意味','現在完了は今も関係がある、過去形は現在と切り離されている','過去形のほうが最近の出来事','現在完了のほうが古い出来事'],ans:1,explain:'現在完了（I have played）は今も関係がある！過去形（I played）は過去に切り離された出来事。微妙な違いだけど大事😊'},
    {cat:'ウォームアップ',q:'「Since when have you been interested in fishing?」の答えとして正しいのは？',hint:'ヒント：since〜で答える！',choices:['For three years.','Since I was five years old.','Yes, I have.','Three years ago.'],ans:1,explain:'Since when（いつから）への答えはSince＋時点！Since I was five years old.（5歳のころから）🎣'},
   ],
   test:[
    {cat:'総合',q:'「私は今まで生きた魚を触ったことがない」は？',hint:'ヒント：have never touched〜',choices:['I have never touched a live fish.','I never touch a live fish.','I have never touch a live fish.','I hadn\'t touch a live fish.'],ans:0,explain:'I have never touched a live fish. touch（触る）の過去分詞はtouched！have never＋過去分詞🐟'},
    {cat:'総合',q:'「彼女はもう3回ラグビーの試合を観に行ったことがある」は？',hint:'ヒント：have been to see〜 または have seen〜',choices:['She has watched rugby games three times.','She watched rugby games three times.','She have watched rugby games three times.','She has watch rugby games three times.'],ans:0,explain:'She has watched rugby games three times. 主語sheなのでhas！watchの過去分詞はwatched🏉'},
    {cat:'総合',q:'「あなたは今まで何回この川で釣りをしたことがありますか？」は？',hint:'ヒント：How many times have you〜?',choices:['How many times have you fished in this river?','How many times did you fish in this river?','How many time have you fished in this river?','How many times have you fish in this river?'],ans:0,explain:'How many times have you fished in this river? timesのs忘れずに！fishの過去分詞はfished🎣'},
    {cat:'総合',q:'「彼らは子どものころからずっとお互いを知っている」は？',hint:'ヒント：have known each other since〜',choices:['They know each other since they were children.','They have known each other since they were children.','They knew each other since they were children.','They have knew each other since they were children.'],ans:1,explain:'They have known each other since they were children. knowの過去分詞はknown！since＋時点😊'},
    {cat:'総合',q:'「その試合はちょうど始まったところだ」は？',hint:'ヒント：has just started',choices:['The game just starts.','The game just started.','The game has just started.','The game have just started.'],ans:2,explain:'The game has just started. gameは3人称単数なのでhas！just＋過去分詞で完了用法🏉'},
   ]
  },
  {week:4,theme:'総合問題②',icon:'🎣',desc:'もう少し難しい総合問題！ここまで来たら実力がついてきた証拠。',
   quiz:[
    {cat:'ウォームアップ',q:'「tell, say, speak, talk」の使い方で正しいのは？',hint:'ヒント：tell＋人、say＋内容',choices:['tell me that〜、say me that〜、どちらも同じ','tell me that〜（伝える）、say that〜（言う）、speak/talk（話す）','say me that〜が正しい','tell that〜が正しい'],ans:1,explain:'tell＋人＋that（伝える）、say＋that（言う、sayの後に人は来ない！）、speak/talk（話す）。テストでsay meはNG✨'},
    {cat:'ウォームアップ',q:'「私はそれ以来それに興味を持っている」の正しい現在完了は？',hint:'ヒント：テストに出た問題！have been interested in',choices:['I am interested in it since then.','I have interested in it since then.','I have been interested in it since then.','I been interested in it since then.'],ans:2,explain:'I have been interested in it since then. be interested inの現在完了はhave been interested in！テスト大問11🏆'},
    {cat:'ウォームアップ',q:'「How long / How many times」どちらを使う？「彼は何回奈良に行ったことがありますか？」',hint:'ヒント：回数か期間か？',choices:['How long has he been to Nara?','How many times has he been to Nara?','How long has he gone to Nara?','How many time has he been to Nara?'],ans:1,explain:'回数を聞くのはHow many times！How many times has he been to Nara?🦌'},
   ],
   test:[
    {cat:'総合・英作文',q:'「あなたのお父さんはどのくらいの間この仕事をしていますか？」は？',hint:'ヒント：How long has your father〜?',choices:['How long does your father work?','How long did your father work?','How long has your father worked?','How long have your father worked?'],ans:2,explain:'How long has your father worked? 主語がyour father（3人称単数）なのでhas！workedは過去分詞😊'},
    {cat:'総合・読解',q:'「Taro has never eaten fish. He doesn\'t like the smell.」→ 太郎について正しいのは？',hint:'ヒント：has never eaten＝一度も食べたことがない',choices:['太郎は魚をよく食べる','太郎は一度も魚を食べたことがない','太郎は魚を食べたことがあるが好きではない','太郎は最近魚を食べていない'],ans:1,explain:'has never eaten fish→一度も魚を食べたことがない！経験用法のnever✨'},
    {cat:'総合・並び替え',q:'[ for / we / years / in / lived / have / ten / Nara ]. → 正しい英文は？',hint:'ヒント：We have lived in Nara for ten years.',choices:['We have lived in Nara for ten years.','We lived for ten years in Nara have.','For ten years we have lived Nara.','We have Nara lived for ten years.'],ans:0,explain:'We have lived in Nara for ten years. have＋過去分詞＋場所＋for＋期間！継続用法🦌'},
    {cat:'総合・英作文',q:'「彼女はちょうど試合に負けたところだ」は？',hint:'ヒント：has just lost〜、loseの過去分詞はlost',choices:['She just loses the game.','She just lost the game.','She has just lost the game.','She have just lost the game.'],ans:2,explain:'She has just lost the game. loseの過去分詞はlost！主語sheなのでhas。just＋過去分詞🏉'},
    {cat:'総合',q:'「父はよく私に早起きすることが大切だと言う」は？',hint:'ヒント：tell me that〜、getting upが主語',choices:['My father often says me that getting up early is important.','My father often tells me that getting up early is important.','My father often tells to me that getting up early is important.','My father often said me that getting up early is important.'],ans:1,explain:'My father often tells me that getting up early is important. tell＋人＋that！say meはNG✨'},
   ]
  },
  {week:4,theme:'テスト直前対策①',icon:'🏉',desc:'テストに出やすい問題を集中練習！間違えやすいポイントを確認しよう。',
   quiz:[
    {cat:'ウォームアップ',q:'テストでよく間違える！meetの過去分詞は？',hint:'ヒント：テストで間違えてたよ！',choices:['meet','meeting','met','meeted'],ans:2,explain:'meetはmeet→met→met！過去形と過去分詞が同じ。テストでmeetと書いてたのが間違い💪'},
    {cat:'ウォームアップ',q:'visitorsのスペルで正しいのは？（テストに出た！）',hint:'ヒント：visit（訪問する）の名詞形',choices:['visiter','visitor','visitors','visiters'],ans:2,explain:'visitorsが正解！visitorのスペルに注意。テストでvisiterと書いてたよ✨'},
    {cat:'ウォームアップ',q:'「have been to」と「have gone to」の違いは？',hint:'ヒント：帰ってきたかどうか',choices:['同じ意味','have been to＝行ったことがある（帰ってきた）、have gone to＝行ったきり（まだいる）','have gone to＝行ったことがある、have been to＝行ったきり','どちらも「行ったことがある」の意味'],ans:1,explain:'have been to（経験、帰ってきた）vs have gone to（行ったきりまだいる）！この違いを覚えよう😊'},
   ],
   test:[
    {cat:'テスト対策',q:'「私はちょうどその本を読み終えた」は？',hint:'ヒント：finishの過去分詞はfinished、readingは動名詞',choices:['I have just finished reading the book.','I have just finish reading the book.','I just finished read the book.','I have just finished read the book.'],ans:0,explain:'I have just finished reading the book. finish＋動名詞（reading）！finishの後はing形が来るよ📚'},
    {cat:'テスト対策',q:'テストで間違えやすい！「彼はまだ来ていない」の正しい英語は？',hint:'ヒント：hasn\'t come yet',choices:['He hasn\'t come already.','He hasn\'t came yet.','He hasn\'t come yet.','He haven\'t come yet.'],ans:2,explain:'He hasn\'t come yet. comeの過去分詞はcome（原形と同じ！）。主語heなのでhasn\'t。yetは文末✨'},
    {cat:'テスト対策',q:'「あなたはいつからラグビーに興味があるの？」は？',hint:'ヒント：Since when〜?',choices:['How long have you been interested in rugby?','Since when have you been interested in rugby?','When have you been interested in rugby?','From when have you interested in rugby?'],ans:1,explain:'Since when have you been interested in rugby? 「いつから」はSince when！How longは「どのくらいの間」🏉'},
    {cat:'テスト対策',q:'「彼女は3年間ずっとラグビーチームのキャプテンだ」は？',hint:'ヒント：be動詞の現在完了＋for',choices:['She is the captain of the rugby team for three years.','She has been the captain of the rugby team for three years.','She was the captain of the rugby team for three years.','She have been the captain of the rugby team for three years.'],ans:1,explain:'She has been the captain of the rugby team for three years. be動詞の現在完了はhas/have been！継続用法🏉'},
    {cat:'テスト対策',q:'「私は今までに外国語を話したことがない」は？',hint:'ヒント：have never spoken〜',choices:['I have never speak a foreign language.','I have never spoken a foreign language.','I never spoke a foreign language.','I have never spoke a foreign language.'],ans:1,explain:'I have never spoken a foreign language. speakの過去分詞はspoken！neverを使った経験用法の否定✨'},
   ]
  },
  {week:4,theme:'テスト直前対策②',icon:'🎣',desc:'最終仕上げ！テスト本番と同じ形式で実力を確認しよう。',
   quiz:[
    {cat:'ウォームアップ',q:'「How many times」と「How long」どちらを使う？「どのくらいの間釣りをしていますか？」',hint:'ヒント：期間か回数か？',choices:['How many times have you been fishing?','How long have you been fishing?','How many time have you fished?','How long did you fish?'],ans:1,explain:'期間を聞くのはHow long！How long have you been fishing? 「どのくらいの間」ずっと釣りをしているか🎣'},
    {cat:'ウォームアップ',q:'「expensiveのスペルで正しいのは？（テストに出た！）',hint:'ヒント：「高価な」という意味',choices:['expencive','expansive','expensive','expensiv'],ans:2,explain:'expensiveが正解！テストでhugeと間違えて書いてたよ。expensive（高価な）✨'},
    {cat:'ウォームアップ',q:'現在完了形でwrittenのスペルは？',hint:'ヒント：writeの過去分詞！ダブルnに注意',choices:['writen','written','writtten','writing'],ans:1,explain:'writtenが正解！ダブルn！テストで間違えてたよ。write→wrote→written✍'},
   ],
   test:[
    {cat:'最終テスト',q:'「私はそれ以来ずっとそれに興味を持っている」は？（テストの大問11！）',hint:'ヒント：I have been interested in it since then.',choices:['I am interested in it since then.','I have interested in it since then.','I have been interested in it since then.','I been interested in it since then.'],ans:2,explain:'I have been interested in it since then. テスト大問11の問題！have been interested in＋since then🏆'},
    {cat:'最終テスト',q:'「私の父はよく私にもっと英語を勉強すべきだと言う」は？（テストの大問11！）',hint:'ヒント：My father often tells me that〜',choices:['My father often says me that I should study English more.','My father often tells me that I should study English more.','My father often told me that I should study English more.','My father often tells to me I should study English more.'],ans:1,explain:'My father often tells me that I should study English more. テスト大問11！tell＋人＋that🏆'},
    {cat:'最終テスト',q:'「トモコはもうその本を買った」は？（テストの大問9！）',hint:'ヒント：has already bought〜',choices:['Tomoko already bought the book.','Tomoko has bought already the book.','Tomoko has already bought the book.','Tomoko have already bought the book.'],ans:2,explain:'Tomoko has already bought the book. テスト大問9(1)の問題！has＋already＋過去分詞🏆'},
    {cat:'最終テスト',q:'「ノリコは私たちに数学を勉強することが大切だと言う」は？（テストの大問9！）',hint:'ヒント：tells us that studying math is important',choices:['Noriko told we study math is important.','Noriko tells us that studying math is important.','Noriko tell us studying math that is important.','Noriko says us that studying math is important.'],ans:1,explain:'Noriko tells us that studying math is important. テスト大問9(3)の問題！tell＋人＋that🏆'},
    {cat:'最終テスト',q:'「私は長い間彼女に会っていない」は？（テストの大問9！）',hint:'ヒント：meetの過去分詞はmet！テストで間違えてた問題！',choices:['I haven\'t meet her for a long time.','I haven\'t met her for a long time.','I didn\'t meet her for a long time.','I haven\'t met her since a long time.'],ans:1,explain:'I haven\'t met her for a long time. meetの過去分詞はmet！テストで間違えてた問題。完璧に覚えよう💪'},
   ]
  },
  {week:4,theme:'テスト直前対策③',icon:'🏉',desc:'テスト3日前！間違えやすいポイントを最終確認。満点を狙おう！',
   quiz:[
    {cat:'ウォームアップ',q:'「I have been to Nara.」と「I went to Nara.」の違いは？',hint:'ヒント：現在との関係！',choices:['同じ意味','前者は経験（行ったことがある）、後者は過去の事実（行った）','前者は過去、後者は現在','前者のほうが最近の出来事'],ans:1,explain:'I have been to Nara（奈良に行ったことがある・経験）vs I went to Nara（奈良に行った・過去の事実）。ニュアンスの違い大切！😊'},
    {cat:'ウォームアップ',q:'「ずっと〜し続けている」という継続の意味を表すのはどれ？',hint:'ヒント：for/sinceがヒント',choices:['I played rugby for three years.','I have played rugby for three years.','I play rugby for three years.','I was playing rugby for three years.'],ans:1,explain:'I have played rugby for three years.（現在完了・継続）だけが「今もずっと続いている」という意味✨'},
    {cat:'ウォームアップ',q:'次の文の（　）に入るのは？「She ( ) never eaten sushi.」',hint:'ヒント：主語sheなのでhas/have？',choices:['have','has','is','was'],ans:1,explain:'主語sheは3人称単数なのでhas！She has never eaten sushi.😊'},
   ],
   test:[
    {cat:'最終確認',q:'「彼は今まで一度もラグビーをしたことがない」は？',hint:'ヒント：has never played〜',choices:['He has never play rugby.','He have never played rugby.','He has never played rugby.','He is never played rugby.'],ans:2,explain:'He has never played rugby. 主語heなのでhas！playの過去分詞はplayed（規則変化）🏉'},
    {cat:'最終確認',q:'「私たちはちょうど練習を終えたところだ」は？',hint:'ヒント：have just finished practice',choices:['We just finish practice.','We have just finished practice.','We just finished practice.','We has just finished practice.'],ans:1,explain:'We have just finished practice. 主語weなのでhave！just＋過去分詞で完了🏉'},
    {cat:'最終確認',q:'「あなたは今まで英語で手紙を書いたことがありますか？」は？',hint:'ヒント：Have you ever written〜?',choices:['Have you ever wrote a letter in English?','Have you ever write a letter in English?','Have you ever written a letter in English?','Did you ever write a letter in English?'],ans:2,explain:'Have you ever written a letter in English? writeの過去分詞はwritten（ダブルn！）✍'},
    {cat:'最終確認',q:'「彼女は子どものころからずっと奈良が好きだ」は？',hint:'ヒント：has liked〜since she was a child',choices:['She likes Nara since she was a child.','She has liked Nara since she was a child.','She liked Nara since she was a child.','She have liked Nara since she was a child.'],ans:1,explain:'She has liked Nara since she was a child. 主語sheなのでhas！since＋時点で継続用法🦌'},
    {cat:'最終確認',q:'「コーチは私たちに諦めないことが大切だと言った」は？',hint:'ヒント：told us that〜、giving up＝諦めること',choices:['The coach told us that not giving up is important.','The coach said us that not giving up is important.','The coach told to us that not giving up is important.','The coach told us that not to give up was important.'],ans:0,explain:'The coach told us that not giving up is important. tell＋人＋that！not giving up（諦めないこと）🏆'},
   ]
  },
  {week:4,theme:'テスト直前対策④',icon:'🎣',desc:'テスト前日！最終チェック。今まで学んだことを総動員しよう！',
   quiz:[
    {cat:'最終チェック',q:'現在完了形の3用法と例文を思い出そう！「I have played rugby three times.」は？',hint:'ヒント：three timesが目印',choices:['継続用法','完了用法','経験用法'],ans:2,explain:'three times（3回）は経験用法の目印！「ラグビーを3回したことがある」という経験🏉'},
    {cat:'最終チェック',q:'「She has just arrived at the station.」は？',hint:'ヒント：justが目印',choices:['継続用法','完了用法','経験用法'],ans:1,explain:'just（ちょうど）は完了用法の目印！「ちょうど駅に着いたところ」という完了✨'},
    {cat:'最終チェック',q:'「He has lived in Nara since 2010.」は？',hint:'ヒント：sinceが目印',choices:['継続用法','完了用法','経験用法'],ans:0,explain:'since（〜から）は継続用法の目印！「2010年からずっと奈良に住んでいる」という継続🦌'},
   ],
   test:[
    {cat:'総まとめ',q:'「私は今まで生のタコを食べたことがある」は？',hint:'ヒント：have ever eaten〜または have eaten〜before',choices:['I have ever eaten raw octopus.','I ever eat raw octopus.','I have eaten raw octopus before.','I ate raw octopus before.'],ans:2,explain:'I have eaten raw octopus before. 経験用法！beforeで経験を表す。I have ever〜は疑問文では使うが肯定文では不自然😊'},
    {cat:'総まとめ',q:'「あなたはどのくらいの間この竿を使っていますか？」と聞くと「5年間使っています」と答えた。正しい会話の組み合わせは？',hint:'ヒント：How long〜?→For five years.',choices:['How long did you use this rod? / I used it for five years.','How long have you used this rod? / I have used it for five years.','How many times have you used this rod? / I have used it for five years.','How long have you used this rod? / I used it for five years.'],ans:1,explain:'How long have you used this rod? / I have used it for five years. 両方とも現在完了！🎣'},
    {cat:'総まとめ',q:'テストに出た問題の総まとめ！「I have been interested in it since then.」を日本語にすると？',hint:'ヒント：have been interested in＋since then',choices:['私はそれ以来それに全く興味がない','私はそれ以来ずっとそれに興味を持っている','私はそれ以前はそれに興味を持っていた','私はそれに少し興味がある'],ans:1,explain:'「私はそれ以来ずっとそれに興味を持っている」！have been interested in（ずっと興味を持っている）＋since then（それ以来）✨'},
    {cat:'総まとめ',q:'「My father often tells me that I should study English more.」を日本語にすると？',hint:'ヒント：tell me that〜、should＝〜すべき',choices:['父はよく私に英語をたくさん勉強したと言う','父はよく私にもっと英語を勉強すべきだと言う','父は私に英語を勉強するように命令した','父はときどき私に英語の勉強を手伝ってくれる'],ans:1,explain:'「父はよく私にもっと英語を勉強すべきだと言う」！often（よく）、tells me that（私に〜だと言う）、should study more（もっと勉強すべき）🏆'},
    {cat:'総まとめ',q:'最後の問題！「あなたはラグビーと釣りのどちらが好きですか？どちらもずっと好きです」を英語にすると？',hint:'ヒント：have liked both〜since〜',choices:['I like both rugby and fishing.','I have liked both rugby and fishing for a long time.','I liked both rugby and fishing for a long time.','I have like both rugby and fishing for a long time.'],ans:1,explain:'I have liked both rugby and fishing for a long time. 継続用法！for a long time（長い間ずっと）。ラグビーも釣りも最高！🏉🎣'},
   ]
  }
];

// ===================== STATE =====================
let currentDay = 0;
let mode = 'quiz'; // 'quiz' or 'test'
let questions = [];
let qIdx = 0;
let answered = false;
let sessionCorrect = 0;
let sessionTotal = 0;
let wrongQs = [];
let quizCorrect = 0;

const STORAGE_KEY = 'eigo30_v1';
let progress = {};

function loadProgress() {
  try {
    const saved = localStorage.getItem(STORAGE_KEY);
    if (saved) progress = JSON.parse(saved);
  } catch(e) { progress = {}; }
}

function saveProgress() {
  try { localStorage.setItem(STORAGE_KEY, JSON.stringify(progress)); } catch(e) {}
}

// ===================== SCREENS =====================
function showScreen(id) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  if (id === 'home') renderHome();
  window.scrollTo(0, 0);
}

// ===================== HOME =====================
function renderHome() {
  loadProgress();
  const done = Object.keys(progress).filter(k => progress[k] && progress[k].done).length;
  const total = Object.keys(progress).reduce((a, k) => a + (progress[k] ? progress[k].correct || 0 : 0), 0);
  const totalQ = Object.keys(progress).reduce((a, k) => a + (progress[k] ? progress[k].total || 0 : 0), 0);
  document.getElementById('h-done').textContent = done;
  document.getElementById('h-correct').textContent = total;
  document.getElementById('h-rate').textContent = totalQ ? Math.round(total / totalQ * 100) + '%' : '—';
  const pct = Math.round(done / 30 * 100);
  document.getElementById('h-pbar').style.width = pct + '%';
  document.getElementById('h-prog-txt').textContent = done + ' / 30日';
  renderCal('cal-w1', 0, 7);
  renderCal('cal-w2', 7, 14);
  renderCal('cal-w3', 14, 21);
  renderCal('cal-w4', 21, 30);
}

function renderCal(elId, from, to) {
  const el = document.getElementById(elId);
  let html = '';
  for (let i = from; i < to; i++) {
    const p = progress[i] || {};
    const done = p.done;
    const cls = done ? 'done' : '';
    const icon = done ? '✓' : '▶';
    html += `<button class="day-btn ${cls}" onclick="selectDay(${i})">
      <div class="day-num">${i + 1}</div>
      <div class="day-icon">${icon}</div>
    </button>`;
  }
  el.innerHTML = html;
}

// ===================== DAY SELECT =====================
function selectDay(idx) {
  currentDay = idx;
  const d = DAYS[idx];
  document.getElementById('intro-title').textContent = 'Day ' + (idx + 1);
  const weeks = ['', 'Week 1 — 不規則動詞・現在完了の基本', 'Week 2 — 否定文・疑問文・3用法', 'Week 3 — 並び替え・英作文・読解', 'Week 4 — 総合・テスト対策'];
  document.getElementById('intro-week').textContent = weeks[d.week];
  document.getElementById('intro-icon').textContent = d.icon;
  document.getElementById('intro-theme').textContent = d.theme;
  document.getElementById('intro-desc').textContent = d.desc;
  showScreen('intro');
}

// ===================== START =====================
function startDay() {
  mode = 'quiz';
  questions = DAYS[currentDay].quiz;
  qIdx = 0;
  answered = false;
  sessionCorrect = 0;
  sessionTotal = 0;
  wrongQs = [];
  quizCorrect = 0;
  showScreen('quiz');
  renderQ();
}

function startTest() {
  mode = 'test';
  questions = DAYS[currentDay].test;
  qIdx = 0;
  answered = false;
  wrongQs = [];
  showScreen('quiz');
  renderQ();
}

// ===================== QUIZ/TEST =====================
function renderQ() {
  const q = questions[qIdx];
  const total = questions.length;
  answered = false;
  const isQuiz = mode === 'quiz';
  const badge = document.getElementById('q-badge');
  badge.textContent = isQuiz ? '🎯 クイズ (ウォームアップ)' : '📝 テスト (本番)';
  badge.className = 'badge ' + (isQuiz ? 'badge-quiz' : 'badge-test');
  document.getElementById('q-counter').textContent = (qIdx + 1) + ' / ' + total;
  document.getElementById('q-pbar').style.width = Math.round((qIdx + 1) / total * 100) + '%';
  document.getElementById('q-cat').textContent = q.cat;
  document.getElementById('q-text').textContent = q.q;
  const hintEl = document.getElementById('q-hint');
  if (q.hint) { hintEl.textContent = q.hint; hintEl.style.display = 'block'; }
  else { hintEl.style.display = 'none'; }
  document.getElementById('q-feedback').style.display = 'none';
  document.getElementById('next-btn').style.display = 'none';
  const choicesEl = document.getElementById('q-choices');
  choicesEl.innerHTML = q.choices.map((c, i) =>
    `<button class="cbtn" onclick="answer(${i})">${c}</button>`
  ).join('');
}

const OK_MSGS = ['完璧！🏉','ナイス！🎣','正解！✨','やるじゃないか！💪','その調子！🎯','完璧な正解！🔥','感覚つかんできたね！🏆'];

function answer(idx) {
  if (answered) return;
  answered = true;
  const q = questions[qIdx];
  const correct = idx === q.ans;
  const btns = document.querySelectorAll('.cbtn');
  btns.forEach(b => b.disabled = true);
  btns[q.ans].classList.add('correct');
  if (!correct) btns[idx].classList.add('wrong');
  sessionTotal++;
  const fb = document.getElementById('q-feedback');
  fb.style.display = 'block';
  if (correct) {
    sessionCorrect++;
    if (mode === 'quiz') quizCorrect++;
    const msg = OK_MSGS[Math.floor(Math.random() * OK_MSGS.length)];
    fb.className = 'feedback fb-ok';
    fb.innerHTML = `<div class="fb-title">${msg}</div><div class="fb-explain">${q.explain}</div>`;
  } else {
    wrongQs.push(q);
    fb.className = 'feedback fb-ng';
    fb.innerHTML = `<div class="fb-title">惜しい！正解は「${q.choices[q.ans]}」だよ</div><div class="fb-explain">${q.explain}</div>`;
  }
  document.getElementById('next-btn').style.display = 'block';
}

function nextQ() {
  qIdx++;
  if (qIdx >= questions.length) {
    if (mode === 'quiz') {
      document.getElementById('pc-score').textContent =
        `クイズ結果：${quizCorrect} / ${questions.length}問正解！\n${quizCorrect === questions.length ? '満点！テストも絶対いけるよ！🏆' : 'テストでしっかり確認しよう！'}`;
      showScreen('phase-change');
    } else {
      showResult();
    }
  } else {
    renderQ();
  }
  window.scrollTo(0, 0);
}

// ===================== RESULT =====================
function showResult() {
  const total = questions.length;
  const correct = sessionCorrect - quizCorrect;
  const testTotal = DAYS[currentDay].test.length;
  const rate = Math.round(correct / testTotal * 100);
  document.getElementById('r-score').textContent = correct;
  document.getElementById('r-den').textContent = '/ ' + testTotal + '問';
  let icon, title, msg;
  if (rate >= 100) { icon = '🏆'; title = '満点！すごい！'; msg = 'テストで満点！この調子でどんどん進もう。ラグビーも勉強も全力で！🏉'; }
  else if (rate >= 80) { icon = '⭐'; title = 'よくできました！'; msg = '評定4に着実に近づいてるよ！間違えた問題をしっかり復習しよう🎣'; }
  else if (rate >= 60) { icon = '💪'; title = 'もう少し！'; msg = '半分以上できた！間違えた問題を復習すれば、すぐ伸びるよ！'; }
  else { icon = '📖'; title = '基礎を確認しよう'; msg = '間違えた問題の解説をよく読んで、もう一度チャレンジしよう！繰り返せば必ず伸びる！'; }
  document.getElementById('r-icon').textContent = icon;
  document.getElementById('r-title').textContent = title;
  document.getElementById('r-msg').textContent = msg;
  // Save progress
  loadProgress();
  if (!progress[currentDay]) progress[currentDay] = { correct: 0, total: 0, done: false };
  progress[currentDay].correct = (progress[currentDay].correct || 0) + correct;
  progress[currentDay].total = (progress[currentDay].total || 0) + testTotal;
  if (rate >= 60) progress[currentDay].done = true;
  saveProgress();
  // Wrong list
  const wrongCard = document.getElementById('r-wrong-card');
  const testWrong = wrongQs.filter(q => DAYS[currentDay].test.includes(q));
  if (testWrong.length > 0) {
    wrongCard.style.display = 'block';
    document.getElementById('r-wrong-list').innerHTML = testWrong.map(q =>
      `<div class="wrong-item">
        <div class="wrong-cat">${q.cat}</div>
        <div class="wrong-q">${q.q.length > 50 ? q.q.substring(0, 50) + '...' : q.q}</div>
        <div class="wrong-ans">→ ${q.choices[q.ans]}</div>
      </div>`
    ).join('');
    document.getElementById('r-retry').style.display = 'block';
  } else {
    wrongCard.style.display = 'none';
    document.getElementById('r-retry').style.display = 'none';
  }
  showScreen('result');
}

function retryWrong() {
  const testWrong = wrongQs.filter(q => DAYS[currentDay].test.includes(q));
  mode = 'retry';
  questions = testWrong;
  qIdx = 0;
  answered = false;
  wrongQs = [];
  showScreen('quiz');
  renderQ();
}

function confirmBack() {
  if (confirm('途中でやめますか？（進捗は保存されません）')) {
    showScreen('home');
  }
}

// ===================== INIT =====================
loadProgress();
renderHome();
</script>
</body>
</html>
