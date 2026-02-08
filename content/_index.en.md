---
title: "Yang's Profile"
date: 2026-02-05
layout: "single"
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;800&display=swap" rel="stylesheet">
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>
/* =========================================
复用之前的 CSS 样式
(为了保证英文版样式一致，这里包含完整的 CSS)
========================================= */
* { box-sizing: border-box; }

body, html {
margin: 0 !important;
padding: 0 !important;
width: 100% !important;
overflow-x: hidden !important;
font-family: 'Inter', -apple-system, BlinkMacSystemFont, "PingFang SC", sans-serif !important;
color: #1d1d1f !important;
scroll-behavior: smooth !important;
scroll-padding-top: 90px !important;
}

/* 清除主题干扰 */
.single .content, .page, main, .container {
max-width: 100% !important;
width: 100% !important;
padding: 0 !important;
margin: 0 !important;
background: transparent !important;
}

/* 隐藏不需要的元素 */
.theme-switch, #theme-check, .search-button, .search-mobile, .post-meta, .post-footer, .post-nav { display: none !important; }

/* 语言切换器处理 */
.language-switch, .desktop .language-switch { display: none !important; }

/* =========================================
水晶导航栏
========================================= */
#header-desktop, #header-mobile {
background: rgba(255, 255, 255, 0.2) !important;
backdrop-filter: blur(30px) saturate(200%) !important;
-webkit-backdrop-filter: blur(30px) saturate(200%);
width: 92% !important;
max-width: 1000px !important;
left: 50% !important;
transform: translateX(-50%) !important;
top: 20px !important;
border-radius: 50px !important;
border: 1px solid rgba(255, 255, 255, 0.3) !important;
box-shadow: 0 10px 40px rgba(0,0,0,0.05) !important;
position: fixed !important;
z-index: 999 !important;
height: 60px !important;
padding: 0 20px !important;
overflow: visible !important;
}

.header-title a {
font-family: 'Inter', sans-serif !important;
font-weight: 800 !important;
font-size: 1.4rem !important;
color: #1d1d1f !important;
letter-spacing: -1px !important;
text-decoration: none !important;
}

.header-title {
position: relative !important;
z-index: 1100 !important;
transform: translateX(-50px) !important;
}

.header-wrapper .header-title::after { display: none !important; }

.menu-item {
font-family: 'Inter', sans-serif !important;
font-size: 0.9rem !important;
font-weight: 600 !important;
color: #444 !important;
padding: 14px !important; 
transition: all 0.2s ease !important;
margin: 10 10px !important;
transform: translateX(50px) !important;
border: none !important; 
}

.menu-item:hover {
color: #000 !important;
transform: translateX(48px) scale(1.05) !important; /* 微调：英文版保持一致的缩放 */
}

/* 垂直居中图标 */
.menu-item i {
display: inline-block;
transform: translateY(1px);
}

/* =========================================
背景流
========================================= */
.section-wrapper {
width: 100vw;
min-height: 100vh;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
text-align: center;
padding: 100px 20px;
position: relative;
}

#profile { background: linear-gradient(to bottom, #ffffff 0%, #f0f8ff 100%); }
#education { background: linear-gradient(to bottom, #f0f8ff 0%, #fffbf0 100%); }
#research { background: linear-gradient(to bottom, #fffbf0 0%, #f1f5f9 100%); }
#projects { background: linear-gradient(to bottom, #f1f5f9 0%, #fff0f5 100%); }
#hobbies { background: linear-gradient(to bottom, #fff0f5 0%, #ffffff 100%); }

/* =========================================
组件样式
========================================= */
.section-title {
font-size: 3rem;
font-weight: 700;
letter-spacing: -1.5px;
margin-bottom: 60px;
color: #111;
}

