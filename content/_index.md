---
title: "Yang's Profile"
date: 2026-02-05
layout: "single"
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;800&display=swap" rel="stylesheet">
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">

<style>
/* =========================================
1. 全局设置
========================================= */
* { box-sizing: border-box; }

body, html {
margin: 0 !important;
padding: 0 !important;
width: 100% !important;
overflow-x: hidden !important;
font-family: 'Inter', -apple-system, BlinkMacSystemFont, "PingFang SC", sans-serif !important;
color: #1d1d1f !important;
scroll-behavior: smooth !important; /* 让跳转有丝滑的滚动动画，而不是生硬的跳变 */
scroll-padding-top: 90px !important; /* 关键！预留出比 Header 高度(60px)稍大的空间 */
}

/* 清除主题干扰 */
.single .content, .page, main, .container {
max-width: 100% !important;
width: 100% !important;
padding: 0 !important;
margin: 0 !important;
background: transparent !important;
}

/* 隐藏不需要的元素 (注意：我把 language-switch 从这里删掉了，这样它就能显示了) */
.theme-switch, #theme-check, .search-button, .search-mobile, .post-meta, .post-footer, .post-nav { display: none !important; }

/* =========================================
2. 💎 水晶导航栏 (Crystal Header) - 修复版
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
}

/* Logo */
.header-title a {
font-family: 'Inter', sans-serif !important;
font-weight: 800 !important;
font-size: 1.4rem !important;
color: #1d1d1f !important;
letter-spacing: -1px !important;
text-decoration: none !important;

}

/* 菜单项 */
.menu-item {
font-family: 'Inter', sans-serif !important;
font-size: 0.9rem !important;
font-weight: 600 !important;
color: #444 !important;
padding: 14px !important; 
transition: all 0.2s ease !important;
margin: 10 10px !important;
transform: translateX(50px) !important;
/* 确保菜单项本身没有边框干扰 */
border: none !important; 
}

.menu-item:hover {
color: #000 !important;
transform: translateX(48px) scale(1.2) !important;
}


/* 1. 彻底隐藏主题自带的语言切换器 (那个 buggy 的下拉菜单) */
.language-switch, .desktop .language-switch {
display: none !important;
}



/* ... (之后的代码) ... */
/* =========================================
3. 色彩桥接 (背景流)
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
4. 组件样式
========================================= */
.hero-title {
font-size: 5.5rem;
font-weight: 800;
letter-spacing: -3px;
line-height: 1.05;
background: linear-gradient(135deg, #111 0%, #666 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
margin-bottom: 25px;
}
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

/* 把 logo 提到更上层并单独移动 */
.header-title {
position: relative !important;   /* 使 left/transform 生效并能设置 z-index */
z-index: 1100 !important;        /* 高于 header 的默认层级 */
transform: translateX(-50px) !important; /* 向左移动（修改数值） */
/* 或者用 left: -28px; 但 transform 更平滑且兼容 hover transform */
}

/* =========================================
5. 新版个人简介 (Profile) 专用样式
========================================= */
/* 个人简介的主容器：在大屏上为左右分栏 */
.profile-container {
display: flex;
flex-direction: row;
gap: 60px; /* 左右栏间距 */
max-width: 1100px;
width: 100%;
align-items: flex-start; /* 顶部对齐 */
text-align: left; /* 强制左对齐，覆盖 section-wrapper 的居中 */
padding-top: 40px; /* 给导航栏留出更多空间 */
}

/* 左侧边栏：头像 + 名字 + 链接 */
.profile-sidebar {
flex: 0 0 280px; /* 固定宽度 */
display: flex;
flex-direction: column;
align-items: center; /* 侧边栏内部居中 */
text-align: center;
}

/* 右侧主内容：简介 + 研究方向 */
.profile-main {
flex: 1; /* 占据剩余空间 */
}

/* 头像样式更新 */
.profile-avatar {
width: 200px;
height: 200px;
border-radius: 50%;
object-fit: cover;
box-shadow: 0 20px 40px rgba(0,0,0,0.1);
border: 4px solid rgba(255,255,255,0.8); /* 增加一个白色边框增加质感 */
margin-bottom: 25px;
}

/* 名字和头衔 */
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
padding: 25px;
margin-bottom: 5px;
font-weight: 500;
}

