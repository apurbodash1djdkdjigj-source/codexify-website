# codexify-website
we read your online business
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Codexify — Global Digital Agency · Bangladesh</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=Bricolage+Grotesque:opsz,wght@12..96,200;12..96,300;12..96,400;12..96,500;12..96,600;12..96,700;12..96,800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
/* ════════════════════════════════════════
   ROOT & RESET
════════════════════════════════════════ */
:root {
  --bg:      #04050F;
  --bg2:     #060812;
  --surface: #0A0D1E;
  --card:    #0D1128;
  --b:       rgba(255,255,255,0.07);
  --b2:      rgba(255,255,255,0.12);
  --blue:    #5B8FFF;
  --indigo:  #7C5CFC;
  --violet:  #A855F7;
  --pink:    #EC4899;
  --cyan:    #06B6D4;
  --teal:    #14B8A6;
  --lime:    #84CC16;
  --amber:   #F59E0B;
  --white:   #F1F5FF;
  --muted:   #4B5680;
  --dim:     #2A3060;
  --r10:     10px;
  --r16:     16px;
  --r20:     20px;
  --r24:     24px;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;-webkit-font-smoothing:antialiased}
body{
  background:var(--bg);color:var(--white);
  font-family:'Bricolage Grotesque',sans-serif;
  overflow-x:hidden;cursor:none;
}
a{text-decoration:none;cursor:none}
button{cursor:none;font-family:inherit}
img{display:block;max-width:100%}
::selection{background:rgba(91,143,255,.3);color:#fff}

/* ════════════════════════════════════════
   SCROLLBAR
════════════════════════════════════════ */
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{
  background:linear-gradient(var(--blue),var(--violet));
  border-radius:4px;
}

/* ════════════════════════════════════════
   CURSOR
════════════════════════════════════════ */
#cur-dot{
  position:fixed;width:8px;height:8px;
  background:#fff;border-radius:50%;
  pointer-events:none;z-index:9999;
  transform:translate(-50%,-50%);
  transition:width .15s,height .15s,background .2s;
  mix-blend-mode:difference;
}
#cur-trail{
  position:fixed;width:36px;height:36px;
  border:1.5px solid rgba(91,143,255,.6);
  border-radius:50%;pointer-events:none;z-index:9998;
  transform:translate(-50%,-50%);
  transition:transform .4s cubic-bezier(.2,1,.2,1);
}
body:has(a:hover) #cur-dot,
body:has(button:hover) #cur-dot{width:20px;height:20px}

/* ════════════════════════════════════════
   GRAIN OVERLAY
════════════════════════════════════════ */
#grain{
  position:fixed;inset:0;z-index:998;
  pointer-events:none;opacity:.028;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='f'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23f)' opacity='1'/%3E%3C/svg%3E");
  background-size:200px 200px;
}

/* ════════════════════════════════════════
   BACKGROUND AURORA
════════════════════════════════════════ */
#aurora{
  position:fixed;inset:0;z-index:0;
  pointer-events:none;overflow:hidden;
}
.aurora-blob{
  position:absolute;border-radius:50%;
  filter:blur(140px);
  will-change:transform;
}
.ab1{
  width:800px;height:800px;
  top:-300px;right:-200px;
  background:radial-gradient(circle at 40% 40%,rgba(91,143,255,.22) 0%,transparent 65%);
  animation:aurDrift 20s ease-in-out infinite;
}
.ab2{
  width:700px;height:700px;
  bottom:-250px;left:-180px;
  background:radial-gradient(circle at 60% 60%,rgba(168,85,247,.18) 0%,transparent 65%);
  animation:aurDrift 16s ease-in-out infinite reverse;
  animation-delay:-8s;
}
.ab3{
  width:500px;height:500px;
  top:35%;left:40%;
  background:radial-gradient(circle at 50% 50%,rgba(6,182,212,.12) 0%,transparent 65%);
  animation:aurDrift 24s ease-in-out infinite;
  animation-delay:-12s;
}
.ab4{
  width:400px;height:400px;
  bottom:20%;right:10%;
  background:radial-gradient(circle at 50% 50%,rgba(236,72,153,.1) 0%,transparent 65%);
  animation:aurDrift 18s ease-in-out infinite reverse;
  animation-delay:-5s;
}
@keyframes aurDrift{
  0%,100%{transform:translate(0,0) scale(1)}
  25%{transform:translate(50px,-30px) scale(1.04)}
  50%{transform:translate(-30px,60px) scale(.97)}
  75%{transform:translate(40px,20px) scale(1.02)}
}

