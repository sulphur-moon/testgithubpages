<template>
  <div class="container">
    <div class="background-gradient"></div>
    
    <main class="content">
      <section class="hero">
        <div class="hero-content">
          <div class="avatar-container">
            <div class="avatar-ring"></div>
            <div class="avatar">
              <span class="avatar-text">你好</span>
            </div>
          </div>
          
          <h1 class="name">开发者姓名</h1>
          <p class="title">全栈开发工程师</p>
          
          <p class="bio">
            热爱编程与创新，专注于构建优雅、高效的 Web 应用。
            擅长 Vue.js、React、Node.js 等技术栈。
          </p>
          
          <div class="social-links">
            <a href="#" class="social-link" v-for="(link, index) in socialLinks" :key="index">
              {{ link.name }}
            </a>
          </div>
        </div>
      </section>
      
      <section class="skills">
        <h2 class="section-title">技术栈</h2>
        <div class="skills-grid">
          <div class="skill-card" v-for="(skill, index) in skills" :key="index">
            <div class="skill-icon">{{ skill.icon }}</div>
            <h3 class="skill-name">{{ skill.name }}</h3>
          </div>
        </div>
      </section>
      
      <footer class="footer">
        <p>© 2024 个人主页 · 用 ❤️ 构建</p>
      </footer>
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const socialLinks = ref([
  { name: 'GitHub', url: '#' },
  { name: 'LinkedIn', url: '#' },
  { name: '博客', url: '#' },
  { name: '邮箱', url: '#' }
])

const skills = ref([
  { name: 'Vue.js', icon: '⚡' },
  { name: 'React', icon: '⚛️' },
  { name: 'TypeScript', icon: '📘' },
  { name: 'Node.js', icon: '🟢' },
  { name: 'Python', icon: '🐍' },
  { name: 'Docker', icon: '🐳' }
])
</script>

<style scoped>
.container {
  position: relative;
  width: 100%;
  min-height: 100vh;
  overflow: hidden;
}

.background-gradient {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: 
    radial-gradient(ellipse at 20% 20%, rgba(120, 119, 198, 0.3), transparent 50%),
    radial-gradient(ellipse at 80% 80%, rgba(255, 119, 198, 0.2), transparent 50%),
    radial-gradient(ellipse at 40% 80%, rgba(99, 255, 222, 0.2), transparent 50%),
    linear-gradient(135deg, #0a0a0f 0%, #1a1a2e 100%);
  z-index: -1;
}

.content {
  position: relative;
  z-index: 1;
  max-width: 900px;
  margin: 0 auto;
  padding: 80px 24px;
}

.hero {
  text-align: center;
  padding: 60px 0;
}

.avatar-container {
  position: relative;
  width: 140px;
  height: 140px;
  margin: 0 auto 32px;
}

.avatar-ring {
  position: absolute;
  top: -4px;
  left: -4px;
  width: 148px;
  height: 148px;
  border-radius: 50%;
  background: linear-gradient(135deg, #667eea, #764ba2, #f093fb, #f5576c);
  background-size: 300% 300%;
  animation: gradient-rotate 4s ease infinite;
}

@keyframes gradient-rotate {
  0%, 100% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
}

.avatar {
  position: relative;
  width: 140px;
  height: 140px;
  border-radius: 50%;
  background: linear-gradient(135deg, #1a1a2e, #16213e);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 48px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4);
}

.avatar-text {
  background: linear-gradient(135deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.name {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 8px;
  background: linear-gradient(135deg, #fff 0%, #a5b4fc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.title {
  font-size: 1.25rem;
  color: #a5b4fc;
  margin-bottom: 24px;
}

.bio {
  max-width: 600px;
  margin: 0 auto 40px;
  font-size: 1.1rem;
  color: #94a3b8;
  line-height: 1.8;
}

.social-links {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
}

.social-link {
  padding: 12px 28px;
  border-radius: 50px;
  background: rgba(102, 126, 234, 0.15);
  border: 1px solid rgba(102, 126, 234, 0.3);
  color: #c7d2fe;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: rgba(102, 126, 234, 0.3);
  border-color: rgba(102, 126, 234, 0.6);
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
}

.skills {
  margin-top: 80px;
}

.section-title {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 40px;
  background: linear-gradient(135deg, #fff 0%, #a5b4fc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 20px;
}

.skill-card {
  padding: 28px 20px;
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.08);
  text-align: center;
  transition: all 0.3s ease;
}

.skill-card:hover {
  background: rgba(255, 255, 255, 0.06);
  border-color: rgba(102, 126, 234, 0.4);
  transform: translateY(-4px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
}

.skill-icon {
  font-size: 2.5rem;
  margin-bottom: 12px;
}

.skill-name {
  font-size: 1rem;
  font-weight: 600;
  color: #e2e8f0;
}

.footer {
  margin-top: 80px;
  text-align: center;
  padding-top: 40px;
  border-top: 1px solid rgba(255, 255, 255, 0.08);
  color: #64748b;
}

@media (max-width: 640px) {
  .name {
    font-size: 2rem;
  }
  
  .skills-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
