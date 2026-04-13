[renan-site.html](https://github.com/user-attachments/files/26683990/renan-site.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Renan Costa — Código da Presença</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400;1,700&family=Montserrat:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
:root {
  --gold:#C8973E; --gold2:#E2B85A; --gold3:#F4D98A;
  --golddim:#4A3510; --goldborder:#2C2008;
  --black:#040404; --ink:#080706; --dark:#0C0B08;
  --card:#111009; --card2:#181510;
  --border:#1C1A12; --text:#D8D0C0; --muted:#5C5444;
  --white:#F8F4EC; --green:#22C55E;
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{background:var(--black);color:var(--text);font-family:'Montserrat',sans-serif;overflow-x:hidden}
::-webkit-scrollbar{width:3px}
::-webkit-scrollbar-track{background:var(--black)}
::-webkit-scrollbar-thumb{background:var(--golddim)}

/* ── GRAIN ── */
body::after{
  content:'';position:fixed;inset:0;z-index:9999;pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
  opacity:.025;
}

/* ═══════════════════════════════
   PARALLAX SECTIONS
═══════════════════════════════ */
.parallax-section{
  position:relative;overflow:hidden;
}
.parallax-bg{
  position:absolute;inset:-20%;
  background-size:cover;background-position:center;
  will-change:transform;
  transition:transform .1s linear;
}
.parallax-overlay{
  position:absolute;inset:0;
  background:rgba(4,4,4,.82);
  z-index:1;
}
.parallax-content{
  position:relative;z-index:2;
}

/* ═══════════════════════════════
   HERO
═══════════════════════════════ */
.hero{
  min-height:100vh;
  display:grid;grid-template-columns:55% 45%;
  position:relative;overflow:hidden;
}

/* Left dark panel */
.hero-left{
  display:flex;flex-direction:column;justify-content:center;
  padding:110px 64px 80px 72px;
  position:relative;z-index:4;
  background:linear-gradient(to right, var(--black) 0%, rgba(4,4,4,.97) 85%, transparent 100%);
}

/* Gold vertical divider */
.hero::after{
  content:'';position:absolute;
  top:0;bottom:0;left:55%;width:1px;
  background:linear-gradient(to bottom,transparent,var(--gold) 40%,var(--gold) 60%,transparent);
  opacity:.3;z-index:3;
}

.hero-eyebrow{
  display:flex;align-items:center;gap:14px;margin-bottom:32px;
}
.eyebrow-line{width:36px;height:1px;background:linear-gradient(to right,var(--gold),transparent);}
.eyebrow-text{
  font-size:10px;font-weight:700;letter-spacing:6px;
  color:var(--gold);text-transform:uppercase;
}

.hero-name{
  font-family:'Cormorant',serif;
  font-size:clamp(68px,8vw,108px);
  font-weight:700;line-height:.85;
  color:var(--white);letter-spacing:-2px;
}
.hero-name-italic{
  font-family:'Cormorant',serif;
  font-size:clamp(68px,8vw,108px);
  font-weight:300;line-height:.9;
  color:var(--gold2);letter-spacing:-2px;
  font-style:italic;display:block;margin-bottom:24px;
}

.hero-tag{
  display:inline-flex;align-items:center;gap:10px;
  border:1px solid var(--goldborder);padding:8px 18px;
  margin-bottom:32px;width:fit-content;
}
.hero-tag span{font-size:9px;font-weight:700;letter-spacing:4px;color:var(--gold);text-transform:uppercase;}
.tag-dot{width:4px;height:4px;border-radius:50%;background:var(--gold);}

.hero-headline{
  font-family:'Cormorant',serif;
  font-size:clamp(18px,2vw,26px);
  font-weight:300;font-style:italic;
  color:var(--text);line-height:1.6;
  max-width:420px;margin-bottom:36px;
}
.hero-headline strong{font-style:normal;font-weight:600;color:var(--gold3);}

/* Proof row */
.proof-row{
  display:flex;gap:0;border:1px solid var(--border);
  margin-bottom:36px;
}
.proof-item{
  flex:1;padding:16px 18px;
  border-right:1px solid var(--border);
  transition:background .2s;
}
.proof-item:last-child{border-right:none;}
.proof-item:hover{background:var(--card);}
.proof-n{
  font-family:'Cormorant',serif;
  font-size:30px;font-weight:700;color:var(--gold2);line-height:1;
}
.proof-l{font-size:9px;font-weight:600;letter-spacing:2px;color:var(--muted);text-transform:uppercase;margin-top:3px;}

.btn-main{
  display:inline-flex;align-items:center;gap:12px;
  background:var(--gold);color:#000;
  font-family:'Montserrat',sans-serif;
  font-size:11px;font-weight:800;letter-spacing:4px;
  text-transform:uppercase;padding:19px 38px;
  text-decoration:none;transition:all .25s;
  width:fit-content;position:relative;overflow:hidden;
  clip-path:polygon(0 0,calc(100% - 14px) 0,100% 14px,100% 100%,14px 100%,0 calc(100% - 14px));
}
.btn-main::before{
  content:'';position:absolute;top:0;left:-100%;
  width:100%;height:100%;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,.25),transparent);
  transition:left .45s;
}
.btn-main:hover{background:var(--gold2);transform:translateY(-2px);}
.btn-main:hover::before{left:100%;}

.btn-ghost{
  font-size:10px;font-weight:600;letter-spacing:3px;
  color:var(--muted);text-transform:uppercase;
  text-decoration:none;padding:4px 0;
  border-bottom:1px solid var(--border);width:fit-content;
  transition:color .2s,border-color .2s;margin-top:12px;
  display:inline-block;
}
.btn-ghost:hover{color:var(--gold);border-color:var(--golddim);}

