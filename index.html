<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>เรียนรู้บล็อกคำสั่ง Scratch - ห้องเรียนครูดีน่า (AR Game Edition)</title>

  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css">

  <!-- MediaPipe Hands -->
  <script src="https://cdn.jsdelivr.net/npm/@mediapipe/camera_utils/camera_utils.js" crossorigin="anonymous"></script>
  <script src="https://cdn.jsdelivr.net/npm/@mediapipe/control_utils/control_utils.js" crossorigin="anonymous"></script>
  <script src="https://cdn.jsdelivr.net/npm/@mediapipe/drawing_utils/drawing_utils.js" crossorigin="anonymous"></script>
  <script src="https://cdn.jsdelivr.net/npm/@mediapipe/hands/hands.js" crossorigin="anonymous"></script>

  <style>
    :root{
      --pink:#ff93c9;
      --pink2:#ffd6e9;
      --blue:#82d9ff;
      --blue2:#dff6ff;
      --yellow:#ffd35a;
      --purple:#9b6df6;
      --orange:#ff9c4a;
      --sound:#ef6fae;
      --motion:#4c97ff;
      --event:#ffbf00;
      --green:#68d391;
      --ink:#344054;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:'Kanit',sans-serif;
      color:var(--ink);
      background:
        radial-gradient(circle at 18px 18px, rgba(255,147,201,.28) 0 4px, transparent 5px),
        radial-gradient(circle at 54px 54px, rgba(130,217,255,.28) 0 4px, transparent 5px),
        #fffafe;
      background-size:72px 72px;
    }
    button,input,select{font-family:inherit}
    .app-shell{height:100vh;overflow:hidden;display:flex;flex-direction:column}
    .glass{
      background:rgba(255,255,255,.82);
      backdrop-filter: blur(14px);
      box-shadow:0 12px 32px rgba(93,90,130,.12);
    }
    .nav-btn{
      border:2px solid rgba(255,255,255,.85);
      box-shadow:0 5px 0 rgba(86,83,121,.12);
      transition:.2s ease;
    }
    .nav-btn:hover{transform:translateY(-2px) scale(1.02)}
    .nav-btn.active{outline:4px solid rgba(255,255,255,.85); transform:translateY(-1px)}
    .view{display:none;height:100%;min-height:0}
    .view.active{display:flex}

    /* Scratch blocks */
    .scratch-block{
      position:relative;
      color:white;
      font-weight:700;
      padding:12px 18px 12px 22px;
      border-radius:9px;
      box-shadow:
        inset 0 -4px 0 rgba(0,0,0,.14),
        inset 0 2px 0 rgba(255,255,255,.22),
        0 5px 12px rgba(50,50,80,.12);
      min-width:190px;
      cursor:pointer;
      user-select:none;
      transition:transform .18s ease, filter .18s ease;
    }
    .scratch-block:hover{transform:scale(1.045);filter:brightness(1.04);z-index:5}
    .scratch-block::before{
      content:"";
      position:absolute; top:-1px; left:28px;
      width:46px; height:10px;
      background:rgba(255,255,255,.55);
      border-radius:0 0 12px 12px;
      opacity:.45;
    }
    .scratch-block::after{
      content:"";
      position:absolute; bottom:-7px; left:34px;
      width:42px;height:10px;
      background:inherit;
      border-radius:0 0 10px 10px;
      filter:brightness(.97);
    }
    .hat-block{border-radius:25px 12px 9px 9px;padding-top:16px}
    .hat-block::before{display:none}
    .c-block{padding-bottom:18px}
    .c-block .c-slot{
      background:rgba(255,255,255,.3);
      height:38px;border-radius:8px;
      margin-top:10px;border:2px dashed rgba(255,255,255,.45);
    }
    .event{background:var(--event)}
    .motion{background:var(--motion)}
    .looks{background:var(--purple)}
    .control{background:var(--orange)}
    .sound{background:var(--sound)}
    .tooltip-wrap{position:relative}
    .tooltip-wrap .tip{
      position:absolute;left:50%;bottom:calc(100% + 10px);
      transform:translateX(-50%) translateY(6px);
      width:245px;background:#273248;color:#fff;
      padding:9px 11px;border-radius:10px;font-size:12px;font-weight:400;
      pointer-events:none;opacity:0;transition:.2s;
      z-index:40;box-shadow:0 10px 30px rgba(0,0,0,.18)
    }
    .tooltip-wrap:hover .tip{opacity:1;transform:translateX(-50%) translateY(0)}
    .workspace{
      position:relative;
      background:
        linear-gradient(rgba(255,255,255,.75),rgba(255,255,255,.75)),
        radial-gradient(circle at 1px 1px,#c8d8eb 1.5px,transparent 1.6px);
      background-size:auto,22px 22px;
    }
    .draggable{position:absolute;cursor:grab;touch-action:none}
    .draggable:active{cursor:grabbing}

    /* worksheet */
    .modal-backdrop{background:rgba(43,52,73,.48);backdrop-filter:blur(6px)}
    .tab-btn.active{background:#ff8fc7;color:#fff}
    .option-chip{border:2px solid #f1b6d4;background:#fff4fa;border-radius:14px;padding:8px 12px;font-weight:700;cursor:pointer}
    .drop-answer{min-width:42px;min-height:34px;border:2px dashed #c47bac;border-radius:9px;display:inline-flex;align-items:center;justify-content:center;background:#fff}
    .tf-btn.selected{transform:scale(1.08);box-shadow:0 0 0 4px rgba(255,255,255,.8)}

    /* AR */
    #gameView{position:relative;overflow:hidden}
    #gameVideo{
      position:absolute;inset:0;width:100%;height:100%;object-fit:cover;
      transform:scaleX(-1);opacity:.18;display:none
    }
    .game-overlay{position:absolute;inset:0;pointer-events:none}
    #magicCursor{
      position:fixed;width:42px;height:42px;z-index:9999;pointer-events:none;
      display:none;transform:translate(-50%,-50%);
      filter:drop-shadow(0 0 12px #ffd43b);
      font-size:34px;color:#ffd43b
    }
    .floating-block{
      position:absolute;bottom:-120px;
      animation:floatUp linear forwards;
      pointer-events:auto
    }
    @keyframes floatUp{
      0%{transform:translateY(0) rotate(-3deg);opacity:.2}
      10%{opacity:1}
      100%{transform:translateY(-115vh) rotate(5deg);opacity:.95}
    }
    @keyframes shake{
      0%,100%{transform:translateX(0)}
      20%{transform:translateX(-12px)}
      40%{transform:translateX(12px)}
      60%{transform:translateX(-8px)}
      80%{transform:translateX(8px)}
    }
    .shake{animation:shake .36s ease}
    @keyframes popOut{
      0%{transform:scale(1);opacity:1}
      60%{transform:scale(1.4);opacity:1}
      100%{transform:scale(.1);opacity:0}
    }
    .pop{animation:popOut .45s ease forwards}
    .starfall{position:fixed;top:-30px;z-index:10000;pointer-events:none;animation:fall 1.4s linear forwards;font-size:24px}
    @keyframes fall{to{transform:translateY(110vh) rotate(540deg);opacity:.2}}

    /* certificate */
    .certificate{
      width:min(1100px,95%);aspect-ratio:1.414/1;
      background:#fffefc;
      border:14px solid #f39ac3;
      outline:3px solid #ffd8e9;
      position:relative;
      box-shadow:0 20px 60px rgba(95,80,110,.18);
    }
    .certificate::before{
      content:"";position:absolute;inset:18px;border:2px solid #f8c8dc;pointer-events:none
    }
    .stamp{
      width:115px;height:115px;border:7px double #e7b51c;border-radius:50%;
      color:#c99b12;font-weight:800;display:flex;align-items:center;justify-content:center;
      text-align:center;transform:rotate(-12deg);opacity:.9
    }
    @media print {
      @page { size: A4 landscape; margin: 0; }
      body{background:white!important}
      body *{visibility:hidden!important}
      #printArea, #printArea *{visibility:visible!important}
      #printArea{
        position:absolute!important;left:0!important;top:0!important;
        width:297mm!important;height:210mm!important;
        display:flex!important;align-items:center!important;justify-content:center!important;
        background:white!important;
      }
      #printArea .certificate{
        width:277mm!important;height:190mm!important;
        box-shadow:none!important;
      }
    }
  </style>
</head>
<body>
<div class="app-shell">
  <header class="glass px-4 py-3 border-b border-white/70 z-50">
    <div class="flex items-center justify-between gap-4">
      <div class="flex items-center gap-3 min-w-0">
        <div class="w-14 h-14 rounded-2xl bg-orange-100 flex items-center justify-center shadow-md border-2 border-white text-4xl">🐱</div>
        <div class="min-w-0">
          <h1 class="font-extrabold text-lg md:text-2xl text-pink-600 leading-tight truncate">การเขียนโปรแกรมภาษา Scratch ห้องเรียนครูดีน่า</h1>
          <p class="text-xs md:text-sm text-sky-600 font-semibold">AR Game Edition • วิชาวิทยาการคำนวณ</p>
        </div>
      </div>
      <div class="flex gap-2 flex-wrap justify-end">
        <button data-view="score" class="nav-btn bg-rose-200 hover:bg-rose-300 px-3 py-2 rounded-xl font-bold text-sm"><i class="fa-solid fa-trophy"></i> สรุปคะแนน</button>
        <button id="worksheetBtn" class="nav-btn bg-fuchsia-200 hover:bg-fuchsia-300 px-3 py-2 rounded-xl font-bold text-sm"><i class="fa-solid fa-book-open"></i> ใบงาน</button>
        <button data-view="quiz" class="nav-btn bg-violet-200 hover:bg-violet-300 px-3 py-2 rounded-xl font-bold text-sm"><i class="fa-solid fa-pen-to-square"></i> แบบฝึกหัด</button>
        <button data-view="learn" class="nav-btn active bg-sky-200 hover:bg-sky-300 px-3 py-2 rounded-xl font-bold text-sm"><i class="fa-solid fa-graduation-cap"></i> เรียน</button>
        <button data-view="board" class="nav-btn bg-emerald-200 hover:bg-emerald-300 px-3 py-2 rounded-xl font-bold text-sm"><i class="fa-solid fa-diagram-project"></i> กระดาน</button>
        <button data-view="game" class="nav-btn bg-amber-200 hover:bg-amber-300 px-3 py-2 rounded-xl font-bold text-sm"><i class="fa-solid fa-gamepad"></i> เกม</button>
        <div id="cameraStatus" class="w-10 h-10 rounded-xl bg-slate-100 text-slate-400 flex items-center justify-center" title="สถานะกล้อง"><i class="fa-solid fa-video-slash"></i></div>
      </div>
    </div>
  </header>

  <main class="flex-1 min-h-0 p-3">
    <!-- LEARN -->
    <section id="learnView" class="view active gap-3">
      <aside class="w-[320px] glass rounded-3xl p-4 overflow-y-auto">
        <h2 class="font-extrabold text-pink-600 text-xl mb-1">คลังบล็อก Scratch</h2>
        <p class="text-sm text-slate-500 mb-4">วางเมาส์เหนือบล็อกเพื่อดูความหมาย</p>
        <div class="space-y-4">
          <div class="tooltip-wrap">
            <div class="scratch-block hat-block event"><i class="fa-solid fa-flag text-green-300"></i> เมื่อคลิกธงเขียว</div>
            <div class="tip">เริ่มต้นการทำงานตามบล็อกคำสั่งที่ต่ออยู่ เมื่อคลิกธงสีเขียว</div>
          </div>
          <div class="tooltip-wrap">
            <div class="scratch-block motion"><i class="fa-solid fa-person-walking-arrow-right"></i> เคลื่อนที่ 10 ก้าว</div>
            <div class="tip">ใช้สั่งตัวละครไปข้างหน้าหรือถอยหลังตามจำนวนก้าว</div>
          </div>
          <div class="tooltip-wrap">
            <div class="scratch-block looks"><i class="fa-solid fa-comment"></i> พูด “สวัสดี!” 2 วินาที</div>
            <div class="tip">สั่งให้ตัวละครพูดข้อความตามที่กำหนด</div>
          </div>
          <div class="tooltip-wrap">
            <div class="scratch-block control c-block"><i class="fa-solid fa-code-branch"></i> ถ้า &lt;เงื่อนไข&gt; แล้ว<div class="c-slot"></div></div>
            <div class="tip">ตรวจสอบเงื่อนไข หากเป็นจริงจึงทำคำสั่งภายใน if</div>
          </div>
          <div class="tooltip-wrap">
            <div class="scratch-block sound"><i class="fa-solid fa-volume-high"></i> เล่นเสียง “Meow”</div>
            <div class="tip">สั่งให้เล่นเสียงที่กำหนด</div>
          </div>
        </div>

        <div class="mt-6 border-t pt-4">
          <h3 class="font-extrabold text-sky-700 mb-2"><i class="fa-solid fa-wand-magic-sparkles"></i> ตัวอย่างผังงานสำเร็จรูป</h3>
          <div class="grid gap-2">
            <button onclick="loadExample('right')" class="bg-sky-100 hover:bg-sky-200 rounded-xl p-3 font-semibold text-left">➡️ เดินไปทางขวา 10 ก้าว</button>
            <button onclick="loadExample('left')" class="bg-sky-100 hover:bg-sky-200 rounded-xl p-3 font-semibold text-left">⬅️ เดินไปทางซ้าย 10 ก้าว</button>
            <button onclick="loadExample('up')" class="bg-sky-100 hover:bg-sky-200 rounded-xl p-3 font-semibold text-left">⬆️ เดินขึ้น 10 ก้าว</button>
          </div>
        </div>
      </aside>

      <div class="flex-1 glass rounded-3xl p-3 flex flex-col min-w-0">
        <div class="flex justify-between items-center mb-2 px-1">
          <div>
            <h2 class="font-extrabold text-xl text-sky-700">บทสรุปการต่อบล็อกคำสั่ง</h2>
            <p class="text-sm text-slate-500">คลิกข้อความในบล็อกบนกระดานเพื่อแก้ไขได้</p>
          </div>
          <button onclick="clearBoard('learnWorkspace')" class="bg-rose-100 hover:bg-rose-200 text-rose-600 rounded-xl px-4 py-2 font-bold"><i class="fa-solid fa-trash"></i> ล้างกระดาน</button>
        </div>
        <div id="learnWorkspace" class="workspace flex-1 rounded-2xl border-2 border-dashed border-sky-200 overflow-hidden relative">
          <div class="absolute inset-0 flex items-center justify-center text-slate-300 font-bold text-xl pointer-events-none">เลือกตัวอย่างจากแถบซ้ายเพื่อเริ่มเรียนรู้</div>
        </div>
      </div>
    </section>

    <!-- BOARD -->
    <section id="boardView" class="view gap-3">
      <aside class="w-[320px] glass rounded-3xl p-4 overflow-y-auto">
        <h2 class="font-extrabold text-emerald-700 text-xl">กระดานต่อบล็อก</h2>
        <p class="text-sm text-slate-500 mb-4">คลิกเพื่อเพิ่มบล็อก แล้วลากไปจัดวางบนกระดาน</p>
        <div class="space-y-3">
          <button onclick="addBoardBlock('event')" class="w-full text-left"><div class="scratch-block hat-block event">🚩 เมื่อคลิกธงเขียว</div></button>
          <button onclick="addBoardBlock('motion')" class="w-full text-left"><div class="scratch-block motion">↔️ เคลื่อนที่ 10 ก้าว</div></button>
          <button onclick="addBoardBlock('looks')" class="w-full text-left"><div class="scratch-block looks">💬 พูด “สวัสดี!”</div></button>
          <button onclick="addBoardBlock('control')" class="w-full text-left"><div class="scratch-block control">🔀 ถ้า...แล้ว</div></button>
          <button onclick="addBoardBlock('sound')" class="w-full text-left"><div class="scratch-block sound">🔊 เล่นเสียง Meow</div></button>
        </div>
        <div class="mt-5 grid gap-2">
          <button onclick="loadExample('right','boardWorkspace')" class="bg-emerald-100 hover:bg-emerald-200 rounded-xl p-3 font-semibold text-left">➡️ ตัวอย่าง: ขวา 10 ก้าว</button>
          <button onclick="loadExample('left','boardWorkspace')" class="bg-emerald-100 hover:bg-emerald-200 rounded-xl p-3 font-semibold text-left">⬅️ ตัวอย่าง: ซ้าย 10 ก้าว</button>
          <button onclick="loadExample('up','boardWorkspace')" class="bg-emerald-100 hover:bg-emerald-200 rounded-xl p-3 font-semibold text-left">⬆️ ตัวอย่าง: ขึ้น 10 ก้าว</button>
        </div>
      </aside>
      <div class="flex-1 glass rounded-3xl p-3 flex flex-col">
        <div class="flex justify-between items-center mb-2">
          <h2 class="font-extrabold text-xl text-emerald-700">Workspace — ลากวางได้</h2>
          <button onclick="clearBoard('boardWorkspace')" class="bg-rose-100 hover:bg-rose-200 text-rose-600 rounded-xl px-4 py-2 font-bold"><i class="fa-solid fa-trash"></i> ล้างกระดาน</button>
        </div>
        <div id="boardWorkspace" class="workspace flex-1 rounded-2xl border-2 border-dashed border-emerald-200 overflow-hidden relative"></div>
      </div>
    </section>

    <!-- QUIZ -->
    <section id="quizView" class="view items-center justify-center">
      <div class="glass rounded-3xl p-6 w-full max-w-4xl h-full overflow-y-auto">
        <div class="text-center mb-6">
          <div class="text-5xl mb-2">🧠✨</div>
          <h2 class="text-3xl font-extrabold text-violet-700">แบบฝึกหัดทบทวน</h2>
          <p class="text-slate-500">ตอบคำถาม 5 ข้อ คะแนนเต็ม 100 คะแนน</p>
        </div>
        <div id="quizContainer" class="space-y-4"></div>
        <div class="flex justify-center mt-6">
          <button onclick="submitQuiz()" class="bg-violet-500 hover:bg-violet-600 text-white rounded-2xl px-7 py-3 font-extrabold shadow-lg"><i class="fa-solid fa-paper-plane"></i> ส่งคำตอบ</button>
        </div>
      </div>
    </section>

    <!-- GAME -->
    <section id="gameView" class="view rounded-3xl glass relative">
      <video id="gameVideo" autoplay playsinline></video>
      <canvas id="gameCanvas" class="absolute inset-0 w-full h-full pointer-events-none"></canvas>

      <div class="absolute z-20 top-4 left-4 right-4 flex items-start justify-between gap-4">
        <div class="glass rounded-2xl px-5 py-3 border border-white">
          <div class="text-xs font-bold text-amber-600">ภารกิจ AR</div>
          <div id="missionText" class="text-xl md:text-2xl font-extrabold text-slate-700">กด “เริ่มเกม” เพื่อล่าบล็อกคำสั่ง</div>
        </div>
        <div class="flex gap-2">
          <div class="glass rounded-2xl px-4 py-3 text-center">
            <div class="text-xs text-slate-500">คะแนน</div>
            <div id="gameScore" class="text-2xl font-extrabold text-amber-500">0</div>
          </div>
          <button id="startGameBtn" onclick="startGame()" class="bg-amber-400 hover:bg-amber-500 text-white rounded-2xl px-5 py-3 font-extrabold shadow-lg"><i class="fa-solid fa-play"></i> เริ่มเกม</button>
        </div>
      </div>

      <div class="absolute bottom-4 left-4 glass rounded-2xl p-3 text-sm z-20 max-w-md">
        <b>วิธีเล่น:</b> ใช้เมาส์คลิกบล็อกที่ตรงกับโจทย์ หรือใช้มือจีบนิ้วโป้งกับนิ้วชี้เพื่อ “คลิก” แบบ Magic Cursor ✨
      </div>
    </section>

    <!-- SCORE -->
    <section id="scoreView" class="view flex-col gap-3 overflow-y-auto">
      <div class="grid md:grid-cols-4 gap-3">
        <div class="glass rounded-2xl p-4 text-center"><div class="text-sm text-slate-500">ใบงาน</div><div id="scoreWorksheet" class="text-3xl font-extrabold text-pink-600">0</div><div class="text-xs">/100</div></div>
        <div class="glass rounded-2xl p-4 text-center"><div class="text-sm text-slate-500">แบบฝึกหัด</div><div id="scoreQuiz" class="text-3xl font-extrabold text-violet-600">0</div><div class="text-xs">/100</div></div>
        <div class="glass rounded-2xl p-4 text-center"><div class="text-sm text-slate-500">เกม AR</div><div id="scoreGame" class="text-3xl font-extrabold text-amber-500">0</div><div class="text-xs">/100</div></div>
        <div class="glass rounded-2xl p-4 text-center"><div class="text-sm text-slate-500">คะแนนเฉลี่ยรวม</div><div id="scoreTotal" class="text-3xl font-extrabold text-emerald-600">0</div><div class="text-xs">/100</div></div>
      </div>

      <div class="glass rounded-3xl p-4 flex-1 min-h-[560px]">
        <div class="flex justify-between items-center mb-3">
          <h2 class="font-extrabold text-xl text-pink-700">เกียรติบัตรผลการเรียน</h2>
          <button onclick="window.print()" class="bg-pink-500 hover:bg-pink-600 text-white rounded-xl px-5 py-2 font-bold"><i class="fa-solid fa-print"></i> พิมพ์ส่งครู (A4 แนวนอน)</button>
        </div>

        <div id="printArea" class="flex justify-center items-center">
          <div class="certificate p-12 flex flex-col items-center text-center justify-between">
            <div>
              <div class="text-5xl">🏅</div>
              <h3 class="text-4xl md:text-5xl font-extrabold text-pink-600 mt-2">เกียรติบัตรแห่งความสำเร็จ</h3>
              <div class="text-lg text-slate-500 mt-1">Scratch • Computational Thinking • AR Learning</div>
            </div>
            <div class="w-full">
              <p class="text-lg">ขอมอบเกียรติบัตรฉบับนี้ให้แก่</p>
              <div id="certName" class="text-3xl md:text-4xl font-extrabold text-sky-700 border-b-2 border-sky-200 inline-block min-w-[420px] pb-1">นักเรียนคนเก่ง</div>
              <div class="mt-3 text-lg">ชั้น <span id="certClass" class="font-bold">-</span> เลขที่ <span id="certNo" class="font-bold">-</span></div>
              <p class="mt-3 text-lg">ผ่านกิจกรรม “เรียนรู้บล็อกคำสั่ง Scratch - ห้องเรียนครูดีน่า (AR Game Edition)”</p>
              <p class="mt-1">ด้วยคะแนนเฉลี่ยรวม <span id="certScore" class="font-extrabold text-2xl text-emerald-600">0</span> / 100 คะแนน</p>
            </div>
            <div class="w-full flex items-end justify-between">
              <div class="text-left">
                <div class="border-t border-slate-400 pt-2 px-8 text-center">
                  <div class="font-bold">คุณครูยุภาวดี พรมสาร</div>
                  <div class="text-sm">ผู้สอนวิชาวิทยาการคำนวณ</div>
                </div>
              </div>
              <div class="stamp">AR<br>SYSTEM<br>★</div>
              <div class="text-right text-sm text-slate-500">
                ห้องเรียนครูดีน่า<br>Learning by Playing
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</div>

<div id="magicCursor">★</div>

<!-- Worksheet Modal -->
<div id="worksheetModal" class="hidden fixed inset-0 z-[100] modal-backdrop p-4">
  <div class="bg-white/95 max-w-6xl mx-auto h-full rounded-3xl shadow-2xl flex flex-col overflow-hidden">
    <div class="p-4 bg-gradient-to-r from-pink-100 to-sky-100 border-b flex items-center justify-between gap-3">
      <div>
        <h2 class="text-2xl font-extrabold text-pink-700"><i class="fa-solid fa-book-open-reader"></i> สมุดใบงาน Scratch</h2>
        <p class="text-sm text-slate-500">ใบงาน 3.1 - 3.8 พร้อมตรวจคะแนนอัตโนมัติ</p>
      </div>
      <button onclick="closeWorksheet()" class="w-10 h-10 rounded-full bg-white text-slate-500 hover:text-rose-500 shadow"><i class="fa-solid fa-xmark text-xl"></i></button>
    </div>

    <div class="p-3 bg-white border-b grid md:grid-cols-3 gap-2">
      <input id="studentName" class="border-2 border-pink-100 rounded-xl px-3 py-2 outline-none focus:border-pink-300" placeholder="ชื่อ-นามสกุล">
      <input id="studentClass" class="border-2 border-sky-100 rounded-xl px-3 py-2 outline-none focus:border-sky-300" placeholder="ชั้น เช่น ป.4">
      <input id="studentNo" class="border-2 border-amber-100 rounded-xl px-3 py-2 outline-none focus:border-amber-300" placeholder="เลขที่">
    </div>

    <div class="px-3 py-2 flex gap-2 overflow-x-auto bg-slate-50 border-b">
      <button class="tab-btn active shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(1,this)">ใบงาน 3.1</button>
      <button class="tab-btn shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(2,this)">ใบงาน 3.2</button>
      <button class="tab-btn shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(3,this)">ใบงาน 3.3</button>
      <button class="tab-btn shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(4,this)">ใบงาน 3.4</button>
      <button class="tab-btn shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(5,this)">ใบงาน 3.5</button>
      <button class="tab-btn shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(6,this)">ใบงาน 3.6</button>
      <button class="tab-btn shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(7,this)">ใบงาน 3.7</button>
      <button class="tab-btn shrink-0 px-4 py-2 rounded-xl font-bold" onclick="showSheet(8,this)">ใบงาน 3.8</button>
    </div>

    <div id="sheetContent" class="flex-1 overflow-y-auto p-5"></div>

    <div class="p-3 border-t flex justify-between items-center bg-white">
      <div class="text-sm text-slate-500">ระบบจะคำนวณคะแนนใบงานจากคำตอบที่ทำไว้</div>
      <button onclick="submitWorksheets()" class="bg-pink-500 hover:bg-pink-600 text-white rounded-xl px-6 py-3 font-extrabold"><i class="fa-solid fa-check-double"></i> ส่งงานตรวจคะแนนอัตโนมัติ</button>
    </div>
  </div>
</div>

<script>
const state = {
  worksheetScore: Number(localStorage.getItem('scratch_ws') || 0),
  quizScore: Number(localStorage.getItem('scratch_quiz') || 0),
  gameScore: Number(localStorage.getItem('scratch_game') || 0),
  gameRunning:false,
  gameRound:0,
  gameCorrect:0,
  targetType:null,
  stream:null,
  pinchDown:false,
  currentSheet:1
};

const blockMeta = {
  event:{label:'เมื่อคลิกธงเขียว', cls:'event hat-block', icon:'🚩'},
  motion:{label:'เคลื่อนที่ 10 ก้าว', cls:'motion', icon:'↔️'},
  looks:{label:'พูด “สวัสดี!”', cls:'looks', icon:'💬'},
  control:{label:'ถ้า...แล้ว', cls:'control', icon:'🔀'},
  sound:{label:'เล่นเสียง “Meow”', cls:'sound', icon:'🔊'}
};

function switchView(name){
  document.querySelectorAll('.view').forEach(v=>v.classList.remove('active'));
  document.getElementById(name+'View').classList.add('active');
  document.querySelectorAll('[data-view]').forEach(b=>b.classList.toggle('active', b.dataset.view===name));
  if(name==='score') updateScores();
  if(name!=='game') state.gameRunning=false;
}
document.querySelectorAll('[data-view]').forEach(b=>b.addEventListener('click',()=>switchView(b.dataset.view)));

function makeBlock(type,text){
  const d=document.createElement('div');
  d.className='scratch-block '+blockMeta[type].cls;
  d.dataset.type=type;
  d.innerHTML=`${blockMeta[type].icon} <span contenteditable="true">${text || blockMeta[type].label}</span>`;
  return d;
}

function clearBoard(id){
  document.getElementById(id).innerHTML='';
}
function loadExample(kind,target='learnWorkspace'){
  const ws=document.getElementById(target);
  ws.innerHTML='';
  const configs={
    right:['เมื่อคลิกธงเขียว','เคลื่อนที่ 10 ก้าว ไปทางขวา','พูด “ฉันเดินไปทางขวาแล้ว!”'],
    left:['เมื่อคลิกธงเขียว','เคลื่อนที่ -10 ก้าว ไปทางซ้าย','พูด “ฉันเดินไปทางซ้ายแล้ว!”'],
    up:['เมื่อคลิกธงเขียว','เปลี่ยนค่า y ทีละ 10','พูด “ฉันเดินขึ้นด้านบนแล้ว!”']
  };
  const types=['event','motion','looks'];
  configs[kind].forEach((txt,i)=>{
    const wrap=document.createElement('div');
    wrap.className='draggable';
    wrap.style.left='80px';
    wrap.style.top=(70+i*76)+'px';
    wrap.appendChild(makeBlock(types[i],txt));
    ws.appendChild(wrap);
    enableDrag(wrap,ws);
  });
}
function addBoardBlock(type){
  const ws=document.getElementById('boardWorkspace');
  const wrap=document.createElement('div');
  wrap.className='draggable';
  wrap.style.left=(40+Math.random()*180)+'px';
  wrap.style.top=(40+Math.random()*220)+'px';
  wrap.appendChild(makeBlock(type));
  ws.appendChild(wrap);
  enableDrag(wrap,ws);
}
function enableDrag(el,container){
  let drag=false,ox=0,oy=0;
  el.addEventListener('pointerdown',e=>{
    if(e.target.getAttribute('contenteditable')==='true') return;
    drag=true;el.setPointerCapture(e.pointerId);
    const r=el.getBoundingClientRect(); ox=e.clientX-r.left; oy=e.clientY-r.top;
  });
  el.addEventListener('pointermove',e=>{
    if(!drag)return;
    const cr=container.getBoundingClientRect();
    let x=e.clientX-cr.left-ox, y=e.clientY-cr.top-oy;
    x=Math.max(0,Math.min(x,cr.width-el.offsetWidth));
    y=Math.max(0,Math.min(y,cr.height-el.offsetHeight));
    el.style.left=x+'px'; el.style.top=y+'px';
  });
  el.addEventListener('pointerup',()=>drag=false);
}

/* Worksheets */
document.getElementById('worksheetBtn').addEventListener('click',()=>{
  document.getElementById('worksheetModal').classList.remove('hidden');
  renderSheet(1);
});
function closeWorksheet(){document.getElementById('worksheetModal').classList.add('hidden')}
function showSheet(n,btn){
  state.currentSheet=n;
  document.querySelectorAll('.tab-btn').forEach(x=>x.classList.remove('active'));
  btn.classList.add('active');
  renderSheet(n);
}
const wsAnswers={m:{},tf:{},seq:{},misc:{}};

function renderSheet(n){
  const c=document.getElementById('sheetContent');
  if(n===1){
    c.innerHTML=`
      <h3 class="text-xl font-extrabold text-pink-700 mb-2">ใบงาน 3.1 : จับคู่บล็อกคำสั่ง</h3>
      <p class="mb-4 text-slate-500">คลิกตัวอักษรคำตอบที่ถูกต้องเพื่อเติมลงในช่องว่าง</p>
      <div class="flex flex-wrap gap-2 mb-5">
        <button class="option-chip" onclick="pickLetter('A')">A. เริ่มต้นโปรแกรม</button>
        <button class="option-chip" onclick="pickLetter('B')">B. เคลื่อนที่</button>
        <button class="option-chip" onclick="pickLetter('C')">C. พูดข้อความ</button>
        <button class="option-chip" onclick="pickLetter('D')">D. ตรวจสอบเงื่อนไข</button>
        <button class="option-chip" onclick="pickLetter('E')">E. เล่นเสียง</button>
      </div>
      <div class="grid md:grid-cols-2 gap-4">
        ${matchRow(1,'event','เมื่อคลิกธงเขียว')}
        ${matchRow(2,'motion','เคลื่อนที่ 10 ก้าว')}
        ${matchRow(3,'looks','พูด “สวัสดี!”')}
        ${matchRow(4,'control','ถ้า...แล้ว')}
        ${matchRow(5,'sound','เล่นเสียง “Meow”')}
      </div>`;
  } else if(n===2){
    c.innerHTML=`
      <h3 class="text-xl font-extrabold text-sky-700 mb-2">ใบงาน 3.2 : ประโยชน์ของบล็อกคำสั่ง</h3>
      <p class="text-slate-500 mb-4">อ่านข้อความ แล้วเลือก ✓ ถูก หรือ ✗ ผิด</p>
      <div class="space-y-3">
        ${tfRow(1,'บล็อกเมื่อคลิกธงเขียวใช้เริ่มการทำงานของโปรแกรม')}
        ${tfRow(2,'บล็อกเคลื่อนที่ใช้สำหรับเล่นเสียงเพลงเท่านั้น')}
        ${tfRow(3,'บล็อกพูดทำให้ตัวละครแสดงข้อความ')}
        ${tfRow(4,'บล็อกถ้า...แล้ว ใช้ตรวจสอบเงื่อนไข')}
        ${tfRow(5,'บล็อกเสียงไม่มีความเกี่ยวข้องกับเสียงในโปรเจกต์ Scratch')}
      </div>`;
  } else if(n===3){
    c.innerHTML=`
      <h3 class="text-xl font-extrabold text-amber-700 mb-2">ใบงาน 3.3 : เขียนโปรแกรมต่อบล็อกคำสั่ง</h3>
      <p class="text-slate-500 mb-4">โจทย์: ให้ตัวละครเริ่มจากธงเขียว → เดิน 10 ก้าว → พูด “สวัสดี!” → เล่นเสียง</p>
      <div class="flex flex-wrap gap-2 mb-5">
        ${[1,2,3,4].map(x=>`<button class="option-chip" onclick="pickNumber(${x})">${x}</button>`).join('')}
      </div>
      <div class="space-y-3">
        ${seqRow('event','เมื่อคลิกธงเขียว',1)}
        ${seqRow('motion','เคลื่อนที่ 10 ก้าว',2)}
        ${seqRow('looks','พูด “สวัสดี!”',3)}
        ${seqRow('sound','เล่นเสียง “Meow”',4)}
      </div>`;
  } else {
    const titles={
      4:'แยกประเภทบล็อก',5:'อ่านโค้ด Scratch',6:'คิดเป็นลำดับขั้นตอน',7:'แก้ไขข้อผิดพลาด',8:'ภารกิจสร้างสรรค์'
    };
    c.innerHTML=`
      <h3 class="text-xl font-extrabold text-emerald-700 mb-2">ใบงาน 3.${n} : ${titles[n]}</h3>
      <div class="bg-emerald-50 border-2 border-emerald-100 rounded-2xl p-5">
        <p class="font-bold mb-3">กิจกรรมเสริม</p>
        <p class="text-slate-600 mb-4">${worksheetExtraText(n)}</p>
        <textarea id="extra${n}" class="w-full h-40 border-2 border-emerald-100 rounded-2xl p-4 outline-none focus:border-emerald-300" placeholder="พิมพ์คำตอบของนักเรียนที่นี่...">${wsAnswers.misc[n]||''}</textarea>
        <button onclick="saveExtra(${n})" class="mt-3 bg-emerald-500 text-white rounded-xl px-4 py-2 font-bold">บันทึกคำตอบ</button>
      </div>`;
  }
}
let selectedLetter=null,selectedNumber=null;
function matchRow(i,type,label){
  const val=wsAnswers.m[i]||'';
  return `<div class="bg-slate-50 rounded-2xl p-4 flex items-center gap-3 border">
    <div class="scratch-block ${blockMeta[type].cls} scale-90 origin-left">${blockMeta[type].icon} ${label}</div>
    <div id="m${i}" onclick="assignLetter(${i})" class="drop-answer font-extrabold text-pink-600">${val}</div>
  </div>`;
}
function pickLetter(x){selectedLetter=x; Swal.fire({toast:true,position:'top-end',icon:'info',title:'เลือก '+x+' แล้ว คลิกช่องว่างที่ต้องการ',showConfirmButton:false,timer:1000})}
function assignLetter(i){if(selectedLetter){wsAnswers.m[i]=selectedLetter;document.getElementById('m'+i).textContent=selectedLetter}}
function tfRow(i,text){
  return `<div class="bg-slate-50 rounded-2xl p-4 flex items-center justify-between gap-3">
    <span class="font-semibold">${i}. ${text}</span>
    <div class="flex gap-2">
      <button onclick="setTF(${i},true,this)" class="tf-btn w-11 h-11 rounded-xl bg-green-500 text-white font-extrabold">✓</button>
      <button onclick="setTF(${i},false,this)" class="tf-btn w-11 h-11 rounded-xl bg-red-500 text-white font-extrabold">✗</button>
    </div>
  </div>`;
}
function setTF(i,v,btn){
  wsAnswers.tf[i]=v;
  btn.parentElement.querySelectorAll('button').forEach(b=>b.classList.remove('selected'));
  btn.classList.add('selected');
}
function seqRow(type,label,i){
  return `<div class="flex items-center gap-3 bg-slate-50 rounded-2xl p-3">
    <div id="s${i}" onclick="assignNumber(${i})" class="drop-answer font-extrabold text-amber-600">${wsAnswers.seq[i]||''}</div>
    <div class="scratch-block ${blockMeta[type].cls}">${blockMeta[type].icon} ${label}</div>
  </div>`;
}
function pickNumber(x){selectedNumber=x}
function assignNumber(i){if(selectedNumber){wsAnswers.seq[i]=selectedNumber;document.getElementById('s'+i).textContent=selectedNumber}}
function worksheetExtraText(n){
  return ({
    4:'ยกตัวอย่างบล็อกคำสั่งอย่างน้อย 3 หมวด พร้อมอธิบายหน้าที่สั้น ๆ',
    5:'อธิบายผลลัพธ์ที่เกิดขึ้นเมื่อต่อบล็อก “เมื่อคลิกธงเขียว → เคลื่อนที่ 10 ก้าว → พูด สวัสดี”',
    6:'เขียนลำดับขั้นตอน 4 ขั้น เพื่อให้ตัวละครเดินและพูดทักทาย',
    7:'ถ้าตัวละครเดินผิดทิศทาง นักเรียนจะแก้ไขบล็อกใด และแก้อย่างไร',
    8:'ออกแบบโปรแกรม Scratch สั้น ๆ ที่มีอย่างน้อย 4 บล็อก และอธิบายสิ่งที่โปรแกรมทำ'
  })[n]
}
function saveExtra(n){
  wsAnswers.misc[n]=document.getElementById('extra'+n).value.trim();
  Swal.fire({icon:'success',title:'บันทึกแล้ว',timer:900,showConfirmButton:false});
}
function submitWorksheets(){
  const keyM={1:'A',2:'B',3:'C',4:'D',5:'E'};
  const keyTF={1:true,2:false,3:true,4:true,5:false};
  const keySeq={1:1,2:2,3:3,4:4};
  let correct=0,total=14;
  Object.keys(keyM).forEach(k=>{if(wsAnswers.m[k]===keyM[k])correct++});
  Object.keys(keyTF).forEach(k=>{if(wsAnswers.tf[k]===keyTF[k])correct++});
  Object.keys(keySeq).forEach(k=>{if(Number(wsAnswers.seq[k])===keySeq[k])correct++});
  // bonus 1 point each for sheets 4-8 with any substantive answer, folded into 100 score
  let bonus=0;
  for(let i=4;i<=8;i++) if((wsAnswers.misc[i]||'').length>=8) bonus++;
  const score=Math.min(100,Math.round((correct/total)*85 + bonus*3));
  state.worksheetScore=score;
  localStorage.setItem('scratch_ws',score);
  syncStudent();
  Swal.fire({icon:'success',title:'ตรวจใบงานเรียบร้อย 🎉',html:`ได้คะแนน <b>${score}/100</b><br>คำตอบหลักถูก ${correct}/${total} ข้อ`,confirmButtonText:'เยี่ยมเลย!'});
}

/* Quiz */
const quizData=[
  {q:'บล็อกใดใช้เริ่มโปรแกรมเมื่อกดธงเขียว?',opts:['เสียง','เหตุการณ์','รูปลักษณ์','ตัวแปร'],a:1},
  {q:'ถ้าต้องการให้ตัวละครเดิน ควรใช้บล็อกหมวดใด?',opts:['เคลื่อนที่','เสียง','สัมผัส','ปากกา'],a:0},
  {q:'บล็อก “พูด … 2 วินาที” มีหน้าที่อะไร?',opts:['ให้ตัวละครเดิน','ให้ตัวละครพูด','เล่นเสียง','หยุดโปรแกรม'],a:1},
  {q:'บล็อก “ถ้า...แล้ว” ใช้เพื่ออะไร?',opts:['ตรวจสอบเงื่อนไข','เปลี่ยนฉากเสมอ','บันทึกเสียง','วาดรูปอย่างเดียว'],a:0},
  {q:'บล็อก “เล่นเสียง Meow” อยู่ในหมวดใด?',opts:['เหตุการณ์','เสียง','เคลื่อนที่','ควบคุม'],a:1}
];
function renderQuiz(){
  const c=document.getElementById('quizContainer');
  c.innerHTML=quizData.map((x,i)=>`
    <div class="bg-white/80 rounded-2xl p-4 border-2 border-violet-100">
      <div class="font-extrabold mb-3">${i+1}. ${x.q}</div>
      <div class="grid md:grid-cols-2 gap-2">
        ${x.opts.map((o,j)=>`<label class="cursor-pointer bg-violet-50 hover:bg-violet-100 rounded-xl p-3"><input type="radio" name="q${i}" value="${j}" class="mr-2"> ${o}</label>`).join('')}
      </div>
    </div>`).join('');
}
function submitQuiz(){
  let correct=0;
  quizData.forEach((x,i)=>{
    const el=document.querySelector(`input[name="q${i}"]:checked`);
    if(el && Number(el.value)===x.a) correct++;
  });
  const score=correct*20;
  state.quizScore=score; localStorage.setItem('scratch_quiz',score);
  Swal.fire({icon:score>=60?'success':'info',title:'ผลแบบฝึกหัด',html:`ถูก ${correct}/5 ข้อ<br><b>${score}/100 คะแนน</b>`});
}
renderQuiz();

/* Game */
async function setupCamera(){
  const video=document.getElementById('gameVideo');
  const status=document.getElementById('cameraStatus');
  if(!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia){
    cameraFallback('อุปกรณ์นี้ไม่รองรับกล้อง');
    return false;
  }
  try{
    state.stream=await navigator.mediaDevices.getUserMedia({video:{facingMode:'user'},audio:false});
    video.srcObject=state.stream; video.style.display='block';
    status.innerHTML='<i class="fa-solid fa-video text-green-500"></i>';
    status.className='w-10 h-10 rounded-xl bg-green-100 flex items-center justify-center';
    await initHands(video);
    Swal.fire({toast:true,position:'top-end',icon:'success',title:'เชื่อมต่อกล้องสำเร็จ! ✨',showConfirmButton:false,timer:1500});
    return true;
  }catch(err){
    cameraFallback('ไม่สามารถเปิดกล้องได้ ใช้เมาส์เล่นแทนได้ตามปกติ');
    return false;
  }
}
function cameraFallback(msg){
  document.getElementById('gameVideo').style.display='none';
  const status=document.getElementById('cameraStatus');
  status.innerHTML='<i class="fa-solid fa-computer-mouse text-sky-500"></i>';
  status.className='w-10 h-10 rounded-xl bg-sky-100 flex items-center justify-center';
  Swal.fire({toast:true,position:'top-end',icon:'info',title:msg,showConfirmButton:false,timer:1800});
}
async function initHands(video){
  if(typeof Hands==='undefined') return;
  const hands=new Hands({locateFile:(file)=>`https://cdn.jsdelivr.net/npm/@mediapipe/hands/${file}`});
  hands.setOptions({maxNumHands:1,modelComplexity:0,minDetectionConfidence:.55,minTrackingConfidence:.55});
  hands.onResults(onHandResults);
  const camera=new Camera(video,{
    onFrame:async()=>{if(state.gameRunning) await hands.send({image:video})},
    width:960,height:540
  });
  camera.start();
}
function onHandResults(results){
  const cursor=document.getElementById('magicCursor');
  if(!results.multiHandLandmarks || !results.multiHandLandmarks.length){cursor.style.display='none';return}
  const lm=results.multiHandLandmarks[0];
  const thumb=lm[4], index=lm[8];
  const x=(1-index.x)*window.innerWidth, y=index.y*window.innerHeight;
  cursor.style.display='block';cursor.style.left=x+'px';cursor.style.top=y+'px';
  const d=Math.hypot(thumb.x-index.x,thumb.y-index.y);
  if(d<.045 && !state.pinchDown){
    state.pinchDown=true;
    cursor.style.transform='translate(-50%,-50%) scale(1.35)';
    const el=document.elementFromPoint(x,y);
    if(el){
      const target=el.closest('.floating-block');
      if(target) target.click();
    }
  } else if(d>.07){
    state.pinchDown=false; cursor.style.transform='translate(-50%,-50%) scale(1)';
  }
}
async function startGame(){
  state.gameRunning=true;state.gameRound=0;state.gameCorrect=0;state.gameScore=0;
  document.getElementById('gameScore').textContent='0';
  document.querySelectorAll('.floating-block').forEach(x=>x.remove());
  setupCamera();
  nextMission();
}
function nextMission(){
  if(!state.gameRunning)return;
  if(state.gameRound>=10){endGame();return}
  state.gameRound++;
  const types=Object.keys(blockMeta);
  state.targetType=types[Math.floor(Math.random()*types.length)];
  document.getElementById('missionText').innerHTML=`ภารกิจ ${state.gameRound}/10: จับบล็อก “<span class="text-amber-600">${blockMeta[state.targetType].label}</span>”`;
  spawnFive();
}
function spawnFive(){
  document.querySelectorAll('.floating-block').forEach(x=>x.remove());
  const game=document.getElementById('gameView');
  const types=Object.keys(blockMeta);
  let pool=[state.targetType];
  while(pool.length<5) pool.push(types[Math.floor(Math.random()*types.length)]);
  pool.sort(()=>Math.random()-.5);
  pool.forEach((type,i)=>{
    const wrap=document.createElement('div');
    wrap.className='floating-block';
    wrap.dataset.type=type;
    wrap.style.left=(8+i*18)+'%';
    wrap.style.animationDuration=(6+Math.random()*2)+'s';
    wrap.style.animationDelay=(Math.random()*.5)+'s';
    wrap.innerHTML=`<div class="scratch-block ${blockMeta[type].cls} scale-90 md:scale-100">${blockMeta[type].icon} ${blockMeta[type].label}</div>`;
    wrap.onclick=()=>hitBlock(wrap);
    wrap.addEventListener('animationend',()=>{if(state.gameRunning && document.body.contains(wrap)){wrap.remove(); if(!document.querySelector('.floating-block')) setTimeout(nextMission,250)}});
    game.appendChild(wrap);
  });
}
function hitBlock(el){
  if(!state.gameRunning)return;
  if(el.dataset.type===state.targetType){
    state.gameCorrect++;
    state.gameScore=state.gameCorrect*10;
    document.getElementById('gameScore').textContent=state.gameScore;
    el.classList.add('pop');
    showerStars();
    applause();
    setTimeout(nextMission,520);
  }else{
    el.classList.add('shake');
    setTimeout(()=>el.classList.remove('shake'),400);
  }
}
function showerStars(){
  for(let i=0;i<18;i++){
    const s=document.createElement('div');
    s.className='starfall';s.textContent=['⭐','✨','🌟'][Math.floor(Math.random()*3)];
    s.style.left=Math.random()*100+'vw';s.style.animationDelay=(Math.random()*.25)+'s';
    document.body.appendChild(s);setTimeout(()=>s.remove(),1800);
  }
}
function applause(){
  try{
    const ctx=new (window.AudioContext||window.webkitAudioContext)();
    [0, .08, .16, .24].forEach((t,i)=>{
      const o=ctx.createOscillator(),g=ctx.createGain();
      o.type='triangle';o.frequency.value=440+i*70;
      g.gain.setValueAtTime(.0001,ctx.currentTime+t);
      g.gain.exponentialRampToValueAtTime(.08,ctx.currentTime+t+.01);
      g.gain.exponentialRampToValueAtTime(.0001,ctx.currentTime+t+.12);
      o.connect(g);g.connect(ctx.destination);o.start(ctx.currentTime+t);o.stop(ctx.currentTime+t+.14);
    });
  }catch(e){}
}
function endGame(){
  state.gameRunning=false;
  document.querySelectorAll('.floating-block').forEach(x=>x.remove());
  state.gameScore=state.gameCorrect*10;
  localStorage.setItem('scratch_game',state.gameScore);
  Swal.fire({icon:'success',title:'จบเกมแล้ว! 🌟',html:`จับถูก ${state.gameCorrect}/10 ภารกิจ<br><b>${state.gameScore}/100 คะแนน</b>`,confirmButtonText:'ดูคะแนน'}).then(()=>switchView('score'));
}

/* Scores / certificate */
function syncStudent(){
  const n=document.getElementById('studentName').value.trim()||'นักเรียนคนเก่ง';
  const c=document.getElementById('studentClass').value.trim()||'-';
  const no=document.getElementById('studentNo').value.trim()||'-';
  localStorage.setItem('scratch_name',n);localStorage.setItem('scratch_class',c);localStorage.setItem('scratch_no',no);
  document.getElementById('certName').textContent=n;
  document.getElementById('certClass').textContent=c;
  document.getElementById('certNo').textContent=no;
}
function updateScores(){
  state.worksheetScore=Number(localStorage.getItem('scratch_ws')||state.worksheetScore||0);
  state.quizScore=Number(localStorage.getItem('scratch_quiz')||state.quizScore||0);
  state.gameScore=Number(localStorage.getItem('scratch_game')||state.gameScore||0);
  const total=Math.round((state.worksheetScore+state.quizScore+state.gameScore)/3);
  document.getElementById('scoreWorksheet').textContent=state.worksheetScore;
  document.getElementById('scoreQuiz').textContent=state.quizScore;
  document.getElementById('scoreGame').textContent=state.gameScore;
  document.getElementById('scoreTotal').textContent=total;
  document.getElementById('certScore').textContent=total;
  document.getElementById('certName').textContent=localStorage.getItem('scratch_name')||'นักเรียนคนเก่ง';
  document.getElementById('certClass').textContent=localStorage.getItem('scratch_class')||'-';
  document.getElementById('certNo').textContent=localStorage.getItem('scratch_no')||'-';
}
['studentName','studentClass','studentNo'].forEach(id=>{
  document.getElementById(id).addEventListener('input',syncStudent);
});
document.getElementById('studentName').value=localStorage.getItem('scratch_name')||'';
document.getElementById('studentClass').value=localStorage.getItem('scratch_class')||'';
document.getElementById('studentNo').value=localStorage.getItem('scratch_no')||'';
updateScores();
loadExample('right');
</script>
</body>
</html>
