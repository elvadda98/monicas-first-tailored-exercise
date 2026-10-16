<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>English for Financial Meetings — Lesson 1 · Monica</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: "Segoe UI", system-ui, -apple-system, sans-serif;
    background: #f1f5f9;
    color: #0f172a;
    min-height: 100vh;
    line-height: 1.5;
  }
  .wrap { max-width: 940px; margin: 0 auto; padding: 20px 16px 90px; }

  /* ---------- header ---------- */
  header.top { margin-bottom: 6px; }
  .brand { font-size: 1.35rem; font-weight: 800; letter-spacing: .3px; }
  .brand .accent { color: #2563eb; }
  .lesson { color: #64748b; font-size: .92rem; margin-top: 2px; }
  .bar { display: flex; align-items: center; justify-content: space-between; gap: 10px; flex-wrap: wrap; margin-top: 14px; }
  #dots { display: flex; gap: 6px; flex-wrap: wrap; }
  .dot {
    border: 1px solid #cbd5e1; background: #ffffff; color: #475569;
    font-size: .78rem; padding: 5px 11px; border-radius: 999px; cursor: pointer;
    transition: all .15s;
  }
  .dot:hover { border-color: #2563eb; color: #1d4ed8; }
  .dot.active { background: #2563eb; color: #ffffff; font-weight: 700; border-color: #2563eb; }
  .dot.done { border-color: #16a34a; color: #15803d; }
  .dot.done.active { background: #2563eb; color: #ffffff; }
  .score-pill {
    background: #ffffff; border: 1px solid #cbd5e1; border-radius: 999px;
    padding: 5px 14px; font-weight: 700; font-size: .9rem; white-space: nowrap;
  }
  .score-pill span { color: #2563eb; }

  /* ---------- slides ---------- */
  .slide { display: none; animation: fade .35s ease; }
  .slide.active { display: block; }
  @keyframes fade { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: none; } }
  .kicker {
    display: inline-block; font-size: .72rem; font-weight: 800; letter-spacing: 1.5px;
    color: #d97706; text-transform: uppercase; margin-bottom: 6px;
  }
  h1 { font-size: 1.7rem; line-height: 1.25; margin-bottom: 10px; }
  h2 { font-size: 1.3rem; margin-bottom: 8px; }
  p.lead { color: #475569; margin-bottom: 14px; }
  .card {
    background: #ffffff; border: 1px solid #e2e8f0; border-radius: 16px;
    padding: 18px 20px; margin-top: 14px; box-shadow: 0 1px 3px rgba(15,23,42,.05);
  }

  /* ---------- cover ---------- */
  .goal-box {
    border-left: 4px solid #2563eb; padding: 12px 16px; background: #eff6ff;
    border-radius: 0 12px 12px 0; margin: 14px 0;
  }
  .steps { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); gap: 10px; margin-top: 14px; }
  .step { background: #ffffff; border: 1px solid #e2e8f0; border-radius: 12px; padding: 12px; text-align: center; }
  .step .n { display: inline-block; width: 26px; height: 26px; border-radius: 50%; background: #2563eb; color: #ffffff; font-weight: 800; line-height: 26px; margin-bottom: 6px; }
  .step .t { font-size: .88rem; font-weight: 700; }
  .step .d { font-size: .78rem; color: #64748b; }

  /* ---------- vocab ---------- */
  .vocab-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(270px, 1fr)); gap: 12px; margin-top: 14px; }
  .vcard { background: #ffffff; border: 1px solid #e2e8f0; border-radius: 14px; padding: 16px; display: flex; flex-direction: column; gap: 7px; box-shadow: 0 1px 3px rgba(15,23,42,.05); }
  .vtag { display: inline-block; font-size: .7rem; font-weight: 800; letter-spacing: .5px; border-radius: 999px; padding: 2px 10px; width: fit-content; }
  .vtag.fin { background: #dbeafe; color: #1e40af; }
  .vtag.con { background: #dcfce7; color: #166534; }
  .vword { font-size: 1.15rem; font-weight: 800; color: #1d4ed8; }
  .vpron { color: #64748b; font-size: .82rem; }
  .vdef { font-size: .92rem; }
  .vex { font-size: .9rem; background: #f8fafc; border: 1px dashed #bfdbfe; border-radius: 9px; padding: 8px 11px; margin-top: auto; }
  .vex::before { content: "💬 "; }
  .vtip { font-size: .8rem; color: #dc2626; }

  /* ---------- exercises ---------- */
  .bank { display: flex; gap: 8px; flex-wrap: wrap; margin: 12px 0 18px; }
  .word {
    background: #eff6ff; color: #1e3a8a; border: 1px solid #bfdbfe; border-radius: 999px;
    padding: 7px 16px; font-size: .95rem; font-weight: 700; cursor: pointer; transition: all .15s;
  }
  .word:hover { border-color: #2563eb; }
  .word.used { opacity: .3; pointer-events: none; }
  .gap-sent { font-size: 1.05rem; margin: 14px 0 3px; }
  .gap-sent .num { display: inline-flex; width: 22px; height: 22px; border-radius: 50%; background: #e2e8f0; color: #475569; font-size: .75rem; font-weight: 700; align-items: center; justify-content: center; margin-right: 8px; }
  .blank {
    display: inline-block; min-width: 120px; text-align: center; padding: 1px 10px;
    border-bottom: 3px dashed #94a3b8; cursor: pointer; color: #b45309; font-weight: 700;
  }
  .blank:hover { border-color: #d97706; }
  .blank.active { border-color: #d97706; background: #fef3c7; border-radius: 6px 6px 0 0; }
  .blank.ok { color: #15803d; border-color: #16a34a; background: #f0fdf4; border-radius: 6px 6px 0 0; }
  .blank.ko { color: #b91c1c; border-color: #dc2626; background: #fef2f2; border-radius: 6px 6px 0 0; }
  .hint { font-size: .8rem; color: #64748b; margin: 0 0 6px 30px; }
  .btn {
    background: #2563eb; color: #ffffff; border: none; border-radius: 999px;
    padding: 10px 20px; font-size: .95rem; font-weight: 800; cursor: pointer; transition: all .15s;
  }
  .btn:hover { background: #1d4ed8; }
  .btn.ghost { background: transparent; color: #334155; border: 1px solid #cbd5e1; }
  .btn.ghost:hover { border-color: #2563eb; color: #1d4ed8; background: transparent; }
  .btn.small { padding: 7px 14px; font-size: .82rem; }
  .btn:disabled { opacity: .4; cursor: default; }
  .fb { border-radius: 12px; padding: 12px 16px; margin-top: 14px; font-size: .95rem; display: none; }
  .fb.show { display: block; animation: fade .25s; }
  .fb.good { background: #f0fdf4; border: 1px solid #16a34a; }
  .fb.bad { background: #fef2f2; border: 1px solid #dc2626; }

  /* ---------- word order cards ---------- */
  .counter { font-size: .8rem; color: #64748b; }
  .ocard { padding: 14px 16px; margin-top: 12px; }
  .ohead { display: flex; align-items: center; gap: 10px; }
  .onum { display: inline-flex; width: 24px; height: 24px; border-radius: 50%; background: #e2e8f0; color: #475569; font-size: .78rem; font-weight: 700; align-items: center; justify-content: center; flex: none; }
  .ostatus { font-size: .95rem; min-width: 26px; }
  .ohintbtn { margin-left: auto; }
  .oanswer { min-height: 48px; }
  .ofb { font-size: .85rem; margin-top: 10px; display: none; }
  .ofb.good { display: block; color: #15803d; }
  .ofb.bad { display: block; color: #b91c1c; }

  /* ---------- word order mechanics ---------- */
  .pool, .answerline { display: flex; flex-wrap: wrap; gap: 8px; align-items: center; }
  .answerline {
    min-height: 58px; border: 2px dashed #cbd5e1; border-radius: 12px; padding: 10px 12px; margin-top: 12px;
  }
  .answerline.ok { border-color: #16a34a; background: #f0fdf4; }
  .tile {
    background: #eff6ff; border: 1px solid #bfdbfe; color: #1e3a8a; border-radius: 10px;
    padding: 8px 14px; font-size: .95rem; font-weight: 700; cursor: pointer; transition: all .15s;
  }
  .tile:hover { border-color: #2563eb; }
  .tile.punct { border: none; background: transparent; font-size: 1.2rem; padding: 8px 2px; color: #0f172a; }

  /* ---------- role play ---------- */
  .chat { display: flex; flex-direction: column; gap: 10px; margin-top: 14px; }
  .bubble { max-width: 82%; padding: 11px 15px; border-radius: 16px; font-size: .97rem; }
  .bubble.client { align-self: flex-start; background: #e2e8f0; color: #0f172a; border-bottom-left-radius: 4px; }
  .bubble.client b { color: #1d4ed8; }
  .bubble.trainer { align-self: flex-end; background: #dbeafe; border: 1px solid #93c5fd; color: #0f172a; border-bottom-right-radius: 4px; }
  .bubble.trainer b { color: #1e40af; }
  .opts { display: flex; flex-direction: column; gap: 9px; margin-top: 16px; }
  .opt {
    text-align: left; background: #ffffff; color: #0f172a; border: 1px solid #cbd5e1;
    border-radius: 12px; padding: 12px 16px; font-size: .95rem; cursor: pointer; transition: all .15s;
  }
  .opt:hover { border-color: #2563eb; background: #f8fafc; }
  .opt.wrong { border-color: #dc2626; background: #fef2f2; opacity: .5; pointer-events: none; }
  .typing { color: #64748b; font-style: italic; font-size: .85rem; align-self: flex-start; }

  /* ---------- final summary ---------- */
  .finalbox { border: 1px solid #16a34a; background: #f0fdf4; border-radius: 16px; padding: 20px; margin-top: 16px; }
  .finalbox h3 { margin-bottom: 6px; }
  .results { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px,1fr)); gap: 10px; margin: 14px 0; }
  .res { background: #ffffff; border: 1px solid #e2e8f0; border-radius: 12px; padding: 12px; text-align: center; }
  .res .v { font-size: 1.3rem; font-weight: 800; color: #1d4ed8; }
  .res .l { font-size: .78rem; color: #64748b; }

  /* ---------- footer ---------- */
  footer.nav {
    position: fixed; left: 0; right: 0; bottom: 0; background: rgba(241,245,249,.95);
    border-top: 1px solid #e2e8f0;
    display: flex; justify-content: center; padding: 12px 16px;
  }
  footer.nav .inner { display: flex; gap: 12px; align-items: center; max-width: 940px; width: 100%; justify-content: space-between; }
  .pageinfo { color: #64748b; font-size: .85rem; }
  .done-badge { display: inline-block; background: #f0fdf4; border: 1px solid #16a34a; color: #15803d; font-size: .78rem; border-radius: 999px; padding: 3px 10px; margin-top: 10px; }
</style>
</head>
<body>
<div class="wrap">

  <header class="top">
    <div class="brand">📈 English for <span class="accent">Financial Meetings</span></div>
    <div class="lesson">Lesson 1 · Presenting financial data with confidence · ~45 min · Teacher: Luca</div>
    <div class="bar">
      <nav id="dots"></nav>
      <div class="score-pill">🏆 <span id="scoreTotal">0</span>/22 points</div>
    </div>
  </header>

  <!-- ============ SLIDE 0 · WELCOME ============ -->
  <section class="slide" id="s0">
    <span class="kicker">Welcome, Monica! 🎯</span>
    <h1>Your next financial presentation — in English</h1>
    <p class="lead">You know the numbers. In this lesson we make sure your English is just as strong as your data — so you can present with confidence in any meeting.</p>

    <div class="goal-box">
      <b>🎯 Today's goal:</b> learn 6 key words — 3 financial terms and 3 connectors — and use them in a real cost review meeting about suppliers: from your opening to your final summary.
    </div>

    <div class="steps">
      <div class="step"><div class="n">1</div><div class="t">Vocabulary</div><div class="d">3 financial terms + 3 connectors</div></div>
      <div class="step"><div class="n">2</div><div class="t">Fill the gaps</div><div class="d">you read and choose</div></div>
      <div class="step"><div class="n">3</div><div class="t">Build the sentences</div><div class="d">you build presentation phrases</div></div>
      <div class="step"><div class="n">4</div><div class="t">Meeting role play 🎭</div><div class="d">you present to your team</div></div>
    </div>

    <div class="card">
      💡 <b>How to use this lesson:</b> click on the words and answers — everything is interactive! Say every sentence <b>out loud</b>, like a real presentation. You are training your presentation muscles. 🎤
    </div>
  </section>

  <!-- ============ SLIDE 1 · VOCABULARY ============ -->
  <section class="slide" id="s1">
    <span class="kicker">Slide 1 · Vocabulary</span>
    <h2>6 words for your next meeting</h2>
    <p class="lead">Read each card, say the word out loud 3 times, then click <b>Next</b>. Notice: 3 words are financial terms and 3 are connectors — the words that guide your audience through the presentation.</p>
    <div class="vocab-grid" id="vocabGrid"></div>
    <div class="card">🔗 <b>Connectors are your GPS in a presentation:</b> use <b>Moreover</b> to ADD a point, <b>Instead</b> to show a DIFFERENT choice, and <b>Due to</b> to explain the REASON. Memorize the full example sentences — you can reuse them word-for-word in real meetings.</div>
  </section>

  <!-- ============ SLIDE 2 · FILL THE GAPS ============ -->
  <section class="slide" id="s2">
    <span class="kicker">Slide 2 · Exercise 1</span>
    <h2>Fill the gaps ✏️</h2>
    <p class="lead">Click a gap, then click the right word from the bank. Check your answers at the end!</p>

    <div class="bank" id="gapBank"></div>
    <div id="gapSents"></div>

    <div style="display:flex; gap:10px; flex-wrap:wrap; margin-top:16px;">
      <button class="btn" id="gapCheck">Check answers ✓</button>
      <button class="btn ghost" id="gapReset">Reset</button>
    </div>
    <div class="fb" id="gapFb"></div>
  </section>

  <!-- ============ SLIDE 3 · BUILD THE SENTENCES ============ -->
  <section class="slide" id="s3">
    <span class="kicker">Slide 3 · Exercise 2</span>
    <h2>Build the sentences 🧩</h2>
    <p class="lead">Ten real sentences for presenting financial data — all on one page. Click the words in the correct order: each sentence checks itself automatically!</p>

    <div style="display:flex; justify-content:space-between; align-items:center; gap:10px; flex-wrap:wrap; margin:6px 0 4px;">
      <div style="font-weight:700;">✅ Solved: <span id="orderSolved" style="color:#15803d;">0</span>/10</div>
      <button class="btn ghost small" id="orderResetAll">↻ Reset all</button>
    </div>

    <div id="orderList"></div>

    <div class="done-badge" id="orderDone" style="display:none;">🏆 All 10 sentences complete — you are presenting like a pro!</div>
  </section>

  <!-- ============ SLIDE 4 · ROLE PLAY ============ -->
  <section class="slide" id="s4">
    <span class="kicker">Slide 4 · Role play — the real thing 🎭</span>
    <h2>The cost review meeting is starting…</h2>
    <p class="lead">You are presenting the quarterly cost review about suppliers. <b>Mark</b> is your manager and <b>Sarah</b> is a colleague. Choose the best answer at each turn. Practice here first — then we'll run this meeting live in our lesson! 🎤</p>

    <div class="chat" id="chat"></div>
    <div class="opts" id="opts"></div>
    <button class="btn ghost small" id="roleHintBtn" style="margin-top:12px;">💡 Need a hint?</button>
    <div class="hint" id="roleHint" style="margin-top:8px; display:none;"></div>
    <div class="fb" id="roleFb"></div>

    <div class="finalbox" id="finalBox" style="display:none;">
      <h3>🎉 Congratulations, Monica!</h3>
      <p>You just presented a full cost review in English — from the opening to the final summary. This is exactly what you'll do in your next meeting.</p>
      <div class="results" id="finalResults"></div>
      <p style="margin-top:10px;"><b>Next step:</b> in our next lesson we run this meeting <b>live</b> — I'll be Mark and Sarah, then we swap roles. After that, we build your lessons around <b>your real data and your real meetings</b>. Ready to become the go-to person for presentations in English? 🚀</p>
      <button class="btn small" id="roleReplay" style="margin-top:12px;">↻ Run the meeting again</button>
    </div>
  </section>

  <footer class="nav">
    <div class="inner">
      <button class="btn ghost" id="prevBtn">← Back</button>
      <div class="pageinfo" id="pageInfo"></div>
      <button class="btn" id="nextBtn">Next →</button>
    </div>
  </footer>
</div>

<script>
/* ================= DATA ================= */
var VOCAB = [
  { word: "revenue", pron: "/ˈrev.ə.nuː/", tag: "fin",
    def: "The money a company receives from selling its products or services.",
    ex: "Our revenue increased by 12% in the third quarter." },
  { word: "suppliers", pron: "/səˈplaɪ.əz/", tag: "fin",
    def: "The companies that sell products or services to your company.",
    ex: "We changed suppliers because their prices were too high." },
  { word: "invoice", pron: "/ˈɪn.vɔɪs/", tag: "fin",
    def: "A document that asks a customer to pay. It shows what was bought and the total price.",
    ex: "Please check the invoice before you pay." },
  { word: "moreover", pron: "/mɔːrˈəʊ.vər/", tag: "con",
    def: "Adds more information to your point. Like \"also\" — but more professional.",
    ex: "Costs went down by 5%. Moreover, delivery is now faster.",
    tip: "💡 After \"Moreover\", always use a comma: \"Moreover, delivery is faster.\"" },
  { word: "instead", pron: "/ɪnˈsted/", tag: "con",
    def: "Shows a different choice — plan B instead of plan A.",
    ex: "Instead of one big order, we made three smaller ones." },
  { word: "due to", pron: "/djuː tuː/", tag: "con",
    def: "Gives the reason for something. Synonym: \"because of\".",
    ex: "Revenue grew due to strong sales in June." }
];

var GAP = [
  { pre: "Our ", post: " increased by 12% this quarter — from €1.2 million to €1.35 million.", ans: "revenue", hint: "💡 = money from sales" },
  { pre: "We changed ", post: " because their prices were too high.", ans: "suppliers", hint: "💡 = companies that sell to us" },
  { pre: "Please check the ", post: " before you pay — it shows what we bought and the total price.", ans: "invoice", hint: "💡 = the document that asks for payment" },
  { pre: "Costs went down by 5%. ", post: ", delivery is now faster.", ans: "moreover", hint: "💡 = connector to ADD information" },
  { pre: "", post: " of one big order, we made three smaller ones.", ans: "instead", hint: "💡 = connector for a DIFFERENT choice" },
  { pre: "Revenue grew ", post: " strong sales in June.", ans: "due to", hint: "💡 = connector for a REASON" }
];

var ORDER = [
  { tiles: ["Let me", "start", "with", "our revenue", "for", "this quarter", "."], hint: "💡 Starts with: «Let me…»" },
  { tiles: ["Our suppliers", "increased", "their prices", "by", "ten percent", "."], hint: "💡 Starts with: «Our suppliers…»" },
  { tiles: ["Please", "check", "the invoice", "before", "you pay", "."], hint: "💡 Starts with: «Please…»" },
  { tiles: ["Revenue", "increased", "due to", "strong sales", "in June", "."], hint: "💡 Starts with: «Revenue…»" },
  { tiles: ["Moreover", ",", "our costs", "are now lower", "."], hint: "💡 Starts with: «Moreover…» — don't forget the comma!" },
  { tiles: ["Instead of", "one supplier", ",", "we now use", "two", "."], hint: "💡 Starts with: «Instead of…»" },
  { tiles: ["We sent", "the invoice", "to", "the new client", "."], hint: "💡 Starts with: «We sent…»" },
  { tiles: ["This increase", "is", "due to", "our new", "marketing campaign", "."], hint: "💡 Starts with: «This increase…»" },
  { tiles: ["As you can see", ",", "supplier costs", "went down", "by 5%", "."], hint: "💡 Starts with: «As you can see…»" },
  { tiles: ["Let's", "move on", "to", "the next slide", "."], hint: "💡 Starts with: «Let's…»" }
];

var ROLE = [
  { speaker: "Mark", client: "Good morning, everyone. Monica, could you start with our supplier costs this quarter?",
    hint: "💡 Start like a professional: \"Let me start with…\"",
    options: [
      { t: "I don't have the data with me today.", ok: false,
        fb: "Always arrive with your data! You are the presenter — you own the numbers." },
      { t: "Good morning. Let me start with our supplier costs for this quarter.", ok: true,
        fb: "Perfect opener! Short, clear and professional — the best way to start a presentation." },
      { t: "Sorry, I can't today. Maybe next week?", ok: false,
        fb: "This is YOUR moment — take it with confidence! A presentation starts with a calm, clear opening." }
    ] },
  { speaker: "Mark", client: "Sure, go ahead. What's the situation with our suppliers?",
    hint: "💡 Give a fact + the reason with \"due to\".",
    options: [
      { t: "The suppliers are bad people.", ok: false,
        fb: "Careful! In a meeting, stay professional: use facts and numbers, not feelings." },
      { t: "I don't know, you should ask the suppliers.", ok: false,
        fb: "You are the expert here — you have the data. Never say \"I don't know\" without checking the numbers first." },
      { t: "Supplier costs went down by 8%, due to our new contract with Rossi & Co.", ok: true,
        fb: "Excellent! A clear fact + the reason with \"due to\". That's exactly how to present data." }
    ] },
  { speaker: "Sarah", client: "Great news! But what about delivery times?",
    hint: "💡 \"Moreover\" to add + \"instead\" to contrast.",
    options: [
      { t: "Delivery is not my department.", ok: false,
        fb: "\"Not my job\" sounds bad in a meeting. Show that you know the whole picture." },
      { t: "Delivery improved too. Moreover, we now have two suppliers instead of one.", ok: true,
        fb: "Brilliant! You used two connectors in one answer: \"Moreover\" to add and \"instead\" to contrast." },
      { t: "That's a secret.", ok: false,
        fb: "Share information with your team — transparency builds trust in a meeting." }
    ] },
  { speaker: "Mark", client: "Good. And the invoices — are we paying on time?",
    hint: "💡 Be precise: mention checking and payment terms.",
    options: [
      { t: "Invoices are boring.", ok: false,
        fb: "Never say this! Invoices are money — always an important topic in finance." },
      { t: "We never check the invoices.", ok: false,
        fb: "Oh no! Always check invoices before paying — that's basic financial control." },
      { t: "Yes, we check every invoice before we pay, and we always pay within thirty days.", ok: true,
        fb: "Great! Clear, precise and professional. Details like this build your credibility." }
    ] },
  { speaker: "Mark", client: "Excellent work. Last question: what's the impact on our revenue?",
    hint: "💡 Connect cause and effect with \"due to\" + a number!",
    options: [
      { t: "Revenue is not important for finance.", ok: false,
        fb: "Revenue is one of THE most important numbers in finance!" },
      { t: "I don't know, that's Mark's job.", ok: false,
        fb: "You have the numbers — connect the dots for your audience. That's what presenting means." },
      { t: "Due to lower costs and faster delivery, revenue increased by 12% this quarter.", ok: true,
        fb: "Perfect! Cause and effect with \"due to\" plus a clear number. That's a presentation highlight." }
    ] },
  { speaker: "Mark", client: "Wonderful. Can you summarize your main points for everyone?",
    hint: "💡 Use \"To sum up:\" + your three key points.",
    options: [
      { t: "No, sorry, I forgot everything.", ok: false,
        fb: "You just presented it — you know this! Summarize with confidence." },
      { t: "Same as I said before, so I won't repeat it.", ok: false,
        fb: "Always summarize at the end — repeating key points helps your audience remember them." },
      { t: "To sum up: supplier costs are down, delivery is faster, and revenue is up by 12%.", ok: true,
        fb: "A perfect summary! Short, structured and confident. That's how you close a presentation. 🎉" }
    ] }
];

/* ================= STATE ================= */
var MAX = { gap: GAP.length, order: ORDER.length, role: ROLE.length };
var TOTAL = MAX.gap + MAX.order + MAX.role;
var score = { gap: null, order: null, role: null };
var done = { vocab: false, gap: false, order: false, role: false };
var current = 0;

function $(id) { return document.getElementById(id); }

/* ================= NAVIGATION ================= */
var LABELS = ["👋 Welcome", "📖 Vocabulary", "✏️ Fill the gaps", "🧩 Build sentences", "🎭 Meeting role play"];

function buildDots() {
  var nav = $("dots");
  LABELS.forEach(function (lab, i) {
    var b = document.createElement("button");
    b.className = "dot"; b.textContent = lab; b.onclick = function () { go(i); };
    nav.appendChild(b);
  });
}
function go(i) {
  current = i;
  var slides = document.querySelectorAll(".slide");
  for (var k = 0; k < slides.length; k++) { slides[k].classList.toggle("active", k === i); }
  var dots = document.querySelectorAll(".dot");
  for (var d = 0; d < dots.length; d++) { dots[d].classList.toggle("active", d === i); }
  $("prevBtn").disabled = (i === 0);
  $("nextBtn").style.visibility = (i === LABELS.length - 1) ? "hidden" : "visible";
  $("pageInfo").textContent = "Slide " + (i + 1) + " / " + LABELS.length;
  window.scrollTo(0, 0);
}
function refreshDots() {
  document.querySelectorAll(".dot")[1].classList.toggle("done", done.vocab);
  document.querySelectorAll(".dot")[2].classList.toggle("done", done.gap);
  document.querySelectorAll(".dot")[3].classList.toggle("done", done.order);
  document.querySelectorAll(".dot")[4].classList.toggle("done", done.role);
}
function totalScore() {
  var s = function (x) { return (x === null ? 0 : x); };
  return s(score.gap) + s(score.order) + s(score.role);
}
function updateScorePill() { $("scoreTotal").textContent = totalScore() + " / " + TOTAL; }

/* ================= SLIDE 1 · VOCAB ================= */
function renderVocab() {
  var g = $("vocabGrid");
  g.innerHTML = "";
  VOCAB.forEach(function (v) {
    var c = document.createElement("div");
    c.className = "vcard";
    var tagLabel = (v.tag === "fin") ? "💰 FINANCIAL" : "🔗 CONNECTOR";
    var tagClass = (v.tag === "fin") ? "fin" : "con";
    c.innerHTML =
      '<span class="vtag ' + tagClass + '">' + tagLabel + "</span>" +
      '<div class="vword">' + v.word + "</div>" +
      '<div class="vpron">🔊 ' + v.pron + "</div>" +
      '<div class="vdef">' + v.def + "</div>" +
      (v.tip ? '<div class="vtip">' + v.tip + "</div>" : "") +
      '<div class="vex">' + v.ex + "</div>";
    g.appendChild(c);
  });
  done.vocab = true;
  refreshDots();
}

/* ================= SLIDE 2 · GAP FILL ================= */
var gapFilled = [];
var gapChecked = false;
var activeBlank = -1;

function renderGap() {
  var bank = $("gapBank");
  bank.innerHTML = "";
  var words = GAP.map(function (g) { return g.ans; });
  words.sort(function () { return Math.random() - 0.5; });
  words.forEach(function (w) {
    var display = (w === "moreover") ? "Moreover" : ((w === "instead") ? "Instead" : w);
    var b = document.createElement("button");
    b.className = "word"; b.textContent = display; b.dataset.word = w;
    b.onclick = function () { placeWord(w); };
    bank.appendChild(b);
  });

  var box = $("gapSents");
  box.innerHTML = "";
  gapFilled = GAP.map(function () { return null; });
  GAP.forEach(function (g, i) {
    var row = document.createElement("div");
    row.className = "gap-sent";
    var blank = document.createElement("span");
    blank.className = "blank"; blank.textContent = "______";
    blank.onclick = function () { selectBlank(i); };
    var num = document.createElement("span");
    num.className = "num"; num.textContent = (i + 1);
    row.appendChild(num);
    row.appendChild(document.createTextNode(g.pre));
    row.appendChild(blank);
    row.appendChild(document.createTextNode(g.post));
    var hint = document.createElement("div");
    hint.className = "hint"; hint.textContent = g.hint;
    box.appendChild(row); box.appendChild(hint);
  });
  gapChecked = false;
  activeBlank = -1;
}
function selectBlank(i) {
  if (gapFilled[i] !== null) {
    var w = gapFilled[i];
    gapFilled[i] = null;
    var bankWords = document.querySelectorAll("#gapBank .word");
    for (var k = 0; k < bankWords.length; k++) {
      if (bankWords[k].dataset.word === w) { bankWords[k].classList.remove("used"); }
    }
  }
  activeBlank = i;
  drawBlanks();
}
function placeWord(w) {
  if (gapFilled.indexOf(w) !== -1) return; // word already used
  var target = activeBlank;
  if (target === -1 || target === null || gapFilled[target] !== null) {
    target = gapFilled.indexOf(null);
  }
  if (target === -1) return;
  gapFilled[target] = w;
  var bankWords = document.querySelectorAll("#gapBank .word");
  for (var k = 0; k < bankWords.length; k++) {
    if (bankWords[k].dataset.word === w) { bankWords[k].classList.add("used"); }
  }
  activeBlank = gapFilled.indexOf(null);
  drawBlanks();
}
function drawBlanks() {
  var blanks = document.querySelectorAll("#gapSents .blank");
  for (var i = 0; i < blanks.length; i++) {
    var display = gapFilled[i];
    if (display === "moreover") { display = "Moreover"; }
    if (display === "instead") { display = "Instead"; }
    blanks[i].textContent = (display === null || display === undefined) ? "______" : display;
    blanks[i].classList.remove("active", "ok", "ko");
    if (i === activeBlank) { blanks[i].classList.add("active"); }
  }
}
function checkGap() {
  var fb = $("gapFb");
  var allFilled = gapFilled.every(function (x) { return x !== null; });
  if (!allFilled) {
    fb.className = "fb bad show";
    fb.innerHTML = "Fill all the gaps first, then check your answers!";
    return;
  }
  var blanks = document.querySelectorAll("#gapSents .blank");
  var ok = 0;
  GAP.forEach(function (g, i) {
    var good = gapFilled[i].toLowerCase().trim() === g.ans;
    blanks[i].classList.add(good ? "ok" : "ko");
    if (good) { ok++; }
  });
  if (!gapChecked) { score.gap = ok; gapChecked = true; }
  if (ok === GAP.length) {
    done.gap = true;
    fb.className = "fb good show";
    fb.innerHTML = "🏆 Perfect! " + ok + "/" + GAP.length + " — all six words in the right place. You are ready for the next step!";
  } else {
    fb.className = "fb bad show";
    fb.innerHTML = "Almost! " + ok + "/" + GAP.length + " correct. Look at the red gaps, try again and check again — practice makes perfect!";
  }
  refreshDots(); updateScorePill();
}
function resetGap() {
  renderGap();
  $("gapFb").className = "fb";
}

/* ================= SLIDE 3 · WORD ORDER (10 sentences, one page) ================= */
var ORDER_STATE = [];

function orderText(o) {
  var s = "";
  for (var i = 0; i < o.tiles.length; i++) {
    var t = o.tiles[i];
    if (t === "?" || t === "." || t === "!" || t === ",") { s += t; }
    else { s += (i === 0 ? "" : " ") + t; }
  }
  return s;
}
function buildOrder() {
  var list = $("orderList");
  list.innerHTML = "";
  score.order = null;
  ORDER_STATE = ORDER.map(function (o, i) {
    var st = { placed: [], tried: false, done: false, card: null };
    var card = document.createElement("div");
    card.className = "card ocard";
    card.innerHTML =
      '<div class="ohead">' +
        '<span class="onum">' + (i + 1) + '</span>' +
        '<span class="ostatus"></span>' +
        '<button class="btn ghost small ohintbtn" type="button">💡 Need a hint?</button>' +
      '</div>' +
      '<div class="hint ohint" style="display:none; margin:8px 0 0;">' + o.hint + '</div>' +
      '<div class="answerline oanswer" style="margin-top:10px;"></div>' +
      '<div class="pool opool" style="margin-top:10px;"></div>' +
      '<div class="ofb"></div>';
    list.appendChild(card);
    st.card = card;
    var pool = card.querySelector(".opool");
    var idx = o.tiles.map(function (_, k) { return k; });
    idx.sort(function () { return Math.random() - 0.5; });
    idx.forEach(function (ti) {
      var t = document.createElement("button");
      var isPunct = (o.tiles[ti] === "?" || o.tiles[ti] === "." || o.tiles[ti] === "!" || o.tiles[ti] === ",");
      t.className = "tile" + (isPunct ? " punct" : "");
      t.textContent = o.tiles[ti];
      t.onclick = function () { placeOrderTile(i, ti); };
      pool.appendChild(t);
    });
    card.querySelector(".ohintbtn").onclick = function () {
      var h = card.querySelector(".ohint");
      h.style.display = (h.style.display === "none") ? "" : "none";
    };
    return st;
  });
  for (var d = 0; d < ORDER.length; d++) { drawOrder(d); }
  done.order = false;
  $("orderDone").style.display = "none";
  updateOrderSolved();
}
function drawOrder(i) {
  var o = ORDER[i];
  var st = ORDER_STATE[i];
  var ans = st.card.querySelector(".oanswer");
  ans.innerHTML = "";
  if (st.placed.length === 0) {
    ans.innerHTML = '<span style="color:#94a3b8;font-size:.85rem;">Click the words below to build the sentence…</span>';
  }
  st.placed.forEach(function (ti, p) {
    var isPunct = (o.tiles[ti] === "?" || o.tiles[ti] === "." || o.tiles[ti] === "!" || o.tiles[ti] === ",");
    var t = document.createElement("button");
    t.className = "tile" + (isPunct ? " punct" : "");
    t.textContent = o.tiles[ti];
    t.onclick = function () { removeOrderTile(i, p); };
    ans.appendChild(t);
  });
  var placedCounts = {};
  st.placed.forEach(function (ti) {
    var w = o.tiles[ti];
    placedCounts[w] = (placedCounts[w] || 0) + 1;
  });
  var seen = {};
  var pool = st.card.querySelectorAll(".opool .tile");
  for (var k = 0; k < pool.length; k++) {
    var txt = pool[k].textContent;
    var occ = seen[txt] || 0;
    seen[txt] = occ + 1;
    pool[k].style.display = (occ < (placedCounts[txt] || 0)) ? "none" : "";
  }
}
function placeOrderTile(i, ti) {
  var st = ORDER_STATE[i];
  if (st.done) return;
  st.placed.push(ti);
  drawOrder(i);
  if (st.placed.length === ORDER[i].tiles.length) { evaluateOrder(i); }
}
function removeOrderTile(i, p) {
  var st = ORDER_STATE[i];
  if (st.done) return;
  st.placed.splice(p, 1);
  drawOrder(i);
}
function evaluateOrder(i) {
  var o = ORDER[i];
  var st = ORDER_STATE[i];
  var correct = st.placed.every(function (v, k) { return v === k; });
  var fb = st.card.querySelector(".ofb");
  if (correct) {
    if (!st.tried) {
      score.order = (score.order === null ? 0 : score.order) + 1;
    }
    st.tried = true;
    st.done = true;
    st.card.querySelector(".oanswer").classList.add("ok");
    st.card.querySelector(".ostatus").innerHTML = "✅";
    fb.className = "ofb good";
    fb.innerHTML = "✅ \"" + orderText(o) + "\" — perfect! You can say this in a real meeting. 🎤";
    updateOrderSolved(); updateScorePill();
  } else {
    st.tried = true;
    st.card.querySelector(".ostatus").innerHTML = "🔁";
    fb.className = "ofb bad";
    fb.innerHTML = "✗ Not the natural order yet — click a word above to remove it and try again. Or click <b>💡 Need a hint?</b>";
  }
}
function updateOrderSolved() {
  var solved = ORDER_STATE.filter(function (s) { return s.done; }).length;
  $("orderSolved").textContent = solved;
  if (solved === ORDER.length) {
    done.order = true;
    $("orderDone").style.display = "";
    refreshDots();
  }
}

/* ================= SLIDE 4 · ROLE PLAY ================= */
var roleTurn = 0;
var roleScore = 0;
var typingTimer = null;

function bubble(text, who, name) {
  var b = document.createElement("div");
  b.className = "bubble " + who;
  var label = (who === "client") ? name : "You";
  b.innerHTML = "<b>" + label + ":</b> " + text;
  $("chat").appendChild(b);
  var box = $("chat");
  box.scrollTop = box.scrollHeight;
}
function showTyping(name) {
  var t = document.createElement("div");
  t.className = "typing"; t.id = "typing";
  t.textContent = name + " is typing…";
  $("chat").appendChild(t);
}
function renderRoleOpts() {
  var turn = ROLE[roleTurn];
  var box = $("opts");
  box.innerHTML = "";
  var idx = turn.options.map(function (_, i) { return i; });
  idx.sort(function () { return Math.random() - 0.5; });
  idx.forEach(function (i) {
    var o = turn.options[i];
    var b = document.createElement("button");
    b.className = "opt"; b.textContent = o.t;
    b.onclick = function () { pickOption(b, o); };
    box.appendChild(b);
  });
  $("roleHint").style.display = "none";
}
function pickOption(el, o) {
  var fb = $("roleFb");
  if (o.ok) {
    el.style.borderColor = "#16a34a";
    el.style.background = "#f0fdf4";
    fb.className = "fb good show";
    fb.innerHTML = "✓ " + o.fb;
    $("opts").innerHTML = "";
    roleScore++;
    score.role = roleScore;
    bubble(o.t, "trainer");
    updateScorePill();
    roleTurn++;
    if (roleTurn < ROLE.length) {
      showTyping(ROLE[roleTurn].speaker);
      typingTimer = setTimeout(function () {
        var t = document.getElementById("typing");
        if (t) { t.remove(); }
        bubble(ROLE[roleTurn].client, "client", ROLE[roleTurn].speaker);
        renderRoleOpts();
      }, 1200);
    } else {
      finishRole();
    }
  } else {
    el.classList.add("wrong");
    fb.className = "fb bad show";
    fb.innerHTML = "✗ " + o.fb;
  }
}
function finishRole() {
  done.role = true;
  refreshDots(); updateScorePill();
  function fmt(x, m) { return (x === null ? "—" : x + "/" + m); }
  $("finalResults").innerHTML =
    '<div class="res"><div class="v">' + fmt(score.gap, MAX.gap) + '</div><div class="l">✏️ Fill the gaps</div></div>' +
    '<div class="res"><div class="v">' + fmt(score.order, MAX.order) + '</div><div class="l">🧩 Build sentences</div></div>' +
    '<div class="res"><div class="v">' + fmt(score.role, MAX.role) + '</div><div class="l">🎭 Meeting role play</div></div>' +
    '<div class="res"><div class="v">' + totalScore() + "/" + TOTAL + '</div><div class="l">🏆 Total</div></div>';
  $("finalBox").style.display = "";
}
function startRole() {
  roleTurn = 0; roleScore = 0;
  if (typingTimer) { clearTimeout(typingTimer); }
  score.role = null;
  $("chat").innerHTML = "";
  $("finalBox").style.display = "none";
  $("roleFb").className = "fb";
  bubble(ROLE[0].client, "client", ROLE[0].speaker);
  renderRoleOpts();
  updateScorePill();
}

/* ================= WIRE-UP ================= */
buildDots();
renderVocab();
renderGap();
buildOrder();
startRole();

$("prevBtn").onclick = function () { go(Math.max(0, current - 1)); };
$("nextBtn").onclick = function () { go(Math.min(LABELS.length - 1, current + 1)); };
$("gapCheck").onclick = checkGap;
$("gapReset").onclick = resetGap;
$("orderResetAll").onclick = function () { buildOrder(); updateScorePill(); };
$("roleHintBtn").onclick = function () {
  var h = $("roleHint");
  h.style.display = "";
  h.textContent = ROLE[roleTurn].hint;
};
$("roleReplay").onclick = startRole;

go(0);
updateScorePill();
</script>
</body>
</html>