/* 社交链接容器 */
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
color: #0071e3; /* 悬停变蓝 */
}

/* 右侧内容样式 */
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
background: #0071e3; /* 蓝色装饰条 */
border-radius: 3px;
}

.bio-text {
font-size: 1.05rem;
line-height: 1.8;
color: #444;
margin-bottom: 40px;
}

/* 研究方向列表 */
.research-list {
list-style: none;
padding: 0;
margin: 0;
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* 响应式网格 */
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

/* 移动端适配：竖向排列 */
@media (max-width: 768px) {
.profile-container {
flex-direction: column;
align-items: center;
gap: 40px;
}
.profile-sidebar {
width: 100%;
}
.profile-main {
width: 100%;
}
.research-list {
grid-template-columns: 1fr; /* 手机上一列 */
}
}
/* =========================================
6. 教育经历 (Education) - 增强版
========================================= */
.edu-list {
display: flex;
flex-direction: column;
gap: 40px; /* 学校之间的间距 */
}

.edu-item {
position: relative;
padding-left: 20px; /* 左侧留出一点空间 */
}

/* 左侧装饰线（可选，增加设计感） */
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
background: #0071e3; /* 当前学历用蓝色高亮 */
}

/* 学校头部 */
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
.tag-phd { background: #1d1d1f; color: #fff; } /* 硕博连读：黑底白字 */
.tag-bach { background: #f0f0f0; color: #666; } /* 本科：灰底灰字 */

.edu-time {
font-family: 'Inter', monospace; /* 数字用等宽字体更好看 */
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

/* 核心指标栏 (GPA/Ranking) */
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
border-color: #fcd34d; /* 金色边框 */
}

/* 荣誉列表 */
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
/* 特别高亮的荣誉 (考研第一/博士立项) */
.award-highlight {
background: #f0f9ff;
color: #0284c7;
border-color: #bae6fd;
font-weight: 600;
}

/* =========================================
7. 研究成果 (Research) - 优化版
========================================= */
.research-container {
display: flex;
flex-direction: column;
gap: 30px;
width: 100%;
max-width: 1100px; /* 整体卡片加宽一点 */
}

.paper-card {
display: flex;
background: rgba(255, 255, 255, 0.8); /* 背景稍微调白一点 */
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.9);
border-radius: 20px;
overflow: hidden;
transition: all 0.3s ease;
box-shadow: 0 10px 30px -10px rgba(0,0,0,0.05);
min-height: 260px; /* 给卡片一个最小高度 */
}

.paper-card:hover {
transform: translateY(-5px);
box-shadow: 0 25px 50px -12px rgba(0,0,0,0.12);
}

/* --- 左侧图片容器：加宽，完整显示 --- */
.paper-img-wrapper {
flex: 0 0 400px; /* 【改动】宽度拉长到 400px，给图片更多空间 */
background: #ffffff; /* 图片背景设为纯白，看起来更干净 */
display: flex;
align-items: center;
justify-content: center;
padding: 10px; /* 给图片留一点内边距 */
border-right: 1px solid rgba(0,0,0,0.05);
}

.paper-img {
width: 100%;
height: 100%;
object-fit: contain; /* 【关键】改为 contain，保证图片完整显示不被裁切 */
transition: transform 0.5s ease;
}

.paper-card:hover .paper-img {
transform: scale(1.03);
}

/* --- 右侧内容 --- */
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

/* --- 【关键】作者高亮样式 --- */
.my-name {
color: #0071e3; /* 蓝色文字 */
font-weight: 700;
background: rgba(0, 113, 227, 0.1); /* 浅蓝色背景 */
padding: 2px 8px; /* 内边距，撑开背景 */
border-radius: 6px; /* 圆角 */
border: 1px solid rgba(0, 113, 227, 0.2); /* 细边框 */
margin: 0 2px; /* 左右留一点空隙 */
}

/* 按钮组 */
.paper-actions {
display: flex;
gap: 15px;
}
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

/* 移动端适配：手机上还是上下排列 */
@media (max-width: 850px) {
.paper-card { flex-direction: column; }
.paper-img-wrapper { 
flex: none; 
width: 100%; 
height: 240px; /* 手机上图片高度 */
border-right: none;
border-bottom: 1px solid rgba(0,0,0,0.05);
}
}

/* =========================================
8. 项目经历 (Projects) - 详细版
========================================= */
.project-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); /* 自适应两列 */
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