/* Hero photo */
.hero-right{position:relative;overflow:hidden;}
.hero-photo-wrap{
  position:absolute;inset:0;
  display:flex;align-items:stretch;
}
.hero-photo-wrap::before{
  content:'';position:absolute;inset:0;z-index:1;
  background:
    linear-gradient(to right,var(--black) 0%,transparent 20%),
    linear-gradient(to left,var(--black) 0%,transparent 8%),
    linear-gradient(to top,var(--black) 0%,transparent 15%);
}
/* green neon glow behind */
.hero-photo-wrap::after{
  content:'';position:absolute;
  width:350px;height:600px;border-radius:50%;
  background:radial-gradient(ellipse,rgba(0,160,70,.14) 0%,transparent 70%);
  top:40%;left:50%;transform:translate(-50%,-50%);z-index:0;
}
.hero-photo-wrap img{
  width:100%;height:100%;
  object-fit:cover;object-position:top center;
  filter:contrast(1.08) brightness(.9) saturate(1.1);
}
.hero-float{
  position:absolute;bottom:52px;left:-2px;
  background:rgba(8,7,6,.94);
  border:1px solid var(--goldborder);border-left:2px solid var(--gold);
  padding:14px 20px;z-index:5;backdrop-filter:blur(10px);
}
.hero-float-label{font-size:8px;font-weight:700;letter-spacing:4px;color:var(--gold);text-transform:uppercase;margin-bottom:3px;}
.hero-float-val{font-size:13px;font-weight:600;color:var(--white);}

/* ═══════════════════════════════
   TICKER
═══════════════════════════════ */
.ticker{
  overflow:hidden;
  background:var(--ink);
  border-top:1px solid var(--goldborder);
  border-bottom:1px solid var(--goldborder);
  padding:13px 0;white-space:nowrap;
}
.ticker-track{
  display:inline-flex;
  animation:tickroll 30s linear infinite;
}
@keyframes tickroll{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.t-i{font-size:10px;font-weight:700;letter-spacing:4px;text-transform:uppercase;color:var(--muted);padding:0 32px;}
.t-d{color:var(--gold);font-size:8px;display:inline-flex;align-items:center;}

/* ═══════════════════════════════
   SECTION BASE
═══════════════════════════════ */
.s{padding:110px 72px;}
.s-inner{max-width:1120px;margin:0 auto;}
.s-dark{background:var(--dark);border-top:1px solid var(--border);border-bottom:1px solid var(--border);}

.s-ey{display:flex;align-items:center;gap:14px;margin-bottom:18px;}
.s-ey-line{width:26px;height:1px;background:var(--gold);flex-shrink:0;}
.s-ey-text{font-size:9px;font-weight:700;letter-spacing:5px;color:var(--gold);text-transform:uppercase;}

.s-title{
  font-family:'Cormorant',serif;
  font-size:clamp(36px,4.5vw,60px);
  font-weight:700;line-height:1.02;color:var(--white);margin-bottom:16px;
}
.s-title em{color:var(--gold2);font-style:italic;font-weight:300;}
.s-sub{font-size:15px;font-weight:300;color:var(--muted);max-width:500px;line-height:1.8;margin-bottom:56px;}

/* ═══════════════════════════════
   PARALLAX PAIN SECTION
═══════════════════════════════ */
.pain-parallax{
  position:relative;overflow:hidden;
  border-top:1px solid var(--border);
  border-bottom:1px solid var(--border);
}
.pain-parallax-bg{
  position:absolute;inset:-30%;
  background-image:url('https://images.unsplash.com/photo-1534438327276-14e5300c3a48?w=1600&q=80');
  background-size:cover;background-position:center;
  will-change:transform;
}
.pain-parallax-overlay{
  position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(4,4,4,.93) 0%,rgba(8,7,4,.88) 100%);
  z-index:1;
}
.pain-parallax-content{position:relative;z-index:2;padding:110px 72px;}

.pain-grid{
  display:grid;grid-template-columns:repeat(3,1fr);
  border:1px solid rgba(28,26,18,.8);
}
.pain-cell{
  padding:34px 28px;
  border-right:1px solid rgba(28,26,18,.8);
  border-bottom:1px solid rgba(28,26,18,.8);
  background:rgba(8,7,4,.6);
  backdrop-filter:blur(4px);
  position:relative;overflow:hidden;
  transition:background .3s;
}
.pain-cell:hover{background:rgba(17,16,9,.85);}
.pain-cell:nth-child(3n){border-right:none;}
.pain-cell:nth-child(n+4){border-bottom:none;}
.pain-cell::after{
  content:'';position:absolute;top:0;left:0;
  width:0;height:2px;background:var(--gold);
  transition:width .4s;
}
.pain-cell:hover::after{width:100%;}
.pain-num{
  font-family:'Cormorant',serif;font-size:52px;font-weight:700;
  -webkit-text-stroke:1px var(--golddim);color:transparent;
  line-height:1;position:absolute;top:10px;right:14px;opacity:.5;
}
.pain-icon{font-size:22px;margin-bottom:12px;display:block;}
.pain-cell h3{font-size:12px;font-weight:700;letter-spacing:1px;color:var(--white);text-transform:uppercase;margin-bottom:8px;}
.pain-cell p{font-size:13px;color:var(--muted);line-height:1.7;}