.bento-card {
background: rgba(255, 255, 255, 0.55);
backdrop-filter: blur(30px);
-webkit-backdrop-filter: blur(30px);
border: 1px solid rgba(255, 255, 255, 0.6);
box-shadow: 0 20px 50px -10px rgba(0,0,0,0.08);
border-radius: 32px;
transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.bento-card:hover {
box-shadow: 0 30px 60px -15px rgba(0,0,0,0.15);
background: rgba(255, 255, 255, 0.75);
}

/* =========================================
Profile Section
========================================= */
.profile-container {
display: flex;
flex-direction: row;
gap: 60px;
max-width: 1100px;
width: 100%;
align-items: flex-start;
text-align: left;
padding-top: 40px;
}

.profile-sidebar {
flex: 0 0 280px;
display: flex;
flex-direction: column;
align-items: center;
text-align: center;
}

.profile-main { flex: 1; }

.profile-avatar {
width: 200px;
height: 200px;
border-radius: 50%;
object-fit: cover;
box-shadow: 0 20px 40px rgba(0,0,0,0.1);
border: 4px solid rgba(255,255,255,0.8);
margin-bottom: 25px;
}

.profile-name {
font-size: 2.2rem;
font-weight: 800;
color: #0e0e0f;
margin: 0 0 10px 0;
letter-spacing: -0.5px;
}

.profile-status {
font-size: 1.1rem;
color: #000000;
padding: 10px; /* 英文版稍微调整padding */
margin-bottom: 15px;
font-weight: 500;
}

.social-links {
display: flex;
gap: 15px;
justify-content: center;
}
.social-btn {
width: 45px;
height: 45px;
border-radius: 50%;
background: #fff;
display: flex;
align-items: center;
justify-content: center;
color: #333;
font-size: 1.2rem;
box-shadow: 0 4px 10px rgba(0,0,0,0.08);
transition: all 0.3s ease;
text-decoration: none;
border: 1px solid rgba(0,0,0,0.05);
}
.social-btn:hover {
transform: translateY(-3px);
box-shadow: 0 8px 20px rgba(0,0,0,0.12);
color: #0071e3;
}

.bio-section-title {
font-size: 1.5rem;
font-weight: 700;
margin-bottom: 20px;
color: #111;
display: flex;
align-items: center;
gap: 10px;
}
.bio-section-title::before {
content: '';
display: block;
width: 6px;
height: 24px;
background: #0071e3;
border-radius: 3px;
}

.bio-text {
font-size: 1.05rem;
line-height: 1.8;
color: #444;
margin-bottom: 40px;
}

.research-list {
list-style: none;
padding: 0;
margin: 0;
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 15px;
}

.research-item {
background: rgba(255, 255, 255, 0.6);
border: 1px solid rgba(255,255,255,0.8);
padding: 15px 20px;
border-radius: 12px;
font-size: 1rem;
font-weight: 500;
color: #333;
display: flex;
align-items: center;
gap: 12px;
transition: all 0.2s;
}
.research-item:hover {
background: #fff;
transform: translateX(5px);
box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}
.research-item i {
color: #0071e3;
font-size: 0.9rem;
}

@media (max-width: 768px) {
.profile-container {
flex-direction: column;
align-items: center;
gap: 40px;
}
.profile-sidebar, .profile-main { width: 100%; }
.research-list { grid-template-columns: 1fr; }
}

/* =========================================
Education Section
========================================= */
.edu-list {
display: flex;
flex-direction: column;
gap: 40px;
}
.edu-item {
position: relative;
padding-left: 20px;
}
.edu-item::before {
content: '';
position: absolute;
left: 0;
top: 8px;
bottom: 0;
width: 4px;
background: #e5e5e5;
border-radius: 2px;
}
.edu-item:first-child::before {
background: #0071e3;
}
.edu-header {
display: flex;
justify-content: space-between;
align-items: flex-start;
flex-wrap: wrap;
gap: 10px;
margin-bottom: 5px;
}
.edu-school {
font-size: 1.4rem;
font-weight: 700;
color: #111;
display: flex;
align-items: center;
gap: 10px;
}
.edu-degree-tag {
font-size: 0.8rem;
padding: 2px 8px;
border-radius: 6px;
font-weight: 600;
text-transform: uppercase;
}
.tag-phd { background: #1d1d1f; color: #fff; }
.tag-bach { background: #f0f0f0; color: #666; }
.edu-time {
font-family: 'Inter', monospace;
font-weight: 600;
color: #0071e3;
background: rgba(0,113,227,0.08);
padding: 4px 12px;
border-radius: 15px;
font-size: 0.9rem;
}
.edu-major {
font-size: 1.1rem;
font-weight: 500;
color: #444;
margin-bottom: 12px;
}
.edu-stats {
display: flex;
gap: 12px;
margin-bottom: 15px;
flex-wrap: wrap;
}
.stat-box {
display: flex;
align-items: center;
gap: 6px;
font-size: 0.9rem;
font-weight: 600;
padding: 6px 12px;
border-radius: 8px;
border: 1px solid rgba(0,0,0,0.05);
}
.stat-gold {
background: linear-gradient(135deg, #fffbeb 0%, #fff 100%);
color: #b45309;
border-color: #fcd34d;
}
.edu-awards {
display: flex;
flex-wrap: wrap;
gap: 8px;
}
.award-badge {
font-size: 0.85rem;
color: #555;
background: #fff;
border: 1px solid #e5e5e5;
padding: 4px 10px;
border-radius: 6px;
display: flex;
align-items: center;
gap: 5px;
}
.award-highlight {
background: #f0f9ff;
color: #0284c7;
border-color: #bae6fd;
font-weight: 600;
}

/* =========================================
Research Section
========================================= */
.research-container {
display: flex;
flex-direction: column;
gap: 30px;
width: 100%;
max-width: 1100px;
}
.paper-card {
display: flex;
background: rgba(255, 255, 255, 0.8);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.9);
border-radius: 20px;
overflow: hidden;
transition: all 0.3s ease;
box-shadow: 0 10px 30px -10px rgba(0,0,0,0.05);
min-height: 260px;
}
.paper-card:hover {
transform: translateY(-5px);
box-shadow: 0 25px 50px -12px rgba(0,0,0,0.12);
}
.paper-img-wrapper {
flex: 0 0 400px;
background: #ffffff;
display: flex;
align-items: center;
justify-content: center;
padding: 10px;
border-right: 1px solid rgba(0,0,0,0.05);
}
.paper-img {
width: 100%;
height: 100%;
object-fit: contain;
transition: transform 0.5s ease;
}
.paper-card:hover .paper-img { transform: scale(1.03); }
.paper-content {
flex: 1;
padding: 30px;
text-align: left;
display: flex;
flex-direction: column;
justify-content: center;
}
.paper-meta {
display: flex;
align-items: center;
gap: 10px;
margin-bottom: 12px;
}
.journal-tag {
color: #b45309;
background: #fffbeb;
padding: 4px 12px;
border-radius: 6px;
font-size: 0.85rem;
font-weight: 700;
border: 1px solid #fcd34d;
}
.year-tag {
font-size: 0.9rem;
color: #666;
font-weight: 600;
}
.paper-title {
font-size: 1.35rem;
font-weight: 700;
color: #111;
line-height: 1.4;
margin: 0 0 15px 0;
}
.paper-authors {
font-size: 1rem;
color: #555;
margin-bottom: 25px;
line-height: 1.6;
}
.my-name {
color: #0071e3;
font-weight: 700;
background: rgba(0, 113, 227, 0.1);
padding: 2px 8px;
border-radius: 6px;
border: 1px solid rgba(0, 113, 227, 0.2);
margin: 0 2px;
}
.paper-actions { display: flex; gap: 15px; }
.action-btn {
display: inline-flex;
align-items: center;
gap: 8px;
padding: 8px 18px;
border-radius: 20px;
font-size: 0.9rem;
font-weight: 600;
text-decoration: none;
transition: all 0.2s;
}
.btn-pdf { background: #1d1d1f; color: #fff; }
.btn-pdf:hover { background: #333; transform: translateY(-2px); }
.btn-code { background: #fff; color: #333; border: 1px solid #ddd; }
.btn-code:hover { background: #f5f5f7; border-color: #999; transform: translateY(-2px); }
@media (max-width: 850px) {
.paper-card { flex-direction: column; }
.paper-img-wrapper { 
flex: none; 
width: 100%; 
height: 240px;
border-right: none;
border-bottom: 1px solid rgba(0,0,0,0.05);
}
}

/* =========================================
Projects Section
========================================= */
.project-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
gap: 30px;
width: 100%;
max-width: 1200px;
margin: 0 auto;
}
.project-card {
background: rgba(255, 255, 255, 0.65);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.8);
border-radius: 20px;
overflow: hidden;
transition: all 0.3s ease;
box-shadow: 0 10px 30px -10px rgba(0,0,0,0.05);
display: flex;
flex-direction: column;
}
.project-card:hover {
transform: translateY(-8px);
box-shadow: 0 20px 40px -10px rgba(0,0,0,0.15);
background: rgba(255, 255, 255, 0.9);
}
.project-thumb {
width: 100%;
height: 200px;
object-fit: cover;
border-bottom: 1px solid rgba(0,0,0,0.05);
}
.project-body {
padding: 25px;
text-align: left;
flex: 1;
}
.project-title {
font-size: 1.25rem;
font-weight: 700;
color: #111;
margin: 0 0 10px 0;
line-height: 1.4;
}
.project-tags {
display: flex;
flex-wrap: wrap;
gap: 8px;
margin-bottom: 15px;
}
.tech-tag {
font-size: 0.75rem;
padding: 3px 10px;
border-radius: 12px;
font-weight: 600;
text-transform: uppercase;
}
.tag-blue { background: #e0f2fe; color: #0284c7; }
.tag-green { background: #dcfce7; color: #166534; }
.tag-purple { background: #f3e8ff; color: #7e22ce; }
.tag-orange { background: #ffedd5; color: #c2410c; }
.tag-red { background: #fee2e2; color: #991b1b; }
.project-desc {
margin: 0;
padding-left: 18px;
color: #555;
font-size: 0.95rem;
line-height: 1.6;
}
.project-desc li { margin-bottom: 8px; }
.project-desc li::marker { color: #0071e3; }
@media (max-width: 768px) {
.project-grid { grid-template-columns: 1fr; }
}

/* =========================================
Hobbies Section
========================================= */
.hobbies-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 25px;
width: 100%;
max-width: 1000px;
}
.hobby-card {
background: rgba(255, 255, 255, 0.6);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.8);
border-radius: 24px;
padding: 30px;
text-align: left;
transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
position: relative;
overflow: hidden;
display: flex;
flex-direction: column;
justify-content: space-between;
height: 220px;
}
.hobby-card:hover {
transform: translateY(-5px) scale(1.02);
background: rgba(255, 255, 255, 0.9);
box-shadow: 0 15px 35px rgba(0,0,0,0.1);
}
.card-gaming {
background: linear-gradient(135deg, #fff 0%, #fff7e6 100%);
border-color: #fcd34d;
}
.card-gaming::before {
content: '';
position: absolute;
top: -50%;
left: -50%;
width: 200%;
height: 200%;
background: radial-gradient(circle, rgba(251, 191, 36, 0.1) 0%, transparent 70%);
animation: rotate 10s linear infinite;
pointer-events: none;
}
.rank-badge {
display: inline-block;
background: linear-gradient(90deg, #f59e0b, #fbbf24);
color: #fff;
font-weight: 800;
font-style: italic;
padding: 4px 12px;
border-radius: 4px;
text-transform: uppercase;
box-shadow: 0 4px 10px rgba(245, 158, 11, 0.4);
font-size: 0.9rem;
margin-bottom: 10px;
}
.card-running {
background: linear-gradient(135deg, #fff 0%, #f0f9ff 100%);
}
.pb-time {
font-family: 'Inter', monospace;
font-size: 2.5rem;
font-weight: 800;
color: #0284c7;
letter-spacing: -2px;
margin-top: auto;
}
.pb-label {
font-size: 0.9rem;
color: #666;
font-weight: 600;
text-transform: uppercase;
}
.hobby-icon-large {
font-size: 3rem;
margin-bottom: 15px;
opacity: 0.15;
position: absolute;
right: 20px;
top: 20px;
}
.hobby-title {
font-size: 1.4rem;
font-weight: 700;
color: #111;
z-index: 1;
margin: 0;
}
.hobby-desc {
font-size: 1rem;
color: #555;
margin-top: 10px;
z-index: 1;
line-height: 1.5;
}
.hobby-tags {
display: flex;
flex-wrap: wrap;
gap: 10px;
margin-top: auto;
}
.hobby-tag {
background: #fff;
padding: 6px 14px;
border-radius: 20px;
font-size: 0.9rem;
font-weight: 600;
box-shadow: 0 2px 8px rgba(0,0,0,0.05);
display: flex;
align-items: center;
gap: 6px;
color: #333;
}
@keyframes rotate {
0% { transform: rotate(0deg); }
100% { transform: rotate(360deg); }
}
@keyframes bounce {
0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
40% {transform: translateY(-10px);}
60% {transform: translateY(-5px);}
}
</style>

<div id="profile" class="section-wrapper">
<div class="profile-container">

<div class="profile-sidebar" data-aos="fade-right">
<img src="/images/avatar.jpg" class="profile-avatar" alt="Avatar">

<h1 class="profile-name">Zihao Yang</h1>
<div class="profile-status">Ph.D. Candidate @ Anhui University</div>

<div class="social-links">
<a href="mailto:yangzh1874@qq.com" class="social-btn" title="Email">
<i class="fa-solid fa-envelope"></i>
</a>
<a href="https://github.com/yangjie1874" target="_blank" class="social-btn" title="GitHub">
<i class="fa-brands fa-github"></i>
</a>
<a href="https://scholar.google.com/citations?hl=zh-CN&user=_lQe2coAAAAJ" target="_blank" class="social-btn" title="Google Scholar">
<i class="fa-solid fa-graduation-cap"></i>
</a>
</div>
</div>

<div class="profile-main" data-aos="fade-left" data-aos-delay="100">

<h2 class="bio-section-title">Biography</h2>
<div class="bio-text">
<p>
Hello! I am Zihao Yang, currently a Ph.D. candidate in Electronic Science and Technology at Anhui University.
My research focuses on the intersection of AI in general vision and agriculture, exploring how machines can "understand" the complex world and perform logical reasoning.
My goal is to build efficient, precise, and continuously learning intelligent vision systems.
</p>
</div>

<h2 class="bio-section-title">Research Interests</h2>
<ul class="research-list">
<li class="research-item">
<i class="fa-solid fa-cube"></i>
<div>
General Vision Models<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(Object Detection / Segmentation)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-comments"></i>
<div>
Vision-Language Models<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(MLLM / Diffusion)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-brain"></i>
<div>
Visual Complex Reasoning<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(Chain-of-Thought / Visual Thinking)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-compress"></i>
<div>
Visual Token Compression<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(Pruning / Distillation)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-clock-rotate-left"></i>
<div>
Visual Continual Learning<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(Memory / Fast-Slow Systems)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-robot"></i>
<div>
Embodied AI<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(Robotics / Autonomous Driving)</span>
</div>
</li>
</ul>
</div>
</div>

<div style="position: absolute; bottom: 20px; animation: bounce 2s infinite; opacity: 0.4;">
<svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="#000" stroke-width="1.5"><path d="M7 13l5 5 5-5M7 6l5 5 5-5"/></svg>
</div>
</div>

<div id="education" class="section-wrapper">
<h2 class="section-title" data-aos="fade-up">Education</h2>

<div class="bento-card" style="width: 100%; max-width: 900px; padding: 50px 40px; text-align: left;" data-aos="zoom-in">

<div class="edu-list">

<div class="edu-item">
<div class="edu-header">
<div class="edu-school">
Anhui University (AHU)
<span class="edu-degree-tag tag-phd">Ph.D. Candidate</span>
</div>
<div class="edu-time">Sept. 2023 - Present</div>
</div>

<div class="edu-major">
Electronic Science & Technology
</div>

<div class="edu-awards">
<div class="award-badge award-highlight" style="width: 100%;">
<i class="fa-solid fa-flask"></i> 
2025 Anhui Prov. Dept. of Edu. Ph.D. Research Project Grant
</div>
</div>
</div>

<div class="edu-item">
<div class="edu-header">
<div class="edu-school">
Anhui Science and Tech. Univ. (AHSTU)
<span class="edu-degree-tag tag-bach">Bachelor</span>
</div>
<div class="edu-time" style="color:#666; background:#f5f5f7;">Sept. 2019 - June 2023</div>
</div>

<div class="edu-major">
Optoelectronic Information Science & Engineering
</div>

<div class="edu-stats">
<div class="stat-box stat-gold">
<i class="fa-solid fa-trophy" style="color: #d97706;"></i>
Rank: 1 / 37
</div>
<div class="stat-box stat-gold">
<i class="fa-solid fa-star" style="color: #d97706;"></i>
GPA: 3.62 / 4.0
</div>
</div>

<div class="edu-awards">
<div class="award-badge award-highlight">
<i class="fa-solid fa-medal"></i> 
Ranked 1st in Entrance Exam (Prelim & Re-exam)
</div>

<div class="award-badge">
<i class="fa-solid fa-sack-dollar"></i> Full Scholarship
</div>
<div class="award-badge">
<i class="fa-solid fa-language"></i> CET-6
</div>
<div class="award-badge">
<i class="fa-solid fa-atom"></i> National Physics Competition (3rd Prize)
</div>
<div class="award-badge">
<i class="fa-solid fa-user-graduate"></i> Outstanding Graduate
</div>
</div>
</div>

</div>
</div>
</div>

<div id="research" class="section-wrapper">
<h2 class="section-title" data-aos="fade-up">Research</h2>

<div class="research-container">

<div class="paper-card" data-aos="fade-up">
<div class="paper-img-wrapper">
<img src="/images/paper3.jpg" class="paper-img" alt="LADNet">
</div>
<div class="paper-content">
<div class="paper-meta">
<span class="journal-tag">Applied Soft Computing</span>
<span class="year-tag">2025</span>
</div>
<h3 class="paper-title">
LADNet: A wheat scab detection network based on lightweight architecture and logic-driven channel perception distillation
</h3>
<p class="paper-authors">
<span class="my-name">Zihao Yang</span>, Wenxia Bao, Maomao Qing, Xianjun Yang
</p>
<div class="paper-actions">
<a href="https://ieeexplore.ieee.org/abstract/document/10737383/" target="_blank" class="action-btn btn-pdf">
<i class="fa-solid fa-file-pdf"></i> Paper
</a>
<a href="https://ieeexplore.ieee.org/abstract/document/10737383/" target="_blank" class="action-btn btn-code">
<i class="fa-brands fa-github"></i> Code
</a>
</div>
</div>
</div>

<div class="paper-card" data-aos="fade-up" data-aos-delay="100">
<div class="paper-img-wrapper">
<img src="/images/paper2.jpg" class="paper-img" alt="Domain Adaptive">
</div>
<div class="paper-content">
<div class="paper-meta">
<span class="journal-tag">Comp. & Elec. in Agri.</span>
<span class="year-tag">2025</span>
</div>
<h3 class="paper-title">
A Domain Adaptive Wheat Scab Detection Method for UAV Images
</h3>
<p class="paper-authors">
Wenxia Bao, <span class="my-name">Zihao Yang</span>, Maomao Qing, Xianjun Yang
</p>
<div class="paper-actions">
<a href="https://www.sciencedirect.com/science/article/pii/S1568494625015716" target="_blank" class="action-btn btn-pdf">
<i class="fa-solid fa-file-pdf"></i> Paper
</a>
<a href="https://www.sciencedirect.com/science/article/pii/S1568494625015716" target="_blank" class="action-btn btn-code">
<i class="fa-brands fa-github"></i> Code
</a>
</div>
</div>
</div>

<div class="paper-card" data-aos="fade-up" data-aos-delay="200">
<div class="paper-img-wrapper">
<img src="/images/paper1.jpg" class="paper-img" alt="IAE-SDNet">
</div>
<div class="paper-content">
<div class="paper-meta">
<span class="journal-tag">IEEE TGRS</span>
<span class="year-tag">2024</span>
</div>
<h3 class="paper-title">
IAE-SDNet: An End-to-End Image Adaptive Enhancement and Wheat Scab Detection Network Using UAV
</h3>
<p class="paper-authors">
Wenxia Bao, <span class="my-name">Zihao Yang</span>, Penfei Zhang, Genshen Hu, Linsheng Huang, Xianjun Yang.
</p>
<div class="paper-actions">
<a href="https://ieeexplore.ieee.org/abstract/document/10737383/" target="_blank" class="action-btn btn-pdf">
<i class="fa-solid fa-file-pdf"></i> Paper
</a>
<a href="https://ieeexplore.ieee.org/abstract/document/10737383/" target="_blank" class="action-btn btn-code">
<i class="fa-brands fa-github"></i> Code
</a>
</div>
</div>
</div>

</div>
</div>

<div id="projects" class="section-wrapper">
<h2 class="section-title" data-aos="fade-up">Selected Projects</h2>

<div class="project-grid">

<div class="project-card" data-aos="fade-right">
<img src="/images/proj_0.jpg" class="project-thumb" alt="Military Target Detection">
<div class="project-body">
<h3 class="project-title">Remote Sensing Zero-Shot Detection & Lightweight Deployment</h3>
<div class="project-tags">
<span class="tech-tag tag-red">Zero-Shot Detection</span>
<span class="tech-tag tag-blue">Ascend NPU</span>
<span class="tech-tag tag-orange">Edge Computing</span>
</div>
<ul class="project-desc">
<li>Designed and implemented a deep learning-based zero-shot object detection model, utilizing cross-modal alignment technology to overcome the limitation of heavy annotation dependence for new military targets.</li>
<li>Led model optimization strategies such as quantization, pruning, and knowledge distillation for domestic Ascend NPUs, implementing the Pt→ONNX→OM pipeline for efficient inference on edge computing devices.</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-left">
<img src="/images/proj_1.jpg" class="project-thumb" alt="Dongfeng Defect Detection">
<div class="project-body">
<h3 class="project-title">Automotive Part Defect Detection (Dongfeng Line)</h3>
<div class="project-tags">
<span class="tech-tag tag-blue">Industrial Vision</span>
<span class="tech-tag tag-green">Defect Detection</span>
<span class="tech-tag tag-purple">PLC Integration</span>
</div>
<ul class="project-desc">
<li>Developed a deep learning vision model to precisely identify surface defects on automotive parts, such as scratches, cracks, deformations, and missing components.</li>
<li>Integrated industrial cameras, lighting, and PLC hardware; developed software modules for image acquisition, processing, result judgment, and data visualization, automating the inspection process.</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-right">
<img src="/images/proj_2.jpg" class="project-thumb" alt="361° Shoe Sole Gluing">
<div class="project-body">
<h3 class="project-title">361° Shoe Sole Automatic Gluing System</h3>
<div class="project-tags">
<span class="tech-tag tag-purple">3D Point Cloud</span>
<span class="tech-tag tag-orange">Robotics</span>
<span class="tech-tag tag-blue">Visual Guided</span>
</div>
<ul class="project-desc">
<li>Designed a fully automated gluing system meeting 361°'s specific process requirements, integrating sole positioning, visual guidance, and precision spraying.</li>
<li>Utilized binocular cameras with structured light for 3D point cloud reconstruction and instance segmentation to extract gluing areas, providing accurate paths for the robotic arm.</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-left">
<img src="/images/proj_3.jpg" class="project-thumb" alt="LLM Pest Classification">
<div class="project-body">
<h3 class="project-title">Provincial Natural Science Foundation — LLM-based Pest Classification</h3>
<div class="project-tags">
<span class="tech-tag tag-green">MLLM</span>
<span class="tech-tag tag-blue">RAG</span>
<span class="tech-tag tag-purple">Knowledge Graph</span>
</div>
<ul class="project-desc">
<li>Led the collection, cleaning, and fine-grained annotation of large-scale agricultural pest images, establishing a dataset of over 100k images across 60 categories.</li>
<li>Researched and applied transfer learning and efficient fine-tuning techniques for Visual Large Models, significantly improving pest recognition with limited samples.</li>
<li>Constructed a Multimodal Knowledge Graph for RAG (Retrieval-Augmented Generation) to reduce MLLM hallucinations and improve accuracy in agricultural Q&A.</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-right">
<img src="/images/proj_4.jpg" class="project-thumb" alt="Wheat Disease Detection">
<div class="project-body">
<h3 class="project-title">National Natural Science Foundation — Wheat Disease Recognition</h3>
<div class="project-tags">
<span class="tech-tag tag-orange">UAV Remote Sensing</span>
<span class="tech-tag tag-green">Domain Adaptation</span>
<span class="tech-tag tag-blue">Meta-Learning</span>
</div>
<ul class="project-desc">
<li>Identified tiny pests and diseases in UAV aerial images of wheat using deep learning algorithms.</li>
<li>Designed model optimization strategies based on domain adaptation and meta-learning, significantly enhancing generalization across different regions, climates, and planting conditions.</li>
</ul>
</div>
</div>

</div>
</div>

<div id="hobbies" class="section-wrapper">
<h2 class="section-title" data-aos="fade-up">Lifestyle & Interests</h2>

<div class="hobbies-grid">

<div class="hobby-card card-gaming" data-aos="zoom-in">
<i class="fa-solid fa-gamepad hobby-icon-large" style="color: #f59e0b;"></i>

<div style="z-index: 2;">
<h3 class="hobby-title">Overwatch</h3>
<p class="hobby-desc">
Hardcore Player.<br>
</p>
</div>

<div style="margin-top: auto; font-size: 0.9rem; color: #b45309; font-weight: 600;">
<i class="fa-solid fa-trophy"></i> Top 500 Player
</div>
</div>

<div class="hobby-card card-running" data-aos="zoom-in" data-aos-delay="100">
<i class="fa-solid fa-stopwatch hobby-icon-large" style="color: #0ea5e9;"></i>

<h3 class="hobby-title">Marathon</h3>
<p class="hobby-desc">Challenge limits, measure the city with footsteps.</p>

<div style="margin-top: auto;">
<div class="pb-label">Half Marathon PB</div>
<div class="pb-time">1:52:58</div>
</div>
</div>

<div class="hobby-card" data-aos="zoom-in" data-aos-delay="200">
<i class="fa-solid fa-mountain-sun hobby-icon-large"></i>
<h3 class="hobby-title">Active Life</h3>
<p class="hobby-desc">Enjoying the wild and the court.</p>

<div class="hobby-tags">
<span class="hobby-tag">
<i class="fa-solid fa-person-hiking" style="color: #166534;"></i> Hiking
</span>
<span class="hobby-tag">
<i class="fa-solid fa-feather" style="color: #166534;"></i> Badminton
</span>
</div>
</div>

<div class="hobby-card" data-aos="zoom-in" data-aos-delay="300">
<i class="fa-solid fa-headphones hobby-icon-large"></i>
<h3 class="hobby-title">Pop Culture</h3>
<p class="hobby-desc">Eason Chan, Jiang Wen, Wong Kar-wai.</p>

<div class="hobby-tags">
<span class="hobby-tag">
<i class="fa-solid fa-music" style="color: #7e22ce;"></i> Eason Chan
</span>
<span class="hobby-tag">
<i class="fa-solid fa-film" style="color: #c2410c;"></i> Movies
</span>
</div>
</div>

</div>
</div>

<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
<script>
AOS.init({
easing: 'ease-out-quart',
duration: 1200,
once: false,
mirror: true
});
</script>