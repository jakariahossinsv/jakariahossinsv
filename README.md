<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Fahim — QA · AI · IoT · Automation</title>
<meta name="description" content="Fahim — QA Enthusiast, AI & IoT Explorer, and future DevOps engineer. Portfolio, skills and tech journey." />
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet" />
<style>
  :root{
    color-scheme: dark;
    --bg:#080B16;
    --bg-2:#0B1020;
    --ink:#EAF0FF;
    --muted:#93A0C4;
    --faint:#5C6890;
    --line:rgba(255,255,255,.09);
    --panel:rgba(255,255,255,.028);
    --panel-2:rgba(255,255,255,.05);
    --cyan:#2DE2E6;
    --violet:#8B5CFF;
    --pink:#FF5DA2;
    --amber:#FFC24B;
    --ok:#35E19B;
    --grad:linear-gradient(92deg,#2DE2E6 0%,#8B5CFF 52%,#FF5DA2 100%);
    --display:"Space Grotesk",system-ui,sans-serif;
    --body:"Inter",system-ui,sans-serif;
    --mono:"JetBrains Mono",ui-monospace,monospace;
    --maxw:1080px;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth}
  body{
    font-family:var(--body);
    background:var(--bg);
    color:var(--ink);
    line-height:1.65;
    overflow-x:hidden;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit;text-decoration:none}
  img{max-width:100%;display:block}

  /* ---------- Background ---------- */
  .bg{
    position:fixed;inset:0;z-index:-3;overflow:hidden;
    background:
      radial-gradient(1200px 760px at 82% -12%, rgba(139,92,255,.20), transparent 60%),
      radial-gradient(1000px 700px at -8% 18%, rgba(45,226,230,.15), transparent 55%),
      radial-gradient(900px 600px at 60% 120%, rgba(255,93,162,.12), transparent 60%),
      var(--bg);
  }
  .blob{position:absolute;border-radius:50%;filter:blur(80px);opacity:.45;animation:floaty 18s ease-in-out infinite}
  .b1{width:420px;height:420px;background:#8B5CFF;top:-80px;right:-60px}
  .b2{width:360px;height:360px;background:#2DE2E6;bottom:-120px;left:-80px;animation-delay:-6s}
  .b3{width:300px;height:300px;background:#FF5DA2;top:40%;left:55%;animation-delay:-11s;opacity:.28}
  .grid-overlay{
    position:fixed;inset:0;z-index:-2;
    background-image:
      linear-gradient(rgba(255,255,255,.035) 1px,transparent 1px),
      linear-gradient(90deg,rgba(255,255,255,.035) 1px,transparent 1px);
    background-size:46px 46px;
    -webkit-mask-image:radial-gradient(circle at 50% 26%, #000 0%, transparent 78%);
    mask-image:radial-gradient(circle at 50% 26%, #000 0%, transparent 78%);
  }

  /* ---------- Scroll progress ---------- */
  .scrollbar-track{position:fixed;top:0;left:0;right:0;height:3px;z-index:120;background:rgba(255,255,255,.05)}
  #scrollbar{height:100%;width:0;background:var(--grad);box-shadow:0 0 12px rgba(45,226,230,.6)}

  /* ---------- Nav ---------- */
  #nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    display:flex;align-items:center;justify-content:space-between;
    padding:16px clamp(18px,5vw,42px);
    transition:background .35s ease, border-color .35s ease, backdrop-filter .35s ease;
    border-bottom:1px solid transparent;
  }
  #nav.solid{background:rgba(8,11,22,.72);backdrop-filter:blur(14px);border-bottom:1px solid var(--line)}
  .brand{display:flex;align-items:center;gap:10px;font-family:var(--mono);font-weight:700;letter-spacing:.5px}
  .brand .mark{
    width:30px;height:30px;border-radius:8px;background:var(--grad);
    display:grid;place-items:center;color:#08101f;font-weight:700;font-size:15px;
    box-shadow:0 0 18px rgba(139,92,255,.5);
  }
  .brand small{color:var(--faint);font-weight:400}
  .nav-links{display:flex;gap:26px;font-family:var(--mono);font-size:13px}
  .nav-links a{color:var(--muted);position:relative;padding:4px 0;transition:color .2s}
  .nav-links a::after{content:"";position:absolute;left:0;bottom:-2px;width:0;height:2px;background:var(--grad);transition:width .25s}
  .nav-links a:hover{color:var(--ink)}
  .nav-links a:hover::after{width:100%}

  /* ---------- Layout ---------- */
  .container{max-width:var(--maxw);margin:0 auto;padding:0 clamp(20px,5vw,24px)}
  .section{padding:clamp(70px,11vw,116px) 0;position:relative}
  .eyebrow{
    font-family:var(--mono);font-size:12.5px;letter-spacing:2px;text-transform:uppercase;
    color:var(--cyan);display:inline-flex;align-items:center;gap:10px;margin-bottom:16px;
  }
  .eyebrow::before{content:"";width:26px;height:1px;background:var(--cyan);opacity:.6}
  .h2{font-family:var(--display);font-weight:600;font-size:clamp(1.7rem,4.2vw,2.55rem);line-height:1.12;letter-spacing:-.5px}
  .lead{color:var(--muted);max-width:60ch;margin-top:14px;font-size:1.02rem}

  /* ---------- Buttons ---------- */
  .btn{
    position:relative;display:inline-flex;align-items:center;gap:9px;
    font-family:var(--mono);font-size:14px;font-weight:500;letter-spacing:.3px;
    padding:13px 22px;border-radius:12px;cursor:pointer;border:1px solid transparent;
    transition:transform .25s ease, box-shadow .25s ease, border-color .25s ease, background .25s ease;
    overflow:hidden;white-space:nowrap;
  }
  .btn svg{width:16px;height:16px}
  .btn-primary{color:#07101f;background:var(--grad);background-size:180% 180%;box-shadow:0 8px 26px rgba(139,92,255,.32)}
  .btn-primary::after{
    content:"";position:absolute;top:0;left:-120%;width:60%;height:100%;
    background:linear-gradient(120deg,transparent,rgba(255,255,255,.55),transparent);transform:skewX(-20deg);
  }
  .btn-primary:hover{transform:translateY(-3px);box-shadow:0 14px 34px rgba(139,92,255,.5);animation:shift 3s ease infinite}
  .btn-primary:hover::after{animation:sheen .9s ease}
  .btn-ghost{color:var(--ink);border-color:var(--line);background:var(--panel)}
  .btn-ghost:hover{transform:translateY(-3px);border-color:rgba(45,226,230,.5);box-shadow:0 0 0 1px rgba(45,226,230,.25),0 10px 26px rgba(0,0,0,.4)}

  /* ---------- HERO ---------- */
  .hero{position:relative;min-height:100svh;display:flex;align-items:center;padding-top:96px;padding-bottom:60px}
  #net{position:absolute;inset:0;width:100%;height:100%;z-index:0;opacity:.55}
  .hero .container{position:relative;z-index:2}
  .hero-grid{display:grid;grid-template-columns:1.25fr .9fr;gap:clamp(30px,5vw,60px);align-items:center}
  .status-chip{
    display:inline-flex;align-items:center;gap:10px;font-family:var(--mono);font-size:12.5px;
    color:var(--muted);border:1px solid var(--line);background:var(--panel);
    padding:7px 14px;border-radius:999px;margin-bottom:22px;
  }
  .status-chip b{color:var(--ok);font-weight:500}
  .pulse{width:9px;height:9px;border-radius:50%;background:var(--ok);box-shadow:0 0 0 0 rgba(53,225,155,.6);animation:pulse 2s infinite}
  .hero h1{
    font-family:var(--display);font-weight:700;letter-spacing:-1.5px;line-height:.98;
    font-size:clamp(2.9rem,8vw,5rem);margin-bottom:6px;
  }
  .hero h1 .grad{
    background:var(--grad);background-size:220% auto;-webkit-background-clip:text;background-clip:text;
    -webkit-text-fill-color:transparent;color:transparent;animation:shift 6s ease infinite;
  }
  .role-line{font-family:var(--mono);font-size:clamp(1rem,3vw,1.4rem);color:var(--ink);margin:14px 0 6px;min-height:1.5em}
  .role-line .prompt{color:var(--cyan)}
  #typedRole{border-right:2px solid var(--pink);padding-right:3px;animation:blink 1s step-end infinite}
  .hero p.intro{color:var(--muted);max-width:52ch;margin:18px 0 30px;font-size:1.05rem}
  .cta{display:flex;gap:14px;flex-wrap:wrap}
  .hero-meta{display:flex;gap:26px;margin-top:34px;flex-wrap:wrap}
  .hero-meta div{font-family:var(--mono)}
  .hero-meta .num{font-size:1.35rem;color:var(--ink);font-weight:700}
  .hero-meta .lbl{font-size:11.5px;color:var(--faint);letter-spacing:1px;text-transform:uppercase}

  /* portrait */
  .portrait{position:relative;justify-self:center;width:min(330px,80vw);aspect-ratio:1}
  .portrait .ring{
    position:absolute;inset:-14px;border-radius:34px;padding:2px;
    background:conic-gradient(from 0deg,#2DE2E6,#8B5CFF,#FF5DA2,#2DE2E6);
    -webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);
    -webkit-mask-composite:xor;mask-composite:exclude;
    animation:spin 8s linear infinite;filter:drop-shadow(0 0 18px rgba(139,92,255,.4));
  }
  .photo{position:absolute;inset:0;border-radius:28px;overflow:hidden;background:radial-gradient(120% 120% at 30% 20%,#141a30,#0b1020);border:1px solid var(--line)}
  #profilePhoto{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;opacity:0;transition:opacity .6s ease}
  #profilePhoto.show{opacity:1}
  .photo-ph{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px;color:var(--faint);text-align:center}
  .photo-ph svg{width:64px;height:64px;opacity:.5}
  .photo-ph span{font-family:var(--mono);font-size:13px;letter-spacing:2px;color:var(--muted)}
  .photo-ph small{font-family:var(--mono);font-size:10.5px;color:var(--faint)}
  .orbit{position:absolute;inset:-14px;animation:spin 14s linear infinite}
  .orbit .dot{position:absolute;width:11px;height:11px;border-radius:50%;box-shadow:0 0 12px currentColor}
  .orbit .d1{top:-5px;left:50%;color:var(--cyan);background:var(--cyan)}
  .orbit .d2{bottom:8%;right:-5px;color:var(--pink);background:var(--pink)}
  .orbit .d3{bottom:8%;left:-5px;color:var(--violet);background:var(--violet)}
  .scroll-hint{position:absolute;left:50%;bottom:26px;transform:translateX(-50%);z-index:2;font-family:var(--mono);font-size:11px;letter-spacing:2px;color:var(--faint);display:flex;flex-direction:column;align-items:center;gap:8px}
  .scroll-hint .mouse{width:22px;height:34px;border:1px solid var(--line);border-radius:12px;position:relative}
  .scroll-hint .mouse::after{content:"";position:absolute;top:6px;left:50%;transform:translateX(-50%);width:3px;height:7px;border-radius:2px;background:var(--cyan);animation:wheel 1.6s ease infinite}

  /* ---------- Panels & reveal ---------- */
  .panel{background:var(--panel);border:1px solid var(--line);border-radius:18px;padding:26px}
  [data-reveal]{opacity:0;transform:translateY(26px);transition:opacity .7s cubic-bezier(.2,.7,.2,1),transform .7s cubic-bezier(.2,.7,.2,1)}
  [data-reveal].in-view{opacity:1;transform:none}

  /* about */
  .about-grid{display:grid;grid-template-columns:1.4fr .9fr;gap:26px;margin-top:34px;align-items:start}
  .about-grid p{color:var(--muted);margin-bottom:14px}
  .about-grid p strong{color:var(--ink);font-weight:600}
  .spec{font-family:var(--mono)}
  .spec .row{display:flex;justify-content:space-between;gap:16px;padding:13px 0;border-bottom:1px dashed var(--line);font-size:13.5px}
  .spec .row:last-child{border-bottom:0}
  .spec .k{color:var(--faint);text-transform:uppercase;letter-spacing:1px;font-size:11px}
  .spec .v{color:var(--ink);text-align:right}
  .spec .v.accent{color:var(--cyan)}

  /* skills */
  .sub{font-family:var(--mono);font-size:12px;letter-spacing:2px;text-transform:uppercase;color:var(--faint);margin:0 0 18px;display:flex;align-items:center;gap:10px}
  .sub::before{content:"▹";color:var(--pink)}
  .skills-wrap{margin-top:36px}
  .skill{margin-bottom:20px}
  .skill-head{display:flex;justify-content:space-between;align-items:baseline;font-family:var(--mono);margin-bottom:8px}
  .skill-head .name{color:var(--ink);font-size:14.5px}
  .skill-head .name .tag{color:var(--faint);font-size:11px;margin-left:8px}
  .skill-val{color:var(--cyan);font-size:13px}
  .skill-track{height:9px;border-radius:999px;background:rgba(255,255,255,.06);overflow:hidden;position:relative}
  .skill-fill{height:100%;width:0;border-radius:999px;background:var(--grad);background-size:200% 100%;transition:width 1.3s cubic-bezier(.2,.7,.2,1);position:relative;animation:shift 4s linear infinite}
  .skill-fill::after{content:"";position:absolute;inset:0;background:linear-gradient(90deg,transparent,rgba(255,255,255,.35),transparent);animation:scan 2.4s linear infinite}

  .cols-2{display:grid;grid-template-columns:1fr 1fr;gap:26px;margin-top:44px}
  .chips{display:flex;flex-wrap:wrap;gap:10px}
  .chip{
    font-family:var(--mono);font-size:13px;color:var(--ink);padding:9px 15px;border-radius:10px;
    border:1px solid var(--line);background:var(--panel-2);display:inline-flex;align-items:center;gap:9px;
    transition:transform .22s,border-color .22s,box-shadow .22s,color .22s;
  }
  .chip .dot{width:8px;height:8px;border-radius:50%;background:var(--cyan);box-shadow:0 0 8px var(--cyan)}
  .chip:hover{transform:translateY(-3px);border-color:rgba(139,92,255,.5);box-shadow:0 8px 22px rgba(0,0,0,.35);color:#fff}

  /* interests + focus */
  .focus-grid{display:grid;grid-template-columns:1fr 1fr;gap:26px;margin-top:34px;align-items:start}
  .pills{display:flex;flex-wrap:wrap;gap:12px;margin-top:6px}
  .pill{
    position:relative;font-family:var(--mono);font-size:14px;padding:11px 18px;border-radius:999px;
    color:var(--ink);background:var(--bg-2);border:1px solid transparent;
    background-image:linear-gradient(var(--bg-2),var(--bg-2)),var(--grad);
    background-origin:border-box;background-clip:padding-box,border-box;
    transition:transform .22s,box-shadow .22s;
  }
  .pill:hover{transform:translateY(-3px) scale(1.03);box-shadow:0 10px 26px rgba(139,92,255,.3)}
  .log{font-family:var(--mono);font-size:14px}
  .log li{list-style:none;display:flex;gap:12px;padding:12px 0;border-bottom:1px dashed var(--line);color:var(--muted)}
  .log li:last-child{border-bottom:0}
  .log li .mk{color:var(--ok)}
  .log li b{color:var(--ink);font-weight:500}

  /* activity */
  .stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:22px;margin-top:34px}
  .stat-card{padding:16px;display:flex;justify-content:center;align-items:center;min-height:150px}
  .stat-card.wide{grid-column:1 / -1}
  .stat-card img{border-radius:10px;width:100%;height:auto}

  /* connect */
  .quote{font-family:var(--display);font-size:clamp(1.4rem,3.6vw,2rem);font-weight:500;line-height:1.3;max-width:20ch;letter-spacing:-.4px}
  .quote .grad{background:var(--grad);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent}
  .socials{display:flex;flex-direction:column;gap:14px;margin-top:6px}
  .social{
    display:flex;align-items:center;gap:16px;padding:16px 20px;border-radius:14px;
    border:1px solid var(--line);background:var(--panel);transition:transform .25s,border-color .25s,box-shadow .25s;
  }
  .social:hover{transform:translateX(6px);border-color:rgba(45,226,230,.5);box-shadow:0 10px 30px rgba(0,0,0,.4)}
  .social .ico{width:44px;height:44px;border-radius:11px;display:grid;place-items:center;flex:none}
  .social .ico svg{width:22px;height:22px;fill:#fff}
  .social .txt{flex:1}
  .social .txt .t{font-family:var(--mono);font-size:15px;color:var(--ink)}
  .social .txt .s{font-size:12.5px;color:var(--faint)}
  .social .arrow{font-family:var(--mono);color:var(--faint);transition:transform .25s,color .25s}
  .social:hover .arrow{transform:translateX(4px);color:var(--cyan)}
  .ico.gh{background:#1b2233} .ico.li{background:#0a66c2} .ico.fb{background:#1877f2}

  /* footer */
  footer{border-top:1px solid var(--line);padding:34px 0;text-align:center;color:var(--faint);font-family:var(--mono);font-size:12.5px}
  footer .grad{background:var(--grad);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent}

  /* ---------- keyframes ---------- */
  @keyframes floaty{0%,100%{transform:translate(0,0)}50%{transform:translate(30px,-26px)}}
  @keyframes spin{to{transform:rotate(360deg)}}
  @keyframes pulse{0%{box-shadow:0 0 0 0 rgba(53,225,155,.6)}70%{box-shadow:0 0 0 10px rgba(53,225,155,0)}100%{box-shadow:0 0 0 0 rgba(53,225,155,0)}}
  @keyframes blink{50%{border-color:transparent}}
  @keyframes shift{0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%}}
  @keyframes sheen{0%{left:-120%}100%{left:130%}}
  @keyframes scan{0%{transform:translateX(-100%)}100%{transform:translateX(100%)}}
  @keyframes wheel{0%{opacity:0;transform:translate(-50%,0)}40%{opacity:1}100%{opacity:0;transform:translate(-50%,10px)}}

  /* ---------- responsive ---------- */
  @media (max-width:860px){
    .nav-links{display:none}
    .hero-grid{grid-template-columns:1fr;text-align:left}
    .portrait{order:-1;margin-bottom:8px}
    .about-grid,.cols-2,.focus-grid,.stats-grid{grid-template-columns:1fr}
    .connect-grid{grid-template-columns:1fr}
  }
  .connect-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:36px;margin-top:34px;align-items:center}

  @media (prefers-reduced-motion: reduce){
    *{animation:none!important;transition:none!important}
    [data-reveal]{opacity:1;transform:none}
    #profilePhoto{opacity:1}
  }
</style>
</head>
<body>
  <!-- backgrounds -->
  <div class="bg"><span class="blob b1"></span><span class="blob b2"></span><span class="blob b3"></span></div>
  <div class="grid-overlay"></div>

  <!-- scroll progress -->
  <div class="scrollbar-track"><div id="scrollbar"></div></div>

  <!-- nav -->
  <nav id="nav">
    <a class="brand" href="#top"><span class="mark">F</span> fahim<small>.dev</small></a>
    <div class="nav-links">
      <a href="#about">// about</a>
      <a href="#skills">// skills</a>
      <a href="#focus">// focus</a>
      <a href="#activity">// activity</a>
      <a href="#connect">// connect</a>
    </div>
  </nav>

  <!-- HERO -->
  <header class="hero" id="top">
    <canvas id="net"></canvas>
    <div class="container">
      <div class="hero-grid">
        <div>
          <span class="status-chip"><span class="pulse"></span> SYSTEM STATUS: <b>ONLINE · LEARNING</b></span>
          <h1>Hi, I'm <span class="grad">Fahim</span></h1>
          <div class="role-line"><span class="prompt">&gt;</span> <span id="typedRole"></span></div>
          <p class="intro">Student at Daffodil International University building toward a future in AI, automation and quality engineering — one project at a time.</p>
          <div class="cta">
            <a class="btn btn-primary" href="#connect">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
              Let's connect
            </a>
            <a class="btn btn-ghost" href="https://github.com/jakariahossinsv" target="_blank" rel="noopener">
              <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2A10 10 0 0 0 8.8 21.5c.5.1.7-.2.7-.5v-1.7c-2.8.6-3.4-1.3-3.4-1.3-.5-1.2-1.1-1.5-1.1-1.5-.9-.6.1-.6.1-.6 1 .1 1.5 1 1.5 1 .9 1.6 2.4 1.1 3 .8.1-.6.3-1.1.6-1.4-2.2-.2-4.6-1.1-4.6-4.9 0-1.1.4-2 1-2.7-.1-.3-.4-1.3.1-2.6 0 0 .8-.3 2.7 1a9.4 9.4 0 0 1 5 0c1.9-1.3 2.7-1 2.7-1 .5 1.3.2 2.3.1 2.6.6.7 1 1.6 1 2.7 0 3.8-2.4 4.7-4.6 4.9.3.3.6.9.6 1.9v2.8c0 .3.2.6.7.5A10 10 0 0 0 12 2Z"/></svg>
              GitHub
            </a>
          </div>
          <div class="hero-meta">
            <div><div class="num grad" style="-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;background-image:var(--grad)">5+</div><div class="lbl">Languages</div></div>
            <div><div class="num grad" style="-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;background-image:var(--grad)">5</div><div class="lbl">QA skills</div></div>
            <div><div class="num grad" style="-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;background-image:var(--grad)">2024</div><div class="lbl">Journey since</div></div>
          </div>
        </div>

        <!-- ================= PROFILE PHOTO =================
             👉 To add your photo: scroll to the bottom <script> and set
                PROFILE_IMAGE_URL = "your-image-link-here";
             (or paste your link into the src="" of the img below.)          -->
        <div class="portrait" data-reveal>
          <div class="ring"></div>
          <div class="orbit"><span class="dot d1"></span><span class="dot d2"></span><span class="dot d3"></span></div>
          <div class="photo">
            <img id="profilePhoto" src="" alt="Fahim" />
            <div class="photo-ph" id="photoPh">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="8" r="4"/><path d="M4 21c0-4 4-6 8-6s8 2 8 6"/></svg>
              <span>ADD PHOTO</span>
              <small>set link in code</small>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="scroll-hint"><span class="mouse"></span>SCROLL</div>
  </header>

  <!-- ABOUT -->
  <section class="section" id="about">
    <div class="container">
      <p class="eyebrow" data-reveal>about</p>
      <h2 class="h2" data-reveal>A curious builder chasing AI, testing<br/>and smart technology.</h2>
      <div class="about-grid">
        <div data-reveal>
          <p>I'm a <strong>QA enthusiast and AI &amp; IoT explorer</strong>, learning by building real things. My goal is to become an <strong>AI journalist and tech storyteller</strong> — someone who both understands the technology deeply and can explain it clearly.</p>
          <p>Right now I'm deep in <strong>C, C++, Java, Python and SQL</strong>, while sharpening my instincts for system testing, automation and quality assurance. I'm curious about how smart systems are built, broken, and made reliable.</p>
          <p>Every project is a new adventure — I like to create, test, and keep learning.</p>
        </div>
        <div class="panel spec" data-reveal data-delay="120">
          <div class="row"><span class="k">University</span><span class="v">Daffodil Int'l University</span></div>
          <div class="row"><span class="k">Goal</span><span class="v accent">AI Journalist &amp; Storyteller</span></div>
          <div class="row"><span class="k">Focus</span><span class="v">AI · IoT · SQA · DevOps</span></div>
          <div class="row"><span class="k">Learning</span><span class="v">C · C++ · Java · Python</span></div>
          <div class="row"><span class="k">Since</span><span class="v">July 2024</span></div>
          <div class="row"><span class="k">Status</span><span class="v accent">Always learning</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="section" id="skills">
    <div class="container">
      <p class="eyebrow" data-reveal>skills</p>
      <h2 class="h2" data-reveal>Diagnostics &amp; tech stack</h2>
      <p class="lead" data-reveal>A live readout of what I'm working with — self-assessed as an enthusiastic learner.</p>

      <div class="skills-wrap" data-reveal>
        <p class="sub">Languages</p>
        <div class="skill" data-val="82">
          <div class="skill-head"><span class="name">Python <span class="tag">// scripting · AI</span></span><span class="skill-val">0%</span></div>
          <div class="skill-track"><div class="skill-fill"></div></div>
        </div>
        <div class="skill" data-val="78">
          <div class="skill-head"><span class="name">C <span class="tag">// fundamentals</span></span><span class="skill-val">0%</span></div>
          <div class="skill-track"><div class="skill-fill"></div></div>
        </div>
        <div class="skill" data-val="72">
          <div class="skill-head"><span class="name">Java <span class="tag">// OOP</span></span><span class="skill-val">0%</span></div>
          <div class="skill-track"><div class="skill-fill"></div></div>
        </div>
        <div class="skill" data-val="68">
          <div class="skill-head"><span class="name">C++ <span class="tag">// DSA</span></span><span class="skill-val">0%</span></div>
          <div class="skill-track"><div class="skill-fill"></div></div>
        </div>
        <div class="skill" data-val="70">
          <div class="skill-head"><span class="name">SQL <span class="tag">// databases</span></span><span class="skill-val">0%</span></div>
          <div class="skill-track"><div class="skill-fill"></div></div>
        </div>
      </div>

      <div class="cols-2">
        <div class="panel" data-reveal>
          <p class="sub">QA &amp; Testing</p>
          <div class="chips">
            <span class="chip"><span class="dot"></span>Manual Testing</span>
            <span class="chip"><span class="dot"></span>Regression Testing</span>
            <span class="chip"><span class="dot"></span>API Testing</span>
            <span class="chip"><span class="dot"></span>Bug Reporting</span>
            <span class="chip"><span class="dot"></span>System Testing</span>
          </div>
        </div>
        <div class="panel" data-reveal data-delay="120">
          <p class="sub">Tools &amp; Platforms</p>
          <div class="chips">
            <span class="chip"><span class="dot" style="background:#F05032;box-shadow:0 0 8px #F05032"></span>Git</span>
            <span class="chip"><span class="dot" style="background:#fff;box-shadow:0 0 8px #fff"></span>GitHub</span>
            <span class="chip"><span class="dot" style="background:#007ACC;box-shadow:0 0 8px #007ACC"></span>VS Code</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOCUS + INTERESTS -->
  <section class="section" id="focus">
    <div class="container">
      <p class="eyebrow" data-reveal>focus</p>
      <h2 class="h2" data-reveal>What I'm exploring right now</h2>
      <div class="focus-grid">
        <div class="panel" data-reveal>
          <p class="sub">Interests</p>
          <div class="pills">
            <span class="pill">AI</span>
            <span class="pill">Automation</span>
            <span class="pill">IoT</span>
            <span class="pill">SQA</span>
            <span class="pill">DevOps</span>
          </div>
        </div>
        <div class="panel" data-reveal data-delay="120">
          <p class="sub">Current log</p>
          <ul class="log">
            <li><span class="mk">▹</span><span>Exploring <b>AI, Automation &amp; IoT</b></span></li>
            <li><span class="mk">▹</span><span>Learning <b>QA best practices, SQA &amp; DevOps</b></span></li>
            <li><span class="mk">▹</span><span>Experimenting with <b>smart systems &amp; emerging tech</b></span></li>
            <li><span class="mk">▹</span><span>Building skills through <b>hands-on projects</b></span></li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- ACTIVITY -->
  <section class="section" id="activity">
    <div class="container">
      <p class="eyebrow" data-reveal>activity</p>
      <h2 class="h2" data-reveal>Live GitHub signal</h2>
      <p class="lead" data-reveal>Pulled straight from my GitHub profile — updates on their own.</p>
      <div class="stats-grid">
        <div class="panel stat-card" data-reveal>
          <img loading="lazy" alt="Fahim's GitHub stats" src="https://github-readme-stats.vercel.app/api?username=jakariahossinsv&show_icons=true&theme=tokyonight&hide_border=true&border_radius=15&bg_color=00000000&title_color=2DE2E6&icon_color=8B5CFF&text_color=93A0C4" />
        </div>
        <div class="panel stat-card" data-reveal data-delay="120">
          <img loading="lazy" alt="Fahim's GitHub streak" src="https://github-readme-streak-stats.herokuapp.com/?user=jakariahossinsv&theme=tokyonight&hide_border=true&border_radius=15&background=00000000&ring=8B5CFF&fire=FF5DA2&currStreakLabel=2DE2E6" />
        </div>
        <div class="panel stat-card wide" data-reveal>
          <img loading="lazy" alt="Fahim's top languages" style="max-width:420px" src="https://github-readme-stats.vercel.app/api/top-langs/?username=jakariahossinsv&layout=compact&theme=tokyonight&hide_border=true&border_radius=15&bg_color=00000000&title_color=2DE2E6&text_color=93A0C4" />
        </div>
      </div>
    </div>
  </section>

  <!-- CONNECT -->
  <section class="section" id="connect">
    <div class="container">
      <p class="eyebrow" data-reveal>connect</p>
      <div class="connect-grid">
        <div data-reveal>
          <p class="quote">"Keep learning, keep building, and <span class="grad">stay curious.</span>"</p>
          <p class="lead">Open to collaboration, learning together, and interesting tech conversations.</p>
        </div>
        <div class="socials" data-reveal data-delay="120">
          <a class="social" href="https://github.com/jakariahossinsv" target="_blank" rel="noopener">
            <span class="ico gh"><svg viewBox="0 0 24 24"><path d="M12 2A10 10 0 0 0 8.8 21.5c.5.1.7-.2.7-.5v-1.7c-2.8.6-3.4-1.3-3.4-1.3-.5-1.2-1.1-1.5-1.1-1.5-.9-.6.1-.6.1-.6 1 .1 1.5 1 1.5 1 .9 1.6 2.4 1.1 3 .8.1-.6.3-1.1.6-1.4-2.2-.2-4.6-1.1-4.6-4.9 0-1.1.4-2 1-2.7-.1-.3-.4-1.3.1-2.6 0 0 .8-.3 2.7 1a9.4 9.4 0 0 1 5 0c1.9-1.3 2.7-1 2.7-1 .5 1.3.2 2.3.1 2.6.6.7 1 1.6 1 2.7 0 3.8-2.4 4.7-4.6 4.9.3.3.6.9.6 1.9v2.8c0 .3.2.6.7.5A10 10 0 0 0 12 2Z"/></svg></span>
            <span class="txt"><div class="t">GitHub</div><div class="s">@jakariahossinsv</div></span>
            <span class="arrow">↗</span>
          </a>
          <a class="social" href="https://www.linkedin.com/in/jakaria-hossin" target="_blank" rel="noopener">
            <span class="ico li"><svg viewBox="0 0 24 24"><path d="M4.98 3.5A2.5 2.5 0 1 1 5 8.5a2.5 2.5 0 0 1 0-5ZM3 9h4v12H3V9Zm7 0h3.8v1.7h.05c.53-1 1.83-2.05 3.77-2.05 4 0 4.75 2.65 4.75 6.1V21H18v-5.3c0-1.27-.02-2.9-1.77-2.9-1.77 0-2.04 1.38-2.04 2.8V21H10V9Z"/></svg></span>
            <span class="txt"><div class="t">LinkedIn</div><div class="s">in/jakaria-hossin</div></span>
            <span class="arrow">↗</span>
          </a>
          <a class="social" href="https://www.facebook.com/jakaria.hossin.222753" target="_blank" rel="noopener">
            <span class="ico fb"><svg viewBox="0 0 24 24"><path d="M22 12a10 10 0 1 0-11.56 9.88v-6.99H7.9V12h2.54V9.8c0-2.5 1.49-3.89 3.77-3.89 1.09 0 2.24.2 2.24.2v2.46h-1.26c-1.24 0-1.63.77-1.63 1.56V12h2.78l-.44 2.89h-2.34v6.99A10 10 0 0 0 22 12Z"/></svg></span>
            <span class="txt"><div class="t">Facebook</div><div class="s">jakaria.hossin</div></span>
            <span class="arrow">↗</span>
          </a>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      Built with <span class="grad">curiosity</span> ✦ Fahim © <span id="year"></span> — "Learning never stops."
    </div>
  </footer>

<script>
(function(){
  'use strict';

  /* ============================================================
     👇  PASTE YOUR IMAGE LINK BETWEEN THE QUOTES BELOW  👇
     Example: const PROFILE_IMAGE_URL = "https://i.ibb.co/xxxx/me.jpg";
     Leave it empty ("") to keep the placeholder.
  ============================================================ */
  const PROFILE_IMAGE_URL = "";

  const reduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  document.addEventListener('DOMContentLoaded', function(){
    // year
    var y = document.getElementById('year'); if(y) y.textContent = new Date().getFullYear();

    // profile image
    var img = document.getElementById('profilePhoto');
    var ph = document.getElementById('photoPh');
    if(img && PROFILE_IMAGE_URL && PROFILE_IMAGE_URL.trim() !== ''){
      img.onload = function(){ img.classList.add('show'); if(ph) ph.style.display='none'; };
      img.onerror = function(){ img.classList.remove('show'); if(ph) ph.style.display='flex'; };
      img.src = PROFILE_IMAGE_URL.trim();
    }

    initTyping();
    initReveal();
    initSkills();
    initScrollProgress();
    initNav();
    if(!reduce) initParticles();
  });

  function initTyping(){
    var el = document.getElementById('typedRole');
    if(!el) return;
    var roles = ["QA Enthusiast","AI & IoT Explorer","Automation Learner","Future DevOps Engineer","AI Journalist & Tech Storyteller"];
    if(reduce){ el.textContent = roles[0]; return; }
    var r=0,c=0,del=false;
    function tick(){
      var w = roles[r];
      if(!del){ c++; el.textContent = w.slice(0,c);
        if(c===w.length){ del=true; setTimeout(tick,1500); return; } }
      else { c--; el.textContent = w.slice(0,c);
        if(c===0){ del=false; r=(r+1)%roles.length; } }
      setTimeout(tick, del?42:88);
    }
    tick();
  }

  function initReveal(){
    var els = document.querySelectorAll('[data-reveal]');
    if(reduce || !('IntersectionObserver' in window)){
      els.forEach(function(e){ e.classList.add('in-view'); }); return;
    }
    var io = new IntersectionObserver(function(entries){
      entries.forEach(function(en){
        if(en.isIntersecting){
          var d = parseInt(en.target.getAttribute('data-delay'),10) || 0;
          setTimeout(function(){ en.target.classList.add('in-view'); }, d);
          io.unobserve(en.target);
        }
      });
    },{threshold:0.14});
    els.forEach(function(e){ io.observe(e); });
  }

  function initSkills(){
    var bars = document.querySelectorAll('.skill');
    if(!('IntersectionObserver' in window)){ bars.forEach(activate); return; }
    var io = new IntersectionObserver(function(entries){
      entries.forEach(function(en){ if(en.isIntersecting){ activate(en.target); io.unobserve(en.target); } });
    },{threshold:0.45});
    bars.forEach(function(b){ io.observe(b); });
  }
  function activate(bar){
    var val = parseInt(bar.getAttribute('data-val'),10) || 0;
    var fill = bar.querySelector('.skill-fill');
    var num = bar.querySelector('.skill-val');
    if(fill) fill.style.width = val + '%';
    if(reduce){ if(num) num.textContent = val + '%'; return; }
    var cur=0, step = Math.max(1, Math.round(val/40));
    var t = setInterval(function(){
      cur += step; if(cur>=val){ cur=val; clearInterval(t); }
      if(num) num.textContent = cur + '%';
    }, 20);
  }

  function initScrollProgress(){
    var bar = document.getElementById('scrollbar');
    if(!bar) return;
    function upd(){
      var h = document.documentElement;
      var max = h.scrollHeight - h.clientHeight;
      bar.style.width = (max>0 ? (h.scrollTop/max)*100 : 0) + '%';
    }
    window.addEventListener('scroll', upd, {passive:true}); upd();
  }

  function initNav(){
    var nav = document.getElementById('nav');
    if(!nav) return;
    function upd(){ if(window.scrollY>40) nav.classList.add('solid'); else nav.classList.remove('solid'); }
    window.addEventListener('scroll', upd, {passive:true}); upd();
  }

  function initParticles(){
    var canvas = document.getElementById('net');
    if(!canvas || !canvas.getContext) return;
    var ctx = canvas.getContext('2d');
    var w,h,pts, DPR = Math.min(window.devicePixelRatio||1, 2);
    function resize(){
      w = canvas.clientWidth; h = canvas.clientHeight;
      canvas.width = w*DPR; canvas.height = h*DPR;
      ctx.setTransform(DPR,0,0,DPR,0,0);
      var n = Math.min(64, Math.max(24, Math.floor(w/18)));
      pts = [];
      for(var i=0;i<n;i++){ pts.push({x:Math.random()*w,y:Math.random()*h,vx:(Math.random()-.5)*.28,vy:(Math.random()-.5)*.28}); }
    }
    function draw(){
      ctx.clearRect(0,0,w,h);
      var i,j;
      for(i=0;i<pts.length;i++){ var p=pts[i]; p.x+=p.vx; p.y+=p.vy;
        if(p.x<0||p.x>w)p.vx*=-1; if(p.y<0||p.y>h)p.vy*=-1; }
      for(i=0;i<pts.length;i++){
        for(j=i+1;j<pts.length;j++){
          var a=pts[i],b=pts[j],dx=a.x-b.x,dy=a.y-b.y,dist=Math.sqrt(dx*dx+dy*dy);
          if(dist<128){ var o=(1-dist/128)*.45;
            ctx.strokeStyle='rgba(45,226,230,'+o+')'; ctx.lineWidth=1;
            ctx.beginPath(); ctx.moveTo(a.x,a.y); ctx.lineTo(b.x,b.y); ctx.stroke(); }
        }
      }
      for(i=0;i<pts.length;i++){ ctx.fillStyle='rgba(139,92,255,.9)';
        ctx.beginPath(); ctx.arc(pts[i].x,pts[i].y,1.6,0,Math.PI*2); ctx.fill(); }
      requestAnimationFrame(draw);
    }
    resize(); draw();
    var to; window.addEventListener('resize', function(){ clearTimeout(to); to=setTimeout(resize,200); });
  }
})();
</script>
</body>
</html>