/* 项目封面图 */
.project-thumb {
width: 100%;
height: 200px; /* 固定高度，保持整齐 */
object-fit: cover;
border-bottom: 1px solid rgba(0,0,0,0.05);
}

.project-body {
padding: 25px;
text-align: left;
flex: 1; /* 让内容撑满 */
}

/* 项目标题 */
.project-title {
font-size: 1.25rem;
font-weight: 700;
color: #111;
margin: 0 0 10px 0;
line-height: 1.4;
}

/* 技术栈标签容器 */
.project-tags {
display: flex;
flex-wrap: wrap;
gap: 8px;
margin-bottom: 15px;
}

/* 单个标签样式 */
.tech-tag {
font-size: 0.75rem;
padding: 3px 10px;
border-radius: 12px;
font-weight: 600;
text-transform: uppercase;
}
/* 几种不同的标签颜色，轮流使用 */
.tag-blue { background: #e0f2fe; color: #0284c7; }
.tag-green { background: #dcfce7; color: #166534; }
.tag-purple { background: #f3e8ff; color: #7e22ce; }
.tag-orange { background: #ffedd5; color: #c2410c; }
.tag-red { background: #fee2e2; color: #991b1b; }

/* 项目细节列表 */
.project-desc {
margin: 0;
padding-left: 18px; /* 列表缩进 */
color: #555;
font-size: 0.95rem;
line-height: 1.6;
}
.project-desc li {
margin-bottom: 8px;
}
.project-desc li::marker {
color: #0071e3; /* 列表圆点变蓝 */
}

/* 移动端适配 */
@media (max-width: 768px) {
.project-grid {
grid-template-columns: 1fr; /* 手机上一列 */
}
}

/* =========================================
9. 兴趣爱好 (Hobbies) - 活力版
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
height: 220px; /* 固定高度，保证整齐 */
}

.hobby-card:hover {
transform: translateY(-5px) scale(1.02);
background: rgba(255, 255, 255, 0.9);
box-shadow: 0 15px 35px rgba(0,0,0,0.1);
}

/* --- 卡片 1: 守望先锋 (Top 500 特效) --- */
.card-gaming {
/* 模拟守望先锋宗师段位的金/电光渐变背景 */
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
animation: rotate 10s linear infinite; /* 背景光旋转 */
pointer-events: none;
}
.rank-badge {
display: inline-block;
background: linear-gradient(90deg, #f59e0b, #fbbf24); /* 金色渐变 */
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

/* --- 卡片 2: 马拉松 --- */
.card-running {
background: linear-gradient(135deg, #fff 0%, #f0f9ff 100%);
}
.pb-time {
font-family: 'Inter', monospace; /* 等宽字体显示数字 */
font-size: 2.5rem;
font-weight: 800;
color: #0284c7;
letter-spacing: -2px;
margin-top: auto; /* 推到底部 */
}
.pb-label {
font-size: 0.9rem;
color: #666;
font-weight: 600;
text-transform: uppercase;
}

/* --- 通用内部样式 --- */
.hobby-icon-large {
font-size: 3rem;
margin-bottom: 15px;
opacity: 0.15; /* 做成大背景水印的效果 */
position: absolute;
right: 20px;
top: 20px;
}
.hobby-title {
font-size: 1.4rem;
font-weight: 700;
color: #111;
z-index: 1; /* 确保文字在背景之上 */
margin: 0;
}
.hobby-desc {
font-size: 1rem;
color: #555;
margin-top: 10px;
z-index: 1;
line-height: 1.5;
}

/* 标签云 (用于音乐/户外) */
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

/* 旋转动画 */
@keyframes rotate {
0% { transform: rotate(0deg); }
100% { transform: rotate(360deg); }
}

</style>

<div id="profile" class="section-wrapper">
<div class="profile-container">

<div class="profile-sidebar" data-aos="fade-right">
<img src="/images/avatar.jpg" class="profile-avatar" alt="Avatar">

<h1 class="profile-name">杨子豪</h1>
<div class="profile-status">安徽大学 · 博士在读</div>

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

<h2 class="bio-section-title">个人简介</h2>
<div class="bio-text">
<p>
你好！我是杨子豪，目前在安徽大学攻读电子科学与技术博士学位。
我致力于人工智能在通用视觉与农业领域的交叉研究，探索如何让机器“看懂”复杂的世界并进行逻辑推理。
我的目标是构建高效、精准且具备持续学习能力的智能视觉系统。
</p>
</div>

<h2 class="bio-section-title">研究方向</h2>
<ul class="research-list">
<li class="research-item">
<i class="fa-solid fa-cube"></i>
<div>
通用视觉模型<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(目标检测 / 语义分割)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-comments"></i>
<div>
视觉语言模型<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(多模态大模型 / 扩散多模态模型)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-brain"></i>
<div>
视觉复杂推理<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(视觉思维链 / 图像思考)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-compress"></i>
<div>
视觉令牌压缩<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(令牌剪枝 / 知识蒸馏)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-clock-rotate-left"></i>
<div>
视觉持续学习<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(记忆机制 / 快慢系统)</span>
</div>
</li>

<li class="research-item">
<i class="fa-solid fa-robot"></i>
<div>
具身智能<br>
<span style="font-size: 0.85rem; color:#666; font-weight:400;">(机器人学 / 自动驾驶)</span>
</div>
</li>
</ul>
</div>
</div>

<div style="position: absolute; bottom: 20px; animation: bounce 2s infinite; opacity: 0.4;">
<svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="#000" stroke-width="1.5"><path d="M7 13l5 5 5-5M7 6l5 5 5-5"/></svg>
</div>
</div>
</div>

<div id="education" class="section-wrapper">
<h2 class="section-title" data-aos="fade-up">教育经历</h2>

<div class="bento-card" style="width: 100%; max-width: 900px; padding: 50px 40px; text-align: left;" data-aos="zoom-in">

<div class="edu-list">

<div class="edu-item">
<div class="edu-header">
<div class="edu-school">
安徽大学 (AHU)
<span class="edu-degree-tag tag-phd">硕博连读</span>
</div>
<div class="edu-time">2023.09 - 至今</div>
</div>

<div class="edu-major">
电子科学与技术 (Electronic Science & Tech)
</div>

<div class="edu-awards">
<div class="award-badge award-highlight" style="width: 100%;">
<i class="fa-solid fa-flask"></i> 
2025 安徽省教育厅博士研究生科研项目立项
</div>
</div>
</div>

<div class="edu-item">
<div class="edu-header">
<div class="edu-school">
安徽科技学院 (AHSTU)
<span class="edu-degree-tag tag-bach">本科</span>
</div>
<div class="edu-time" style="color:#666; background:#f5f5f7;">2019.09 - 2023.06</div>
</div>

<div class="edu-major">
光电信息科学与工程
</div>



<div class="edu-stats">
<div class="stat-box stat-gold">
<i class="fa-solid fa-trophy" style="color: #d97706;"></i>
排名: 1 / 37
</div>
<div class="stat-box stat-gold">
<i class="fa-solid fa-star" style="color: #d97706;"></i>
GPA: 3.62 / 4.0
</div>
</div>

<div class="edu-awards">
<div class="award-badge award-highlight">
<i class="fa-solid fa-medal"></i> 
考研初复试全院第一录取
</div>

<div class="award-badge">
<i class="fa-solid fa-sack-dollar"></i> 全额奖学金
</div>
<div class="award-badge">
<i class="fa-solid fa-language"></i> CET-6
</div>
<div class="award-badge">
<i class="fa-solid fa-atom"></i> 物理竞赛国家级三等奖
</div>
<div class="award-badge">
<i class="fa-solid fa-user-graduate"></i> 优秀毕业生
</div>
</div>
</div>

</div>
</div>
</div>
<div id="research" class="section-wrapper">
<h2 class="section-title" data-aos="fade-up">研究成果</h2>

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
<h2 class="section-title" data-aos="fade-up">项目经历</h2>

<div class="project-grid">

<div class="project-card" data-aos="fade-right">
<img src="/images/proj_0.jpg" class="project-thumb" alt="Military Target Detection">
<div class="project-body">
<h3 class="project-title">遥感目标零样本检测及轻量化部署</h3>
<div class="project-tags">
<span class="tech-tag tag-red">Zero-Shot Detection</span>
<span class="tech-tag tag-blue">Ascend NPU</span>
<span class="tech-tag tag-orange">Edge Computing</span>
</div>
<ul class="project-desc">
<li>设计并实现基于深度学习的零样本目标检测模型，利用跨模态对齐技术，突破传统模型对新类别军事目标依赖大量标注数据的限制。</li>
<li>针对国产昇腾 NPU，主导模型量化、剪枝、知识蒸馏等优化策略，以 Pt→ONNX→OM 为主线，实现模型在边缘计算设备的高效推理。</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-left">
<img src="/images/proj_1.jpg" class="project-thumb" alt="Dongfeng Defect Detection">
<div class="project-body">
<h3 class="project-title">汽车生产线零件缺陷检测</h3>
<div class="project-tags">
<span class="tech-tag tag-blue">Industrial Vision</span>
<span class="tech-tag tag-green">Defect Detection</span>
<span class="tech-tag tag-purple">PLC Integration</span>
</div>
<ul class="project-desc">
<li>设计并实现基于深度学习的视觉检测模型，精准识别汽车零件的表面缺陷，如划痕、裂纹、变形、缺失等。</li>
<li>集成工业相机、光源、PLC 等硬件，开发图像采集、处理、结果判定及数据可视化软件模块，实现检测流程自动化，替代原有人工目检环节。</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-right">
<img src="/images/proj_2.jpg" class="project-thumb" alt="361° Shoe Sole Gluing">
<div class="project-body">
<h3 class="project-title">361° 鞋底自动涂胶系统设计</h3>
<div class="project-tags">
<span class="tech-tag tag-purple">3D Point Cloud</span>
<span class="tech-tag tag-orange">Robotics</span>
<span class="tech-tag tag-blue">Visual Guided</span>
</div>
<ul class="project-desc">
<li>设计满足 361° 品牌特定工艺要求的全自动涂胶系统方案，集成鞋底定位、视觉引导、精密喷涂，实现多种鞋型底部自动化涂胶。</li>
<li>通过双目相机结合结构光进行三维点云重建，通过实例分割算法，实现对鞋面涂胶区域点云提取，为机械臂提供准确的涂胶路径。</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-left">
<img src="/images/proj_3.jpg" class="project-thumb" alt="LLM Pest Classification">
<div class="project-body">
<h3 class="project-title">省自然科学基金 — 基于大模型的害虫分类</h3>
<div class="project-tags">
<span class="tech-tag tag-green">MLLM</span>
<span class="tech-tag tag-blue">RAG</span>
<span class="tech-tag tag-purple">Knowledge Graph</span>
</div>
<ul class="project-desc">
<li>主导大规模、高多样性农业害虫图像的采集、清洗与精细标注，建立包含 60 类、超 10 万张图像的首个面向大模型训练的专用害虫数据集。</li>
<li>研究并应用视觉大模型的迁移学习与高效微调技术，显著提升模型在有限标注样本下的害虫识别能力。</li>
<li>构建多模态知识图谱进行 RAG，减小 MLLM 的幻觉现象，提高 MLLM 在农业病害问答中的准确性。</li>
</ul>
</div>
</div>

<div class="project-card" data-aos="fade-right">
<img src="/images/proj_4.jpg" class="project-thumb" alt="Wheat Disease Detection">
<div class="project-body">
<h3 class="project-title">国家自然科学基金 — 基于深度学习的小麦病虫害识别</h3>
<div class="project-tags">
<span class="tech-tag tag-orange">UAV Remote Sensing</span>
<span class="tech-tag tag-green">Domain Adaptation</span>
<span class="tech-tag tag-blue">Meta-Learning</span>
</div>
<ul class="project-desc">
<li>基于深度学习算法，对无人机航拍的小麦图像上的微小病虫害进行识别。</li>
<li>设计基于域自适应与元学习的模型优化策略，显著提升模型对不同地域、气候、种植条件的泛化力。</li>
</ul>
</div>
</div>

</div>
</div>

<div id="hobbies" class="section-wrapper">
<h2 class="section-title" data-aos="fade-up">兴趣爱好</h2>

<div class="hobbies-grid">

<div class="hobby-card card-gaming" data-aos="zoom-in">
<i class="fa-solid fa-gamepad hobby-icon-large" style="color: #f59e0b;"></i>

<div style="z-index: 2;">
<h3 class="hobby-title">Overwatch</h3>
<p class="hobby-desc">
骨灰级玩家。<br>
</p>
</div>

<div style="margin-top: auto; font-size: 0.9rem; color: #b45309; font-weight: 600;">
<i class="fa-solid fa-trophy"></i> 500强选手
</div>
</div>

<div class="hobby-card card-running" data-aos="zoom-in" data-aos-delay="100">
<i class="fa-solid fa-stopwatch hobby-icon-large" style="color: #0ea5e9;"></i>

<h3 class="hobby-title">Marathon</h3>
<p class="hobby-desc">挑战自我，用脚步丈量城市。</p>

<div style="margin-top: auto;">
<div class="pb-label">Half Marathon PB</div>
<div class="pb-time">1:52:58</div>
</div>
</div>

<div class="hobby-card" data-aos="zoom-in" data-aos-delay="200">
<i class="fa-solid fa-mountain-sun hobby-icon-large"></i>
<h3 class="hobby-title">Active Life</h3>
<p class="hobby-desc">享受山野与球场的自由。</p>

<div class="hobby-tags">
<span class="hobby-tag">
<i class="fa-solid fa-person-hiking" style="color: #166534;"></i> 登山
</span>
<span class="hobby-tag">
<i class="fa-solid fa-feather" style="color: #166534;"></i> 羽毛球
</span>
</div>
</div>

<div class="hobby-card" data-aos="zoom-in" data-aos-delay="300">
<i class="fa-solid fa-headphones hobby-icon-large"></i>
<h3 class="hobby-title">Pop Culture</h3>
<p class="hobby-desc">陈奕迅，姜文，王家卫。</p>

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
<style>
@keyframes bounce {
0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
40% {transform: translateY(-10px);}
60% {transform: translateY(-5px);}
}
</style>

<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
<script>
AOS.init({
easing: 'ease-out-quart',
duration: 1200,
once: false,
mirror: true
});
</script>