/* ════════════════════════════════════════
   GRID DOTS
════════════════════════════════════════ */
#dots{
  position:fixed;inset:0;z-index:0;pointer-events:none;
  background-image:radial-gradient(circle,rgba(91,143,255,.12) 1px,transparent 1px);
  background-size:40px 40px;
  mask-image:radial-gradient(ellipse 80% 80% at 50% 50%,#000 40%,transparent 100%);
}

/* ════════════════════════════════════════
   NAV
════════════════════════════════════════ */
#nav{
  position:fixed;top:0;left:0;right:0;z-index:500;
  height:68px;
  display:flex;align-items:center;justify-content:space-between;
  padding:0 clamp(1.5rem,4vw,5rem);
  transition:background .4s,border-color .4s,backdrop-filter .4s;
}
#nav.scrolled{
  background:rgba(4,5,15,.75);
  backdrop-filter:blur(32px) saturate(1.6);
  border-bottom:1px solid var(--b);
}
.nav-logo{display:flex;align-items:center;gap:11px}
.nav-cx{width:36px;height:36px}
.nav-wm{
  font-family:'Syne',sans-serif;
  font-size:1.2rem;font-weight:800;letter-spacing:-.03em;
  background:linear-gradient(110deg,#fff 0%,#aac4ff 55%,#c49cff 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.nav-links{display:flex;gap:2rem;align-items:center}
.nav-links a{
  font-size:.8rem;font-weight:500;letter-spacing:.01em;
  color:var(--muted);transition:color .25s;position:relative;
}
.nav-links a:hover{color:var(--white)}
.nav-pill{
  display:flex;align-items:center;gap:7px;
  padding:8px 20px;border-radius:100px;
  background:linear-gradient(135deg,rgba(91,143,255,.12),rgba(124,92,252,.12));
  border:1px solid rgba(91,143,255,.22);
  font-size:.76rem;font-weight:700;letter-spacing:.02em;
  color:var(--white);
  transition:border-color .25s,box-shadow .25s;
}
.nav-pill:hover{
  border-color:rgba(91,143,255,.45);
  box-shadow:0 0 28px rgba(91,143,255,.2);
}
.pulse-dot{
  width:6px;height:6px;border-radius:50%;
  background:var(--lime);
  box-shadow:0 0 8px var(--lime);
  animation:pulse 2s infinite;
}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.5;transform:scale(1.5)}}

/* ════════════════════════════════════════
   HERO
════════════════════════════════════════ */
#hero{
  position:relative;z-index:1;
  min-height:100vh;
  display:flex;flex-direction:column;
  justify-content:center;align-items:center;
  text-align:center;
  padding:120px clamp(1.5rem,6vw,8rem) 100px;
  overflow:hidden;
}

/* Horizontal light beam */
#hero::before{
  content:'';
  position:absolute;top:50%;left:50%;
  transform:translate(-50%,-50%);
  width:120%;height:1px;
  background:linear-gradient(90deg,
    transparent 0%,
    rgba(91,143,255,.15) 20%,
    rgba(124,92,252,.3) 50%,
    rgba(91,143,255,.15) 80%,
    transparent 100%);
  pointer-events:none;
}

.hero-eyebrow{
  display:inline-flex;align-items:center;gap:10px;
  background:rgba(91,143,255,.07);
  border:1px solid rgba(91,143,255,.18);
  border-radius:100px;
  padding:6px 18px;
  font-family:'DM Mono',monospace;
  font-size:.65rem;font-weight:400;letter-spacing:.18em;
  text-transform:uppercase;color:rgba(170,196,255,.7);
  margin-bottom:2.2rem;
  animation:fadeSlideDown .8s ease both;
}
.hero-eyebrow::before{
  content:'';width:6px;height:6px;border-radius:50%;
  background:var(--lime);box-shadow:0 0 10px var(--lime);
  animation:pulse 2s infinite;
}

@keyframes fadeSlideDown{from{opacity:0;transform:translateY(-16px)}to{opacity:1;transform:none}}
@keyframes fadeSlideUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:none}}