/* ═══════════════════════════════
   LEAD MAGNET
═══════════════════════════════ */
.magnet-layout{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:center;}
.magnet-doc{
  position:relative;
  background:var(--card2);
  border:1px solid var(--border);
}
.magnet-doc::before{
  content:'';position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(to right,var(--gold),var(--gold2),transparent);
}
.magnet-doc-head{padding:32px 36px 24px;border-bottom:1px solid var(--border);}
.magnet-badge{
  display:inline-flex;align-items:center;gap:8px;
  background:var(--goldborder);border:1px solid var(--golddim);
  padding:5px 14px;margin-bottom:14px;
}
.magnet-badge span{font-size:9px;font-weight:800;letter-spacing:4px;color:var(--gold);text-transform:uppercase;}
.magnet-doc h3{font-family:'Cormorant',serif;font-size:24px;font-weight:700;color:var(--white);line-height:1.3;}
.magnet-doc-body{padding:28px 36px 36px;}
.magnet-list{list-style:none;display:flex;flex-direction:column;gap:13px;margin-bottom:26px;}
.magnet-list li{display:flex;align-items:flex-start;gap:12px;font-size:13px;color:var(--text);line-height:1.55;}
.magnet-list li span{color:var(--gold);font-weight:700;flex-shrink:0;}
.magnet-sep{height:1px;background:var(--border);margin:22px 0;}
.input-f{background:var(--ink);border:1px solid var(--border);height:48px;display:flex;align-items:center;padding:0 16px;font-size:12px;color:var(--muted);margin-bottom:10px;letter-spacing:.5px;}
.btn-wpp{
  display:flex;align-items:center;justify-content:center;gap:10px;
  background:#22C55E;color:#000;
  font-family:'Montserrat',sans-serif;font-size:11px;font-weight:800;letter-spacing:3px;
  text-transform:uppercase;padding:17px 24px;text-decoration:none;
  transition:all .2s;
  clip-path:polygon(0 0,calc(100% - 10px) 0,100% 10px,100% 100%,10px 100%,0 calc(100% - 10px));
}
.btn-wpp:hover{background:#16a34a;transform:translateY(-2px);}
.magnet-note{margin-top:10px;font-size:10px;color:var(--muted);text-align:center;letter-spacing:1px;}

.magnet-copy h2{font-family:'Cormorant',serif;font-size:clamp(32px,3.8vw,50px);font-weight:700;color:var(--white);line-height:1.08;margin-bottom:20px;}
.magnet-copy h2 em{color:var(--gold2);font-style:italic;font-weight:300;}
.magnet-copy p{font-size:15px;color:var(--muted);line-height:1.85;font-weight:300;margin-bottom:14px;}
.magnet-copy .hl{font-size:14px;font-weight:600;color:var(--gold);letter-spacing:.5px;}

/* ═══════════════════════════════
   METHOD — PARALLAX
═══════════════════════════════ */
.method-parallax{position:relative;overflow:hidden;border-top:1px solid var(--border);}
.method-parallax-bg{
  position:absolute;inset:-30%;
  background-image:url('https://images.unsplash.com/photo-1571902943202-507ec2618e8f?w=1600&q=80');
  background-size:cover;background-position:center;
  will-change:transform;
}
.method-parallax-overlay{
  position:absolute;inset:0;
  background:linear-gradient(160deg,rgba(4,4,4,.95) 0%,rgba(10,8,2,.9) 100%);
  z-index:1;
}
.method-parallax-content{position:relative;z-index:2;padding:110px 72px;}

.method-row{
  display:grid;grid-template-columns:repeat(4,1fr);
  position:relative;
}
.method-row::before{
  content:'';position:absolute;
  top:30px;left:12.5%;width:75%;height:1px;
  background:linear-gradient(to right,transparent,var(--golddim) 20%,var(--golddim) 80%,transparent);
}
.method-step{padding:0 22px 36px;text-align:center;position:relative;z-index:1;}
.method-circle{
  width:60px;height:60px;border-radius:50%;
  border:1px solid var(--golddim);background:rgba(4,4,4,.9);
  display:flex;align-items:center;justify-content:center;
  margin:0 auto 22px;
  font-family:'Cormorant',serif;font-size:22px;font-weight:700;color:var(--gold2);
  position:relative;
}
.method-circle::after{content:'';position:absolute;inset:-4px;border-radius:50%;border:1px solid var(--goldborder);}
.method-step h3{font-size:11px;font-weight:700;letter-spacing:2px;color:var(--white);text-transform:uppercase;margin-bottom:10px;}
.method-step p{font-size:12px;color:var(--muted);line-height:1.7;}

/* ═══════════════════════════════
   VIDEO
═══════════════════════════════ */
.video-layout{display:grid;grid-template-columns:1fr 1fr;gap:72px;align-items:center;}
.video-frame{
  position:relative;padding-bottom:177.78%;overflow:hidden;
  border:1px solid var(--border);
}
.video-frame::before{
  content:'';position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(to right,var(--gold),transparent);z-index:1;
}
.video-frame iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:none;}
.video-copy h2{font-family:'Cormorant',serif;font-size:clamp(30px,3.5vw,48px);font-weight:700;color:var(--white);line-height:1.08;margin-bottom:18px;}
.video-copy h2 em{color:var(--gold2);font-style:italic;font-weight:300;}
.video-copy p{font-size:15px;color:var(--muted);line-height:1.85;font-weight:300;margin-bottom:14px;}

/* ═══════════════════════════════
   TESTIMONIALS — PARALLAX
═══════════════════════════════ */
.testi-parallax{position:relative;overflow:hidden;border-top:1px solid var(--border);}
.testi-parallax-bg{
  position:absolute;inset:-30%;
  background-image:url('https://images.unsplash.com/photo-1517836357463-d25dfeac3438?w=1600&q=80');
  background-size:cover;background-position:center top;
  will-change:transform;
}
.testi-parallax-overlay{
  position:absolute;inset:0;
  background:linear-gradient(160deg,rgba(4,4,4,.95) 0%,rgba(8,6,2,.92) 100%);
  z-index:1;
}
.testi-parallax-content{position:relative;z-index:2;padding:110px 72px;}

