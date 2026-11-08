
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#ffffff">
<title>YourBrand.ai | Create Beautiful Ebooks</title>

<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800&family=Playfair+Display:wght@500;600;700&display=swap" rel="stylesheet">

<style>
:root{
--orange:#f47761;
--pink:#fac5bb;
--brown:#382d29;
--muted:#827a76;
--cream:#faf7f3;
--border:#eae6e1;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;color:var(--brown);background:#fff}
button{font:inherit;cursor:pointer}
a{text-decoration:none;color:inherit}
.container{width:min(1100px,92%);margin:auto}

/* HEADER */
header{
height:70px;
background:#fff;
position:sticky;
top:0;
z-index:50;
border-bottom:1px solid #f1efec;
}
.nav{
height:100%;
display:flex;
align-items:center;
justify-content:space-between;
width:92%;
max-width:1200px;
margin:auto;
}
.logo{font-size:21px;font-weight:700;letter-spacing:-.7px}
.logo span{color:var(--orange)}
.menu-btn{
background:none;border:0;font-size:29px;
color:var(--brown);padding:5px;line-height:1;
}
.menu-panel{
display:none;position:absolute;top:70px;right:4%;
width:190px;background:white;padding:20px;
border:1px solid var(--border);border-radius:10px;
box-shadow:0 10px 30px #00000012;
}
.menu-panel.open{display:flex;flex-direction:column;gap:17px}
.menu-panel a{font-size:13px}
.menu-panel a:hover{color:var(--orange)}

/* HERO */
.hero{
padding:30px 0 60px;text-align:center;
background:radial-gradient(ellipse at 50% 25%,#fff9f7,white 70%);
}
.social-proof{
display:inline-flex;align-items:center;gap:12px;
border:1px solid #f1ded9;border-radius:40px;
padding:11px 19px;color:#a95645;
font-size:14px;font-weight:700;margin-bottom:40px;
}
.proof-dot{
width:12px;height:12px;border-radius:50%;
background:var(--orange);box-shadow:0 0 0 5px #fce5df;
}
.hero h1{
font-size:clamp(43px,7vw,75px);
font-weight:800;letter-spacing:-2.5px;
line-height:1.13;margin-bottom:35px;
}
.hero h1 span{color:var(--orange)}
.hero-description{
max-width:740px;margin:auto;
font-size:clamp(16px,2.5vw,25px);
line-height:1.7;color:var(--muted);
}
.prompt-wrap{max-width:760px;margin:35px auto 18px}
.prompt-box{
position:relative;height:190px;
border:1.5px solid #e7e3df;border-radius:22px;
background:white;box-shadow:0 15px 45px #00000008;
}
.prompt-box textarea{
width:100%;height:145px;padding:23px 25px 55px;
border:0;outline:none;resize:none;background:transparent;
font-family:inherit;font-size:19px;line-height:1.6;
}
.prompt-box textarea::placeholder{color:#c1bfbd}
.send-btn{
position:absolute;right:17px;bottom:15px;
height:57px;width:57px;border:0;border-radius:50%;
background:var(--pink);color:white;font-size:32px;
transition:.2s;
}
.send-btn:hover{background:var(--orange);transform:translateY(-3px)}
.suggestions{
display:flex;justify-content:center;flex-wrap:wrap;
gap:12px;margin-top:18px;
}
.suggestion{
padding:10px 18px;border:1px solid #e8e4df;
border-radius:30px;background:white;color:#706761;font-size:13px;
}
.suggestion:first-child,.suggestion:hover{
border-color:#f1c6bc;color:#a95848;background:#fffaf8;
}
.hero-note{margin-top:38px;color:#aaa39e;font-size:16px;line-height:1.6}
.see-how{display:inline-block;margin-top:19px;color:#958d87;font-size:17px;font-weight:700}

/* PLATFORMS */
.platforms{padding:55px 0 85px;text-align:center}
.platform-title{
color:#aaa39f;font-size:16px;letter-spacing:2px;
font-weight:600;margin-bottom:38px;
}
.platform-grid{
display:flex;justify-content:center;align-items:center;
flex-wrap:wrap;gap:38px;max-width:900px;margin:auto;
}
.platform{
width:65px;height:60px;display:flex;
align-items:center;justify-content:center;
filter:grayscale(1);opacity:.65;transition:.2s;
}
.platform:hover{filter:none;opacity:1;transform:translateY(-3px)}
.platform img{max-width:52px;max-height:43px;object-fit:contain}

/* BOOK SHOWCASE */
.showcase{background:var(--cream);padding:85px 0 90px;text-align:center}
.section-tag{
display:inline-block;background:white;border:1px solid #f0e5df;
border-radius:40px;padding:12px 23px;color:#a65b4a;
font-size:14px;font-weight:700;margin-bottom:30px;
}
.section-title{
font-size:clamp(35px,5vw,53px);line-height:1.2;
letter-spacing:-1.5px;font-weight:800;color:var(--brown);
max-width:850px;margin:0 auto 22px;
}
.section-description{
max-width:800px;margin:auto;color:#827873;
font-size:clamp(15px,2.2vw,22px);line-height:1.8;
}
.book-viewer{max-width:570px;margin:48px auto 0}
.book-stage{display:flex;justify-content:center;perspective:1200px;padding:5px}
.single-page{
width:100%;max-width:440px;height:510px;
min-height:510px;max-height:510px;
background:white;border-radius:5px;
box-shadow:0 15px 40px #00000012;
overflow:hidden;position:relative;transform-origin:left center;
}
.single-page.turning{animation:pageTurn .48s ease}
@keyframes pageTurn{
0%{transform:rotateY(0);opacity:1}
45%{transform:rotateY(-17deg);opacity:.75}
100%{transform:rotateY(0);opacity:1}
}
.book-cover{
width:100%;height:510px;min-height:510px;max-height:510px;
display:flex;flex-direction:column;justify-content:space-between;
align-items:center;text-align:center;padding:45px 30px;
color:white;background:linear-gradient(145deg,#c77d65,#814a42);
overflow:hidden;
}
.cover-top{font-size:11px;letter-spacing:3px}
.cover-art{font-size:80px;margin:15px 0}
.cover-title{font-family:'Playfair Display',serif;font-size:36px;line-height:1.2}
.cover-subtitle{font-size:13px;line-height:1.7;margin-top:16px}
.cover-author{font-size:11px;letter-spacing:3px}
.inside-page{
width:100%;height:510px;min-height:510px;max-height:510px;
padding:42px 38px 30px;display:flex;flex-direction:column;
justify-content:space-between;text-align:left;background:white;overflow:hidden;
}
.page-content{overflow:hidden}
.page-top-label{font-size:10px;color:#a99b92;letter-spacing:2px;margin-bottom:27px}
.page-decoration{height:3px;width:40px;background:var(--orange);margin-bottom:18px}
.inside-page h3{
font-family:'Playfair Display',serif;font-size:26px;
line-height:1.3;margin-bottom:20px;
}
.inside-page p{
font-family:'Playfair Display',serif;font-size:14px;
line-height:1.9;color:#74665f;white-space:pre-line;
}
.page-bottom{
display:flex;justify-content:space-between;align-items:center;
margin-top:20px;font-size:10px;color:#a69b94;flex-shrink:0;
}
.page-navigation{
display:flex;align-items:center;justify-content:center;
gap:28px;margin-top:28px;
}
.circle-btn{
width:49px;height:49px;border-radius:50%;
border:1px solid #e4dcd5;background:white;
color:var(--brown);font-size:23px;display:grid;place-items:center;
transition:.2s;
}
.circle-btn:hover{background:var(--orange);color:white;border-color:var(--orange)}
.circle-btn:disabled{opacity:.35;cursor:not-allowed}
.page-counter{font-size:15px;color:#70645d;font-weight:700;min-width:70px}
.book-information{margin-top:25px}
.book-information h3{font-family:'Playfair Display',serif;font-size:23px;margin-bottom:8px}
.book-information p{font-size:13px;color:#938981}

/* NEW FEATURES INTRODUCTION */
.creation-section{background:#faf7f3;padding:85px 0}
.creation-heading{text-align:center;margin-bottom:45px}
.creation-pill{
display:inline-block;background:#fff;border:1px solid #eee4dc;
border-radius:40px;padding:10px 23px;color:#9c5949;
font-size:13px;font-weight:700;
}
.creation-pill span{color:#aaa09a;font-size:12px;margin-left:9px}
.creation-heading h2{
font-size:clamp(34px,5vw,52px);letter-spacing:-1.5px;
margin:25px 0 14px;color:#382d29;
}
.creation-heading p{color:#a39a94;font-size:15px;line-height:1.8}
.creation-card,.cover-studio{
background:#fff;border:1px solid #eee8e2;
border-radius:19px;padding:30px;
box-shadow:0 12px 35px #49372b08;
}
.creation-card{max-width:760px;margin:0 auto 35px}
.creation-icon{
width:53px;height:53px;background:#fff0e9;
border-radius:15px;display:grid;place-items:center;
font-size:27px;margin-bottom:20px;
}
.creation-card h3{color:#382d29;font-size:27px;margin-bottom:10px;letter-spacing:-.6px}
.creation-card .subtext{
color:#a49b95;font-size:13px;line-height:1.8;margin-bottom:24px;
}
.orange-label,.cover-label{
color:#ef785f;font-size:12px;font-weight:800;
letter-spacing:2px;margin-bottom:13px;
}
.creation-input{
width:100%;min-height:115px;resize:vertical;
border:1px solid #e9e3dc;border-radius:13px;
padding:19px;font-family:inherit;font-size:14px;
outline:none;color:#382d29;background:#fff;
}
.creation-input:focus{border-color:#efaa99}
.example-prompt{
margin-top:17px;padding:15px 17px;
border:1px solid #eee7e0;border-radius:11px;
display:flex;justify-content:space-between;align-items:center;
gap:10px;color:#72665f;font-size:13px;background:#fffdfa;
}
.example-prompt button{
border:0;background:transparent;color:#ef785f;font-size:23px;
}
.ready-row{
display:flex;align-items:center;gap:10px;
margin-top:22px;color:#5d6e5c;font-size:13px;font-weight:700;
}
.green-check{
height:23px;width:23px;min-width:23px;
border-radius:50%;background:#38965c;color:white;
display:grid;place-items:center;font-size:14px;
}
.mini-book-area{display:flex;justify-content:center;padding:25px 0 5px}
.mini-book{
width:155px;height:205px;border-radius:5px;
background:linear-gradient(145deg,#789b65,#294e38);
box-shadow:7px 8px 18px #00000020;
display:flex;flex-direction:column;justify-content:space-between;
text-align:center;padding:19px 12px;color:white;
}
.mini-book small{font-size:8px;letter-spacing:2px}
.mini-book strong{font-family:'Playfair Display',serif;font-size:23px;line-height:1.3}
.mini-book span{font-size:9px;letter-spacing:1px}
.cover-studio{max-width:900px;margin:0 auto}
.cover-studio-heading{text-align:center}
.cover-studio-heading .creation-icon{margin:0 auto 20px}
.cover-studio-heading h3{
font-size:clamp(28px,4vw,39px);color:#382d29;margin-bottom:12px;
}
.cover-studio-heading h3 span{color:#ef785f}
.cover-studio-heading p{
color:#a49b95;font-size:13px;line-height:1.8;
max-width:520px;margin:0 auto 35px;
}
.cover-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
.cover-option{text-align:center}
.cover-art{
width:100%;max-width:190px;height:245px;margin:auto;
padding:20px 12px;border-radius:5px;
box-shadow:5px 8px 18px #00000019;
display:flex;flex-direction:column;justify-content:space-between;
align-items:center;color:white;transition:.25s;
}
.cover-art:hover{transform:translateY(-7px)}
.cover-art small{font-size:8px;letter-spacing:2px}
.cover-art strong{font-family:'Playfair Display',serif;font-size:23px;line-height:1.3}
.cover-art span{font-size:9px;letter-spacing:1px}
.cover-one{background:linear-gradient(150deg,#263b63,#111d38)}
.cover-two{background:linear-gradient(150deg,#d7b77b,#785333)}
.cover-three{background:linear-gradient(150deg,#805d9b,#36254e)}
.cover-option h4{font-size:13px;margin-top:17px;color:#493a32}
.cover-option p{font-size:11px;color:#a49b95;margin-top:6px}
.cover-studio .ready-row{justify-content:center;margin-top:32px}

/* FEATURES */
.features-section{padding:90px 0}
.section-head{text-align:center;margin-bottom:48px}
.section-head p{color:var(--muted);font-size:14px;margin-top:13px}
.features{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.feature{
padding:27px;border:1px solid var(--border);
border-radius:13px;background:white;transition:.2s;
}
.feature:hover{transform:translateY(-4px);box-shadow:0 10px 25px #00000008}
.feature-icon{
width:45px;height:45px;border-radius:12px;
background:#fff0ec;display:grid;place-items:center;
font-size:22px;margin-bottom:17px;
}
.feature h3{font-size:18px;margin-bottom:10px}
.feature p{font-size:13px;line-height:1.8;color:var(--muted)}

/* HOW IT WORKS */
.how{background:#fff8f5;padding:85px 0}
.steps{display:grid;grid-template-columns:repeat(3,1fr);gap:25px}
.step{text-align:center;padding:20px}
.step-number{font-size:43px;color:var(--orange);font-weight:800}
.step h3{font-size:20px;margin:15px 0 10px}
.step p{font-size:13px;line-height:1.8;color:var(--muted)}

/* REVIEWS */
.reviews{padding:90px 0;background:white}
.review-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.review-card{border:1px solid var(--border);border-radius:13px;padding:24px;background:white}
.stars{color:#e8a63e;font-size:20px;letter-spacing:3px;margin-bottom:15px}
.review-card h3{font-size:16px;margin-bottom:10px}
.review-text{font-size:13px;color:#77706b;line-height:1.8}
.review-text.collapsed{
display:-webkit-box;-webkit-line-clamp:3;
-webkit-box-orient:vertical;overflow:hidden;
}
.read-more{
background:none;border:0;color:#d86e59;
font-size:12px;font-weight:700;margin-top:9px;
}
.reviewer{display:flex;align-items:center;gap:11px;margin-top:20px}
.avatar{
height:36px;width:36px;border-radius:50%;
background:#fae7df;display:grid;place-items:center;
font-weight:700;color:#a85c49;font-size:13px;
}
.reviewer strong{font-size:12px}
.reviewer small{display:block;color:#999;font-size:10px;margin-top:3px}

/* PRICING */
.pricing{padding:90px 0}
.price-card{
max-width:430px;margin:auto;padding:32px;
border:1px solid var(--border);border-radius:15px;
}
.price{font-size:50px;font-weight:800;margin:18px 0}
.price small{font-size:13px;color:var(--muted)}
.price-card ul{list-style:none;margin:25px 0}
.price-card li{padding:10px 0;font-size:14px}
.price-card li:before{content:"✓";color:var(--orange);margin-right:10px}
.btn-primary{
background:var(--orange);color:white;border:0;
border-radius:8px;padding:13px 20px;
font-size:13px;font-weight:700;
}
.price-card button{width:100%}

/* FAQ */
.faq-section{background:var(--cream);padding:85px 0}
.faq{max-width:750px;margin:auto}
.faq-item{padding:20px 0;border-bottom:1px solid #e5ded7}
.faq-question{
display:flex;justify-content:space-between;
cursor:pointer;font-size:14px;font-weight:700;
}
.faq-answer{
display:none;color:var(--muted);font-size:13px;
line-height:1.8;padding-top:14px;
}
.faq-item.active .faq-answer{display:block}

/* CTA AND FOOTER */
.cta{padding:75px 0;text-align:center}
.cta-inner{background:#382d29;color:white;border-radius:17px;padding:60px 20px}
.cta-inner h2{font-size:clamp(30px,5vw,45px);margin-bottom:15px}
.cta-inner p{color:#d9cfca;margin-bottom:22px;font-size:14px}
footer{border-top:1px solid var(--border);padding:28px 0}
.footer{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:15px}
.footer p,.footer-links{font-size:12px;color:var(--muted)}
.footer-links{display:flex;gap:20px}

/* BOOK CREATOR */
.generator{
position:fixed;inset:0;background:#201c1af5;
z-index:100;display:none;overflow-y:auto;padding:18px;
}
.generator.open{display:block}
.gen-inner{max-width:950px;margin:auto;color:white}
.gen-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:25px}
.gen-top button{
background:#ffffff20;color:white;border:0;
padding:11px 17px;border-radius:8px;
}
.gen-grid{display:grid;grid-template-columns:330px 1fr;gap:20px}
.gen-panel{background:white;color:var(--brown);padding:24px;border-radius:12px}
.gen-panel h2{font-size:23px;margin-bottom:10px}
.gen-panel>p{font-size:12px;color:var(--muted);margin-bottom:20px}
.field{margin-bottom:16px}
.field label{display:block;font-size:11px;font-weight:700;margin-bottom:8px}
.field input,.field textarea,.field select{
width:100%;padding:12px;border:1px solid var(--border);
border-radius:7px;font:inherit;font-size:12px;
}
.field textarea{height:90px;resize:vertical}
.gen-panel .btn-primary{width:100%}
.gen-preview{background:#f7f4f0;color:var(--brown);padding:20px;border-radius:12px}
.gen-preview-top{display:flex;justify-content:space-between;font-size:12px;margin-bottom:15px}
.result-cover{
min-height:220px;background:linear-gradient(145deg,#f47761,#9c4c43);
display:flex;flex-direction:column;align-items:center;
justify-content:center;color:white;text-align:center;padding:25px;
}
.result-cover h2{font-family:'Playfair Display',serif;font-size:28px;margin:18px 0}
.result-content{background:white;padding:23px}
.result-content h3{margin:15px 0}
.result-content p{font-size:12px;line-height:1.8;color:var(--muted)}
.chapter-nav{display:flex;flex-wrap:wrap;gap:6px;margin:13px 0}
.chapter-nav button{
padding:8px;border:1px solid var(--border);
background:white;border-radius:5px;font-size:10px;
}
.chapter-nav button.selected{background:var(--brown);color:white}
.result-content textarea{
width:100%;height:145px;padding:12px;
border:1px solid var(--border);font:inherit;font-size:12px;
}
.result-actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
.status{font-size:11px;color:#60856a;margin-top:12px}

/* MOBILE */
@media(max-width:750px){
.features,.review-grid{grid-template-columns:repeat(2,1fr)}
.gen-grid{grid-template-columns:1fr}
}
@media(max-width:550px){
header{height:65px}
.nav{width:92%}
.logo{font-size:19px}
.menu-btn{font-size:28px}
.menu-panel{top:65px}
.hero{padding:25px 0 45px}
.social-proof{font-size:12px;padding:10px 13px;margin-bottom:38px}
.hero h1{font-size:46px;letter-spacing:-1.8px;margin-bottom:32px}
.hero-description{font-size:17px}
.prompt-wrap{margin-top:30px}
.prompt-box{height:165px}
.prompt-box textarea{height:125px;padding:21px;font-size:17px}
.send-btn{height:50px;width:50px;right:14px;bottom:12px;font-size:28px}
.suggestions{flex-direction:column;align-items:center}
.suggestion{font-size:13px;padding:10px 17px}
.hero-note{font-size:14px;margin-top:35px}
.platforms{padding:45px 0 75px}
.platform-grid{gap:20px 13px}
.platform{width:55px;height:50px}
.platform img{max-width:42px;max-height:36px}
.showcase{padding:70px 0}
.section-title{font-size:36px;letter-spacing:-1px}
.section-description{font-size:16px}
.single-page{height:450px;min-height:450px;max-height:450px}
.book-cover,.inside-page{height:450px;min-height:450px;max-height:450px}
.book-cover{padding:35px 22px}
.cover-title{font-size:31px}
.cover-art{font-size:68px}
.inside-page{padding:32px 24px 24px}
.inside-page h3{font-size:23px}
.inside-page p{font-size:13px;line-height:1.8}
.creation-section{padding:65px 0}
.creation-card,.cover-studio{padding:22px 17px}
.creation-card h3{font-size:23px}
.example-prompt{font-size:11px}
.cover-grid{gap:10px}
.cover-art{height:185px;padding:13px 7px}
.cover-art strong{font-size:17px}
.cover-art small,.cover-art span{font-size:7px}
.cover-option h4{font-size:11px}
.features-section,.pricing,.faq-section,.how,.reviews{padding:70px 0}
.features,.steps,.review-grid{grid-template-columns:1fr}
.cta-inner{padding:45px 17px}
.footer{flex-direction:column;align-items:flex-start}
}
</style>
</head>

<body>

<!-- HEADER -->
<header>
<div class="nav">
<a href="#" class="logo">YourBrand<span>.ai</span></a>
<button class="menu-btn" onclick="toggleMenu()" aria-label="Open menu">☰</button>
<nav class="menu-panel" id="menuPanel">
<a href="#showcase">Book examples</a>
<a href="#creation">Features</a>
<a href="#features">More features</a>
<a href="#how">How it works</a>
<a href="#reviews">Reviews</a>
<a href="#pricing">Pricing</a>
<a href="#faq">FAQ</a>
</nav>
</div>
</header>

<!-- HERO -->
<section class="hero">
<div class="container">
<div class="social-proof">
<span class="proof-dot"></span>
Loved by 12,000+ creators publishing with AI
</div>

<h1>Write it once.<br><span>Let it earn<br>forever.</span></h1>

<p class="hero-description">
Just tell Booker what you know. Watch it write every chapter and design your cover, building your finished ebook live in front of you.
</p>

<div class="prompt-wrap">
<div class="prompt-box">
<textarea id="mainPrompt" placeholder="Tell Booker what your book is about..."></textarea>
<button class="send-btn" onclick="startBook()">↑</button>
</div>

<div class="suggestions">
<button class="suggestion" onclick="useSuggestion(this)">A meal-prep guide for busy parents</button>
<button class="suggestion" onclick="useSuggestion(this)">Side-hustle 101 for complete beginners</button>
<button class="suggestion" onclick="useSuggestion(this)">A productivity system that actually sticks</button>
</div>
</div>

<div class="hero-note">No credit card to start · cancel anytime · plans from $29/mo</div>
<a href="#how" class="see-how">See how it works ↓</a>
</div>
</section>

<!-- PUBLISHING PLATFORMS -->
<section class="platforms">
<div class="container">
<div class="platform-title">PUBLISH AND SELL ON</div>
<div class="platform-grid">

<a class="platform" href="https://kdp.amazon.com/" target="_blank">
<img src="https://cdn.simpleicons.org/amazonkindle/777777" alt="Amazon KDP">
</a>
<a class="platform" href="https://books.apple.com/" target="_blank">
<img src="https://cdn.simpleicons.org/applebooks/777777" alt="Apple Books">
</a>
<a class="platform" href="https://www.etsy.com/" target="_blank">
<img src="https://cdn.simpleicons.org/etsy/777777" alt="Etsy">
</a>
<a class="platform" href="https://gumroad.com/" target="_blank">
<img src="https://cdn.simpleicons.org/gumroad/777777" alt="Gumroad">
</a>
<a class="platform" href="https://www.instagram.com/" target="_blank">
<img src="https://cdn.simpleicons.org/instagram/777777" alt="Instagram">
</a>
<a class="platform" href="https://www.tiktok.com/" target="_blank">
<img src="https://cdn.simpleicons.org/tiktok/777777" alt="TikTok">
</a>
<a class="platform" href="https://www.facebook.com/" target="_blank">
<img src="https://cdn.simpleicons.org/facebook/777777" alt="Facebook">
</a>
<a class="platform" href="https://www.shopify.com/" target="_blank">
<img src="https://cdn.simpleicons.org/shopify/777777" alt="Shopify">
</a>

</div>
</div>
</section>

<!-- EBOOK SHOWCASE -->
<section class="showcase" id="showcase">
<div class="container">
<div class="section-tag">FLIP THROUGH A REAL BOOK</div>
<h2 class="section-title">See exactly what you'll create</h2>
<p class="section-description">
These are real books made with YourBrand.ai. One is a polished ebook which can sell many times. Tap the arrows to flip through its first pages.
</p>

<div class="book-viewer">
<div class="book-stage">
<div class="single-page" id="singlePage"></div>
</div>

<div class="page-navigation">
<button class="circle-btn" id="prevBtn" onclick="previousPage()">←</button>
<span class="page-counter" id="pageCounter">1 of 12</span>
<button class="circle-btn" id="nextBtn" onclick="nextPage()">→</button>
</div>

<div class="book-information">
<h3>Healthy Living: Small Habits, Big Changes</h3>
<p>Ebook cover + 11 pages · Digital Ebook</p>
</div>
</div>
</div>
</section>

<!-- NEW FEATURES: IDEA TO BOOK AND COVER STUDIO -->
<section class="creation-section" id="creation">
<div class="container">

<div class="creation-heading">
<div class="creation-pill">FEATURES <span>WHAT YOU GET</span></div>
<h2>Everything you need to<br>publish and profit.</h2>
<p>No writing degree, no design skill, no ghostwriter invoice.<br>Just your idea and a few minutes.</p>
</div>

<!-- IDEA TO FINISHED BOOK -->
<div class="creation-card">

<div class="creation-icon">✎</div>

<h3>From idea to finished book.</h3>

<p class="subtext">
Type one sentence about what you want to know.
Get ebook turns it into a titled, chaptered and fully written ebook.
</p>

<div class="orange-label">YOUR IDEA</div>

<textarea class="creation-input" id="featureIdea" placeholder="Type your book idea here..."></textarea>

<div class="orange-label" style="margin-top:25px">
FROM IDEA TO FINISHED BOOK
</div>

<div class="example-prompt">
<span>How to grow tomatoes in small spaces</span>
<button onclick="fillFeatureIdea()">→</button>
</div>

<div class="mini-book-area">
<div class="mini-book">
<small>THE GARDENING GUIDE</small>
<strong>Grow<br>Tomatoes<br>Anywhere</strong>
<span>A PRACTICAL GUIDE</span>
</div>
</div>

<div class="ready-row">
<span class="green-check">✓</span>
Fully ebook ready
</div>

</div>

<!-- COVER STUDIO -->
<div class="cover-studio">

<div class="cover-studio-heading">
<div class="creation-icon">▧</div>
<div class="orange-label">COVER STUDIO</div>

<h3>Covers that <span>earn the click.</span></h3>

<p>
Get a professional cover design for you and the kind that stands out on the crowded store page.
</p>
</div>

<div class="cover-label">EXPLORE YOUR COVER DESIGNS</div>

<div class="cover-grid">

<div class="cover-option">
<div class="cover-art cover-one">
<small>THE COMPLETE GUIDE</small>
<strong>Dating<br>Mastery</strong>
<span>BUILD BETTER CONNECTIONS</span>
</div>
<h4>Dating Mastery</h4>
<p>Modern & elegant</p>
</div>

<div class="cover-option">
<div class="cover-art cover-two">
<small>THE ART OF LIVING</small>
<strong>Balance &<br>Brilliance</strong>
<span>YOUR JOURNEY STARTS HERE</span>
</div>
<h4>Balance & Brilliance</h4>
<p>Premium & minimal</p>
</div>

<div class="cover-option">
<div class="cover-art cover-three">
<small>UNLOCK YOUR POTENTIAL</small>
<strong>Success<br>Secrets</strong>
<span>THE NEXT CHAPTER</span>
</div>
<h4>Success Secrets</h4>
<p>Bold & creative</p>
</div>

</div>

<div class="ready-row">
<span class="green-check">✓</span>
Cover ready
</div>

</div>
</div>
</section>

<!-- MORE FEATURES -->
<section class="features-section" id="features">
<div class="container">
<div class="section-head">
<div class="section-tag">YOUR COMPLETE BOOK STUDIO</div>
<h2 class="section-title">Everything you need to create your next ebook.</h2>
<p>One workspace. Your ideas. Your finished digital products.</p>
</div>

<div class="features">
<div class="feature"><div class="feature-icon">✍️</div><h3>AI Book Writing</h3><p>Transform your ideas into organized book outlines and readable chapters.</p></div>
<div class="feature"><div class="feature-icon">🎨</div><h3>Book Cover Design</h3><p>Create attractive cover concepts for your digital books.</p></div>
<div class="feature"><div class="feature-icon">📚</div><h3>Book Structures</h3><p>Organize your ebooks into sections and chapters.</p></div>
<div class="feature"><div class="feature-icon">📝</div><h3>Chapter Editor</h3><p>Edit your manuscript and customize your writing.</p></div>
<div class="feature"><div class="feature-icon">📄</div><h3>Book Export</h3><p>Prepare your book for digital publishing.</p></div>
<div class="feature"><div class="feature-icon">🚀</div><h3>Publishing Workflow</h3><p>Bring your book idea from the first prompt to a finished manuscript.</p></div>
</div>
</div>
</section>

<!-- HOW IT WORKS -->
<section class="how" id="how">
<div class="container">
<div class="section-head">
<div class="section-tag">HOW IT WORKS</div>
<h2 class="section-title">Your knowledge deserves to become a book.</h2>
</div>
<div class="steps">
<div class="step"><div class="step-number">01</div><h3>Tell Booker your idea</h3><p>Enter a topic or concept you want to turn into a book.</p></div>
<div class="step"><div class="step-number">02</div><h3>Create your manuscript</h3><p>Develop your outline and chapters in one workspace.</p></div>
<div class="step"><div class="step-number">03</div><h3>Publish your ebook</h3><p>Review your work and prepare it for publishing.</p></div>
</div>
</div>
</section>

<!-- REVIEWS -->
<section class="reviews" id="reviews">
<div class="container">
<div class="section-head">
<div class="section-tag">CREATOR REVIEWS</div>
<h2 class="section-title">Loved by creators.</h2>
<p>See what people have to say.</p>
</div>

<div class="review-grid">

<div class="review-card">
<div class="stars">★★★★★</div>
<h3>Really easy to use!</h3>
<p class="review-text collapsed" id="review1">
I always wanted to write my own ebook but never knew where to start. The simple workflow makes the whole idea feel much more manageable. I especially like the way the chapters are organized and how I can review everything before finishing my book.
</p>
<button class="read-more" onclick="toggleReview('review1',this)">Read more</button>
<div class="reviewer"><div class="avatar">S</div><div><strong>Sarah M.</strong><small>Digital Creator</small></div></div>
</div>

<div class="review-card">
<div class="stars">★★★★★</div>
<h3>Beautiful book layouts.</h3>
<p class="review-text collapsed" id="review2">
The book preview is my favourite part. Seeing a cover and the inside pages together makes it easier to imagine the final product. I also appreciate being able to edit the writing instead of having everything feel fixed.
</p>
<button class="read-more" onclick="toggleReview('review2',this)">Read more</button>
<div class="reviewer"><div class="avatar">J</div><div><strong>James R.</strong><small>Self Publisher</small></div></div>
</div>

<div class="review-card">
<div class="stars">★★★★★</div>
<h3>Great for beginners.</h3>
<p class="review-text collapsed" id="review3">
I like how straightforward the experience is. Instead of feeling overwhelmed by a blank document, you can start with an idea and organize it into sections. The clean design and book preview make the experience feel welcoming.
</p>
<button class="read-more" onclick="toggleReview('review3',this)">Read more</button>
<div class="reviewer"><div class="avatar">E</div><div><strong>Emily K.</strong><small>Content Creator</small></div></div>
</div>

</div>
<p style="text-align:center;font-size:11px;color:#aaa;margin-top:25px">
Illustrative sample testimonials — replace with genuine customer reviews before publishing.
</p>
</div>
</section>

<!-- PRICING -->
<section class="pricing" id="pricing">
<div class="container">
<div class="section-head">
<div class="section-tag">SIMPLE PRICING</div>
<h2 class="section-title">Start creating today.</h2>
</div>

<div class="price-card">
<h3>Creator Plan</h3>
<div class="price">$29<small> / month</small></div>
<p style="font-size:12px;color:#888">Example pricing. Payments are not connected.</p>
<ul>
<li>Book creation workspace</li>
<li>Book outline tools</li>
<li>Chapter editing</li>
<li>Cover design workspace</li>
<li>Manuscript preview</li>
<li>Publishing preparation</li>
</ul>
<button class="btn-primary" onclick="openGenerator()">Start creating →</button>
</div>
</div>
</section>

<!-- FAQ -->
<section class="faq-section" id="faq">
<div class="container">
<div class="section-head">
<div class="section-tag">FAQ</div>
<h2 class="section-title">Frequently asked questions.</h2>
</div>

<div class="faq">
<div class="faq-item"><div class="faq-question" onclick="toggleFaq(this)">What is Booker? <span>+</span></div><div class="faq-answer">Booker is the ebook creation assistant concept, designed to help users turn ideas into organized books.</div></div>
<div class="faq-item"><div class="faq-question" onclick="toggleFaq(this)">Do I need writing experience? <span>+</span></div><div class="faq-answer">No. The planned workflow is designed for beginners as well as experienced writers.</div></div>
<div class="faq-item"><div class="faq-question" onclick="toggleFaq(this)">Can I edit my book? <span>+</span></div><div class="faq-answer">Yes. The demonstration workspace includes editable chapter text.</div></div>
<div class="faq-item"><div class="faq-question" onclick="toggleFaq(this)">Can I download my book? <span>+</span></div><div class="faq-answer">The frontend demonstration allows you to download your sample manuscript as an HTML document.</div></div>
<div class="faq-item"><div class="faq-question" onclick="toggleFaq(this)">Can I sell my ebooks? <span>+</span></div><div class="faq-answer">You can prepare your manuscript for publishing. Actual sales depend on the publishing platform and its policies.</div></div>
</div>
</div>
</section>

<!-- CTA -->
<section class="cta">
<div class="container">
<div class="cta-inner">
<h2>Write it once. Let it earn forever.</h2>
<p>Your next ebook starts with a single idea.</p>
<button class="btn-primary" onclick="openGenerator()">Create your first book →</button>
</div>
</div>
</section>

<!-- FOOTER -->
<footer>
<div class="container footer">
<a href="#" class="logo">YourBrand<span>.ai</span></a>
<div class="footer-links">
<a href="#features">Features</a>
<a href="#pricing">Pricing</a>
<a href="#faq">FAQ</a>
</div>
<p>© 2026 YourBrand.ai</p>
</div>
</footer>

<!-- BOOK CREATOR MODAL -->
<div class="generator" id="generator">
<div class="gen-inner">

<div class="gen-top">
<h2>Booker — Book Studio</h2>
<button onclick="closeGenerator()">✕ Close</button>
</div>

<div class="gen-grid">

<div class="gen-panel">
<h2>Create your book</h2>
<p>Customize your book details and create a sample preview.</p>

<div class="field">
<label>BOOK TOPIC</label>
<textarea id="bookTopic" placeholder="What is your book about?"></textarea>
</div>

<div class="field">
<label>TARGET AUDIENCE</label>
<input id="bookAudience" placeholder="Example: Beginners">
</div>

<div class="field">
<label>BOOK TYPE</label>
<select id="bookType">
<option>Educational Ebook</option>
<option>Practical Guide</option>
<option>Business Ebook</option>
<option>Self Improvement</option>
<option>Workbook</option>
</select>
</div>

<button class="btn-primary" onclick="generateBook()">Generate book preview →</button>
<div class="status" id="genStatus"></div>
</div>

<div class="gen-preview">
<div class="gen-preview-top">
<b>YOUR BOOK PREVIEW</b>
<span id="previewStatus">Waiting for your idea</span>
</div>

<div id="bookResult" style="background:white;min-height:350px;padding:30px;text-align:center">
<div style="font-size:50px;margin-top:90px">📖</div>
<h3>Your book starts here.</h3>
</div>
</div>

</div>
</div>
</div>

<script>

/* HEADER */
function toggleMenu(){
document.getElementById('menuPanel').classList.toggle('open');
}

document.querySelectorAll('.menu-panel a').forEach(link=>{
link.addEventListener('click',()=>{
document.getElementById('menuPanel').classList.remove('open');
});
});

/* HERO PROMPT */
function useSuggestion(button){
document.getElementById('mainPrompt').value=button.textContent.trim();
}

function openGenerator(topic=''){
document.getElementById('generator').classList.add('open');
document.body.style.overflow='hidden';
if(topic)document.getElementById('bookTopic').value=topic;
}

function closeGenerator(){
document.getElementById('generator').classList.remove('open');
document.body.style.overflow='';
}

function startBook(){
const topic=document.getElementById('mainPrompt').value.trim();
if(topic.length<5){
document.getElementById('mainPrompt').focus();
return;
}
openGenerator(topic);
generateBook();
}

document.getElementById('mainPrompt').addEventListener('keydown',function(e){
if(e.key==='Enter'&&!e.shiftKey){
e.preventDefault();
startBook();
}
});

/* FEATURE EXAMPLE */
function fillFeatureIdea(){
const input=document.getElementById('featureIdea');
input.value='How to grow tomatoes in small spaces';
input.focus();
}

/* BOOK READER */
const bookPages=[
{
heading:'Welcome to a Healthier Life',
text:'Small changes can make a meaningful difference over time. This book explores simple ways to build everyday habits that support a balanced lifestyle.\n\nThe goal is not perfection. It is consistency, curiosity and progress.'
},
{
heading:'Chapter 1 — Start Small',
text:'A lasting routine often begins with a small, manageable action.\n\nChoose one habit that fits your everyday schedule. Make it easy to repeat and give yourself time to become comfortable with it.'
},
{
heading:'Chapter 2 — Building a Routine',
text:'A routine works best when it fits naturally into your day.\n\nConnect a new habit to something you already do. Keep your plan realistic and adjust it when your circumstances change.'
},
{
heading:'Chapter 3 — Everyday Nutrition',
text:'A balanced eating pattern can include a variety of fruits, vegetables, grains, proteins and other foods.\n\nExplore different ingredients, enjoy variety and learn simple meal preparation techniques.'
},
{
heading:'Chapter 4 — Meal Planning',
text:'Planning meals can make busy days easier.\n\nCreate a simple weekly menu, prepare a shopping list and organize ingredients in advance. Leave room for flexibility.'
},
{
heading:'Chapter 5 — Staying Active',
text:'Movement can be part of ordinary daily life.\n\nFind enjoyable activities that suit your interests and abilities. Consistency matters more than complicated routines.'
},
{
heading:'Chapter 6 — Rest and Recovery',
text:'Rest is an important part of everyday wellbeing.\n\nBuild a comfortable evening routine and make space for regular breaks throughout your day.'
},
{
heading:'Chapter 7 — Managing Busy Days',
text:'Busy schedules can make routines challenging.\n\nPrepare simple alternatives for days when your normal plan is difficult. Small actions can help maintain continuity.'
},
{
heading:'Chapter 8 — Creating Your Own Plan',
text:'Choose the ideas that work best for your lifestyle.\n\nWrite down a few realistic habits, identify possible obstacles and decide how you will review your progress.'
},
{
heading:'A Weekly Habit Checklist',
text:'My weekly planning checklist:\n\n□ Plan meals\n\n□ Organize daily activities\n\n□ Make time for enjoyable movement\n\n□ Review personal goals\n\n□ Prepare for the week ahead'
},
{
heading:'Your Next Chapter',
text:'A healthier routine is something you can continue developing.\n\nStay flexible, keep learning and celebrate the useful habits you build along the way.'
}
];

let currentPage=0;
const totalPages=12;

function renderBook(){
const page=document.getElementById('singlePage');

if(currentPage===0){
page.innerHTML=`
<div class="book-cover">
<div class="cover-top">YOUR GUIDE TO BETTER LIVING</div>
<div>
<div class="cover-art">🌿</div>
<h2 class="cover-title">Healthy Living:<br>Small Habits,<br>Big Changes</h2>
<p class="cover-subtitle">A practical guide to building better everyday habits.</p>
</div>
<div class="cover-author">A PRACTICAL GUIDE</div>
</div>`;
}else{
const data=bookPages[currentPage-1];
page.innerHTML=`
<div class="inside-page">
<div class="page-content">
<div class="page-top-label">HEALTHY LIVING · YOURBRAND.AI</div>
<div class="page-decoration"></div>
<h3>${data.heading}</h3>
<p>${data.text}</p>
</div>
<div class="page-bottom">
<span>HEALTHY LIVING</span>
<span>${currentPage+1}</span>
</div>
</div>`;
}

document.getElementById('pageCounter').textContent=(currentPage+1)+' of '+totalPages;
document.getElementById('prevBtn').disabled=currentPage===0;
document.getElementById('nextBtn').disabled=currentPage===totalPages-1;
}

function changePage(direction){
const next=currentPage+direction;
if(next<0||next>=totalPages)return;

const page=document.getElementById('singlePage');
page.classList.remove('turning');
void page.offsetWidth;

currentPage=next;
renderBook();
page.classList.add('turning');
}

function nextPage(){changePage(1)}
function previousPage(){changePage(-1)}

renderBook();

/* REVIEW READ MORE */
function toggleReview(id,button){
const review=document.getElementById(id);
review.classList.toggle('collapsed');
button.textContent=review.classList.contains('collapsed')?'Read more':'Read less';
}

/* FAQ */
function toggleFaq(element){
element.parentElement.classList.toggle('active');
}

/* FRONTEND BOOK CREATOR */
let chapters=[];
let currentChapter=0;
let generatedTitle='';

function escapeHTML(str){
return String(str).replace(/[&<>"']/g,c=>({
'&':'&amp;',
'<':'&lt;',
'>':'&gt;',
'"':'&quot;',
"'":'&#39;'
})[c]);
}

function generateBook(){
const topic=document.getElementById('bookTopic').value.trim();
const audience=document.getElementById('bookAudience').value.trim()||'General readers';

if(topic.length<5){
document.getElementById('genStatus').textContent='Please enter a book topic.';
return;
}

document.getElementById('genStatus').textContent='Creating your sample book...';
document.getElementById('previewStatus').textContent='Working...';

setTimeout(()=>{
generatedTitle=topic.charAt(0).toUpperCase()+topic.slice(1);

chapters=[
{title:'Introduction',text:`Welcome to ${generatedTitle}.\n\nThis book is designed for ${audience}. It introduces the subject in a clear and approachable way.`},
{title:'Understanding the Basics',text:`Explore the foundations of ${generatedTitle}.\n\nLearn the central concepts, understand the terminology and build your knowledge step by step.`},
{title:'Essential Principles',text:`Discover the important principles behind this subject.\n\nOrganize your learning into useful sections and support factual information with reliable research.`},
{title:'Practical Applications',text:`Explore examples and practical ways to apply what you have learned.\n\nAdapt the recommendations to your audience and circumstances.`},
{title:'Common Challenges',text:`Understand common questions and difficulties.\n\nLook for reliable resources and additional information where necessary.`},
{title:'Conclusion',text:`Thank you for reading ${generatedTitle}.\n\nContinue learning and developing your understanding of this topic.`}
];

currentChapter=0;
renderGeneratedBook();

document.getElementById('genStatus').textContent='✓ Sample book created.';
document.getElementById('previewStatus').textContent='Preview ready';
},500);
}

function renderGeneratedBook(){
document.getElementById('bookResult').innerHTML=`
<div class="result-cover">
<div>YOUR BRAND EDITION</div>
<h2>${escapeHTML(generatedTitle)}</h2>
<div>✦ A PRACTICAL GUIDE ✦</div>
</div>
<div class="result-content">
<h3>Table of contents</h3>
<div class="chapter-nav" id="chapterNav"></div>
<h3 id="chapterTitle"></h3>
<textarea id="chapterEditor"></textarea>
<div class="result-actions">
<button class="btn-primary" onclick="saveChapter()">Save changes</button>
<button class="btn-primary" onclick="downloadBook()">Download book</button>
</div>
</div>`;
renderChapter();
}

function renderChapter(){
const nav=document.getElementById('chapterNav');
const editor=document.getElementById('chapterEditor');
if(!nav||!editor)return;

nav.innerHTML='';

chapters.forEach((chapter,index)=>{
const button=document.createElement('button');
button.textContent=(index+1)+'. '+chapter.title;
button.className=index===currentChapter?'selected':'';

button.onclick=()=>{
saveChapter();
currentChapter=index;
renderChapter();
};

nav.appendChild(button);
});

document.getElementById('chapterTitle').textContent=chapters[currentChapter].title;
editor.value=chapters[currentChapter].text;
}

function saveChapter(){
const editor=document.getElementById('chapterEditor');
if(editor&&chapters[currentChapter]){
chapters[currentChapter].text=editor.value;
}
}

function downloadBook(){
saveChapter();

let html=`<!DOCTYPE html><html><head><meta charset="UTF-8">
<title>${escapeHTML(generatedTitle)}</title>
<style>
body{max-width:750px;margin:50px auto;padding:20px;font-family:Georgia;line-height:1.9}
h1{text-align:center}
h2{margin-top:40px}
p{white-space:pre-line}
</style>
</head><body><h1>${escapeHTML(generatedTitle)}</h1>`;

chapters.forEach(chapter=>{
html+=`<h2>${escapeHTML(chapter.title)}</h2><p>${escapeHTML(chapter.text)}</p>`;
});

html+='</body></html>';

const blob=new Blob([html],{type:'text/html;charset=utf-8'});
const url=URL.createObjectURL(blob);
const link=document.createElement('a');

link.href=url;
link.download='yourbrand-ebook.html';
link.click();

URL.revokeObjectURL(url);
}

</script>
</body>
</html>