/* HERO HEADLINE */
.hero-h{
  font-family:'Syne',sans-serif;
  font-size:clamp(3.2rem,7.5vw,8rem);
  font-weight:800;letter-spacing:-.05em;line-height:.96;
  margin-bottom:2rem;
}
.hero-h .line1{
  display:block;color:var(--white);
  animation:fadeSlideUp .8s .1s ease both;
}
.hero-h .line2{
  display:block;
  background:linear-gradient(120deg,
    var(--blue) 0%,
    var(--indigo) 30%,
    var(--violet) 60%,
    var(--pink) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
  background-size:300% 100%;
  animation:fadeSlideUp .8s .2s ease both, gradMove 5s linear infinite;
}
.hero-h .line3{
  display:block;color:rgba(241,245,255,.25);
  animation:fadeSlideUp .8s .3s ease both;
}
@keyframes gradMove{
  0%{background-position:0% 50%}
  100%{background-position:300% 50%}
}

.hero-sub{
  font-size:clamp(.9rem,1.5vw,1.15rem);
  font-weight:300;line-height:1.9;
  color:rgba(241,245,255,.45);
  max-width:580px;
  margin:0 auto 2.8rem;
  animation:fadeSlideUp .8s .4s ease both;
}
.hero-sub em{color:rgba(241,245,255,.85);font-style:normal;font-weight:500}

.hero-ctas{
  display:flex;gap:.9rem;justify-content:center;flex-wrap:wrap;
  margin-bottom:4.5rem;
  animation:fadeSlideUp .8s .5s ease both;
}

/* Primary CTA */
.cta-main{
  position:relative;overflow:hidden;
  display:inline-flex;align-items:center;gap:10px;
  padding:.9rem 2.2rem;
  border-radius:12px;border:none;
  background:linear-gradient(135deg,var(--blue),var(--indigo));
  color:#fff;font-size:.9rem;font-weight:700;letter-spacing:.01em;
  box-shadow:0 8px 40px rgba(91,143,255,.35),inset 0 1px 0 rgba(255,255,255,.15);
  transition:transform .2s,box-shadow .2s;
}
.cta-main::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(to bottom,rgba(255,255,255,.12),transparent);
  pointer-events:none;
}
.cta-main:hover{
  transform:translateY(-3px) scale(1.01);
  box-shadow:0 16px 60px rgba(91,143,255,.5),inset 0 1px 0 rgba(255,255,255,.15);
}
.cta-main .arr{
  display:inline-block;
  transition:transform .2s;
}
.cta-main:hover .arr{transform:translateX(4px)}

/* Ghost CTA */
.cta-ghost{
  display:inline-flex;align-items:center;gap:9px;
  padding:.9rem 2.2rem;border-radius:12px;
  background:rgba(255,255,255,.04);
  border:1px solid rgba(255,255,255,.1);
  color:rgba(241,245,255,.7);
  font-size:.9rem;font-weight:500;
  transition:background .2s,border-color .2s,color .2s;
}
.cta-ghost:hover{
  background:rgba(255,255,255,.08);
  border-color:rgba(255,255,255,.2);
  color:var(--white);
}

/* PARTNER BADGES */
.hero-partners{
  display:flex;align-items:center;gap:1.5rem;
  justify-content:center;flex-wrap:wrap;
  animation:fadeSlideUp .8s .65s ease both;
}
.hp-label{
  font-family:'DM Mono',monospace;
  font-size:.62rem;letter-spacing:.14em;text-transform:uppercase;
  color:var(--muted);
}
.hp-sep{width:1px;height:18px;background:var(--b2)}
.hp-badge{
  display:flex;align-items:center;gap:8px;
  background:rgba(255,255,255,.04);
  border:1px solid rgba(255,255,255,.08);
  border-radius:10px;padding:6px 15px;
  font-size:.76rem;font-weight:600;
  color:rgba(241,245,255,.5);
  transition:border-color .2s,color .2s,box-shadow .2s;
}
.hp-badge:hover{
  border-color:rgba(255,255,255,.18);
  color:var(--white);
  box-shadow:0 0 20px rgba(0,0,0,.3);
}
.hpb-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0}
.d-b44{background:var(--blue);box-shadow:0 0 8px var(--blue)}
.d-lv{background:var(--violet);box-shadow:0 0 8px var(--violet)}

/* SCROLL INDICATOR */
.scroll-ind{
  position:absolute;bottom:2.5rem;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  animation:fadeSlideUp .8s .9s ease both;
}
.scroll-ind span{
  font-family:'DM Mono',monospace;
  font-size:.55rem;letter-spacing:.2em;text-transform:uppercase;
  color:var(--muted);
}
.scroll-mouse{
  width:22px;height:34px;
  border:1.5px solid rgba(255,255,255,.15);
  border-radius:100px;
  display:flex;justify-content:center;padding-top:6px;
}
.scroll-wheel{
  width:3px;height:6px;background:var(--blue);
  border-radius:3px;
  animation:scrollW 2s ease-in-out infinite;
}
@keyframes scrollW{
  0%{transform:translateY(0);opacity:1}
  80%{transform:translateY(12px);opacity:0}
  81%{transform:translateY(0);opacity:0}
  100%{opacity:1}
}

