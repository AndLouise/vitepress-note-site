---
# https://vitepress.dev/reference/default-theme-home-page
layout: home

hero:
  name: "雨过天晴"
  text: "And_Louise_Note"
  tagline: 空山新雨后，天气晚来秋
  actions:
    - theme: brand
      text: Markdown Examples
      link: /markdown-examples
    - theme: alt
      text: API Examples
      link: /api-examples
    - theme: alt
      text: 学习笔记
      link: /study

features:
  - title: 📚 技术学习笔记
    details: 开发学习记录
    link: /study-notes/technology
    linkText: 查看技术笔记
  - title: 📖 读书笔记
    details: 阅读书籍的精华摘录和个人思考
    link: /study-notes/books
    linkText: 查看读书笔记
  - title: ✍️ 生活日记
    details: 日常生活的记录、感悟和成长
    link: /diary/life
    linkText: 查看日记
---

<!-- ==================== -->
<!-- 以下是新增的自定义内容 -->
<!-- ==================== -->

<div class="custom-content">

## 🎯 最新动态

<div class="update-cards">
  <div class="update-card">
    <h3>📝 最近更新</h3>
    <ul>
      <li>✅ 完成 VitePress 网站搭建</li>
      <li>🔄 正在优化网站样式</li>
      <li>📚 准备添加技术文档</li>
    </ul>
  </div>

  <div class="update-card">
    <h3>🚀 计划功能</h3>
    <ul>
      <li>🔍 添加搜索功能</li>
      <li>🎨 自定义主题色</li>
      <li>📱 移动端优化</li>
    </ul>
  </div>
</div>

## 📂 内容分类

<div class="category-grid">
  <a href="/markdown-examples" class="category-card">
    <div class="category-icon">📖</div>
    <h3>文档教程</h3>
    <p>学习笔记和技术文档</p>
  </a>

  <a href="/api-examples" class="category-card">
    <div class="category-icon">⚙️</div>
    <h3>API 参考</h3>
    <p>接口文档和使用示例</p>
  </a>

  <a href="#" class="category-card">
    <div class="category-icon">💡</div>
    <h3>技术分享</h3>
    <p>经验总结和最佳实践</p>
  </a>

  <a href="#" class="category-card">
    <div class="category-icon">🔧</div>
    <h3>工具资源</h3>
    <p>实用工具和资源推荐</p>
  </a>
</div>

## 👋 关于本站

<div class="about-section">
  <p>这里是 <strong>And_Louise_Note</strong>，一个用于记录学习笔记和技术总结的知识库。</p>
  
  <div class="stats">
    <div class="stat-item">
      <span class="stat-number">10+</span>
      <span class="stat-label">篇文章</span>
    </div>
    <div class="stat-item">
      <span class="stat-number">5</span>
      <span class="stat-label">个分类</span>
    </div>
    <div class="stat-item">
      <span class="stat-number">持续</span>
      <span class="stat-label">更新中</span>
    </div>
  </div>
</div>

</div>

<style>
/* 自定义内容容器 */
.custom-content {
  max-width: 1200px;
  margin: 4rem auto;
  padding: 0 2rem;
}

/* 更新卡片样式 */
.update-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.update-card {
  background: var(--vp-c-bg-soft);
  border: 1px solid var(--vp-c-divider);
  border-radius: 12px;
  padding: 1.5rem;
  transition: all 0.3s ease;
}

.update-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
}

.update-card h3 {
  margin-top: 0;
  color: var(--vp-c-brand);
}

.update-card ul {
  padding-left: 1.2rem;
}

.update-card li {
  margin: 0.5rem 0;
  line-height: 1.6;
}

/* 分类网格 */
.category-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.category-card {
  display: block;
  background: var(--vp-c-bg-soft);
  border: 1px solid var(--vp-c-divider);
  border-radius: 12px;
  padding: 2rem;
  text-align: center;
  text-decoration: none;
  color: inherit;
  transition: all 0.3s ease;
}

.category-card:hover {
  background: var(--vp-c-brand);
  color: white;
  transform: translateY(-4px);
  box-shadow: 0 10px 30px rgba(62, 175, 124, 0.3);
  text-decoration: none;
}

.category-card:hover .category-icon {
  transform: scale(1.1);
}

.category-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
  transition: transform 0.3s ease;
}

.category-card h3 {
  margin: 1rem 0 0.5rem;
  font-size: 1.25rem;
}

.category-card p {
  margin: 0;
  opacity: 0.8;
  font-size: 0.9rem;
}

/* 关于区域 */
.about-section {
  background: linear-gradient(135deg, var(--vp-c-bg-soft) 0%, var(--vp-c-bg) 100%);
  border-radius: 16px;
  padding: 2.5rem;
  margin: 3rem 0;
  text-align: center;
}

.about-section p {
  font-size: 1.1rem;
  line-height: 1.7;
  margin-bottom: 2rem;
}

/* 统计数字 */
.stats {
  display: flex;
  justify-content: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.stat-item {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2rem;
  font-weight: bold;
  color: var(--vp-c-brand);
}

.stat-label {
  display: block;
  font-size: 0.9rem;
  opacity: 0.8;
  margin-top: 0.5rem;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .custom-content {
    padding: 0 1rem;
    margin: 2rem auto;
  }
  
  .update-cards,
  .category-grid {
    grid-template-columns: 1fr;
  }
  
  .stats {
    gap: 1.5rem;
  }
  
  .about-section {
    padding: 1.5rem;
  }
}

/* 标题样式优化 */
.custom-content h2 {
  border-bottom: 3px solid var(--vp-c-brand);
  padding-bottom: 0.75rem;
  margin-top: 3rem;
  font-size: 1.8rem;
}

.custom-content h2:first-child {
  margin-top: 0;
}
</style>