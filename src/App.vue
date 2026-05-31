<script setup>
const navItems = [
  { label: '首页', href: '#home' },
  { label: '文章', href: '#posts' },
  { label: '研究', href: '#research' },
  { label: '关于', href: '#about' },
]

const featuredPosts = [
  {
    title: '从点云到位姿：LiDAR SLAM 的前端笔记',
    date: '2026-05-31',
    category: 'LiDAR SLAM',
    summary: '整理 ICP、特征提取与回环检测中的关键概念，给后续实验留下清晰入口。',
    readTime: '6 min',
  },
  {
    title: 'NeRF 在遥感场景中的表达能力',
    date: '2026-05-24',
    category: 'NeRF',
    summary: '记录多视角重建、稀疏视角约束与大尺度场景训练中的一些观察。',
    readTime: '8 min',
  },
  {
    title: 'Visual SLAM 学习路线：从特征法到直接法',
    date: '2026-05-12',
    category: 'Visual SLAM',
    summary: '用一篇文章串起相机模型、PnP、Bundle Adjustment 与后端优化。',
    readTime: '10 min',
  },
]

const researchTopics = [
  'Visual SLAM',
  'LiDAR SLAM',
  'NeRF',
  'Remote Sensing',
]

const timeline = [
  {
    label: '当前关注',
    text: '多传感器建图、三维重建与遥感影像理解。',
  },
  {
    label: '博客计划',
    text: '把论文阅读、实验复现和工程踩坑整理成可检索的笔记。',
  },
  {
    label: '长期目标',
    text: '构建一个面向机器人感知与空间智能的公开知识库。',
  },
]
</script>

<template>
  <div class="site-shell">
    <header class="site-header">
      <a class="brand" href="#home" aria-label="Jinghao Xia blog home">
        <span class="brand-mark">JX</span>
        <span>Jinghao Xia</span>
      </a>

      <nav class="nav-links" aria-label="Primary navigation">
        <a v-for="item in navItems" :key="item.href" :href="item.href">
          {{ item.label }}
        </a>
      </nav>
    </header>

    <main>
      <section id="home" class="hero-section">
        <div class="hero-copy">
          <p class="eyebrow">Personal Blog · Robotics Perception</p>
          <h1>记录 SLAM、NeRF 与遥感方向的研究思考</h1>
          <p class="hero-text">
            我是 Jinghao Xia，一名本科生。这里会持续整理论文阅读、实验复现、工程笔记与阶段性想法。
          </p>
          <div class="hero-actions">
            <a class="primary-button" href="#posts">阅读文章</a>
            <a class="ghost-button" href="#research">研究方向</a>
          </div>
        </div>

        <div class="hero-visual" aria-label="Research notebook illustration">
          <div class="orbit-map">
            <span class="node node-camera"></span>
            <span class="node node-lidar"></span>
            <span class="node node-map"></span>
            <span class="track track-one"></span>
            <span class="track track-two"></span>
          </div>
          <div class="visual-panel">
            <span class="panel-label">Research Stack</span>
            <strong>SLAM · 3D Vision · Remote Sensing</strong>
          </div>
        </div>
      </section>

      <section id="posts" class="section-block">
        <div class="section-heading">
          <p class="eyebrow">Latest Notes</p>
          <h2>最新文章</h2>
        </div>

        <div class="post-grid">
          <article v-for="post in featuredPosts" :key="post.title" class="post-card">
            <div class="post-meta">
              <span>{{ post.category }}</span>
              <time :datetime="post.date">{{ post.date }}</time>
            </div>
            <h3>{{ post.title }}</h3>
            <p>{{ post.summary }}</p>
            <span class="read-time">{{ post.readTime }}</span>
          </article>
        </div>
      </section>

      <section id="research" class="section-block split-section">
        <div>
          <p class="eyebrow">Research Interests</p>
          <h2>研究方向</h2>
          <p class="section-text">
            关注机器人感知、三维场景表达和遥感数据理解，希望把理论推导、代码实现和实验分析放在同一个语境里。
          </p>
        </div>

        <div class="topic-list">
          <span v-for="topic in researchTopics" :key="topic">{{ topic }}</span>
        </div>
      </section>

      <section id="about" class="section-block about-section">
        <div class="section-heading">
          <p class="eyebrow">About</p>
          <h2>关于这个博客</h2>
        </div>

        <div class="timeline">
          <article v-for="item in timeline" :key="item.label" class="timeline-item">
            <span>{{ item.label }}</span>
            <p>{{ item.text }}</p>
          </article>
        </div>
      </section>
    </main>
  </div>
</template>