/* ════════════════════════════════════════
   MARQUEE STRIP
════════════════════════════════════════ */
.marquee-wrap{
  position:relative;z-index:1;overflow:hidden;
  background:var(--bg2);
  border-top:1px solid var(--b);border-bottom:1px solid var(--b);
  padding:.85rem 0;
}
.marquee-track{
  display:flex;gap:0;
  animation:marqueeRoll 28s linear infinite;
  width:max-content;
}
.marquee-track:hover{animation-play-state:paused}
@keyframes marqueeRoll{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.mi{
  display:inline-flex;align-items:center;gap:.7rem;
  padding:0 2.5rem;
  font-family:'DM Mono',monospace;
  font-size:.68rem;font-weight:400;letter-spacing:.12em;
  text-transform:uppercase;color:var(--muted);
  white-space:nowrap;
}
.mi .gem{
  font-size:.9rem;
  background:linear-gradient(135deg,var(--blue),var(--violet));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
}

/* ════════════════════════════════════════
   SECTION BASICS
════════════════════════════════════════ */
.section{
  position:relative;z-index:1;
  padding:clamp(5rem,8vw,9rem) clamp(1.5rem,5vw,6rem);
}
.s-bg2{background:var(--bg2)}
.s-eyebrow{
  display:inline-flex;align-items:center;gap:10px;
  font-family:'DM Mono',monospace;
  font-size:.62rem;font-weight:400;letter-spacing:.2em;
  text-transform:uppercase;color:var(--blue);
  margin-bottom:.9rem;
}
.s-eyebrow::before{
  content:'';width:20px;height:1px;
  background:linear-gradient(90deg,var(--blue),transparent);
}
.s-title{
  font-family:'Syne',sans-serif;
  font-size:clamp(1.9rem,3.5vw,3.2rem);
  font-weight:800;letter-spacing:-.04em;line-height:1.08;
  margin-bottom:.9rem;
}
.s-sub{
  font-size:.95rem;font-weight:300;
  color:rgba(241,245,255,.45);
  line-height:1.9;max-width:520px;
}

/* ════════════════════════════════════════
   MARQUEE NUMBERS (IMPACT SECTION)
════════════════════════════════════════ */
.impact-section{
  position:relative;z-index:1;
  padding:clamp(4rem,6vw,6rem) clamp(1.5rem,5vw,6rem);
  background:var(--surface);
  border-top:1px solid var(--b);
  border-bottom:1px solid var(--b);
}
.impact-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:1px;
  background:var(--b);
}
.impact-item{
  padding:2.5rem 2rem;
  background:var(--surface);
  text-align:center;
  transition:background .25s;
}
.impact-item:hover{background:var(--card)}
.impact-num{
  font-family:'Syne',sans-serif;
  font-size:clamp(2rem,4vw,3.5rem);
  font-weight:800;letter-spacing:-.04em;
  line-height:1;
  background:linear-gradient(135deg,var(--blue),var(--cyan));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  margin-bottom:.4rem;
}
.impact-lbl{
  font-size:.72rem;font-weight:500;letter-spacing:.08em;
  text-transform:uppercase;color:var(--muted);
}

/* ════════════════════════════════════════
   WHY BD
════════════════════════════════════════ */
.why-grid{
  display:grid;grid-template-columns:1fr 1fr;
  gap:5rem;align-items:center;
  margin-top:4rem;
}
.why-text p{
  font-size:.93rem;font-weight:300;line-height:1.95;
  color:rgba(241,245,255,.5);margin-bottom:1rem;
}
.why-text p strong{color:var(--white);font-weight:600}
.why-checks{
  margin-top:2rem;
  display:grid;grid-template-columns:1fr 1fr;
  gap:.4rem .8rem;
}
.wc{
  display:flex;align-items:center;gap:10px;
  padding:.7rem;border-radius:10px;
  font-size:.8rem;color:rgba(241,245,255,.55);
  transition:background .2s,color .2s;
}
.wc:hover{background:var(--card);color:var(--white)}
.wc-check{
  width:20px;height:20px;flex-shrink:0;
  border-radius:6px;
  background:linear-gradient(135deg,rgba(91,143,255,.15),rgba(124,92,252,.15));
  border:1px solid rgba(91,143,255,.2);
  display:flex;align-items:center;justify-content:center;
  font-size:.65rem;
}

