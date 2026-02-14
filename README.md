<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Valentine’s 💘</title>
  <style>
    :root{
      --bg1:#ffdde1;
      --bg2:#ee9ca7;
      --card:#ffffffcc;
      --text:#2b2b2b;
      --accent:#ff2d55;
      --accent2:#b5179e;
      --shadow: 0 20px 60px rgba(0,0,0,.15);
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      min-height:100vh;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
      color:var(--text);
      background: radial-gradient(1200px 800px at 20% 10%, #fff7f9 0%, transparent 60%),
                  radial-gradient(1000px 700px at 80% 20%, #ffe5f0 0%, transparent 60%),
                  linear-gradient(135deg, var(--bg1), var(--bg2));
      overflow-x:hidden;
    }

    /* Floating hearts */
    .hearts{position:fixed; inset:0; pointer-events:none; overflow:hidden;}
    .heart{
      position:absolute;
      width:14px; height:14px;
      background:var(--accent);
      transform:rotate(45deg);
      opacity:.6;
      filter: drop-shadow(0 6px 10px rgba(255,45,85,.35));
      animation: floatUp linear infinite;
    }
    .heart:before, .heart:after{
      content:"";
      position:absolute;
      width:14px; height:14px;
      background:inherit;
      border-radius:50%;
    }
    .heart:before{left:-7px; top:0;}
    .heart:after{left:0; top:-7px;}
    @keyframes floatUp{
      0%{transform:translateY(110vh) rotate(45deg) scale(var(--s)); opacity:0;}
      10%{opacity:.7;}
      100%{transform:translateY(-20vh) rotate(45deg) scale(var(--s)); opacity:0;}
    }

    /* Confetti hearts (simple) */
    .burst{position:fixed; inset:0; pointer-events:none; overflow:hidden;}
    .spark{
      position:absolute;
      width:10px; height:10px;
      background:var(--accent);
      transform:rotate(45deg);
      opacity:0;
      animation: pop 900ms ease forwards;
    }
    .spark:before, .spark:after{
      content:"";
      position:absolute;
      width:10px; height:10px;
      background:inherit;
      border-radius:50%;
    }
    .spark:before{left:-5px; top:0;}
    .spark:after{left:0; top:-5px;}
    @keyframes pop{
      0%{transform:translate(0,0) rotate(45deg) scale(.6); opacity:0;}
      10%{opacity:.95;}
      100%{transform:translate(var(--dx), var(--dy)) rotate(45deg) scale(1); opacity:0;}
    }

    .wrap{
      max-width: 980px;
      margin: 0 auto;
      padding: 56px 20px 80px;
      display:grid;
      gap:22px;
      grid-template-columns: 1.15fr .85fr;
      align-items:start;
    }
    @media (max-width: 880px){
      .wrap{grid-template-columns:1fr; padding-top:38px;}
    }

    .card{
      background:var(--card);
      backdrop-filter: blur(10px);
      border:1px solid rgba(255,255,255,.55);
      border-radius: 24px;
      box-shadow: var(--shadow);
      padding: 26px;
    }

    .headline{display:flex; gap:14px; align-items:center; margin-bottom: 10px;}
    .badge{
      width:44px; height:44px;
      border-radius: 14px;
      display:grid;
      place-items:center;
      background: linear-gradient(135deg, #ff2d55, #b5179e);
      color:white;
      font-size: 22px;
      box-shadow: 0 16px 35px rgba(181,23,158,.25);
      flex: 0 0 auto;
    }
    h1{font-size: clamp(28px, 4vw, 44px); margin:0; letter-spacing:-.02em;}
    .sub{margin: 8px 0 0; opacity:.85; line-height:1.6}

    .ctaRow{display:flex; gap:12px; flex-wrap:wrap; margin-top:18px;}
    button{
      appearance:none;
      border:0;
      padding: 12px 16px;
      border-radius: 14px;
      font-weight: 800;
      cursor:pointer;
      transition: transform .12s ease, box-shadow .12s ease, filter .12s ease;
    }
    .primary{
      background: linear-gradient(135deg, #ff2d55, #ff6b6b);
      color:white;
      box-shadow: 0 18px 40px rgba(255,45,85,.32);
    }
    .secondary{
      background: rgba(255,255,255,.65);
      border:1px solid rgba(0,0,0,.08);
      color:#222;
    }
    button:hover{transform: translateY(-1px); filter:saturate(1.08)}
    button:active{transform: translateY(0px); filter:saturate(1)}

    .note{margin-top:18px; display:grid; gap:10px;}
    label{font-size:13px; opacity:.8; font-weight:800;}
    input, textarea{
      width:100%;
      padding: 12px 14px;
      border-radius: 14px;
      border:1px solid rgba(0,0,0,.10);
      background: rgba(255,255,255,.70);
      outline:none;
      font-size:14px;
    }
    textarea{min-height: 110px; resize: vertical;}

    .preview{position: sticky; top: 18px;}
    @media (max-width: 880px){.preview{position:static;}}

    .postcard{
      border-radius: 22px;
      padding: 22px;
      background: radial-gradient(1200px 500px at 20% 10%, rgba(255,255,255,.9) 0%, rgba(255,255,255,.55) 45%, rgba(255,255,255,.35) 100%),
                  linear-gradient(135deg, rgba(255,255,255,.55), rgba(255,255,255,.18));
      border: 1px solid rgba(255,255,255,.55);
      box-shadow: 0 18px 55px rgba(0,0,0,.14);
      overflow:hidden;
    }
    .postcardTop{display:flex; align-items:center; justify-content:space-between; gap:12px;}
    .toFrom{font-weight:900; letter-spacing:-.01em;}
    .stamp{
      width: 54px; height: 54px;
      border-radius: 16px;
      background: linear-gradient(135deg, #b5179e, #ff2d55);
      display:grid; place-items:center;
      color:#fff; font-size:22px;
      transform: rotate(8deg);
      box-shadow: 0 14px 35px rgba(255,45,85,.25);
      flex: 0 0 auto;
    }
    .msg{margin: 16px 0 0; line-height:1.75; font-size: 15.5px; white-space: pre-wrap;}
    .sig{margin-top: 16px; font-weight: 900; color: var(--accent2);}

    .divider{height:1px; background: linear-gradient(90deg, transparent, rgba(0,0,0,.12), transparent); margin: 18px 0;}
    .tiny{font-size:12px; opacity:.78; line-height:1.5}

    /* Fullscreen overlays (Ask / Tree / Slideshow) */
    .overlay{position:fixed; inset:0; display:grid; place-items:center; padding:22px; z-index:50;}
    .overlayCard{width:min(760px, 100%); background:var(--card); backdrop-filter: blur(10px); border:1px solid rgba(255,255,255,.55); border-radius:24px; box-shadow:var(--shadow); padding:22px;}
    .overlayHeader{display:flex; gap:14px; align-items:center; margin-bottom:10px;}

    /* Ask */
    .askBtns{margin-top:18px; display:flex; gap:12px; align-items:center; justify-content:flex-start; min-height:74px;}

    /* Heart Tree */
    .treeStage{position:relative; height:360px; border-radius:20px; overflow:hidden;
      background: radial-gradient(700px 320px at 50% 15%, rgba(255,255,255,.85) 0%, rgba(255,255,255,.55) 45%, rgba(255,255,255,.25) 100%),
                  linear-gradient(135deg, rgba(255,255,255,.35), rgba(255,255,255,.08));
      border:1px solid rgba(255,255,255,.55);
      box-shadow: 0 18px 55px rgba(0,0,0,.12);
    }
    .tree{position:absolute; inset:0; width:100%; height:100%;}
    .leafLayer, .rainLayer{position:absolute; inset:0; pointer-events:none;}

    .drawTrunk{animation: fadeInUp 650ms ease forwards; transform-origin: 50% 100%;}
    .drawBranches{animation: fadeInUp 650ms ease 220ms forwards; transform-origin: 50% 50%;}
    @keyframes fadeInUp{from{transform:translateY(10px) scale(.98); opacity:0;} to{transform:translateY(0) scale(1); opacity:1;}}

    .leaf{position:absolute; width:16px; height:16px; transform:rotate(45deg) scale(.6); opacity:0;
      animation: leafPop 520ms ease forwards;
      filter: drop-shadow(0 10px 16px rgba(255,45,85,.25));
    }
    .leaf:before, .leaf:after{content:""; position:absolute; width:16px; height:16px; background:inherit; border-radius:50%;}
    .leaf:before{left:-8px; top:0;}
    .leaf:after{left:0; top:-8px;}
    @keyframes leafPop{0%{opacity:0; transform:rotate(45deg) scale(.5);} 70%{opacity:1; transform:rotate(45deg) scale(1.15);} 100%{opacity:1; transform:rotate(45deg) scale(1);}}

    .rainHeart{position:absolute; top:-24px; width:14px; height:14px; transform:rotate(45deg); opacity:.9;
      animation: rain var(--dur) ease-in forwards;
      filter: drop-shadow(0 10px 18px rgba(255,45,85,.20));
    }
    .rainHeart:before, .rainHeart:after{content:""; position:absolute; width:14px; height:14px; background:inherit; border-radius:50%;}
    .rainHeart:before{left:-7px; top:0;}
    .rainHeart:after{left:0; top:-7px;}
    @keyframes rain{to{transform: translateX(var(--drift)) translateY(420px) rotate(45deg); opacity:0;}}

    /* Slideshow */
    .slideStage{position:.slideStage{position:relative; height:460px; border-radius:20px; overflow:hidden;
      border:1px solid rgba(255,255,255,.55);
      box-shadow: 0 18px 55px rgba(0,0,0,.12);
      background: rgba(255,255,255,.25);
    }
    .slideHint{position:absolute; left:12px; right:12px; bottom:12px;
      padding:10px 12px; border-radius:16px;
      background: rgba(255,255,255,.72);
      border:1px solid rgba(0,0,0,.08);
      backdrop-filter: blur(10px);
      font-weight:900; text-align:center;
      opacity:.9;
    }
    .slideImg{position:absolute; inset:0; width:100%; height:100%; object-fit:cover; opacity:0; transform:scale(1.02);
      transition: opacity 420ms ease, transform 520ms ease;
    }
    .slideImg.show{opacity:1; transform:scale(1.0)}
    
    /* Footer */
    footer{max-width: 980px; margin: 0 auto; padding: 0 20px 30px; text-align:center; opacity:.85;}

  </style>
</head>
<body>
  <div class="hearts" id="hearts" aria-hidden="true"></div>
  <div class="burst" id="burst" aria-hidden="true"></div>

  <!-- 1) ASK OVERLAY -->
  <section class="overlay" id="ask" aria-label="Valentine question">
    <div class="overlayCard">
      <div class="overlayHeader">
        <div class="badge">💘</div>
        <div>
          <h1 style="margin:0;">Will you be my Valentine?</h1>
          <p class="sub" style="margin:10px 0 0;">Choose wisely… 😄</p>
        </div>
      </div>
      <div class="askBtns" id="askBtns">
        <button class="primary" id="yesBtn">Yes 💖</button>
        <button class="secondary" id="noBtn">No 🙈</button>
      </div>
      <p class="tiny" style="margin-top:14px;">(Psst… the “No” button gets shy.)</p>
    </div>
  </section>

  <!-- 2) HEART TREE OVERLAY -->
  <section class="overlay" id="treeWrap" aria-label="Heart tree celebration" hidden>
    <div class="overlayCard">
      <div class="overlayHeader">
        <div class="badge">🌳</div>
        <div>
          <h1 style="margin:0;">Yay! 💞</h1>
          <p class="sub" style="margin:10px 0 0;">A heart-tree just for you.</p>
        </div>
      </div>
      <div class="treeStage" id="treeStage">
        <svg class="tree" viewBox="0 0 420 320" role="img" aria-label="Tree with hearts">
          <defs>
            <linearGradient id="trunkGrad" x1="0" x2="0" y1="0" y2="1">
              <stop offset="0" stop-color="#7a4b2a"/>
              <stop offset="1" stop-color="#4a2b1b"/>
            </linearGradient>
          </defs>
          <path d="M40 270 C120 245, 300 245, 380 270 L380 320 L40 320 Z" fill="rgba(0,0,0,.08)"/>
          <path id="trunk" d="M205 270 C190 220, 198 190, 205 165 C210 130, 198 110, 205 85 C215 110, 232 130, 226 165 C235 195, 248 220, 234 270 Z" fill="url(#trunkGrad)" opacity="0" />
          <path id="branches" d="M210 150 C175 140, 155 120, 145 95 C170 112, 192 118, 212 120 C235 110, 262 95, 288 70 C274 105, 250 135, 222 148" fill="none" stroke="rgba(74,43,27,.85)" stroke-width="10" stroke-linecap="round" opacity="0"/>
        </svg>
        <div class="leafLayer" id="leafLayer" aria-hidden="true"></div>
        <div class="rainLayer" id="rainLayer" aria-hidden="true"></div>
      </div>
      <div class="ctaRow" style="justify-content:center; margin-top:14px;">
        <button class="primary" id="toSlideshow">Next 💞</button>
      </div>
    </div>
  </section>

  <!-- 3) SLIDESHOW OVERLAY -->
  <section class="overlay" id="slideWrap" aria-label="Photo slideshow" hidden>
    <div class="overlayCard" style="padding:18px;">
      <div class="overlayHeader" style="margin-bottom:12px;">
        <div class="badge">📸</div>
        <div>
          <h1 style="margin:0;">Us (on repeat) 💗</h1>
          <p class="sub" style="margin:10px 0 0;">Just sit back — no buttons needed.</p>
        </div>
      </div>

      <div class="slideStage" id="slideStage" aria-label="Slideshow (tap to skip)">
        <img id="slideA" class="slideImg" alt="Slideshow photo" />
        <img id="slideB" class="slideImg" alt="Slideshow photo" />
        <div class="slideHint">Tap anywhere to see the next photo ✨</div>
      </div>

      <div id="spotifyBox">
        <iframe id="spotifyFrame" title="Spotify Player" style="width:100%; height:152px; border:0; border-radius:16px;" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
      </div>

      <div class="ctaRow" style="justify-content:center; margin-top:14px;">
        <button class="primary" id="enterSite">Continue ✨</button>
      </div>

      <p class="tiny" style="margin-top:10px;">
        Tip for you (the creator): replace the photo list in the code with your photos, or keep the file picker version and I’ll re-enable it.
      </p>
    </div>
  </section>

  <!-- MAIN SITE -->
  <main class="wrap" id="main" hidden>
    <section class="card">
      <div class="headline">
        <div class="badge">💘</div>
        <div>
          <h1>Happy Valentine’s Day</h1>
          <p class="sub">Customize your note below 💌</p>
        </div>
      </div>

      <div class="divider"></div>

      <div class="note">
        <div>
          <label for="to">To</label>
          <input id="to" placeholder="e.g., My Favorite Human" value="My Favorite Human" />
        </div>
        <div>
          <label for="from">From</label>
          <input id="from" placeholder="e.g., Your Name" value="Someone Who Adore You" />
        </div>
        <div>
          <label for="message">Message</label>
          <textarea id="message" placeholder="Write something sweet…">Roses are red,
Violets are blue,
Life is better,
Because of you.

Will you be my Valentine? 💖</textarea>
        </div>
      </div>

      <div class="ctaRow">
        <button class="primary" id="celebrate">Send with Love ✨</button>
        <button class="secondary" id="copy">Copy Link Text 🔗</button>
        <button class="secondary" id="surprise">More Surprises 🎁</button>
      </div>

      <p class="tiny" style="margin-top:14px;">Want more pages, a different theme, or a “memory timeline” layout? Tell me what vibe you want.</p>
    </section>

    <aside class="preview">
      <div class="postcard" aria-label="Preview postcard">
        <div class="postcardTop">
          <div class="toFrom">
            <div>To: <span id="pTo">My Favorite Human</span></div>
            <div style="opacity:.78; font-weight:800; margin-top:4px;">From: <span id="pFrom">Someone Who Adore You</span></div>
          </div>
          <div class="stamp">💞</div>
        </div>
        <div class="divider"></div>
        <div class="msg" id="pMsg">Roses are red,
Violets are blue,
Life is better,
Because of you.

Will you be my Valentine? 💖</div>
        <div class="sig">— With all my love</div>
      </div>

      <div class="card" style="margin-top:16px; padding:18px;">
        <div style="font-weight:900; margin-bottom:6px;">Mini controls</div>
        <div class="tiny">
          <ul style="margin:10px 0 0; padding-left:18px;">
            <li>“More Surprises” shows different cute messages.</li>
            <li>“Copy Link Text” copies a ready-to-send note.</li>
            <li>Background clicks sometimes pop hearts.</li>
          </ul>
        </div>
      </div>
    </aside>
  </main>

  <footer>
    <div class="tiny">Made with ❤️. Spotify tip: use Spotify “Share → Embed track/playlist” and paste the embed link.</div>
  </footer>

  <script>
    const rand = (a,b)=> Math.random()*(b-a)+a;
    const pick = (arr)=> arr[Math.floor(Math.random()*arr.length)];

    // Floating background hearts
    const hearts = document.getElementById('hearts');
    for(let i=0;i<26;i++){
      const h = document.createElement('div');
      h.className = 'heart';
      h.style.left = rand(0,100) + 'vw';
      h.style.animationDuration = rand(6,14) + 's';
      h.style.animationDelay = (-rand(0,8)) + 's';
      h.style.setProperty('--s', rand(.7, 1.8));
      h.style.opacity = rand(.25, .75);
      h.style.background = Math.random() < .25 ? 'var(--accent2)' : 'var(--accent)';
      hearts.appendChild(h);
    }

    // Bursts
    const burst = document.getElementById('burst');
    function heartBurst(x,y){
      const N = 22;
      for(let i=0;i<N;i++){
        const s = document.createElement('div');
        s.className = 'spark';
        s.style.left = x + 'px';
        s.style.top = y + 'px';
        s.style.setProperty('--dx', rand(-160, 160) + 'px');
        s.style.setProperty('--dy', rand(-180, 120) + 'px');
        s.style.background = Math.random() < .35 ? 'var(--accent2)' : 'var(--accent)';
        burst.appendChild(s);
        s.addEventListener('animationend', ()=> s.remove());
      }
    }

    // Tiny toast
    let toastEl;
    function toast(msg){
      if(toastEl) toastEl.remove();
      toastEl = document.createElement('div');
      toastEl.textContent = msg;
      Object.assign(toastEl.style, {
        position:'fixed', left:'50%', bottom:'22px', transform:'translateX(-50%)',
        padding:'10px 14px', background:'rgba(255,255,255,.78)',
        border:'1px solid rgba(0,0,0,.10)', borderRadius:'14px',
        boxShadow:'0 16px 40px rgba(0,0,0,.16)', backdropFilter:'blur(10px)',
        fontWeight:'900', zIndex:9999
      });
      document.body.appendChild(toastEl);
      toastEl.animate([
        {opacity:0, transform:'translateX(-50%) translateY(10px)'},
        {opacity:1, transform:'translateX(-50%) translateY(0px)'},
        {opacity:1, transform:'translateX(-50%) translateY(0px)'},
        {opacity:0, transform:'translateX(-50%) translateY(10px)'}
      ], {duration:2200, easing:'ease-out'}).onfinish = ()=> toastEl?.remove();
    }

    // 1) Ask logic
    const ask = document.getElementById('ask');
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');
    const askBtns = document.getElementById('askBtns');

    let noScale = 1;
    let yesScale = 1;

    function moveNoButton(){
      const card = askBtns.getBoundingClientRect();
      const btn = noBtn.getBoundingClientRect();
      const pad = 6;
      const maxX = Math.max(pad, card.width - btn.width - pad);
      const maxY = Math.max(pad, card.height - btn.height - pad);
      const x = rand(pad, maxX);
      const y = rand(pad, maxY);
      noBtn.style.position = 'absolute';
      askBtns.style.position = 'relative';
      noBtn.style.left = x + 'px';
      noBtn.style.top = y + 'px';

      noScale = Math.max(0.35, noScale * 0.85);
      yesScale = Math.min(1.9, yesScale * 1.10);
      noBtn.style.transform = `scale(${noScale})`;
      yesBtn.style.transform = `scale(${yesScale})`;

      heartBurst(btn.left + btn.width/2, btn.top + btn.height/2);
    }

    ['mouseenter','pointerdown','click'].forEach(evt => {
      noBtn.addEventListener(evt, (e)=>{ e.preventDefault(); moveNoButton(); });
    });

    // 2) Tree overlay
    const treeWrap = document.getElementById('treeWrap');
    const trunk = document.getElementById('trunk');
    const branches = document.getElementById('branches');
    const leafLayer = document.getElementById('leafLayer');
    const rainLayer = document.getElementById('rainLayer');
    const toSlideshow = document.getElementById('toSlideshow');

    function makeLeaf(x,y,delay){
      const leaf = document.createElement('div');
      leaf.className = 'leaf';
      leaf.style.left = x + '%';
      leaf.style.top = y + '%';
      leaf.style.animationDelay = delay + 'ms';
      leaf.style.background = Math.random() < .28 ? 'var(--accent2)' : 'var(--accent)';
      leafLayer.appendChild(leaf);
    }

    function startHeartRain(){
      const start = Date.now();
      const timer = setInterval(()=>{
        const now = Date.now();
        if(now - start > 2800){ clearInterval(timer); return; }
        const h = document.createElement('div');
        h.className = 'rainHeart';
        h.style.left = rand(5,95) + '%';
        h.style.setProperty('--dur', rand(1.8, 3.2) + 's');
        h.style.setProperty('--drift', rand(-40, 40) + 'px');
        h.style.background = Math.random() < .3 ? 'var(--accent2)' : 'var(--accent)';
        rainLayer.appendChild(h);
        h.addEventListener('animationend', ()=> h.remove());
      }, 70);
    }

    function growTree(){
      trunk.style.opacity = '1';
      branches.style.opacity = '1';
      trunk.classList.add('drawTrunk');
      branches.classList.add('drawBranches');

      leafLayer.innerHTML = '';
      rainLayer.innerHTML = '';

      const leaves = [
        [46, 28],[52, 26],[58, 28],[40, 32],[64, 34],
        [36, 40],[44, 38],[52, 36],[60, 38],[68, 42],
        [32, 50],[40, 52],[50, 48],[60, 52],[70, 54],
        [38, 62],[50, 60],[62, 62],[46, 70],[56, 70]
      ];
      leaves.forEach((p, i)=> makeLeaf(p[0], p[1], i*70));

      const stage = document.getElementById('treeStage').getBoundingClientRect();
      heartBurst(stage.left + stage.width/2, stage.top + stage.height/3);
      startHeartRain();
    }

    yesBtn.addEventListener('click', ()=>{
      ask.hidden = true;
      treeWrap.hidden = false;
      setTimeout(growTree, 120);
      toast('She said yes!! 💖');
    });

    // 3) Slideshow overlay (no controls)
    const slideWrap = document.getElementById('slideWrap');
    const slideA = document.getElementById('slideA');
    const slideB = document.getElementById('slideB');
    const slideStage = document.getElementById('slideStage');

    // Replace these with your own photos (local hosted URLs or data URLs)
    // Example if hosting: ['photos/01.jpg','photos/02.jpg',...]
    let photos = [
      'https://images.unsplash.com/photo-1518199266791-5375a83190b7?auto=format&fit=crop&w=1400&q=80',
      'https://images.unsplash.com/photo-1520975693411-b2451a62d5f1?auto=format&fit=crop&w=1400&q=80',
      'https://images.unsplash.com/photo-1517841905240-472988babdf6?auto=format&fit=crop&w=1400&q=80'
    ];

    let idx = 0;
    let timer;
    let front = 'A';

    function showSlide(i){
      if(!photos.length) return;
      idx = (i + photos.length) % photos.length;
      const url = photos[idx];
      const incoming = (front === 'A') ? slideB : slideA;
      const outgoing = (front === 'A') ? slideA : slideB;
      incoming.src = url;
      incoming.classList.add('show');
      outgoing.classList.remove('show');
      front = (front === 'A') ? 'B' : 'A';
    }

    function next(){ showSlide(idx + 1); }
    function startAuto(){ stopAuto(); timer = setInterval(next, 3000); }
    function stopAuto(){ if(timer) clearInterval(timer); timer = null; }

    // Tap/click anywhere on slideshow -> next
    slideStage?.addEventListener('click', ()=>{
      next();
      const r = slideStage.getBoundingClientRect();
      heartBurst(r.left + r.width/2, r.top + r.height/2);
      startAuto();
    });

    // Spotify embed (pre-filled)
    const spotifyFrame = document.getElementById('spotifyFrame');
    spotifyFrame.src = 'https://open.spotify.com/embed/track/3qhlB30KknSejmIvZZLjOD';

    // Note: browsers may block autoplay. The Spotify player will appear; user may need to press play once.

    toSlideshow.addEventListener('click', ()=>{
      treeWrap.hidden = true;
      slideWrap.hidden = false;
      showSlide(0);
      startAuto();
      const rect = toSlideshow.getBoundingClientRect();
      heartBurst(rect.left + rect.width/2, rect.top + rect.height/2);
      toast('Okay… now look 😳💗');
    });

t = message.value || '';
    }
    [to, from, message].forEach(el => el.addEvdocument.getElementById('enterSite').addEventListener('click', ()=>{
      slideWrap.hidden = true;
      main.hidden = false;
      stopAuto();
      const rect = document.getElementById('enterSite').getBoundingClientRect();
      heartBurst(rect.left + rect.width/2, rect.top + rect.height/2);
      toast('Welcome 💘');
    });ard.writeText(txt);
        toast('Copied! Paste it into your chat ✨');
      }catch{
        const ta = document.createElement('textarea');
        ta.value = txt;
        document.body.appendChild(ta);
        ta.select();
        document.execCommand('copy');
        ta.remove();
        toast('Copied! Paste it into your chat ✨');
      }
    });

    // Celebrate burst
    document.getElementById('celebrate').addEventListener('click', (e)=>{
      const rect = e.target.getBoundingClientRect();
      heartBurst(rect.left + rect.width/2, rect.top + rect.height/2);
      e.target.animate([
        {transform:'translateY(-1px) scale(1.0)'},
        {transform:'translateY(-1px) scale(1.03)'},
        {transform:'translateY(-1px) scale(1.0)'}
      ], {duration:280, easing:'ease-out'});
      toast(pick(['Sent with love 💞','Love delivered 💌','Boom! Hearts! 💖']));
    });

    // Surprise button (multiple surprises)
    const surpriseLines = [
      'You’re my favorite notification. 📱💗',
      'If kisses were stars, I’d give you the sky. ✨',
      'I choose you—today and all the tomorrows. 💞',
      'My heart does a little dance when I think of you. 🩷',
      'You + me = my happiest place. 🥰',
      'Plot twist: I like you… a LOT. 😳💘',
      'If love was a playlist, you’d be on repeat. 🎶',
      'I’d still pick you in every universe. 🌙'
    ];
    document.getElementById('surprise').addEventListener('click', ()=>{
      const line = pick(surpriseLines);
      toast(line);
      heartBurst(rand(100, window.innerWidth-100), rand(120, window.innerHeight-140));
      // sometimes pop an alert too
      if(Math.random() < 0.35){
        alert(line + "

Happy Valentine’s! 💖");
      }
    });

    // Background click burst sometimes
    window.addEventListener('click', (e)=>{
      if(e.target.tagName === 'BUTTON' || e.target.closest('button')) return;
      if(Math.random() < 0.18) heartBurst(e.clientX, e.clientY);
    });
    // Init slideshow first frame (in case)
    slideA.src = photos[0];
    slideA.classList.add('show');

  </script>
</body>
</html>