.google-bar{
  display:flex;align-items:center;gap:24px;
  border:1px solid var(--border);padding:22px 30px;
  margin-bottom:48px;background:rgba(17,16,9,.8);
  width:fit-content;backdrop-filter:blur(8px);
  position:relative;
}
.google-bar::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(to right,var(--gold),transparent);}
.g-num{font-family:'Cormorant',serif;font-size:50px;font-weight:700;color:var(--gold2);line-height:1;}
.g-sep{width:1px;height:44px;background:var(--border);}
.g-info .g-stars{color:#FBBF24;font-size:18px;letter-spacing:3px;}
.g-info .g-label{font-size:10px;font-weight:600;letter-spacing:2px;color:var(--muted);text-transform:uppercase;margin-top:3px;}
.g-quote{font-family:'Cormorant',serif;font-size:15px;font-style:italic;color:var(--text);max-width:240px;line-height:1.6;}

.testi-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:rgba(28,26,18,.5);}
.testi{
  background:rgba(17,16,9,.85);backdrop-filter:blur(6px);
  padding:34px 28px;position:relative;overflow:hidden;transition:background .25s;
}
.testi:hover{background:rgba(24,21,16,.95);}
.testi::after{content:'';position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--gold);transition:width .4s;}
.testi:hover::after{width:100%;}
.testi-quote{font-family:'Cormorant',serif;font-size:90px;font-weight:700;color:var(--golddim);opacity:.2;line-height:1;position:absolute;top:8px;right:14px;}
.testi-stars{color:#FBBF24;font-size:12px;letter-spacing:3px;margin-bottom:16px;}
.testi-text{font-size:14px;color:var(--text);line-height:1.8;font-style:italic;margin-bottom:24px;position:relative;z-index:1;}
.testi-author{display:flex;align-items:center;gap:12px;}
.testi-av{
  width:42px;height:42px;border-radius:50%;
  background:linear-gradient(135deg,var(--golddim),#120C00);
  border:1px solid var(--golddim);
  display:flex;align-items:center;justify-content:center;
  font-family:'Cormorant',serif;font-size:16px;font-weight:700;color:var(--gold2);flex-shrink:0;
}
.testi-name{font-size:13px;font-weight:700;color:var(--white);}
.testi-role{font-size:10px;color:var(--muted);margin-top:2px;letter-spacing:.5px;}

/* ═══════════════════════════════
   PRODUCTS
═══════════════════════════════ */
.products-grid{display:grid;grid-template-columns:1fr 1.6fr 1fr;gap:1px;background:var(--border);}
.product-card{
  background:var(--card);padding:42px 34px;
  display:flex;flex-direction:column;position:relative;overflow:hidden;transition:background .25s;
}
.product-card:hover{background:var(--card2);}
.product-card.feat{background:linear-gradient(160deg,#130F02 0%,#111009 100%);}
.product-card.feat::before{
  content:'';position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(to right,transparent,var(--gold),var(--gold2),transparent);
}
.product-feat-badge{
  position:absolute;top:18px;right:18px;
  background:var(--gold);font-size:8px;font-weight:800;letter-spacing:3px;color:#000;
  padding:4px 12px;text-transform:uppercase;
}
.product-type{font-size:9px;font-weight:700;letter-spacing:4px;color:var(--gold);text-transform:uppercase;margin-bottom:12px;}
.product-name{font-family:'Cormorant',serif;font-size:26px;font-weight:700;color:var(--white);line-height:1.15;margin-bottom:12px;}
.product-desc{font-size:13px;color:var(--muted);line-height:1.75;margin-bottom:22px;flex-grow:1;}
.product-feats{list-style:none;display:flex;flex-direction:column;gap:8px;margin-bottom:28px;}
.product-feats li{display:flex;align-items:flex-start;gap:9px;font-size:12px;color:var(--text);line-height:1.5;}
.product-feats li::before{content:'✓';color:var(--gold);font-weight:700;flex-shrink:0;}
.product-price{font-family:'Cormorant',serif;font-size:40px;font-weight:700;color:var(--gold2);line-height:1;margin-bottom:4px;}
.product-price-note{font-size:10px;color:var(--muted);letter-spacing:1px;margin-bottom:22px;}

.consult-plans{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px;}
.plan-box{border:1px solid var(--goldborder);padding:14px;text-align:center;background:rgba(0,0,0,.3);position:relative;overflow:hidden;}
.plan-box.best{border-color:var(--golddim);}
.plan-box.best::after{
  content:'MELHOR CUSTO';position:absolute;top:-1px;right:-1px;
  background:var(--golddim);font-size:7px;font-weight:800;letter-spacing:2px;
  color:var(--gold3);padding:3px 8px;text-transform:uppercase;
}
.plan-label{font-size:8px;font-weight:700;letter-spacing:3px;color:var(--gold);text-transform:uppercase;margin-bottom:7px;}
.plan-price{font-family:'Cormorant',serif;font-size:28px;font-weight:700;color:var(--gold2);line-height:1;}
.plan-note{font-size:9px;color:var(--muted);margin-top:3px;}
.plan-save{font-size:9px;color:var(--green);font-weight:600;margin-top:2px;}

.btn-product{
  display:flex;align-items:center;justify-content:center;gap:8px;
  padding:14px 18px;text-decoration:none;
  font-family:'Montserrat',sans-serif;font-size:10px;font-weight:800;letter-spacing:3px;
  text-transform:uppercase;transition:all .2s;
  clip-path:polygon(0 0,calc(100% - 8px) 0,100% 8px,100% 100%,8px 100%,0 calc(100% - 8px));
}
.btn-product.ghost{border:1px solid var(--goldborder);color:var(--gold);background:transparent;}
.btn-product.ghost:hover{background:var(--goldborder);color:var(--gold2);}
.btn-product.gold{background:var(--gold);color:#000;border:none;}
.btn-product.gold:hover{background:var(--gold2);transform:translateY(-2px);}
.btn-product.wpp{background:#22C55E;color:#000;border:none;}
.btn-product.wpp:hover{background:#16a34a;transform:translateY(-2px);}

/* ═══════════════════════════════
   BIO — PARALLAX
═══════════════════════════════ */
.bio-parallax{position:relative;overflow:hidden;border-top:1px solid var(--border);}
.bio-parallax-bg{
  position:absolute;inset:-30%;
  background-image:url('https://images.unsplash.com/photo-1590487988256-9ed24133863e?w=1600&q=80');
  background-size:cover;background-position:center;
  will-change:transform;
}
.bio-parallax-overlay{
  position:absolute;inset:0;
  background:linear-gradient(160deg,rgba(4,4,4,.97) 0%,rgba(8,6,2,.93) 100%);
  z-index:1;
}
.bio-parallax-content{position:relative;z-index:2;padding:110px 72px;}

.bio-layout{display:grid;grid-template-columns:5fr 7fr;gap:80px;align-items:center;}
.bio-photo{position:relative;overflow:hidden;height:580px;}
.bio-photo img{width:100%;height:100%;object-fit:cover;object-position:top center;filter:contrast(1.05) brightness(.88);}
.bio-photo::after{
  content:'';position:absolute;inset:0;
  background:
    linear-gradient(to bottom,var(--black) 0%,transparent 12%,transparent 80%,var(--black) 100%),
    linear-gradient(to right,transparent 72%,var(--black) 100%),
    linear-gradient(to left,var(--black) 0%,transparent 6%);
}
.bio-photo::before{
  content:'';position:absolute;top:0;left:0;
  width:56px;height:56px;
  border-top:2px solid var(--gold);border-left:2px solid var(--gold);z-index:2;
}
.bio-copy h2{font-family:'Cormorant',serif;font-size:clamp(30px,3.8vw,50px);font-weight:700;color:var(--white);line-height:1.08;margin-bottom:22px;}
.bio-copy h2 em{color:var(--gold2);font-style:italic;font-weight:300;}
.bio-copy p{font-size:15px;color:var(--muted);line-height:1.9;font-weight:300;margin-bottom:14px;}
.bio-copy p strong{color:var(--gold3);font-weight:600;}
.bio-creds{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--border);margin-top:32px;}
.cred{background:rgba(17,16,9,.85);padding:16px 18px;display:flex;align-items:center;gap:10px;font-size:12px;color:var(--text);font-weight:500;backdrop-filter:blur(4px);}
.cred::before{content:'';width:5px;height:5px;border-radius:50%;background:var(--gold);flex-shrink:0;}

/* ═══════════════════════════════
   FINAL CTA — PARALLAX
═══════════════════════════════ */
.final-parallax{position:relative;overflow:hidden;border-top:1px solid var(--border);}
.final-parallax-bg{
  position:absolute;inset:-30%;
  background-image:url('https://images.unsplash.com/photo-1605296867304-46d5465a13f1?w=1600&q=80');
  background-size:cover;background-position:center;
  will-change:transform;
}
.final-parallax-overlay{
  position:absolute;inset:0;
  background:linear-gradient(160deg,rgba(4,4,4,.96) 0%,rgba(6,5,1,.94) 100%);
  z-index:1;
}
.final-parallax-content{
  position:relative;z-index:2;
  padding:140px 72px;text-align:center;
}
/* Ghost word */
.final-parallax-content::before{
  content:'PRESENÇA';
  position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  font-family:'Cormorant',serif;font-size:clamp(80px,13vw,170px);
  font-weight:700;color:var(--golddim);opacity:.05;
  white-space:nowrap;letter-spacing:14px;pointer-events:none;
}
.final-eyebrow{font-size:9px;font-weight:700;letter-spacing:6px;color:var(--gold);text-transform:uppercase;margin-bottom:20px;}
.final-title{font-family:'Cormorant',serif;font-size:clamp(44px,6vw,82px);font-weight:700;color:var(--white);line-height:1.0;margin-bottom:20px;}
.final-title em{color:var(--gold2);font-style:italic;font-weight:300;}
.final-sub{font-size:16px;color:var(--muted);max-width:440px;margin:0 auto 48px;line-height:1.8;font-weight:300;}

/* ═══════════════════════════════
   FOOTER
═══════════════════════════════ */
footer{
  background:var(--black);border-top:1px solid var(--border);
  padding:44px 72px;display:flex;align-items:center;justify-content:space-between;
}
.foot-brand{font-family:'Cormorant',serif;font-size:24px;font-weight:700;color:var(--white);}
.foot-brand em{color:var(--gold);font-style:italic;}
.foot-tag{font-size:9px;font-weight:700;letter-spacing:4px;color:var(--muted);text-transform:uppercase;margin-top:5px;}
.foot-right{font-size:10px;color:var(--muted);letter-spacing:1px;text-align:right;line-height:1.8;}

/* ═══════════════════════════════
   REVEAL ANIMATIONS
═══════════════════════════════ */
.reveal{opacity:0;transform:translateY(22px);transition:opacity .75s ease,transform .75s ease;}
.reveal.visible{opacity:1;transform:translateY(0);}
.rd1{transition-delay:.1s}.rd2{transition-delay:.2s}.rd3{transition-delay:.3s}.rd4{transition-delay:.4s}

@keyframes heroIn{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
.hero-left > *{animation:heroIn .7s ease both;}
.hero-eyebrow{animation-delay:.05s}.hero-name{animation-delay:.2s}
.hero-name-italic{animation-delay:.28s}.hero-tag{animation-delay:.36s}
.hero-headline{animation-delay:.44s}.proof-row{animation-delay:.54s}
.cta-stack{animation-delay:.64s}

/* ═══════════════════════════════
   RESPONSIVE
═══════════════════════════════ */
@media(max-width:960px){
  .hero{grid-template-columns:1fr}.hero-right,.hero::after{display:none}
  .hero-left{padding:80px 26px}
  .pain-grid,.testi-grid,.products-grid,.bio-layout,.magnet-layout,.video-layout,.bio-creds{grid-template-columns:1fr}
  .method-row{grid-template-columns:1fr 1fr}.method-row::before{display:none}
  .s,.pain-parallax-content,.method-parallax-content,.testi-parallax-content,
  .bio-parallax-content,.final-parallax-content{padding:70px 26px}
  footer{flex-direction:column;gap:12px;text-align:center}.foot-right{text-align:center}
  .google-bar{width:100%}
  .consult-plans{grid-template-columns:1fr 1fr}
}

/* WPP icon inline helper */
.wpp-icon{display:inline-flex;align-items:center;gap:8px;}
</style>
</head>
<body>

<!-- ═══ HERO ═══ -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">
      <div class="eyebrow-line"></div>
      <div class="eyebrow-text">Código da Presença</div>
    </div>
    <div class="hero-name">Renan</div>
    <div class="hero-name-italic">Costa</div>
    <div class="hero-tag">
      <div class="tag-dot"></div>
      <span>Método Presença Alpha</span>
      <div class="tag-dot"></div>
      <span>Personal Trainer</span>
    </div>
    <p class="hero-headline">
      Transformação real não começa no espelho.<br>
      Começa em <strong>como você é percebido</strong> antes de abrir a boca.
    </p>
    <div class="proof-row">
      <div class="proof-item"><div class="proof-n">9+</div><div class="proof-l">Anos de experiência</div></div>
      <div class="proof-item"><div class="proof-n">5.0</div><div class="proof-l">Estrelas Google</div></div>
      <div class="proof-item"><div class="proof-n">19</div><div class="proof-l">Avaliações reais</div></div>
    </div>
    <div class="cta-stack">
      <a href="https://wa.me/5561991091690?text=Ol%C3%A1%20Renan!%20Quero%20receber%20o%20guia%20Postura%20Alpha%20gratuito!" class="btn-main" target="_blank">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.849L.057 23.886a.5.5 0 00.606.61l6.196-1.485A11.945 11.945 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.882a9.877 9.877 0 01-5.031-1.374l-.36-.214-3.733.895.928-3.64-.234-.374A9.852 9.852 0 012.118 12C2.118 6.52 6.52 2.118 12 2.118S21.882 6.52 21.882 12 17.48 21.882 12 21.882z"/></svg>
        Receber Guia Gratuito
      </a>
      <a href="#produtos" class="btn-ghost">Ver produtos e consultoria →</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-photo-wrap">
      <img src="data:image/jpeg;base64,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" alt="Renan Costa">
    </div>
    <div class="hero-float">
      <div class="hero-float-label">Graduado em Educação Física</div>
      <div class="hero-float-val">9 anos · Brasília & Goiânia</div>
    </div>
  </div>
</section>

<!-- ═══ TICKER ═══ -->
<div class="ticker">
  <div class="ticker-track">
    <span class="t-i">Código da Presença</span><span class="t-d">◆</span>
    <span class="t-i">Postura Alpha</span><span class="t-d">◆</span>
    <span class="t-i">Método Presença Alpha</span><span class="t-d">◆</span>
    <span class="t-i">Renan Costa Personal</span><span class="t-d">◆</span>
    <span class="t-i">9 Anos de Experiência</span><span class="t-d">◆</span>
    <span class="t-i">5.0 ★★★★★ Google</span><span class="t-d">◆</span>
    <span class="t-i">Transformação Real</span><span class="t-d">◆</span>
    <span class="t-i">Código da Presença</span><span class="t-d">◆</span>
    <span class="t-i">Postura Alpha</span><span class="t-d">◆</span>
    <span class="t-i">Método Presença Alpha</span><span class="t-d">◆</span>
    <span class="t-i">Renan Costa Personal</span><span class="t-d">◆</span>
    <span class="t-i">9 Anos de Experiência</span><span class="t-d">◆</span>
    <span class="t-i">5.0 ★★★★★ Google</span><span class="t-d">◆</span>
    <span class="t-i">Transformação Real</span><span class="t-d">◆</span>
  </div>
</div>

<!-- ═══ DOR — PARALLAX ═══ -->
<section class="pain-parallax reveal">
  <div class="pain-parallax-bg" data-parallax="0.3"></div>
  <div class="pain-parallax-overlay"></div>
  <div class="pain-parallax-content">
    <div style="max-width:1120px;margin:0 auto;">
      <div class="s-ey"><div class="s-ey-line"></div><div class="s-ey-text">Reconhece algum desses padrões?</div></div>
      <h2 class="s-title">O problema não é <em>falta de esforço</em></h2>
      <p class="s-sub">Ninguém te ensinou a diferença entre treinar o corpo e construir a imagem que esse corpo projeta.</p>
      <div class="pain-grid">
        <div class="pain-cell reveal rd1"><div class="pain-num">01</div><span class="pain-icon">👁</span><h3>Evita contato visual</h3><p>Insegurança em ambientes sociais mesmo com o corpo trabalhado.</p></div>
        <div class="pain-cell reveal rd2"><div class="pain-num">02</div><span class="pain-icon">📐</span><h3>Postura que não transmite</h3><p>Seu corpo não passa a confiança que você sente por dentro.</p></div>
        <div class="pain-cell reveal rd3"><div class="pain-num">03</div><span class="pain-icon">🎯</span><h3>Treina sem direção real</h3><p>Meses de academia sem evolução em presença ou imagem.</p></div>
        <div class="pain-cell reveal rd1"><div class="pain-num">04</div><span class="pain-icon">📉</span><h3>Ocupa pouco espaço</h3><p>Você chega num lugar e passa despercebido. Não é o corpo — é o padrão.</p></div>
        <div class="pain-cell reveal rd2"><div class="pain-num">05</div><span class="pain-icon">🔄</span><h3>Volta ao mesmo padrão</h3><p>Começa bem, muda por semanas, mas sempre volta ao comportamento anterior.</p></div>
        <div class="pain-cell reveal rd3"><div class="pain-num">06</div><span class="pain-icon">👔</span><h3>Sabe que poderia mais</h3><p>Clareza de que poderia transmitir mais autoridade — mas não sabe como chegar lá.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ LEAD MAGNET ═══ -->
<section class="s reveal" id="guia">
  <div class="s-inner">
    <div class="magnet-layout">
      <div class="magnet-doc reveal rd1">
        <div class="magnet-doc-head">
          <div class="magnet-badge"><span>Guia Gratuito</span></div>
          <h3>"Postura Alpha — O que Ninguém te Ensinou sobre Presença"</h3>
        </div>
        <div class="magnet-doc-body">
          <ul class="magnet-list">
            <li><span>→</span> A postura que faz você parecer inseguro mesmo quando não é</li>
            <li><span>→</span> Por que seu pescoço entrega mais do que qualquer roupa</li>
            <li><span>→</span> O ajuste de 30 segundos que muda como você é percebido</li>
            <li><span>→</span> O padrão postural de quem domina qualquer ambiente</li>
            <li><span>→</span> Como aplicar antes de qualquer reunião, evento ou encontro</li>
          </ul>
          <div class="magnet-sep"></div>
          <div class="input-f">Seu nome</div>
          <div class="input-f">Seu WhatsApp</div>
          <a href="https://wa.me/5561991091690?text=Ol%C3%A1%20Renan!%20Quero%20receber%20o%20guia%20Postura%20Alpha%20gratuito!" class="btn-wpp" target="_blank">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.849L.057 23.886a.5.5 0 00.606.61l6.196-1.485A11.945 11.945 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.882a9.877 9.877 0 01-5.031-1.374l-.36-.214-3.733.895.928-3.64-.234-.374A9.852 9.852 0 012.118 12C2.118 6.52 6.52 2.118 12 2.118S21.882 6.52 21.882 12 17.48 21.882 12 21.882z"/></svg>
            Receber no WhatsApp — Grátis
          </a>
          <p class="magnet-note">100% gratuito · sem cartão · sem compromisso</p>
        </div>
      </div>
      <div class="magnet-copy reveal rd2">
        <div class="s-ey"><div class="s-ey-line"></div><div class="s-ey-text">Primeiro passo — gratuito</div></div>
        <h2>Antes de qualquer investimento, você precisa <em>enxergar o problema</em></h2>
        <p>A maioria tenta resolver postura com exercício. Mas o problema começa antes — nos padrões que seu corpo aprendeu a comunicar ao longo de anos.</p>
        <p>Esse guia mostra com precisão onde sua postura está sabotando sua imagem — e o primeiro ajuste que você pode fazer ainda hoje.</p>
        <p class="hl">Transformação real começa com presença real.</p>
      </div>
    </div>
  </div>
</section>

<!-- ═══ MÉTODO — PARALLAX ═══ -->
<section class="method-parallax reveal">
  <div class="method-parallax-bg" data-parallax="0.25"></div>
  <div class="method-parallax-overlay"></div>
  <div class="method-parallax-content">
    <div style="max-width:1120px;margin:0 auto;">
      <div class="s-ey"><div class="s-ey-line"></div><div class="s-ey-text">Como funciona</div></div>
      <h2 class="s-title">O Método <em>Presença Alpha</em></h2>
      <p class="s-sub">Não é treino convencional. É uma abordagem que reconstrói o que você comunica antes de abrir a boca.</p>
      <div class="method-row">
        <div class="method-step reveal rd1"><div class="method-circle">01</div><h3>Diagnóstico Postural</h3><p>Identificamos os padrões exatos que estão sabotando sua imagem hoje.</p></div>
        <div class="method-step reveal rd2"><div class="method-circle">02</div><h3>Correção Estrutural</h3><p>Exercícios específicos para reprogramar postura — não apenas fortalecer.</p></div>
        <div class="method-step reveal rd3"><div class="method-circle">03</div><h3>Presença Aplicada</h3><p>Como você anda, senta, gesticula e ocupa espaço em qualquer ambiente.</p></div>
        <div class="method-step reveal rd4"><div class="method-circle">04</div><h3>Imagem Consistente</h3><p>Uma nova forma permanente de ser percebido — para sempre.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ VÍDEO ═══ -->
<section class="s s-dark reveal">
  <div class="s-inner">
    <div class="video-layout">
      <div class="video-frame reveal rd1">
        <iframe src="https://www.youtube.com/embed/hx_fVBpRPhM" allowfullscreen allow="autoplay; encrypted-media"></iframe>
      </div>
      <div class="video-copy reveal rd2">
        <div class="s-ey"><div class="s-ey-line"></div><div class="s-ey-text">Assista antes de decidir</div></div>
        <h2>Veja como funciona <em>minha consultoria</em></h2>
        <p>Em poucos minutos explico o que você recebe, como funciona o acompanhamento e por que o método vai além do treino convencional.</p>
        <p>Se fizer sentido, o próximo passo é uma conversa direta no WhatsApp.</p>
        <a href="https://wa.me/5561991091690?text=Ol%C3%A1%20Renan!%20Assisti%20seu%20v%C3%ADdeo%20e%20quero%20saber%20mais%20sobre%20a%20consultoria!" class="btn-main" style="margin-top:16px;" target="_blank">Falar com Renan →</a>
      </div>
    </div>
  </div>
</section>

<!-- ═══ DEPOIMENTOS — PARALLAX ═══ -->
<section class="testi-parallax reveal">
  <div class="testi-parallax-bg" data-parallax="0.25"></div>
  <div class="testi-parallax-overlay"></div>
  <div class="testi-parallax-content">
    <div style="max-width:1120px;margin:0 auto;">
      <div class="s-ey"><div class="s-ey-line"></div><div class="s-ey-text">Resultados reais</div></div>
      <h2 class="s-title">O que <em>alunos dizem</em></h2>
      <div class="google-bar reveal rd1">
        <div class="g-num">5.0</div>
        <div class="g-sep"></div>
        <div class="g-info"><div class="g-stars">★★★★★</div><div class="g-label">19 avaliações verificadas · Google Business</div></div>
        <div class="g-sep"></div>
        <div class="g-quote">"Nota máxima mantida. Cada avaliação é de um aluno real com resultado real."</div>
      </div>
      <div class="testi-grid">
        <div class="testi reveal rd1">
          <div class="testi-quote">"</div>
          <div class="testi-stars">★★★★★</div>
          <p class="testi-text">"Menos de dois meses e 7 kg a menos na balança, e roupas que antes não serviam agora estão folgadas. Além de tudo a compreensão e o apoio nos treinos. Profissional incrível."</p>
          <div class="testi-author"><div class="testi-av">CA</div><div><div class="testi-name">Cesar Augusto</div><div class="testi-role">Google · há 7 semanas</div></div></div>
        </div>
        <div class="testi reveal rd2" style="background:rgba(24,21,10,.9);">
          <div class="testi-quote">"</div>
          <div class="testi-stars">★★★★★</div>
          <p class="testi-text">"Super competente e profissional, tive ótimos resultados com ele. Recomendo para quem quer resultado de verdade e acompanhamento de qualidade."</p>
          <div class="testi-author"><div class="testi-av">EM</div><div><div class="testi-name">Erica Mendonça</div><div class="testi-role">Local Guide · 24 avaliações · há 12 semanas</div></div></div>
        </div>
        <div class="testi reveal rd3">
          <div class="testi-quote">"</div>
          <div class="testi-stars">★★★★★</div>
          <p class="testi-text">"Profissional comprometido e dedicado! A forma como conduz os treinos e acompanha a evolução do aluno é diferenciada. Indico sempre!"</p>
          <div class="testi-author"><div class="testi-av">TA</div><div><div class="testi-name">Thiago Aires de Rezende</div><div class="testi-role">Local Guide · 18 avaliações · há 7 semanas</div></div></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ PRODUTOS ═══ -->
<section class="s reveal" id="produtos">
  <div class="s-inner">
    <div class="s-ey"><div class="s-ey-line"></div><div class="s-ey-text">Produtos & Consultoria</div></div>
    <h2 class="s-title">Escolha sua <em>próxima etapa</em></h2>
    <p class="s-sub">Cada produto é uma etapa do mesmo método. Comece pelo que faz mais sentido para você agora.</p>
    <div class="products-grid">

      <!-- Coluna esquerda: 2 produtos -->
      <div style="display:flex;flex-direction:column;gap:1px;background:var(--border);">
        <div class="product-card reveal rd1" style="flex:1;">
          <div class="product-type">📘 E-book</div>
          <div class="product-name">Musculação + Saúde Mental</div>
          <div class="product-desc">Como disciplina, treino e mentalidade se conectam para gerar constância real — sem burnout, sem abandono.</div>
          <ul class="product-feats">
            <li>Psicologia da consistência no treino</li>
            <li>Como criar disciplina sustentável</li>
            <li>Técnicas anti-abandono comprovadas</li>
          </ul>
          <div class="product-price">R$27,90</div>
          <div class="product-price-note">Pagamento único · acesso imediato</div>
          <a href="https://mental-muscle-web.lovable.app" class="btn-product ghost" target="_blank">Quero o E-book →</a>
        </div>
        <div class="product-card reveal rd2" style="flex:1;">
          <div class="product-type">🎬 Vídeo Aula</div>
          <div class="product-name">Glúteo Turbinado</div>
          <div class="product-desc">Treino completo com execução ensinada exercício por exercício. Dois níveis inclusos.</div>
          <ul class="product-feats">
            <li>Execução correta de cada movimento</li>
            <li>Treino para iniciantes</li>
            <li>Treino avançado para experientes</li>
          </ul>
          <div class="product-price">R$29,90</div>
          <div class="product-price-note">Pagamento único · acesso imediato</div>
          <a href="https://mentealpha-gluteo-pro.lovable.app/" class="btn-product ghost" target="_blank">Quero o Treino →</a>
        </div>
      </div>

      <!-- Consultoria destaque -->
      <div class="product-card feat reveal rd2">
        <div class="product-feat-badge">Mais Completo</div>
        <div class="product-type" style="margin-top:14px;">🏆 Consultoria Personalizada</div>
        <div class="product-name">Método Presença Alpha</div>
        <div class="product-desc">Acompanhamento completo e individual. Para quem quer transformar postura, físico e presença com direcionamento estratégico real.</div>
        <ul class="product-feats">
          <li>Diagnóstico postural individualizado</li>
          <li>Plano de treino 100% personalizado</li>
          <li>Correção de postura e linguagem corporal</li>
          <li>Acompanhamento semanal de evolução</li>
          <li>Suporte direto via WhatsApp</li>
          <li>Direcionamento estratégico completo</li>
        </ul>
        <div class="consult-plans">
          <div class="plan-box">
            <div class="plan-label">Plano Mensal</div>
            <div class="plan-price">R$190</div>
            <div class="plan-note">por mês</div>
          </div>
          <div class="plan-box best">
            <div class="plan-label">Plano Trimestral</div>
            <div class="plan-price">R$480</div>
            <div class="plan-note">3 meses</div>
            <div class="plan-save">Economia de R$90</div>
          </div>
        </div>
        <a href="https://wa.me/5561991091690?text=Ol%C3%A1%20Renan!%20Quero%20come%C3%A7ar%20minha%20consultoria%20personalizada%20do%20M%C3%A9todo%20Presen%C3%A7a%20Alpha!" class="btn-product wpp" target="_blank">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.849L.057 23.886a.5.5 0 00.606.61l6.196-1.485A11.945 11.945 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.882a9.877 9.877 0 01-5.031-1.374l-.36-.214-3.733.895.928-3.64-.234-.374A9.852 9.852 0 012.118 12C2.118 6.52 6.52 2.118 12 2.118S21.882 6.52 21.882 12 17.48 21.882 12 21.882z"/></svg>
          Quero Minha Consultoria
        </a>
        <p style="margin-top:10px;font-size:9px;color:var(--muted);text-align:center;letter-spacing:1px;">VAGAS LIMITADAS · RESPOSTA EM ATÉ 24H</p>
      </div>

    </div>
  </div>
</section>

<!-- ═══ BIO — PARALLAX ═══ -->
<section class="bio-parallax reveal">
  <div class="bio-parallax-bg" data-parallax="0.2"></div>
  <div class="bio-parallax-overlay"></div>
  <div class="bio-parallax-content">
    <div style="max-width:1120px;margin:0 auto;">
      <div class="bio-layout">
        <div class="bio-photo reveal rd1">
          <img src="data:image/jpeg;base64,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" alt="Renan Costa">
        </div>
        <div class="bio-copy reveal rd2">
          <div class="s-ey"><div class="s-ey-line"></div><div class="s-ey-text">Quem é Renan Costa</div></div>
          <h2>Não é só sobre mudar o corpo. <em>É sobre mudar como você é percebido.</em></h2>
          <p>Sou profissional de Educação Física há mais de <strong>9 anos</strong>, acompanhando a evolução e transformação de dezenas de alunos em Brasília e Goiânia.</p>
          <p>Ao longo da carreira percebi algo que nenhuma faculdade ensina: a maioria das pessoas treina o corpo e esquece de treinar a <strong>imagem que esse corpo projeta</strong>. Postura, presença, como você ocupa espaço — isso muda como as pessoas te percebem antes de você abrir a boca.</p>
          <p>Por isso criei o <strong>Código da Presença</strong>: uma abordagem que vai além do físico e trabalha a forma como você se posiciona no mundo.</p>
          <div class="bio-creds">
            <div class="cred">Graduado em Educação Física</div>
            <div class="cred">9+ anos de experiência</div>
            <div class="cred">5.0 ★ · 19 avaliações Google</div>
            <div class="cred">Brasília & Goiânia</div>
            <div class="cred">Criador do Método Presença Alpha</div>
            <div class="cred">Código da Postura — guia exclusivo</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ CTA FINAL — PARALLAX ═══ -->
<section class="final-parallax reveal">
  <div class="final-parallax-bg" data-parallax="0.3"></div>
  <div class="final-parallax-overlay"></div>
  <div class="final-parallax-content">
    <div class="final-eyebrow">Primeiro passo — gratuito</div>
    <h2 class="final-title">Comece agora.<br><em>Sem risco. Sem custo.</em></h2>
    <p class="final-sub">Receba o guia Postura Alpha e descubra o que sua postura está comunicando sem que você perceba.</p>
    <a href="https://wa.me/5561991091690?text=Ol%C3%A1%20Renan!%20Quero%20receber%20o%20guia%20Postura%20Alpha%20gratuito!" class="btn-main" style="margin:0 auto;" target="_blank">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.849L.057 23.886a.5.5 0 00.606.61l6.196-1.485A11.945 11.945 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.882a9.877 9.877 0 01-5.031-1.374l-.36-.214-3.733.895.928-3.64-.234-.374A9.852 9.852 0 012.118 12C2.118 6.52 6.52 2.118 12 2.118S21.882 6.52 21.882 12 17.48 21.882 12 21.882z"/></svg>
      Receber Guia no WhatsApp — Grátis
    </a>
  </div>
</section>

<!-- ═══ FOOTER ═══ -->
<footer>
  <div>
    <div class="foot-brand">Renan <em>Costa</em></div>
    <div class="foot-tag">Código da Presença · Método Presença Alpha</div>
  </div>
  <div class="foot-right">
    Personal Trainer · 9 Anos de Experiência<br>
    Brasília & Goiânia · 61 99109-1690
  </div>
</footer>

<script>
// ── Scroll reveal ──
const observer = new IntersectionObserver((entries) => {
  entries.forEach(el => { if(el.isIntersecting) el.target.classList.add('visible'); });
}, { threshold: 0.08 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// ── Parallax on scroll ──
function updateParallax() {
  const scrollY = window.scrollY;
  document.querySelectorAll('[data-parallax]').forEach(el => {
    const rate = parseFloat(el.dataset.parallax);
    const section = el.parentElement;
    const rect = section.getBoundingClientRect();
    const offset = (rect.top + rect.height / 2 - window.innerHeight / 2) * rate;
    el.style.transform = `translateY(${offset}px)`;
  });
}
window.addEventListener('scroll', updateParallax, { passive: true });
updateParallax();
</script>
</body>
</html>
