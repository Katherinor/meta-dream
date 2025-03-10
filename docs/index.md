---
# https://vitepress.dev/reference/default-theme-home-page
layout: home

hero:
  name: "糖炒栗子铺"
  text: "Meta Dream"
  tagline: 一个精神寄托之处，记录人间琐事；生活随笔；前端工程；
  image:
    src: /logo/trans_bg.png
    alt: Meta Dream
  actions:
    - theme: brand
      text: 开始阅读
      link: /markdown-examples
    - theme: alt
      text: 关于我
      link: /about

features:
  - icon: 🎨
    title: 前端工程
    details: Vue3、React、TypeScript等前端技术栈的学习笔记和实战经验分享
    link: /frontend
    linkText: 查看更多
  - icon: 📝
    title: 生活随笔
    details: 记录生活中的点点滴滴，分享有趣的故事和感悟
    link: /life
    linkText: 阅读故事
  - icon: 🎯
    title: 技术成长
    details: 分享学习经验、职业发展、技术视野等个人成长经历
    link: /growth
    linkText: 了解更多
  - icon: 🌈
    title: 兴趣爱好
    details: 分享生活中的兴趣爱好，让技术生活更有趣
    link: /hobby
    linkText: 一起分享

footer: true
---

<style>
:root {
  --vp-home-hero-name-color: transparent;
  --vp-home-hero-name-background: -webkit-linear-gradient(120deg, #bd34fe 30%, #41d1ff);
}

/* 页面容器 */
.VPHome {
  position: relative;
  min-height: 100vh;
  overflow: hidden;
}

/* 云雾效果容器 */
.fog-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: 0;
  pointer-events: none;
}

/* 多层云雾效果 */
.fog-layer {
  position: absolute;
  width: 100%;
  height: 100%;
  mix-blend-mode: overlay;
}

.fog-layer:nth-child(1) {
  background-image: 
    url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.005' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
  opacity: 0.6;
  filter: blur(40px);
  animation: fogMove 25s infinite alternate;
  background-size: 200% 200%;
  mix-blend-mode: soft-light;
  background-color: rgba(189,52,254,0.2);
}

.fog-layer:nth-child(2) {
  background-image: radial-gradient(
    circle at 50% 50%,
    rgba(189,52,254,0.25) 0%,
    rgba(65,209,255,0.2) 30%,
    transparent 70%
  );
  animation: fogPulse 15s infinite alternate;
  filter: blur(30px);
  mix-blend-mode: screen;
}

.fog-layer:nth-child(3) {
  background-image: 
    repeating-radial-gradient(
      circle at 50% 50%,
      rgba(189,52,254,0.15) 10%,
      rgba(65,209,255,0.12) 20%,
      transparent 50%
    );
  animation: fogFloat 20s infinite alternate-reverse;
  filter: blur(20px);
  mix-blend-mode: plus-lighter;
}

/* 云雾动画 */
@keyframes fogMove {
  0% {
    transform: translate(0, 0) scale(1);
  }
  50% {
    transform: translate(-10%, 5%) scale(1.1);
  }
  100% {
    transform: translate(10%, -5%) scale(1.05);
  }
}

@keyframes fogPulse {
  0% {
    opacity: 0.6;
    transform: scale(1);
  }
  50% {
    opacity: 0.8;
    transform: scale(1.05);
  }
  100% {
    opacity: 0.5;
    transform: scale(0.95);
  }
}

@keyframes fogFloat {
  0% {
    transform: translateY(0) rotate(0);
    opacity: 0.5;
  }
  50% {
    transform: translateY(-2%) rotate(1deg);
    opacity: 0.7;
  }
  100% {
    transform: translateY(2%) rotate(-1deg);
    opacity: 0.6;
  }
}

/* 内容层级调整 */
.VPHero {
  position: relative;
  z-index: 1;
}

/* 修改特性区域的背景和布局 */
.VPFeatures {
  position: relative;
  z-index: 1;
  background: transparent;
  padding: 2rem 0;
  margin-top: -2rem;
}

/* 移除之前的渐变遮罩层 */
.VPFeatures::after {
  display: none; /* 移除遮罩效果 */
}

/* 移除之前的云雾背景 */
.VPFeatures::before {
  display: none; /* 移除额外的背景效果 */
}

/* 优化卡片样式 */
.VPFeature {
  background: rgba(255, 255, 255, 0.5); /* 降低卡片背景不透明度 */
  backdrop-filter: blur(8px);
  border-radius: 12px;
  padding: 24px;
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 
    0 4px 6px rgba(189,52,254,0.05),
    0 0 20px rgba(255,255,255,0.2);
}

.VPFeature:hover {
  transform: translateY(-5px);
  background: rgba(255, 255, 255, 0.6);
  box-shadow: 
    0 8px 15px rgba(189,52,254,0.1),
    0 0 30px rgba(65,209,255,0.1);
  border-color: rgba(189,52,254,0.2);
}

/* 调整卡片容器样式 */
.VPFeatures .container {
  position: relative;
  z-index: 2;
  padding: 0 24px;
}

/* 调整链接颜色 */
.VPFeature .link {
  color: var(--vp-c-brand);
  opacity: 0.8;
  transition: opacity 0.2s;
}

.VPFeature:hover .link {
  opacity: 1;
}

/* 调整图标样式 */
.VPFeature .icon {
  background: linear-gradient(120deg, rgba(189,52,254,0.2), rgba(65,209,255,0.2));
  border-radius: 8px;
  padding: 8px;
  transition: all 0.3s ease;
}

.VPFeature:hover .icon {
  transform: scale(1.1) rotate(5deg);
  background: linear-gradient(120deg, rgba(189,52,254,0.3), rgba(65,209,255,0.3));
}

/* 文字效果 */
.VPHero .name,
.VPHero .text {
  text-shadow: 
    0 2px 15px rgba(189,52,254,0.5),
    0 0 30px rgba(65,209,255,0.4),
    0 0 45px rgba(189,52,254,0.3);
  animation: textGlow 8s ease-in-out infinite;
}

@keyframes textGlow {
  0%, 100% {
    text-shadow: 
      0 2px 15px rgba(189,52,254,0.5),
      0 0 30px rgba(65,209,255,0.4),
      0 0 45px rgba(189,52,254,0.3);
  }
  50% {
    text-shadow: 
      0 2px 20px rgba(189,52,254,0.6),
      0 0 40px rgba(65,209,255,0.5),
      0 0 60px rgba(189,52,254,0.4);
  }
}

/* 响应式调整 */
@media (min-width: 640px) {
  .fog-layer:nth-child(1) {
    filter: blur(60px);
  }
  .fog-layer:nth-child(2) {
    filter: blur(45px);
  }
}

@media (min-width: 960px) {
  .fog-layer:nth-child(1) {
    filter: blur(80px);
  }
  .fog-layer:nth-child(2) {
    filter: blur(60px);
  }
}
</style>

<script setup>
import { onMounted, onUnmounted } from 'vue'

onMounted(() => {
  // 创建云雾容器
  const fogContainer = document.createElement('div')
  fogContainer.className = 'fog-container'
  
  // 创建三层云雾
  for (let i = 0; i < 3; i++) {
    const fogLayer = document.createElement('div')
    fogLayer.className = 'fog-layer'
    fogContainer.appendChild(fogLayer)
  }
  
  // 添加到页面
  const home = document.querySelector('.VPHome')
  if (home) {
    home.insertBefore(fogContainer, home.firstChild)
  }
})

onUnmounted(() => {
  // 清理云雾效果
  const fogContainer = document.querySelector('.fog-container')
  fogContainer?.remove()
})
</script>