.why-stats{display:flex;flex-direction:column;gap:1rem}
.ws-card{
  background:var(--card);
  border:1px solid var(--b);
  border-radius:20px;
  padding:1.8rem 2rem;
  position:relative;overflow:hidden;
  transition:transform .3s,border-color .3s;
}
.ws-card::before{
  content:'';
  position:absolute;top:0;left:0;bottom:0;width:2px;
  background:linear-gradient(180deg,var(--blue),var(--violet));
  border-radius:2px 0 0 2px;
  opacity:0;transition:opacity .3s;
}
.ws-card:hover{transform:translateX(6px);border-color:rgba(91,143,255,.2)}
.ws-card:hover::before{opacity:1}
.ws-n{
  font-family:'Syne',sans-serif;
  font-size:clamp(2rem,3.5vw,2.8rem);
  font-weight:800;letter-spacing:-.04em;line-height:1;
  background:linear-gradient(120deg,var(--blue),var(--cyan));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;margin-bottom:.3rem;
}
.ws-l{font-size:.78rem;font-weight:400;color:var(--muted);line-height:1.5}

/* ════════════════════════════════════════
   PARTNERS
════════════════════════════════════════ */
.partners-section{background:var(--bg)}
.partners-intro{text-align:center;margin-bottom:5rem}
.partners-intro .s-eyebrow{justify-content:center}
.partners-intro .s-sub{margin:0 auto;text-align:center}

.p-cards{
  display:grid;grid-template-columns:1fr 1fr;
  gap:2rem;max-width:900px;margin:0 auto;
}
.pc{
  position:relative;overflow:hidden;
  border-radius:28px;
  padding:3.5rem 3rem;
  border:1px solid transparent;
  background:var(--card);
  transition:transform .35s cubic-bezier(.2,1,.2,1);
}
.pc:hover{transform:translateY(-10px)}

.pc-b44{
  background:linear-gradient(var(--card),var(--card)) padding-box,
             linear-gradient(135deg,rgba(91,143,255,.3),rgba(6,182,212,.3)) border-box;
}
.pc-b44:hover{
  box-shadow:0 30px 80px rgba(91,143,255,.12);
}
.pc-lv{
  background:linear-gradient(var(--card),var(--card)) padding-box,
             linear-gradient(135deg,rgba(168,85,247,.3),rgba(236,72,153,.3)) border-box;
}
.pc-lv:hover{
  box-shadow:0 30px 80px rgba(168,85,247,.1);
}

/* glow top line */
.pc::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;opacity:.9;
}
.pc-b44::before{background:linear-gradient(90deg,transparent 5%,var(--blue) 30%,var(--cyan) 70%,transparent 95%)}
.pc-lv::before{background:linear-gradient(90deg,transparent 5%,var(--violet) 30%,var(--pink) 70%,transparent 95%)}

/* ambient glow behind */
.pc-glow{
  position:absolute;top:-40%;right:-20%;
  width:300px;height:300px;border-radius:50%;
  opacity:.07;pointer-events:none;
}
.pc-b44 .pc-glow{background:radial-gradient(var(--blue),transparent)}
.pc-lv  .pc-glow{background:radial-gradient(var(--violet),transparent)}

.pc-icon{
  width:68px;height:68px;border-radius:20px;
  display:flex;align-items:center;justify-content:center;
  font-size:2rem;margin-bottom:1.8rem;
}
.pc-b44 .pc-icon{
  background:linear-gradient(135deg,rgba(91,143,255,.12),rgba(6,182,212,.07));
  border:1px solid rgba(91,143,255,.2);
}
.pc-lv .pc-icon{
  background:linear-gradient(135deg,rgba(168,85,247,.12),rgba(236,72,153,.07));
  border:1px solid rgba(168,85,247,.2);
}

.pc-name{
  font-family:'Syne',sans-serif;
  font-size:1.5rem;font-weight:800;letter-spacing:-.03em;
  margin-bottom:.2rem;
}
.pc-b44 .pc-name{
  background:linear-gradient(120deg,var(--blue),var(--cyan));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.pc-lv .pc-name{
  background:linear-gradient(120deg,var(--violet),var(--pink));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.pc-role{
  font-family:'DM Mono',monospace;
  font-size:.6rem;letter-spacing:.16em;text-transform:uppercase;
  color:var(--muted);margin-bottom:1.4rem;
}
.pc-desc{
  font-size:.87rem;font-weight:300;line-height:1.85;
  color:rgba(241,245,255,.45);
}
.pc-chips{display:flex;flex-wrap:wrap;gap:.45rem;margin-top
